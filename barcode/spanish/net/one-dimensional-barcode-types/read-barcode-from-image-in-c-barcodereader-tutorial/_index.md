---
category: general
date: 2026-08-15
description: Leer código de barras de una imagen en C# usando BarCodeReader. Aprende
  cómo leer varios códigos de barras en C#, leer códigos de barras PDF417 y ver un
  ejemplo completo de BarCodeReader en C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image
- read multiple barcodes c#
- how to read pdf417 barcode
- c# barcodereader example
language: es
lastmod: 2026-08-15
og_description: Lee códigos de barras desde una imagen en C# con una guía paso a paso.
  Descubre cómo leer múltiples códigos de barras en C#, decodificar símbolos PDF417
  y ejecutar un ejemplo completo de BarCodeReader en C#.
og_image_alt: Screenshot of C# code that reads barcode from image using BarCodeReader
og_title: Leer código de barras de una imagen en C# – Tutorial de BarCodeReader
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Read barcode from image in C# using BarCodeReader. Learn how to read
    multiple barcodes C#, read PDF417 barcode, and see a full C# BarCodeReader example.
  headline: Read barcode from image in C# – BarCodeReader tutorial
  type: TechArticle
tags:
- barcode
- C#
- .NET
- image processing
title: Leer código de barras de una imagen en C# – tutorial de BarCodeReader
url: /es/net/one-dimensional-barcode-types/read-barcode-from-image-in-c-barcodereader-tutorial/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Leer código de barras desde una imagen en C# – tutorial de BarCodeReader

Si necesitas **leer código de barras desde una imagen** en una aplicación .NET, esta guía te muestra exactamente cómo hacerlo con la clase `BarCodeReader`. También verás cómo **leer varios códigos de barras C#**, decodificar un símbolo PDF417 y obtener un **ejemplo completo de C# BarCodeReader** que puedes copiar en tu proyecto.

El tutorial cubre cada paso—desde agregar el paquete NuGet requerido hasta imprimir los campos extendidos de PDF417—para que termines con un programa de consola ejecutable. No se necesita documentación externa; todo el código y las explicaciones están incluidas.

## Lo que necesitarás

* .NET 6.0 SDK o posterior (el código funciona con .NET Core y .NET Framework)
* Visual Studio 2022 o cualquier editor compatible con C#
* El paquete NuGet `Aspose.BarCode` (o la biblioteca equivalente que proporciona `BarCodeReader`)
* Un archivo de imagen que contenga un código de barras Macro PDF417 (p. ej., `ExtPDF417Meta.png`)

Tener estos requisitos previos garantiza que el ejemplo compile sin configuración adicional.

## Leer código de barras desde una imagen con BarCodeReader

El primer paso es crear una instancia de `BarCodeReader` que apunte al archivo de imagen y le indique a la biblioteca qué tipo de código de barras buscar.

```csharp
using System;
using Aspose.BarCode;               // Namespace for BarCodeReader
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // Path to the image that holds the Macro PDF417 barcode
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417 barcodes only
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Read all barcodes present in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Basic barcode information
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");

                // Extended Macro PDF417 fields (available only for this type)
                Console.WriteLine($"File ID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name        : {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum         : {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Time Stamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee        : {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender           : {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator Flag  : {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**Por qué esto funciona:**  
`BarCodeReader` abre la imagen, escanea el `DecodeType` especificado y devuelve una colección de objetos `BarCodeResult`. Cada resultado contiene los datos genéricos del código de barras (`CodeTypeName`, `CodeText`) y, para Macro PDF417, un objeto `Extended.Pdf417` que expone todos los campos adicionales definidos por el estándar.

## Leer varios códigos de barras C# en una sola imagen

A veces una imagen contiene más de un código de barras (p. ej., un código QR junto a un PDF417). Para manejar ese escenario, simplemente omite el `DecodeType` explícito o pasa `DecodeType.AllSupported` y recorre los resultados.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Found {result.CodeTypeName}: {result.CodeText}");
    }
}
```

