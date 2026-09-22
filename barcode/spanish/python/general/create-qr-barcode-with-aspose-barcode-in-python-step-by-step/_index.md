---
category: general
date: 2026-08-09
description: Crea un código QR en Python usando Aspose.BarCode. Aprende cómo generar
  un codetext extendido, ajustar la apariencia y guardar la imagen, todo en un solo
  tutorial.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create QR barcode
- Aspose.BarCode Python
- extended codetext QR
- QR code generation Python
- barcode visual customization
language: es
lastmod: 2026-08-09
og_description: Crea un código QR en Python con Aspose.BarCode. Esta guía muestra
  cómo generar un codetext ampliado, establecer parámetros visuales y exportar la
  imagen.
og_image_alt: Screenshot of a generated QR barcode created with Aspose.BarCode in
  Python
og_title: Crear código de barras QR con Aspose.BarCode en Python – ejemplo completo
  de código
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  headline: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  type: TechArticle
- description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  name: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  steps:
  - name: Common variations
    text: '- **Multiple ECI segments:** Call `add_eci_codetext` multiple times to
      mix several languages. - **Different ECI identifiers:** Use `27` for ISO‑8859‑1,
      `28` for ISO‑8859‑2, etc., depending on your target encoding.'
  - name: Edge case handling
    text: '- **High‑density data:** If the encoded data is large, you may need to
      increase `x_dimension` or choose a higher error‑correction level (via `qr_generator.parameters.qr.error_correction_level`).
      - **Transparent background:** Set `qr_generator.parameters.barcode.bg_color
      = Color.Transparent` for PNGs'
  - name: Verifying the result
    text: 'Open the saved file in any image viewer. You should see a QR code that,
      when scanned, returns the combined string:'
  type: HowTo
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: Crear código de barras QR con Aspose.BarCode en Python – guía paso a paso
url: /es/python/general/create-qr-barcode-with-aspose-barcode-in-python-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear código de barras QR con Aspose.BarCode en Python – guía paso a paso

Si necesitas **crear un código de barras QR** en Python, este tutorial te guía a través de todo el proceso usando la biblioteca Aspose.BarCode. Ya sea que estés codificando IDs de productos, texto multilingüe o datos personalizados, verás cómo construir un codetext extendido, ajustar la configuración visual y guardar la imagen final en un único script ejecutable.

El ejemplo también muestra cómo mostrar la versión de la biblioteca, lo que te ayuda a verificar que estás ejecutando una versión compatible. Al final de esta guía tendrás una imagen de código de barras QR lista para usar y una comprensión clara de cada opción de configuración.

## Requisitos previos

- Python 3.8+ instalado.
- El paquete `aspose-barcode` (instalar mediante `pip install aspose-barcode`).
- Familiaridad básica con la sintaxis de Python.
- Permiso de escritura en el directorio de salida donde se guardará el archivo PNG.

> **Consejo profesional:** Usa un entorno virtual para evitar conflictos de versiones con otros proyectos.

## Paso 1: Verificar la versión de la biblioteca Aspose.BarCode

Mostrar la versión de la biblioteca garantiza que estás usando una versión que soporta codetext extendido y codificación QR.

```python
from asposebarcode import BuildVersionInfo

# Show the current Aspose.BarCode version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)
```

**Por qué es importante:**  
Las versiones más antiguas pueden carecer de la clase `ExtCodetextBuilder` necesaria para segmentos mixtos de texto plano y ECI. Confirmar la versión evita errores en tiempo de ejecución más adelante en el flujo de trabajo.

## Paso 2: Construir una cadena de codetext extendido

Un codetext extendido te permite combinar datos ASCII simples con segmentos Unicode (ECI), lo cual es esencial para códigos QR multilingües.

```python
from asposebarcode import ExtCodetextBuilder

# Initialize the builder
ext_builder = ExtCodetextBuilder()

# Add a plain segment – typically a product ID or numeric code
ext_builder.add_plain_codetext("ABC12345")

# Add an ECI segment – here we embed Japanese greeting "こんにちは"
# 26 is the ECI identifier for UTF‑8 encoding
ext_builder.add_eci_codetext(26, "こんにちは")

# Retrieve the full extended codetext that the QR generator will use
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")
```

**Por qué es importante:**  
El método `add_plain_codetext` almacena los datos como ASCII estándar, mientras que `add_eci_codetext` antepone un bloque Unicode con el designador ECI apropiado. Este enfoque garantiza que los escáneres QR interpreten correctamente el texto japonés, evitando caracteres corruptos.

### Variaciones comunes

- **Segmentos ECI múltiples:** Llama a `add_eci_codetext` varias veces para mezclar varios idiomas.
- **Identificadores ECI diferentes:** Usa `27` para ISO‑8859‑1, `28` para ISO‑8859‑2, etc., según la codificación objetivo.

## Paso 3: Generar el código de barras QR usando el codetext extendido

Ahora que tenemos una cadena correctamente formateada, podemos crear el código QR.

