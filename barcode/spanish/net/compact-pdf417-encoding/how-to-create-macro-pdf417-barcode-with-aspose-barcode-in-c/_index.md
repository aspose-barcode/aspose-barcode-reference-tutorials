---
category: general
date: 2026-11-20
description: Aprenda a crear un código de barras macro PDF417 en C# usando Aspose.BarCode.
  Esta guía cubre los metadatos, los parámetros y el guardado de la imagen.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- macro PDF417 metadata
- Aspose.BarCode C#
- PDF417 macro parameters
- barcode generator example
language: es
lastmod: 2026-11-20
og_description: Crea un código de barras macro PDF417 en C# con Aspose.BarCode. Sigue
  este tutorial completo para establecer metadatos, configurar parámetros y exportar
  un PNG.
og_image_alt: Screenshot of a generated macro PDF417 barcode image
og_title: Crear código de barras macro PDF417 en C# – guía paso a paso
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to create macro PDF417 barcode in C# using Aspose.BarCode.
    This guide covers metadata, parameters, and saving the image.
  headline: How to create macro PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to create macro PDF417 barcode in C# using Aspose.BarCode.
    This guide covers metadata, parameters, and saving the image.
  name: How to create macro PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: Expected output
    text: 'Running the program prints a confirmation line similar to:'
  - name: What if I need more than 20 segments?
    text: The `MacroPdf417SegmentsCount` property can be set up to `255`. Ensure the
      receiving system can handle the larger segment count, and consider splitting
      the data into a manageable number of symbols.
  - name: How does the checksum affect scanning?
    text: The CCITT‑16 checksum (`MacroPdf417Checksum`) provides an additional error‑checking
      layer. If a scanner detects a mismatch, it will reject the barcode. You can
      omit the checksum if your workflow does not require it.
  - name: Can I generate a PDF417 macro barcode without Aspose?
    text: Yes, other libraries (e.g., ZXing.Net, Dynamsoft) support PDF417, but macro‑specific
      fields are often missing. Aspose.BarCode offers the most complete implementation
      for macro metadata.
  - name: What image formats are supported for saving?
    text: The `Save` method accepts any format defined in `BarCodeImageFormat`, such
      as `Png`, `Jpeg`, `Gif`, `Bmp`, and `Tiff`. Choose a format that matches your
      downstream processing pipeline.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Cómo crear un código de barras macro PDF417 con Aspose.BarCode en C#
url: /es/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un código de barras macro PDF417 con Aspose.BarCode en C#

Si necesitas **crear un código de barras macro PDF417** en una aplicación .NET, este tutorial muestra los pasos exactos. Verás cómo configurar los metadatos específicos de macro, ajustar la configuración visual y guardar el resultado como un archivo PNG.

Generar un código de barras macro PDF417 es útil cuando deseas dividir un gran conjunto de datos en varios símbolos manteniendo un identificador a nivel de archivo. En el ejemplo a continuación utilizamos la biblioteca Aspose.BarCode, que ofrece una API fluida para todas las funciones de PDF417.

