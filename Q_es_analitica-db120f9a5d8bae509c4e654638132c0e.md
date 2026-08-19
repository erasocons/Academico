La analítica de datos se compone de cuatro pilares fundamentales: **los tipos de análisis**, **el ciclo de vida del dato**, **la arquitectura/stack tecnológico** y **las habilidades del equipo**.

---

## 1. Los 4 Tipos de Análisis (Niveles de Madurez)

Representan las etapas del análisis según la pregunta que responden y el valor de negocio que entregan:

1. **Analítica Descriptiva (*¿Qué pasó?*):** 
   * Examina datos históricos para entender tendencias o eventos pasados.
   * **Herramientas/Entregables:** Reportes, dashboards (Power BI, Tableau) y métricas clave de desempeño (KPIs).
2. **Analítica Diagnóstica (*¿Por qué pasó?*):** 
   * Profundiza en los datos para encontrar causas raíz, correlaciones y patrones.
   * **Técnicas:** Drills-down en dashboards, pruebas de hipótesis, análisis de correlación y segmentación.
3. **Analítica Predictiva (*¿Qué pasará?*):** 
   * Utiliza modelos estadísticos y algoritmos de Machine Learning para prever escenarios futuros.
   * **Técnicas:** Regresiones, modelos de clasificación, análisis de series temporales y redes neuronales.
4. **Analítica Prescriptiva (*¿Qué debemos hacer?*):** 
   * Recomienda acciones específicas para optimizar resultados basándose en las predicciones.
   * **Técnicas:** Optimización matemática, simulación de escenarios y motores de decisión automatizados.

---

## 2. El Ciclo de Vida de los Datos (Proceso)

Es la secuencia de pasos técnicos necesarios para transformar datos crudos en conocimiento útil:

* **Ingesta y Captura:** Recolección de datos desde bases de datos relacionales (SQL), APIs, archivos (CSV, JSON), sensores o logs web.
* **Limpieza y Preparación (Data Wrangling):** Tratamiento de valores nulos, eliminación de duplicados, corrección de tipos de datos y estructuración.
* **Almacenamiento:** Organización de la información en *Data Warehouses* (como BigQuery, Snowflake), *Data Lakes* o bases de datos SQL/NoSQL.
* **Exploración y Modelado (EDA & ML):** Aplicación de análisis exploratorio, ingeniería de características (*feature engineering*) y entrenamiento de modelos.
* **Visualización y Comunicación:** Creación de dashboards interactivos y presentación de hallazgos alineados a las metas de negocio.

---

## 3. Componentes Tecnológicos y Herramientas

* **Lenguajes de Programación:** Python (Pandas, NumPy, Scikit-Learn) y R.
* **Bases de Datos y Consulta:** SQL (PostgreSQL, MySQL, SQL Server) para extracción y manipulación.
* **Visualización y BI:** Power BI, Tableau, Looker, Matplotlib/Seaborn.
* **Ingeniería y Cloud:** GCP, AWS, Azure, Databricks, Spark para procesamiento a gran escala.

---

## 4. Perfiles y Roles Clave

Un proyecto de analítica de datos suele integrar tres roles principales:

* **Analista de Datos (Data Analyst):** Enfocado en traducir datos en información de negocio mediante SQL, dashboards y storytelling.
* **Ingeniero de Datos (Data Engineer):** Diseña y mantiene los flujos de datos (ETL/ELT), arquitecturas de almacenamiento y pipelines de datos.
* **Científico de Datos (Data Scientist):** Construye modelos predictivos y estadísticos avanzados para resolver problemas complejos.