```python
from asposebarcode import BarCodeGenerator, EncodeTypes, BarCodeImageFormat

# Create the QR generator with the extended codetext
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)
```

**Por qué es importante:**  
`EncodeTypes.QR` indica a Aspose.BarCode que use la simbología QR. Pasar el `extended_codetext` directamente vincula los datos mixtos a la matriz QR, preservando tanto la parte plana como la Unicode.

## Paso 4: Ajustar la apariencia visual (opcional pero recomendado)

Ajustar finamente los parámetros visuales del código de barras mejora la fiabilidad del escaneo y se alinea con las directrices de marca.

```python
# Set module (pixel) size – larger values increase overall image size
qr_generator.parameters.barcode.x_dimension = 4      # each module = 4 pixels

# Set border thickness – a thin white border helps scanners isolate the QR code
qr_generator.parameters.barcode.border_width = 2    # 2-pixel border
```

**Por qué es importante:**  
- **`x_dimension`** controla el tamaño de cada módulo QR; si es demasiado pequeño puede causar errores de lectura en dispositivos de baja resolución.  
- **`border_width`** agrega una zona silenciosa. Algunos escáneres requieren al menos una zona silenciosa de 4 módulos; la biblioteca la agrega automáticamente, pero puedes aumentarla para mayor seguridad.

### Manejo de casos límite

- **Datos de alta densidad:** Si los datos codificados son grandes, puede que necesites aumentar `x_dimension` o elegir un nivel de corrección de errores más alto (a través de `qr_generator.parameters.qr.error_correction_level`).  
- **Fondo transparente:** Configura `qr_generator.parameters.barcode.bg_color = Color.Transparent` para PNGs con canales alfa.

## Paso 5: Guardar la imagen del código de barras QR

Finalmente, escribe la imagen en disco en el formato que prefieras.

```python
# Define output path – replace YOUR_DIRECTORY with an actual folder
output_file = "YOUR_DIRECTORY/extended_qr.png"

# Save as PNG; other formats include JPEG, BMP, GIF, TIFF
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

**Por qué es importante:**  
Guardar como PNG preserva la calidad sin pérdidas, lo cual es ideal para códigos QR que necesitan bordes nítidos. Si necesitas un formato diferente para una aplicación web, simplemente cambia la enumeración `BarCodeImageFormat`.

### Verificando el resultado

Abre el archivo guardado en cualquier visor de imágenes. Deberías ver un código QR que, al escanearlo, devuelve la cadena combinada:

```
ABC12345
こんにちは
```

La mayoría de las aplicaciones modernas de escáner QR muestran primero el segmento plano y luego renderizan correctamente el saludo en japonés.

---

## Script completo ejecutable

Copia todo el bloque a continuación en un archivo llamado `create_qr_barcode.py` y ejecútalo con `python create_qr_barcode.py`. Ajusta `YOUR_DIRECTORY` a una carpeta con permisos de escritura en tu máquina.

```python
# create_qr_barcode.py
from asposebarcode import (
    BuildVersionInfo,
    ExtCodetextBuilder,
    BarCodeGenerator,
    EncodeTypes,
    BarCodeImageFormat,
)

# 1️⃣ Display library version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)

# 2️⃣ Build extended codetext (plain + Japanese Unicode)
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC12345")
ext_builder.add_eci_codetext(26, "こんにちは")
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")

# 3️⃣ Create QR generator
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)

# 4️⃣ Optional visual tweaks
qr_generator.parameters.barcode.x_dimension = 4
qr_generator.parameters.barcode.border_width = 2

# 5️⃣ Save image
output_file = "YOUR_DIRECTORY/extended_qr.png"
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

Ejecutar este script muestra la versión, el codetext extendido y una confirmación de que el archivo PNG fue creado.

---

## Conclusión

Ahora sabes cómo **crear imágenes de código de barras QR** en Python usando Aspose.BarCode. El tutorial cubrió:

1. Verificar la versión de la biblioteca.
2. Construir codetext extendido con segmentos planos y ECI (Unicode).
3. Generar el código QR.
4. Personalizar parámetros visuales como el tamaño del módulo y el ancho del borde.
5. Guardar la imagen final en formato PNG.

Desde aquí puedes explorar:

- Cambiar los niveles de corrección de errores (`qr_generator.parameters.qr.error_correction_level`).
- Añadir un logotipo o imagen de fondo (`qr_generator.parameters.qr.logo`).
- Exportar a otros formatos como SVG para gráficos web escalables.
- Integrar el generador en un endpoint Flask o Django para crear códigos QR al vuelo.

Experimenta con diferentes cargas de datos y configuraciones visuales para adaptarlas a la marca y requisitos de escaneo de tu aplicación. ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo crear codetext extendido de dotcode con Aspose.BarCode para .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Crear código de barras aspose .net - Configuración del texto de DataMatrix](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Cómo crear zona silenciosa de código de barras para ITF-14 usando Aspose.BarCode para .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}