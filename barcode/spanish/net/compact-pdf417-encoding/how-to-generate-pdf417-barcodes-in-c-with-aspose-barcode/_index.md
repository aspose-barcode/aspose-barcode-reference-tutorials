---
category: general
date: 2026-09-10
description: Cómo generar códigos de barras PDF417 en C# usando Aspose.BarCode. Sigue
  una guía paso a paso para crear Macro PDF417, ajustar parámetros y exportar como
  PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- macro pdf417 barcode
- aspose.barcode for .net
- c# barcode generator
- pdf417 barcode parameters
- barcode image export
language: es
lastmod: 2026-09-10
og_description: Cómo generar códigos de barras PDF417 en C# con Aspose.BarCode. Aprende
  el flujo de trabajo completo, desde la configuración hasta guardar una imagen PNG
  de Macro PDF417.
og_image_alt: Screenshot of a generated Macro PDF417 barcode saved as a PNG file
og_title: Cómo generar códigos de barras PDF417 en C# – guía completa de Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: How to generate PDF417 barcodes in C# using Aspose.BarCode. Follow
    a step‑by‑step guide to create Macro PDF417, adjust parameters, and export as
    PNG.
  headline: How to generate PDF417 barcodes in C# with Aspose.BarCode
  type: TechArticle
- description: How to generate PDF417 barcodes in C# using Aspose.BarCode. Follow
    a step‑by‑step guide to create Macro PDF417, adjust parameters, and export as
    PNG.
  name: How to generate PDF417 barcodes in C# with Aspose.BarCode
  steps:
  - name: '**Create a Macro PDF417 generator** – `EncodeTypes.MacroPdf417` tells Aspose.BarCode
      to use the macro version of PDF417, which supports splitting a large payload
      across multiple symbols.'
    text: '**Create a Macro PDF417 generator** – `EncodeTypes.MacroPdf417` tells Aspose.BarCode
      to use the macro version of PDF417, which supports splitting a large payload
      across multiple symbols.'
  - name: '**Adjust basic appearance** – `XDimension` controls the module (dot) width;
      `Columns` defines how many columns each symbol will contain, influencing both
      size and readability.'
    text: '**Adjust basic appearance** – `XDimension` controls the module (dot) width;
      `Columns` defines how many columns each symbol will contain, influencing both
      size and readability.'
  - name: '**Set macro‑specific fields** – These properties (`MacroPdf417FileID`,
      `MacroPdf417SegmentID`, etc.) are required by the PDF417 macro specification
      to re‑assemble the original data on the scanner side.'
    text: '**Set macro‑specific fields** – These properties (`MacroPdf417FileID`,
      `MacroPdf417SegmentID`, etc.) are required by the PDF417 macro specification
      to re‑assemble the original data on the scanner side.'
  - name: '**Export the image** – `BarCodeImageFormat.Png` provides a lossless image
      that works well for web, print, and mobile scenarios.'
    text: '**Export the image** – `BarCodeImageFormat.Png` provides a lossless image
      that works well for web, print, and mobile scenarios.'
  - name: '**Visual verification** – Open `MacroPdf417.png` in any image viewer. You
      should see a stacked set of vertical bars with a small text caption (the encoded
      data).'
    text: '**Visual verification** – Open `MacroPdf417.png` in any image viewer. You
      should see a stacked set of vertical bars with a small text caption (the encoded
      data).'
  - name: '**Scanner test** – Use a mobile barcode scanner app that supports PDF417.
      Scan the image; the app should return the original “Sample text” plus macro
      metadata (file ID, segment ID, etc.).'
    text: '**Scanner test** – Use a mobile barcode scanner app that supports PDF417.
      Scan the image; the app should return the original “Sample text” plus macro
      metadata (file ID, segment ID, etc.).'
  - name: '**Error handling** – If the scanner reports “checksum error,” double‑check
      `MacroPdf417Checksum` and ensure the `MacroPdf417Terminator` is set correctly
      on the last segment.'
    text: '**Error handling** – If the scanner reports “checksum error,” double‑check
      `MacroPdf417Checksum` and ensure the `MacroPdf417Terminator` is set correctly
      on the last segment.'
  - name: '**Performance** – Generating many segments in a loop can be CPU‑intensive.
      Re‑use a single `BarcodeGenerator` instance and only update the macro fields
      between saves to improve throughput.'
    text: '**Performance** – Generating many segments in a loop can be CPU‑intensive.
      Re‑use a single `BarcodeGenerator` instance and only update the macro fields
      between saves to improve throughput.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspose
