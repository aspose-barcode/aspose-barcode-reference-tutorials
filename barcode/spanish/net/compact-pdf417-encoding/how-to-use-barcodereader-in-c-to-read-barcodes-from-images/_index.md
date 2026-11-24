---
category: general
date: 2026-11-23
description: Aprende a usar BarCodeReader en C# para leer códigos de barras a partir
  de una imagen, incluida la decodificación de Macro PDF417, con un ejemplo de código
  completo y explicaciones claras.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use barcodereader
- read barcodes from image c#
language: es
lastmod: 2026-11-23
og_description: Cómo usar BarCodeReader en C# para leer códigos de barras a partir
  de una imagen. Sigue esta guía paso a paso para decodificar Macro PDF417 y otros
  formatos con código listo para ejecutar.
og_image_alt: Screenshot of BarCodeReader console output showing decoded Macro PDF417
  data
og_title: Cómo usar BarCodeReader en C# – leer códigos de barras de imágenes rápidamente
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  headline: How to use BarCodeReader in C# to read barcodes from images
  type: TechArticle
- description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  name: How to use BarCodeReader in C# to read barcodes from images
  steps:
  - name: 1. Decoding multiple barcode formats
    text: 'If you need to detect more than one format, pass a combined `DecodeType`
      flag:'
  - name: 2. Managing large images
    text: 'Large images can cause high memory usage. Downscale the image before passing
      it to the reader:'
  - name: 3. Error handling
    text: 'Wrap the reading logic in a try‑catch block to surface decoding failures:'
  type: HowTo
tags:
- barcode
- C#
- image-processing
title: Cómo usar BarCodeReader en C# para leer códigos de barras de imágenes
url: /es/net/compact-pdf417-encoding/how-to-use-barcodereader-in-c-to-read-barcodes-from-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo usar BarCodeReader en C# para leer códigos de barras a partir de imágenes

Si necesitas **cómo usar BarCodeReader** para una lectura rápida de códigos de barras, esta guía te muestra exactamente eso. Ya sea que estés construyendo un sistema de punto de venta o automatizando la captura de documentos, aprenderás a leer códigos de barras de imágenes en proyectos C# con solo unas pocas líneas de código.

En este tutorial verás un ejemplo completo y ejecutable que decodifica un código de barras Macro PDF417, extrae sus propiedades extendidas y muestra información útil en la consola. No se requiere documentación externa: todo lo que necesitas está aquí.

## Requisitos previos

* .NET 6.0 (o posterior) instalado – el código apunta a la última versión LTS.
* Una referencia al paquete NuGet **Aspose.BarCode** (o cualquier compatible) que proporciona `BarCodeReader`.
* Un archivo de imagen que contenga un código de barras Macro PDF417 (el ejemplo usa `ExtPDF417Meta.png`).

> **Consejo profesional:** Si estás usando Visual Studio, agrega el paquete mediante `dotnet add package Aspose.BarCode` o la interfaz de usuario del Administrador de paquetes NuGet.

## Paso 1: Crear una instancia de BarCodeReader

