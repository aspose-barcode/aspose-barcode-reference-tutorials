---
category: general
date: 2026-08-03
description: Leer código de barras PDF417 de una imagen usando C# BarCodeReader –
  un ejemplo completo de lector de códigos de barras que también muestra cómo leer
  múltiples códigos de barras.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read PDF417 barcode
- barcode reader example
- read multiple barcodes
- read barcodes image
language: es
lastmod: 2026-08-03
og_description: Lea rápidamente códigos de barras PDF417 con un ejemplo de BarCodeReader
  en C#. Siga esta guía paso a paso para decodificar macro PDF417 y leer varios códigos
  de barras de una imagen.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: Leer código de barras PDF417 en C# – ejemplo completo de lector de códigos
  de barras
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  headline: Read PDF417 barcode in C# – barcode reader example
  type: TechArticle
- description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  name: Read PDF417 barcode in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
title: Leer código de barras PDF417 en C# – ejemplo de lector de códigos de barras
url: /es/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Leer código de barras PDF417 en C# – ejemplo de lector de códigos de barras

Si necesitas leer datos de códigos de barras PDF417 a partir de una imagen, esta guía te muestra cómo hacerlo con la clase **BarCodeReader** en C#. Aprenderás un ejemplo de lector de códigos de barras que también maneja macro PDF417 y puede leer múltiples códigos de barras en una sola imagen.

Trabajar con códigos de barras a menudo implica lidiar con diferentes fuentes de imágenes, condiciones de iluminación variables y, a veces, datos compuestos como segmentos macro PDF417. Este tutorial cubre todo lo que necesitas para decodificar un código de barras PDF417, extraer sus campos extendidos y procesar varios códigos de barras de la misma foto. Al final tendrás un programa de consola ejecutable que lee códigos de barras de un archivo de imagen y muestra información detallada en la consola.

## Lo que necesitarás

Antes de comenzar, asegúrate de tener:

* SDK de .NET 6.0 o posterior instalado  
* Una versión reciente del paquete NuGet **Aspose.BarCode for .NET** (o cualquier biblioteca compatible que proporcione `BarCodeReader` y `DecodeType.MacroPdf417`)  
* Un archivo de imagen que contenga un código de barras PDF417 o macro PDF417 (el ejemplo usa `ExtPDF417Meta.png`)  
* Un editor de código o IDE como Visual Studio 2022  

No se requieren servicios adicionales ni APIs externas.

## Configuración del proyecto para la lectura de códigos de barras

1. **Crear un nuevo proyecto de consola**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **Agregar la biblioteca de códigos de barras**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **Copiar la imagen del código de barras**  

   Coloca `ExtPDF417Meta.png` (o cualquier imagen que contenga un código de barras PDF417) en la carpeta del proyecto.  
   Para este tutorial asumimos que el archivo se encuentra en `YOUR_DIRECTORY/ExtPDF417Meta.png`.

El proyecto ya está listo para compilar y ejecutar el ejemplo de lector de códigos de barras.

## Cómo leer códigos de barras PDF417 con BarCodeReader

El núcleo de la solución es un bloque `using` que crea una instancia de `BarCodeReader`, especifica `DecodeType.MacroPdf417` y recorre cada código de barras detectado. El siguiente código es un programa completo y autónomo que puedes pegar en `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
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

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**Por qué funciona**:  

* `DecodeType.MacroPdf417` indica al lector que busque la extensión macro de PDF417, que lleva metadatos adicionales como ID de archivo, recuento de segmentos y marcas de tiempo.  
* La instrucción `using` garantiza que los recursos no administrados (manejadores de archivo, búferes nativos de decodificación) se liberen rápidamente.  
* El bucle `foreach` procesa automáticamente **todos** los códigos de barras que contiene la imagen, cumpliendo el requisito de *leer múltiples códigos de barras*.  

Cuando ejecutes el programa (`dotnet run`), deberías ver una salida similar a la siguiente:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

Si la imagen contiene más de un código de barras PDF417, el bucle imprime un bloque separado para cada código, demostrando así cómo **leer múltiples códigos de barras** de una sola imagen.

## Lectura de múltiples códigos de barras desde una imagen

La misma instancia de `BarCodeReader` puede decodificar varios tipos de códigos de barras a la vez. Para ampliar el alcance más allá del macro PDF417 a cualquier PDF417 (o incluso QR, Code128, etc.), ajusta la bandera `DecodeType`:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* es una máscara de bits, por lo que puedes combinar cualquier número de formatos compatibles. Esta flexibilidad convierte el fragmento en un **ejemplo de lector de códigos de barras** que funciona para una amplia variedad de casos de uso, como escanear etiquetas de productos, boletos o tarjetas de identificación.

## Accediendo a los campos macro PDF417 de forma segura

Macro PDF417 añade un conjunto rico de propiedades extendidas. Sin embargo, no todos los códigos de barras incluyen cada campo. Acceder a una propiedad inexistente puede lanzar una `NullReferenceException`. El enfoque más seguro es verificar cada propiedad antes de imprimirla:

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*Por qué es importante*: En implementaciones del mundo real puedes recibir códigos de barras PDF417 simples que carecen de datos macro. La verificación defensiva asegura que tu aplicación continúe ejecutándose sin fallos.

## Errores comunes y mejores prácticas

| Problema | Por qué ocurre | Solución recomendada |
|----------|----------------|----------------------|
| La ruta de la imagen es incorrecta | `BarCodeReader` lanza una excepción de archivo no encontrado antes de que ocurra cualquier decodificación | Usa `Path.Combine` y valida que el archivo exista con `File.Exists` |
| Imagen de baja resolución | El decodificador no puede localizar los bordes del código de barras, resultando en cero detecciones | Proporciona una resolución mínima de 300 dpi para obtener resultados fiables |
| Código de barras rotado > 45° | Muchas bibliotecas asumen una orientación vertical | Habilita `reader.RecognitionOptions.RotateImage = true` si el |

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo leer códigos de barras DataMatrix con Aspose.BarCode para .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Leer código de barras DataMatrix C# – Generar modo DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Leer código de barras desde una imagen – Dominando la extracción de región de código de barras en Java con Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}