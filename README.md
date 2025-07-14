# 🧳 Travel Chatbot AI (Groq + Streamlit + Render)

Este proyecto implementa un asistente de viajes inteligente utilizando:

- **Groq API** (modelo LLaMA 3 70B) para procesamiento de lenguaje natural.
- **Streamlit** para el frontend web interactivo.
- **Render PostgreSQL** para almacenar preguntas y respuestas.

---

## 🚀 Características

- Interfaz web para hacer preguntas sobre viajes.
- Consultas procesadas por LLaMA 3 (Groq).
- Persistencia en PostgreSQL: historial de conversación guardado.
- Configuración fácil con `.env`.

---

## 🧠 Casos de uso

- Recomendaciones de destinos.
- Consejos sobre transporte y alojamiento.
- Ideas de actividades según la temporada o ubicación.
- Preguntas generales sobre viajes (documentación, clima, seguridad...).

---

## 🛠️ Instalación

### 1. Clona el repositorio


git clone https://github.com/tuusuario/travel-chatbot
cd travel-chatbot


### 2. Instala dependencias


### 3. Crea un archivo .env



### 4. Ejecuta el chatbot


### Estructura del proyecto

_API_POYECTO_VO
├── main.py              # Streamlit frontend
├── groq_client.py       # Comunicación con la API de Groq
├── db.py                # Conexión a PostgreSQL
├── models.py            # Modelo ORM para la tabla
├── create_table.sql     # Script SQL para crear la tabla
├── requirements.txt     # Lista de dependencias
├── .env                 # Claves de entorno (no subir a GitHub)
└── README.md            # Documentación


### SQL de la tabla


CREATE TABLE IF NOT EXISTS conversations (
    id SERIAL PRIMARY KEY,
    question TEXT NOT NULL,
    answer TEXT NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);



## Modelo LLM usado

LLaMA 3 70B (Versatile) desde la plataforma Groq.



## Contribuciones

¡Pull requests bienvenidos! Mejorar la UX, añadir autentificación, un admin panel, o exportación de logs.




