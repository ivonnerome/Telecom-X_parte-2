📊 Telecom X - Parte 2
Predicción de Cancelación de Clientes (Churn)


📌 1. Propósito del Proyecto

El objetivo principal de este análisis es predecir la cancelación de clientes (churn) en Telecom X utilizando variables relevantes del comportamiento y características contractuales de los usuarios.

A través de técnicas de análisis exploratorio de datos (EDA) y modelos de Machine Learning, se busca:

Identificar los factores que más influyen en la cancelación.

Construir modelos predictivos para anticipar clientes en riesgo.

Proponer estrategias de retención basadas en evidencia analítica.


🗂 2. Estructura del Proyecto
TelecomX-Churn-Parte2/
│
├── data/
│   ├── telecomX_tratado.csv
│
├── notebooks/
│   ├── TelecomX_Parte2_Modelado.ipynb
│
├── visuals/
│   ├── antiguedad_vs_churn.png
│   ├── cargo_mensual_vs_churn.png
│
├── README.md


📁 Descripción de Archivos

datos_tratados.csv
Dataset limpio y preprocesado listo para modelado.

TelecomX_Parte2_Modelado.ipynb
Cuaderno principal donde se realiza:

EDA

Preparación de datos

Modelado

Evaluación

Conclusiones

visuals/
Carpeta con visualizaciones generadas durante el análisis.



🧹 3. Preparación de los Datos

🔹 3.1 Clasificación de Variables
Variables Numéricas:

Antigüedad (tenure)

Cargo mensual

Cargo total

Variables Categóricas:

Tipo de contrato

Método de pago

Servicios adicionales

Género

Facturación electrónica

Etc.


🔹 3.2 Limpieza de Datos

Conversión de tipos incorrectos (ej. cargos totales como string → float).

Manejo de valores faltantes.

Eliminación de columnas irrelevantes (ej. ID cliente).



🔹 3.3 Codificación de Variables

Se aplicó:

One-Hot Encoding para variables categóricas nominales.

Transformación binaria para variables Sí/No.

Justificación:
Los modelos de Machine Learning requieren variables numéricas para operar correctamente.

🔹 3.4 Normalización

Se aplicó StandardScaler a variables numéricas para:

Evitar que variables con mayor escala dominen el modelo.

Mejorar el rendimiento de la Regresión Logística.

Random Forest no requiere normalización estricta, pero se mantuvo consistencia en el pipeline.

🔹 3.5 Separación de Datos

Se dividió el dataset en:

80% entrenamiento

20% prueba

train_test_split(test_size=0.2, random_state=42)

Justificación:
Permite evaluar el desempeño del modelo en datos no vistos y evitar sobreajuste.

🤖 4. Modelización

Se implementaron dos modelos principales:

🔸 Regresión Logística

Alta interpretabilidad.

Permite identificar dirección del impacto de cada variable.

Buen desempeño en recall (detección de churn).

🔸 Random Forest

Captura relaciones no lineales.

Detecta interacciones entre variables.

Identifica importancia relativa de variables.

📊 5. Análisis Exploratorio (EDA) e Insights

Durante el análisis se identificaron patrones clave:

📌 Antigüedad vs Churn

Clientes con menor antigüedad presentan mayor probabilidad de cancelación.

Los primeros meses representan etapa crítica de abandono.

📌 Cargo Mensual vs Churn

Clientes con cargos más altos muestran mayor densidad de cancelación.

Evidencia de sensibilidad al precio.

📌 Tipo de Contrato

Contratos mensuales presentan mayor churn.

Contratos anuales/bianuales reducen significativamente la cancelación.

🎯 Principales Factores de Cancelación

Baja antigüedad

Alto cargo mensual

Contrato mensual

Bajo número de servicios adicionales

Perfil de mayor riesgo:

Cliente nuevo + alto costo + contrato mensual

🚀 6. Estrategias Propuestas

Programas de onboarding para nuevos clientes.

Incentivos para migrar a contratos anuales.

Descuentos estratégicos en clientes de alto cargo mensual.

Cross-selling de servicios adicionales.

⚙️ 7. Instrucciones para Ejecutar el Proyecto
📌 Requisitos

Instalar las siguientes bibliotecas:

pip install pandas numpy matplotlib seaborn scikit-learn
📌 Ejecución

Clonar el repositorio:

git clone <url-del-repositorio>

Acceder a la carpeta del proyecto.

Abrir el notebook:

jupyter notebook

Ejecutar:

TelecomX_Parte2_Modelado.ipynb

Asegurarse de que el archivo telecomX_tratado.csv esté dentro de la carpeta data/.

📌 Conclusión

El análisis demuestra que la cancelación de clientes está fuertemente influenciada por factores económicos y de permanencia.

La combinación de modelos permitió identificar patrones estructurales y construir una base sólida para estrategias de retención basadas en datos.
