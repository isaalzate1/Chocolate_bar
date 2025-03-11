# EDA Y PIPELINE: CHOCOLATE BAR RATINGS 

CARGA Y LIMPIEZA:

Limpieza de nombres de columnas y transformación de variables:
- Se corrigen los nombres de las columnas para eliminar saltos de línea y espacios innecesarios.
- Se convierte la columna “Cocoa Percent” de string (con “%”) a variable numérica.
- Identificación de tipos de variables y detección de datos faltantes:

EDA:
- Visualización de las primeras filas, información general y estadísticas descriptivas.
- Identificación de valores faltantes.
- Análisis de rangos de las variables numéricas.
- Exploración y conteo de categorías en las variables categóricas.
- Visualización de histogramas para variables numéricas y un mapa de calor de la correlación.
 
PIPELINE
- Se utiliza ColumnTransformer para definir transformaciones específicas para variables numéricas (imputación y escalado) y categóricas (imputación y one-hot encoding).
- Se integra en un pipeline global usando Pipeline de scikit-learn.

CONCLUSIONES

ENTENDER EL DATASET: Se identificaron los tipos de variables (numéricas y categóricas), se analizaron los rangos y distribuciones, y se detectaron valores faltantes. Esto es fundamental para conocer el estado y calidad de los datos antes de cualquier análisis o modelado.

LIMPIEZA Y PREPARACIÓN:Ajustamos los nombres de las columnas para que fueran más claros y convertimos algunos valores (por ejemplo, quitamos el símbolo “%” de la columna "Cocoa Percent" para trabajar con números). Esto nos ayuda a que los datos estén en el formato correcto para analizarlos.

CREACIÓN PIPELINE:Dividimos el trabajo en dos partes:

- Para las columnas numéricas: reemplazamos los valores que faltaban con la media y luego escalamos los números para que estén en una escala similar.

- Para las columnas de texto: reemplazamos los valores faltantes con el dato que más se repite y convertimos el texto en números (usando una técnica llamada one-hot encoding).

Todo esto lo juntamos en un solo flujo de trabajo (pipeline), que se encarga de preparar los datos de forma automática.

BENEFICIOS DEL PIPELINE: Al tener un proceso ordenado, nos aseguramos de que cada vez que usemos los datos (ya sea para entrenar un modelo o para hacer predicciones), se apliquen exactamente los mismos pasos. Esto evita errores y hace el trabajo más consistente y reproducible.