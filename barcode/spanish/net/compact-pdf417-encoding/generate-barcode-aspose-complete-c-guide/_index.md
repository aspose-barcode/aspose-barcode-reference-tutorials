---
category: general
date: 2026-08-12
description: Genera códigos de barras con Aspose usando Aspose.BarCode y aprende a
  generar PDF417 con texto personalizado en unos pocos pasos fáciles.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode aspose
- how to generate pdf417
- create barcode custom text
- Aspose.BarCode macro pdf417
- barcode metadata Aspose
language: es
lastmod: 2026-08-12
og_description: Generar código de barras Aspose usando Aspose.BarCode. Este tutorial
  muestra cómo generar PDF417 con texto personalizado, metadatos de macro y guardar
  el resultado como PNG.
og_image_alt: Screenshot of a MacroPdf417 barcode generated with Aspose.BarCode in
  C#
og_title: Generar código de barras aspose – guía paso a paso
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Generate barcode aspose with Aspose.BarCode and learn how to generate
    pdf417 with custom text in a few easy steps.
  headline: Generate barcode aspose – complete C# guide
  type: TechArticle
tags:
- Aspose
- barcode
- pdf417
title: Generar código de barras Aspose – guía completa de C#
url: /es/net/compact-pdf417-encoding/generate-barcode-aspose-complete-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generar código de barras aspose – guía completa en C#

Si necesitas **generar código de barras aspose** para un símbolo MacroPdf417, este tutorial te guía a través de todo el proceso. Verás cómo configurar opciones específicas de macro, incrustar texto personalizado y guardar el código de barras como una imagen PNG.

Generar un código de barras con Aspose.BarCode elimina los cálculos manuales y garantiza el cumplimiento de la especificación PDF417. En los pasos siguientes también aprenderás **cómo generar pdf417** con metadatos personalizados como ID de archivo, recuento de segmentos y marcas de tiempo. Al final de la guía tendrás un ejemplo de código listo para usar que puedes incorporar a cualquier proyecto .NET.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* .NET 6.0 o posterior (el código también funciona con .NET Framework 4.7+)
* Una licencia válida de Aspose.BarCode para .NET (la evaluación gratuita sirve para pruebas)
* Visual Studio 2022 o cualquier IDE de C# que prefieras
* Familiaridad básica con la sintaxis de C# y los conceptos de programación orientada a objetos

No se requieren paquetes NuGet adicionales más allá de **Aspose.BarCode**.

## Paso 1: Instalar el paquete NuGet Aspose.BarCode

Abre tu proyecto en Visual Studio y ejecuta el siguiente comando en la Consola del Administrador de paquetes:

```powershell
Install-Package Aspose.BarCode
```

El paquete agrega el espacio de nombres `Aspose.BarCode`, que contiene la clase `BarcodeGenerator` utilizada a lo largo de este tutorial.

## Paso 2: Crear un generador de código de barras para MacroPdf417

La primera línea crea una instancia de `BarcodeGenerator` que apunta a la simbología **MacroPdf417** e incrusta el texto personalizado que deseas codificar.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

// Step 2: Initialize the generator with custom text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The rest of the configuration goes here
}
```

*Por qué es importante*: El enumerado `EncodeTypes.MacroPdf417` indica a Aspose que trate el código de barras como un símbolo PDF417 habilitado para macro, lo que permite dividir datos grandes en varios segmentos. La cadena `"Åspóse.Barcóde©"` demuestra que el generador maneja correctamente caracteres Unicode.

## Paso 3: Definir el tamaño básico del módulo

El tamaño del módulo controla la densidad visual del código de barras. Un valor de píxel de `2` produce una imagen nítida que se imprime bien en impresoras de etiquetas estándar.

```csharp
    // Step 3: Set the X‑dimension (module width) in pixels
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Aumentar el valor hace que el código de barras sea más grande, mientras que disminuirlo puede provocar problemas de escaneo en dispositivos de baja resolución.

## Paso 4: Configurar opciones de diseño específicas de macro PDF417

MacroPdf417 requiere varios parámetros adicionales. Estas configuraciones te permiten dividir los datos en varios archivos, identificar cada segmento y verificar la integridad.

