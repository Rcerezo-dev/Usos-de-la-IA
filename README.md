# Usos de la Inteligencia Artificial

Este repositorio recoge una serie de prácticas y ejercicios desarrollados en la asignatura **Usos de la Inteligencia Artificial**, orientada a comprender, aplicar y evaluar el uso de tecnologías de IA en distintos contextos educativos y profesionales.

El objetivo principal de la asignatura es que el alumnado adquiera una visión práctica y crítica del uso de la IA, entendiendo tanto su potencial como sus limitaciones.
En este caso, crearemos una carpeta con una tarea e alumnos, y en una segunda carpeta, añadiremos la rúbrica de evaluación que explica la tarea y cómo debe de ser evaluada.
La idea es que al leer todas las tareas a la vez, el LLM tome idea del contexto del nivel de la clase (fallos comunes, y demás) y evalúe todas las tareas siguiendo un criterio justo y coherente entre todas las tareas. Esta evaluación NUNCA deberá ser tomada como definitiva, ya que esta tarea corresponde a la figura del profesor. 
Como salida, el LLM nos dará un documento con los fallos más comunes, que el profesor puede usar para hacer un .ppt de fallos para explicar en clase, y un documento de evaluación individual para cada alumno. 

## Objetivos de la asignatura

- Comprender qué es la Inteligencia Artificial y sus principales áreas de aplicación.
- Utilizar herramientas de IA de forma responsable y eficaz.
- Aplicar soluciones basadas en IA a problemas reales.
- Analizar resultados y tomar decisiones basadas en datos.
- Reflexionar sobre los aspectos éticos, legales y sociales de la IA.

## Estructura del repositorio
Proyecto Usos de la IA
│
├── Entrega.ipynb
│   └── Notebook principal desde el que se ejecuta el flujo completo
│      de carga, análisis y generación de feedback.
│
├── tareas/
│   │
│   ├── Rúbricas/
│   │   └── rubrica tarea 1.docx
│   │      Documento de rúbrica utilizado como referencia pedagógica
│   │      durante el análisis.
│   │
│   └── Tarea 1/
│      ├── alumno1.docx
│      ├── alumno2.docx
│      └── alumno3.docx
│         Trabajos originales del alumnado en formato .docx.
│
├── evaluaciones/
│   │
│   │
│   └── Tarea 1/
│       ├── alumno1.txt
│       ├── alumno2.txt
│       ├── alumno3.txt
│       └── feedback_general.txt
│          Resultados de la evaluación organizados por tarea,
│          incluyendo análisis individual y análisis global del grupo.


## Contenidos trabajados

- Introducción a la Inteligencia Artificial
- IA generativa y modelos de lenguaje
- Procesamiento de lenguaje natural (NLP)
- Análisis y tratamiento de datos
- Automatización de tareas mediante IA
- Uso de IA en contextos educativos y profesionales
- Riesgos, sesgos y ética en la Inteligencia Artificial

## Tecnologías utilizadas

- **Python** como lenguaje principal de programación.
- **Jupyter Notebook** para el desarrollo y explicación de prácticas.
- **Bibliotecas de IA y datos**, como:
  - NumPy
  - pandas
  - scikit-learn
  - matplotlib / seaborn
- **Modelos y APIs de IA**, como:
  - Modelos de lenguaje (LLM)
  - APIs de servicios de IA
- **Git y GitHub** para control de versiones y entrega de trabajos.
- **Langraph**

## Requisitos

Para trabajar con este repositorio es necesario disponer de:

- Python 3.9 o superior.
- Un entorno virtual (recomendado).
- Las dependencias indicadas en el archivo `requirements.txt`.
- Acceso a internet para el uso de APIs o herramientas de IA en la nube, cuando sea necesario.

## Uso del repositorio

1. Clonar el repositorio.
2. Crear y activar un entorno virtual.
3. Instalar las dependencias con:
   ```bash
   pip install -r requirements.txt
