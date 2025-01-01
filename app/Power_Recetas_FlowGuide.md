# Power Automate: Intrucciones para la construcción del flujo
> [!NOTE]  
> Para facilitar su compresión se presentan los textos y guías en Castellano e Inglés

> Texts in Castilian Spanish. English as follows.

----------------
# Inicio. Creación del flujo.  
1. Abrir la web de **Microsoft Power Automate** [Link](https://make.powerautomate.com/)
2. Acceder al menú lateral izquiero y crear un flujo completamente nuevo (desde cero) del tipo "Flujo de nube automático".
3. Seleccionar el desencadenador **"Cuando Power Apps llama a un flujo versión 2"**
   
   ![image](https://github.com/user-attachments/assets/8be44043-96d1-4fc1-b2ef-6a39e2ae4afa)

4. Indicar los parámetros del tipo de entrada a "Texto" e indicar una variable a la que llamaremos **"mensajeusuario".**

   ![image](https://github.com/user-attachments/assets/644632a8-5770-41d2-a2e6-37f913eb6010)

----------  
# Creación de la receta a modo de texto (ChatGPT).  

> [!NOTE]  
> Crea antes de continuar con este paso una API Key en OpenAI.
> Puedes crear una desde este enlace [!Link](https://platform.openai.com/)


En esta parte nos centraremos en las 4 acciones que forman parte de esta sección, para llamar a ChatGPT, recuperar el texto de la receta que se representará en la Power Apps y preparar los datos (último paso de esta sección, para que se pueda pintar la receta con Dall-E)  


  
  ![image](https://github.com/user-attachments/assets/9ab46356-1de3-4a7d-80ff-fe7f8302d98b)

5. **Añadir una solicitud HTTP a OpenAI:**

   Añadimos la acción del tipo **"HTTP"** a la que renombraremos como **(HTTP Receta Texto)**
   Esta acción nos servirá para llamar a los servicios de ChatGPT disponibles en OpenAI.
   Dentro de la acción, rellenaremos los detalles de la URL, Método, Cabeceras y Cuerpo. Como el ejemplo de la imagen.

    **URL:** https://api.openai.com/v1/chat/completions  

    **Método:** POST  

    **Cabeceras:**  
      Authorization: Bearer seguido de Clave (API Key) proporcionada por OpenAI.
   
      Content-Type: application/json  
    
    **Body:**
      ```
       {"model": "gpt-4", "messages": [{
      "role": "system",
      "content": "Eres un chef experto. Crea la receta de forma económica. Incluye emoticonos. Gracias."},
      {"role": "user",
       "content": "@{triggerBody()}"}}
      ```
       
   (La expresión dinámica "Body" conecta esta acción con el desecadenador anterior, donde el usuario ha pedido una receta de algo).
     
   ![image](https://github.com/user-attachments/assets/920a79e4-6c1e-437f-8174-c7a018677b53)

     
6. **Procesar la respuesta de ChatGPT:**

   El resultado de ChatGPT será un objeto JSON.
   De modo que para poder interpretarlo, deberemos añadir la acción del tipo **"Parse JSON"**.
   
   En el **Contenido**, selecciona el cuerpo **(body)** de la respuesta HTTP.
   
   Define el **Esquema** del JSON automáticamente pegando un ejemplo de respuesta de ChatGPT. Un ejemplo podría ser:

 ```
   json

   {
     "id": "chatcmpl-123",
     "object": "chat.completion",
     "choices": [
    {
      "message": {
      "role": "assistant",
      "content": "Aquí está tu receta..."}}]
    }
```

7. **Extraer el texto de la receta**

     Añade ahora un nuevo paso del tipo **Comopose** o **Redactar** (dependerá uno u otro del idioma que tengas definido en tu entorno).
     Esto nos ayudará a crear una variable, donde almacenaremos la receta con origen ChatGPT. A esa variable, la llamaremos **TextoReceta**.
     Esta variable es **muy importante** pues la retomaremos en Power Apps.

     Asigna el valor:  ```body('Parse_JSON')?['choices'][0]['message']['content'] ```
