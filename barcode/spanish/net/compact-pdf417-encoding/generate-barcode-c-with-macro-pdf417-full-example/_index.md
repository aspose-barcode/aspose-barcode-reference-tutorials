---
category: general
date: 2026-08-19
description: Generar código de barras en C# usando Aspose.BarCode para crear un Macro
  PDF417 con texto personalizado y guardarlo como archivo de imagen.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode C#
- how to generate pdf417
- create barcode custom text
- generate barcode image file
language: es
lastmod: 2026-08-19
og_description: Genera códigos de barras en C# con Aspose.BarCode, aprende a generar
  PDF417, agrega texto personalizado y guarda el archivo de imagen del código de barras.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C#
og_title: Generar código de barras C# – Guía Macro PDF417
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Generate barcode C# using Aspose.BarCode to create a Macro PDF417 with
    custom text and save as an image file.
  headline: Generate barcode C# with Macro PDF417 – full example
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as
      needed.
    question: Can I generate a different image format?
  - answer: Macro PDF417 is designed for segmentation. Adjust `MacroPdf417SegmentsCount`
      and `MacroPdf417SegmentID` for each part, then concatenate the scanned results.
    question: What if my data exceeds a single barcode?
  - answer: Aspose.BarCode fully supports Unicode. Ensure your source file is saved
      with UTF‑8 encoding to avoid character corruption.
    question: Is Unicode support guaranteed?
  - answer: A licensed version removes the evaluation watermark and provides full
      functionality. The trial works for testing and learning.
    question: Do I need a license for production?
  type: FAQPage
tags:
- barcode
- C#
- Aspose
title: Generar código de barras C# con Macro PDF417 – ejemplo completo
url: /es/net/compact-pdf417-encoding/generate-barcode-c-with-macro-pdf417-full-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generar código de barras C# con Macro PDF417 – ejemplo completo

Si necesitas **generar código de barras C#** para un formato Macro PDF417, esta guía te muestra una solución lista‑para‑ejecutar. Verás cómo **generar pdf417**, incrustar texto personalizado y **generar archivo de imagen de código de barras** en un único programa autónomo.

El tutorial cubre todo, desde la instalación de la biblioteca Aspose.BarCode hasta la configuración de los metadatos de Macro PDF417, para que puedas copiar el código directamente en tu proyecto y ver el resultado de inmediato.

## Requisitos previos

- .NET 6.0 SDK o posterior (el código también funciona con .NET Framework 4.7+)
- Visual Studio 2022 (o cualquier IDE que soporte C#)
- Una licencia de Aspose.BarCode para .NET (la prueba gratuita funciona para evaluación)
- Familiaridad básica con la sintaxis de C#

> **Consejo profesional:** Instala el paquete NuGet mediante la CLI para evitar incompatibilidades de versiones:  
> `dotnet add package Aspose.BarCode`

## Paso 1: Configurar el proyecto e importar la biblioteca

Crea una nueva aplicación de consola y agrega las directivas `using` requeridas.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // The full barcode generation logic starts in the next step.
        }
    }
}
```

**Por qué este paso es importante:**  
El espacio de nombres `Aspose.BarCode.Generation` proporciona la clase `BarcodeGenerator`, que es el punto de entrada para crear cualquier tipo de código de barras, incluido Macro PDF417. Importar `System` te brinda acceso a `DateTime` para los metadatos de marca de tiempo.

## Paso 2: Crear un generador Macro PDF417 con texto personalizado

Reemplaza el comentario de marcador de posición con la inicialización del generador. Esto demuestra **crear texto personalizado de código de barras** mientras también seleccionas el tipo de codificación correcto.

```csharp
// Step 2: Initialize a barcode generator for Macro PDF417 with custom text.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MacroPdf417,          // Choose Macro PDF417 as the symbology
    "Åspóse.Barcóde©");               // Custom text can contain Unicode characters
```

**Explicación:**  
- `EncodeTypes.MacroPdf417` indica a Aspose que produzca un código de barras PDF417 que soporta funciones macro (segmentación de archivos, suma de verificación, etc.).  
- El texto `"Åspóse.Barcóde©"` muestra que los caracteres Unicode son totalmente compatibles, lo cual a menudo se requiere para aplicaciones internacionales.

## Paso 3: Configurar la apariencia y los metadatos de Macro PDF417

Ajusta finamente las dimensiones del código de barras y establece los campos específicos de macro requeridos para el manejo de archivos segmentados.

```csharp
// Appearance: set the narrow bar width to 2 pixels.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// PDF417 specific settings
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;  // Total number of segments
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01"; // Logical file name
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;     // CCITT‑16 CRC checksum
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;   // Approximate file size in bytes
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**Por qué estas configuraciones son importantes:**

