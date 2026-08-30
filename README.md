DataXperience — Proyecto Final

Análisis exploratorio, estadístico y predictivo sobre un conjunto de datos de precios de computadores portátiles. Proyecto final del curso DataXperience — Ciencia de Datos, Universidad EAN.

Integrantes
Brayan Felipe Alvarez Nieto	Etapa 1 — Preparación de datos	
Jhonatan Stiben Rey Velasquez	Etapa 2 — Análisis estadístico	
Andres Sebastian Quintana Morales	Etapa 3 — Visualización y modelado	

Docente: Camila Silva

🎥 Video explicativo

[▶ Ver el video del proyecto]([PEGAR AQUÍ EL ENLACE])

Duración: [X] minutos.

Pregunta de investigación

¿Qué características técnicas explican el precio de un computador portátil, y con qué precisión puede estimarse ese precio a partir de sus especificaciones?

Dataset

Fuente: Laptop Price — Kaggle

	
Registros	1.303 portátiles
Variables originales	13
Variables tras la depuración	18
Variable objetivo	Price_euros (continua)

Contiene marca, tipo de equipo, tamaño y resolución de pantalla, procesador, memoria RAM, almacenamiento, tarjeta gráfica, sistema operativo, peso y precio de venta en euros.

Etapas del proyecto
Etapa 1 — Fundamentos y preparación de datos

Selección y justificación del conjunto de datos, diagnóstico de calidad y depuración.

El diagnóstico inicial no encontró valores nulos ni duplicados, pero sí un problema distinto: diez de las trece columnas eran texto sin procesar, incluyendo variables que por su naturaleza deberían ser numéricas. La limpieza consistió en convertir ese texto en información utilizable:

Ram y Weight — eliminación de la unidad pegada al valor ("8GB" → 8).
ScreenResolution — separación de tres atributos mezclados (panel IPS, pantalla táctil y resolución) y cálculo de la densidad de píxeles (PPI).
Memory — normalización de unidades (GB/TB), separación de equipos con dos discos y desglose por tipo de almacenamiento.
Cpu y Gpu — extracción de la gama y el fabricante a partir del modelo completo.
OpSys — agrupación de nueve categorías en cuatro familias.

Resultado: 18 variables utilizables sin pérdida de registros.

Etapa 2 — Análisis estadístico

[Completar: medidas de tendencia central y dispersión, análisis de la forma de las distribuciones, detección de valores atípicos y comparación entre variables.]

Etapa 3 — Visualización, modelado y storytelling

[Completar: visualizaciones finales, narrativa de datos, modelo predictivo, métricas de evaluación y aplicación profesional.]

Estructura del repositorio
dataexperience-final-project/
├── data/
│   ├── laptop_price.csv           # Conjunto original descargado de Kaggle
│   └── laptop_price_limpio.csv    # Conjunto depurado (salida de la Etapa 1)
├── notebooks/
│   ├── Etapa1_Preparacion_de_Datos.ipynb
│   ├── Etapa2_Analisis_Estadistico.ipynb
│   ├── Etapa3_Visualizacion_y_Modelo.ipynb
│   └── Proyecto_Final_Integrado.ipynb   # Los tres notebooks unificados
├── informe/
│   └── Informe_Proyecto_Final.pdf
├── .gitignore
└── README.md

Cómo ejecutar el proyecto

Opción recomendada — Google Colab:

Abrir Google Colab.
Archivo → Subir cuaderno y seleccionar el notebook deseado de la carpeta notebooks/.
Subir el CSV correspondiente al panel de archivos de la sesión:
Etapa 1 → laptop_price.csv
Etapas 2 y 3 → laptop_price_limpio.csv
Ejecutar las celdas en orden.

Opción local:

bash
git clone https://github.com/sebastianquintanam/dataexperience-final-project.git
cd dataexperience-final-project
pip install pandas numpy matplotlib seaborn scikit-learn
jupyter notebook

Herramientas

Python · pandas · NumPy · Matplotlib · Seaborn · scikit-learn · Google Colab · Git y GitHub

Notas
El archivo original debe leerse con encoding='latin-1'; la codificación por defecto falla por la presencia de caracteres acentuados en los nombres de producto.
Las etapas 2 y 3 parten de laptop_price_limpio.csv, no del archivo original.
