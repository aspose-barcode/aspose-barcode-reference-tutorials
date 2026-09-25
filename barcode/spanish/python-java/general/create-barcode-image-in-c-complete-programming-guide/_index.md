---
category: general
date: 2026-08-09
description: Crea una imagen de código de barras en C# con esta guía paso a paso.
  Aprende a generar códigos de barras, ajustar la altura del código de barras en píxeles
  y crear múltiples códigos de barras de manera eficiente.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to generate barcode
- barcode generator c#
- create multiple barcodes
- barcode height pixels
language: es
lastmod: 2026-08-09
og_description: Crea una imagen de código de barras en C# rápidamente. Sigue este
  tutorial para aprender a generar códigos de barras, establecer la altura del código
  de barras en píxeles y producir múltiples códigos de barras.
og_image_alt: Screenshot of barcode images generated with C# code showing different
  heights
og_title: Crear imagen de código de barras en C# – guía completa para desarrolladores
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create barcode image in C# with this step-by-step guide. Learn how
    to generate barcode, adjust barcode height pixels, and create multiple barcodes
    efficiently.
  headline: Create barcode image in C# – complete programming guide
  type: TechArticle
- description: Create barcode image in C# with this step-by-step guide. Learn how
    to generate barcode, adjust barcode height pixels, and create multiple barcodes
    efficiently.
  name: Create barcode image in C# – complete programming guide
  steps:
  - name: Define the output folder
    text: Choose a folder where the generated PNG files will be stored. Using an absolute
      path avoids permission surprises.
  - name: Instantiate the barcode generator
    text: For a DataBar Omnidirectional barcode, pass `EncodeTypes.DatabarOmniDirectional`
      and the GS1‑128 data string.
  - name: Set common barcode parameters
    text: The most common visual tweaks are the X‑dimension (module width) and the
      bar height. Both are expressed in pixels.
  - name: Save the first barcode image
    text: '```csharp // Step 4: Save the barcode image with a 30 px height string
      file30 = Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"); barcode.Save(file30,
      BarCodeImageFormat.Png); ```'
  - name: Adjust the barcode height pixels
    text: Changing the height does not require a new `BarcodeGenerator` instance—just
      modify the parameter.
  - name: Save the second barcode image
    text: '```csharp // Step 6: Save the barcode image with the new 60 px height string
      file60 = Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"); barcode.Save(file60,
      BarCodeImageFormat.Png); ```'
  - name: Expected output
    text: 'After running the full sample, the `Barcodes` folder contains:'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Crear imagen de código de barras en C# – guía completa de programación
url: /es/python-java/general/create-barcode-image-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear imagen de código de barras en C# – guía completa de programación

Si necesitas **crear una imagen de código de barras** en una aplicación .NET, esta guía te muestra exactamente **cómo generar códigos de barras** usando la biblioteca Aspose.BarCode. Verás cómo controlar los **píxeles de altura del código de barras**, guardar la imagen y producir **múltiples códigos de barras** sin duplicar código.

El tutorial cubre todo, desde la instalación del paquete hasta la personalización de dimensiones, para que puedas copiar‑pegar un ejemplo listo para ejecutar en tu proyecto hoy mismo.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* SDK .NET 6.0 o posterior instalado  
* Visual Studio 2022 (o cualquier IDE de C#)  
* Paquete NuGet `Aspose.BarCode` – instalar con  

```bash
dotnet add package Aspose.BarCode
```

No se requieren dependencias adicionales.

## Cómo generar una imagen de código de barras con BarcodeGenerator C#

La clase principal para crear una imagen de código de barras es `BarcodeGenerator`. Encapsula el tipo de codificación, la cadena de datos y todos los parámetros de renderizado.

### Paso 1: Definir la carpeta de salida

Elige una carpeta donde se almacenarán los archivos PNG generados. Usar una ruta absoluta evita sorpresas de permisos.

```csharp
// Step 1: Define the output folder
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputFolder);
```

> **¿Por qué?** Crear la carpeta programáticamente garantiza que las llamadas posteriores a `Save` tengan éxito incluso en una máquina nueva.

### Paso 2: Instanciar el generador de códigos de barras

Para un código de barras DataBar Omnidirectional, pasa `EncodeTypes.DatabarOmniDirectional` y la cadena de datos GS1‑128.

```csharp
// Step 2: Create a DataBar Omnidirectional barcode generator with the data to encode
var barcode = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

