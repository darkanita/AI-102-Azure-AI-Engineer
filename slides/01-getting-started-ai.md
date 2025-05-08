---
marp: true
paginate: true
theme: default
---

# 🧠 AI-102 - Lab 01
## Introducción a Azure AI Services

---

## 🎯 Objetivos del Laboratorio

- Crear un recurso de Cognitive Services en Azure.
- Usar el SDK de Python para consumir una API.
- Integrar Cognitive Services en una app sencilla.

---

## 🗓️ Agenda - Sesión 1 (2h 30min)

### 1. Bienvenida e Introducción (15 min)
- Objetivos de la certificación AI-102
- Rol del Azure AI Engineer

### 2. Configuración del Entorno (20 min)
- Acceso al repositorio GitHub
- Codespaces, Azure CLI, Python SDKs

### 3. Teoría: ¿Qué es Cognitive Services? (20 min)
- Categorías: Visión, Lenguaje, Voz, Decisión
- Formas de consumo: Portal, SDK, REST API, Containers

### 4. Laboratorio Guiado (60 min)
- Crear recurso en Azure
- Llamar API con SDK Python
- Crear app con Streamlit

### 5. Revisión y Preguntas (15 min)
- Validación de resultados
- Soporte individual

### 6. Reto opcional (20 min)
- Mejorar app para aceptar múltiples frases
- Añadir botón para limpiar entradas

---

## 🧠 ¿Qué es Azure Cognitive Services?

- APIs listas para usar con capacidades de IA.
- Categorías:
  - Visión (análisis de imágenes)
  - Lenguaje (análisis de texto, traducción)
  - Voz (reconocimiento y síntesis)
  - Decisión (moderación, personalización)

---

## ⚙️ Opciones de Consumo

- Portal de Azure
- SDKs (Python, .NET, JS, Java)
- REST API
- Contenedores Docker para uso local u offline

---

## 🔧 Crear el recurso en Azure

1. Ir al [Portal de Azure](https://portal.azure.com)
2. Buscar “Cognitive Services”
3. Crear el recurso (nombre, región, pricing F0)
4. Obtener endpoint y clave

---

## 🧪 Usar el SDK de Python

```python
from azure.ai.textanalytics import TextAnalyticsClient
from azure.core.credentials import AzureKeyCredential
```

- Crear cliente con `TextAnalyticsClient`
- Llamar a `analyze_sentiment()`

---

## 💻 Crear una App con Streamlit

- Captura texto del usuario
- Analiza sentimiento
- Muestra el resultado visualmente

```bash
pip install streamlit
streamlit run app.py
```

---

## ✅ Validación

- [ ] Recurso creado en Azure
- [ ] SDK probado con éxito
- [ ] App funcional

---

## 🧩 Reto del Estudiante (Bonus)

### Mejora tu app:
- [ ] Acepta una lista de frases
- [ ] Muestra resultados en una tabla
- [ ] Añade botón para limpiar el texto

> ¡Comparte tu resultado en la próxima clase!

---

## 📚 Recursos

- https://portal.azure.com
- https://learn.microsoft.com/azure/cognitive-services/
- https://microsoftlearning.github.io/AI-102-AIEngineer/
