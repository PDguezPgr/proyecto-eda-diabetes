# 📝 Informe Técnico Integrado y Bitácora de Aprendizaje

**Proyecto:** Análisis Exploratorio de Datos (EDA) sobre Diabetes (BRFSS 2015)  
**Autor/a del presente tratamiento de datos:** PDguezPgr
**Entorno de Desarrollo:** Python 3.12.3 (`venv`), VS Code, Jupyter Notebook, Git/GitHub  
**Fecha de Consolidación:** 9 de noviembre de 2026  
**Repositorio GitHub:** https://github.com/PDguezPgr/proyecto-eda-diabetes
---

## 1. 🎯 Resumen Ejecutivo del Proyecto

El objetivo principal de este proyecto ha sido la realización de un **Análisis Exploratorio de Datos (EDA)** riguroso sobre el dataset epidemiológico **BRFSS 2015**, enfocado en identificar los factores sociodemográficos y metabólicos determinantes en la prevalencia de la diabetes.

A lo largo del ciclo de vida del proyecto, se estableció un flujo de trabajo reproducible que abarcó desde el aislamiento del entorno virtual en Python y la ingeniería de características epidemiológicas, hasta la creación de dashboards interactivos en Plotly y la gestión avanzada del control de versiones en GitHub.

---

## 2. 🚀 Evolución del Proyecto y Matización del Progreso

### Fase 1: Configuración del Entorno y Análisis Exploratorio Inicial
* **Entorno Virtual (`venv`):** Creación e independización de un entorno virtual en Python 3.12.3 para garantizar el aislamiento de paquetes y la reproducibilidad.
* **Librerías Base:** Configuración de la pila estándar de Data Science (`pandas`, `numpy`, `matplotlib`, `seaborn`, `ipykernel`).
* **Inspección de Datos:** Carga del dataset BRFSS, verificación de consistencia de tipos de datos y análisis de ausencia de valores nulos o inconsistencias.

### Fase 2: Ingeniería de Características (Feature Engineering) y Normalización
* **Segmentación Poblacional:** Creación de grupos etarios (`Age_Group`) y categorización de rangos de IMC (`BMI_Cat`).
* **Normalización Epidemiológica:** Cálculo de prevalencias en escala poblacional relativa (**casos por cada 1.000 habitantes / `Prevalencia_Pct`**), corrigiendo el sesgo introducido por tamaños muestrales dispares entre grupos.
* **Índices de Riesgo Compuesto:** Definición del `Risk_Score` integrando factores comórbidos (hipertensión, hipercolesterolemia, tabaquismo, sedentarismo).

### Fase 3: Transición a Visualización Interactiva (Plotly)
* **Visualización Estática:** Diagramas de distribución, boxplots y mapas de calor (Heatmaps) en `seaborn`.
* **Adopción de Plotly:** Implementación de gráficos interactivos multivariables (`px.bar`, `px.scatter`) para examinar simultáneamente Edad, Categoría de IMC y Prevalencia de Diabetes.
* **Formateo Avanzado:** Incorporación de etiquetas HTML (`<br>`) en los títulos de los gráficos para generar leyendas claras y evitar superposición visual en VS Code.
* **Exportación HTML:** Generación del archivo independiente `grafico_interactivo_diabetes.html` (`fig.write_html()`) para permitir exploración interactiva completa en cualquier navegador web.

### Fase 4: Depuración Técnica, Control de Versiones (Git) y Publicación
* **Resolución de Incompatibilidades:** Solución del `ModuleNotFoundError` al incorporar `plotly` y actualización de `nbformat` para soporte en el kernel de Jupyter.
* **Optimización de Celdas:** Eliminación de gráficos duplicados en VS Code mediante la configuración explícita de `fig.show(renderer="vscode")`.
* **Saneamiento de Git:**
  * Creación e implementación de `.gitignore` para omitir la carpeta pesada `venv/`.
  * Desvinculación de la memoria intermedia de Git con `git rm -r --cached venv`.
  * Desbloqueo de procesos colgados borrando el archivo temporal `.git/index.lock`.
