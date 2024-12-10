# langchainaws

Este proyecto nos muestra una arquitectura para construir un software de preguntas y respuestas utilizando python, este software se basa en los generadores de recuperación aumentada RAG:

Los generadores RAG tienen 2 componentes:

1- Indexación: Una canalización para ingerir datos de una fuente e indexarlos. Esto suele ocurrir sin conexión.
2- Recuperación y generación: La cadena RAG real, que toma la consulta del usuario en tiempo de ejecución y recupera los datos relevantes del índice, luego los pasa al modelo.

##Arquitectura

![image](https://github.com/user-attachments/assets/97b075ac-2f40-4702-b868-782606cdd052) 
(Fuente: [Medium.com](https://medium.com/@Kishore-B/building-rag-application-using-langchain-openai-faiss-3b2af23d98ba))


## Explicación de arquitectura
-Este software se encuentra construido sobre cuadernos de Jypiter en Python y se puede resumir la arquitectura en 6 partes:

## 1. Carga de Datos
### Origen de Datos: 
- Los datos se extraen de diferentes fuentes, como archivos PDF, páginas web, documentos, entre otras cosas.
- Se utiliza un componente que convierte estos datos no estructurados en un formato procesable para los siguientes pasos.
- Divide los documentos en fragmentos más pequeños para facilitar el manejo y la recuperación más eficiente.
### 2. Indexación
- Cada fragmento de texto se transforma en un vector numérico mediante un modelo de embeddings. Estos vectores capturan el significado semántico de los fragmentos.
- Vector Store (Pinecone): Los embeddings se almacenan en Pinecone, una base de datos vectorial que permite búsquedas eficientes basadas en similitud.
### 3. Consulta del Usuario
- El usuario introduce una consulta o pregunta en lenguaje natural.
### 4. Recuperación
- El sistema utiliza la consulta del usuario para buscar en la base de datos vectorial los fragmentos más relevantes mediante búsquedas de similitud.
- Los fragmentos recuperados son aquellos que mejor responden a la consulta del usuario.
### 5. Generación de Respuesta
Los fragmentos recuperados se proporcionan como entrada al modelo de lenguaje. Este genera una respuesta combinando los datos recuperados y su conocimiento previo. Para el caso de esta arquitectura se empleo ChatGPT de OpenIA
### 6. Respuesta al Usuario
La respuesta generada por el modelo se envía de vuelta al usuario, respondiendo a su consulta de manera precisa y relevante.

## Paso a paso del taller

### Instalación de langchain en el entorno de Python
<img width="1344" alt="Screenshot 2024-12-10 at 7 19 56 AM" src="https://github.com/user-attachments/assets/2e82d9e4-5c06-4daf-aaf9-9f26ad67e182">

### Instalación del paquete langchain_comunity
<img width="1347" alt="Screenshot 2024-12-10 at 7 21 30 AM" src="https://github.com/user-attachments/assets/d21256f6-144c-489f-9f93-5a527e810984">

### Implementación de una arquitectura básica para una RAG (Retrieval-Augmented Generation)

<img width="1117" alt="Screenshot 2024-12-10 at 7 23 02 AM" src="https://github.com/user-attachments/assets/298a2f83-ac5a-4a9a-86ec-ad582536c93e">

### Importación de contenido al modelo

<img width="1362" alt="Screenshot 2024-12-10 at 7 25 12 AM" src="https://github.com/user-attachments/assets/97094472-8197-4311-b642-4443638af659">

### División de contenido original en fragmentos más pequeños
<img width="1344" alt="Screenshot 2024-12-10 at 7 26 56 AM" src="https://github.com/user-attachments/assets/a28d7fc1-ad72-4ce1-a15b-e3c73edc6c1d">

### Creación de base de datos vectorial con los fragmentos creados en el paso anterior

Se incluye una prueba de su funcionamiento.

<img width="1361" alt="Screenshot 2024-12-10 at 7 28 38 AM" src="https://github.com/user-attachments/assets/da9712e7-9e04-4c52-8b14-b0c196592e51">

### Instalación del proyecto langchain con open IA, No se incluyo el API Key por seguridad

<img width="1352" alt="Screenshot 2024-12-10 at 7 31 43 AM" src="https://github.com/user-attachments/assets/d1f2f225-8a0e-4da8-89df-77e213da3208">

### Prueba de una pregunta se extrae información de la base de datos vertorial

<img width="1351" alt="Screenshot 2024-12-10 at 7 35 57 AM" src="https://github.com/user-attachments/assets/e71ce087-681e-47d9-86b4-807cd299c0e9">

<img width="1348" alt="Screenshot 2024-12-10 at 7 36 20 AM" src="https://github.com/user-attachments/assets/6cc4a215-ba2a-441b-9e29-b57ec3d216ea">

### Instalación de las librerias para utilizar paincone

<img width="1356" alt="Screenshot 2024-12-10 at 7 36 49 AM" src="https://github.com/user-attachments/assets/44885cc0-6f66-4a60-a44a-9aa53f8f3633">

### Integración de PINECONE al proyecto no se incluye el API por seguridad

<img width="1350" alt="Screenshot 2024-12-10 at 7 37 42 AM" src="https://github.com/user-attachments/assets/cdb06eeb-1d45-453f-b4c6-c81bc58df242">

### Creación de BD Vectorial en Pinecone

<img width="1347" alt="Screenshot 2024-12-10 at 7 38 38 AM" src="https://github.com/user-attachments/assets/e2d0a612-6946-464f-b3a5-4096a481b889">

### Añadir documentos a la BD vectorial Incluye prueba

<img width="1308" alt="Screenshot 2024-12-10 at 7 40 10 AM" src="https://github.com/user-attachments/assets/768b4333-5427-4bdc-a8d8-d0e15c3b904b">

<img width="1338" alt="Screenshot 2024-12-10 at 7 40 28 AM" src="https://github.com/user-attachments/assets/976a959f-c5f9-463c-a216-0c1e09647283">


### Obteniendo resultados del ejercicio empleando OpenIA, Pinecone

<img width="1351" alt="Screenshot 2024-12-10 at 7 40 47 AM" src="https://github.com/user-attachments/assets/8369201b-a9dc-469e-8a4f-9667d844e80a">










