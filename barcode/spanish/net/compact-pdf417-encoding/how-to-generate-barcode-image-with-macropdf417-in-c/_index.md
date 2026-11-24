---
category: general
date: 2026-11-23
description: Aprende a generar una imagen de código de barras usando Aspose.BarCode
  para .NET con metadatos MacroPdf417 en C#. Sigue la guía completa paso a paso.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode image
- MacroPdf417 barcode
- Aspose.BarCode for .NET
- set barcode metadata
- barcode image format
- C# barcode generation
language: es
lastmod: 2026-11-23
og_description: Cómo generar una imagen de código de barras usando Aspose.BarCode
  para .NET. Este tutorial muestra la configuración de metadatos MacroPdf417 y la
  generación de códigos de barras en C#.
og_image_alt: Barcode image generated with MacroPdf417 using C#
og_title: Cómo generar una imagen de código de barras con MacroPdf417 en C#
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to generate barcode image using Aspose.BarCode for .NET with
    MacroPdf417 metadata in C#. Follow the complete step‑by‑step guide.
  headline: How to generate barcode image with MacroPdf417 in C#
  type: TechArticle
- description: Learn how to generate barcode image using Aspose.BarCode for .NET with
    MacroPdf417 metadata in C#. Follow the complete step‑by‑step guide.
  name: How to generate barcode image with MacroPdf417 in C#
  steps:
  - name: Open a terminal or the Package Manager Console in Visual Studio.
    text: Open a terminal or the Package Manager Console in Visual Studio.
  - name: 'Run the following command:'
    text: 'Run the following command:'
  - name: '**Visual inspection** – The barcode should display a series of stacked
      columns with a quiet zone (white margin) around it.'
    text: '**Visual inspection** – The barcode should display a series of stacked
      columns with a quiet zone (white margin) around it.'
  - name: '**Decoding test** – Use a barcode scanner app or the Aspose.BarCode `BarCodeReader`
      class to read the image back and confirm that all metadata fields are correctly
      embedded.'
    text: '**Decoding test** – Use a barcode scanner app or the Aspose.BarCode `BarCodeReader`
      class to read the image back and confirm that all metadata fields are correctly
      embedded.'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- PDF417
title: Cómo generar una imagen de código de barras con MacroPdf417 en C#
url: /es/net/compact-pdf417-encoding/how-to-generate-barcode-image-with-macropdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo generar una imagen de código de barras con MacroPdf417 en C#

Si necesita **generar una imagen de código de barras** en una aplicación .NET, esta guía le muestra exactamente cómo hacerlo con **Aspose.BarCode for .NET**. Vamos a recorrer la creación de un **código de barras MacroPdf417**, configurar sus metadatos y guardar el resultado como un archivo PNG.

Este tutorial cubre todo, desde la instalación de la biblioteca hasta la escritura de un programa de consola completo y ejecutable. Al final tendrá una muestra de código lista para usar que produce una imagen de código de barras de alta calidad, y comprenderá cómo **establecer metadatos del código de barras**, elegir un **formato de imagen del código de barras** y solucionar problemas comunes. No se requiere experiencia previa con Aspose, solo un conocimiento básico de C#.

## Instalar Aspose.BarCode para .NET

Antes de poder **generar una imagen de código de barras**, necesita el paquete NuGet de Aspose.BarCode.

1. Abra una terminal o la Consola del Administrador de paquetes en Visual Studio.  
2. Ejecute el siguiente comando:

```bash
dotnet add package Aspose.BarCode
```

El paquete agrega el espacio de nombres `Aspose.BarCode.Generation`, que contiene la clase `BarcodeGenerator` utilizada para la **generación de códigos de barras en C#**.

> **Consejo profesional:** Use la última versión estable (a partir de noviembre 2026 la versión actual es 24.11) para obtener las funciones más recientes y correcciones de errores.

## Crear la instancia de BarcodeGenerator

