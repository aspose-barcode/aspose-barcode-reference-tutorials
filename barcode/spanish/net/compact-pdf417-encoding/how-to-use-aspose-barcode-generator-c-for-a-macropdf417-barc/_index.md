---
category: general
date: 2026-10-05
description: Aspose Barcode Generator C# le permite agregar datos macro y generar
  códigos de barras PDF417 sin esfuerzo. Aprenda paso a paso cómo agregar metadatos
  macro y crear una imagen PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode generator c#
- how to add macro
- how to generate pdf417
language: es
lastmod: 2026-10-05
og_description: Aspose Barcode Generator C# te muestra cómo agregar metadatos macro
  y generar un código de barras PDF417 en unas pocas líneas de código.
og_image_alt: Screenshot of a MacroPdf417 barcode created with Aspose Barcode Generator
  C#
og_title: Generador de códigos de barras Aspose C# – agregar macro y generar código
  de barras PDF417
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Aspose Barcode Generator C# lets you add macro data and generate PDF417
    barcodes effortlessly. Learn step‑by‑step how to add macro metadata and create
    a PDF417 image.
  headline: How to use Aspose Barcode Generator C# for a MacroPdf417 barcode
  type: TechArticle
tags:
- barcode
- csharp
- aspose
title: Cómo usar Aspose Barcode Generator C# para un código de barras MacroPdf417
url: /es/net/compact-pdf417-encoding/how-to-use-aspose-barcode-generator-c-for-a-macropdf417-barc/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo usar Aspose Barcode Generator C# para un código de barras MacroPdf417

Si necesitas crear un código de barras MacroPdf417 en C#, **Aspose Barcode Generator C#** ofrece una API concisa que maneja tanto la imagen del código de barras como los metadatos macro requeridos. Este tutorial te muestra exactamente cómo añadir información macro y generar una imagen de código de barras PDF417 en solo unos pocos pasos.

Aprenderás a configurar parámetros visuales, incrustar campos macro como el ID de archivo y la marca de tiempo, y guardar el resultado como PNG. No se requieren herramientas externas, solo la biblioteca Aspose.BarCode y un entorno de desarrollo .NET.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* .NET 6.0 o posterior instalado  
* Visual Studio 2022 (o cualquier IDE de C#)  
* Una copia con licencia o de evaluación de **Aspose.BarCode for .NET**  

El código funciona en Windows, Linux y macOS porque la biblioteca es independiente de la plataforma.

## Paso 1: Instalar el paquete NuGet Aspose.BarCode

Abre tu proyecto en Visual Studio y ejecuta el siguiente comando en la **Package Manager Console**:

```powershell
Install-Package Aspose.BarCode
```

Esto agrega el ensamblado `Aspose.BarCode` y sus dependencias a tu proyecto.

## Paso 2: Crear la instancia del generador de códigos de barras

La primera línea crea un objeto `BarcodeGenerator` para la simbología **MacroPdf417** y suministra el texto que deseas codificar.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

// Step 2: Initialise the generator with MacroPdf417 and the payload text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // subsequent configuration goes here
}
```

*Por qué es importante*: El valor `EncodeTypes.MacroPdf417` indica a la biblioteca que espere campos relacionados con macro, que establecerás en el siguiente paso.

## Paso 3: Definir la apariencia visual

Puedes controlar el tamaño de cada módulo (el cuadrado negro o blanco más pequeño) y el número de columnas en la matriz PDF417. Ajustar `XDimension` influye en la resolución general de la imagen.

```csharp
    // Step 3: Visual settings
    generator.Parameters.Barcode.XDimension.Pixels = 2;          // width of a single module
    generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol
```

Aumentar `Columns` reduce la altura del código de barras, mientras que una `XDimension` mayor hace que la imagen sea más nítida en pantallas de alta DPI.

## Paso 4: Añadir metadatos macro (cómo añadir macro)

MacroPdf417 requiere varios campos adicionales que describen el archivo origen y su segmentación. Las siguientes propiedades se asignan directamente a las especificaciones macro de PDF417:

```csharp
    // Step 4: Macro fields – how to add macro data
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;               // unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;                  // current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;              // total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";             // optional file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                // CCITT‑16 placeholder
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                   // creation timestamp
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";            // recipient identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";               // sender identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                   // marks the last segment
```

*Por qué estos campos*:  
* `MacroPdf417FileID` une todos los segmentos, garantizando que un escáner pueda volver a ensamblar el documento original.  
* `MacroPdf417SegmentID` y `MacroPdf417SegmentsCount` permiten al decodificador conocer el orden y el número total de partes.  
* `MacroPdf417FileSize` y `MacroPdf417Checksum` proporcionan verificaciones de integridad, útiles para transferencias de datos grandes.

## Paso 5: Guardar la imagen del código de barras (cómo generar pdf417)

Finalmente, escribe el código de barras en disco. El método `Save` acepta una ruta de archivo y un formato de imagen. PNG conserva los bordes nítidos del código de barras sin artefactos de compresión.

```csharp
    // Step 5: Save the generated barcode – how to generate pdf417 image
    generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

Cuando el programa se ejecute, encontrarás **ExtPDF417Meta.png** en la carpeta de salida. Abrir la imagen muestra un código de barras MacroPdf417 limpio, listo para imprimir o incrustar en un PDF.

### Salida esperada

| Nombre de archivo   | Formato | Dimensiones (aprox.) |
|---------------------|---------|----------------------|
| ExtPDF417Meta.png  | PNG     | 300 × 150 px (varía con `XDimension`) |

Escanear la imagen con un lector compatible con PDF417 (p. ej., ZXing, Aspose.BarCode for .NET) devuelve el texto original **“Åspóse.Barcóde©”** junto con todos los campos macro.

## Problemas comunes y cómo evitarlos

| Problema | Por qué ocurre | Solución |
|----------|----------------|----------|
| **Incorrect `EncodeTypes`** | Usar `EncodeTypes.Pdf417` en lugar de `EncodeTypes.MacroPdf417` desactiva los campos macro. | Siempre instancie el generador con `EncodeTypes.MacroPdf417`. |
| **Missing macro fields** | Algunos escáneres ignoran el código de barras si se omiten los campos macro requeridos. | Complete al menos `FileID`, `SegmentID`, `SegmentsCount` y `Terminator`. |
| **Too small `XDimension`** | Un valor inferior a 1 píxel puede producir un código de barras ilegible en pantallas de baja resolución. | Mantenga `XDimension` ≥ 2 píxeles para la mayoría de escenarios de pantalla e impresión. |
| **File path errors** | Proporcionar una ruta relativa que no exista lanza una excepción. | Use `Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png")` o una ruta absoluta. |

## Código fuente completo

A continuación tienes el ejemplo completo y ejecutable que puedes copiar en un nuevo proyecto de consola.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with MacroPdf417 and the payload text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Visual appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns

                // Macro fields – how to add macro
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save the barcode – how to generate pdf417
                generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("MacroPdf417 barcode generated successfully.");
        }
    }
}
```

Ejecuta el programa (`dotnet run`). Después de la ejecución, la consola muestra un mensaje de éxito y el archivo PNG aparece en la carpeta de salida del proyecto.

## Próximos pasos

* **Encode larger data** – Increase `Columns` or adjust `Rows` (via `Pdf417.Rows`) to fit more characters.  
* **Embed in PDF** – Use Aspose.PDF to place the generated PNG into a document.  
* **Scan verification** – Leverage `Aspose.BarCode.Reader` to decode the barcode and confirm macro fields programmatically.  

Explorar estos temas profundiza tu comprensión de **how to generate PDF417** barcodes con información macro enriquecida y te prepara para casos de uso reales como procesamiento por lotes de documentos o intercambio seguro de datos.

---

*¡Feliz codificación! Si encontraste útil esta guía, considera compartirla con tus compañeros o darle una estrella al repositorio Aspose.BarCode en GitHub.*

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo crear un código de barras macro PDF417 en C# usando Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Cómo generar un código de barras PDF417 en C# con Barcode Generator](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcode-generator/)
- [Ejemplo de Aspose barcode: generar Macro PDF417 en C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}