* **Documentación Final:** Actualización de `requirements.txt`, refinamiento del `README.md` destacando las visualizaciones interactiva/normalizada e inclusión del informe en PDF (`Informe Ejecutivo - EDA Diabetes BRFSS 2015.pdf`).

---

## 3. 🛠️ Matriz Consolidada de Desafíos Técnicos y Soluciones

| Dimensión | Desafío Inicial | Causa Raíz | Solución Aplicada |
| :--- | :--- | :--- | :--- |
| **Ingeniería de Datos** | Sesgo en la comparación de conteos brutos de diabetes entre rangos de edad. | Disparidad en la cantidad total de encuestados por grupo etario. | Normalización epidemiológica a escala relativa (casos por 1.000 hab). |
| **Visualización** | Imposibilidad de inspeccionar 3+ dimensiones en gráficos estáticos sin saturación. | Limitación del espacio 2D plano en Matplotlib/Seaborn. | Implementación de Plotly Express interactivo y exportación modular en `.html`. |
| **Entorno Python** | `ModuleNotFoundError` de Plotly y error de `nbformat` al ejecutar la celda. | Falta de paquetes de integración entre Plotly y el Kernel del `venv`. | Instalación en `venv` de `plotly` y `nbformat`, y actualización de `requirements.txt`. |
| **Sintaxis Plotly** | `SyntaxError: invalid syntax` en la línea de `fig.update_layout(`. | Cierre incompleto del paréntesis principal de `px.bar(...)` en la línea anterior. | Corrección de la estructura sintáctica del bloque de código Plotly. |
| **Visualización Doble** | VS Code renderizaba dos gráficos calcados en la misma celda de notebook. | Imprimir `fig.show()` y dejar la variable `fig` suelta al final de la celda. | Dejar únicamente `fig.show(renderer="vscode")` en la última línea del bloque. |
| **Control de Versiones** | Repositorio saturado con miles de archivos de `venv/` y error `index.lock`. | Falta de `.gitignore` previo y bloqueo por proceso de Git colgado en segundo plano. | Configurar `.gitignore`, ejecutar `git rm --cached -r venv` y eliminar `.git/index.lock`. |
| **Visualización GitHub** | El archivo HTML interactivo no se previsualizaba directamente en la interfaz de GitHub. | Restricción de GitHub a la ejecución de JavaScript en HTML pesados (>MBs). | Incluir captura estática en el notebook e instrucciones explícitas en el `README.md`. |

---

## 4. 📌 Bitácora Personal y Aprendizajes Clave

### A. Conceptos Consolidados
- [x] **Selección y Carga de datos:** Selección de dataset de interes y volcado. Importación de librerias de trabajo.
- [x] **Consulta de dimensiones y visualización de primeras filas:** 
- [x] **Ejecución del paquete ipykernel:** Para conectar Python con el entorno de ejecución. Errores recurrentes.
- [x] **Bitacora y gestión de avances documentados:** Importancia de documentar cada una de las estapas mediante bitacora, Git y commits correspondientes con seguimiento del Readme.
- [x] **Tratamiento Epidemiológico de Datos:** Importancia de controlar variables de confusión (como la edad o el IMC) mediante segmentación y normalización a escalas relativas.
- [x] **Visualización Multidimensional:** Criterios para alternar entre gráficos estáticos (para informes impresos/PDF) e interactivos (para exploración de usuario).
- [x] **Gestión Rigurosa de Repositorios:** Mantenimiento de repositorios limpios sin incluir entornos de ejecución (`venv/`), asegurando la reproducibilidad mediante `requirements.txt`.

### B. Puntos para Profundizar en Futuros Proyectos
- [ ] **Despliegue de Dashboards Continuos:** Transicionar de exportaciones estáticas en HTML a aplicaciones web interactivas completas con **Streamlit** o **Dash**.
- [ ] **Modelado Predictivo:** Aplicar algoritmos de clasificación supervisada (`LogisticRegression`, `RandomForestClassifier`, `XGBoost`) para predecir la probabilidad individual de diabetes según el perfil de riesgo.
- [ ] **Automatización de Git:** Configuración de hooks de Git y flujos de integración continua (CI/CD) para validación automática de notebooks antes de cada push.

---
