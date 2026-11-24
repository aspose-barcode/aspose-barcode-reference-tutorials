---
category: general
date: 2026-11-23
description: Cómo generar imágenes de códigos de barras en Python con Aspose.BarCode.
  Aprende a crear un código de barras Planet, ajustar la dimensión X y generar un
  PNG con barras vacías.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- Python barcode generation
- Aspose.BarCode library
- Planet barcode symbology
- empty bars barcode
- barcode image PNG
language: es
lastmod: 2026-11-23
og_description: Cómo generar códigos de barras en Python usando Aspose.BarCode. Este
  tutorial le guía paso a paso para crear un código de barras Planet con barras vacías
  y guardarlo como PNG.
og_image_alt: Screenshot of Python code that generates a Planet barcode with empty
  bars saved as a PNG file
og_title: Cómo generar códigos de barras en Python – guía completa
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: How to generate barcode images in Python with Aspose.BarCode. Learn
    to create a Planet barcode, adjust X‑dimension, and output an empty‑bars PNG.
  headline: How to generate barcode images in Python using Aspose.BarCode
  type: TechArticle
- description: How to generate barcode images in Python with Aspose.BarCode. Learn
    to create a Planet barcode, adjust X‑dimension, and output an empty‑bars PNG.
  name: How to generate barcode images in Python using Aspose.BarCode
  steps:
  - name: Switching to a different symbology
    text: 'If you need a QR code, Code 128, or any other format, replace `EncodeTypes.Planet`
      with the appropriate enum value:'
  - name: Changing the image format
    text: 'Aspose.BarCode supports PNG, JPEG, BMP, and TIFF. To generate a JPEG instead:'
  - name: Adjusting image size without losing quality
    text: 'You can control the overall image dimensions via the `resolution` property
      or by scaling the X‑dimension and Y‑dimension together. For high‑resolution
      prints, set a higher DPI:'
  - name: Handling long data strings
    text: 'The Planet symbology has a limited data capacity (up to 8 characters).
      If you try to encode a longer string, the generator raises an exception. Validate
      the length before creating the barcode:'
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: Cómo generar imágenes de códigos de barras en Python usando Aspose.BarCode
url: /es/python-java/general/how-to-generate-barcode-images-in-python-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo generar imágenes de códigos de barras en Python usando Aspose.BarCode

Generar imágenes de códigos de barras en Python es sencillo con la biblioteca Aspose.BarCode. Esta guía le muestra paso a paso cómo generar un código de barras usando la simbología Planet, personalizar la dimensión X y producir un archivo PNG con estilo de barras vacías.

Verá un script completo y ejecutable que puede copiar en su proyecto. El tutorial también cubre variaciones comunes —como cambiar a una simbología diferente o a otro formato de salida— para que pueda adaptar la solución a sus propios requisitos.

## Requisitos previos

* Python 3.8 o superior instalado.
* Acceso a una terminal o símbolo del sistema.
* Una licencia activa de Aspose.BarCode para Python (la evaluación gratuita funciona para pruebas).
* Familiaridad básica con la gestión de paquetes de Python (`pip`).

## Paso 1: Instalar el paquete Aspose.BarCode

Aspose distribuye su API de Python a través de PyPI. Instálelo con el gestor de paquetes estándar:

```bash
pip install asposebarcode
```

> **Consejo profesional:** Use un entorno virtual (`python -m venv venv`) para mantener las dependencias aisladas de otros proyectos.

## Paso 2: Importar las clases necesarias de Aspose.BarCode

La instrucción de importación trae el generador, la enumeración de simbologías y la enumeración de formatos de imagen.

```python
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

* `BarcodeGenerator` crea el objeto de código de barras.
* `EncodeTypes` enumera todas las simbologías compatibles —aquí usaremos `Planet`.
* `BarCodeImageFormat` define el tipo de archivo de salida (PNG, JPEG, etc.).

## Paso 3: Crear un generador de códigos de barras para la simbología Planet

Instancie el generador con la simbología deseada y los datos que desea codificar.

```python
# Create a generator for the Planet symbology with the value "123456"
barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

La simbología `Planet` produce un patrón circular que es ideal para propósitos decorativos o de marca.

## Paso 4: Ajustar la dimensión X (ancho del módulo)

La dimensión X controla el ancho de la barra más pequeña (módulo). Configurarla a 4 píxeles produce una imagen clara y de alta resolución.

```python
# Set the module width to 4 pixels
barcode.parameters.barcode.x_dimension.pixels = 4
```

Cambiar la dimensión X es útil cuando necesita un código de barras que escale bien para impresión o visualización en pantalla.

## Paso 5: Desactivar las barras rellenas para un estilo de barras vacías

