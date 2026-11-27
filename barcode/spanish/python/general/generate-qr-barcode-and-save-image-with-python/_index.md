---
category: general
date: 2026-11-27
description: Genera códigos QR en Python usando Aspose.Barcode y aprende cómo guardar
  la imagen del código de barras en disco rápidamente.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate QR barcode
- save barcode image
- Aspose.Barcode Python
- extended codetext QR
- barcode version information
language: es
lastmod: 2026-11-27
og_description: Genera códigos QR en Python con Aspose.Barcode y guarda la imagen
  del código de barras al instante. Sigue el ejemplo completo para crear, personalizar
  y almacenar códigos QR.
og_image_alt: Screenshot of a generated QR barcode created with Python
og_title: Genera código QR y guarda la imagen con Python – guía paso a paso
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Generate QR barcode in Python using Aspose.Barcode and learn how to
    save barcode image to disk quickly.
  headline: Generate QR barcode and save image with Python
  type: TechArticle
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: Generar código QR y guardar la imagen con Python
url: /es/python/general/generate-qr-barcode-and-save-image-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generar código de barras QR y guardar la imagen con Python

Si necesitas **generar un código de barras QR** en una aplicación Python, esta guía te muestra cómo hacerlo usando la biblioteca Aspose.Barcode. También aprenderás la forma correcta de **guardar la imagen del código de barras** en una carpeta local, obtener detalles de la versión de la biblioteca y manejar segmentos de codetext extendidos.

Crear códigos QR es un requisito común para sistemas de tickets, pagos móviles y seguimiento de productos. Al final de este tutorial tendrás un script listo‑para‑ejecutar que produce un archivo de imagen de código de barras QR y muestra información de versión para depuración o cumplimiento.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* Python 3.8 o superior instalado.
* El paquete `aspose-barcode`. Instálalo con `pip install aspose-barcode`.
* Permiso de escritura en el directorio donde se almacenará la imagen del código de barras.

No se requieren servicios externos adicionales; todo el proceso se ejecuta localmente.

## Paso 1: Construir un codetext extendido con `ExtCodetextBuilder`

El codetext extendido te permite mezclar texto plano y segmentos ECI (Extended Channel Interpretation) en un solo código QR. Esto es útil cuando necesitas incrustar caracteres de diferentes juegos de caracteres, como el símbolo del euro.

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# Create the builder instance
ext_builder = ExtCodetextBuilder()

# Add a plain text segment
ext_builder.add_plain_codetext("ABC123")

# Add an ECI segment that uses ISO‑IEC 8859‑1 (code page 3)
ext_builder.add_eci_codetext(3, "€123")
```

**Por qué este paso es importante:**  
`ExtCodetextBuilder` ensambla la cadena final que el codificador QR procesará. Sin construir el codetext extendido, el código de barras contendría solo caracteres ASCII simples y no podría representar símbolos específicos de la localidad.

## Paso 2: Recuperar la cadena combinada de codetext extendido

```python
# Get the final extended codetext that will be encoded
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

La salida se ve así:

```
Extended codetext: ABC123[ECI3]€123
```

El marcador entre corchetes `[ECI3]` indica al codificador QR que cambie al juego de caracteres especificado para los caracteres siguientes.

## Paso 3: Generar el código de barras QR usando el codetext extendido

```python
# Create a QR barcode generator with the extended codetext
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)
```

**Explicación:**  
`BarcodeGenerator` recibe dos argumentos: el tipo de código de barras (`QR`) y los datos a codificar (`extended_codetext`). El generador prepara todas las estructuras internas necesarias para el renderizado.

## Paso 4: Guardar la imagen del código de barras generado

```python
# Define the output path – adjust the folder as needed
output_path = "output/qr_extended.png"

# Save the image in PNG format
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")
```