> **Nota:** El objeto `BarcodeGenerator` es reutilizable; puedes cambiar sus parámetros entre guardados para **crear múltiples códigos de barras** a partir de los mismos datos.

### Paso 3: Establecer los parámetros comunes del código de barras

Los ajustes visuales más comunes son la X‑dimension (ancho del módulo) y la altura de la barra. Ambos se expresan en píxeles.

```csharp
// Step 3: Set common barcode parameters (X‑dimension and initial height)
barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin modules for sharper output
barcode.Parameters.Barcode.BarHeight.Pixels = 30;  // initial height – 30 px
```

> **¿Por qué establecer la X‑dimension?** Una X‑dimension más pequeña produce mayor resolución, lo cual es importante cuando la imagen se imprimirá o mostrará en pantallas de alta DPI.

### Paso 4: Guardar la primera imagen de código de barras

```csharp
// Step 4: Save the barcode image with a 30 px height
string file30 = Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png");
barcode.Save(file30, BarCodeImageFormat.Png);
```

El archivo `DatabarBarHeight30Pixels.png` ahora contiene un código de barras DataBar Omnidirectional de 30 píxeles de altura.

### Paso 5: Ajustar los píxeles de altura del código de barras

Cambiar la altura no requiere una nueva instancia de `BarcodeGenerator`, solo modifica el parámetro.

```csharp
// Step 5: Change the bar height to 60 px for the same barcode
barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

### Paso 6: Guardar la segunda imagen de código de barras

```csharp
// Step 6: Save the barcode image with the new 60 px height
string file60 = Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png");
barcode.Save(file60, BarCodeImageFormat.Png);
```

Ahora tienes dos archivos PNG con diferentes **píxeles de altura del código de barras**, demostrando lo fácil que es crear variaciones de **imagen de código de barras**.

## Configurar dinámicamente los píxeles de altura del código de barras

A menudo necesitas una serie de códigos de barras con alturas que coincidan con elementos de UI o etiquetas impresas. El siguiente método auxiliar abstrae el cambio de altura:

```csharp
/// <summary>
/// Saves a barcode image with a custom height.
/// </summary>
/// <param name="generator">Configured BarcodeGenerator instance.</param>
/// <param name="heightPx">Desired bar height in pixels.</param>
/// <param name="fileName">Target file name (including path).</param>
void SaveBarcodeWithHeight(BarcodeGenerator generator, int heightPx, string fileName)
{
    generator.Parameters.Barcode.BarHeight.Pixels = heightPx;
    generator.Save(fileName, BarCodeImageFormat.Png);
}
```

Ahora puedes llamar a `SaveBarcodeWithHeight(barcode, 45, "BarHeight45.png");` para **crear una imagen de código de barras** con una altura de 45 píxeles en una sola línea.

## Crear múltiples códigos de barras en un bucle

Cuando tienes una colección de identificadores de producto, un bucle `foreach` elimina el código repetitivo. Este ejemplo muestra cómo **crear múltiples códigos de barras** a partir de un arreglo de GTINs.

```csharp
string[] gtins = { "01234567890123", "09876543210987", "12345098765432" };
int[] heights = { 30, 45, 60 }; // different heights for visual variety

