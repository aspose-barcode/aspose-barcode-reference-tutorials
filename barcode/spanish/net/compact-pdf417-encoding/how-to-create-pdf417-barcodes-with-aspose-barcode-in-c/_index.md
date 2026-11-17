---
category: general
date: 2026-11-17
description: Cómo crear códigos de barras PDF417 usando Aspose.BarCode – guía paso
  a paso que también muestra cómo crear códigos de barras Aspose en C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to create pdf417
- create barcode aspose
language: es
lastmod: 2026-11-17
og_description: Cómo crear códigos de barras PDF417 usando Aspose.BarCode. Este tutorial
  le guía paso a paso para crear códigos de barras Aspose, configurar los metadatos
  Macro PDF417 y guardar la imagen.
og_image_alt: Screenshot of a PDF417 barcode generated with Aspose.BarCode in C#
og_title: Cómo crear códigos de barras PDF417 con Aspose.BarCode – guía completa en
  C#
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: How to create PDF417 barcodes using Aspose.BarCode – step‑by‑step guide
    that also shows how to create barcode aspose in C#.
  headline: How to create PDF417 barcodes with Aspose.BarCode in C#
  type: TechArticle
- description: How to create PDF417 barcodes using Aspose.BarCode – step‑by‑step guide
    that also shows how to create barcode aspose in C#.
  name: How to create PDF417 barcodes with Aspose.BarCode in C#
  steps:
  - name: Set up the project and import Aspose.BarCode
    text: 'Create a new console project and add the Aspose.BarCode NuGet package:'
  - name: Initialise the `BarcodeGenerator` for Macro PDF417
    text: The `BarcodeGenerator` constructor takes the barcode type and the text you
      want to encode. For Macro PDF417 you use `EncodeTypes.MacroPdf417`.
  - name: Configure appearance and Macro PDF417 metadata
    text: Configure appearance and Macro PDF417 metadata
  - name: Save the barcode image
    text: '```csharp // Choose the output folder (ensure it exists) and save as PNG.
      string outputPath = "MacroPdf417.png"; generator.Save(outputPath, BarCodeImageFormat.Png);
      Console.WriteLine($"PDF417 barcode saved to {outputPath}"); } ```'
  - name: Full, runnable example
    text: 'Putting everything together, here’s the complete program you can compile
      and run immediately:'
  type: HowTo
tags:
- barcode
- pdf417
- aspose
- csharp
title: Cómo crear códigos de barras PDF417 con Aspose.BarCode en C#
url: /es/net/compact-pdf417-encoding/how-to-create-pdf417-barcodes-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear códigos de barras PDF417 con Aspose.BarCode en C#

Si necesitas **cómo crear PDF417** códigos de barras para inventario, envío o seguimiento de documentos, esta guía te muestra los pasos exactos con Aspose.BarCode. Verás cómo crear barcode aspose, configurar los campos Macro PDF417 y exportar el resultado como una imagen PNG, todo en un único programa C# ejecutable.

Crear un código de barras PDF417 es común cuando debes codificar grandes cantidades de datos en un formato compacto y legible por máquinas. Aspose.BarCode hace que el proceso sea sencillo, permitiéndote ajustar finamente dimensiones, columnas y el conjunto completo de metadatos Macro PDF417. Al final de este tutorial tendrás un ejemplo completo y autocontenido que podrás incorporar en cualquier proyecto .NET.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* .NET 6.0 SDK o posterior (el código también funciona con .NET Framework 4.7+).
* Una licencia válida de Aspose.BarCode para .NET (la evaluación gratuita funciona para pruebas).
* Visual Studio 2022, VS Code o cualquier IDE compatible con C#.
* Familiaridad básica con la sintaxis de C# y la instrucción `using`.

> **Consejo profesional:** Si ejecutas el ejemplo sin una licencia, Aspose añadirá una pequeña marca de agua a la imagen generada.

## Cómo crear un código de barras PDF417 con Aspose.BarCode

Las siguientes secciones dividen la implementación en cuatro pasos claros. Cada paso incluye un fragmento de código, una explicación de **por qué** el código es necesario y consejos prácticos que puedes aplicar a tus propios proyectos.

### Paso 1: Configurar el proyecto e importar Aspose.BarCode

Crea un nuevo proyecto de consola y agrega el paquete NuGet Aspose.BarCode:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Luego abre `Program.cs` y agrega los espacios de nombres requeridos:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

*Por qué es importante:* Importar `Aspose.BarCode.Generation` te da acceso a `BarcodeGenerator` y a la enumeración `EncodeTypes`, que son las clases centrales para la creación de códigos de barras.

### Paso 2: Inicializar el `BarcodeGenerator` para Macro PDF417

El constructor de `BarcodeGenerator` recibe el tipo de código de barras y el texto que deseas codificar. Para Macro PDF417 utilizas `EncodeTypes.MacroPdf417`.

```csharp
// Initialise a Macro PDF417 generator with the data you want to encode.
using (BarcodeGenerator generator = 
       new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text for PDF417"))
{
    // The generator instance will be disposed automatically at the end of the block.
```

*Por qué es importante:* La instrucción `using` garantiza que los recursos no administrados (como los manejadores GDI+) se liberen rápidamente, evitando fugas de memoria en servicios de larga ejecución.

### Paso 3: Configurar la apariencia y los metadatos Macro PDF417

#### 3.1 Ajustar parámetros visuales

```csharp
    // Set the module (X) dimension – 2 pixels gives a reasonably dense barcode.
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Define the number of columns; fewer columns make the barcode taller.
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

#### 3.2 Rellenar los campos Macro PDF417

Macro PDF417 te permite dividir un documento grande en varios segmentos de código de barras. Los campos a continuación son opcionales pero a menudo requeridos para sistemas de logística o gestión documental.

```csharp
    // Unique identifier for the whole file (must be the same across all segments).
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Segment index (starting at 1). Here we generate the 12th segment.
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that will be produced.
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Human‑readable file name, useful for audits.
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // CCITT‑16 checksum – helps receivers verify data integrity.
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate file size in bytes; some scanners use this for validation.
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;

    // Timestamp of the original file creation.
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2024, 5, 1);

    // Optional address fields that can be read by advanced scanners.
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator tells the scanner that this is the last segment.
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;
```

*Por qué son útiles estos campos:*  
* **FileID** une todos los segmentos, permitiendo la reconstrucción.  
* **SegmentID** y **SegmentsCount** indican al escáner el orden y cuándo la serie está completa.  
* **Checksum** y **FileSize** proporcionan verificaciones rápidas de integridad sin decodificar toda la carga útil.

> **Cuidado:** El `MacroPdf417FileID` debe ser único por documento lógico. Reutilizar el mismo ID para archivos no relacionados puede causar errores de reconstrucción.

### Paso 4: Guardar la imagen del código de barras

```csharp
    // Choose the output folder (ensure it exists) and save as PNG.
    string outputPath = "MacroPdf417.png";
    generator.Save(outputPath, BarCodeImageFormat.Png);
    Console.WriteLine($"PDF417 barcode saved to {outputPath}");
}
```

*¿Por qué PNG?* PNG conserva los datos de píxeles exactos sin artefactos de compresión, lo que es ideal para escáneres de códigos de barras que dependen de bordes nítidos.

### Ejemplo completo y ejecutable

Juntando todo, aquí tienes el programa completo que puedes compilar y ejecutar de inmediato:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1‑4: generate a Macro PDF417 barcode and save it as PNG
            using (BarcodeGenerator generator = 
                   new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text for PDF417"))
            {
                // Appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // Macro PDF417 metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
                    new DateTime(2024, 5, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
                    Pdf417MacroTerminator.Set;

                // Save
                string outputPath = "MacroPdf417.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"PDF417 barcode saved to {outputPath}");
            }
        }
    }
}
```

**Salida esperada:** Después de ejecutar el programa, encontrarás `MacroPdf417.png` en la carpeta del proyecto. Al abrir la imagen verás un denso código de barras PDF417 de alto contraste que codifica “Sample text for PDF417” junto con los metadatos macro que proporcionaste.

## Preguntas comunes y manejo de casos límite

| Pregunta | Respuesta |
|----------|-----------|
| *¿Puedo generar múltiples segmentos en un bucle?* | Sí. Incrementa `MacroPdf417SegmentID` en cada iteración, mantén `MacroPdf417FileID` constante y actualiza `MacroPdf417SegmentsCount` solo después de conocer el número total de segmentos. |
| *¿Qué pasa si los datos superan un solo símbolo PDF417?* | Macro |

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo crear un código de barras macro PDF417 en C# usando Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Cómo crear un código de barras micro PDF417 en C# usando Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c/)
- [Cómo crear un código de barras – PDF417 compacto con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}