---
category: general
date: 2026-09-10
description: Codifique caracteres no ASCII en un código QR y guarde la imagen del
  código QR con un constructor simple de Python. Siga una guía paso a paso usando
  ExtCodetextBuilder y BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- encode non ascii characters
- save qr code image
- extended codetext builder
- eci encoding python
- barcode generation python
language: es
lastmod: 2026-09-10
og_description: Codificar caracteres no ASCII en un código QR y guardar la imagen
  del código QR usando Python. Este tutorial muestra cómo crear un texto de código
  extendido, generar un código QR y almacenar la imagen.
og_image_alt: Diagram showing encode non ASCII characters in QR code and save QR code
  image workflow
og_title: Codificar caracteres no ASCII en un código QR y guardar la imagen del código
  QR – guía paso a paso en Python
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Encode non ASCII characters in a QR code and save QR code image with
    a simple Python builder. Follow a step‑by‑step guide using ExtCodetextBuilder
    and BarcodeGenerator.
  headline: Encode non ASCII characters in QR code and save QR code image
  type: TechArticle
tags:
- barcode
- QR code
- Python
title: Codificar caracteres no ASCII en un código QR y guardar la imagen del código
  QR
url: /es/python/general/encode-non-ascii-characters-in-qr-code-and-save-qr-code-imag/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Codificar caracteres no ASCII en código QR y guardar la imagen del código QR

Si necesitas **codificar caracteres no ASCII** en un código QR, esta guía te muestra exactamente cómo hacerlo y luego **guardar la imagen del código QR** en disco. Ya sea que estés manejando datos en ruso, chino o emojis, el ExtCodetextBuilder te permite mezclar texto plano y segmentos codificados con ECI sin manipular manualmente los bytes.

Aprenderás cómo crear una cadena de codetext extendido, generar un código QR que entienda esa cadena y, finalmente, escribir la imagen del código de barras en un archivo. El tutorial asume conocimientos básicos de Python y que tienes el SDK `barcode` instalado.

## Requisitos previos

* Python 3.8+ instalado.
* El paquete Python `barcode` (o el SDK correspondiente) que proporciona `ExtCodetextBuilder`, `CodetextEncodingType` y `BarcodeGenerator`.
* Permiso de escritura en el directorio donde deseas **guardar la imagen del código QR**.

Puedes instalar el SDK con pip (reemplaza `barcode-sdk` con el nombre real del paquete):

```bash
pip install barcode-sdk
```

## Paso 1: Crear un constructor de codetext extendido

El primer paso es instanciar `ExtCodetextBuilder`. Este objeto recopila múltiples segmentos de texto y produce una única cadena que la simbología del código QR puede interpretar.

```python
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Initialize the builder that will hold all text parts
ext_builder = ExtCodetextBuilder()
```

*Por qué es importante*: los códigos QR admiten **codetext extendido**, lo que significa que puedes incrustar varios modos de codificación (plano, ECI, etc.) en un solo código de barras. El constructor abstrae el formato de bajo nivel requerido por la especificación QR.

## Paso 2: Añadir un segmento de texto plano

El texto plano es el modo predeterminado y funciona para caracteres ASCII. Añadirlo primero proporciona una alternativa legible para los escáneres que ignoran ECI.

```python
# Add simple ASCII text
ext_builder.add_plain_codetext("HelloWorld")
```

Si omites este paso, el código QR contendrá solo el segmento ECI, lo que algunos lectores antiguos podrían no decodificar correctamente.

## Paso 3: Añadir un segmento codificado con ECI para caracteres no ASCII

Para incluir caracteres fuera del rango ASCII —como cirílico, chino o emojis— debes especificar una codificación ECI (Extended Channel Interpretation). Aquí usamos UTF‑8 para la palabra rusa “Привет”.

```python
# Add a UTF‑8 encoded segment containing non‑ASCII characters
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")  # Russian “Hi”
```

*Por qué funciona*: la especificación QR define valores ECI que indican al escáner qué conjunto de caracteres aplicar. Sin el marcador ECI, los bytes crudos se interpretarían como ISO‑8859‑1, lo que produciría una salida distorsionada.

## Paso 4: Obtener la cadena combinada de codetext extendido

Después de añadir todos los segmentos deseados, llama a `get_extended_codetext()` para obtener la cadena final que espera el generador de códigos de barras.