Un código de barras de barras vacías muestra solo los contornos de las barras, lo que puede ser útil para aplicaciones con mucho diseño.

```python
# Produce an empty‑bars barcode by disabling filled bars
barcode.parameters.barcode.filled_bars = False
```

Cuando `filled_bars` es `False`, el generador dibuja formas huecas en lugar de sólidas.

## Paso 6: Guardar la imagen del código de barras como archivo PNG

Finalmente, escriba el código de barras en disco. PNG es sin pérdida y ampliamente compatible.

```python
# Save the barcode as a PNG image
barcode.save("output/PlanetEmptyBars.png", BarCodeImageFormat.Png)
```

El método `save` crea automáticamente el directorio de destino si no existe.

## Ejemplo completo – un script completo y ejecutable

Unir todas las piezas le brinda un programa autónomo que puede ejecutar inmediatamente:

```python
# -*- coding: utf-8 -*-
"""
Generate a Planet barcode with empty bars and save it as PNG.
Requires: asposebarcode (pip install asposebarcode)
"""

from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# Step 1: Create the generator
barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Configure appearance
barcode.parameters.barcode.x_dimension.pixels = 4   # X‑dimension = 4 px
barcode.parameters.barcode.filled_bars = False    # empty‑bars style

# Step 3: Save as PNG
output_path = os.path.join(output_dir, "PlanetEmptyBars.png")
barcode.save(output_path, BarCodeImageFormat.Png)

print(f"Barcode saved to: {output_path}")
```

**Salida esperada:** Después de ejecutar el script, `output/PlanetEmptyBars.png` contiene una imagen de 200 × 200 píxeles de un código de barras Planet con barras huecas. Abrir el archivo en cualquier visor de imágenes mostrará el patrón circular con el valor numérico codificado en su interior.

## Variaciones comunes y casos límite

### Cambiar a una simbología diferente

Si necesita un código QR, Code 128, o cualquier otro formato, reemplace `EncodeTypes.Planet` con el valor de enumeración apropiado:

```python
barcode = BarcodeGenerator(EncodeTypes.QR, "https://example.com")
```

### Cambiar el formato de imagen

Aspose.BarCode soporta PNG, JPEG, BMP y TIFF. Para generar un JPEG en su lugar:

```python
barcode.save("output/PlanetEmptyBars.jpg", BarCodeImageFormat.Jpeg)
```

### Ajustar el tamaño de la imagen sin perder calidad

Puede controlar las dimensiones generales de la imagen mediante la propiedad `resolution` o escalando la dimensión X y la dimensión Y juntas. Para impresiones de alta resolución, establezca un DPI más alto:

```python
barcode.parameters.image.resolution = 300  # 300 dpi for print quality
```

### Manejar cadenas de datos largas

La simbología Planet tiene una capacidad de datos limitada (hasta 8 caracteres). Si intenta codificar una cadena más larga, el generador lanza una excepción. Valide la longitud antes de crear el código de barras:

```python
data = "123456"
if len(data) > 8:
    raise ValueError("Planet barcode supports a maximum of 8 characters.")
```

## Consejos y trampas

* **Activación de licencia:** Para uso en producción, aplique su archivo de licencia al inicio del script con `asposebarcode.License().set_license("Aspose.Total.lic")`. Omitir este paso incrustará una marca de agua en la imagen de salida.
* **Seguridad en hilos:** Las instancias de `BarcodeGenerator` no son seguras para hilos. Cree una instancia separada por hilo si genera códigos de barras en paralelo.
* **Rendimiento:** Reutilizar un generador para varios valores (llamando a `barcode.value = "new data"`) es más rápido que construir un nuevo objeto cada vez.
* **Rutas de archivo:** Use `os.path.join` para construir rutas independientes de la plataforma, especialmente al desplegar en Linux o macOS.

## Conclusión

Ahora sabe cómo generar imágenes de códigos de barras en Python con Aspose.BarCode, personalizar la dimensión X, producir un estilo de barras vacías y guardar el resultado como PNG. El ejemplo completo puede adaptarse a otras simbologías, formatos de salida y estilos visuales, brindándole una base flexible para cualquier característica relacionada con códigos de barras en sus aplicaciones.

**Próximos pasos:** Explore palabras clave secundarias adicionales como *Python barcode generation* probando diferentes codificaciones, experimente con configuraciones de compresión de *barcode image PNG*, o integre las imágenes generadas en un servicio web usando Flask o FastAPI. ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarle a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en sus propios proyectos.

- [Cómo crear un código de barras planet PNG con Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [Cómo crear una imagen de código de barras en Python con Aspose.BarCode](/barcode/english/python-java/general/how-to-create-barcode-image-in-python-with-aspose-barcode/)
- [Cómo generar una imagen de código QR en Python con Aspose.Barcode – Guía completa](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}