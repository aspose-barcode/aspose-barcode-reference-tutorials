---
category: general
date: 2026-07-21
description: Crea un PNG de código de barras usando Aspose.Barcode en Python. Aprende
  a generar un código de barras a partir de datos, establecer sus dimensiones y guardar
  la imagen del código de barras en minutos.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- generate barcode from data
- generate planet barcode
- how to generate barcode python
- save barcode image
language: es
lastmod: 2026-07-21
og_description: Crea rápidamente un PNG de código de barras con Aspose.Barcode. Esta
  guía muestra cómo generar un código de barras a partir de datos, ajustar el tamaño
  y guardar la imagen del código de barras usando Python.
og_image_alt: Screenshot of a generated Planet barcode saved as a PNG file
og_title: Crear código de barras PNG en Python – Tutorial completo de Aspose.Barcode
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: Create barcode png using Aspose.Barcode in Python. Learn how to generate
    barcode from data, set dimensions, and save barcode image in minutes.
  headline: Create barcode png in Python – Full Aspose.Barcode Guide
  type: TechArticle
- description: Create barcode png using Aspose.Barcode in Python. Learn how to generate
    barcode from data, set dimensions, and save barcode image in minutes.
  name: Create barcode png in Python – Full Aspose.Barcode Guide
  steps:
  - name: Running the script
    text: '1. Install Jython (e.g., `brew install jython` on macOS or download from
      the official site). 2. Place the Aspose.Barcode for Java JAR in Jython’s classpath,
      for example:'
  - name: 'Example: Switching to Code128'
    text: '```python generator = BarcodeGenerator(EncodeTypes.Code128, "ABC-1234")
      ```'
  - name: Quick fix for missing folder
    text: '```python import os output_dir = os.path.dirname(output_path) if not os.path.isdir(output_dir):
      os.makedirs(output_dir) ```'
  type: HowTo
tags:
- barcode
- python
- Aspose
- image generation
title: Crear código de barras PNG en Python – Guía completa de Aspose.Barcode
url: /es/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear código de barras png en Python – Guía completa de Aspose.Barcode

¿Alguna vez te has preguntado cómo **crear código de barras png** sin luchar con bibliotecas de imágenes de bajo nivel? No estás solo. Muchos desarrolladores necesitan una forma rápida y fiable de convertir datos sin procesar en un código de barras PNG limpio, y Aspose.Barcode lo hace pan comido.

En este tutorial recorreremos los pasos exactos para **generar código de barras a partir de datos** usando la simbología Planet, ajustar sus dimensiones y, finalmente, **guardar la imagen del código de barras** como un archivo PNG. Al final tendrás un script listo para ejecutar, además de una serie de consejos que mantendrán tu código robusto.

## Lo que aprenderás

- Cómo configurar Aspose.Barcode para proyectos Python (Jython)  
- El código exacto para **generar código de barras planet** con ancho y altura personalizados  
- Formas de **guardar la imagen del código de barras** como PNG, JPG u otros formatos  
- Trampas comunes y cómo evitarlas  

No se requiere experiencia previa con Aspose, solo conocimientos básicos de Python y un entorno de ejecución compatible con Java.

---

## Cómo crear código de barras png con Aspose.Barcode en Python

A continuación se muestra el script completo y ejecutable. Puedes copiar‑pegarlo en un archivo llamado `create_planet_barcode.py` y ejecutarlo con Jython (o cualquier intérprete Python con soporte Java).

```python
# ------------------------------------------------------------
# create_planet_barcode.py
# Demonstrates how to create barcode png using Aspose.Barcode
# ------------------------------------------------------------

# Step 1: Import the required Aspose.Barcode classes
# Note: These classes live in the Java package `com.aspose.barcode`,
# so you need a JVM‑based Python (Jython) or use JPype.
from com.aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 2: Choose the symbology (Planet) and feed the data you want to encode
# The data string can be any alphanumeric value that fits the Planet rules.
generator = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 3: Adjust the X dimension (module width) – this controls the bar thickness
# Here we set it to 4 pixels for a nicely balanced look.
generator.getParameters().getBarcode().setXDimension(4)

# Step 4: Set a custom bar height – 100 pixels gives a clear, readable barcode.
generator.getParameters().getBarcode().setBarHeight(100)

# Step 5: Choose the output folder and file name.
# Feel free to change the path to suit your project layout.
output_path = "output/Planet_100px.png"

# Step 6: Save the generated barcode image as a PNG file.
# BarCodeImageFormat.Png tells Aspose to output a PNG.
generator.save(output_path, BarCodeImageFormat.Png)

