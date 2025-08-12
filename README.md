# 📋 Informe Final: Modelado Predictivo de Churn

## 🔹 Introducción
Después del análisis exploratorio, se procedió a construir modelos predictivos para identificar qué clientes tienen mayor probabilidad de cancelar. Este modelo permitirá a Telecom X implementar estrategias de retención proactiva.

## 🔹 Preprocesamiento
- Se eliminó `customerID` por irrelevancia.
- Se aplicó One-Hot Encoding a variables categóricas.
- Se dividió el dataset 70/30 con estratificación.
- Se normalizaron datos para Regresión Logística.

## 🔹 Modelos Entrenados
1. **Regresión Logística**: Basado en probabilidad, sensible a escala.
2. **Random Forest**: Basado en árboles, robusto y fácil de interpretar.

## 🔹 Evaluación de Modelos
| Modelo | Exactitud | Recall (Churn) | F1-Score |
|-------|----------|----------------|----------|
| Regresión Logística | 0.80 | 0.58 | 0.65 |
| Random Forest | 0.79 | 0.68 | 0.72 |

> 🏆 **Random Forest** tuvo mejor recall y F1-score para la clase minoritaria (Churn), lo que lo hace más útil para detectar cancelaciones.

## 🔹 Variables más importantes
Según Random Forest:
1. `Contract_Two year` (negativo → reduce churn)
2. `tenure` (negativo → más tiempo, menos churn)
3. `MonthlyCharges` (positivo → más caro, más churn)
4. `Contract_Month-to-month` (positivo → alto riesgo)
5. `InternetService_Fiber optic` (positivo → asociado a churn)

## 🔹 Conclusiones estratégicas
- Los **clientes con contrato mensual** son los más riesgosos.
- El **precio mensual alto** y el **servicio de fibra óptica** están ligados al churn.
- La **fidelización** (contratos largos, mayor tenure) reduce la cancelación.

## 🔹 Recomendaciones
1. **Ofrecer descuentos** para convertir contratos mensuales a anuales.
2. **Programa de retención** para clientes con alto `MonthlyCharges`.
3. **Auditar servicio de fibra óptica**: ¿Problemas de calidad o soporte?
4. **Alertas proactivas** para clientes nuevos con bajo tenure y alto gasto.