Lo primero que haces al trabajar con una biblioteca de códigos de barras es instanciar un lector que apunte a la imagen de origen y le indique a la API qué tipo(s) de código de barras buscar.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Step 1: Initialise BarCodeReader for a Macro PDF417 image
using (BarCodeReader barcodeReader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png",
           DecodeType.MacroPdf417))
{
    // The using block guarantees proper disposal of native resources.
```

*Por qué este paso es importante:*  
`BarCodeReader` abre la imagen, asigna memoria nativa y prepara los algoritmos de decodificación para el `DecodeType` especificado. Al limitar el tipo a `MacroPdf417`, reduces la carga de CPU y mejoras la precisión de detección.

## Paso 2: Leer todos los códigos de barras encontrados en la imagen

Una sola imagen puede contener varios códigos de barras, especialmente al tratar con datos macro‑codificados. El método `ReadBarCodes` devuelve un enumerable de objetos `BarCodeResult`, cada uno representando un código detectado.

```csharp
    // Step 2: Iterate over every barcode found
    foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
    {
```

*Por qué este paso es importante:*  
Iterar sobre la colección garantiza que captures cada instancia, lo cual es esencial para escenarios de procesamiento por lotes o cuando un documento incrusta varios códigos.

## Paso 3: Acceder a las propiedades extendidas de Macro PDF417

Macro PDF417 almacena metadatos adicionales como identificadores de archivo, números de segmento y recuento total de segmentos. Estos valores se exponen a través de la propiedad `Extended.Pdf417` de `BarCodeResult`.

```csharp
        // Step 3: Pull extended Macro PDF417 information
        var macroInfo = barcodeResult.Extended.Pdf417;
```

*Por qué este paso es importante:*  
Los campos extendidos te permiten reconstruir documentos multi‑segmento o validar que todas las partes pertenecen a la misma fuente. Omitir este paso solo te daría el texto sin formato, perdiendo contexto valioso.

## Paso 4: Mostrar la información más útil

Finalmente, escribe los datos en la consola (o en cualquier registrador) para que puedas verificar la operación de lectura. El ejemplo muestra el tipo de código, el texto decodificado y varios campos macro.

```csharp
        // Step 4: Display key details
        Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
        Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
        Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
        // Additional macro fields are available:
        // macroInfo.MacroPdf417SegmentID
        // macroInfo.MacroPdf417SegmentsCount
    }
}
```

**Salida esperada en la consola**

```
Code Type: MacroPdf417
Code Text: 1234567890
Macro PDF417 File ID: 42
```

> **Nota:** Si la imagen no contiene un código de barras Macro PDF417, `ReadBarCodes()` devuelve una colección vacía y el cuerpo del bucle nunca se ejecuta. Siempre verifica si el resultado está vacío en código de producción.

## Leer códigos de barras desde una imagen en C# – manejo de escenarios comunes

### 1. Decodificar múltiples formatos de códigos de barras

Si necesitas detectar más de un formato, pasa una bandera `DecodeType` combinada:

```csharp
using (BarCodeReader reader = new BarCodeReader(
           "sample.png",
           DecodeType.Pdf417 | DecodeType.QR | DecodeType.DataMatrix))
{
    // Same iteration logic as before
}
```

### 2. Gestionar imágenes grandes

Las imágenes grandes pueden provocar un alto consumo de memoria. Reduce la escala de la imagen antes de pasarla al lector:

```csharp
using (Bitmap original = new Bitmap("large.png"))
using (Bitmap resized = new Bitmap(original, new Size(1024, 768)))
{
    // Save resized image to a temporary stream and feed it to BarCodeReader
}
```

### 3. Manejo de errores

Envuelve la lógica de lectura en un bloque try‑catch para exponer fallos de decodificación:

```csharp
try
{
    // reading code from previous steps
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## Ejemplo completo funcional

A continuación se muestra el programa completo que puedes copiar, pegar y ejecutar. Incluye todos los pasos, las directivas `using` necesarias y una estructura simple de manejo de errores.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        try
        {
            using (BarCodeReader barcodeReader = new BarCodeReader(
                       imagePath,
                       DecodeType.MacroPdf417))
            {
                bool anyFound = false;

                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    anyFound = true;
                    var macroInfo = barcodeResult.Extended.Pdf417;

                    Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
                    Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
                    Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
                    Console.WriteLine($"Segment ID: {macroInfo.MacroPdf417SegmentID}");
                    Console.WriteLine($"Segments Count: {macroInfo.MacroPdf417SegmentsCount}");
                    Console.WriteLine(new string('-', 40));
                }

                if (!anyFound)
                {
                    Console.WriteLine("No barcodes were detected in the image.");
                }
            }
        }
        catch (BarCodeException ex)
        {
            Console.Error.WriteLine($"Error reading barcode: {ex.Message}");
        }
    }
}
```

**Ejecutar el programa** muestra cada código de barras Macro PDF417 detectado y sus campos extendidos, o te informa que no se encontraron códigos de barras.

## Conclusión

Ahora sabes **cómo usar BarCodeReader** para leer códigos de barras desde aplicaciones C# que procesan imágenes, incluyendo la extracción de metadatos Macro PDF417. La solución cubre la inicialización, iteración, acceso a propiedades extendidas y consejos prácticos para manejar múltiples formatos, imágenes grandes y errores.

A continuación, podrías explorar:

* **Leer códigos QR** – reemplaza `DecodeType.MacroPdf417` por `DecodeType.QR`.
* **Guardar datos decodificados** en una base de datos o archivo JSON para procesamiento posterior.
* **Integrar con ASP.NET Core** para aceptar imágenes cargadas mediante una API web.

¡Siéntete libre de experimentar con diferentes tipos de códigos de barras y fuentes de imágenes! ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [tutorial de lector de códigos de barras en c# – leer códigos de barras Macro PDF417 paso a paso usando GroupDocs.Barcode](/barcode/english/net/compact-pdf417-encoding/c-barcode-reader-tutorial-read-macro-pdf417-barcodes-step-by/)
- [Cómo usar un generador de códigos de barras C# para Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/)
- [Leer código de barras desde una imagen C# – guía completa con Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}