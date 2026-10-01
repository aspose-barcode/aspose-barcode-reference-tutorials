---
category: general
date: 2026-08-19
description: Cómo generar códigos de barras con ECI usando Aspose.Barcode para Python.
  Aprende a añadir datos ECI, mezclar texto plano y guardar la imagen en una guía
  clara.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to add eci
- Aspose.Barcode Python
- extended codetext barcode
- ECI encoding Python
language: es
lastmod: 2026-08-19
og_description: Cómo generar códigos de barras con ECI usando Aspose.Barcode para
  Python. Sigue este tutorial para aprender a agregar datos ECI, personalizar la apariencia
  y guardar el resultado.
og_image_alt: Screenshot showing a barcode generated with how to generate barcode
  example
og_title: Cómo generar códigos de barras con ECI usando Aspose.Barcode Python – paso
  a paso
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  headline: How to generate barcode with ECI using Aspose.Barcode Python
  type: TechArticle
- description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  name: How to generate barcode with ECI using Aspose.Barcode Python
  steps:
  - name: Expected result
    text: When you open `extended_codetext.png`, you should see a Code 128 barcode
      that encodes the numeric string `1234567890` followed by the Chinese characters
      “特殊字符”. Scanning the barcode with a modern scanner that respects ECI will return
      the original mixed string.
  - name: What if I need a different character set?
    text: Choose the appropriate ECI value from the ISO/IEC 18004 table. For example,
      ECI 27 represents ISO‑8859‑1 (Latin‑1). Replace the numeric identifier in `add_eci_codetext`
      accordingly.
  - name: Can I embed more than one ECI block?
    text: Yes. Call `add_eci_codetext` multiple times. The builder inserts the necessary
      ECI switch codes between blocks, preserving the order you add them.
  - name: Does the generator support QR codes with ECI?
    text: Absolutely. Replace `barcode.Symbology.CODE_128` with `barcode.Symbology.QR`
      and adjust any QR‑specific parameters (e.g., error correction level) via `generator.parameters.qr`.
  - name: How to handle very long data strings?
    text: For linear barcodes like Code 128, the maximum length is about 80 characters
      when using extended codetext. If you exceed that, consider switching to a two‑dimensional
      symbology such as QR or Data Matrix, which can store thousands of characters.
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: Cómo generar códigos de barras con ECI usando Aspose.Barcode Python
url: /es/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo generar un código de barras con ECI usando Aspose.Barcode Python

Si necesitas saber **cómo generar un código de barras** que contenga tanto caracteres simples como datos codificados con ECI, esta guía muestra el proceso completo. Verás exactamente **cómo añadir eci** a las secciones, ajustar el tamaño y escribir la imagen en disco con un único script ejecutable.

El tutorial cubre:

* Recuperar la versión de la biblioteca Aspose.Barcode (opcional pero útil para depuración).  
* Construir una cadena de texto extendida que mezcle caracteres simples y codificados con ECI.  
* Crear un generador de códigos de barras para una simbología que admita texto extendido.  
* Personalizar las dimensiones del código de barras y guardar el archivo PNG final.

No se requiere documentación externa; copia el código, ejecútalo y tendrás una imagen de código de barras que incluye caracteres chinos codificados con ECI 26 (UTF‑8).

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* Python 3.8 o superior instalado.  
* Paquete `aspose-barcode` instalado (`pip install aspose-barcode`).  
* Permiso de escritura en la carpeta donde planeas guardar el archivo PNG.

Si utilizas un entorno virtual, actívalo primero para mantener las dependencias aisladas.

## Paso 1: Verificar la versión de Aspose.Barcode (opcional)

Conocer la versión exacta de la biblioteca ayuda cuando necesitas informar errores o comparar funcionalidades entre versiones.

```python
import aspose.barcode as barcode
from aspose.barcode.generation import BuildVersionInfo

ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)
```

*Por qué es importante*: La salida de la versión confirma que el entorno de ejecución coincide con la documentación que estás siguiendo. Diferentes versiones pueden admitir distintos valores de ECI, por lo que es una verificación rápida de sanidad.

## Paso 2: Construir un texto extendido con partes simples y codificadas con ECI

Aspose.Barcode proporciona `ExtCodetextBuilder` para concatenar datos simples y segmentos codificados con ECI. En este ejemplo mezclamos una cadena numérica con caracteres chinos.

```python
from aspose.barcode.generation import ExtCodetextBuilder

builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using ECI 26 (UTF‑8)
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)
```

*Explicación*:  
* `add_plain_codetext` inserta datos que la simbología del código de barras trata como caracteres ordinarios.  
* `add_eci_codetext` indica al generador que anteponga un indicador ECI (aquí **26**, que corresponde a UTF‑8) antes del texto suministrado. Esto es exactamente **cómo añadir eci** a un código de barras.

