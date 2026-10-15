---
category: general
date: 2026-10-15
description: Crea un código de barras a partir de una cadena en Python usando Aspose.BarCode,
  aprende a generar un código de barras Code 128 y guarda el PNG del código de barras
  en solo unas pocas líneas.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from string
- generate code 128 barcode
- how to save barcode
- generate barcode png
- encode data into barcode
language: es
lastmod: 2026-10-15
og_description: Crear código de barras a partir de una cadena en Python para codificar
  datos en un código de barras Code 128 y guardarlo como archivo PNG con Aspose.BarCode.
og_image_alt: Screenshot of a generated Code 128 barcode saved as a PNG image
og_title: Crear código de barras a partir de una cadena en Python – guía paso a paso
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode from string in Python using Aspose.BarCode, learn how
    to generate Code 128 barcode and save barcode PNG in just a few lines.
  headline: Create barcode from string in Python with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Replace `EncodeTypes.CODE_128` with another enum value such as `EncodeTypes.QR`,
      `EncodeTypes.EAN_13`, or `EncodeTypes.PDF_417`. The rest of the code remains
      the same.
    question: What if I need a different symbology?
  - answer: Code 128 supports the full 128‑character ASCII set. For Unicode data,
      consider using QR Code (`EncodeTypes.QR`) which handles UTF‑8 natively.
    question: Can I generate a barcode from non‑ASCII characters?
  - answer: Pass a different member of `BarCodeImageFormat` to `save`, e.g., `BarCodeImageFormat.JPEG`
      or `BarCodeImageFormat.BMP`.
    question: How do I change the image format?
  - answer: Wrap the `save` call in a try/except block and handle `PermissionError`
      gracefully, perhaps by prompting the user for an alternative path.
    question: What if the output directory is read‑only?
  type: FAQPage
tags:
- barcode
- Python
- Aspose
- Code128
title: Crear código de barras a partir de una cadena en Python con Aspose.BarCode
url: /es/python-java/general/create-barcode-from-string-in-python-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear código de barras a partir de una cadena en Python con Aspose.BarCode

Si necesitas **crear código de barras a partir de una cadena** en Python, esta guía te muestra los pasos exactos con Aspose.BarCode. Aprenderás cómo **generar un código de barras Code 128**, ajustar su apariencia y **guardar el PNG del código de barras** en disco. La solución funciona en cualquier plataforma que soporte Python 3.9+ y requiere solo unas pocas líneas de código.

Generar códigos de barras programáticamente elimina errores de entrada manual y agiliza flujos de trabajo como el seguimiento de inventario, la emisión de tickets y la impresión de etiquetas. Al final de este tutorial podrás **codificar datos en un código de barras**, personalizar sus dimensiones y almacenar la imagen donde la necesites.

## Prerrequisitos

Antes de comenzar, asegúrate de tener:

- Python 3.9 o superior instalado  
- Acceso a Internet para descargar el paquete Aspose.BarCode  
- Permiso de escritura en el directorio donde guardarás el archivo PNG  

Si estás usando un entorno virtual (altamente recomendado), actívalo ahora.

## Instalar el paquete Aspose.BarCode para Python

Aspose proporciona una biblioteca pure‑Python que maneja todas las simbologías de códigos de barras comunes, incluido Code 128. Instálala con pip:

```bash
pip install aspose-barcode
```

*Consejo profesional:* Fija la versión (p.ej., `aspose-barcode==23.9`) para evitar cambios inesperados que rompan la producción.

## Crear código de barras a partir de una cadena en Python

El primer paso funcional es importar las clases requeridas e instanciar un generador para la simbología deseada. Este ejemplo usa **Code 128**, que es ideal para datos alfanuméricos.

```python
# Step 1: Import the Aspose.BarCode classes
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 2: Create a generator for Code 128 and provide the data string
barcode_generator = BarcodeGenerator(EncodeTypes.CODE_128, "1234567890")
```

**Por qué es importante:** `EncodeTypes.CODE_128` indica a la biblioteca qué estándar de código de barras aplicar, mientras que el segundo argumento (`"1234567890"`) es la **cadena que deseas codificar en el código de barras**. Puedes reemplazarla con cualquier cadena ASCII de hasta 80 caracteres para Code 128.

## Generar código de barras Code 128

Una vez que el generador está listo, puedes producir la imagen del código de barras en memoria. La biblioteca renderiza automáticamente el código de barras basado en los datos proporcionados.

```python
# Step 3: Render the barcode to an image object (in memory)
barcode_image = barcode_generator.generate_barcode_image()
```

En este punto `barcode_image` es una instancia de `System.Drawing.Image` (en Windows) o un objeto de imagen compatible en otras plataformas. Puedes mostrarlo directamente en una GUI, incrustarlo en un PDF o seguir personalizándolo.

## Ajustar la apariencia del código de barras

Ajustar finamente las propiedades visuales garantiza que el código de barras se escanee de forma fiable en tu entorno específico. Los ajustes comunes incluyen la dimensión X (el ancho de la barra más estrecha) y la altura total de la barra.

```python
# Step 4: Adjust appearance – X dimension and bar height
barcode_generator.parameters.barcode.x_dimension.pixels = 2   # width of the smallest bar
barcode_generator.parameters.barcode.bar_height.pixels = 100  # height of the bars (optional)
```

