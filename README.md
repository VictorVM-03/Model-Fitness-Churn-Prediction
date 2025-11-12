# Model Fitness: Predicción de Churn y Segmentación de Clientes

## Contexto del Proyecto

La cadena de gimnasios Model Fitness busca combatir la alta tasa de deserción de clientes (churn) y desarrollar una estrategia de retención más efectiva. El objetivo de este proyecto es analizar los perfiles de los clientes para entender los factores que influyen en su decisión de irse y construir un modelo de Machine Learning que pueda predecir esta fuga de forma proactiva.

## Objetivos del Análisis

1.  **Predecir la Probabilidad de Churn:** Construir y evaluar un modelo de clasificación binaria para predecir la probabilidad de que un cliente abandone el gimnasio el próximo mes.
2.  **Identificar Factores Clave:** Analizar qué características del cliente (ej. contrato, antigüedad, asistencia) tienen mayor impacto en el churn.
3.  **Segmentar a los Clientes:** Utilizar clustering (K-Means) para crear "retratos" o segmentos de clientes e identificar los grupos con mayor y menor riesgo.
4.  **Generar Recomendaciones:** Proponer una estrategia de retención de clientes basada en los hallazgos del análisis.

## Herramientas Utilizadas

* **Python**
* **Pandas** y **NumPy** para la manipulación y limpieza de datos.
* **Matplotlib** y **Seaborn** para el análisis exploratorio de datos (EDA) y visualizaciones.
* **Scikit-learn** para construir los modelos de Machine Learning (Regresión Logística, Bosque Aleatorio) y para el Clustering (K-Means).
* **Jupyter Notebook** como entorno de trabajo.

## Hallazgos Clave y Modelado

### 1. Modelo Predictivo (Bosque Aleatorio)

El modelo de **Bosque Aleatorio (Random Forest)** fue el que obtuvo el mejor desempeño para la tarea de predicción, logrando un **Recall del 83.49%**. Esto lo convierte en una herramienta sumamente eficaz para identificar correctamente a la mayoría de los clientes que están en riesgo real de cancelación, permitiendo una intervención proactiva.

### 2. Segmentación de Riesgo (Clustering K-Means)

El análisis de clústeres identificó 5 segmentos de clientes, destacando tres grupos clave para la estrategia de negocio:

* **Clúster 3 (Riesgo Extremo):** Clientes con la tasa de Churn más alta **(>57%)**.
    * **Perfil:** Son clientes nuevos (antigüedad promedio de 2.1 meses), con contratos cortos y una frecuencia de asistencia muy baja (menos de 1 vez por semana).

* **Clúster 4 (Riesgo No Contactable):** Clientes con un Churn alto **(~27%)**.
    * **Perfil:** Su característica distintiva es **no haber proporcionado un número de teléfono**, lo que impide cualquier acción de retención directa (SMS, llamadas).

* **Clúster 2 (Lealtad):** El grupo más leal, con una tasa de Churn de solo **<2.2%**.
    * **Perfil:** Clientes con contratos de muy largo plazo (casi un año), mayor edad promedio y un alto gasto en servicios adicionales (cafetería, masajes), indicando un alto compromiso y rentabilidad.

## Recomendaciones Estratégicas de Retención

Basado en los hallazgos, se proponen tres estrategias de negocio:

**1. Incentivar el Compromiso a Largo Plazo:**
* **Acción:** Ofrecer descuentos escalonados o servicios premium (ej. 1 sesión de masaje gratuita) a los clientes que renueven o se inscriban en contratos de 6 o 12 meses, ya que la duración del contrato es un fuerte predictor de lealtad.
* **Acción:** Crear un "Programa de Lealtad" que recompense automáticamente a clientes con más de 4 meses de antigüedad (el perfil del Clúster 2).

**2. Intervención Temprana (Enfoque en Clúster 3):**
* **Acción:** Utilizar el modelo de Bosque Aleatorio para activar una **alerta automática** cuando un cliente (especialmente en sus primeros 3 meses) tenga una frecuencia de asistencia menor a 1 vez por semana.
* **Acción:** Al activarse la alerta, contactar al cliente ofreciendo una **sesión de entrenamiento personal gratuita** o una invitación a una clase grupal exclusiva para reengancharlos.

**3. Maximizar Valor y Captura de Datos (Enfoque en Clúster 2 y 4):**
* **Acción:** Promocionar "Paquetes de Bienestar" (membresía + servicios adicionales) al Clúster 2, ya que son los más rentables y propensos a comprar.
* **Acción:** Ofrecer un incentivo inmediato (ej. un cupón de cafetería) a los clientes del Clúster 4 a cambio de proporcionar o actualizar su número de teléfono, para poder incluirlos en las campañas de retención.

* ---
## 📂 Cómo Ejecutar este Proyecto

El análisis completo, desde la limpieza de datos hasta el modelado y la clusterización, se encuentra en el Jupyter Notebook principal.

1.  Clona este repositorio:
    ```bash
    git clone [https://github.com/VictorVM-03/Model-Fitness-Churn-Prediction.git](https://github.com/VictorVM-03/Model-Fitness-Churn-Prediction.git)
    ```
2.  Navega a la carpeta del proyecto.
3.  Abre el archivo `.ipynb` (ej. `Sprint_13.ipynb`) usando Jupyter Notebook o Jupyter Lab.
