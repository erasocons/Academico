# Tipos de Datos en la Analítica de Datos: Fundamentos y Aplicación Práctica

> *\"Los números no tienen forma de hablar por sí mismos. Nosotros hablamos por ellos. Les infundimos significado.\"*  
> — Nate Silver, *The Signal and the Noise*

En la analítica de datos y la ciencia de datos, el primer paso fundamental para resolver cualquier problema no es la elección del algoritmo ni el lenguaje de programación, sino comprender la naturaleza de los datos con los que estamos trabajando. El tipo de datos determina qué operaciones matemáticas podemos realizar, qué visualizaciones son éticas y efectivas, y qué modelos predictivos podemos construir.

Este documento ofrece una clasificación detallada y progresiva de los tipos de datos utilizados en analítica, fundamentada en la teoría estadística y la práctica de negocio.

---

## 1. Clasificación Estadística Tradicional

Desde una perspectiva estadística, las variables (cualquier medida que pueda tomar diferentes valores en distintas circunstancias) se dividen en dos grandes familias: **categóricas** (cualitativas) y **numéricas** (cuantitativas).

### A. Variables Categóricas (Cualitativas)
Son medidas que toman valores en dos o más categorías o clases mutuamente excluyentes. Estas categorías pueden o no tener un orden natural.

1. **Variables Binarias (Dicotómicas):**
   * **Definición:** Es el caso más simple de datos categóricos, donde la variable solo puede tomar dos valores posibles (generalmente etiquetados como *Sí* o *No*, *1* o *0*, *Éxito* o *Fallo*).
   * **Representación matemática:** Se modelan matemáticamente mediante una **distribución de Bernoulli**.
   * **Ejemplos:** Supervivencia de un pasajero del Titanic (*Sobrevivió / No sobrevivió*), abandono de un cliente (*Churn / No Churn*), o si una transacción es fraudulenta (*Legítima / Fraude*).

2. **Variables Nominales (No ordenadas):**
   * **Definición:** Categorías discretas que no poseen un orden jerárquico intrínseco. No podemos decir que una categoría es "mayor" o "menor" que otra.
   * **Ejemplos:** El país de origen de un usuario, el color de un automóvil, o el hospital en el que se realiza una cirugía cardíaca.

3. **Variables Ordinales (Ordenadas):**
   * **Definición:** Categorías que poseen un orden o jerarquía natural que facilita la comparación de "mayor a menor", aunque la distancia matemática exacta entre los rangos no sea medible de forma precisa.
   * **Ejemplos:** Rangos militares, niveles de satisfacción del cliente (*Muy insatisfecho, Insatisfecho, Neutral, Satisfecho, Muy satisfecho*) o escalas Likert en encuestas.

4. **Números Agrupados o Discretizados (Binned Data):**
   * **Definición:** Datos continuos que han sido agrupados intencionalmente en contenedores (*bins*) o intervalos discretos por razones analíticas o de reporte.
   * **Ejemplos:** Niveles de obesidad definidos por umbrales de Índice de Masa Corporal (IMC) o rangos de edad (ej. *0-18, 19-35, 36-50, 51+*).

---

### B. Variables Numéricas (Cuantitativas)
Representan cantidades medibles y se expresan directamente a través de números.

1. **Variables de Conteo (Discretas):**
   * **Definición:** Mediciones cuyos valores posibles están restringidos únicamente a números enteros no negativos ($0, 1, 2, \\dots$). Representan eventos que ocurren de forma entera.
   * **Representación matemática:** Comúnmente modeladas mediante la **distribución de Poisson**.
   * **Ejemplos:** El número de homicidios por año en una región, la cantidad de llamadas que entran a un centro de atención telefónica, o el conteo de frijoles en un frasco.

2. **Variables Continuas:**
   * **Definición:** Mediciones que, al menos en teoría, pueden ser registradas con precisión infinita o decimal dentro de un rango específico de números reales.
   * **Ejemplos:** El peso, la altura de una persona, el salario anual de un empleado, o la tasa de desempleo nacional. Aunque en la práctica a menudo se redondean a enteros, su naturaleza subyacente es continua.

---

## 2. Clasificación por Estructura Informática

En el entorno del Big Data y el procesamiento moderno de datos, es crucial clasificar la información por su formato y facilidad de ingestión para los sistemas computacionales.

```
                           ┌─────────────────────────┐
                           │      Tipos de Datos     │
                           └────────────┬────────────┘
                                        │
           ┌────────────────────────────┼────────────────────────────┐
           ▼                            ▼                            ▼
 ┌───────────────────┐        ┌───────────────────┐        ┌───────────────────┐
 │   Estructurados   │        │ Semiestructurados │        │  No Estructurados │
 └─────────┬─────────┘        └─────────┬─────────┘        └─────────┬─────────┘
           │                            │                            │
┌──────────┼──────────┐                 │ (Esquema Flexible y        │ (Feature Engineering/
▼          ▼          ▼                 ▼  Autodescriptivo)          ▼  Text Mining)
Tabular Matrices   Series Temp.   Archivos JSON, XML,           Texto Libre, Audio,
(DFs)  (ndarrays)  (Timestamps)   NoSQL, YAML                   Imágenes, Video
```

