---
category: general
date: 2026-10-28
description: Cómo generar códigos de barras con texto personalizado usando Aspose.BarCode
  – guía paso a paso para desarrolladores .NET para crear imágenes de códigos de barras
  con Aspose.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- generate barcode custom text
- create barcode aspose
language: es
lastmod: 2026-10-28
og_description: Cómo generar código de barras con texto personalizado en .NET usando
  Aspose.BarCode. Sigue esta guía completa para crear y guardar un código de barras
  Macro PDF417.
og_image_alt: how to generate barcode example PNG image showing a Macro PDF417 barcode
og_title: Cómo generar un código de barras con texto personalizado – tutorial de Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: How to generate barcode with custom text using Aspose.BarCode – step‑by‑step
    guide for .NET developers to create barcode Aspose images.
  headline: How to generate barcode with custom text using Aspose.BarCode for .NET
  type: TechArticle
- description: How to generate barcode with custom text using Aspose.BarCode – step‑by‑step
    guide for .NET developers to create barcode Aspose images.
  name: How to generate barcode with custom text using Aspose.BarCode for .NET
  steps:
  - name: Why each line matters
    text: '* **EncodeTypes.MacroPdf417** – selects the Macro PDF417 symbology, which
      supports segmented data and metadata. * **XDimension.Pixels** – controls the
      size of each module; a value of 2 pixels yields a clear, scannable image. *
      **Pdf417.Columns** – reduces the overall width, making the barcode more c'
  - name: Using a different barcode type
    text: If you need to **generate barcode custom text** for a QR code instead of
      Macro PDF417, replace `EncodeTypes.MacroPdf417` with `EncodeTypes.QR`. The rest
      of the parameter structure stays the same, but QR codes do not support Macro
      metadata fields.
  - name: Handling Unicode characters
    text: The example already includes Unicode characters (`Å`, `ó`, `©`). Aspose.BarCode
      handles UTF‑8 input out of the box, but you should ensure the source file is
      saved with UTF‑8 encoding to avoid compile‑time warnings.
  - name: Saving to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG in addition to PNG. Change
      the `BarCodeImageFormat` enum value accordingly:'
  - name: Large data sets
    text: Macro PDF417 can split data across multiple segments. When the text exceeds
      the capacity of a single segment, increment `MacroPdf417SegmentID` and keep
      `MacroPdf417SegmentsCount` consistent across all generated parts. This approach
      is essential for **create barcode aspose** scenarios where the paylo
  - name: Error handling
    text: 'Wrap the generation logic in a try‑catch block to surface runtime issues
      such as invalid file paths or unsupported characters:'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- .NET
title: Cómo generar un código de barras con texto personalizado usando Aspose.BarCode
  para .NET
url: /es/net/one-dimensional-barcode-types/how-to-generate-barcode-with-custom-text-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo generar un código de barras con texto personalizado usando Aspose.BarCode para .NET

Generar un código de barras con texto personalizado es un requisito frecuente cuando necesitas incrustar identificadores, marcas de tiempo u otros metadatos directamente en un código visual. Este tutorial te muestra cómo generar un código de barras Macro PDF417 que lleva texto personalizado y un conjunto completo de metadatos, usando la biblioteca **Aspose.BarCode** para .NET.

Aprenderás cómo configurar el generador, aplicar texto personalizado, establecer los campos específicos de Macro PDF417 y guardar el resultado como una imagen PNG. No se requieren herramientas externas, solo el paquete NuGet Aspose.BarCode y un entorno de desarrollo .NET.

## Requisitos previos

* SDK .NET 6.0 o posterior instalado  
* Visual Studio 2022 (o cualquier IDE que soporte .NET)  
* Paquete NuGet **Aspose.BarCode for .NET** (`Install-Package Aspose.BarCode`)  

Estos requisitos previos garantizan que el código compile y se ejecute sin configuración adicional.

## Paso 1: Instalar el paquete Aspose.BarCode

Abre una terminal en la carpeta de tu proyecto y ejecuta:

```bash
dotnet add package Aspose.BarCode
```

El comando agrega la última versión estable de Aspose.BarCode a tu proyecto, dándote acceso a la clase `BarcodeGenerator` y a todos los parámetros relacionados.

## Paso 2: Crear una nueva aplicación de consola

