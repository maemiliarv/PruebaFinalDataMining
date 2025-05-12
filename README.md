Proyecto Final - Minería de Datos

Predicción de Cancelación de Suscripciones (Churn) - Interconnect

Descripción del proyecto
Este proyecto tiene como objetivo predecir la cancelación de suscripciones (churn) de clientes de la empresa Interconnect, permitiendo al equipo de marketing identificar usuarios en riesgo y aplicar estrategias de retención proactivas. Se ha desarrollado un modelo de machine learning siguiendo la metodología CRISP-DM, utilizando datos de contratos, servicios, características personales y hábitos de consumo.

Dataset utilizado
contract.csv — Información de contratos (tipo, duración, pagos).
internet.csv — Servicios de Internet y características técnicas.
personal.csv — Datos demográficos y de segmentación.
phone.csv — Servicios telefónicos y líneas asociadas.

Tecnologías y librerías
Python 3.10
Pandas, NumPy, Matplotlib, Seaborn
Scikit-learn
XGBoost
SHAP
Joblib

Estructura del repositorio
data/              # Datos originales (no subidos al repo)
model/             # Modelos entrenados (.joblib)
notebook/          # Notebook del proyecto
src/               # Código auxiliar (opcional)
README.md             # Este archivo
requirements.txt      # Dependencias del proyecto
.gitignore            # Exclusiones de git (data, .ipynb_checkpoints, etc.)

Metodología aplicada (CRISP-DM)
Business Understanding
Definición del problema, hipótesis clave y KPI (AUC-ROC, F1-score).
Data Understanding
Exploración inicial, análisis de nulos, outliers y supuestos.
Data Preparation
Unificación de datasets, limpieza, imputación de nulos, encoding, escalado, creación de nuevas features (Tenure).
Modeling
Entrenamiento de 3 algoritmos:
Logistic Regression (baseline)
Random Forest (ensemble)
XGBoost (boosting - mejor desempeño)
Validación con cross-validation (k=5) y manejo de desbalance con class_weight y scale_pos_weight.
Evaluation
Comparación de modelos con métricas AUC-ROC y F1-score. Interpretabilidad mediante SHAP y Feature Importance (Gain).
Deployment & Próximos pasos
Plan de despliegue en producción, monitoreo de drift, automatización de campañas y retraining trimestral.

Resultados destacados
Mejor modelo: XGBoost con AUC-ROC de 0.92 y F1-score de 0.80.
Variables más importantes: TotalCharges, Tenure, MonthlyCharges.
Recomendaciones de negocio: campañas personalizadas a clientes con churn_prob > 0.7.
💾
Reproducibilidad
Clonar el repositorio:
git clone https://github.com/tu-usuario/tu-repo-churn.git
cd tu-repo-churn
Instalar dependencias:
pip install -r requirements.txt
Ejecutar el notebook:
Abrir notebook/rivadeneira_maria_churn.ipynb y correr "Restart & Run All".