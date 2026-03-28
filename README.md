# AI Essay Grader para Profesores de Inglés

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python&logoColor=white)
![LangGraph](https://img.shields.io/badge/LangGraph-0.1-brightgreen)
![LangChain](https://img.shields.io/badge/LangChain-0.1-green)
![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4-orange?logo=openai&logoColor=white)

Herramienta de evaluación automatizada construida con **LangGraph** que lee redacciones de estudiantes (`.docx`), analiza la clase en su conjunto y genera feedback personalizado y calificaciones para cada estudiante — en segundos en lugar de horas.

---

## El problema

Como profesor de inglés, corregir tareas escritas cada semana es una de las tareas que más tiempo consumen fuera del aula. El flujo de trabajo anterior era así:

1. Descargar todas las entregas de los estudiantes desde Moodle una por una
2. Copiar y pegar cada redacción en ChatGPT manualmente
3. Copiar el feedback de vuelta en un documento para cada estudiante

Esta herramienta colapsa los tres pasos en una sola ejecución.

---

## Cómo funciona

```mermaid
graph TD
    A[📁 Cargar redacciones de estudiantes\n.docx desde carpeta] --> B[📋 Cargar rúbrica]
    B --> C[🔍 Análisis global de la clase\nerrores comunes · nivel medio · patrones]
    C --> D[💾 Guardar feedback_general.txt\npara sesión de revisión en clase]
    D --> E[📝 Evaluación individual\nalumno1 · alumno2 · alumno3 ...]
    E --> F[📄 Generar un .txt por estudiante\nnota · desglose de criterios · feedback personalizado]

```La decisión clave de diseño es la arquitectura en dos fases:

Análisis global primero — el LLM lee todas las redacciones juntas y construye una comprensión compartida del nivel de la clase, los errores comunes y los patrones destacados.
Evaluación individual con contexto — cada estudiante es evaluado utilizando ese contexto compartido como marco de referencia. Esto produce calificaciones consistentes y comparables en toda la clase (a diferencia de evaluar cada redacción de forma aislada, lo que introduce variabilidad en la corrección).

---

## Ejemplo de salida

**`evaluaciones/Tarea 1/alumno1.txt`**
```
NOTA FINAL: 8.5

DESGLOSE POR CRITERIOS:
- Intercultural content and awareness: 1.8 — Good understanding of cultural differences...
- Vocabulary range and appropriacy: 1.9 — Wide range used appropriately. Minor issues with...
- Grammar and sentence structure: 1.7 — Good control overall. Watch preposition use...
...

FEEDBACK PERSONALIZADO:
Well done on your intercultural guide. Try to avoid general statements and provide more
specific examples. Pay attention to preposition use and maintain a formal register throughout.
```

**`evaluaciones/Tarea 1/feedback_general.txt`** — Class-level analysis with common errors, example sentences from real essays, and corrections. Ready to turn into a review PowerPoint.

---

## Estructura del proyecto

```
.
├── Pipeline_Usos_de_la_IA.ipynb   # Main notebook: full pipeline
├── tareas/
│   ├── Rúbricas/          # Grading rubrics (.docx)
│   └── Tarea 1/           # Student submissions (.docx)
└── evaluaciones/
    └── Tarea 1/           # Generated output (one .txt per student + class feedback)
```

---

## Setup

**1. Clonar e instalar dependencias**
```bash
git clone <repo-url>
cd <repo-folder>
pip install python-dotenv python-docx langchain langchain-openai langgraph openai
```

**2. Configura tu API key**
```bash
cp .env.example .env
# Edit .env and add your OpenAI API key
```

**3. Añade tus archivos**
- Coloca las entregas de estudiantes .docx en tareas/Tarea 1/
- Coloca la rúbrica de evaluación .docx en tareas/Rúbricas/

**4. ejecuta el notebook**

Abre `Entrega.ipynb` y ejecuta todas las celdas de arriba a abajo. Los resultados aparecerán en evaluaciones/.

---

## Tech stack

| Technology | Role |
|---|---|
| **LangGraph** | Flujo de trabajo multi-nodo con estado (análisis global → evaluación individual) |
| **LangChain + OpenAI** | Integración con LLM (GPT-4) |
| **TypedDict** | Estado tipado compartido entre nodos del grafo |
| **python-docx** | Lectura de entregas de estudiantes y rúbricas en .docx |
| **python-dotenv** | Gestión segura de la API key |

---

## Escalabilidad y próximos pasos

- **Multi-format input**: añadir soporte para `.pdf`, `.txt` y fotos de trabajos escritos a mano (GPT-4 Vision)
- **Parallel evaluation**: fan-out con `Send` de LangGraph para evaluar a todos los estudiantes simultáneamente
- **Moodle integration**: usar la API REST de Moodle para descargar automáticamente las entregas y subir las notas
- **Student anonymization**: detección y reemplazo de nombres mediante NER antes de enviar a la API (cumplimiento RGPD)
- **Multi-subject support**: añadir un campo `asignatura` al estado y redirigir a prompts específicos por materia
