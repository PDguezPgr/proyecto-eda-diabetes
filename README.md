# 📊 Análisis Exploratorio de Datos (EDA) - Factores de Riesgo de Diabetes (BRFSS 2015)

Este repositorio contiene el **Análisis Exploratorio de Datos (EDA)** realizado sobre el dataset **BRFSS 2015** (Behavioral Risk Factor Surveillance System del CDC), orientado a identificar los principales factores de riesgo fisiológicos, demográficos y de estilo de vida asociados al diagnóstico de diabetes.

---

## 🎯 Objetivos del Proyecto

1. **Exploración Fisiológica y Demográfica:** Identificar los principales determinantes de la prevalencia de diabetes en una población de 253.680 registros.
2. **Feature Engineering:** Generar variables categóricas y compuestas (`Risk_Score`) que permitan capturar la acumulación de factores de riesgo metabólicos.
3. **Respuesta a Preguntas de Investigación:** Responder hipótesis cuantitativas clave mediante análisis estadístico y tablas agregadas (`groupby`, `agg`, `pivot_table`).

---

## 📂 Estructura del Repositorio

```text
├── data/
│   └── diabetes_health_indicators.csv #Dataset limpio de entrada
├── eda_diabetes.ipynb   # Cuaderno principal de Jupyter con EDA completo
├── requirements.txt     # Dependencias y librerías del proyecto
└── README.md            # Documentación principal del proyecto

🛠️ Tecnologías y Librerías Utilizadas
Python 3.x

    - Pandas: Manipulación, agregación y limpieza de datos.

    - NumPy: Operaciones vectorizadas y transformaciones.

    - Matplotlib & Seaborn: Visualización de distribuciones, análisis bivariado y matrices de correlación (heatmap).

💡 Hallazgos y Conclusiones Clave
    - Percepción de Salud (GenHlth): 
        La salud general percibida es uno de los predictores individuales más potentes de la diabetes ($r \approx 0.30$).

    - Comorbilidad Fisiológica (HighBP, HighChol, BMI): 
        La hipertensión arterial ($r \approx 0.27$), el índice de masa corporal ($r \approx 0.22$) y el colesterol elevado ($r \approx 0.21$) muestran fuerte coexistencia con la enfermedad.

    - Impacto del Feature Engineering (Risk_Score): 
        La combinación sintética de hipertensión, colesterol e IMC $\ge 30$ eleva la correlación lineal a $r \approx 0.38$, demostrando que el riesgo metabólico actúa por acumulación sinérgica.

    - Calidad de Datos y Outliers: 
        Se identificaron 2.181 registros atípicos (3,16%) en IMC correspondientes a obesidad severa/mórbida. Se decidió conservar la totalidad de la muestra (253.680 registros) por su validez clínica en encuestas epidemiológicas.

    🚀 Instrucciones de Instalación y Ejecución
    Seguir estos pasos para clonar y ejecutar el entorno de análisis localmente:

    1. Clonar el repositorio:
       git clone [https://github.com/PDguezPgr/proyecto-eda-diabetes.git](https://github.com/PdguezPgr/proyecto-eda-diabetes.git)
       cd proyecto-eda-diabetes 

    2. Crear y activar el entorno virtual:
    # En Git Bash (Windows)
       python -m venv venv
       source venv/Scripts/activate

    3. Instalar dependencias:
       pip install -r requirements.txt

    4. Abrir y ejecutar el notebook:
       Abrir VS Code o Jupyter Lab y ejecutar eda_diabetes.ipynb de arriba a abajo.

