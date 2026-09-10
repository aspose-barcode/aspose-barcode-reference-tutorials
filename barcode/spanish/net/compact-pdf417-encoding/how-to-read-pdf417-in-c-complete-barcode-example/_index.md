---
category: general
date: 2026-07-27
description: Cómo leer códigos de barras PDF417 en C# rápidamente. Aprende a leer
  varios códigos de barras, decodificar imágenes y obtener los metadatos Macro PDF417
  en un ejemplo completo de código de barras en C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- c# barcode example
- read barcode image c#
language: es
lastmod: 2026-07-27
og_description: Cómo leer códigos de barras PDF417 en C# con esta guía paso a paso.
  Decodifica imágenes, maneja múltiples códigos de barras y extrae los metadatos Macro
  PDF417 en un ejemplo listo para ejecutar.
og_image_alt: Screenshot showing how to read PDF417 barcode using C# code
og_title: Cómo leer PDF417 en C# – Ejemplo completo de código de barras
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  headline: How to Read PDF417 in C# – Complete Barcode Example
  type: TechArticle
- description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  name: How to Read PDF417 in C# – Complete Barcode Example
  steps:
  - name: Loads a barcode image from disk.
    text: Loads a barcode image from disk.
  - name: Decodes **PDF417** (including Macro PDF417) barcodes.
    text: Decodes **PDF417** (including Macro PDF417) barcodes.
  - name: Prints basic information such as code type and text.
    text: Prints basic information such as code type and text.
  - name: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
    text: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image-processing
- Aspose
title: Cómo leer PDF417 en C# – Ejemplo completo de código de barras
url: /es/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo leer PDF417 en C# – Ejemplo completo de código de barras

¿Alguna vez te has preguntado **cómo leer códigos de barras PDF417** en una aplicación C# sin volverte loco? No eres el único. Ya sea que estés construyendo un escáner logístico, un validador de tickets, o simplemente necesites extraer datos de una identificación codificada en PDF417, el proceso puede parecer un poco misterioso al principio.  

En este tutorial recorreremos un **ejemplo de código de barras c#** que lee una imagen PDF417, maneja **leer múltiples códigos de barras** si están presentes, y extrae todos los útiles metadatos Macro PDF417 que puedas necesitar.

## Lo que construirás

Al final de esta guía tendrás un pequeño programa de consola que:

1. Carga una imagen de código de barras desde el disco.  
2. Decodifica códigos de barras **PDF417** (incluyendo Macro PDF417).  
3. Imprime información básica como el tipo de código y el texto.  
4. Muestra el conjunto completo de campos Macro PDF417 (ID de archivo, ID de segmento, checksum, etc.).  

Sin servicios externos, solo un paquete NuGet único y unas pocas líneas de C#.

## Requisitos previos – Lo que necesitas antes de comenzar

- **.NET 6.0** o posterior (el código también funciona en .NET Framework 4.6+).  
- Una versión reciente de la biblioteca **Aspose.BarCode for .NET** – instálala vía NuGet (`Install-Package Aspose.BarCode`).  
- Un archivo de imagen que contenga un código de barras PDF417 (la demo usa `ExtPDF417Meta.png`).  
- Una comprensión básica de aplicaciones de consola C# (si has escrito “Hello World”, estás listo).

> **Consejo profesional:** Si no tienes una muestra de PDF417 a mano, genera una en el sitio de demostración de Aspose o usa una aplicación de smartphone que pueda crear etiquetas PDF417.

## Paso 1: Configura el proyecto e instala la biblioteca

Primero, crea un nuevo proyecto de consola:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
dotnet add package Aspose.BarCode
```

Esto incluye las dependencias del **ejemplo de código de barras c#** que necesitamos. Abre `Program.cs` y reemplaza el código predeterminado con el esqueleto a continuación:

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
            // We'll fill this in in the next steps.
        }
    }
}
```

## Paso 2: Inicializa el lector de códigos de barras para PDF417

El corazón de la solución es la clase `BarCodeReader`. Le indicamos qué archivo escanear y qué tipo de código de barras nos interesa—en este caso `DecodeType.Pdf417` o la variante macro `DecodeType.MacroPdf417`. Usar el tipo macro garantiza que capturemos los campos extendidos.

