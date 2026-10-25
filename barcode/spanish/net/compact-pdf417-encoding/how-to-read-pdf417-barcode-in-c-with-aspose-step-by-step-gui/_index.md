---
category: general
date: 2026-10-24
description: Aprende a leer códigos de barras PDF417 en C# usando Aspose.BarCode.
  Este tutorial cubre la lectura de una imagen de código de barras, la extracción
  de campos Macro PDF417 y el manejo de escenarios comunes.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode image c#
- read barcode with aspose
language: es
lastmod: 2026-10-24
og_description: Cómo leer códigos de barras PDF417 en C# usando Aspose.BarCode. Sigue
  este tutorial completo para decodificar imágenes, recuperar los metadatos Macro
  PDF417 y evitar errores comunes.
og_image_alt: Screenshot showing how to read PDF417 barcode results in a C# console
  application
og_title: Cómo leer códigos de barras PDF417 en C# con Aspose – guía completa
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  headline: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  name: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  steps:
  - name: Why use `DecodeType.MacroPdf417`?
    text: '* **Macro PDF417** stores additional fields (file ID, segment count, timestamps,
      etc.) that are not present in standard PDF417. * The `Extended` property of
      `BarCodeResult` is populated only when you request the macro type, saving you
      a separate parsing step.'
  - name: What each property means
    text: '| Property | Description | |----------|-------------| | **MacroPdf417FileID**
      | Unique identifier for the whole multi‑segment document. | | **MacroPdf417SegmentID**
      | Index of the current segment (starting at 0). | | **MacroPdf417SegmentsCount**
      | Total number of segments that belong to the file. | '
  - name: Missing macro fields
    text: 'Sometimes a PDF417 barcode is generated without the optional macro fields.
      Accessing a missing property returns `null` or `0`. Guard against this if you
      plan to store the values:'
  - name: Corrupted or low‑quality images
    text: 'If the image is blurry, you can improve detection by enabling the `BarCodeReader`
      quality options:'
  - name: Multiple barcode formats in one image
    text: 'If you suspect other barcode types might be present, use `DecodeType.AllSupported`
      and filter results:'
  type: HowTo
- questions:
  - answer: Yes. Change `DecodeType.MacroPdf417` to `DecodeType.Pdf417`. The `Extended`
      property will be empty, but `CodeText` and `CodeTypeName` remain available.
    question: Can I read a standard PDF417 (non‑macro) with the same code?
  - answer: Absolutely. Use the overload `new BarCodeReader(Stream, DecodeType)` and
      pass a `FileStream` or `MemoryStream`. This is useful when the image comes from
      a web API.
    question: Does Aspose.BarCode support reading from a stream instead of a file
      path?
  - answer: 'The `MacroPdf417Checksum` field contains the raw CRC‑16 value. You can
      recompute the checksum on the reconstructed file and compare it to ensure data
      integrity. ## Next steps and related topics * **Write PDF417 barcodes** – explore
      `BarCodeGenerator` to create macro barcodes for testing. * **Combine'
    question: How do I validate the checksum?
  type: FAQPage
tags:
- barcode
- Aspose.BarCode
- C#
title: Cómo leer códigos de barras PDF417 en C# con Aspose – guía paso a paso
url: /es/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-with-aspose-step-by-step-gui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo leer códigos de barras PDF417 en C# con Aspose – guía paso a paso

Si necesitas **cómo leer códigos de barras PDF417** en una aplicación .NET, esta guía te muestra exactamente cómo leer códigos de barras PDF417 en C# usando la biblioteca Aspose.BarCode. Ya sea que estés procesando documentos escaneados, capturas móviles o imágenes importadas por lotes, el código a continuación decodifica el código de barras y extrae cada propiedad Macro PDF417 que puedas necesitar.

