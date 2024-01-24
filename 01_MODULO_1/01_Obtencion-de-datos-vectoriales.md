---
layout: page
title: Unidad 1 - Obtención de datos vectoriales
parent: Módulo 1 - Obtención de datos y Operaciones Análiticas en la Práctica
nav_order: 1
---

# Introducción - Obtención de datos vectoriales

Los datos vectoriales son una forma de representar características del mundo real dentro del entorno de un Sistema de Información Geográfica (SIG). Los objetos espaciales vectoriales tienen atributos, que consisten en texto o información numérica que describe los objetos espaciales. Un objeto espacial es algo que puede verse en el paisaje. 

<img align="center" src="../images/datosvectoriales.png" vspace="10" width="2000"> 

## Descargar versión estable de QGIS
1. Ir a la página de descargas de QGIS. [Descargar QGIS](https://qgis.org/es/site/forusers/download.html).
2. En la sección de “Descargas de instalación”, encontrarás las opciones para diferentes sistemas operativos. Si estás usando Windows, debes hacer clic en `Descarga para Windows` o seleccionar Mac o Linux.
3. En la página de descarga, tienes dos opciones: la versión más reciente (QGIS 3.34 ‘Prizren’) y la versión más estable a largo plazo (QGIS 3.28 ‘Firenze’).  `Recomendablemente descargar la versión más estable a largo plazo`. [Versión estable](https://qgis.org/downloads/QGIS-OSGeo4W-3.28.15-1.msi).
4. Una vez que hagas clic en el enlace de descarga, se descargará un archivo de instalación en tu computadora.
5. Cuando la descarga se complete, abre el archivo de instalación y sigue las instrucciones para instalar QGIS.

Nota: Es importante mencionar que después de instalar QGIS, el primer intento de inicio puede fallar debido a las protecciones de seguridad. Para habilitar QGIS, debes hacer clic con el botón derecho sobre su icono en la carpeta Aplicaciones y seleccionar ‘Abrir’ en el menú contextual. Aparecerá un cuadro de diálogo de confirmación en el que deberás hacer clic de nuevo en el botón ‘Abrir’. Esto sólo tiene que hacerse una vez.

## Datos geoespaciales de tipo vectorial relacionados con políticas públicas

Los datos geoespaciales son un requisito previo para la buena formulación de políticas y el apoyo y seguimiento del progreso del desarrollo. La Agenda 2030 reconoce que la información geoespacial y estadística oportuna, disponible y accesible, ambas integradas con varios tipos de información adicional, son fundamentales para el seguimiento de los Objetivos de Desarrollo Sostenible. 

### Tipos de datos vectoriales
Los objetos espaciales vectoriales tienen atributos, que consisten en texto o información numérica que describe los objetos espaciales. Un objeto espacial tiene su forma representada utilizando geometría. La geometría se compone de uno o más vértices interconectados. Un vértice describe una posición en el espacio utilizando un eje X, Y y opcionalmente un eje Z.

Los datos vectoriales se caracterizan por representar características geográficas mediante puntos, líneas y polígonos. 

Cuando la geometría de un objeto espacial consiste en un solo vértice, se conoce como un elemento punto. Cuando la geometría consiste en dos o más vértices y el primer y último vértice no son iguales, se forma un elemento línea o polilínea. Cuando tres o más vértices están presentes, y el último vértice es igual al primero, se forma un elemento polígono.

1. **Puntos:** Los puntos se utilizan para representar características que se pueden ubicar con una única coordenada geográfica. Por ejemplo, podrían representar ubicaciones específicas como propiedades o ciudades.
2. **Líneas:** Las líneas, también conocidas como trayectorias, se utilizan para representar características lineales en el espacio geográfico. Por ejemplo, podrían representar carreteras o ríos.
3. **Polígonos:**  Los polígonos se utilizan para representar áreas. Estos son conjuntos de líneas que forman una forma cerrada. Por ejemplo, podrían representar áreas geográficas como montañas, masas de agua, o los límites de una ciudad.


<img align="center" src="../images/tiposdatosvectoriales.png"  vspace="10" width="300">

## Recopilación de información vectorial

Para recopilar información vectorial geoespacial, es posible utilizar varias herramientas y recursos. Algunos ejemplos:

1. **MyGeodata Cloud:** Esta es una interfaz en línea donde puedes explorar datos de otros usuarios, cargar tus propios datos, administrarlos o mostrarlos en un mapa.
2. **QGIS:** Con QGIS, puedes abrir mapas digitales en la computadora, crear nueva información espacial y realizar análisis espacial.
3. **R:** Hoy en día, R cuenta con un conjunto de librerías diseñadas exclusivamente para trabajar con datos geoespaciales.
4. **Google Earth Engine:**  Contiene colecciones de datos cargadas por instituciones oficiales y datos de otros usuarios de manera colaborativa.
5. **Open Street Map:**  Contiene colecciones de datos de superficie urbana de manera colaborativa.
6. **SEDAC:**  Centro de datos de la NASA que provee datos socioeconómicos georreferenciados.
7. **AIDDATA:** Extraer datos de límites administrativos.
8. **MapBiomas:**Información registrada de vectores de referencia nacional países de América del Sur


<img align="center" src="../images/datosadministrativo.png"  vspace="10" width="600">

The Global Administrative Unit Layers (GAUL). *Source: United Nations & FAO, GEE.* 


### Características, Limitaciones y Ventajas de los formatos de datos vectoriales

Los datos geoespaciales vectoriales suelen estar disponibles en varios formatos, incluyendo GeoJSON, shapefiles, MapInfo, GML, geodatabase, KML y otros formatos compatibles con la biblioteca GDAL2. Estos datos se pueden descargar y luego importar a las herramientas mencionadas anteriormente para su análisis y visualización.

### Formatos más utilizados

| Formato| Ventajas | Limitaciones                              |
|------|-----------------|------------------------------------------|
| CSV: Los archivos CSV son archivos de texto plano donde las comas se utilizan para delimitar los datos. Son ampliamente utilizados en diversas industrias para intercambiar datos debido a su formato simple y estandarizado.   | Son eficientes para almacenar y transferir datos entre diferentes aplicaciones. Son fáciles de leer y procesar por la mayoría de las aplicaciones de software      | No tienen soporte nativo para almacenar información espacial. Para almacenar datos espaciales, generalmente se utilizan en combinación con otros formatos o estándares, como WKT (Well-Known Text) para representar geometrías.                     |
| KML: (Keyhole Markup Language) es un formato basado en XML utilizado para mostrar datos geográficos en navegadores terrestres como Google Earth. Permite a los usuarios crear y compartir información geoespacial, incluyendo puntos, líneas, imágenes, polígonos y modelos 3D    | A diferencia de un shapefile, un archivo KML puede definir simbología, etiquetado y transparencia. También es capaz de agregar superposiciones de iconos y gráficos      |  No tiene una tabla de atributos asociada y no puede producir una salida dinámica por sí solo, ya que es un lenguaje estático                                        |
| GeoJSON: Es un formato para codificar estructuras de datos geoespaciales utilizando JavaScript Object Notation (JSON). Es ampliamente utilizado en la comunidad geoespacial y se considera el estándar para representar e intercambiar datos geoespaciales en la web  | Soporta varios tipos de geometrías, como puntos, líneas y polígonos, y puede incluir propiedades y atributos adicionales para cada característica. Es compatible con herramientas populares de análisis de datos, como GeoPandas de Python o el paquete sf de R   | Al igual que KML, GeoJSON es un formato estático y no puede producir una salida dinámica por sí solo           |
| Zipped Shapefile: Los shapefiles son un formato de almacenamiento de datos vectoriales geoespaciales. Cada shapefile representa un solo tipo de geometría: puntos, líneas o polígonos   | Son rápidos de dibujar y editar. Los shapefiles manejan características individuales que se superponen o que son no contiguas. Requieren menos espacio en disco y son más fáciles de leer y escribir      | No pueden almacenar valores nulos, ni anotaciones o características de red. Los nombres de los campos dentro de la tabla de atributos están limitados a diez caracteres |
| HTML: Es un lenguaje de marcado que se utiliza para crear la estructura de una página web. Es ampliamente utilizado y soportado por todos los navegadores | Es fácil de usar, aprender e implementar. No se requiere software especial. Contiene potentes facilidades de formato de texto  | No puede producir una salida dinámica por sí solo, ya que es un lenguaje estático. Hacer la estructura de los documentos HTML puede ser difícil de entender                       