```csharp
// Step 2: Create the reader, targeting Macro PDF417 barcodes
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(
           imagePath, DecodeType.MacroPdf417))
{
    // The rest of the logic lives inside this block.
}
```

¿Por qué usar `MacroPdf417` en lugar de `Pdf417` simple? Macro PDF417 lleva metadatos adicionales (ID de archivo, recuento de segmentos, marcas de tiempo, etc.) en los que muchas aplicaciones del mundo real confían—piensa en manifiestos de envío divididos en varias páginas.

## Paso 3: Lee todos los códigos de barras encontrados en la imagen

Una sola imagen puede contener **leer múltiples códigos de barras**—quizás un código QR junto a un PDF417. El método `ReadBarCodes()` devuelve un `IEnumerable<BarCodeResult>` que podemos iterar.

```csharp
// Step 3: Iterate through every barcode detected
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Inside we’ll output both generic and macro‑specific data.
}
```

Si la imagen solo contiene un PDF417, el bucle se ejecuta una vez, manteniendo el código flexible para escenarios futuros donde puedas necesitar **leer múltiples códigos de barras** del mismo escaneo.

## Paso 4: Muestra información básica del código de barras

Antes de profundizar en los campos macro, es útil mostrar el tipo de código de barras y el texto decodificado. Esto te ayuda a verificar que el lector realmente reconoció un PDF417 y no otra simbología.

```csharp
Console.WriteLine($"CodeType : {result.CodeTypeName}");
Console.WriteLine($"CodeText : {result.CodeText}");
```

`CodeTypeName` mostrará *MacroPdf417* (o *Pdf417* si la bandera macro no está establecida), mientras que `CodeText` contiene los datos sin procesar codificados en el código de barras.

## Paso 5: Extrae los metadatos Macro PDF417

La propiedad `Extended` te brinda una inmersión profunda en la estructura específica de PDF417. Cada campo que imprimimos a continuación se corresponde directamente con la especificación macro de PDF417.

```csharp
// Step 5: Macro PDF417 metadata – all optional, but very handy
Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
```

Cada línea extrae una pieza diferente de la carga macro:

- **FileID** – un identificador único para todo el conjunto de documentos.  
- **SegmentID** – qué parte del archivo multisegmento estás viendo.  
- **SegmentsCount** – número total de segmentos esperados.  
- **FileName**, **Checksum**, **FileSize** – útiles para validar la integridad del archivo transferido.  
- **TimeStamp**, **Addressee**, **Sender** – campos opcionales que muchos sistemas logísticos incorporan.  

Si alguno de estos campos falta en el código de barras de origen, la biblioteca devuelve `null` o `0`, lo que puedes manejar según sea necesario.

## Paso 6: Ejecuta el ejemplo completo

Juntando todo, aquí tienes el programa completo, listo para ejecutar:

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
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the reader for Macro PDF417 (covers both standard and macro)
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Loop through every barcode detected – handles read multiple barcodes gracefully
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic info
                    Console.WriteLine($"CodeType : {result.CodeTypeName}");
                    Console.WriteLine($"CodeText : {result.CodeText}");

                    // Macro PDF417 specific metadata
                    Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding complete. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Salida esperada

Al ejecutar el programa con un `ExtPDF417Meta.png` válido, deberías ver algo similar a:

```
CodeType : MacroPdf417
CodeText : https://example.com/track?order=12345
Pdf417MacroFileID          : 101
Pdf417MacroSegmentID       : 1
Pdf417MacroSegmentsCount   : 3
Pdf417MacroFileName        : order_manifest.pdf
Pdf417MacroChecksum        : 0x1A2B3C4D
Pdf417MacroFileSize        : 45296
Pdf417MacroTimeStamp       : 2024-03-15T10:27:00Z
Pdf417MacroAddressee       : LogisticsDept
Pdf417MacroSender          : WarehouseA
MacroPdf417Terminator      : true
----------------------------------------
Decoding complete. Press any key to exit.
```

Si la imagen contiene más de un código de barras,

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo generar códigos de barras PDF417 – Codificación Compacta PDF417](/barcode/english/net/compact-pdf417-encoding/)
- [Cómo crear códigos de barras – PDF417 compacto con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cómo leer códigos de barras DataMatrix con Aspose.BarCode para .NET](/barcode/english/net/datamatrix-barcode-reading/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}