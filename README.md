# Proyecto de Análisis y Segmentación de Clientes - ConnectaTel (2024)

## Objetivo del Proyecto
Analizar, limpiar y segmentar los datasets multi-fuente de la compañía de telecomunicaciones ConnectaTel correspondientes al periodo 2024, con el fin de identificar patrones de comportamiento, gestionar anomalías estadísticas y aportar insights accionables para la estrategia comercial y de retención de clientes.

### Datasets Utilizados
El proyecto integra y procesa tres fuentes de datos principales ubicadas en la carpeta /datasets/:
- plans.csv: Contiene la definición de los planes tarifarios disponibles.
- users_latam.csv: Almacena el perfil demográfico de los usuarios (ID, edad, ciudad, fecha de registro y tipo de plan).
- usage.csv: Registra la actividad operativa de los clientes (mensajes enviados, llamadas realizadas y duración/minutos de comunicación).

### Etapas del Realización del Análisis
- Carga e Inspección Inicial: Lectura de estructuras de datos y detección preliminar de anomalías volumétricas.
- Limpieza y Calidad de Datos:
- Reemplazo del valor centinela -999 en la edad por la mediana estadística.
- Estandarización de caracteres inválidos (?) en ciudades a valores nulos (pd.NA).
- Acotación temporal de fechas de registro futuras (2026) hacia valores vacíos (pd.NaT), limitando el estudio estrictamente al año 2024.
- Análisis de nulos condicionales (MAR) en duración y longitud según el tipo de servicio.
- Agrupación y Perfilamiento: Consolidación de métricas de uso por usuario y fusión con el perfil demográfico (user_profile).
- Análisis Estadístico y Visualización: Generación de resúmenes descriptivos, histogramas de distribución por plan y diagramas de caja para detección de valores atípicos mediante el método IQR.
- Segmentación de Clientes: Clasificación de la base en función de su nivel de actividad (Bajo uso, Uso medio, Alto uso) y grupos de edad (Joven, Adulto, Adulto Mayor).
- Reporte Ejecutivo: Síntesis de hallazgos orientada a la toma de decisiones gerenciales.

### Cómo Ejecutar el Notebook
- Puedes abrir y ejecutar todo el flujo de trabajo de forma interactiva directamente en Google Colab:
- Haz clic en el botón de apertura en Colab (si tienes la extensión o vínculo configurado) o sube el archivo .ipynb a tu entorno de Google Colab.
- Asegúrate de contar con la carpeta /datasets/ cargada en el entorno con los tres archivos CSV requeridos (plans.csv, users_latam.csv, usage.csv).
- Ejecuta las celdas secuencialmente de arriba hacia abajo (Shift + Enter).

### Guía de Reproducción
- Clona este repositorio en tu máquina local o accede mediante la plataforma en la nube.
- Verifica que las librerías base de Python estén instaladas (pandas, numpy, matplotlib, seaborn).
- Ejecuta el cuaderno principal para replicar los pasos de limpieza, gráficos y las tablas de segmentación comercial.
