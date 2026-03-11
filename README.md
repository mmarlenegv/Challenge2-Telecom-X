# 📊 Análisis de Retención de Clientes (Churn) - Telecom X

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2C2D72?style=for-the-badge&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557c?style=for-the-badge&logo=python&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-4A90E2?style=for-the-badge&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626.svg?&style=for-the-badge&logo=Jupyter&logoColor=white)

## 📌 Contexto del Proyecto
**Telecom X** se enfrenta a un desafío crítico: una alta tasa de cancelación de clientes (Churn). Este proyecto consiste en un proceso completo de **Extracción, Transformación, Limpieza (ETL)** y **Análisis Exploratorio de Datos (EDA)** para identificar los patrones y factores que influyen en la decisión de un usuario de abandonar el servicio.

El análisis sienta las bases de negocio para el futuro desarrollo de modelos predictivos de Machine Learning que permitan anticipar y mitigar la evasión.

## 🎯 Objetivos
- Consumir y procesar datos crudos desde una API (formato JSON anidado).
- Limpiar y preparar un dataset de más de 7,000 registros para análisis.
- Identificar perfiles de clientes con alto riesgo de abandono.
- Generar recomendaciones estratégicas basadas en datos reales.

---

## 🛠️ Metodología y Procesamiento de Datos (ETL)
El dataset original requirió un tratamiento riguroso para asegurar la calidad de los datos:
1. **Extracción:** Lectura de datos desde una API usando la librería `requests`.
2. **Aplanamiento:** Uso de `pd.json_normalize()` para estructurar diccionarios anidados.
3. **Limpieza:** - Eliminación de registros sin variable objetivo (`Churn` nulo).
   - Conversión de tipos de datos (Ej. `Cargos_Totales` a `float64`).
4. **Feature Engineering:** Creación de la métrica `Cuentas_Diarias` (cargo mensual / 30).
5. **Estandarización:** Traducción de variables al español y normalización de nombres de columnas.

> **Dataset Final:** 7,043 registros | 21 variables | 0 valores nulos | 0 duplicados.

---

## 📈 Descubrimientos Clave (Insights)
Tras el Análisis Exploratorio (EDA), se identificaron los siguientes patrones en la evasión (que representa un **26.6%** de la base):

* **⏱️ Tiempo de vida muy corto:** Los clientes que cancelan duran en promedio solo **10 meses**, frente a los 38 meses de los clientes leales.
* **📄 El peligro del mes a mes:** Los contratos mensuales presentan una tasa de evasión crítica (1,655 cancelaciones). Los contratos anuales reducen drásticamente este riesgo.
* **💸 La paradoja del servicio Premium:** Los usuarios del servicio de *Fibra Óptica* cancelan más que los de conexión estándar (DSL), a pesar de pagar facturas más altas (promedio de $79.7/mes vs $64.5/mes).
* **💳 Fricción en pagos:** El método de pago por "cheque electrónico" concentra más del triple de cancelaciones que otros métodos.

---

## 🚀 Recomendaciones Estratégicas
1. **Incentivar la migración de contratos:** Ofrecer beneficios para pasar de planes mensuales a anuales.
2. **Escudo de Retención:** Crear campañas de fidelización enfocadas en los primeros 12 meses (periodo crítico).
3. **Auditoría de Fibra Óptica:** Revisar la calidad y relación precio-valor de este servicio, ya que está generando alta insatisfacción.
4. **Modelo Predictivo:** Utilizar este dataset limpio para entrenar un algoritmo de Machine Learning que asigne un "Score de Riesgo" a los clientes actuales.

---

## 💻 Cómo explorar este proyecto

Tienes dos opciones muy sencillas para revisar mi trabajo:

**Opción 1: Verlo directamente aquí en GitHub (Recomendado)**
Simplemente haz clic en el archivo con extensión `.ipynb` que está en la lista de archivos arriba. GitHub te mostrará todo el código, los gráficos y el informe final directamente en tu navegador, sin necesidad de instalar nada.

**Opción 2: Descargarlo para probar el código**
1. Haz clic en el botón verde **"<> Code"** en la parte superior de esta página.
2. Selecciona la opción **"Download ZIP"**.
3. Extrae la carpeta descargada en tu computadora.
4. Abre el archivo `.ipynb` usando **Jupyter Notebook** o súbelo a **Google Colab** para ejecutar las celdas tú mismo.

Desarrollado con 💙 y datos por [Marlene Galvez/mmarlenegv]*
