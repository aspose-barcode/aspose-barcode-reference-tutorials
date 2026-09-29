---
category: general
date: 2026-08-03
description: Crea códigos de barras PDF417 en C# rápidamente. Aprende cómo generar
  un código de barras PDF417 y cómo guardar la imagen del código de barras como PNG
  con Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417 barcode
- how to save barcode image
language: es
lastmod: 2026-08-03
og_description: Crea un código de barras PDF417 en C# con Aspose.Barcode. Sigue esta
  guía para generar un código de barras PDF417 y aprender cómo guardar la imagen del
  código de barras de manera eficiente.
og_image_alt: Screenshot of a generated compact PDF417 barcode saved as PNG
og_title: Crear código de barras PDF417 en C# – tutorial completo de programación
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  headline: Create PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  name: Create PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: Why this matters
    text: '* **EncodeTypes.Pdf417** tells the library to use the PDF417 standard,
      which supports large data payloads and error correction. * Providing Unicode
      characters proves the generator handles non‑ASCII input without extra configuration.'
  - name: Practical tip
    text: If you need a taller barcode for limited horizontal space, increase `Columns`.
      Setting `Truncate` to `true` reduces the overall height by removing quiet zones,
      which is ideal for mobile screens.
  - name: Expected result
    text: Running the program creates `CompactPdf417.png` in the project folder. Opening
      the file shows a compact PDF417 barcode that encodes the string *Åspóse.Barcóde©*.
      The image can be embedded in HTML, PDF reports, or printed on labels.
  - name: Verifying the output
    text: 'After the program finishes, you can verify the file exists with a quick
      command:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: Crear código de barras PDF417 en C# – guía paso a paso
url: /es/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear código de barras PDF417 en C# – guía paso a paso

Si necesitas **crear código de barras PDF417** en una aplicación .NET, esta guía te muestra exactamente cómo generar un código de barras PDF417 y cómo guardar la imagen del código de barras. Obtendrás un archivo PNG que puede usarse en informes, tickets o aplicaciones móviles de escaneo.

El tutorial cubre todo, desde la configuración del proyecto hasta el archivo PNG final. No se requiere documentación externa; simplemente sigue los pasos y ejecuta el código.

## Lo que necesitarás

* SDK de .NET 6.0 o posterior (el código también funciona con .NET Framework 4.7+)
* Visual Studio 2022 o cualquier IDE que soporte C#
* Acceso a Internet para instalar el paquete NuGet **Aspose.Barcode for .NET**

Estos requisitos previos garantizan que el código se compile sin configuración adicional.

## Crear código de barras PDF417 – configuración del proyecto

1. Abre una línea de comandos y crea un nuevo proyecto de consola:

   ```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

2. Añade la biblioteca Aspose.Barcode:

   ```bash
   dotnet add package Aspose.Barcode
   ```

3. Abre el archivo `Program.cs` generado. Las sentencias `using` al inicio te dan acceso a las clases de códigos de barras:

   ```csharp
   using System;
   using Aspose.Barcode.Generation;
   using Aspose.Barcode;
   ```

El proyecto está ahora listo para **crear código de barras PDF417**.

## Cómo generar código de barras PDF417 con Aspose.Barcode

El núcleo de la creación del código de barras reside en la clase `BarcodeGenerator`. Especificas la simbología (`EncodeTypes.Pdf417`) y los datos que deseas codificar.

```csharp
// Step 1: Initialise the generator with PDF417 symbology and sample text.
// The text includes Unicode characters to demonstrate full‑range support.
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

### Por qué es importante

* **EncodeTypes.Pdf417** indica a la biblioteca que use el estándar PDF417, que soporta grandes cargas de datos y corrección de errores.
* Proveer caracteres Unicode demuestra que el generador maneja entradas no ASCII sin configuración adicional.

## Cómo configurar la apariencia del código de barras

Puedes controlar el tamaño de cada módulo, el número de columnas y si el código de barras usa modo compacto (truncado). Estas configuraciones afectan tanto la legibilidad como el tamaño del archivo.

```csharp
// Step 2: Set the module (X) dimension – each barcode element will be 2 pixels wide.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Configure PDF417‑specific options.
generator.Parameters.Barcode.Pdf417.Columns = 3;      // Number of columns (affects height)
generator.Parameters.Barcode.Pdf417.Truncate = true; // Enable compact mode
```

### Consejo práctico

Si necesitas un código de barras más alto para espacio horizontal limitado, aumenta `Columns`. Configurar `Truncate` a `true` reduce la altura total al eliminar las zonas silenciosas, lo cual es ideal para pantallas móviles.

## Cómo guardar la imagen del código de barras como PNG

Después de configurar el generador, llama a `Save` con una ruta de archivo y el formato de imagen deseado. El método escribe la imagen directamente en el disco.

```csharp
// Step 4: Save the generated barcode as a PNG image.
string outputPath = @"./CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

### Resultado esperado

Ejecutar el programa crea `CompactPdf417.png` en la carpeta del proyecto. Al abrir el archivo se muestra un código de barras PDF417 compacto que codifica la cadena *Åspóse.Barcóde©*. La imagen puede incrustarse en HTML, informes PDF o imprimirse en etiquetas.

## Código fuente completo

A continuación se muestra el programa completo y ejecutable. Cópialo en `Program.cs` y ejecuta `dotnet run`.

```csharp
using System;
using Aspose.Barcode.Generation;
using Aspose.Barcode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with PDF417 symbology and sample text.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Åspóse.Barcóde©");

            // Set the module width to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Configure PDF417‑specific options.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Define the output file path.
            string outputPath = @"./CompactPdf417.png";

            // Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Verificando la salida

Después de que el programa termine, puedes verificar que el archivo existe con un comando rápido:

```bash
dotnet run && ls -l CompactPdf417.png
```

Si el archivo aparece, el proceso de **crear código de barras PDF417** se completó con éxito.

## Variaciones comunes y casos límite

| Situación | Ajuste |
|-----------|--------|
| **Cadena de datos más larga** | Aumenta `Columns` o establece `Rows` para acomodar más codewords. |
| **Formato de imagen diferente** | Reemplaza `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` o `Gif`. |
| **Resolución más alta** | Establece `generator.Parameters.ImageResolution` antes de `Save`. |
| **Color de fondo** | Usa `generator.Parameters.Barcode.ImageBackgroundColor = Color.White;` |
| **Manejo de excepciones** | Envuelve `generator.Save` en un bloque `try/catch` para capturar errores de E/S. |

## Conclusión

Ahora sabes cómo **crear código de barras PDF417** en C# usando Aspose.Barcode, configurar su apariencia y **guardar la imagen del código de barras** como archivo PNG. El ejemplo completo muestra cada paso necesario, desde la configuración del proyecto hasta la verificación, para que puedas integrar la generación de códigos de barras en cualquier solución .NET.

A continuación, considera explorar temas relacionados como **cómo generar códigos QR**, **incrustar códigos de barras en documentos PDF**, o **personalizar colores de códigos de barras**. Cada uno de estos se basa en la misma API del generador, lo que te permite ampliar las capacidades de escaneo de tu aplicación con un esfuerzo mínimo. ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo crear código de barras – PDF417 compacto con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cómo generar códigos de barras DataMatrix (ECC 200) con Aspose.BarCode para .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Cómo generar código de barras Aztec con relación de aspecto personalizada usando Aspose.BarCode para .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}