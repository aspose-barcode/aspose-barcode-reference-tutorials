---
category: general
date: 2026-08-12
description: Configura rápidamente el diseño de códigos de barras Databar en Python.
  Aprende a establecer columnas, filas y guardar imágenes con la biblioteca generadora
  de códigos de barras.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- configure databar barcode layout
- Databar Expanded Stacked
- barcode generator Python
- set barcode columns
- set barcode rows
language: es
lastmod: 2026-08-12
og_description: Configura el diseño del código de barras Databar en Python para controlar
  columnas, filas y la salida de imagen. Sigue esta guía para obtener una solución
  lista para ejecutar.
og_image_alt: Screenshot of a Databar Expanded Stacked barcode with custom column
  layout
og_title: Configura el diseño del código de barras Databar en Python – tutorial completo
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Configure Databar barcode layout in Python quickly. Learn to set columns,
    rows, and save images with the barcode generator library.
  headline: Configure Databar barcode layout in Python – step‑by‑step guide
  type: TechArticle
- description: Configure Databar barcode layout in Python quickly. Learn to set columns,
    rows, and save images with the barcode generator library.
  name: Configure Databar barcode layout in Python – step‑by‑step guide
  steps:
  - name: Import the required classes
    text: '```python from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
      ```'
  - name: Create a barcode generator for Databar Expanded Stacked
    text: '```python # Initialize the generator with the desired symbology and value
      barcode_generator = BarcodeGenerator( EncodeTypes.DatabarExpandedStacked, "Databar
      Expanded Stacked long" ) ```'
  - name: Set the number of columns (horizontal layout)
    text: '```python # Configure the layout to use 4 columns barcode_generator.parameters.barcode.data_bar.columns
      = 4 ```'
  - name: Save the barcode image with the column layout
    text: '```python # Save the image as a PNG file barcode_generator.save("output/ExpandedCols4.png",
      BarCodeImageFormat.Png) ```'
  - name: Create a second generator for the same barcode type (row layout)
    text: If you prefer a vertical stack, you work with rows instead of columns. The
      code below re‑uses the same value but creates a fresh `BarcodeGenerator` instance
      to avoid mixing column and row settings.
  - name: Set the number of rows (vertical layout)
    text: '```python # Configure the layout to use 3 rows barcode_generator.parameters.barcode.data_bar.rows
      = 3 ```'
  - name: Save the barcode image with the row layout
    text: '```python # Save the vertically stacked barcode barcode_generator.save("output/ExpandedRows3.png",
      BarCodeImageFormat.Png) ```'
  type: HowTo
tags:
- barcode
- Python
- Databar
- image generation
title: Configura el diseño del código de barras Databar en Python – guía paso a paso
url: /es/python-java/general/configure-databar-barcode-layout-in-python-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configurar el diseño del código de barras Databar en Python – guía paso a paso

Si necesitas **configurar el diseño del código de barras Databar en Python**, esta guía te lleva a través de todo el proceso. Verás cómo establecer el número de columnas o filas para un código de barras Databar Expanded Stacked y cómo guardar la imagen resultante con una única llamada a la biblioteca generadora de códigos de barras.

Controlar el diseño es esencial cuando incrustas códigos de barras en empaques estrechos, recibos o pantallas móviles. En las secciones siguientes cubriremos las importaciones requeridas, las dos opciones de diseño (columnas y filas) y las mejores prácticas para guardar una imagen PNG limpia.

## Lo que necesitarás

* Python 3.8 o superior
* `aspose.barcode` (o cualquier paquete compatible de generación de códigos de barras) instalado  
  ```bash
  pip install aspose-barcode
  ```
* Permiso de escritura en una carpeta donde se almacenarán los archivos PNG

No se requieren herramientas externas adicionales: la biblioteca maneja el renderizado, el escalado y la codificación de la imagen internamente.

## Cómo configurar el diseño del código de barras Databar en Python

El núcleo de la solución es la clase `BarcodeGenerator`. Acepta un enum `EncodeTypes` que identifica la simbología del código de barras—en este caso `EncodeTypes.DatabarExpandedStacked`. Después de crear el generador puedes ajustar el diseño estableciendo las propiedades `columns` o `rows` en el objeto de parámetro `data_bar`.

### Paso 1: Importar las clases requeridas

```python
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

Estas importaciones te dan acceso al generador, a la enumeración para los tipos Databar y a la constante de formato de imagen PNG.

### Paso 2: Crear un generador de códigos de barras para Databar Expanded Stacked

```python
# Initialize the generator with the desired symbology and value
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
```

*¿Por qué este paso?*  
`EncodeTypes.DatabarExpandedStacked` indica a la biblioteca que produzca la simbología **Databar Expanded Stacked**, que admite cadenas numéricas más largas manteniendo una huella compacta. El segundo argumento es el dato a codificar; puede ser cualquier cadena que cumpla con la especificación Databar.

### Paso 3: Establecer el número de columnas (diseño horizontal)

```python
# Configure the layout to use 4 columns
barcode_generator.parameters.barcode.data_bar.columns = 4
```

**set barcode columns** es la frase clave para esta operación. Cuando aumentas el recuento de columnas, el código de barras se extiende horizontalmente, lo que puede ser útil para etiquetas anchas. La biblioteca recalcula automáticamente el ancho del módulo para mantener el tamaño total consistente.

