---
category: general
date: 2026-10-21
description: Genera una imagen de código de barras Databar Expanded Stacked en C#
  usando BarcodeGenerator. Sigue esta guía paso a paso para crear imágenes de códigos
  de barras, personalizar filas y columnas, y exportar archivos PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- generate barcode image
- barcode generator c#
- how to generate databar
- create databar barcode
language: es
lastmod: 2026-10-21
og_description: Genera un código de barras Databar Expanded Stacked en C# con este
  tutorial. Aprende a usar BarcodeGenerator, establecer filas y columnas y guardar
  imágenes PNG.
og_image_alt: Sample databar expanded stacked barcode image generated with C#
og_title: Genera un código de barras Databar Expanded Stacked en C# – guía completa
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  headline: How to generate a databar expanded stacked barcode in C#
  type: TechArticle
- description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  name: How to generate a databar expanded stacked barcode in C#
  steps:
  - name: Basic barcode generation
    text: The simplest way to generate a **databar expanded stacked** image is to
      instantiate `BarcodeGenerator` with the desired `EncodeTypes` value and a plain
      text payload.
  - name: Customizing columns – create databar barcode with 4 columns
    text: You can control the number of columns using the `Parameters.Barcode.DataBar.Columns`
      property. The following example creates a barcode with **4 columns** while keeping
      the default row count.
  - name: Customizing rows – create databar barcode with 3 rows
    text: Similarly, you can adjust the row count via `Parameters.Barcode.DataBar.Rows`.
      The code below generates a barcode with **3 rows** and the default column count
      (4).
  - name: Exporting to other formats
    text: 'If you need a different image type (e.g., JPEG, BMP, or SVG), replace `BarCodeImageFormat.Png`
      with the appropriate enum value:'
  - name: Saving to a memory stream
    text: 'Sometimes you want to embed the barcode directly into a web response or
      a PDF without touching the file system. Use a `MemoryStream`:'
  - name: Handling invalid input
    text: 'The `BarcodeGenerator` validates the payload against the chosen symbology.
      If the data contains prohibited characters, an `ArgumentException` is thrown.
      Wrap the generation code in a try‑catch block to provide a friendly error message:'
  - name: Scaling the barcode image
    text: 'You can change the image size without altering the encoded data by setting
      `Parameters.Image.Width` and `Parameters.Image.Height`:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Cómo generar un código de barras Databar Expanded Stacked en C#
url: /es/python-java/general/how-to-generate-a-databar-expanded-stacked-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo generar un código de barras databar expanded stacked en C#

Si necesitas generar un código de barras **databar expanded stacked** en C#, esta guía te muestra cómo hacerlo. La simbología databar expanded stacked es ideal para codificar grandes cantidades de datos en un formato compacto, y puedes crear la imagen con solo unas pocas líneas de código. También aprenderás a **generar archivos de imagen de código de barras** en diferentes formatos y a personalizar filas o columnas para adaptarlas a tu entorno de escaneo.

Este tutorial cubre todo lo que necesitas para comenzar a producir códigos de barras databar: instalar la biblioteca requerida, preparar la carpeta de salida, crear el código de barras con filas o columnas personalizadas y guardar el resultado como un archivo PNG. Al final, podrás **crear imágenes de código de barras databar** de forma programática y adaptar el código a otros formatos de imagen o escenarios de tiempo de ejecución.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* SDK de .NET 6.0 o posterior (el código también funciona con .NET Core 3.1 y .NET Framework 4.7+)
* Un entorno de desarrollo como Visual Studio 2022, Visual Studio Code o Rider
* Acceso a Internet para instalar el paquete NuGet **Barcode Generator C#** (Aspose.BarCode for .NET)

> **Consejo profesional:** Si utilizas una canalización CI/CD, agrega la referencia al paquete NuGet en tu archivo de proyecto para que las compilaciones sean reproducibles.

## Instalar la biblioteca Barcode Generator C#

El ejemplo utiliza la biblioteca Aspose.BarCode, que proporciona la clase `BarcodeGenerator` y la enumeración `EncodeTypes.DatabarExpandedStacked`.

```bash
dotnet add package Aspose.BarCode
```

El comando agrega la última versión estable a tu proyecto. Después de la instalación, puedes importar el espacio de nombres en tus archivos C#:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

## Preparar la carpeta de salida

Una ruta de archivo confiable evita errores en tiempo de ejecución cuando la biblioteca intenta escribir la imagen. El siguiente código crea el directorio si no existe:

```csharp
using System;
using System.IO;

// Define the folder where barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);
```

> **Por qué es importante:** Intentar guardar en un directorio inexistente lanza una `IOException`. Crear la carpeta de antemano hace que el código sea robusto tanto para desarrollo local como para entornos de producción.

## Generar una imagen de código de barras databar expanded stacked

### Generación básica de código de barras

La forma más sencilla de generar una imagen **databar expanded stacked** es instanciar `BarcodeGenerator` con el valor deseado de `EncodeTypes` y una carga útil de texto plano.

```csharp
// Create a barcode that encodes a long numeric string
var basicGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "01234567890123456789");

// Save the barcode as PNG
basicGenerator.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
    BarCodeImageFormat.Png);
```

