# 📈 Churn Prediction - Telecom X (Data Science Challenge)

Este proyecto tiene como objetivo predecir la cancelación de clientes (*churn*) en una empresa de telecomunicaciones utilizando técnicas avanzadas de Machine Learning. Fue desarrollado como parte del programa **Challenge ONE Data Science – Telecom X (Parte 2)**, con enfoque en la selección y evaluación de modelos explicativos y predictivos.

---

## 🧠 Objetivo

Desarrollar un modelo de clasificación binaria que prediga si un cliente va a cancelar o no el servicio, utilizando información demográfica, contractual y de comportamiento.

---

## 🧰 Tecnologías y Librerías

- Python 3
- Pandas, NumPy
- Scikit-learn
- XGBoost
- imbalanced-learn (SMOTE)
- SHAP
- Matplotlib, Seaborn
- Tabulate

---

## 🧪 Proceso de Trabajo

1. **Carga y limpieza de datos**
   - Eliminación de nulos (`account.Charges.Total`)
   - Codificación binaria y one-hot
   - Ingeniería de características (e.g., `Cuentas_Diarias`)

2. **Análisis exploratorio**
   - Correlaciones, boxplots, distribución de churn

3. **Balanceo de clases**
   - Aplicación de SMOTE solo sobre entrenamiento

4. **Normalización**
   - Aplicación de `StandardScaler` para modelos basados en distancia

5. **Modelado**
   - Regresión Logística
   - Random Forest
   - KNN
   - XGBoost
   - SVM (linear)

6. **Selección de variables**
   - RFE con Random Forest, XGBoost
   - Backward Selection automática basada en AUC

7. **Evaluación**
   - AUC, F1-Score, precisión, recall
   - Matriz de confusión
   - Interpretación con coeficientes, SHAP y permutación

---

## 📊 Resultados

| Modelo               | AUC     | F1 (Churn) | Variables Usadas                |
|----------------------|---------|------------|----------------------------------|
| Backward XGBoost     | 0.8202  | 0.5607     | Selección automática (25 vars)  |
| RFE XGBoost          | 0.8172  | 0.5591     | Top 10 por RFE                  |
| RFE Random Forest    | 0.8039  | 0.5399     | Top 10 por RFE                  |
| Regresión Logística  | 0.8453  | 0.5930     | Todas + escalado                |

> ✅ Se recomienda el modelo **XGBoost con selección backward**, por su equilibrio entre interpretabilidad y capacidad predictiva.

---

## 🔎 Principales variables asociadas a Churn

- `customer.tenure` (meses de permanencia)
- `account.Charges.Total` (gasto acumulado)
- `internet.InternetService_Fiber optic`
- `account.Contract_One year / Two year`
- `internet.TechSupport_Yes`
- `account.PaymentMethod_Electronic check`

---

## 💡 Propuestas de acción

- Ofrecer contratos más largos con beneficios escalonados.
- Detectar e intervenir a clientes nuevos con poco uso del servicio.
- Promover bundles para clientes con fibra óptica.
- Mejorar la accesibilidad al soporte técnico.
- Revisión de clientes con método de pago `Electronic check`.

---

## 📂 Estructura del Repositorio

├── data/ # Fuentes de datos (CSV)
├── notebooks/ # Notebooks en Colab o Jupyter
├── models/ # Modelos entrenados (opcional)
├── figures/ # Gráficos y visualizaciones
├── README.md # Este archivo
└── requirements.txt # Librerías necesarias (opcional)

## 📜 Licencia

Este proyecto es de uso libre para fines educativos y no comerciales.  
Créditos requeridos al reutilizar fragmentos del análisis o visualizaciones.

---

## 🤝 Contribuciones

Las sugerencias y mejoras son bienvenidas.  
Puedes abrir un issue o enviar un pull request si deseas colaborar.