Puedes llamar a `add_eci_codetext` varias veces para incrustar varios bloques de idioma diferentes. El constructor maneja automáticamente las secuencias de escape requeridas.

## Paso 3: Elegir una simbología que admita texto extendido

No todos los tipos de código de barras pueden almacenar segmentos ECI. Code 128, QR y Data Matrix son opciones comunes. El ejemplo usa Code 128 porque es ampliamente compatible y funciona bien con datos alfanuméricos mixtos.

```python
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,   # Code128 supports extended codetext
    extended_codetext
)
```

*¿Por qué Code 128?*: Acepta todo el rango ASCII y las secuencias de escape ECI generadas por el constructor, lo que lo hace ideal para el escenario de **cómo generar un código de barras** que mezcla texto simple y codificado.

## Paso 4: Ajustar la apariencia del código de barras

Puedes controlar el tamaño, la altura, los márgenes y muchos otros aspectos visuales mediante el objeto `parameters`.

```python
# Width of a single module (the smallest bar)
generator.parameters.barcode.x_dimension = 2   # 2 pixels per module

# Height of the bars (for linear barcodes)
generator.parameters.barcode.bar_height = 50  # 50 pixels tall

# Optional: add quiet zone (margin) if required by a scanner
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10   # 10 pixels margin on each side
```

*Consejo*: Si planeas imprimir el código de barras, incrementa `x_dimension` y `bar_height` proporcionalmente para mantener la legibilidad al DPI objetivo.

## Paso 5: Guardar la imagen del código de barras

Finalmente, escribe la imagen generada en un archivo. Aspose.Barcode admite PNG, JPEG, BMP y muchos otros formatos.

```python
output_path = "output/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

Asegúrate de que la carpeta `output` exista o créala con `os.makedirs("output", exist_ok=True)` antes de llamar a `save`.

### Resultado esperado

Al abrir `extended_codetext.png`, deberías ver un código de barras Code 128 que codifica la cadena numérica `1234567890` seguida de los caracteres chinos “特殊字符”. Escanear el código con un lector moderno que respete ECI devolverá la cadena mixta original.

![Barcode generated with how to generate barcode example](https://example.com/images/barcode-sample.png){: .align-center alt="Código de barras generado con ejemplo de cómo generar código de barras"}

## Preguntas frecuentes y casos límite

### ¿Qué pasa si necesito un conjunto de caracteres diferente?

Elige el valor ECI apropiado de la tabla ISO/IEC 18004. Por ejemplo, ECI 27 representa ISO‑8859‑1 (Latin‑1). Sustituye el identificador numérico en `add_eci_codetext` según corresponda.

### ¿Puedo incrustar más de un bloque ECI?

Sí. Llama a `add_eci_codetext` varias veces. El constructor inserta los códigos de cambio ECI necesarios entre los bloques, preservando el orden en que los añades.

### ¿El generador admite códigos QR con ECI?

Absolutamente. Sustituye `barcode.Symbology.CODE_128` por `barcode.Symbology.QR` y ajusta los parámetros específicos de QR (por ejemplo, nivel de corrección de errores) mediante `generator.parameters.qr`.

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorLevel.H
```

### ¿Cómo manejar cadenas de datos muy largas?

Para códigos de barras lineales como Code 128, la longitud máxima es de aproximadamente 80 caracteres cuando se usa texto extendido. Si superas ese límite, considera cambiar a una simbología bidimensional como QR o Data Matrix, que pueden almacenar miles de caracteres.

## Script completo y ejecutable

A continuación tienes el programa completo que puedes copiar y pegar en un archivo llamado `generate_extended_barcode.py` y ejecutar directamente.

```python
import os
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# ------------------------------------------------------------------
# Optional: print library version – useful for troubleshooting
# ------------------------------------------------------------------
ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)

# ------------------------------------------------------------------
# Build extended codetext: plain numbers + Chinese characters (ECI 26)
# ------------------------------------------------------------------
builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using UTF‑8
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)

# ------------------------------------------------------------------
# Create a Code128 generator – supports the extended codetext format
# ------------------------------------------------------------------
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,
    extended_codetext
)

# ------------------------------------------------------------------
# Customize appearance (size, quiet zone, etc.)
# ------------------------------------------------------------------
generator.parameters.barcode.x_dimension = 2
generator.parameters.barcode.bar_height = 50
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10

# ------------------------------------------------------------------
# Ensure output directory exists and save the image
# ------------------------------------------------------------------
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)
output_path = os.path.join(output_dir, "extended


## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo generar una imagen de código de barras con personalización de espacio suplementario usando Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [Cómo generar una imagen de código de barras en Java con Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [Cómo generar un código de barras DataMatrix con Aspose.BarCode para .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}