---
category: general
date: 2026-10-28
description: Cómo decodificar códigos de barras PDF417 en C# rápidamente. Aprende
  a leer imágenes de códigos de barras en C# usando Aspose.BarCode con un ejemplo
  completo y ejecutable.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcode image c#
- PDF417 decoding C#
- barcode reader C#
- Aspose.BarCode example
language: es
lastmod: 2026-10-28
og_description: Cómo decodificar códigos de barras PDF417 en C# con Aspose.BarCode.
  Esta guía le muestra cómo leer una imagen de código de barras en C# paso a paso,
  con el código incluido.
og_image_alt: Screenshot of C# code that decodes a PDF417 barcode from an image
og_title: Cómo decodificar códigos de barras PDF417 en C# – tutorial de C# para leer
  imágenes de códigos de barras
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: How to decode PDF417 barcodes in C# quickly. Learn to read barcode
    image C# using Aspose.BarCode with a complete, runnable example.
  headline: How to decode PDF417 barcodes in C# and read barcode image C#
  type: TechArticle
- description: How to decode PDF417 barcodes in C# quickly. Learn to read barcode
    image C# using Aspose.BarCode with a complete, runnable example.
  name: How to decode PDF417 barcodes in C# and read barcode image C#
  steps:
  - name: What each line does
    text: '| Line | Explanation | |------|-------------| | `result.CodeTypeName` |
      Human‑readable name of the detected barcode type (e.g., “MacroPdf417”). | |
      `result.CodeText` | The raw data encoded in the barcode. | | `result.Extended.Pdf417.MacroPdf417FileID`
      | Identifier that ties all segments of a macro P'
  - name: Handling common edge cases
    text: '| Situation | Recommended handling | |-----------|----------------------|
      | **No barcode found** | Check `reader.ReadBarCodes().Any()` before the loop
      and display a friendly message. | | **Corrupted image** | Wrap the `BarCodeReader`
      creation in a `try/catch` block for `BarCodeException`. | | **Mult'
  - name: Next steps
    text: '* Explore other barcode formats by changing `DecodeType` (e.g., `DecodeType.QR`,
      `DecodeType.Code128`). * Combine multiple decoded segments to reconstruct the
      original document. * Use the `BarCodeGenerator` class to create test PDF417
      barcodes on the fly.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Cómo decodificar códigos de barras PDF417 en C# y leer la imagen del código
  de barras en C#
url: /es/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-and-read-barcode-image-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo decodificar códigos de barras PDF417 en C# y leer la imagen del código de barras C#

Si necesitas **how to decode pdf417** en una aplicación .NET, esta guía te brinda una solución lista para ejecutar. Verás exactamente cómo **read barcode image c#** usando la biblioteca Aspose.BarCode, extraer los campos macro‑PDF417 y mostrarlos en la consola.

