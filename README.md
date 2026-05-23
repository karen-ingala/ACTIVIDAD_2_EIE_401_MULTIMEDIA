# ACTIVIDAD_2_EIE_401_MULTIMEDIA
# Procesamiento de Imágenes Aplicado a una Imagen GPS 🛰️

Este repositorio contiene el desarrollo de la **Actividad 2** para la asignatura de **Procesamiento Digital Multimedia**. El objetivo principal del proyecto es aplicar herramientas fundamentales de procesamiento digital de imágenes para limpiar, aislar y analizar una trayectoria GPS que se encuentra fuertemente degradada por ruido exógeno sobre un mapa base.

## 📋 Tabla de Contenidos
1. [Descripción del Proyecto](#descripción-del-proyecto)
2. [Tecnologías Utilizadas](#tecnologías-utilizadas)
3. [Estructura del Análisis](#estructura-del-análisis)
4. [Instalación y Uso](#instalación-y-uso)
5. [Autor](#autor)

## 🎯 Descripción del Proyecto
El flujo de trabajo se desarrolló íntegramente en un Jupyter Notebook. Partiendo de una señal de entrada ruidosa (interferencia tipo "sal y pimienta" continua), se implementan técnicas matemáticas y espaciales para rescatar la señal útil (la ruta GPS) anulando el fondo topográfico estructurado. Además, se verifica algebraicamente la propiedad de reconstrucción perfecta utilizando el análisis de frecuencias por Wavelets.

## 🛠️ Tecnologías Utilizadas
El proyecto está escrito en **Python** y hace uso de las siguientes librerías:
* `OpenCV` (cv2) - Lectura y aplicación de filtros espaciales.
* `NumPy` - Operaciones matriciales y manejo de tipos de datos.
* `Matplotlib` - Generación de histogramas y despliegue visual de resultados.

## 🧠 Estructura del Análisis
El desarrollo dentro del Notebook (`Actividad_2_IngalaKaren_ID_GPS_Imagen_Haar.ipynb`) se divide en 5 secciones clave:

1. **Visualización de la Información:** Carga de los mapas de bits en escala de grises para establecer el escenario base y la verdad de campo (*Ground Truth*).
2. **Histograma de Intensidad:** Análisis de la distribución probabilística de los niveles de gris para diagnosticar la viabilidad de segmentación y justificar el uso de filtros.
3. **Filtros Espaciales:** Comparación práctica entre el **Filtro Gaussiano** (reducción de ruido continuo) y el **Filtro de Mediana** (eliminación de ruido impulsivo/sal y pimienta sin afectar bordes).
4. **Estimación y Remoción de Fondo:** Uso de un kernel de gran escala ($51 \times 51$) para estimar la iluminación base y sustraer matemáticamente las estructuras estáticas del mapa urbano $I_{corr}(x,y) = I(x,y) - B(x,y)$.
5. **Transformada Wavelet 2D tipo Haar:** Implementación matricial manual (sin dependencias externas complejas) para descomponer la imagen en subbandas de frecuencia ($LL, LH, HL, HH$) y validación de reconstrucción exacta sin pérdidas.

## 🚀 Instalación y Uso

1. Clona este repositorio en tu máquina local:
   ```bash
   git clone [https://github.com/tu_usuario/tu_repositorio.git](https://github.com/tu_usuario/tu_repositorio.git)
