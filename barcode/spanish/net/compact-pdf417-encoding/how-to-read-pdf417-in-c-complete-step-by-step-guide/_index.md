---
category: general
date: 2026-07-15
description: Cómo leer códigos de barras PDF417 en C# y leer varios códigos de barras
  de una imagen. Aprende a leer imágenes de códigos de barras en C# con código detallado
  y consejos.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcode image c#
- Aspose.BarCode PDF417
- C# barcode decoding
language: es
lastmod: 2026-07-15
og_description: Cómo leer códigos de barras PDF417 en C# rápidamente. Esta guía te
  muestra cómo leer varios códigos de barras de una sola imagen y decodificar cada
  propiedad.
og_image_alt: Screenshot of C# console output displaying PDF417 barcode details
og_title: Cómo leer PDF417 en C# – Ejemplo de código completo y explicación
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: How to read PDF417 barcode in C# and read multiple barcodes from an
    image. Learn to read barcode image C# with detailed code and tips.
  headline: How to Read PDF417 in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: How to read PDF417 barcode in C# and read multiple barcodes from an
    image. Learn to read barcode image C# with detailed code and tips.
  name: How to Read PDF417 in C# – Complete Step‑by‑Step Guide
  steps:
  - name: Why This Code Works
    text: '* **`BarCodeReader`** is the core class that streams the image, detects
      barcodes, and returns a collection of `BarCodeResult` objects. * Passing **`DecodeType.MacroPdf417`**
      tells the library to treat Macro‑PDF417 specially; it still returns plain PDF417
      symbols, which satisfies the **read multiple '
  - name: What if the image has both Macro‑PDF417 and regular PDF417 symbols?
    text: The same `BarCodeReader` call will return both. You can differentiate them
      by checking `result.CodeType` (`MacroPdf417` vs `Pdf417`). The extended properties
      will be `null` for a plain PDF417, so the `if (macro != null)` guard prevents
      a `NullReferenceException`.
  - name: My barcode is rotated or skewed—will the reader still work?
    text: Aspose.BarCode includes built‑in rotation and distortion compensation. As
      long as the barcode is at least 30 % of the image width, the decoder will usually
      succeed. For extreme cases you can enable `reader.Options.AllowInvertedBarcodes
      = true;` before calling `ReadBarCodes()`.
  - name: How do I handle large batches of images?
    text: Wrap the reading logic in a `foreach (var file in Directory.GetFiles(folder,
      "*.png"))` loop. The `using` pattern ensures each image’s native resources are
      freed before the next iteration, keeping memory usage low.
  type: HowTo
tags:
- C#
- barcode
- PDF417
- Aspose
title: Cómo leer PDF417 en C# – Guía completa paso a paso
url: /es/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo leer PDF417 en C# – Guía completa paso a paso

¿Alguna vez te has preguntado **cómo leer PDF417** de una imagen usando C#? No eres el único. La mayoría de los desarrolladores se topan con un obstáculo cuando necesitan extraer los campos extendidos Macro‑PDF417 de un documento escaneado. ¿La buena noticia? Con solo unas pocas líneas de código puedes decodificar un PDF417, leer varios códigos de barras en la misma imagen y obtener todas las propiedades ocultas que la especificación ofrece.

En este tutorial recorreremos un ejemplo del mundo real que muestra **cómo leer PDF417**, cómo **leer varios códigos de barras** de un solo archivo, y por qué el código **read barcode image C#** tiene esa forma. Al final tendrás una aplicación de consola lista para ejecutar que imprime cada pieza de información que puedas necesitar: ID de archivo, ID de segmento, checksum, marcas de tiempo, lo que sea.

## Prerrequisitos

Antes de sumergirnos, asegúrate de contar con:

* .NET 6.0 SDK o posterior (el código funciona también con .NET Core y .NET Framework).  
* Visual Studio 2022 (o cualquier editor que prefieras).  
* El paquete NuGet **Aspose.BarCode for .NET** – es la biblioteca que realmente analiza PDF417.  
* Una imagen de muestra que contenga un código de barras Macro‑PDF417 (por ejemplo `ExtPDF417Meta.png`).  

No se requiere configuración adicional; la biblioteca incluye todos los decodificadores que necesitas.

## Paso 1: Instalar Aspose.BarCode

Abre la carpeta de tu proyecto en una terminal y ejecuta:

```bash
dotnet add package Aspose.BarCode
```

Ese comando descarga la última versión estable (a julio 2026 es la 23.12). Si prefieres la consola del Administrador de paquetes dentro de Visual Studio, usa:

```powershell
Install-Package Aspose.BarCode
```

> **Consejo profesional:** bloquea la versión (`23.12.0`) en tu `.csproj` para evitar cambios incompatibles accidentales más adelante.

## Paso 2: Crear la estructura básica de una aplicación de consola

Crea un nuevo proyecto de consola si aún no tienes uno:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Reemplaza el `Program.cs` autogenerado con el código que aparece a continuación. Explicaremos cada bloque en las siguientes secciones.