Leer una imagen de código de barras en C# puede resultar intimidante, especialmente cuando el código contiene metadatos extendidos. Este tutorial elimina la incertidumbre al proporcionar un ejemplo completo y ejecutable, explicando cada línea y cubriendo casos límite como segmentos macro ausentes o imágenes corruptas. Al final, podrás integrar la decodificación de PDF417 en cualquier proyecto C# con confianza.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* .NET 6.0 SDK o posterior instalado  
* Visual Studio 2022 (o cualquier IDE que soporte .NET)  
* Una licencia o evaluación gratuita de **Aspose.BarCode for .NET** – puedes obtener una clave temporal en el sitio web de Aspose  
* Un archivo de imagen que contenga un código de barras Macro PDF417 (p. ej., `ExtPDF417Meta.png`)

> **Consejo profesional:** Si solo deseas experimentar, Aspose ofrece una prueba de 30 días que incluye la funcionalidad completa para la lectura de códigos de barras.

## Paso 1: Instalar el paquete NuGet Aspose.BarCode

Abre la carpeta de tu proyecto en una terminal y ejecuta:

```bash
dotnet add package Aspose.BarCode
```

El paquete agrega el espacio de nombres `Aspose.BarCode.ReadRecognition`, que contiene la clase `BarCodeReader` utilizada para decodificar imágenes.

## Paso 2: Crear un BarCodeReader para una imagen PDF417

El constructor de `BarCodeReader` recibe dos argumentos: la ruta al archivo de imagen y el `DecodeType` que deseas usar. Especificar `DecodeType.MacroPdf417` indica a Aspose que busque símbolos Macro PDF417 y que rellene automáticamente las propiedades extendidas.

```csharp
using Aspose.BarCode.ReadRecognition;

// Replace with the actual path to your barcode image
string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image
```

### ¿Por qué usar `DecodeType.MacroPdf417`?

* **Macro PDF417** almacena campos adicionales (ID de archivo, recuento de segmentos, marcas de tiempo, etc.) que no están presentes en un PDF417 estándar.  
* La propiedad `Extended` de `BarCodeResult` se rellena solo cuando solicitas el tipo macro, ahorrándote un paso de análisis separado.

## Paso 3: Iterar a través de todos los códigos de barras detectados

Una sola imagen puede contener varios símbolos PDF417 (por ejemplo, cuando un documento se divide en varias páginas). El método `ReadBarCodes()` devuelve un `IEnumerable<BarCodeResult>` que puedes recorrer.

```csharp
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // Basic information
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

Si la imagen no contiene ningún código de barras, el bucle simplemente no se ejecuta y el programa finaliza de forma ordenada. Este comportamiento hace que el código sea seguro para procesamiento por lotes donde algunos archivos pueden no tener códigos de barras.

## Paso 4: Mostrar las propiedades extendidas de Macro PDF417

La propiedad `Extended.Pdf417` agrupa todos los campos específicos del macro. Cada campo se corresponde directamente con la especificación PDF417, por lo que puedes almacenarlos en una base de datos, registrarlos o utilizarlos para validaciones posteriores.

```csharp
        // Macro PDF417 extended properties
        Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
    }
}
```

### Qué significa cada propiedad

| Propiedad | Descripción |
|----------|-------------|
| **MacroPdf417FileID** | Identificador único para todo el documento de varios segmentos. |
| **MacroPdf417SegmentID** | Índice del segmento actual (comenzando en 0). |
| **MacroPdf417SegmentsCount** | Número total de segmentos que pertenecen al archivo. |
| **MacroPdf417FileName** | Nombre de archivo opcional incrustado en el código de barras. |
| **MacroPdf417Checksum** | Suma de verificación CRC‑16 para el bloque de datos macro. |
| **MacroPdf417FileSize** | Tamaño original del archivo en bytes. |
| **MacroPdf417TimeStamp** | Marca de tiempo cuando se generó el código de barras macro. |
| **MacroPdf417Addressee** | Destinatario previsto del documento. |
| **MacroPdf417Sender** | Emisor del documento. |
| **MacroPdf417Terminator** | Indicador de terminador que señala el final de la secuencia macro. |

Estos campos son especialmente útiles cuando estás reconstruyendo un PDF o imagen grande que se dividió en varios símbolos PDF417 para imprimir en medios de baja resolución.

## Paso 5: Manejar casos límite comunes

### Campos macro ausentes

A veces un código de barras PDF417 se genera sin los campos macro opcionales. Acceder a una propiedad inexistente devuelve `null` o `0`. Protege tu código si planeas almacenar los valores:

```csharp
string fileName = result.Extended.Pdf417.MacroPdf417FileName ?? "Unnamed";
long fileSize = result.Extended.Pdf417.MacroPdf417FileSize;
```

### Imágenes corruptas o de baja calidad

Si la imagen está borrosa, puedes mejorar la detección habilitando las opciones de calidad del `BarCodeReader`:

```csharp
reader.BarcodeSettings.ImageQuality = 90; // value between 0‑100
reader.BarcodeSettings.PureBarcode = false; // allow detection in noisy backgrounds
```

Estas configuraciones son opcionales pero pueden aumentar drásticamente la tasa de éxito para documentos escaneados.

### Múltiples formatos de código de barras en una sola imagen

Si sospechas que pueden estar presentes otros tipos de códigos de barras, usa `DecodeType.AllSupported` y filtra los resultados:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        if (result.CodeType == DecodeType.MacroPdf417)
        {
            // Process macro PDF417 as shown above
        }
    }
}
```