title: Cómo generar códigos de barras PDF417 en C# con Aspose.BarCode
url: /es/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo generar códigos de barras PDF417 en C# con Aspose.BarCode

Si necesitas **cómo generar pdf417** en un proyecto .NET, este tutorial muestra el flujo de trabajo completo. Verás cómo crear un código de barras Macro PDF417, afinar sus configuraciones y exportar el resultado como una imagen PNG, todo con Aspose.BarCode para .NET.

Generar códigos de barras PDF417 es común en logística, emisión de boletos y flujos de trabajo de documentos seguros. Al final de esta guía tendrás un generador de códigos de barras C# listo para usar que podrás integrar en cualquier aplicación.

## Lo que necesitarás

- **Visual Studio 2022** (o cualquier IDE de C#)  
- **.NET 6.0** o posterior  
- **Aspose.BarCode for .NET** NuGet package (`Install-Package Aspose.BarCode`)  
- Familiaridad básica con la sintaxis de C#  

> **Consejo profesional:** Usa la última versión de Aspose.BarCode para obtener las funciones más recientes de Macro PDF417 y correcciones de errores.

---

## Cómo generar códigos de barras PDF417 en C#  

A continuación se muestra un ejemplo completamente ejecutable que crea un código de barras **Macro PDF417**, configura sus campos específicos de macro y guarda la imagen.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // STEP 1 – create a Macro PDF417 generator with the desired text
        using (BarcodeGenerator generator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
        {
            // STEP 2 – adjust basic barcode appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
            generator.Parameters.Barcode.Pdf417.Columns = 5;     // number of columns

            // STEP 3 – configure Macro PDF417 specific fields
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp =
                new DateTime(2023, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // STEP 4 – save the generated barcode as a PNG image
            generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
        }

        Console.WriteLine("Macro PDF417 barcode generated: MacroPdf417.png");
    }
}
```

### Por qué cada paso es importante

1. **Crear un generador Macro PDF417** – `EncodeTypes.MacroPdf417` indica a Aspose.BarCode que use la versión macro de PDF417, que permite dividir una carga útil grande en varios símbolos.  
2. **Ajustar la apariencia básica** – `XDimension` controla el ancho del módulo (punto); `Columns` define cuántas columnas tendrá cada símbolo, influyendo tanto en el tamaño como en la legibilidad.  
3. **Establecer los campos específicos de macro** – Estas propiedades (`MacroPdf417FileID`, `MacroPdf417SegmentID`, etc.) son requeridas por la especificación macro de PDF417 para volver a ensamblar los datos originales en el escáner.  
4. **Exportar la imagen** – `BarCodeImageFormat.Png` proporciona una imagen sin pérdida que funciona bien para web, impresión y escenarios móviles.

## Configuración de Aspose.BarCode para .NET (generador de códigos de barras C#)

Antes de poder ejecutar el código anterior, debes agregar la biblioteca Aspose.BarCode a tu proyecto:

```bash
dotnet add package Aspose.BarCode
```

*El paquete NuGet incluye todas las dependencias, por lo que no se necesitan DLL adicionales.*

Si apuntas a .NET Framework, el mismo comando `Install-Package Aspose.BarCode` funciona desde la consola del Administrador de paquetes.

### Errores comunes

- **Licencia faltante** – Por defecto Aspose se ejecuta en modo de evaluación, lo que añade una marca de agua al código de barras. Registra un archivo de licencia (`License license = new License(); license.SetLicense("Aspose.BarCode.lic");`) para eliminarla.  
- **`EncodeTypes` incorrecto** – Usar `EncodeTypes.Pdf417` en lugar de `EncodeTypes.MacroPdf417` ignorará todos los campos macro, rompiendo la reconstrucción de múltiples segmentos.

## Configuración de los parámetros del código de barras Macro PDF417

Los campos macro te permiten dividir un documento grande en varios símbolos PDF417. Aquí tienes una referencia rápida:

| Property | Propósito | Rango típico |
|----------|-----------|--------------|
| `MacroPdf417FileID` | Identificador único para el archivo completo | 0‑2³¹‑1 |
| `MacroPdf417SegmentID` | Índice del segmento actual (comienza en 0) | 0‑254 |
| `MacroPdf417SegmentsCount` | Número total de segmentos en el archivo | 1‑255 |
| `MacroPdf417FileName` | Nombre legible opcional | 0‑255 caracteres |
| `MacroPdf417Checksum` | Checksum CCITT‑16 para detección de errores | 0‑65535 |
| `MacroPdf417FileSize` | Tamaño original del archivo en bytes | 0‑2³¹‑1 |
| `MacroPdf417TimeStamp` | Marca de tiempo de creación (opcional) | `DateTime` value |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Metadatos opcionales para enrutamiento | Any string |
| `MacroPdf417Terminator` | Indica el segmento final (`Set` o `Unset`) | `Pdf417MacroTerminator` enum |

Ajusta estos valores para que coincidan con los datos que estás codificando. Por ejemplo, si divides un archivo de 2 MB en 20 segmentos, establece `MacroPdf417FileSize` a `2_000_000` y `MacroPdf417SegmentsCount` a `20`.

## Exportando el código de barras como imagen PNG (exportación de imagen de código de barras)

Guardar el código de barras como PNG es el formato de exportación más común porque preserva bordes nítidos y soporta transparencia. Aspose.BarCode también soporta JPEG, BMP, GIF y TIFF; elige el que se ajuste a tu proceso posterior.

```csharp
generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
```

**Consejos para una salida de alta calidad**

- Aumenta `XDimension.Pixels` para módulos más grandes al imprimir en medios de alta resolución.  
- Usa `BarCodeImageFormat.Tiff` con compresión CCITT Group 4 para PDFs compatibles con fax.  
- Configura `generator.Parameters.ImageOptions.Resolution` si necesitas un DPI específico (p. ej., 300 dpi para impresión).

## Pruebas y solución de problemas de tu código de barras PDF417

1. **Verificación visual** – Abre `MacroPdf417.png` en cualquier visor de imágenes. Deberías ver un conjunto apilado de barras verticales con una pequeña leyenda de texto (los datos codificados).  
2. **Prueba con escáner** – Usa una aplicación móvil de escaneo de códigos de barras que soporte PDF417. Escanea la imagen; la aplicación debería devolver el “Texto de muestra” original más los metadatos macro (ID de archivo, ID de segmento, etc.).  
3. **Manejo de errores** – Si el escáner informa “error de checksum”, verifica nuevamente `MacroPdf417Checksum` y asegura que `MacroPdf417Terminator` esté configurado correctamente en el último segmento.  
4. **Rendimiento** – Generar muchos segmentos en un bucle puede ser intensivo en CPU. Reutiliza una única instancia de `BarcodeGenerator` y solo actualiza los campos macro entre guardados para mejorar el rendimiento.

## Conclusión

Ahora sabes **cómo generar códigos de barras PDF417** en C# usando Aspose.BarCode, desde la instalación de la biblioteca hasta la configuración de los campos Macro PDF417 y la exportación de una imagen PNG limpia. La solución completa demuestra:

- Configurar un **generador de códigos de barras C#** con el tipo Macro PDF417  
- Personalizar los **parámetros del código de barras PDF417** para datos de varios segmentos  
- Realizar la **exportación de imagen de código de barras** para uso posterior  

Desde aquí puedes explorar temas avanzados como incrustar el código de barras en documentos PDF, generar códigos QR complementarios o automatizar el procesamiento por lotes de archivos grandes.

**Próximos pasos**

- Prueba diferentes valores de `BarCodeImageFormat` (p. ej., `Tiff` para impresiones de alta resolución).  
- Combina Macro PDF417 con otras simbologías en el mismo documento usando `generator.Parameters.Barcode.Symbology`.  
- Revisa la [documentación de Aspose.BarCode](https://docs.aspose.com/barcode/net/) para opciones de personalización más avanzadas como nivel de corrección de errores y modos de codificación.

¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Generar código de barras con texto – Guía completa de PDF417 Macro](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)
- [ajustar tamaño del código de barras – Guía C# para generar códigos de barras PDF417](/barcode/english/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Cómo generar código de barras PDF417 – Guía completa de programación](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}