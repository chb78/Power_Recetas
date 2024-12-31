# Power Apps Recetas Navideñas con IA🎄 
(Text in Castilian Spanish. English as follows)

Este proyecto es una solución para explorar las posibilidades que ofrece la combinación de la plataforma de Microsoft, a través de Power Apps, Power Automate, la API de OpenAI y Azure Blob Storage para generar recetas navideñas únicas, acompañadas de imágenes generadas automáticamente mediante DALL-E.  Ideal para aprender cómo integrar inteligencia artificial con herramientas de Microsoft y construir aplicaciones útiles a posteriori.

La Power Apps de recetas se apoya en un flujo de Power Automate, que realiza las siguientes acciones:

1. Se recibe una solicitud desde Power Apps a través de un campo de texto para pedir una receta.
2. Power Automate procesa la solicitud para generar el texto a través de las APIs disponibles en OpenAI (ChatGPT) e imágenes (DALL-E).
3. Power Automate almacena las imágenes en Azure Blob Storage para su posterior representación en Power Apps.
4. Power Automate devuelve las URLs públicas de la imagen y el texto de la receta, con ingredientes y pasos para su representación en Power Apps.

El proyecto se complementa con un esqueleto a modo de ejemplo de la Power Apps y del flujo de Power Automate. (Package.ZIP)
Comparto igualmente un vídeo de funcionamiento de la solución y documento .PDF con los pasos se seguir a modo de guía.

![image](https://github.com/user-attachments/assets/e1e6a683-d014-4e47-acfc-e03e44dd83ce)


# ¿Por qué es útil esta solución?
El proyecto responde a un reto personal por conocer las posibilidades de integración entre los servicios en la nube de la plataforma de Microsoft y OpenAI.
Sirve como punto de partida para conocer los límites (a fecha de este documento), y potenciales mejoras así como intercambio de conocimiento.
A lo largo de la construcción de la solución, he podido detectar que Power Automate necesita de algunos pasos (triggers) para poder realizar acciones, apoyadas en código. (Bajo código convertido en expresiones dinámicas)
De manera que se descubre que no todo es "conectar y listo". Pero puede ser fácilmente aprendido por cualquier persona interesada en este tipo de proyectos.


# ¿Por dónde empezar?
Para este proyecto se pueden utilizar las siguientes tecnologías y con sesiones de 30 días de prueba. Más adelante, se puede pasar a planes de pago con el objetivo de encontrar un caso de uso adecuado o hacer evolucionar la solución.
Las tecnologías y licencias utiliados son:
1. Microsoft Power Apps. 
2. Microsoft Automate.
3. Microsoft Azure Blobstorage.
4. OpenAI a través de ChatGPT y Dall-E.

![image](https://github.com/user-attachments/assets/f85d7e87-925a-43b9-8297-e1c66c30cb47)

![image](https://github.com/user-attachments/assets/246a6c14-260b-4fbc-bf31-b3a9dcc8c7f3)


# Power Apps Christmas Recipes with AI 🎄
<a name="Christmas Recipes with AI"></a>
This project is a solution designed to explore the possibilities offered by Microsoft's platform through the integration of Power Apps, Power Automate, OpenAI API, and Azure Blob Storage. It generates unique Christmas recipes accompanied by images automatically created using DALL-E. This is an ideal way to learn how to integrate artificial intelligence with Microsoft tools and build useful applications for future use.

The Power Apps recipe solution relies on a Power Automate flow that performs the following actions:

1. A request is received from Power Apps via a text field to ask for a recipe.
2. Power Automate processes the request to generate text using the APIs available from OpenAI (ChatGPT) and images (DALL-E).
3. Power Automate stores the images in Azure Blob Storage for subsequent representation in Power Apps.
4. Power Automate returns the public URLs of the image and the recipe text, including ingredients and steps, for representation in Power Apps.

The project includes a sample skeleton of the Power Apps and the Power Automate flow. (Package.ZIP)  
Additionally, I am sharing a video demonstrating the solution in action and a PDF document with step-by-step instructions as a guide. Thank you for your help!

# Why Is This Solution Useful?
This project addresses a personal challenge to explore the integration possibilities between Microsoft’s cloud platform services and OpenAI. 
It serves as a starting point to understand the current limitations (as of the date of this document), identify potential improvements, and foster knowledge sharing. 
Throughout the development of this solution, I observed that Power Automate requires certain steps (triggers) to perform actions supported by code (low-code converted into dynamic expressions). 
This highlights that not everything is as simple as "connect and go," but it can easily be learned by anyone interested in this type of project.

# Where to Start?
For this project, you can use the following technologies, taking advantage of 30-day trial sessions. Later, you can transition to paid plans with the goal of identifying a suitable use case or evolving the solution.
The technologies and licenses used are:

1. Microsoft Power Apps.
2. Microsoft Power Automate.
3. Microsoft Azure Blob Storage.
4. OpenAI via ChatGPT and DALL-E.
