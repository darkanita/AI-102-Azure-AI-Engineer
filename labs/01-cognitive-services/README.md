# 🧪 Laboratorio 01: Introducción a Azure Cognitive Services

## 🎯 Objetivo
Al finalizar este laboratorio, serás capaz de:
- Crear un recurso de Azure Cognitive Services usando la interfaz web.
- Realizar llamadas básicas a las APIs usando el SDK de Python.
- Integrar una llamada a Cognitive Services dentro de una aplicación Python sencilla.

## 📝 Prerrequisitos
- Cuenta activa de Azure.
- Entorno de desarrollo en GitHub Codespaces (ya configurado con Python y Azure SDKs).

---

## 1️⃣ Crear un recurso de Azure Cognitive Services (Portal de Azure)

1. Accede al [Portal de Azure](https://portal.azure.com/).
2. Haz clic en **Crear un recurso** > busca y selecciona **Cognitive Services**.
3. Completa el formulario:
   - **Nombre**: `ai102-cognitive-demo`
   - **Suscripción**: tu suscripción activa
   - **Grupo de recursos**: crea uno nuevo o usa uno existente
   - **Región**: selecciona una cercana
   - **Tipo de precio**: `F0` (gratis, si está disponible)
4. Revisa y crea el recurso.
5. Una vez creado, accede a él y copia el **Endpoint** y la **Key1**.

---

## 2️⃣ Realizar una solicitud a la API usando Python SDK

### Instala las dependencias (si es necesario):
```bash
pip install azure-ai-textanalytics
```

### Código base:
```python
from azure.core.credentials import AzureKeyCredential
from azure.ai.textanalytics import TextAnalyticsClient

endpoint = "<TU_ENDPOINT>"
key = "<TU_KEY>"

credential = AzureKeyCredential(key)
client = TextAnalyticsClient(endpoint=endpoint, credential=credential)

response = client.analyze_sentiment(documents=["Azure es una plataforma excelente para IA."])
for doc in response:
    print(f"Sentimiento: {doc.sentiment}, Confianza: {doc.confidence_scores}")
```

### Resultado esperado:
```
Sentimiento: positive, Confianza: positive=0.99, neutral=0.01, negative=0.0
```

---

## 3️⃣ Integración en una App Python sencilla

Crea un archivo `app.py`:
```python
import streamlit as st
from azure.core.credentials import AzureKeyCredential
from azure.ai.textanalytics import TextAnalyticsClient

st.title("Análisis de Sentimiento con Azure")
texto = st.text_input("Introduce un texto:")

if st.button("Analizar"):
    endpoint = "<TU_ENDPOINT>"
    key = "<TU_KEY>"
    client = TextAnalyticsClient(endpoint=endpoint, credential=AzureKeyCredential(key))
    result = client.analyze_sentiment(documents=[texto])[0]
    st.write(f"Sentimiento: {result.sentiment}")
    st.write(f"Confianza: {result.confidence_scores}")
```

### Ejecutar app con Streamlit:
```bash
pip install streamlit
streamlit run app.py
```

---

## ✅ Validación
- [ ] Has creado el recurso correctamente.
- [ ] Has ejecutado con éxito el SDK.
- [ ] Has integrado una llamada a Cognitive Services en una app básica.

---

## ⏱️ Tiempo estimado: 25-30 minutos