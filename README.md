# 📑 Challenge 3 ONE TelecomX Parte 2

## 🔍 Evaluación de Regresión Logística

---

* ✅ **Accuracy** : 0.8009
* 🎯 **Precision**: 0.6529
* 📡 **Recall**   : 0.5365
* ⚖️ **F1-score** : 0.5890

**Matriz de Confusión:**

```
[[1389  160]
 [ 260  301]]
```

**Reporte Completo:**

```
              precision    recall  f1-score   support

           0       0.84      0.90      0.87      1549
           1       0.65      0.54      0.59       561

    accuracy                           0.80      2110
   macro avg       0.75      0.72      0.73      2110
weighted avg       0.79      0.80      0.79      2110
```

---

## 🔍 Evaluación de Random Forest

---

* ✅ **Accuracy** : 0.7820
* 🎯 **Precision**: 0.6145
* 📡 **Recall**   : 0.4831
* ⚖️ **F1-score** : 0.5409

**Matriz de Confusión:**

```
[[1379  170]
 [ 290  271]]
```

**Reporte Completo:**

```
              precision    recall  f1-score   support

           0       0.83      0.89      0.86      1549
           1       0.61      0.48      0.54       561

    accuracy                           0.78      2110
   macro avg       0.72      0.69      0.70      2110
weighted avg       0.77      0.78      0.77      2110
```

---

## 📊 Comparación de Modelos

| Modelo              | Accuracy | Precision | Recall | F1-score |
| ------------------- | -------- | --------- | ------ | -------- |
| Regresión Logística | 0.8009   | 0.6529    | 0.5365 | 0.5890   |
| Random Forest       | 0.7820   | 0.6145    | 0.4831 | 0.5409   |

---

## 📌 Análisis Crítico

* **Mejor desempeño:** La **Regresión Logística** superó ligeramente al Random Forest en todas las métricas principales, especialmente en **accuracy** (0.80 vs 0.78) y **F1-score** (0.589 vs 0.541).

* **Overfitting/Underfitting:**

  * Ningún modelo presenta un **overfitting severo**, ya que la diferencia entre métricas en clases mayoritaria y minoritaria no es extrema.
  * Sin embargo, ambos modelos muestran **underfitting en la clase positiva (cancelación)**, ya que el recall (0.54 en LogReg, 0.48 en RF) indica que muchos clientes cancelados no fueron detectados.
  * Posibles causas: desbalance en los datos (clase negativa más numerosa) y complejidad insuficiente para capturar patrones de cancelación.

* **Acciones recomendadas:**

  * Aplicar **técnicas de balanceo** (SMOTE, undersampling, oversampling).
  * Afinar **hiperparámetros** en Random Forest para mejorar recall.
  * Considerar modelos más complejos (XGBoost, Gradient Boosting) o ensamblados.

---

## 🎯 Conclusión

* El modelo de **Regresión Logística** es el más adecuado en esta primera iteración por su mejor balance entre precisión y recall.
* La clase de **cancelación (1)** requiere mayor atención, ya que ambos modelos presentan baja sensibilidad en su detección.
* Factores clave que deben analizarse en profundidad: características relacionadas con la duración de la relación con el cliente, consumo de servicios y variables demográficas.

**Estrategia de Retención:**

1. Identificar clientes con **alto riesgo de cancelación** mediante el modelo de Regresión Logística.
2. Implementar campañas de **retención personalizada** en este segmento.
3. Aplicar **programas de fidelización** para aumentar la permanencia.
4. Continuar mejorando el modelo mediante balanceo de clases y ajuste de hiperparámetros.
