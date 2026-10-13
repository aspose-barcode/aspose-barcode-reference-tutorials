---
category: general
date: 2026-09-23
description: Aprenda a generar códigos de barras Code 128 y guardar la imagen del
  código de barras usando Aspose.BarCode en Python – guía paso a paso.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate code 128 barcode
- save barcode image
- Aspose.BarCode Python
- extended codetext builder
- barcode PNG export
language: es
lastmod: 2026-09-23
og_description: Genera un código de barras Code 128 y guarda la imagen del código
  de barras con Aspose.BarCode en Python. Sigue este ejemplo completo para crear,
  personalizar y exportar el código de barras como un archivo PNG.
og_image_alt: Python-generated Code 128 barcode saved as PNG image
og_title: Generar código de barras Code 128 y guardar la imagen del código de barras
  – Guía de Python
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to generate Code 128 barcode and save barcode image using
    Aspose.BarCode in Python – step‑by‑step guide.
  headline: How to generate Code 128 barcode and save barcode image with Aspose.BarCode
  type: TechArticle
tags:
- barcode
- Code 128
- Python
- Aspose
title: Cómo generar un código de barras Code 128 y guardar la imagen del código de
  barras con Aspose.BarCode
url: /es/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo generar un código de barras Code 128 y guardar la imagen del código de barras con Aspose.BarCode

Si necesitas **generar un código de barras Code 128** y **guardar la imagen del código de barras** en un proyecto Python, este tutorial muestra los pasos exactos. Usando `ExtCodetextBuilder` de Aspose.BarCode puedes incrustar texto plano y segmentos Unicode en una sola carga útil, y luego renderizar el resultado como un archivo PNG.

Verás un script completo y ejecutable, una explicación de cada línea y consejos para problemas comunes, como el manejo de la codificación ECI o la elección de la carpeta de salida correcta. No se requiere documentación externa—solo copia, pega y ejecuta.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* Python 3.8+ instalado.
* El paquete `aspose.barcode` (instálalo con `pip install aspose-barcode`).
* Permiso de escritura en el directorio donde se guardará el PNG.

El código funciona con cualquier simbología soportada por Aspose.BarCode, pero el ejemplo se centra en **Code 128** porque codifica eficientemente datos alfanuméricos y admite conjuntos de caracteres extendidos.

## Paso 1: Importar las clases requeridas

```python
import barcode                     # Core Aspose.BarCode namespace
from barcode import BarCodeWriter, BarCodeEncodeMode, BarCodeImageFormat
from barcode import ExtCodetextBuilder, BuildVersionInfo
```

*¿Por qué este paso?* Importar las clases te da acceso al constructor para texto codificado extendido, al escritor que crea la imagen y al asistente de versiones que puede ser útil para depurar actualizaciones de la biblioteca.

## Paso 2: Construir el texto codificado extendido