## Paso 3: Escribir el código completo “Cómo leer PDF417”

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Set the path to the image that contains one or more PDF417 codes
            // -----------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarCodeReader for MacroPdf417 decoding
            // -----------------------------------------------------------------
            // The DecodeType flag tells Aspose to look specifically for Macro‑PDF417,
            // but it will also pick up plain PDF417 symbols that happen to be in the
            // same image – perfect for the “read multiple barcodes” scenario.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // -----------------------------------------------------------------
                // 3️⃣  Iterate over every barcode found in the image
                // -----------------------------------------------------------------
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // -------------------------------------------------------------
                    // 4️⃣  Basic barcode information – works for any barcode type
                    // -------------------------------------------------------------
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // -------------------------------------------------------------
                    // 5️⃣  Macro‑PDF417 extended properties (the real reason you’re here)
                    // -------------------------------------------------------------
                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40)); // visual separator
                }
            }

            // -----------------------------------------------------------------
            // 6️⃣  Keep the console window open when running from VS
            // -----------------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

### Por qué este código funciona

* **`BarCodeReader`** es la clase central que procesa la imagen, detecta los códigos de barras y devuelve una colección de objetos `BarCodeResult`.  
* Pasar **`DecodeType.MacroPdf417`** indica a la biblioteca que trate Macro‑PDF417 de forma especial; sigue devolviendo símbolos PDF417 simples, lo que satisface el requisito de **read multiple barcodes**.  
* El objeto **`Extended.Pdf417.MacroPdf417`** contiene todos los campos opcionales definidos por la norma ISO/IEC 15438 – ahí obtienes `FileID`, `SegmentID`, `Checksum`, etc.  
* El bloque `using` garantiza que los recursos nativos se liberen, evitando fugas de memoria en servicios de larga ejecución.

## Paso 4: Ejecutar la aplicación y verificar la salida

Desde la terminal:

```bash
dotnet run
```

Deberías ver algo como:

```
Code Type : MacroPdf417
Code Text : 1234567890...
File ID          : 12
Segment ID       : 1
Segments Count   : 3
File Name        : invoice2024.pdf
Checksum         : 9A3F
File Size        : 245760
Time Stamp       : 2024-11-02T14:23:00Z
Addressee        : Acme Corp
Sender           : Logistics Dept
Terminator       : 1
----------------------------------------
Done. Press any key to exit...
```

Si la imagen contiene más de un código de barras, el bucle imprimirá una línea separadora (`----------------------------------------`) y continuará con el siguiente resultado—exactamente lo que representa **read multiple barcodes** en la práctica.

## Preguntas frecuentes y casos límite

### ¿Qué pasa si la imagen tiene símbolos Macro‑PDF417 y PDF417 normales?

La misma llamada a `BarCodeReader` devolverá ambos. Puedes diferenciarlos comprobando `result.CodeType` (`MacroPdf417` vs `Pdf417`). Las propiedades extendidas serán `null` para un PDF417 simple, por lo que la condición `if (macro != null)` evita una `NullReferenceException`.

### ¿Mi código de barras está rotado o sesgado—seguirá funcionando el lector?

Aspose.BarCode incluye compensación integrada de rotación y distorsión. Mientras el código de barras ocupe al menos el 30 % del ancho de la imagen, el decodificador suele tener éxito. En casos extremos puedes habilitar `reader.Options.AllowInvertedBarcodes = true;` antes de llamar a `ReadBarCodes()`.

### ¿Cómo manejo lotes grandes de imágenes?

Envuelve la lógica de lectura en un bucle `foreach (var file in Directory.GetFiles(folder, "*.png"))`. El patrón `using` asegura que los recursos nativos de cada imagen se liberen antes de la siguiente iteración, manteniendo bajo el consumo de memoria.

## Listado completo del código (listo para copiar y pegar)

A continuación tienes todo el programa en un solo bloque para copiar y pegar rápidamente. No hay dependencias ocultas—solo el paquete NuGet Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

## Resumen – Lo que cubrimos

* **Cómo leer PDF417** usando Aspose.BarCode en C#.  
* Los pasos exactos para **read multiple barcodes** desde una sola imagen.  
* Cómo **read barcode image C#** y extraer cada campo Macro‑PDF417.  
* Consejos para rotación, procesamiento por lotes y manejo de datos extendidos ausentes.

## Próximos pasos y temas relacionados

* **Encode PDF417** – genera tus propios códigos de barras Macro‑PDF417 con `BarCodeBuilder`.  
* **Read other 2‑D symbologies** – QR, DataMatrix, Aztec – usando la misma clase `BarCodeReader`.  
* **Integrate with ASP.NET Core** – expón un endpoint web que acepte una imagen subida y devuelva JSON con los campos decodificados.  

Siéntete libre de experimentar: cambia la ruta de la imagen, coloca un PDF417 simple en la misma carpeta, o ajusta las banderas `DecodeType` para ver cómo se comporta la biblioteca. Cuanto más juegues, más cómodo te sentirás con los escenarios **read barcode image C#**.

¿Tienes una imagen complicada que se niega a decodificar? Deja un comentario abajo o abre un issue en el repositorio GitHub del proyecto de ejemplo. ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Read DataMatrix barcode C# – Generate DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}