# Power Automate: Intrucciones para la construcción del flujo
> [!NOTE]  
> Para facilitar su compresión se presentan los textos y guías en Castellano e Inglés
> Texts in Castilian Spanish. English as follows.

----------------
# Inicio.  
1. Abrir la web de **Microsoft Power Automate** [Link](https://make.powerautomate.com/)
2. Acceder al menú lateral izquiero y crear un flujo completamente nuevo (desde cero) del tipo "Flujo de nube automático".
3. Seleccionar el desencadenador **"Cuando Power Apps llama a un flujo versión 2"**
   
   ![image](https://github.com/user-attachments/assets/8be44043-96d1-4fc1-b2ef-6a39e2ae4afa)

4. Indicar los parámetros del tipo de entrada a "Texto" e indicar una variable a la que llamaremos **"mensajeusuario".**

  ![image](https://github.com/user-attachments/assets/644632a8-5770-41d2-a2e6-37f913eb6010)

5. Añadimos la accuón del tipo **"HTTP"** a la que renombraremos como **"HTTP Receta Texto)**
   Esta acción nos servirápara llamar a los servicios de ChatGPT disponibles en OpenAI.
   Dentro de la acción, rellenaremos los detalles de la URL, Método, Cabeceras y Cuerpo. Como el ejemplo de la imagen.

**URL:** https://api.openai.com/v1/chat/completions  

**Método:** POST  

**Cabeceras:**  
    Authorization: Bearer seguido de Clave (API Key) proporcionada por OpenAI.
    Content-Type: application/json  
    
**Body:**
    {"model": "gpt-4", "messages": [{
      "role": "system",
      "content": "Eres un chef experto. Crea la receta de forma económica. Incluye emoticonos. Gracias."},
    {"role": "user",
     "content": "@{triggerBody()}"}}  
     
   ![image](https://github.com/user-attachments/assets/920a79e4-6c1e-437f-8174-c7a018677b53)
