---
category: general
date: 2026-10-15
description: Cómo leer imágenes de códigos de barras en C# rápidamente usando BarCodeReader.
  Aprende a leer múltiples códigos de barras y ve un ejemplo de lector de códigos
  de barras en C# que funciona con Macro‑PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode
- read multiple barcodes
- c# barcode reader example
- Macro‑PDF417 decoding
- barcode metadata extraction
language: es
lastmod: 2026-10-15
og_description: Cómo leer códigos de barras en C# usando BarCodeReader. Este tutorial
  muestra un ejemplo completo de lector de códigos de barras en C# que maneja múltiples
  códigos de barras y extrae metadatos Macro‑PDF417.
og_image_alt: Screenshot showing how to read barcode with C# BarCodeReader
og_title: Cómo leer códigos de barras en C# – ejemplo paso a paso
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  headline: How to read barcode images in C# – full example guide
  type: TechArticle
- description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  name: How to read barcode images in C# – full example guide
  steps:
  - name: Initialise the `BarCodeReader`
    text: '```csharp using Aspose.BarCode; using Aspose.BarCode.BarCodeRecognition;'
  - name: Read all barcodes present in the image
    text: '```csharp // Step 2: Read all barcodes in the image BarCodeResult[] results
      = reader.ReadBarCodes(); ```'
  - name: Display basic barcode details
    text: '```csharp foreach (BarCodeResult result in results) { Console.WriteLine($"CodeType:
      {result.CodeTypeName}"); Console.WriteLine($"CodeText: {result.CodeText}");
      ```'
  - name: Retrieve and show Macro‑PDF417 specific metadata
    text: '```csharp // Macro‑PDF417 extended data Console.WriteLine($"FileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Segment: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Count: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
      Console.WriteLine($"FileName'
  - name: Full runnable program
    text: Below is a self‑contained console application that puts all four steps together.
      Copy the code into a new `.cs` file, adjust the `imagePath`, and run `dotnet
      run`.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Cómo leer imágenes de códigos de barras en C# – guía completa con ejemplo
url: /es/net/one-dimensional-barcode-types/how-to-read-barcode-images-in-c-full-example-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo leer imágenes de códigos de barras en C# – guía completa con ejemplo

Si necesitas **cómo leer códigos de barras** de una imagen en una aplicación .NET, esta guía te brinda una solución lista para ejecutar. Verás un **ejemplo de lector de códigos de barras en C#** que funciona con símbolos Macro‑PDF417 y puede **leer varios códigos de barras** de una sola imagen.

Leer códigos de barras es un requisito común para sistemas de inventario, validación de tickets y procesamiento de documentos. Al final de este tutorial podrás:

* Inicializar el `BarCodeReader` para cualquier formato compatible.  
* Extraer información básica como el tipo de código y el texto decodificado.  
* Recuperar los metadatos específicos de Macro‑PDF417 (ID de archivo, segmento, suma de verificación, …).  
* Manejar imágenes que contienen varios códigos de barras sin código adicional.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* .NET 6.0 SDK o posterior instalado.  
* Un entorno de desarrollo (Visual Studio 2022, VS Code o Rider).  
* El paquete NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`) – proporciona la clase `BarCodeReader` utilizada en el ejemplo.  
* Un archivo de imagen que contenga un código de barras Macro‑PDF417 (p.ej., `MacroPdf417.png`).  

Puedes instalar el paquete NuGet con el siguiente comando:

```bash
dotnet add package Aspose.BarCode
```

## Cómo leer códigos de barras con BarCodeReader en C#

El núcleo de la solución se compone de cuatro pasos concisos. Cada paso está envuelto en un bloque `using` para garantizar que los recursos no administrados se liberen rápidamente.

### Paso 1: Inicializar el `BarCodeReader`

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Path to the image that contains the Macro‑PDF417 barcode(s)
string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

// Initialise the reader for the specific DecodeType
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The remaining steps are inside this block
}
```

**Por qué es importante:**  
`BarCodeReader` acepta una ruta de archivo y un `DecodeType`. Especificar `DecodeType.MacroPdf417` indica a la biblioteca que busque solo símbolos Macro‑PDF417, lo que mejora la velocidad de detección y reduce falsos positivos.

### Paso 2: Leer todos los códigos de barras presentes en la imagen

```csharp
    // Step 2: Read all barcodes in the image
    BarCodeResult[] results = reader.ReadBarCodes();
```

**Por qué es importante:**  
El método `ReadBarCodes()` devuelve una matriz que puede contener uno o varios objetos `BarCodeResult`. Este es el punto donde la capacidad de **leer varios códigos de barras** brilla: no necesitas un bucle separado para cada posible código de barras.

### Paso 3: Mostrar detalles básicos del código de barras

```csharp
    foreach (BarCodeResult result in results)
    {
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

**Por qué es importante:**  
`CodeTypeName` indica qué simbología se detectó (p.ej., “MacroPDF417”), mientras que `CodeText` contiene la carga útil decodificada. Estos dos campos son los más utilizados en la lógica posterior.

### Paso 4: Recuperar y mostrar los metadatos específicos de Macro‑PDF417

```csharp
        // Macro‑PDF417 extended data
        Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
        Console.WriteLine(new string('-', 40));
    }
}
```

**Por qué es importante:**  
Macro‑PDF417 extiende el formato PDF417 regular con metadatos a nivel de documento. Acceder a la propiedad `Extended.Pdf417` te brinda todo lo necesario para reconstruir el archivo original, validar la integridad o dirigir los datos al destinatario adecuado.

### Programa completo ejecutable

A continuación se muestra una aplicación de consola autónoma que combina los cuatro pasos. Copia el código en un nuevo archivo `.cs`, ajusta `imagePath` y ejecuta `dotnet run`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // 1️⃣ Initialise the BarCodeReader for Macro‑PDF417 images
            // ------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // ------------------------------------------------------------
                // 2️⃣ Read all barcodes present in the image
                // ------------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes were detected.");
                    return;
                }

                // ------------------------------------------------------------
                // 3️⃣ Iterate over each result – this is where we **read multiple barcodes**
                // ------------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // ------------------------------------------------------------
                    // 4️⃣ Extract Macro‑PDF417 metadata (c# barcode reader example)
                    // ------------------------------------------------------------
                    Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

#### Salida esperada en la consola

```
CodeType: MacroPDF417
CodeText: https://example.com/document
FileID:    12
Segment:   3
Count:     5
FileName:  report.pdf
Checksum:  0x1A2B3C4D
FileSize:  1048576
Time:      2024-08-15T14:23:00Z
Addressee: John Doe
Sender:    Acme Corp.
Terminator:END
----------------------------------------
```

Si la imagen contiene más de un símbolo Macro‑PDF417, el programa imprime un bloque separado para cada código de barras, demostrando la capacidad de **leer varios códigos de barras** sin código adicional.

## Manejo de casos límite comunes

| Situación | Qué hacer | Razón |
|-----------|------------|--------|
| **Archivo no encontrado** | Envuelve la construcción de `BarCodeReader` en un bloque `try/catch (FileNotFoundException)` y muestra un mensaje amigable. | Evita que la aplicación se bloquee e informa al usuario sobre el recurso faltante. |
| **No se detectó código de barras** | Verifica `results.Length == 0` (como se muestra en el programa completo) y maneja la situación de forma elegante. | Proporciona una retroalimentación clara cuando la imagen no contiene ninguna simbología compatible. |
| **Tipo de código de barras diferente** | Cambia `DecodeType.MacroPdf417` a `DecodeType.AllSupportedTypes` u otro valor enum específico. | Permite que la misma base de código funcione con QR, Code128, DataMatrix, etc., mientras sigue soportando **leer varios códigos de barras**. |
| **Imágenes grandes** | Establece `reader.AutoSize = true` o reduce la escala de la imagen antes de pasarla al lector. | Mejora el rendimiento y reduce la presión de memoria en el CLR. |
| **Uso seguro en hilos** | Crea una instancia separada de `BarCodeReader` por hilo; la clase no es segura para hilos. | Evita condiciones de carrera en escáneres o servicios web multihilo. |

## Consejos profesionales para código de producción

* **Liberar temprano:** La instrucción `using` garantiza que los recursos nativos (p.ej., buffers de imagen) se liberen rápidamente. En servicios de larga duración, libera el lector tan pronto como termines de procesar cada imagen.  
* **Batch processing**

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Leer código de barras desde imagen C# – guía completa con Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [Cómo crear código de barras macro PDF417 en C# usando Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Cómo leer PDF417 en C# – ejemplo completo de lector de códigos de barras](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}