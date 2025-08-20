# Challenge-TelecomX
Análisis de Evasión de Clientes

## 🔹 1. Introducción
La empresa Telecom X enfrenta una **alta tasa de evasión de clientes (churn)**, lo que representa un desafío significativo para su rentabilidad y crecimiento. El objetivo de este análisis fue explorar los datos de los clientes para identificar los factores y patrones clave asociados con la cancelación del servicio.


## 🔹 2. Limpieza y Tratamiento de Datos
Para asegurar la calidad y fiabilidad del análisis, se realizó un proceso de preparación de datos, que incluyó los siguientes pasos:

*   **Extracción de Datos:** Se cargaron los datos directamente desde la API en formato JSON, convirtiéndolos a un DataFrame de Pandas para su manipulación.
*   **Corrección de Tipos de Datos:** La columna `account_Charges_Total` se convirtió a un formato numérico (`float64`) y los valores nulos resultantes se rellenaron con `0`.
*   **Manejo de Inconsistencias:** Se identificaron y eliminaron **224 registros** que no contenían información en la variable objetivo `Churn`.
*   **Estandarización de Columnas:** Las columnas con respuestas binarias (ej. 'Yes'/'No') fueron transformadas a un formato numérico (1/0).
*   **Ingeniería de Características:** Se creó la columna `Cuentas_Diarias` a partir del cargo mensual para ofrecer una perspectiva adicional.

El resultado fue un dataset limpio y coherente con **7,043 registros** listos para el análisis.

## 🔹 3. Análisis Exploratorio de Datos
El análisis reveló una tasa de evasión general del **26.5%**, confirmando que el problema es significativo. Los hallazgos más relevantes son:

### Hallazgo 1: El Tipo de Contrato es el Predictor Más Fuerte de Evasión
Los clientes con contratos **`Month-to-month` (mes a mes)** presentan una tasa de cancelación drásticamente superior en comparación con aquellos con contratos de uno o dos años.

### Hallazgo 2: Los Clientes Nuevos con Cargos Mensuales Altos son los Más Vulnerables
El análisis de variables numéricas mostró dos patrones claros:
*   **Antigüedad (`tenure`):** La mayoría de las cancelaciones ocurren durante los **primeros meses de servicio**.
*   **Cargo Mensual (`MonthlyCharges`):** Los clientes que cancelan tienden a tener, en promedio, **facturas mensuales más altas**.

### Hallazgo 3: Ciertos Servicios y Métodos de Pago están Asociados a un Mayor Riesgo
*   **Servicio de Internet:** Los clientes con **`Fibra Óptica`** muestran una tasa de churn más alta que los de `DSL`.
*   **Método de Pago:** Los clientes que utilizan **`Electronic check` (Cheque Electrónico)** cancelan en una proporción mucho mayor que aquellos con métodos automáticos.

## 🔹 4. Conclusiones e Insights
El análisis nos permite construir un **perfil claro del cliente con alto riesgo de evasión**:

*   Tiene un contrato **mes a mes**.
*   Es un cliente **relativamente nuevo** (baja antigüedad).
*   Paga una **factura mensual elevada**.
*   Utiliza **métodos de pago no automáticos**, como el cheque electrónico.
*   **No ha contratado servicios de valor añadido**, como Soporte Técnico.

Estos factores, especialmente combinados, crean un escenario de alto riesgo que la empresa puede ahora identificar proactivamente.

## 🔹 5. Recomendaciones Estratégicas

1.  **Fomentar Contratos a Largo Plazo:** Crear campañas de marketing y ofrecer incentivos (descuentos, servicios adicionales gratuitos) a los clientes con contratos mes a mes para que migren a planes anuales o de dos años.

2.  **Implementar un Programa de Onboarding:** Enfocar los esfuerzos de retención en los primeros 3-6 meses de servicio del cliente. Esto podría incluir llamadas de seguimiento, tutoriales personalizados y ofertas especiales para fortalecer la relación inicial.

3.  **Revisar la Oferta de Fibra Óptica:** Investigar por qué los clientes de este servicio se van más. Las posibles causas podrían ser problemas de estabilidad, una percepción de alto costo-beneficio o una competencia agresiva.

4.  **Incentivar Pagos Automáticos:** Ofrecer un pequeño descuento o beneficio a los clientes que cambien de cheque electrónico a métodos de pago automáticos, lo cual no solo reduce el churn sino que también disminuye la fricción administrativa.