#### Consejo profesional
El recuento máximo de columnas para Databar Expanded Stacked es 8. Establecer un valor superior al límite lo limitará al máximo, pero es mejor validar tu entrada de antemano.

### Paso 4: Guardar la imagen del código de barras con el diseño de columnas

```python
# Save the image as a PNG file
barcode_generator.save("output/ExpandedCols4.png", BarCodeImageFormat.Png)
```

**save barcode image** es la acción que escribe el código de barras renderizado en disco. PNG es sin pérdida, lo que preserva los bordes nítidos requeridos para un escaneo fiable.

### Paso 5: Crear un segundo generador para el mismo tipo de código de barras (diseño de filas)

Si prefieres una pila vertical, trabajas con filas en lugar de columnas. El código a continuación reutiliza el mismo valor pero crea una nueva instancia de `BarcodeGenerator` para evitar mezclar configuraciones de columnas y filas.

```python
# New generator instance for row configuration
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
```

### Paso 6: Establecer el número de filas (diseño vertical)

```python
# Configure the layout to use 3 rows
barcode_generator.parameters.barcode.data_bar.rows = 3
```

**set barcode rows** organiza los módulos del código de barras verticalmente. Un diseño de tres filas reduce la altura de cada pila individual, haciendo que el código de barras sea adecuado para recibos estrechos o pantallas móviles.

#### Caso límite
Si estableces `rows` en 1, la biblioteca genera un Databar de una sola fila (equivalente a un Databar estándar). Los valores por debajo de 1 se ignoran y se restablecen al valor predeterminado (1 fila).

### Paso 7: Guardar la imagen del código de barras con el diseño de filas

```python
# Save the vertically stacked barcode
barcode_generator.save("output/ExpandedRows3.png", BarCodeImageFormat.Png)
```

Nuevamente, **save barcode image** usando PNG para mantener la salida nítida.

## Ejemplo completo ejecutable

Unir todas las piezas te brinda un script autónomo que puedes incorporar a cualquier proyecto Python.

```python
# ------------------------------------------------------------
# configure_databar_layout.py
# Demonstrates how to configure Databar barcode layout in Python
# ------------------------------------------------------------

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# -----------------------------------------------------------------
# 1️⃣ Column layout – 4 columns
# -----------------------------------------------------------------
col_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
col_generator.parameters.barcode.data_bar.columns = 4   # set barcode columns
col_path = os.path.join(output_dir, "ExpandedCols4.png")
col_generator.save(col_path, BarCodeImageFormat.Png)   # save barcode image
print(f"Column layout saved to {col_path}")

# -----------------------------------------------------------------
# 2️⃣ Row layout – 3 rows
# -----------------------------------------------------------------
row_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
row_generator.parameters.barcode.data_bar.rows = 3      # set barcode rows
row_path = os.path.join(output_dir, "ExpandedRows3.png")
row_generator.save(row_path, BarCodeImageFormat.Png)   # save barcode image
print(f"Row layout saved to {row_path}")
```

**Salida esperada**

Ejecutar el script crea dos archivos PNG:

* `output/ExpandedCols4.png` – un código de barras extendido a través de cuatro columnas
* `output/ExpandedRows3.png` – un código de barras comprimido en tres filas

Ambas imágenes pueden abrirse en cualquier visor de imágenes o importarse directamente en facturas PDF, plantillas de etiquetas o páginas web.

## Preguntas frecuentes y solución de problemas

| Question | Answer |
|----------|--------|
| *What if the barcode looks blurry?* | Increase the image resolution by setting `barcode_generator.parameters.image_width` and `image_height` before calling `save`. |
| *Can I use other image formats?* | Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as needed. |
| *Is there a limit on the data length?* | Databar Expanded Stacked supports up to 74 numeric characters. Exceeding the limit raises a `ArgumentException`. |
| *How do I change the foreground color?* | Use `barcode_generator.parameters.barcode.color = Color.Blue` (import `System.Drawing.Color`). |
| *Can I combine columns and rows?* | No. The API treats columns and rows as mutually exclusive layout modes. Choose one per barcode instance. |

## Próximos pasos

Ahora que puedes **configure Databar barcode layout**, considera explorar estos temas relacionados:

* **Add text captions** – use `barcode_generator.parameters.barcode.code_text` to display the encoded value beneath the image.
* **Embed the barcode in a PDF** – combine the generated PNG with `aspose.pdf` to create printable documents.
* **Dynamic sizing** – calculate optimal column or row counts based on label dimensions at runtime.
* **Batch processing** – loop over a CSV of product codes to generate a library of barcode images automatically.

Experimenta con diferentes valores de columnas y filas para ver cómo afectan la fiabilidad del escaneo en tus dispositivos objetivo. Cuanto más pruebes, mejor comprenderás los compromisos entre el tamaño del código de barras, la legibilidad y las limitaciones de espacio.

---

*¡Feliz codificación! Si encontraste útil este tutorial, compártelo con tus compañeros o deja un comentario sobre los desafíos de diseño que enfrentaste.*

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Crear imagen de código de barras DotCode – filas y columnas (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Crear imagen de código de barras c# – Configurar filas y columnas de Codablock F](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Ajuste de altura del código de barras Databar unidimensional](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}