```csharp
    // Step 4: Macro‑specific layout
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

*Por qué es importante*: La propiedad `Columns` influye en el ancho del código de barras, mientras que los campos macro (`FileID`, `SegmentID`, `SegmentsCount`, `FileName`) permiten que los sistemas posteriores vuelvan a ensamblar los datos originales correctamente.

## Paso 5: Añadir metadatos macro adicionales

Aspose.BarCode te permite incrustar campos macro opcionales como suma de verificación, tamaño de archivo, marca de tiempo e información del remitente/receptor. Estos campos son útiles para auditorías y detección de errores.

```csharp
    // Step 5: Optional macro metadata
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                 // CCITT‑16 example
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // Approximate size in bytes
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                       // Creation date
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                       // Marks the last segment
```

*Por qué es importante*: La suma de verificación protege contra errores de transmisión, mientras que la marca de tiempo y los campos de remitente proporcionan contexto para el procesamiento posterior. Establecer `MacroPdf417Terminator` a `Set` indica que este es el segmento final de la serie macro.

## Paso 6: Guardar el código de barras como imagen PNG

Finalmente, escribe el código de barras generado en disco. PNG conserva la calidad sin pérdidas, lo que es ideal para el escaneo.

```csharp
    // Step 6: Export the barcode
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Cuando el código finaliza, el archivo `ExtPDF417Meta.png` contiene un código de barras MacroPdf417 de alta resolución que codifica el texto personalizado y todos los metadatos macro.

### Resultado esperado

Abrir `ExtPDF417Meta.png` muestra un código de barras orientado verticalmente con filas y columnas claramente definidas. Escanear la imagen con cualquier lector PDF417 devuelve la cadena original **Åspóse.Barcóde©** y los campos macro que configuraste (ID de archivo, ID de segmento, suma de verificación, etc.).

## Cómo generar pdf417 sin opciones de macro (escenario alternativo)

Si solo necesitas un código de barras PDF417 estándar, omite las propiedades de macro y conserva la configuración básica:

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(
           EncodeTypes.Pdf417, "Standard PDF417 data"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 3;
    generator.Parameters.Barcode.Pdf417.Columns = 6;
    generator.Save("StandardPdf417.png", BarCodeImageFormat.Png);
}
```

Este fragmento demuestra **cómo generar pdf417** rápidamente cuando no se requiere la funcionalidad macro.

## Problemas comunes y consejos profesionales

| Problema | Por qué ocurre | Solución |
|----------|----------------|----------|
| El código de barras es demasiado pequeño para escanear | `XDimension` establecida en 1 píxel o columnas demasiado altas | Usa al menos `2` píxeles para `XDimension` y mantén las columnas entre `3` y `9` para tamaños de etiqueta típicos |
| Los caracteres Unicode aparecen como � | Desajuste de codificación en el archivo del proyecto | Asegúrate de que el archivo del proyecto esté guardado como UTF-8 y que el archivo fuente contenga el BOM correcto |
| Los campos macro son ignorados por el escáner | `MacroPdf417Terminator` no está configurado para el último segmento | Establece `MacroPdf417Terminator = Pdf417MacroTerminator.Set` en el segmento final |
| El archivo de imagen está corrupto | El flujo de salida no se cierra correctamente | Usa la instrucción `using` (como se muestra) para garantizar la eliminación del generador |

## Ejemplo completo y ejecutable

Copia el siguiente código en una nueva aplicación de consola y ejecútalo. El programa crea el código de barras, lo guarda y muestra la ruta de salida en la consola.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace AsposeBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with custom Unicode text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Basic size
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // Macro layout
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Optional macro metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputFile = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
                barcodeGenerator.Save(outputFile, BarCodeImageFormat.Png);

                Console.WriteLine($"Barcode saved to: {outputFile}");
            }
        }
    }
}
```

Al ejecutar el programa se imprime una línea similar a:

```
Barcode saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

Abre el archivo para verificar la salida visual.

## Conclusión

Ahora sabes cómo **generar código de barras aspose** para la simbología MacroPdf417, incrustar texto Unicode personalizado, configurar metadatos macro y exportar el resultado como una imagen PNG. El mismo patrón te permite **cómo generar pdf417** sin opciones de macro, y puedes adaptar el código a otros formatos de código de barras compatibles con Aspose.BarCode.

A continuación, explora temas relacionados como **crear código de barras texto personalizado** para códigos QR, añadir filtros de color con parámetros `Color`, o incrustar códigos de barras directamente en documentos PDF usando Aspose.PDF. Experimenta con diferentes valores de `XDimension` y recuentos de columnas para afinar el código de barras según tu impresora o escáner específico.

¡Feliz codificación y disfruta de la fiabilidad que Aspose.BarCode aporta a tus soluciones de códigos de barras en .NET!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to generate DataMatrix barcode with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [Generate Barcode Java - Set Code Text using Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}