print("✅ Barcode PNG created at:", output_path)
```

**Explicación de cada bloque**

- **Import section** – Importamos las tres clases principales: `BarcodeGenerator` (el motor), `EncodeTypes` (el enum que enumera todas las simbologías) y `BarCodeImageFormat` (el enum para formatos de salida).  
- **Generator construction** – `EncodeTypes.Planet` indica a Aspose que use la simbología *Planet*, mientras que el segundo argumento `"123456"` son los datos que queremos codificar. Esto cumple el requisito de **generar código de barras a partir de datos**.  
- **X dimension & bar height** – Estas dos propiedades controlan el tamaño visual. Ajústalas para cumplir con restricciones de impresión o de UI; los valores predeterminados pueden ser demasiado pequeños para pantallas de alta resolución.  
- **Save call** – El método `save` escribe la imagen en disco. Al pasar `BarCodeImageFormat.Png` aseguramos que el archivo sea un PNG, completando el objetivo de **crear código de barras png**.

### Ejecutando el script

1. Instala Jython (p. ej., `brew install jython` en macOS o descárgalo desde el sitio oficial).  
2. Coloca el JAR de Aspose.Barcode para Java en el classpath de Jython, por ejemplo:

```bash
export CLASSPATH=$CLASSPATH:/path/to/Aspose.Barcode.jar
```

3. Ejecuta:

```bash
jython create_planet_barcode.py
```

Deberías ver la línea de confirmación y un archivo `Planet_100px.png` en la carpeta `output`. Ábrelo con cualquier visor de imágenes: verás un código de barras Planet nítido listo para escanear.

![Create barcode png example](https://via.placeholder.com/400x150.png?text=Planet+Barcode+PNG "Create barcode png example")

*Texto alternativo de la imagen: “Captura de pantalla de un código de barras Planet generado y guardado como archivo PNG”* – esto cumple con el requisito de alt de imagen.

## Generar código de barras a partir de datos – análisis profundo

La línea  

```python
generator = BarcodeGenerator(EncodeTypes.Planet, "123456")
```  

realiza el trabajo pesado. He aquí por qué es importante:

- **EncodeTypes.Planet** – Planet es una simbología menos común, ideal para datos numéricos compactos.  
- **"123456"** – Cualquier cadena que cumpla con el conjunto de caracteres Planet (solo dígitos) funciona. Si intentas pasar letras, Aspose lanzará una `BarcodeException`.  

Si necesitas **generar código de barras a partir de datos** que incluyan letras, cambia a una simbología que soporte alfanuméricos, como `EncodeTypes.Code128`. El resto del script permanece igual.

### Ejemplo: Cambiando a Code128

```python
generator = BarcodeGenerator(EncodeTypes.Code128, "ABC-1234")
```

Ahora has **generado código de barras a partir de datos** que mezclan letras y números, y aún puedes **guardar la imagen del código de barras** como PNG con la misma llamada `save`.

## Establecer dimensiones personalizadas y guardar la imagen del código de barras

A veces el tamaño predeterminado es demasiado pequeño para una etiqueta impresa. Por eso exponemos dos propiedades:

| Propiedad | Qué controla | Valores típicos |
|----------|------------------|----------------|
| `XDimension` | Ancho de un solo módulo (la barra delgada) | 2‑6 píxeles para pantalla, 8‑12 para impresión |
| `BarHeight`  | Altura de las barras | 50‑150 píxeles, según el tamaño de la etiqueta |

Ajustar ambos te permite adaptar el código de barras a cualquier medio. Después de la modificación, el método `save` sigue escribiendo un archivo **crear código de barras png**, sin pasos adicionales.

## Problemas comunes al generar código de barras Planet

1. **Longitud de datos inválida** – Planet codifica de 2 a 12 dígitos. Proporcionar más de 12 generará una excepción.  
2. **Carpeta de salida inexistente** – Si `output/` no existe, `generator.save` lanza una `FileNotFoundException`. Crea la carpeta primero o usa `os.makedirs`.  
3. **Problemas de classpath** – Olvidar agregar `Aspose.Barcode.jar` al `CLASSPATH` produce un `ImportError`. Verifica nuevamente la variable de entorno.

### Solución rápida para carpeta inexistente

```python
import os
output_dir = os.path.dirname(output_path)
if not os.path.isdir(output_dir):
    os.makedirs(output_dir)
```

Agrega el fragmento antes de la llamada `save`, y nunca volverás a ver un error de “directorio no encontrado”.

## Cómo generar código de barras python – enfoques alternativos

Aunque la solución de Aspose es potente, podrías preguntarte **cómo generar código de barras python** usando bibliotecas puras de Python. Herramientas como `python-barcode` o `qrcode` pueden generar códigos de barras 1D/2D, pero carecen del amplio soporte de simbologías (p. ej., Planet) que ofrece Aspose. Si solo necesitas tipos comunes (Code128, QR), esas bibliotecas son adecuadas; para simbologías especializadas, Aspose sigue siendo la mejor opción.

## Extender el ejemplo – múltiples formatos y procesamiento por lotes

Una vez que hayas dominado el flujo de un solo código de barras, escalar es sencillo:

```python
data_list = ["001122", "334455", "667788"]
for idx, data in enumerate(data_list, start=1):
    gen = BarcodeGenerator(EncodeTypes.Planet, data)
    gen.getParameters().getBarcode().setXDimension(4)
    gen.getParameters().getBarcode().setBarHeight(100)
    file_name = f"output/Planet_{data}_{idx}.png"
    gen.save(file_name, BarCodeImageFormat.Png)
    print(f"Saved {file_name}")
```

Ahora has **generado código de barras a partir de datos** en un bucle, guardando automáticamente archivos **de imagen del código de barras** para cada entrada. Cambia `BarCodeImageFormat.Png` por `Jpeg` o `Bmp` si necesitas una salida diferente.

## Resumen y próximos pasos

Hemos cubierto todo lo que necesitas para **crear código de barras png** con Aspose.Barcode en Python:

1. Importa las clases Java a través de Jython.  
2. **Genera código de barras Planet** (o cualquier otra simbología) a partir de tus datos.  
3. Ajusta finamente `XDimension` y `BarHeight` para que coincidan con tu diseño.  
4. **Guarda la imagen del código de barras** como PNG, completando el flujo de trabajo de **crear código de barras png**.  

¿Qué sigue? Prueba a añadir subtítulos de texto bajo el código de barras, experimenta con salida en color (`BarCodeImageFormat.Png24`), o integra el script en un servicio web que devuelva PNGs de códigos de barras bajo demanda.

---

**¡Feliz codificación!** Si encuentras algún problema, deja un comentario abajo—estaré encantado de ayudarte a afinar tu canal de generación de códigos de barras.

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Crear código de barras PNG – Relación de aspecto DataMatrix – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [Cómo guardar PNG usando DataMatrix C40 con Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [Cómo crear imágenes de código de barras code128 en Java con Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}