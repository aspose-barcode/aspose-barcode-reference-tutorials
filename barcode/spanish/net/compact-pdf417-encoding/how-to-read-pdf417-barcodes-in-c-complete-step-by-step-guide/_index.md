---
category: general
date: 2026-09-22
description: Aprende a leer códigos de barras PDF417 en C# con un ejemplo completo
  de lector de códigos de barras. Este tutorial te muestra cómo leer imágenes de códigos
  de barras en C# de forma rápida y fiable.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read barcode image c#
- c# barcode reader example
language: es
lastmod: 2026-09-22
og_description: Cómo leer códigos de barras PDF417 en C# usando un ejemplo conciso
  de lector de códigos de barras. Sigue la guía para decodificar imágenes Macro PDF417
  y extraer metadatos.
og_image_alt: Screenshot of C# code that reads a PDF417 barcode and prints its metadata
og_title: Cómo leer códigos de barras PDF417 en C# – ejemplo completo de lector de
  códigos de barras
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to read PDF417 barcodes in C# with a full barcode reader
    example. This tutorial shows you how to read barcode image C# quickly and reliably.
  headline: How to read PDF417 barcodes in C# – complete step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcodes in C# with a full barcode reader
    example. This tutorial shows you how to read barcode image C# quickly and reliably.
  name: How to read PDF417 barcodes in C# – complete step‑by‑step guide
  steps:
  - name: Why each step matters
    text: '1. **Creating the reader with `DecodeType.MacroPdf417`** – Macro PDF417
      is a special variant that can carry file‑level metadata. Specifying the decode
      type ensures the SDK parses those extra fields instead of treating the code
      as a plain PDF417. 2. **Iterating over `ReadBarCodes()`** – An image can '
  - name: Reading a non‑macro PDF417 barcode
    text: If your source images contain regular PDF417 codes (no macro metadata),
      replace `DecodeType.MacroPdf417` with `DecodeType.Pdf417`. The rest of the code
      stays identical, but the `Extended.Pdf417` block will be empty because those
      fields simply don’t exist.
  - name: Handling multi‑segment PDFs
    text: 'Macro PDF417 can split a large document across several barcode segments.
      To reassemble the original file you must:'
  - name: Dealing with corrupted images
    text: '- **Low contrast** – Increase image preprocessing (e.g., histogram equalization)
      before passing it to `BarCodeReader`. - **Rotation** – Use `barcodeReader.SetRotateAngle(90)`
      or enable auto‑rotate if the SDK supports it. - **Partial scans** – Ensure the
      image resolution is at least 300 dpi; otherwis'
  - name: Next steps
    text: '- Explore **read barcode image C#** techniques for other symbologies (QR,
      DataMatrix) using the same `BarCodeReader` API. - Integrate the barcode decoder
      into an ASP.NET Core service to process uploads on the fly. - Experiment with
      image preprocessing libraries (e.g., `OpenCvSharp`) to boost success'
  type: HowTo
tags:
- barcode
- pdf417
- c#
title: Cómo leer códigos de barras PDF417 en C# – guía completa paso a paso
url: /es/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo leer códigos de barras PDF417 en C# – guía completa paso a paso

Si necesitas **how to read pdf417** en una aplicación .NET, esta guía te muestra el código exacto y el razonamiento que necesitas. Al final de las dos primeras frases sabrás cómo leer una imagen de código de barras en C# usando la popular clase `BarCodeReader`, y tendrás un ejemplo listo para ejecutar que extrae cada pieza de los metadatos Macro PDF417.

Leer códigos de barras PDF417 es un requisito común al procesar etiquetas de envío, tarjetas de embarque o documentos seguros. Este tutorial cubre todo, desde la configuración del lector hasta el manejo de casos límite, para que puedas integrar la lectura de códigos de barras con confianza.

## Lo que lograrás

- Decodificar un archivo de imagen Macro PDF417.
- Imprimir información básica del código de barras (tipo y texto).
- Acceder a todos los campos extendidos de Macro PDF417 como ID de archivo, recuento de segmentos y marca de tiempo.
- Entender los problemas comunes al trabajar con códigos PDF417 de varios segmentos.

**Prerequisitos**

- .NET 6.0 o posterior (el código también funciona con .NET Framework 4.7+).
- Una referencia al SDK de códigos de barras que proporcione `BarCodeReader`, `DecodeType` y `BarCodeResult` (p.ej., Aspose.BarCode, Dynamsoft, o cualquier biblioteca que exponga la misma API).
- Un archivo de imagen (`ExtPDF417Meta.png`) que contiene un código de barras Macro PDF417.

> **Consejo profesional:** Coloca la imagen en una carpeta relativa a la raíz de tu proyecto y establece su propiedad **Copy to Output Directory** a *Copy if newer* para que la ruta funcione durante la depuración.

