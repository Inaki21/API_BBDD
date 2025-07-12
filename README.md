# API_BBDD
Este proyecto consiste en una aplicación web que utiliza modelos de lenguaje (LLM) para generar respuestas a partir de consultas de los usuarios.

# Proyecto API - Asistente Virtual con IA Generativa

Este proyecto consiste en una **aplicación web** que utiliza **modelos de lenguaje (LLM)** para generar respuestas a partir de consultas de los usuarios. La aplicación está construida usando **Flask** en **Python** y se conecta a una base de datos **PostgreSQL** para almacenar un registro de las interacciones. El proyecto está contenido dentro de un contenedor **Docker** para facilitar su despliegue y ejecución.

## Tecnologías Utilizadas

- **Python 3.10**
- **Flask**: Framework web para la creación de la API.
- **psycopg2-binary**: Conector para interactuar con la base de datos **PostgreSQL**.
- **pgAdmin**: Herramienta para gestionar la base de datos.
- **Docker**: Para contenerizar la aplicación y facilitar su despliegue.
- **Groq**: Utilizado para la conexión a un modelo de lenguaje como **GPT**.

## Requisitos

1. **Docker**: Para ejecutar la aplicación en un contenedor.
2. **PostgreSQL**: Para gestionar la base de datos.
3. **pgAdmin**: Para gestionar la base de datos de manera visual.

## Instalación

### 1. Clonar el repositorio

Clona este repositorio en tu máquina local:

```bash
git clone https://github.com/tu_usuario/tu_repositorio.git
cd tu_repositorio



2. Configuración de PostgreSQL
Instalar PostgreSQL si no lo tienes:

Crear la base de datos:

Abre pgAdmin y conecta tu servidor de PostgreSQL.

Crea una nueva base de datos llamada chatbot_db.

Configurar la conexión en el archivo .env:

Crea un archivo .env en la raíz del proyecto y agrega las credenciales de la base de datos:

DB_HOST=localhost
DB_NAME=chatbot_db
DB_USER=postgres
DB_PASSWORD=tu_contraseña
GROQ_API_KEY=tu_api_key_de_groq

3. Configuración de Docker

Instalar Docker

Construir la imagen Docker:

Una vez que tengas todo configurado, construye la imagen de Docker con:

docker build -t chatbot-app .
Ejecutar el contenedor Docker:

Después de construir la imagen, ejecuta el contenedor con el siguiente comando:


docker run -p 5000:5000 chatbot-app
Esto iniciará la aplicación en http://localhost:5000.

Uso
Página principal:

Puedes acceder a la página principal de la aplicación en http://localhost:5000 desde tu navegador. Deberías ver el siguiente mensaje en formato JSON:

{
  "message": "¡La aplicación está funcionando!"
}
Hacer una consulta al modelo:

Envía una solicitud POST a http://localhost:5000/ask con un cuerpo JSON como el siguiente:


{
  "user_message": "¿Cuántos dedos hay en dos manos?"
}
La respuesta será algo similar a:


{
  "response": "En dos manos hay 10 dedos."
}
La interacción se guardará automáticamente en la base de datos PostgreSQL.

Estructura del Proyecto

/API_PROYECTO
    /source
        /PostgreSQL
            app.py            # Código de la aplicación Flask
            db.py             # Manejo de la base de datos PostgreSQL
            chatbot.py        # Interacción con el modelo de lenguaje
            Dockerfile        # Instrucciones para crear la imagen Docker
            requirements.txt  # Dependencias de la aplicación
        .env                  # Variables de entorno para la configuración

Dependencias
Las dependencias de la aplicación están listadas en el archivo requirements.txt:

flask
psycopg2-binary
python-dotenv
groq
Puedes instalar estas dependencias ejecutando:

pip install -r requirements.txt
Consideraciones
La aplicación está diseñada para funcionar tanto en entornos locales como contenedorizados usando Docker.

Si deseas ejecutar la base de datos de manera remota (por ejemplo, en AWS RDS), solo necesitas actualizar el archivo .env con los detalles de tu base de datos en la nube.

Contribuciones
Si deseas contribuir a este proyecto, por favor crea un pull request en GitHub. Asegúrate de seguir las buenas prácticas de desarrollo y mantener el código limpio y bien documentado.


