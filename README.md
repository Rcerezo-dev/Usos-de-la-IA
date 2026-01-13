 Usos de la IA en el ámbito educativo

Este repositorio forma parte del proyecto “Usos de la IA”, cuyo objetivo es explorar, diseñar e implementar herramientas basadas en modelos de lenguaje (LLM) para mejorar tareas docentes, especialmente en la enseñanza del inglés en Formación Profesional.

El foco principal del proyecto es automatizar procesos repetitivos como la corrección de tareas y la generación de feedback, manteniendo siempre un control pedagógico humano sobre los resultados.

 *Objetivos del proyecto*

- Reducir el tiempo dedicado a tareas repetitivas del profesorado.

-Automatizar la corrección y el análisis de trabajos escritos.

-Generar feedback útil, coherente y alineado con rúbricas reales.

-Explorar arquitecturas basadas en LLMs, prompting y flujos tipo LangGraph.

 Qué hace actualmente el proyecto

En su estado actual, el proyecto permite:

- Cargar trabajos de estudiantes desde archivos .docx.

- Cargar rúbricas desde documentos .docx.

Analizar:

nivel general del grupo

errores comunes

aspectos bien trabajados

diferencias entre trabajos más y menos logrados

Preparar la base para:

evaluación individual

análisis global

flujos paralelos de corrección

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

 Instalación y uso
1️ Clonar el repositorio

2️ Crear entorno virtual
python -m venv .venv


Activar en Windows:

.venv\Scripts\activate

3️ Abrir el archivo entrega.ipynb

4. Ejecutar todas las celdas 

 Contexto educativo

Proyecto desarrollado en el contexto de:

Formación Profesional

Enseñanza del inglés

Proyecto académico: Usos de la IA

Con un enfoque práctico, ético y realista del uso de la inteligencia artificial en el aula.