![How to read PDF417 barcode using C#](https://example.com/placeholder-image.png)

## Cómo leer códigos de barras PDF417 en C# – el código completo

A continuación tienes un programa autónomo que puedes pegar en una aplicación de consola. Crea un lector de códigos de barras, itera sobre cada resultado decodificado y muestra tanto los campos estándar como los extendidos de Macro PDF417.

```csharp
using System;
using Aspose.BarCode;          // Replace with the namespace of your barcode SDK
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode reader for a Macro PDF417 image
        // The second argument tells the SDK to look specifically for Macro PDF417 codes.
        using var barcodeReader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417);

        // Step 2: Decode all barcodes present in the image
        foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
        {
            // Step 3: Display the basic barcode information
            Console.WriteLine($"CodeType: {result.CodeTypeName}");
            Console.WriteLine($"CodeText: {result.CodeText}");

            // Step 4: Output Macro PDF417 specific metadata
            // All properties are available through the Extended.Pdf417 object.
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
            Console.WriteLine(new string('-', 40));
        }
    }
}
```

### Por qué cada paso es importante

1. **Crear el lector con `DecodeType.MacroPdf417`** – Macro PDF417 es una variante especial que puede transportar metadatos a nivel de archivo. Especificar el tipo de decodificación garantiza que el SDK analice esos campos extra en lugar de tratar el código como un PDF417 simple.
2. **Iterar sobre `ReadBarCodes()`** – Una imagen puede contener más de un código de barras (p.ej., un QR junto a un PDF417). El bucle garantiza que captures cada resultado.
3. **Imprimir `CodeTypeName` y `CodeText`** – Estas son las propiedades más usadas; te proporcionan el nombre de la simbología y la carga útil legible por humanos.
4. **Acceder a `Extended.Pdf417`** – El objeto `Extended` solo aparece para tipos de decodificación relacionados con PDF417. Cada propiedad se corresponde directamente con la especificación Macro PDF417, permitiéndote reconstruir el archivo original o validar el orden de los segmentos.

## Variaciones comunes y casos límite

### Lectura de un código de barras PDF417 no macro

Si tus imágenes de origen contienen códigos PDF417 regulares (sin metadatos macro), reemplaza `DecodeType.MacroPdf417` por `DecodeType.Pdf417`. El resto del código permanece idéntico, pero el bloque `Extended.Pdf417` estará vacío porque esos campos simplemente no existen.

### Manejo de PDFs multi‑segmento

Macro PDF417 puede dividir un documento grande en varios segmentos de código de barras. Para volver a ensamblar el archivo original debes:

1. Recopilar el `Pdf417MacroSegmentID` de cada segmento.
2. Ordenar los segmentos por su ID.
3. Verificar que `Pdf417MacroSegmentsCount` coincida con el número de segmentos recibidos.
4. Concatenar el `CodeText` de cada segmento en orden.
5. Opcionalmente validar `Pdf417MacroChecksum`.

A continuación tienes un fragmento conciso que demuestra la lógica de reensamblado:

```csharp
var segments = new SortedDictionary<int, string>();
int expectedCount = 0;

foreach (var result in barcodeReader.ReadBarCodes())
{
    int segId = result.Extended.Pdf417.MacroPdf417SegmentID;
    int segCount = result.Extended.Pdf417.MacroPdf417SegmentsCount;
    expectedCount = segCount;               // will be the same for every segment
    segments[segId] = result.CodeText;       // store payload by segment ID
}

// Verify we have all parts
if (segments.Count == expectedCount)
{
    string fullPayload = string.Concat(segments.Values);
    Console.WriteLine("Reassembled payload:");
    Console.WriteLine(fullPayload);
}
else
{
    Console.WriteLine($"Missing segments: expected {expectedCount}, received {segments.Count}");
}
```

### Tratamiento de imágenes corruptas

- **Bajo contraste** – Incrementa el preprocesamiento de la imagen (p.ej., ecualización de histograma) antes de pasarla a `BarCodeReader`.
- **Rotación** – Usa `barcodeReader.SetRotateAngle(90)` o habilita la auto‑rotación si el SDK lo soporta.
- **Escaneos parciales** – Asegúrate de que la resolución de la imagen sea al menos 300 dpi; de lo contrario el SDK podría perder segmentos pequeños.

## ejemplo de lector de códigos de barras c# – mejores prácticas

| Práctica | Razón |
|----------|--------|
| **Dispose el lector con `using`** | Garantiza que los recursos nativos se liberen rápidamente, evitando fugas de memoria. |
| **Validar que `result.Extended` no sea nulo** | Algunos SDK devuelven `null` para códigos no macro; la verificación evita una `NullReferenceException`. |
| **Registrar el `Pdf417MacroFileID`** | Este identificador es único por archivo y útil para auditorías. |
| **Encerrar la decodificación en un try/catch** | Errores de I/O (archivo faltante) o formatos no soportados generan excepciones que deben manejarse de forma adecuada. |

```csharp
try
{
    // decoding logic here
}
catch (FileNotFoundException ex)
{
    Console.Error.WriteLine($"Image not found: {ex.FileName}");
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## Salida esperada

Ejecutar el programa completo contra un `ExtPDF417Meta.png` correctamente formateado produce una salida similar a:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-08-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

Si la imagen contiene varios segmentos, el bucle imprimirá los metadatos de cada segmento secuencialmente.

## Conclusión

Ahora sabes **how to read pdf417** códigos de barras en C# y tienes un **c# barcode reader example** que extrae cada campo Macro PDF417. La solución cubre la decodificación básica, extracción de metadatos, reensamblado multi‑segmento y manejo de errores, brindándote una base lista para producción para cualquier flujo de trabajo de procesamiento de documentos.

### Próximos pasos

- Explora técnicas de **read barcode image C#** para otras simbologías (QR, DataMatrix) usando la misma API `BarCodeReader`.
- Integra el decodificador de códigos de barras en un servicio ASP.NET Core para procesar cargas al instante.
- Experimenta con bibliotecas de preprocesamiento de imágenes (p.ej., `OpenCvSharp`) para mejorar la tasa de éxito en escaneos de baja calidad.

¡Feliz codificación, y siéntete libre de adaptar el ejemplo a tu caso de uso específico!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo guardar códigos de barras en C# – Generar códigos PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Cómo leer PDF417 en C# – Guía completa paso a paso](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [Cómo establecer nivel de error en código de barras PDF417 – Guía completa](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}