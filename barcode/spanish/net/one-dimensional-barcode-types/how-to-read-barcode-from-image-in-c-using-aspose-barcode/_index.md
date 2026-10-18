---
category: general
date: 2026-10-18
description: Aprende a leer códigos de barras desde una imagen en C# con Aspose.BarCode,
  cubriendo la extracción de metadatos Macro PDF417 y el código de ejemplo completo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode from image
- C# barcode reader
- Macro PDF417 metadata
- BarCodeReader class
- DecodeType.MacroPdf417
- barcode metadata extraction
language: es
lastmod: 2026-10-18
og_description: Cómo leer códigos de barras desde una imagen usando C# Aspose.BarCode.
  Sigue este tutorial paso a paso para extraer los metadatos de Macro PDF417 y manejar
  escenarios comunes.
og_image_alt: Screenshot showing output of how to read barcode from image with C#
  Aspose.BarCode
og_title: Cómo leer códigos de barras desde una imagen en C# – guía completa de Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to read barcode from image in C# with Aspose.BarCode, covering
    Macro PDF417 metadata extraction and complete sample code.
  headline: How to read barcode from image in C# using Aspose.BarCode
  type: TechArticle
- description: Learn how to read barcode from image in C# with Aspose.BarCode, covering
    Macro PDF417 metadata extraction and complete sample code.
  name: How to read barcode from image in C# using Aspose.BarCode
  steps:
  - name: Expected console output
    text: '``` CodeType: MacroPdf417 CodeText: https://example.com/document.pdf MacroFileID:
      12345 MacroSegmentID: 1 MacroSegmentsCount: 3 MacroFileName: document.pdf MacroChecksum:
      0x1A2B3C4D MacroFileSize: 204800 MacroTimeStamp: 2023-07-15T10:23:45Z MacroAddressee:
      Acme Corp MacroSender: Warehouse 7 MacroTer'
  - name: Large images
    text: 'Reading very large images can consume significant memory. Use the `BarcodeReader`
      overload that accepts `ReaderParameters` to limit the maximum image size:'
  - name: Missing or corrupted metadata
    text: If any of the Macro fields are missing, the corresponding property returns
      `null` or `0`. Log these cases and decide whether to treat the barcode as incomplete.
  - name: Multiple barcode types in one image
    text: 'If an image may contain other barcode formats, you can pass an array of
      `DecodeType` values:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Cómo leer un código de barras de una imagen en C# usando Aspose.BarCode
url: /es/net/one-dimensional-barcode-types/how-to-read-barcode-from-image-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo leer códigos de barras desde una imagen en C# usando Aspose.BarCode

Si necesitas **cómo leer códigos de barras desde una imagen** en una aplicación .NET, esta guía muestra los pasos exactos con Aspose.BarCode. Ya sea que estés procesando documentos escaneados, recibos o etiquetas de inventario, verás cómo leer el código de barras, extraer los metadatos Macro PDF417 y manejar casos límite típicos.

Leer un código de barras desde una imagen es una tarea rutinaria, pero extraer los campos extendidos de Macro PDF417 añade una capa de complejidad. Este tutorial cubre el flujo de trabajo completo, desde la configuración del proyecto hasta un ejemplo completamente ejecutable, para que puedas copiar‑pegar el código y ver resultados inmediatos.

## Lo que aprenderás

- Cómo configurar Aspose.BarCode para proyectos C#.
- La forma correcta de instanciar el **lector de códigos de barras C#** para una imagen Macro PDF417.
- Cómo iterar sobre cada código de barras detectado y mostrar información básica.
- Cómo acceder a los **metadatos Macro PDF417** como ID de archivo, ID de segmento y checksum.
- Consejos para manejar metadatos faltantes, imágenes grandes y errores comunes de decodificación.

**Requisitos previos**

- .NET 6.0 (o posterior) instalado.  
- Familiaridad básica con C# y Visual Studio (cualquier IDE sirve).  
- Un archivo de imagen que contenga un código de barras Macro PDF417 (p. ej., `ExtPDF417Meta.png`).  

## Paso 1: Instalar Aspose.BarCode

Abre una terminal en la carpeta de tu proyecto y ejecuta:

```bash
dotnet add package Aspose.BarCode
```

El paquete incluye la **clase BarCodeReader**, que implementa la funcionalidad del **lector de códigos de barras C#** necesaria para este tutorial.

## Paso 2: Configurar el entorno de desarrollo