Crea una aplicación de consola mínima que alojará la lógica de generación del código de barras:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The full barcode generation flow is encapsulated in a separate method
            GenerateMacroPdf417Barcode();
        }

        /// <summary>
        /// Generates a Macro PDF417 barcode with custom text and metadata, then saves it as PNG.
        /// </summary>
        private static void GenerateMacroPdf417Barcode()
        {
            // Step 1: Instantiate the generator with the desired encode type and data
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the visual appearance of the barcode
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // Size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;            // Number of columns in the symbol

                // Step 3: Populate Macro PDF417 specific metadata fields
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example value
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the barcode image to disk
                string outputPath = @"ExtPDF417Meta.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode saved to {outputPath}");
            }
        }
    }
}
```

### Por qué cada línea es importante

* **EncodeTypes.MacroPdf417** – selecciona la simbología Macro PDF417, que soporta datos segmentados y metadatos.  
* **XDimension.Pixels** – controla el tamaño de cada módulo; un valor de 2 píxeles produce una imagen clara y escaneable.  
* **Pdf417.Columns** – reduce el ancho total, haciendo el código de barras más compacto para etiquetas impresas.  
* **MacroPdf417* properties** – incrusta información a nivel de archivo (ID, recuento de segmentos, marcas de tiempo, etc.) directamente en el código de barras. Esta capacidad es única de Macro PDF417 y se usa frecuentemente en logística o sistemas de gestión documental.  
* **Save(..., BarCodeImageFormat.Png)** – escribe un archivo PNG sin pérdida, preservando los bordes nítidos del código de barras para un escaneo fiable.

## Paso 3: Ejecutar el programa y verificar la salida

Compila y ejecuta la aplicación de consola:

```bash
dotnet run
```

El programa crea `ExtPDF417Meta.png` en el directorio de trabajo del proyecto. Al abrir el archivo se muestra un código de barras Macro PDF417 que codifica el texto **“Åspóse.Barcóde©”** junto con los metadatos que proporcionaste.

**Salida esperada** – una imagen PNG similar a la que se muestra a continuación:

![ejemplo de salida de generación de código de barras imagen PNG que muestra un código de barras Macro PDF417](ExtPDF417Meta.png)

*El texto alternativo de la imagen (“ejemplo de salida de generación de código de barras imagen PNG”) refuerza la palabra clave principal para accesibilidad y SEO.*

## Variaciones comunes y casos límite

### Usar un tipo de código de barras diferente

Si necesitas **generar código de barras con texto personalizado** para un código QR en lugar de Macro PDF417, reemplaza `EncodeTypes.MacroPdf417` por `EncodeTypes.QR`. El resto de la estructura de parámetros permanece igual, pero los códigos QR no soportan campos de metadatos Macro.

### Manejo de caracteres Unicode

El ejemplo ya incluye caracteres Unicode (`Å`, `ó`, `©`). Aspose.BarCode maneja la entrada UTF‑8 de forma nativa, pero debes asegurarte de que el archivo fuente se guarde con codificación UTF‑8 para evitar advertencias en tiempo de compilación.

### Guardar en otros formatos de imagen

Aspose.BarCode soporta BMP, JPEG, TIFF y SVG además de PNG. Cambia el valor del enum `BarCodeImageFormat` según corresponda:

```csharp
generator.Save("barcode.svg", BarCodeImageFormat.Svg);
```

### Conjuntos de datos grandes

Macro PDF417 puede dividir los datos en varios segmentos. Cuando el texto supera la capacidad de un solo segmento, incrementa `MacroPdf417SegmentID` y mantén `MacroPdf417SegmentsCount` consistente en todas las partes generadas. Este enfoque es esencial para escenarios de **create barcode aspose** donde la carga útil es mayor que la que puede contener un solo código de barras.

### Manejo de errores

Envuelve la lógica de generación en un bloque try‑catch para exponer problemas en tiempo de ejecución, como rutas de archivo no válidas o caracteres no soportados:

```csharp
try
{
    GenerateMacroPdf417Barcode();
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Barcode generation failed: {ex.Message}");
}
```

## Consejos profesionales para una generación fiable de códigos de barras

* **Validar el código de barras** después de crearlo usando `BarCodeReader`. Este paso adicional confirma que los datos codificados coinciden con tus expectativas.

  ```csharp
  using (BarCodeReader reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.MacroPdf417))
  {
      if (reader.Read())
          Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
  }
  ```

* **Mantén la X‑dimension entre 2 – 4 píxeles** para la mayoría de los escáneres. Valores menores pueden producir imágenes ilegibles en dispositivos de baja resolución.

* **Evita nombres de archivo muy largos** en `MacroPdf417FileName`. La especificación limita el campo a 32 caracteres.

* **Utiliza marcas de tiempo consistentes** (UTC) al generar múltiples segmentos para simplificar el procesamiento posterior.

## Conclusión

Ahora sabes **cómo generar un código de barras** con texto personalizado usando Aspose.BarCode para .NET, cómo configurar los metadatos de Macro PDF417 y cómo guardar el resultado como una imagen PNG. El ejemplo completo y ejecutable muestra cada paso necesario, desde la instalación del paquete NuGet hasta el manejo de caracteres Unicode y el guardado de la salida.

Desde aquí puedes:

* **Generar código de barras con texto personalizado** para otras simbologías (QR, DataMatrix, etc.)  
* **Crear flujos de trabajo de barcode Aspose** que procesen por lotes miles de imágenes  
* Integrar el código de generación de códigos de barras en servicios ASP.NET Core, servicios de Windows o Azure Functions  

¡Experimenta con diferentes parámetros, explora campos de metadatos adicionales e incorpora el código de barras en tus canalizaciones de automatización de documentos! ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo crear un código de barras PDF417 con Aspose – Guía completa paso a paso](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Generar código de barras a partir de texto usando Aspose.BarCode – Guía C#](/barcode/english/net/one-dimensional-barcode-types/generate-barcode-from-text-using-aspose-barcode-c-guide/)
- [Cómo usar Aspose.BarCode para crear texto de código DataMatrix en .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}