### A. Datos Estructurados
Es información que se presenta en formatos altamente organizados con esquemas fijos y significados definidos por columna.
* **Datos Tabulares (Hojas de cálculo / Tablas de bases de datos relacionales):** Cada fila representa una entidad o instancia (un cliente, un producto) y cada columna representa un atributo o característica de tipo específico (numérico, texto, fecha). Es el formato estándar de las librerías analíticas como **pandas** (mediante objetos *DataFrame* y *Series*).
* **Matrices (Arreglos Multidimensionales):** Bloques homogéneos de memoria (como los *ndarrays* de **NumPy**) optimizados para computación matemática vectorial masiva.
* **Tablas Relacionadas:** Múltiples tablas estructuradas interconectadas mediante columnas clave (llaves primarias y foráneas en SQL).
* **Series Temporales (Time Series):** Datos registrados de forma repetida en intervalos de tiempo regulares o irregulares, donde cada registro está indexado por un *Timestamp* o timestamp secuencial (ej. precios de cierre diarios de una acción, lecturas de temperatura cada 5 minutos).

### B. Datos Semiestructurados
Es una forma intermedia de datos que no residen en una tabla estructurada estricta o un esquema de base de datos relacional rígido, pero que poseen marcadores, etiquetas u otros elementos de organización internos que permiten identificar campos individuales y anidar información de forma jerárquica. Esto los hace inherentemente autodescriptivos y flexibles.

* **Formatos Estándar en la Industria:**
  * **JSON (JavaScript Object Notation):** Un estándar de facto para el intercambio de datos por HTTP a través de APIs web. Es más libre y flexible que un CSV tradicional, estructurando los datos en combinaciones de objetos (diccionarios en Python) y arreglos (listas).
  * **XML (eXtensible Markup Language):** Un formato general jerárquico y anidado ampliamente utilizado que soporta la inclusión de metadatos ricos definidos por etiquetas personalizables.
* **Procesamiento y Transformación (Data Wrangling):**
  * Para su consumo y análisis, las librerías modernas de Python y pandas proporcionan excelentes abstracciones. El analista puede utilizar funciones de alto nivel como `pandas.read_json` y `pandas.read_xml` para parsear y cargar directamente estos archivos en un *DataFrame*.
  * Para estructuras JSON extremadamente complejas o altamente anidadas procedentes de respuestas de APIs web, se utiliza la deserialización nativa mediante `json.loads` del paquete estándar `json`, posibilitando un procesamiento exploratorio de datos ágil o su posterior aplanamiento (*flattening*) con utilidades como `pandas.json_normalize` para ser preparados como entradas de modelos predictivos.

### C. Datos No Estructurados
Información que no posee un formato estructurado o semiestructurado nativo. Está diseñada principalmente para el consumo humano y posee estructuras complejas o lingüísticas difíciles de procesar directamente por algoritmos matemáticos estándar.
* **Ejemplos típicos:** Artículos de noticias de texto libre, transcripciones de audio, correos electrónicos, imágenes o videos.
* **Transformación (Feature Engineering):** Para analizar datos no estructurados con herramientas analíticas tradicionales, es obligatorio realizar una extracción de características (*feature engineering*) para convertirlos en representaciones estructuradas. Por ejemplo, un corpus de artículos de noticias se procesa y transforma en una tabla de frecuencia de palabras (enfoque de \"Bolsa de palabras\" o *Bag-of-Words*) que mide la prevalencia de términos clave para realizar análisis de sentimiento o modelado de temas.

---

## 3. Impacto de los Tipos de Datos en el Modelado Analítico

La distinción entre tipos de datos es el factor determinante para definir el enfoque metodológico en cualquier proyecto analítico:

### A. Definición de la Tarea: ¿Clasificación o Regresión?
El tipo de la **variable objetivo** (el atributo que deseamos predecir o estimar, denotado frecuentemente como $y$) define la arquitectura del modelo de aprendizaje supervisado:
* **Si la variable objetivo es Categórica (ej. Binaria):** Enfrentamos una tarea de **Clasificación**. El objetivo es de estimar la probabilidad de pertenencia a una clase o segmento (*class probability estimation*). Usamos algoritmos como Regresión Logística, Árboles de Decisión de Clasificación, Support Vector Machines (SVM) o clasificadores Naive Bayes.
* **Si la variable objetivo es Numérica (ej. Continua):** Enfrentamos una tarea de **Regresión** (estimación de valor). El objetivo es calcular el valor numérico esperado de la variable para una nueva instancia. Usamos modelos como Regresión Lineal Múltiple o Árboles de Regresión.

### B. Preparación y Codificación de Variables (Wrangling)
Muchos algoritmos analíticos y de modelado (como la regresión lineal, logística o las redes neuronales) son estrictamente matemáticos y requieren que todas las **variables de entrada (predictores)** sean numéricas. Por ello, las variables categóricas nominales deben convertirse mediante técnicas de codificación o transformarse de formato:
* **Variables Dummy / Codificación One-Hot:** Consiste en tomar una columna categórica con $K$ categorías y expandirla en $K$ (o $K-1$) columnas binarias de $0$ y $1$ que indiquen la presencia o ausencia de cada categoría (evitando problemas de colinealidad en modelos lineales).
* **Tratamiento de Valores Faltantes (Nulls/NA):** El manejo de datos nulos varía según el tipo. Para variables continuas, es común imputar la media o la mediana; para variables categóricas, se pueden tratar los valores faltantes como una categoría separada (\"Desconocido\") o imputar la moda.