Crea una nueva aplicación de consola si aún no tienes una:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Agrega las directivas `using` al inicio de `Program.cs`:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;
```

Estos espacios de nombres exponen la **clase BarCodeReader** y la enumeración `DecodeType` requeridas para la decodificación de Macro PDF417.

## Paso 3: Inicializar el BarCodeReader para Macro PDF417

La esencia de **cómo leer códigos de barras desde una imagen** es crear una instancia de `BarCodeReader` que apunte al `DecodeType` específico. Para Macro PDF417 debes pasar `DecodeType.MacroPdf417`:

```csharp
// Step 3: Create a barcode reader for a Macro PDF417 image
using (BarCodeReader reader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png", DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image.
}
```

**Por qué es importante:**  
Seleccionar `DecodeType.MacroPdf417` indica a la biblioteca que busque el formato extendido Macro PDF417, que contiene campos adicionales más allá de los datos básicos del código de barras. Si utilizas un `DecodeType.Pdf417` genérico, esos campos extra serían ignorados.

## Paso 4: Iterar sobre los códigos de barras detectados

Una sola imagen puede contener varios códigos de barras. El método `ReadBarCodes()` devuelve una colección enumerable de objetos `BarCodeResult`. Recorre la colección para mostrar la información básica de cada código de barras:

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    Console.WriteLine($"CodeType: {result.CodeTypeName}");
    Console.WriteLine($"CodeText: {result.CodeText}");
}
```

`CodeTypeName` indica la simbología exacta del código de barras (p. ej., “MacroPdf417”), mientras que `CodeText` contiene la cadena decodificada.

## Paso 5: Extraer y mostrar los metadatos Macro PDF417

Cuando el código de barras es un Macro PDF417, la propiedad `Extended.Pdf417` proporciona un conjunto amplio de campos de metadatos. Accede a ellos directamente como se muestra a continuación:

```csharp
Console.WriteLine($"MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroTerminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
```

Estos campos te proporcionan todo lo necesario para reconstruir el archivo original de múltiples segmentos, verificar la integridad y asociar el código de barras con un documento o remitente específico.

### Salida esperada en la consola

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
MacroFileID: 12345
MacroSegmentID: 1
MacroSegmentsCount: 3
MacroFileName: document.pdf
MacroChecksum: 0x1A2B3C4D
MacroFileSize: 204800
MacroTimeStamp: 2023-07-15T10:23:45Z
MacroAddressee: Acme Corp
MacroSender: Warehouse 7
MacroTerminator: END
```

Si la imagen no contiene un código de barras Macro PDF417, el objeto `Extended.Pdf417` será `null`. Protege tu código contra esto para evitar `NullReferenceException`:

```csharp
if (result.Extended?.Pdf417 != null)
{
    // Safe to read metadata
}
else
{
    Console.WriteLine("No Macro PDF417 metadata found.");
}
```

## Paso 6: Manejo de errores comunes y casos límite

### Imágenes grandes

Leer imágenes muy grandes puede consumir una cantidad significativa de memoria. Usa la sobrecarga de `BarcodeReader` que acepta `ReaderParameters` para limitar el tamaño máximo de la imagen:

```csharp
ReaderParameters parameters = new ReaderParameters
{
    MaxImageSize = 4096 // pixels
};

using (BarCodeReader reader = new BarCodeReader(
           "large_image.png", DecodeType.MacroPdf417, parameters))
{
    // Process as before
}
```

### Metadatos faltantes o corruptos

Si alguno de los campos Macro falta, la propiedad correspondiente devuelve `null` o `0`. Registra estos casos y decide si tratar el código de barras como incompleto.

### Múltiples tipos de códigos de barras en una imagen

Si una imagen puede contener otros formatos de códigos de barras, puedes pasar un arreglo de valores `DecodeType`:

```csharp
DecodeType[] types = { DecodeType.MacroPdf417, DecodeType.QR, DecodeType.Code128 };
using (BarCodeReader reader = new BarCodeReader("mixed.png", types))
{
    // Iterate as before
}
```

Este enfoque mantiene la lógica de **cómo leer códigos de barras desde una imagen** flexible sin sacrificar el rendimiento.

## Paso 7: Código fuente completo

A continuación se muestra el programa completo, listo para ejecutar. Reemplaza `YOUR_DIRECTORY/ExtPDF417Meta.png` con la ruta a tu propia imagen.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image containing a Macro PDF417 barcode
            const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the C# barcode reader for Macro PDF417
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate over all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // Safely access Macro PDF417 metadata
                    if (result.Extended?.Pdf417 != null)
                    {
                        Console.WriteLine($"MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                        Console.WriteLine($"MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                        Console.WriteLine($"MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                        Console.WriteLine($"MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                        Console.WriteLine($"MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                        Console.WriteLine($"MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                        Console.WriteLine($"MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                        Console.WriteLine($"MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                        Console.WriteLine($"MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                        Console.WriteLine($"MacroTerminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro PDF417 metadata found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Barcode processing completed.");
        }
    }
}
```

Ejecuta el programa con:

```bash
dotnet run
```

Deberías ver el tipo de código de barras, el texto decodificado y todos los campos Macro PDF417 disponibles impresos en la consola.

## Conclusión

En este tutorial aprendiste **cómo leer códigos de barras desde una imagen** usando Aspose.BarCode para C#. La guía cubrió la configuración del **lector de códigos de barras C#**,

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Leer código de barras desde una imagen C# – guía completa con Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [Cómo crear un código de barras macro PDF417 en C# usando Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Cómo leer código de barras PDF417 en C# – guía completa paso a paso](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}