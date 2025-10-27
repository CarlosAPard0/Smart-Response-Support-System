# Tutorial: Crear un Chatbot RAG con OpenAI (Proyecto de examen)

Este repositorio contiene un examen original y una versión tutorial refinada que demuestra cómo construir un chatbot con RAG (Retrieval-Augmented Generation) usando las APIs de OpenAI.

Contenido:
- `notebook.ipynb`: Notebook original del examen.
- `tutorial_notebook.ipynb`: Notebook tutorial, limpio y comentado (en español).
- `knowledge_base.csv`, `predefined_responses.json`, `chatbot_responses.json`: Datos de ejemplo (si están presentes).
- `requirements.txt`: Dependencias necesarias.

Requisitos previos:
- Python 3.9+
- Una clave de OpenAI configurada en la variable de entorno `OPENAI_API_KEY` si deseas ejecutar llamadas reales a la API.

Instalación (PowerShell):

```powershell
python -m venv .venv; .\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

Cómo usar:
1. Abre `tutorial_notebook.ipynb` en Jupyter / VS Code.
2. Si no tienes clave de OpenAI, ejecuta el notebook en modo `mock` para ver el flujo completo sin llamadas a la API.
3. Para ejecución real, exporta `OPENAI_API_KEY` y ejecuta las celdas.

Archivos creados por este asistente:
- `tutorial_notebook.ipynb`: Notebook tutorial con explicación por stages.
- `README.md`: Este archivo.
- `requirements.txt`: Lista de dependencias.

Siguientes pasos recomendados:
- Revisar y ajustar el umbral de similitud (SIMILARITY_THRESHOLD) según tu KB.
- Añadir pruebas unitarias para las funciones de similitud y preprocesamiento.
- Considerar un backend simple (FastAPI/Flask) para exponer el chatbot.