```python
# Create a builder for extended codetext
builder = ExtCodetextBuilder()

# Add plain text (no ECI) – this part is simple ASCII
builder.add_plain_codetext("ABC123")

# Add a Unicode segment with ECI 0x03 (UTF‑8). The word “Пример” means “Example” in Russian.
builder.add_eci_codetext(0x03, "Пример")

# Retrieve the full extended codetext string
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

`ExtCodetextBuilder` te permite mezclar datos ASCII simples y datos Unicode en una sola carga útil del código de barras. El byte ECI (Extended Channel Interpretation) `0x03` indica al escáner que los bytes siguientes están codificados en UTF‑8, lo cual es esencial para idiomas como ruso, chino o árabe.

## Paso 3: Configurar el escritor de códigos de barras para Code 128

```python
writer = BarCodeWriter()
writer.encode_type = BarCodeEncodeMode.CODE_128   # Choose Code 128 symbology
writer.code_text = extended_codetext
```

Establecer `encode_type` a `CODE_128` indica al escritor que renderice un **código de barras Code 128**. La propiedad `code_text` recibe la cadena extendida construida en el paso anterior.

## Paso 4: Guardar la imagen del código de barras como PNG

```python
output_path = "YOUR_DIRECTORY/extended_codetext.png"
writer.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode image saved to {output_path}")
```

El método `save` escribe el código de barras en un archivo. Usar `BarCodeImageFormat.PNG` garantiza compresión sin pérdida y amplia compatibilidad con aplicaciones web y móviles.

## Paso 5 (opcional): Verificar la versión de la biblioteca Aspose.BarCode

```python
version_info = BuildVersionInfo()
print("Assembly version :", version_info.ASSEMBLY_VERSION)
print("Product version   :", f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR}")
print("Release date      :", version_info.RELEASE_DATE)
```

Conocer la versión exacta de la biblioteca ayuda cuando necesitas reportar errores o comparar el comportamiento entre versiones.

## Resultado esperado

Ejecutar el script produce una salida en consola similar a:

```
Extended codetext: ABC123[ECI=03]Пример
Assembly version : 23.12.0.0
Product version   : 23.12
Release date      : 2023-12-01
Barcode image saved to YOUR_DIRECTORY/extended_codetext.png
```

El PNG generado (`extended_codetext.png`) se ve así:

![Python-generated Code 128 barcode saved as PNG image](images/code128_extended.png)

*La imagen muestra un código de barras Code 128 que codifica tanto la cadena ASCII `ABC123` como la palabra rusa “Пример”.*

## Preguntas frecuentes y manejo de casos límite

| Pregunta | Respuesta |
|----------|-----------|
| **¿Puedo usar una simbología diferente?** | Sí. Reemplaza `BarCodeEncodeMode.CODE_128` por cualquier otro modo soportado, como `QR`, `EAN_13` o `PDF_417`. |
| **¿Qué pasa si mi texto Unicode contiene emojis?** | Los emojis también son caracteres UTF‑8, por lo que la misma llamada `add_eci_codetext` funciona. Asegúrate de que el escáner de destino admita el ECI que uses. |
| **¿Cómo cambio el tamaño de la imagen?** | Establece `writer.x_dimension` y `writer.bar_height` antes de llamar a `save`. |
| **¿Qué carpeta debo usar para `output_path`?** | Cualquier carpeta a la que el proceso Python pueda escribir. Usa `os.makedirs` con `exist_ok=True` para crearla automáticamente. |

## Consejos profesionales

* **Evita codificar rutas de forma rígida.** Usa `os.path.join` y `Path` del módulo `pathlib` para compatibilidad multiplataforma.
* **Valida el código de barras.** Después de guardar, puedes leer la imagen con `barcode.BarCodeReader` para confirmar que el texto codificado coincide con `extended_codetext`.
* **Consejo de rendimiento.** Si generas muchos códigos de barras en un bucle, reutiliza una única instancia de `BarCodeWriter` y solo actualiza `code_text` en cada iteración.

## Conclusión

Ahora sabes cómo **generar un código de barras Code 128** con datos ASCII y Unicode combinados y **guardar la imagen del código de barras** como PNG usando Aspose.BarCode en Python. El script completo cubre la construcción del texto codificado extendido, la configuración del escritor, la exportación de la imagen y la verificación de versiones de la biblioteca.

A partir de aquí puedes explorar:

* Añadir colores de primer plano/fondo (`writer.back_color`, `writer.fore_color`).
* Incrustar el código de barras en PDFs con `Aspose.PDF`.
* Usar la clase `BarCodeReader` para decodificar la imagen guardada y verificar el contenido automáticamente.

¡Feliz codificación, y siéntete libre de experimentar con otras simbologías y formatos de imagen!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Generar código de barras Code128 con Aspose.Barcode Python – Guía completa](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [Cómo generar códigos de barras en Python – guía paso a paso completa](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Cómo generar una imagen de código QR en Python con Aspose.Barcode – Guía completa](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}