| Configuración | Propósito |
|---------------|-----------|
| `XDimension.Pixels` | Controla la densidad visual; 2 px produce una imagen clara y escaneable. |
| `Columns` | Determina cuántas columnas de datos aparecen por fila, afectando el tamaño del código de barras. |
| `MacroPdf417FileID` | Identifica de forma única el archivo lógico a través de todos los segmentos. |
| `MacroPdf417SegmentID` / `SegmentsCount` | Permite la reconstrucción del archivo original a partir de múltiples códigos de barras. |
| `MacroPdf417FileName` | Nombre legible por humanos almacenado dentro del código de barras para procesamiento posterior. |
| `MacroPdf417Checksum` | Proporciona detección de errores usando el algoritmo CCITT‑16 CRC. |
| `MacroPdf417FileSize` | Ayuda al decodificador a saber cuándo se ha recibido el archivo completo. |
| `MacroPdf417TimeStamp` | Registra cuándo se generó el código de barras, útil para auditorías. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Campos opcionales que pueden ser usados en flujos de trabajo empresariales. |
| `MacroPdf417Terminator` | Indica que este segmento es el final (`Set`). |

## Paso 4: Guardar el código de barras como archivo de imagen

Finalmente, escribe el código de barras en un archivo PNG para que puedas verlo o incrustarlo en otro lugar.

```csharp
// Step 4: Save the generated barcode image to a file.
string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";   // Adjust the folder as needed
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode saved to {outputPath}");
```

**Lo que verás:**  
Una imagen PNG llamada `ExtPDF417Meta.png` que contiene un código de barras Macro PDF417 que codifica el texto personalizado y todos los campos de metadatos que configuraste arriba. La imagen puede abrirse con cualquier visor estándar o insertarse en PDFs, informes o páginas web.

## Código fuente completo (listo para copiar y pegar)

```csharp
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize generator with custom Unicode text.
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.MacroPdf417,
                "Åspóse.Barcóde©");

            // Appearance settings.
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Macro PDF417 metadata.
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save the barcode image.
            string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Salida esperada

Ejecutar el programa imprime:

```
Barcode saved to C:\Barcodes\ExtPDF417Meta.png
```

Abrir `ExtPDF417Meta.png` muestra un código de barras Macro PDF417 limpio que se escanea correctamente con cualquier lector PDF417, preservando el texto personalizado `"Åspóse.Barcóde©"` y los metadatos macro que definiste.

## Preguntas comunes y casos límite

- **¿Puedo generar un formato de imagen diferente?**  
  Sí. Reemplaza `BarCodeImageFormat.Png` con `Jpeg`, `Bmp` o `Gif` según sea necesario.

- **¿Qué pasa si mis datos exceden un solo código de barras?**  
  Macro PDF417 está diseñado para segmentación. Ajusta `MacroPdf417SegmentsCount` y `MacroPdf417SegmentID` para cada parte, luego concatena los resultados escaneados.

- **¿Se garantiza el soporte Unicode?**  
  Aspose.BarCode soporta Unicode completamente. Asegúrate de que tu archivo fuente esté guardado con codificación UTF‑8 para evitar la corrupción de caracteres.

- **¿Necesito una licencia para producción?**  
  Una versión con licencia elimina la marca de agua de evaluación y brinda funcionalidad completa. La versión de prueba funciona para pruebas y aprendizaje.

## Conclusión

Ahora sabes cómo **generar código de barras C#** para un Macro PDF417, **cómo generar pdf417** con metadatos enriquecidos, **crear texto personalizado de código de barras**, y **generar archivo de imagen de código de barras** usando Aspose.BarCode. El ejemplo completo y ejecutable muestra cada paso necesario, desde la configuración del proyecto hasta guardar la imagen PNG final.

### Próximos pasos

- Experimenta con otras configuraciones de PDF417 como `ErrorCorrectionLevel` y `CompactPdf417` para símbolos más pequeños.  
- Integra el código de barras generado en un informe PDF usando Aspose.PDF.  
- Explora la generación por lotes: recorre una colección de archivos y produce una serie de códigos de barras Macro PDF417 segmentados.

¡Siéntete libre de adaptar el código a tu propio flujo de trabajo, y que la generación de códigos de barras se convierta en una parte fluida de tus aplicaciones C#. ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo generar código de barras Aztec con relación de aspecto personalizada usando Aspose.BarCode para .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Generar imagen de código de barras – Code 93 con Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/)
- [Cómo generar y ajustar la altura del código de barras para One-Dimensional Databar usando Aspose.BarCode para .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}