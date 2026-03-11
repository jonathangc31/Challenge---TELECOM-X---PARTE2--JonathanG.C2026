<h1 align="center"> 📊 Telecom X – Parte 2 </h1>
<h3 align="center">Predicción de Cancelación de Clientes (Churn Prediction)</h3>

---

## 🎯 Descripción del Proyecto

El objetivo principal de este proyecto es **predecir la cancelación de clientes (churn)** en Telecom X utilizando técnicas de Machine Learning.

La cancelación representa una pérdida directa de ingresos para la empresa, por lo que identificar clientes en riesgo permite:

- 📉 Reducir la tasa de cancelación  
- 📊 Tomar decisiones basadas en datos  
- 🎯 Implementar estrategias de retención efectivas  

## 🧹 Preparación de los Datos

### 🔎 Clasificación de Variables

Se clasificaron las variables en:

**📌 Numéricas**
- `tenure`
- `MonthlyCharges`
- `TotalCharges`
- `SeniorCitizen`

**📌 Categóricas**
- Género
- Tipo de contrato
- Método de pago
- Servicios contratados
- Facturación electrónica

### 🔄 Limpieza y Transformación

- ✔ Conversión de `TotalCharges` a formato numérico  
- ✔ Eliminación de valores nulos  
- ✔ Eliminación de `customerID` (no aporta valor predictivo)  

### 🔢 Codificación (Encoding)

Se aplicó **One-Hot Encoding** a variables categóricas:

```python
pd.get_dummies(drop_first=True)

## 📏 Normalización

Se utilizó **StandardScaler** para modelos sensibles a la escala:

- Regresión Logística  
- KNN  
- SVM  

Los modelos basados en árboles no requieren normalización, pero se aplicó para mantener consistencia metodológica.

## 🧹 Preparación de los Datos
## ✂ Separación de Datos

Los datos fueron divididos en:

- **80% entrenamiento**
- **20% prueba**

```python
train_test_split(test_size=0.2, stratify=y, random_state=42)

## 🤖 Modelos Implementados

### 1️⃣ Regresión Logística

Modelo lineal e interpretable ideal para clasificación binaria.

**Resultados obtenidos:**

- Accuracy: 0.80  
- Precision: 0.65  
- Recall: 0.53  
- F1-score: 0.58  

### 2️⃣ Árbol de Decisión

Modelo no lineal basado en reglas.

**Resultados obtenidos:**

- Accuracy: 0.78  
- Precision: 0.60  
- Recall: 0.52  
- F1-score: 0.55  

## 📊 Análisis Exploratorio de Datos (EDA)

Durante el análisis exploratorio se identificaron los siguientes patrones clave:

### 🔴 Factores que aumentan la probabilidad de cancelación:

- Baja antigüedad del cliente (tenure bajo)  
- Contratos mes a mes  
- Cargos mensuales elevados  

### 🟢 Factores que reducen la probabilidad de cancelación:

- Contratos anuales o de dos años  
- Mayor tiempo de permanencia  
- Mayor gasto acumulado  

## 📈 Visualizaciones Generadas

- Matriz de correlación (Heatmap)  
- Boxplot: Tenure vs Churn  
- Boxplot: TotalCharges vs Churn  
- Matriz de confusión de los modelos  

Estas visualizaciones permitieron validar patrones y detectar relaciones relevantes entre variables y cancelación.

## 🧠 Conclusiones

El modelo con mejor desempeño fue la **Regresión Logística**, mostrando mejor equilibrio entre precisión y recall.

Principales variables asociadas al churn:

- Tipo de contrato  
- Antigüedad del cliente  
- Cargos mensuales  

## 🎯 Estrategias de Retención Propuestas

- 📌 Incentivar la migración a contratos anuales  
- 📌 Implementar campañas preventivas para clientes nuevos  
- 📌 Ofrecer promociones a clientes con cargos elevados  
- 📌 Utilizar el modelo predictivo para detectar clientes en riesgo  

## 🛠️ Tecnologías Utilizadas

- Python  
- Pandas  
- NumPy  
- Matplotlib  
- Seaborn  
- Scikit-learn  
- Jupyter Notebook  

## ⚙️ Cómo Ejecutar el Proyecto

### 1️⃣ Instalar dependencias

```bash
pip install pandas numpy matplotlib seaborn scikit-learn

##🚀 Resultado Final

Este proyecto demuestra el flujo completo de un proyecto de Machine Learning:

Limpieza y transformación de datos

Análisis exploratorio

Modelado predictivo

Evaluación con métricas

Interpretación de variables

Propuesta estratégica basada en datos