Al final de esta guía tendrás un programa de consola listo para ejecutar que produce una imagen de código de barras que contiene toda la información de macro.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* .NET 6.0 SDK o posterior instalado.
* Visual Studio 2022 (o cualquier IDE que admita C#).
* El paquete NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`).

Puedes añadir el paquete con el siguiente comando:

```bash
dotnet add package Aspose.BarCode
```

## Paso 1: Inicializar el generador de códigos de barras para macro PDF417

El primer paso es instanciar un `BarcodeGenerator` con el valor del enumerado `EncodeTypes.MacroPdf417`. Esto indica a la biblioteca que trate el código de barras como un símbolo macro PDF417.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The generator is now ready for further configuration.
```

*Por qué es importante*: Seleccionar `MacroPdf417` habilita todas las propiedades relacionadas con macro en el objeto de parámetros `Pdf417`.

## Paso 2: Establecer la apariencia visual básica

Un código de barras legible comienza con un tamaño de módulo y un recuento de columnas adecuados. La propiedad `XDimension.Pixels` controla el ancho de un solo módulo, mientras que `Pdf417.Columns` define cuántas columnas de datos contiene cada fila.

```csharp
    // Set module width to 2 pixels.
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

    // Use 5 columns per row – a compact layout for this example.
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
```

Ajustar estos valores influye tanto en la fiabilidad del escáner como en el tamaño de la imagen.

## Paso 3: Definir los detalles de identificación del archivo macro

Macro PDF417 requiere un identificador de archivo, un identificador de segmento y el recuento total de segmentos. Estos tres campos permiten que un escáner vuelva a ensamblar el conjunto de datos original.

```csharp
    // Unique file identifier for the whole macro file.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (starting at 0 or 1 based on your protocol).
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the complete file.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Optional human‑readable file name.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

Estos **parámetros macro PDF417** son el núcleo de la funcionalidad macro. Sin ellos, un escáner no puede enlazar los símbolos entre sí.

## Paso 4: Añadir metadatos macro opcionales

Más allá de los identificadores obligatorios, el formato macro admite campos adicionales como checksum, tamaño de archivo, marca de tiempo, destinatario, remitente y una bandera de terminador. Proveer estos datos mejora la detección de errores y brinda contexto a los sistemas posteriores.

```csharp
    // CCITT‑16 checksum example.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate file size in bytes (helps the receiver allocate buffers).
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;

    // Timestamp of when the macro file was generated.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the final segment.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Consejo profesional*: Si tu flujo de trabajo no necesita un campo en particular, puedes dejarlo con su valor predeterminado. La biblioteca omitirá el elemento de datos correspondiente del código de barras.

## Paso 5: Guardar la imagen del código de barras

Después de configurar todos los parámetros, llama a `Save` para exportar el código de barras. El ejemplo guarda el archivo PNG en un directorio especificado por el usuario.

```csharp
    // Replace with a valid folder on your machine.
    string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

    // Save as PNG – other formats (Jpeg, Gif, etc.) are also supported.
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Cuando el programa finaliza, `ExtPDF417Meta.png` contiene un código de barras macro PDF417 que codifica el texto `"Åspóse.Barcóde©"` junto con todos los metadatos macro.

## Código fuente completo

A continuación se muestra el programa completo y autocontenido. Cópialo en un nuevo proyecto de consola y ejecútalo después de instalar el paquete NuGet Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a macro PDF417 barcode generator.
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Visual appearance.
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

                // Step 3: Core macro identifiers.
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Step 4: Optional macro metadata.
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 5: Export the image.
                string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Macro PDF417 barcode saved to {outputPath}");
            }
        }
    }
}
```

### Salida esperada

Ejecutar el programa imprime una línea de confirmación similar a:

```
Macro PDF417 barcode saved to YOUR_DIRECTORY/ExtPDF417Meta.png
```

Abrir el archivo PNG muestra un código de barras denso y de alto contraste. Escanearlo con un lector compatible con PDF417 devuelve el texto original más todos los campos macro.

## Preguntas frecuentes y casos especiales

### ¿Qué pasa si necesito más de 20 segmentos?

La propiedad `MacroPdf417SegmentsCount` puede establecerse hasta `255`. Asegúrate de que el sistema receptor pueda manejar el recuento mayor de segmentos y considera dividir los datos en un número manejable de símbolos.

### ¿Cómo afecta el checksum al escaneo?

El checksum CCITT‑16 (`MacroPdf417Checksum`) proporciona una capa adicional de verificación de errores. Si un escáner detecta una discrepancia, rechazará el código de barras. Puedes omitir el checksum si tu flujo de trabajo no lo requiere.

### ¿Puedo generar un código de barras PDF417 macro sin Aspose?

Sí, otras bibliotecas (p. ej., ZXing.Net, Dynamsoft) admiten PDF417, pero a menudo carecen de los campos específicos de macro. Aspose.BarCode ofrece la implementación más completa para los metadatos macro.

### ¿Qué formatos de imagen son compatibles para guardar?

El método `Save` acepta cualquier formato definido en `BarCodeImageFormat`, como `Png`, `Jpeg`, `Gif`, `Bmp` y `Tiff`. Elige un formato que coincida con tu canal de procesamiento posterior.

## Conclusión

Ahora sabes cómo **crear un código de barras macro PDF417** en C# usando Aspose.BarCode. El tutorial cubrió la inicialización del generador, la configuración visual, los identificadores de archivo macro, los metadatos opcionales y la exportación de la imagen. Con esta base puedes integrar macro PDFs en sistemas de inventario, seguimiento de documentos o cualquier escenario que requiera transmisión de datos segmentada.

Los siguientes pasos incluyen experimentar con diferentes valores de `XDimension` para mayor resolución, añadir ajustes de nivel de corrección de errores o integrar el código de barras en una API web que devuelva directamente el flujo PNG. Para temas relacionados, consulta los tutoriales sobre **ejemplo de generador de códigos de barras**, **parámetros macro PDF417** y **manejo de metadatos macro PDF417**.

¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [How to create PDF417 barcode image in C# with Macro PDF417 options](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}