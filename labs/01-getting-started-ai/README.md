# 🧪 Laboratorio 01: Preparación para un Proyecto de Desarrollo de IA

## 🎯 Objetivo
Familiarizarte con el ecosistema de servicios de Azure AI, explorar escenarios de aplicación, crear tu primer recurso de IA, interactuar con el SDK y construir una aplicación sencilla. Este laboratorio se alinea con el módulo **“Prepararse para el desarrollo de soluciones de IA en Azure”** del curso AI-102T00.

## 📝 Prerrequisitos
- Cuenta activa de Azure (con permisos para crear recursos)
- Acceso al portal: https://portal.azure.com

---

## 1️⃣ Explorar escenarios de Azure AI

1. Accede a [https://ai.azure.com](https://ai.azure.com) (**Azure AI Foundry**).
2. Explora las secciones:
   - Modelos (OpenAI, Azure OpenAI, modelos de Microsoft)
   - Experiencias preconfiguradas (resumen, clasificación, extracción, Q&A)
3. Piensa en un **caso de uso real** en el que puedas aplicar alguno de estos servicios (por ejemplo: análisis de sentimientos, transcripción de audio, extracción de datos de formularios).

✍️ **Tarea**: Escribe un párrafo describiendo un escenario de negocio en el que aplicarías una solución de IA.

---

## 2️⃣ Elegir y evaluar una experiencia

1. Elige una experiencia preconfigurada en Azure AI Foundry (por ejemplo, análisis de texto o detección de objetos).
2. Carga o ingresa tus propios datos.
3. Observa el resultado, evalúa su utilidad y precisión.

📝 **Actividad**:
- ¿Qué experiencia elegiste?
- ¿Qué entrada proporcionaste?
- ¿El resultado fue útil? ¿Qué mejorarías?

---

## 3️⃣ Crear tu primer recurso de Azure AI Services

1. Ve al portal de Azure: https://portal.azure.com
2. Crea un recurso de **Azure AI Services**:
   - Nombre: `ai102-ai-services`
   - Región más cercana
   - Tipo de precio: F0 (gratis, si está disponible)
3. Guarda tu **endpoint** y **clave**.

---

## 4️⃣ Interactuar con Azure AI Services desde código

Usa el SDK de Azure para interactuar con el recurso creado.

```python
from azure.core.credentials import AzureKeyCredential
from azure.ai.textanalytics import TextAnalyticsClient

endpoint = "<tu-endpoint>"
key = "<tu-key>"

client = TextAnalyticsClient(endpoint=endpoint, credential=AzureKeyCredential(key))
response = client.analyze_sentiment(documents=["Este curso es excelente."])
print(response[0].sentiment)
```

✅ Ejecuta el código y valida la respuesta.

---

## 5️⃣ Crear una aplicación sencilla con Streamlit

Envuelve la lógica anterior en una interfaz web rápida:

```python
import streamlit as st
from azure.ai.textanalytics import TextAnalyticsClient
from azure.core.credentials import AzureKeyCredential

st.title("Análisis de Sentimiento")
texto = st.text_input("Introduce una frase:")

if st.button("Analizar"):
    client = TextAnalyticsClient("<tu-endpoint>", AzureKeyCredential("<tu-key>"))
    result = client.analyze_sentiment([texto])[0]
    st.write(f"Sentimiento: {result.sentiment}")
```

Ejecuta con:
```bash
streamlit run app.py
```

---

## 6️⃣ Reto del Estudiante (Opcional)

💡 **Objetivo:** Extender la app para aceptar múltiples frases y mostrar un resumen visual.

### Tareas:
- Permitir ingresar varias frases (una por línea).
- Mostrar los resultados por frase en una **tabla** o **gráfico de barras**.

📝 **Sugerencia técnica**:
```python
frases = texto.splitlines()
resultados = client.analyze_sentiment(frases)
for r in resultados:
    st.write(r.sentiment)
```

✅ **Entrega sugerida**: subir el código a GitHub o compartir una captura del resultado.

---

## 7️⃣ Análisis y Reflexión Final

- [ ] Identificaste un escenario real de aplicación de IA
- [ ] Evaluaste una experiencia con tus propios datos
- [ ] Creaste un recurso funcional en Azure
- [ ] Interactuaste con Azure AI desde código
- [ ] Probaste una app básica funcional
- [ ] Completaste el reto opcional (si lo intentaste)

🧠 **Reflexiona**:
- ¿Cómo se alinea tu caso de uso con los servicios disponibles?
- ¿Qué obstáculos técnicos anticipas al implementar esta solución?

---

## ⏱️ Tiempo estimado: 75-90 minutos

## 📚 Recursos
- [Documentación Azure AI Services](https://learn.microsoft.com/azure/cognitive-services/)
- [Azure AI Foundry](https://ai.azure.com)
- [SDK Python](https://learn.microsoft.com/python/api/overview/azure/ai-textanalytics-readme)
- [Módulo Microsoft Learn - Prepararse para el desarrollo de IA](https://learn.microsoft.com/es-es/training/modules/prepare-azure-ai-development/)