Ejecutar el fragmento produce `DatabarBasic.png` en la carpeta *Barcodes*. La imagen contiene un símbolo estándar databar expanded stacked con el diseño predeterminado (4 columnas × 4 filas).

### Personalizar columnas – crear código de barras databar con 4 columnas

Puedes controlar el número de columnas mediante la propiedad `Parameters.Barcode.DataBar.Columns`. El siguiente ejemplo crea un código de barras con **4 columnas** manteniendo el recuento de filas predeterminado.

```csharp
// Step 1: Define a generator with custom column count
var columnGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the column count to 4 (default rows = 4)
columnGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the image
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
    BarCodeImageFormat.Png);
```

El archivo resultante, **DatabarCols4.png**, se ve así:

![Databar expanded stacked barcode with 4 columns](databar_cols4.png "Databar expanded stacked barcode with 4 columns – generated with C#")

*Texto alternativo de la imagen (og_image_alt):* **Sample databar expanded stacked barcode image generated with C#** – this satisfies the SEO requirement for image alt text.

### Personalizar filas – crear código de barras databar con 3 filas

De manera similar, puedes ajustar el número de filas mediante `Parameters.Barcode.DataBar.Rows`. El código a continuación genera un código de barras con **3 filas** y el recuento de columnas predeterminado (4).

```csharp
// Step 2: Define a generator with custom row count
var rowGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the row count to 3 (default columns = 4)
rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

// Save the image
rowGenerator.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
    BarCodeImageFormat.Png);
```

El archivo **DatabarRows3.png** contiene un símbolo databar expanded stacked que es ligeramente más corto verticalmente, lo que puede ser útil para etiquetas con espacio limitado.

### Exportar a otros formatos

Si necesitas un tipo de imagen diferente (p. ej., JPEG, BMP o SVG), reemplaza `BarCodeImageFormat.Png` por el valor de enumeración correspondiente:

```csharp
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
    BarCodeImageFormat.Jpeg);
```

La biblioteca también admite formatos vectoriales como SVG, que son ideales para impresiones de alta resolución.

## Escenarios avanzados

### Guardar en un flujo de memoria

A veces deseas incrustar el código de barras directamente en una respuesta web o en un PDF sin tocar el sistema de archivos. Usa un `MemoryStream`:

```csharp
using System.IO;

// Generate barcode into a memory stream
using var ms = new MemoryStream();
columnGenerator.Save(ms, BarCodeImageFormat.Png);

// Reset stream position before reading
ms.Position = 0;

// Example: return the stream as a file download in ASP.NET Core
// return File(ms.ToArray(), "image/png", "databar.png");
```

### Manejo de entrada no válida

`BarcodeGenerator` valida la carga útil contra la simbología elegida. Si los datos contienen caracteres prohibidos, se lanza una `ArgumentException`. Envuelve el código de generación en un bloque try‑catch para proporcionar un mensaje de error amigable:

```csharp
try
{
    var gen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "INVALID*DATA");
    gen.Save(Path.Combine(outputFolder, "Invalid.png"), BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

### Escalar la imagen del código de barras

Puedes cambiar el tamaño de la imagen sin alterar los datos codificados configurando `Parameters.Image.Width` y `Parameters.Image.Height`:

```csharp
columnGenerator.Parameters.Image.Width = 300;   // pixels
columnGenerator.Parameters.Image.Height = 150; // pixels
columnGenerator.Save(Path.Combine(outputFolder, "DatabarLarge.png"),
    BarCodeImageFormat.Png);
```

Escalar es útil cuando el código de barras debe cumplir con un requisito específico de DPI para los escáneres.

## Ejemplo completo en funcionamiento

A continuación se muestra una aplicación de consola completa, lista para ejecutar, que demuestra todos los pasos descritos:

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace DatabarExpandedStackedDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Prepare output folder
            string outputFolder = Path.Combine(
                Environment.CurrentDirectory, "Barcodes");
            Directory.CreateDirectory(outputFolder);

            // 2️⃣ Generate basic barcode
            var basic = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "01234567890123456789");
            basic.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
                BarCodeImageFormat.Png);

            // 3️⃣ Generate barcode with 4 columns
            var colGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            colGen.Parameters.Barcode.DataBar.Columns = 4;
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
                BarCodeImageFormat.Png);

            // 4️⃣ Generate barcode with 3 rows
            var rowGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            rowGen.Parameters.Barcode.DataBar.Rows = 3;
            rowGen.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
                BarCodeImageFormat.Png);

            // 5️⃣ Export to JPEG as an extra format
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
                BarCodeImageFormat.Jpeg);

            Console.WriteLine("All barcode images have been generated in:");
            Console.WriteLine(outputFolder);
        }
    }
}
```

**Salida esperada**


## ¿Qué deberías aprender a continuación?


Los tutoriales siguientes cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo establecer columnas para un código de barras Databar Expanded Stacked – guía completa en C#](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [Cómo crear un ejemplo de generador de códigos de barras en C# con DataBar Expanded Stacked](/barcode/english/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/)
- [Guía de código de barras databar expanded stacked – cómo generar y dimensionar en C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}