**Por qué deberías usar este enfoque:**  
Llamar a `save` escribe directamente la imagen en disco usando el formato inferido de la extensión del archivo. El método admite PNG, JPEG, BMP y TIFF, dándote flexibilidad para diferentes consumidores posteriores.

### Verificando la imagen guardada

Abre el archivo `output/qr_extended.png` con cualquier visor de imágenes. Deberías ver un código QR que, al escanearlo, devuelve la cadena `ABC123€123`. La mayoría de los escáneres QR móviles modernos manejan el segmento ECI automáticamente.

## Paso 5: Consultar la información de versión de Aspose.BarCode (opcional pero útil)

Conocer la versión exacta de la biblioteca Aspose.BarCode ayuda cuando necesitas reportar errores o verificar compatibilidad.

```python
# Retrieve version details
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Salida típica:

```
Aspose.BarCode version:
  Assembly version : 23.9.0.0
  File version     : 23.9.0
  Product          : Aspose.BarCode for Python via .NET
  Release date     : 2023-09-15
```

## Script completo – copia, pega y ejecuta

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# 1️⃣ Build extended codetext
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC123")
ext_builder.add_eci_codetext(3, "€123")
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 2️⃣ Generate QR barcode
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)

# 3️⃣ Save barcode image
output_path = "output/qr_extended.png"
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")

# 4️⃣ Display version information
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Ejecutar el script produce la imagen del código QR y muestra tanto el codetext extendido como los detalles de versión en la consola.

## Variaciones comunes y casos límite

| Situación | Ajuste recomendado |
|-----------|--------------------|
| **Juego de caracteres diferente** | Cambia el identificador ECI pasado a `add_eci_codetext`. Para UTF‑8 usa `5`. |
| **Corrección de errores más alta** | Establece `barcode.parameters.barcode.qr_error_level = bc.QRErrorLevel.H` antes de llamar a `save`. |
| **Tamaño de imagen personalizado** | Usa `barcode.parameters.image_width` y `barcode.parameters.image_height` para controlar las dimensiones en píxeles. |
| **Salida no PNG** | Cambia la extensión del archivo en `output_path` a `.jpg` o `.bmp`. La biblioteca selecciona automáticamente el codificador correcto. |

## Consejos profesionales

* **Crear la carpeta de salida** programáticamente si puede no existir:

  ```python
  import os
  os.makedirs(os.path.dirname(output_path), exist_ok=True)
  ```

* **Validar el código QR** después de generarlo leyendo de nuevo con `aspose.barcode.BarcodeReader`. Esto asegura que los datos codificados coincidan con lo esperado, especialmente al usar segmentos ECI.

  ```python
  reader = bc.BarcodeReader(output_path, bc.DecodeType.QR)
  for result in reader.read():
      print("Decoded text:", result.code_text)
  ```

* **Consejo de rendimiento** – reutiliza una única instancia de `BarcodeGenerator` si necesitas generar muchos códigos QR en un bucle. Restablece la propiedad `code_text` en lugar de crear un nuevo objeto en cada iteración.

## Conclusión

Ahora sabes cómo **generar un código de barras QR** en Python con Aspose.Barcode, construir un codetext extendido que mezcle segmentos planos y ECI, y **guardar correctamente la imagen del código de barras** en disco. El script también muestra cómo obtener información de versión de la biblioteca para la solución de problemas.

Próximos pasos que podrías explorar incluyen:

* Añadir superposición de logotipo o colores personalizados al código QR.
* Incrustar el código de barras QR directamente en PDFs usando Aspose.PDF.
* Automatizar la generación por lotes para grandes conjuntos de datos.

¡Siéntete libre de experimentar con diferentes cargas de datos, niveles de corrección de errores y formatos de imagen! ¡Feliz codificación!


## ¿Qué deberías aprender a continuación?


Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [How to generate Code 128 barcode and save barcode image with Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [How to generate DataMatrix barcode in Python with Aspose.BarCode](/barcode/english/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}