*¿Por qué ajustar estos valores?*  
- **Dimensión X** influye en la densidad del código de barras; un valor más pequeño produce un código más compacto que cabe en etiquetas pequeñas.  
- **Altura de la barra** afecta la legibilidad; barras más altas son más fáciles de detectar por los escáneres a distancia.

También puedes cambiar colores, añadir márgenes o incrustar texto legible por humanos mediante el objeto `parameters`. Consulta la documentación de Aspose.BarCode para la lista completa de opciones.

## Cómo guardar el código de barras como PNG

Guardar la imagen generada es el paso final en el flujo de trabajo de **crear código de barras a partir de una cadena**. La biblioteca soporta varios formatos; PNG es sin pérdida y ampliamente soportado.

```python
# Step 5: Save the barcode image to a PNG file
output_path = "output/barcode.png"
barcode_generator.save(output_path, BarCodeImageFormat.PNG)
```

El método `save` escribe la imagen en el sistema de archivos usando el formato que especificas. Si el directorio de destino (`output/` en este ejemplo) no existe, Python lanzará un `FileNotFoundError`. Crea el directorio previamente o maneja la excepción:

```python
import os

output_dir = os.path.dirname(output_path)
os.makedirs(output_dir, exist_ok=True)   # ensures the directory exists
barcode_generator.save(output_path, BarCodeImageFormat.PNG)
```

**Resultado esperado:** Después de ejecutar el script, `output/barcode.png` contiene un código de barras Code 128 claro que codifica `"1234567890"`. Abrir el archivo en cualquier visor de imágenes mostrará un código de barras negro sobre blanco listo para escanear.

## Ejemplo completo y ejecutable

Juntando todas las piezas, aquí tienes un script autónomo que puedes copiar, pegar y ejecutar:

```python
"""
Complete example: create barcode from string, generate Code 128 barcode,
customize appearance, and save barcode PNG using Aspose.BarCode.
"""

import os
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1. Define input data and output location
data_to_encode = "1234567890"
output_path = "output/barcode.png"

# 2. Ensure the output directory exists
os.makedirs(os.path.dirname(output_path), exist_ok=True)

# 3. Initialise the generator for Code 128
generator = BarcodeGenerator(EncodeTypes.CODE_128, data_to_encode)

# 4. Optional: tweak visual parameters
generator.parameters.barcode.x_dimension.pixels = 2
generator.parameters.barcode.bar_height.pixels = 100

# 5. Save as PNG
generator.save(output_path, BarCodeImageFormat.PNG)

print(f"Barcode saved to {output_path}")
```

Ejecuta el script con `python create_barcode.py`. Si todo está instalado correctamente, verás:

```
Barcode saved to output/barcode.png
```

Abre el archivo PNG y verifica que el código de barras coincida con la cadena original usando cualquier aplicación escáner de códigos de barras.

## Preguntas comunes y casos límite

- **¿Qué pasa si necesito una simbología diferente?**  
  Reemplaza `EncodeTypes.CODE_128` con otro valor de enumeración como `EncodeTypes.QR`, `EncodeTypes.EAN_13` o `EncodeTypes.PDF_417`. El resto del código permanece igual.

- **¿Puedo generar un código de barras a partir de caracteres no ASCII?**  
  Code 128 soporta el conjunto completo de 128 caracteres ASCII. Para datos Unicode, considera usar QR Code (`EncodeTypes.QR`) que maneja UTF‑8 de forma nativa.

- **¿Cómo cambio el formato de imagen?**  
  Pasa un miembro diferente de `BarCodeImageFormat` a `save`, por ejemplo, `BarCodeImageFormat.JPEG` o `BarCodeImageFormat.BMP`.

- **¿Qué pasa si el directorio de salida es de solo lectura?**  
  Envuelve la llamada `save` en un bloque try/except y maneja `PermissionError` de forma elegante, quizás solicitando al usuario una ruta alternativa.

- **Consejo de rendimiento:**  
  Generar miles de códigos de barras en un bucle puede ser intensivo para la CPU. Reutiliza una única instancia de `BarcodeGenerator` y solo actualiza `generator.parameters.barcode.code_text` entre iteraciones.

## Conclusión

Ahora sabes cómo **crear código de barras a partir de una cadena** en Python usando Aspose.BarCode, **generar un código de barras Code 128**, personalizar su tamaño y **guardar el PNG del código de barras** en disco. Esta solución de extremo a extremo te permite **codificar datos en un código de barras** de forma rápida y fiable, facilitando la integración de códigos de barras en sistemas de inventario, plataformas de tickets o cualquier aplicación que requiera identificadores legibles por máquina.

**Próximos pasos**

- Explora otras simbologías (alternativas a `generate code 128 barcode`) como QR o DataMatrix.  
- Añade lógica de manejo de errores para que el script sea robusto en producción (`how to save barcode` failures).  
- Incrusta el PNG generado en PDFs o informes HTML (`generate barcode png` para la web).  

¡Feliz codificación y disfruta de la simplicidad de la generación programática de códigos de barras!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo generar código de barras Code 128 y guardar la imagen del código de barras con Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [Cómo generar una imagen de código QR en Python con Aspose.Barcode – Guía completa](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Crear PNG de código de barras en Python – Guía completa de Aspose.Barcode](/barcode/english/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}