**Por qué necesitas esto:**  
Especificar `AllSupported` indica al motor que pruebe todos los formatos de código de barras que conoce, lo que garantiza que captures cada símbolo en la imagen. Este es el enfoque recomendado cuando no puedes predecir los tipos de códigos de barras de antemano.

## Cómo leer códigos de barras PDF417 usando C#

Si solo te interesa el formato clásico PDF417 (no macro), cambia el `DecodeType` a `Pdf417`. El resto del código permanece idéntico, excepto que los campos extendidos no están disponibles.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"PDF417 text: {result.CodeText}");
    }
}
```

**Por qué esto es importante:**  
El PDF417 clásico no expone las propiedades específicas del macro, por lo que el bloque `Extended.Pdf417` no es necesario. Usar el `DecodeType` preciso también acelera el escaneo porque la biblioteca omite algoritmos no compatibles.

## Ejemplo completo de C# BarCodeReader que puedes copiar

A continuación se muestra el programa completo que combina los tres escenarios en una única aplicación de consola fácil de ejecutar. Reemplaza `YOUR_DIRECTORY/ExtPDF417Meta.png` con la ruta real a tu imagen.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 1️⃣ Read Macro PDF417 and show extended fields
        Console.WriteLine("=== Macro PDF417 ===");
        ReadMacroPdf417(imagePath);

        // 2️⃣ Read any barcode type present (multiple barcodes)
        Console.WriteLine("\n=== All supported barcodes ===");
        ReadAllBarcodes(imagePath);

        // 3️⃣ Read classic PDF417 only
        Console.WriteLine("\n=== Classic PDF417 ===");
        ReadClassicPdf417(imagePath);
    }

    static void ReadMacroPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");
                Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                // ... other extended fields omitted for brevity
                Console.WriteLine(new string('-', 30));
            }
        }
    }

    static void ReadAllBarcodes(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.AllSupported))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"{result.CodeTypeName}: {result.CodeText}");
            }
        }
    }

    static void ReadClassicPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.Pdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"PDF417 text: {result.CodeText}");
            }
        }
    }
}
```

### Salida esperada

Cuando la imagen de ejemplo contiene un código de barras Macro PDF417, la consola imprime algo similar a:

```
=== Macro PDF417 ===
Code Type : MacroPdf417
Code Text : 1234567890
File ID   : 5
Segment ID       : 2
Segments Count   : 3
File Name        : report.pdf
Checksum         : 0x1A2B
File Size        : 84212
Time Stamp       : 2024-03-15T10:22:31Z
Addressee        : John Doe
Sender           : Acme Corp
Terminator Flag  : True
------------------------------

=== All supported barcodes ===
MacroPdf417: 1234567890
QrCode: https://example.com

=== Classic PDF417 ===
PDF417 text: 0987654321
```

Si la imagen contiene solo un PDF417 regular, la sección “Macro PDF417” estará vacía y la sección “Classic PDF417” mostrará el texto decodificado.

## Conclusión

Ahora sabes cómo **leer código de barras desde una imagen** en C# usando `BarCodeReader`, cómo **leer varios códigos de barras C#** en un solo archivo, y los pasos exactos para **leer códigos de barras PDF417**—tanto en sus variantes macro como clásicas. El **ejemplo completo de C# BarCodeReader** está listo para pegar en cualquier proyecto .NET, y puedes ampliarlo para manejar otros formatos o integrarlo en una canalización de procesamiento de imágenes más grande.

**Próximos pasos**

* Explora patrones de manejo de errores como `try / catch` alrededor del bloque del lector.  
* Experimenta con el objeto `ReaderParameters` para ajustar la velocidad y precisión de la detección.  
* Combina la lectura de códigos de barras con bibliotecas de preprocesamiento de imágenes (

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo leer códigos de barras DataMatrix con Aspose.BarCode para .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Leer código de barras DataMatrix C# – Generar modo DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Leer código de barras desde una imagen – Dominio de la extracción de región de código de barras en Java con Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}