La decodificación de códigos de barras PDF417 suele aparecer en sistemas de logística, emisión de boletos y verificación de identidad. Al final de este tutorial podrás cargar cualquier imagen que contenga un código de barras Macro PDF417, decodificarla y acceder a los valores de file ID, segment ID y segment count que son esenciales para ensamblar documentos de varios segmentos.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* .NET 6.0 SDK o posterior instalado  
* Visual Studio 2022 (o cualquier IDE de C#)  
* Un paquete NuGet Aspose.BarCode para .NET (`Aspose.BarCode`)  
* Un archivo de imagen que contenga un código de barras Macro PDF417 (el ejemplo usa `ExtPDF417Meta.png`)

Puedes agregar el paquete NuGet con el siguiente comando:

```bash
dotnet add package Aspose.BarCode
```

## Paso 1: Configurar el proyecto e importar espacios de nombres

Crea un nuevo proyecto de consola e importa los espacios de nombres requeridos. Las directivas `using` te dan acceso a `BarCodeReader`, `DecodeType` y a los objetos de extensión de resultados.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;
```

> **Why this step matters** – Importar los espacios de nombres correctos evita errores de compilación y hace que la superficie de la API esté disponible para la lógica de decodificación posterior.

## Paso 2: Especificar la ruta de la imagen

Define la ruta completa o relativa a la imagen del código de barras. Mantener la ruta en una variable hace que el código sea reutilizable para diferentes imágenes.

```csharp
// Step 2: Specify the path to the image that contains a Macro PDF417 barcode
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
```

> **Tip:** Usa `Path.Combine` si construyes la ruta a partir de varias partes; maneja los separadores de directorios en diferentes sistemas operativos.

## Paso 3: Crear un `BarCodeReader` configurado para la decodificación de Macro PDF417

Instancia `BarCodeReader` con la ruta de la imagen y la bandera `DecodeType.MacroPdf417`. Esto indica a la biblioteca que busque específicamente símbolos Macro PDF417.

```csharp
// Step 3: Create a BarCodeReader configured for MacroPdf417 decoding
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image.
```

> **Why this step matters** – Seleccionar el `DecodeType` adecuado mejora el rendimiento porque el motor omite formatos de códigos de barras no relacionados.

## Paso 4: Leer todos los códigos de barras y mostrar la información macro

Itera sobre cada `BarCodeResult` devuelto por `reader.ReadBarCodes()`. El objeto de resultado contiene tanto campos genéricos (`CodeTypeName`, `CodeText`) como extensiones específicas de Macro PDF417 (`MacroPdf417FileID`, `MacroPdf417SegmentID`, `MacroPdf417SegmentsCount`).

```csharp
    // Step 4: Read all barcodes in the image and display the most relevant macro information
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Code Type : {result.CodeTypeName}");
        Console.WriteLine($"Code Text : {result.CodeText}");

        // Macro PDF417 specific fields
        Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Segment ID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Segments  : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
    }
}
```

### Qué hace cada línea

| Línea | Explicación |
|------|-------------|
| `result.CodeTypeName` | Nombre legible por humanos del tipo de código de barras detectado (p.ej., “MacroPdf417”). |
| `result.CodeText` | Los datos sin procesar codificados en el código de barras. |
| `result.Extended.Pdf417.MacroPdf417FileID` | Identificador que une todos los segmentos de un documento macro PDF417. |
| `result.Extended.Pdf417.MacroPdf417SegmentID` | Índice del segmento actual dentro del documento completo. |
| `result.Extended.Pdf417.MacroPdf417SegmentsCount` | Número total de segmentos esperados para el documento. |

> **Pro tip:** Almacena los campos macro en una base de datos si necesitas volver a ensamblar el documento completo más tarde. El `File ID` te permite agrupar los segmentos que pertenecen a la misma fuente.

## Paso 5: Ejecutar el programa y verificar la salida

Compila y ejecuta la aplicación de consola:

```bash
dotnet run
```

Una salida típica de consola se ve así:

```
Code Type : MacroPdf417
Code Text : 0123456789ABCD
File ID   : 101
Segment ID: 1
Segments  : 3
```

Si la imagen contiene múltiples símbolos Macro PDF417, el bucle imprime cada uno secuencialmente.

### Manejo de casos límite comunes

| Situación | Manejo recomendado |
|-----------|--------------------|
| **No barcode found** | Verifica `reader.ReadBarCodes().Any()` antes del bucle y muestra un mensaje amigable. |
| **Corrupted image** | Envuelve la creación de `BarCodeReader` en un bloque `try/catch` para `BarCodeException`. |
| **Multiple barcode formats** | Usa `DecodeType.AllSupported` y filtra los resultados por `result.CodeTypeName == "MacroPdf417"`. |
| **Large images** | Reduce la escala de la imagen antes de decodificar para mejorar el rendimiento; la biblioteca acepta un objeto `Bitmap`. |

## Código fuente completo

A continuación se muestra el programa completo y autónomo. Cópialo en `Program.cs` de un nuevo proyecto de consola y reemplaza `YOUR_DIRECTORY/ExtPDF417Meta.png` con la ruta real a tu imagen.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417Decoder
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Specify the path to the image that contains a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Step 3: Create a BarCodeReader configured for MacroPdf417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Step 4: Read all barcodes in the image and display the most relevant macro information
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // Macro PDF417 specific fields
                    Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Segment ID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Segments  : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                }
            }
        }
    }
}
```

## Conclusión

Ahora sabes **how to decode pdf417** códigos de barras en C# y cómo **read barcode image c#** usando Aspose.BarCode. El tutorial te guió a través de la configuración del proyecto, carga de la imagen, configuración del lector, extracción de resultados y manejo de casos límite. Con esta base puedes integrar la decodificación de PDF417 en sistemas de inventario, validadores de boletos o cualquier flujo de trabajo que dependa de datos macro‑codificados.

### Próximos pasos

* Explora otros formatos de códigos de barras cambiando `DecodeType` (p.ej., `DecodeType.QR`, `DecodeType.Code128`).  
* Combina múltiples segmentos decodificados para reconstruir el documento original.  
* Usa la clase `BarCodeGenerator` para crear códigos de barras PDF417 de prueba al instante.  

Siéntete libre de experimentar con diferentes fuentes de imágenes, ajustar la salida de consola, o incrustar la lógica de decodificación en una API web para procesamiento en tiempo real. ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo decodificar PDF417 en C# con un ejemplo de lector de códigos de barras](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/)
- [Cómo generar códigos de barras PDF417 en C# con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/)
- [Cómo leer un código de barras desde una imagen c# usando Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}