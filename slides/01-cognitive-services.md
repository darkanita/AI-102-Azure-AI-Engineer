---
marp: true
paginate: true
theme: default
---

# 🧠 AI-102 - Lab 01
## Introducción a Azure Cognitive Services

---

## 🎯 Objetivos del Laboratorio

- Crear un recurso de Cognitive Services en Azure.
- Usar el SDK de Python para consumir una API.
- Integrar Cognitive Services en una app sencilla.

---

## 🧠 ¿Qué es Azure Cognitive Services?

- Conjunto de APIs de IA listas para usar.
- Categorías principales:
  - Visión
  - Lenguaje
  - Voz
  - Decisión

---

## ⚙️ Opciones de Consumo

- Portal de Azure (interfaz gráfica)
- REST APIs / SDKs (.NET, Python, JS, Java)
- Contenedores Docker para ejecución local

---

## 🔧 Crear el recurso en Azure

1. Ir al [Portal de Azure](https://portal.azure.com)
2. Buscar “Cognitive Services”
3. Crear un recurso:
   - Nombre, región, pricing F0 si está disponible
4. Copiar **endpoint** y **clave** una vez creado

---

## 🧪 Usar el SDK de Python

```python
from azure.ai.textanalytics import TextAnalyticsClient
from azure.core.credentials import AzureKeyCredential
```

- Crear cliente con `TextAnalyticsClient`
- Llamar a `analyze_sentiment()` con una lista de documentos

---

## 💻 Integración en App Python (Streamlit)

- Crear `app.py`
- Pedir texto al usuario
- Mostrar resultado de análisis de sentimiento

**Librerías**:
```bash
pip install streamlit
```
**Ejecutar**:
```bash
streamlit run app.py
```

---

## ✅ Validación

- [ ] Recurso creado correctamente
- [ ] SDK probado con éxito
- [ ] App básica integrada y funcional

---

## 🙋 Preguntas y Demo Guiada

- Abrir el Codespace
- Seguir los pasos del README del Lab 01

**Tiempo estimado**: 25-30 minutos

---

## 📚 Recursos

- https://portal.azure.com
- https://learn.microsoft.com/azure/cognitive-services/
- https://microsoftlearning.github.io/AI-102-AIEngineer/