for (int i = 0; i < gtins.Length; i++)
{
    // Encode each GTIN as a DataBar Omnidirectional barcode
    var gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional,
                                   $"(01){gtins[i]}");

    // Reuse the X‑dimension setting for consistency
    gen.Parameters.Barcode.XDimension.Pixels = 2;

    // Choose a height from the heights array (or calculate dynamically)
    int height = heights[i % heights.Length];
    string filePath = Path.Combine(outputFolder,
        $"Databar_{gtins[i]}_Height{height}px.png");

    SaveBarcodeWithHeight(gen, height, filePath);
}
```

El bucle produce tres archivos PNG, cada uno con un valor distinto de **píxeles de altura del código de barras**. Como el método auxiliar `SaveBarcodeWithHeight` encapsula el cambio de altura, el bucle principal se mantiene limpio y centrado en los datos.

### Resultado esperado

Después de ejecutar el ejemplo completo, la carpeta `Barcodes` contiene:

```
DatabarBarHeight30Pixels.png
DatabarBarHeight60Pixels.png
Databar_01234567890123_Height30px.png
Databar_09876543210987_Height45px.png
Databar_12345098765432_Height60px.png
```

Abrir cualquier PNG muestra un código de barras DataBar Omnidirectional nítido que puede ser escaneado por aplicaciones móviles estándar.

## Errores comunes y consejos profesionales

| Problema | Por qué ocurre | Cómo evitarlo |
|----------|----------------|---------------|
| **EncodeTypes incorrectos** | Usar un tipo 1D para un DataBar producirá una imagen ilegible. | Siempre elige `EncodeTypes.DatabarOmniDirectional` (u otra variante DataBar) para cargas útiles GS1‑128. |
| **X‑dimension insuficiente** | Una X‑dimension muy baja puede hacer que las barras finas desaparezcan en monitores de baja resolución. | Mantén `XDimension.Pixels` ≥ 2 para visualización en pantalla; aumenta a 3‑4 para impresión. |
| **Errores de ruta de archivo** | Las rutas relativas pueden resolverse a directorios inesperados. | Usa `Path.Combine` y `Environment.CurrentDirectory` para construir rutas absolutas. |
| **Sobrescritura de imágenes** | Reutilizar el mismo nombre de archivo en un bucle sobrescribe resultados anteriores. | Incluye identificadores únicos (p. ej., GTIN o marca de tiempo) en el nombre del archivo. |
| **Paquete NuGet faltante** | El código compila pero lanza `FileNotFoundException` en tiempo de ejecución. | Verifica que `Aspose.BarCode` esté instalado y que el proyecto lo referencie. |

## Ejemplo completo en funcionamiento

A continuación se muestra el programa completo que puedes copiar en una aplicación de consola. Incluye todos los pasos, métodos auxiliares y manejo de errores.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Prepare output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // ---------- Single barcode with two heights ----------
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        barcode.Parameters.Barcode.XDimension.Pixels = 2;
        barcode.Parameters.Barcode.BarHeight.Pixels = 30;
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);

        barcode.Parameters.Barcode.BarHeight.Pixels = 60;
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);

        // ---------- Helper for dynamic heights ----------
        void SaveBarcodeWithHeight(BarcodeGenerator gen, int heightPx, string fileName)
        {
            gen.Parameters.Barcode.BarHeight.Pixels = heightPx;
            gen.Save(fileName, BarCodeImageFormat.Png);
        }

        // ---------- Multiple barcodes ----------
        string[] gtins = { "01234567890123", "09876543210987", "12345098765432" };
        int[] heights = { 30, 45, 60 };

        for (int i = 0; i < gtins.Length; i++)
        {
            var gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional,
                                           $"(01){gtins[i]}");
            gen.Parameters.Barcode.XDimension.Pixels = 2;

            int height = heights[i % heights.Length];
            string filePath = Path.Combine(outputFolder,
                $"Databar_{gtins[i]}_Height{height}px.png");

            SaveBarcodeWithHeight(gen, height, filePath);
        }

        Console.WriteLine($"Barcode images created in: {outputFolder}");
    }
}
```

Ejecutando este programa


## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Crear código de barras con altura personalizada – Códigos de barras unidimensionales](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [Crear imagen de código de barras C# – Ejemplo GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Crear imagen de código de barras DotCode – filas y columnas (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}