```python
# Combine all parts into one extended codetext string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

El valor impreso parece una serie de caracteres de control seguidos del texto real, pero nunca necesitas analizarlo manualmente.

## Paso 5: Generar un código QR usando el codetext extendido

Ahora crea un `BarcodeGenerator`, establece la simbología a QR (la única simbología 2‑D común que admite codetext extendido) y proporciona la cadena combinada.

```python
# Initialize the QR generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)          # QR supports extended codetext
qr_generator.set_code_text(extended_codetext)
```

*Consejo*: Si intentas el mismo proceso con Code‑128 o DataMatrix, el SDK lanzará una excepción porque esos formatos no pueden interpretar marcadores ECI.

## Paso 6: Guardar la imagen del código QR

Finalmente, escribe el código de barras en un archivo PNG. Aquí es donde **guardas la imagen del código QR** para su uso posterior.

```python
output_path = "output/qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

Asegúrate de que la carpeta `output` exista o créala con `os.makedirs('output', exist_ok=True)` antes de llamar a `save`.

### Ejemplo completo ejecutable

Al combinar todos los pasos obtienes un script autónomo que puedes ejecutar de inmediato:

```python
import os
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Ensure the output directory exists
os.makedirs("output", exist_ok=True)

# 1️⃣ Create the builder
ext_builder = ExtCodetextBuilder()

# 2️⃣ Add plain ASCII text
ext_builder.add_plain_codetext("HelloWorld")

# 3️⃣ Add UTF‑8 encoded non‑ASCII text (Russian)
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")

# 4️⃣ Retrieve the combined string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 5️⃣ Generate QR code
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)
qr_generator.set_code_text(extended_codetext)

# 6️⃣ Save the image
output_file = "output/qr_extended.png"
qr_generator.save(output_file)
print(f"QR code saved to {output_file}")
```

**Salida esperada** (consola):

```
Extended codetext: <binary representation showing ECI markers>
QR code saved to output/qr_extended.png
```

Abrir `qr_extended.png` con cualquier escáner QR mostrará `HelloWorldПривет`. Los escáneres que entienden ECI renderizarán correctamente los caracteres cirílicos; los demás mostrarán solo la parte ASCII.

## Preguntas frecuentes y casos límite

| Pregunta | Respuesta |
|----------|-----------|
| *¿Puedo usar otras codificaciones como Shift‑JIS?* | Sí. Reemplaza `CodetextEncodingType.UTF_8` con `CodetextEncodingType.SHIFT_JIS` y proporciona el texto apropiado. |
| *¿Qué pasa si los datos combinados exceden la capacidad del QR?* | Los códigos QR tienen límites de versión (hasta 177 × 177 módulos). Si el constructor lanza una excepción de tamaño, aumenta el nivel de corrección de errores o divide los datos en varios códigos QR. |
| *¿Necesito establecer una versión QR específica?* | El SDK selecciona automáticamente la versión más pequeña que se ajuste a los datos. Puedes forzar una versión con `qr_generator.set_qr_version(10)` si es necesario. |
| *¿La imagen será transparente?* | Por defecto el SDK escribe un PNG con fondo blanco. Usa `qr_generator.set_background_color(Color.Transparent)` antes de `save` si necesitas transparencia. |

## Conclusión

En este tutorial aprendiste cómo **codificar caracteres no ASCII** en un código QR usando `ExtCodetextBuilder` y luego **guardar la imagen del código QR** con `BarcodeGenerator`. El proceso implica construir una cadena de codetext extendido, añadir segmentos tanto de texto plano como codificados con ECI, generar la simbología QR y, finalmente, escribir el archivo de imagen.

A partir de aquí puedes explorar:

* Añadir más segmentos ECI (diferentes idiomas o emojis).
* Ajustar los niveles de corrección de errores del QR para mayor fiabilidad.
* Incrustar el PNG generado en PDFs o páginas web.

¡Feliz codificación y disfruta creando códigos QR multilingües!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo generar una imagen de código QR en Python con Aspose.Barcode – Guía completa](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Generar código de barras Code128 con Aspose.Barcode Python – Guía completa](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [mostrar nombre del producto usando la biblioteca de códigos de barras Python – guía paso a paso](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}