El primer paso de código crea un `BarcodeGenerator` configurado para el tipo de **código de barras MacroPdf417** y proporciona la cadena de datos que desea codificar.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a BarcodeGenerator for MacroPdf417 with the desired text
            using (BarcodeGenerator barcodeGenerator =
                   new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Subsequent configuration goes here...
```

El bloque `using` garantiza que el generador se elimine correctamente, liberando cualquier recurso no administrado.

## Configurar apariencia básica

Un código de barras legible comienza con dimensiones sensatas. Aquí establecemos el ancho en píxeles de cada módulo (`XDimension`) y el número de columnas para la matriz PDF417.

```csharp
                // Step 2: Set basic barcode appearance
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel width of a module
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

*¿Por qué estos valores?*  
- **XDimension** controla cuán gruesa aparece cada barra; 2 píxeles funciona bien para la visualización en pantalla y la mayoría de impresoras.  
- **Columns** afecta el ancho total; un número pequeño de columnas mantiene el código de barras compacto mientras preserva la capacidad de corrección de errores.

## Establecer metadatos del código de barras (específico de MacroPdf417)

MacroPdf417 le permite incrustar información a nivel de archivo directamente en el código de barras. Aquí es donde **establece metadatos del código de barras** como ID de archivo, ID de segmento y marcas de tiempo.

```csharp
                // Step 3: Configure MacroPdf417 specific metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### Qué significa cada propiedad

| Propiedad | Propósito |
|----------|-----------|
| **MacroPdf417FileID** | Identificador único para el archivo lógico al que pertenece el código de barras. |
| **MacroPdf417SegmentID** | Índice del segmento actual (basado en 0). |
| **MacroPdf417SegmentsCount** | Número total de segmentos que componen el archivo completo. |
| **MacroPdf417FileName** | Nombre legible por humanos del archivo fuente. |
| **MacroPdf417Checksum** | Suma de verificación CCITT‑16 opcional para la verificación de integridad de datos. |
| **MacroPdf417FileSize** | Tamaño esperado del archivo original en bytes. |
| **MacroPdf417TimeStamp** | Fecha y hora en que se generó el código de barras – útil para el seguimiento de versiones. |
| **MacroPdf417Addressee / Sender** | Cadenas personalizadas que pueden contener información de enrutamiento. |
| **MacroPdf417Terminator** | Indica si este segmento es el final (`Set`) o no (`Unset`). |

> **Caso límite:** Si planea dividir un documento grande en muchos segmentos, mantenga el `SegmentsCount` consistente en todos los códigos de barras generados. Los recuentos que no coincidan provocarán fallas en la decodificación.

## Elegir el formato de imagen del código de barras y guardar

Aspose admite muchos **formatos de imagen de código de barras** (PNG, JPEG, BMP, TIFF, etc.). PNG es sin pérdida y funciona bien para la mayoría de escenarios web e impresión.

```csharp
                // Step 4: Save the generated barcode image
                string outputPath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode image saved to: {outputPath}");
            } // end using
        }
    }
}
```

Reemplace `YOUR_DIRECTORY` con una carpeta absoluta o relativa donde la aplicación tenga permiso de escritura.

Cuando el programa se ejecute, debería ver un mensaje en la consola confirmando la ubicación del archivo. Abra el archivo PNG con cualquier visor de imágenes; verá un nítido **código de barras MacroPdf417** que codifica el texto suministrado y los metadatos que definió.

### Salida esperada

```
Barcode image saved to: C:\Projects\BarcodeDemo\ExtPDF417Meta.png
```

El tamaño del archivo de imagen será aproximadamente 30‑40 KB, dependiendo del `XDimension` y el número de columnas elegidos.

## Verificar el código de barras y solucionar problemas

1. **Inspección visual** – El código de barras debe mostrar una serie de columnas apiladas con una zona silenciosa (margen blanco) a su alrededor.  
2. **Prueba de decodificación** – Use una aplicación escáner de códigos de barras o la clase `BarCodeReader` de Aspose.BarCode para leer la imagen y confirmar que todos los campos de metadatos están incrustados correctamente.  



## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarle a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en sus propios proyectos.

- [Generar imagen de código de barras PDF417 con Aspose.BarCode en C# – guía paso a paso](/barcode/english/net/compact-pdf417-encoding/how-to-create-barcode-image-with-pdf417-in-c-step-by-step-gu/)
- [Cómo generar un código de barras con texto personalizado usando Aspose.BarCode para .NET](/barcode/english/net/one-dimensional-barcode-types/how-to-generate-barcode-with-custom-text-using-aspose-barcod/)
- [Cómo leer códigos de barras de una imagen usando C# con Aspose.BarCode – guía paso a paso](/barcode/english/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}