## Ejemplo completo ejecutable

Copia el siguiente programa en un nuevo proyecto de consola (`dotnet new console`) y ejecútalo. Reemplaza la variable `imagePath` con la ubicación de tu propia imagen Macro PDF417.

```csharp
using System;
using Aspose.BarCode.ReadRecognition;

class Program
{
    static void Main()
    {
        // Path to the barcode image
        string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Optional: improve detection on low‑quality scans
            reader.BarcodeSettings.ImageQuality = 90;
            reader.BarcodeSettings.PureBarcode = false;

            // Iterate through every barcode found in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Output extended Macro PDF417 fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender ?? \"N/A\"}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**Salida esperada** (los valores variarán según tu imagen):

```
CodeType: MacroPdf417
CodeText: 1234567890ABCDEFGHIJ
Pdf417MacroFileID: 42
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: Invoice_2026_10.pdf
Pdf417MacroChecksum: 32768
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2026-10-24T14:32:10Z
Pdf417MacroAddressee: AccountingDept
Pdf417MacroSender: SalesTeam
MacroPdf417Terminator: True
----------------------------------------
```

Si la imagen no contiene símbolos Macro PDF417, el programa no escribe nada y finaliza silenciosamente—perfecto para trabajos por lotes que procesan muchos archivos.

## Preguntas frecuentes

**P: ¿Puedo leer un PDF417 estándar (no macro) con el mismo código?**  
R: Sí. Cambia `DecodeType.MacroPdf417` a `DecodeType.Pdf417`. La propiedad `Extended` quedará vacía, pero `CodeText` y `CodeTypeName` seguirán disponibles.

**P: ¿Aspose.BarCode admite la lectura desde un stream en lugar de una ruta de archivo?**  
R: Absolutamente. Usa la sobrecarga `new BarCodeReader(Stream, DecodeType)` y pasa un `FileStream` o `MemoryStream`. Esto es útil cuando la imagen proviene de una API web.

**P: ¿Cómo valido la suma de verificación?**  
R: El campo `MacroPdf417Checksum` contiene el valor CRC‑16 sin procesar. Puedes volver a calcular la suma de verificación sobre el archivo reconstruido y compararla para garantizar la integridad de los datos.

## Próximos pasos y temas relacionados

* **Write PDF417 barcodes** – explore `BarCodeGenerator` to create macro barcodes for testing.  
* **Combine multiple segments** – after reading all segments, order them by `MacroPdf417SegmentID` and concatenate `CodeText` to reconstruct the original payload.  
* **Performance tuning** – for high‑throughput scenarios, reuse a single `BarCodeReader` instance across many images and

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo leer PDF417 en C# – Ejemplo completo de código de barras](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [Cómo crear un código de barras macro PDF417 en C# usando Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Leer código de barras desde una imagen C# – guía completa con Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}