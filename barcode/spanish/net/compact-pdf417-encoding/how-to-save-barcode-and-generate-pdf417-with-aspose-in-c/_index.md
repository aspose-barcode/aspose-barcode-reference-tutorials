---
category: general
date: 2026-09-29
description: Cómo guardar códigos de barras usando Aspose.BarCode en C# y aprender
  a generar PDF417 con metadatos macro. Sigue la guía paso a paso.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- how to generate pdf417
- how to set pdf417
- generate barcode with aspose
language: es
lastmod: 2026-09-29
og_description: Cómo guardar un código de barras usando Aspose.BarCode en C# es sencillo.
  Este tutorial muestra cómo generar PDF417 con metadatos macro y establecer todos
  los parámetros requeridos.
og_image_alt: Screenshot showing how to save barcode as PNG with PDF417 macro metadata
og_title: Cómo guardar un código de barras con Aspose – Guía de generación de PDF417
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to save barcode using Aspose.BarCode in C# and learn how to generate
    PDF417 with macro metadata. Follow step‑by‑step guide.
  headline: How to save barcode and generate PDF417 with Aspose in C#
  type: TechArticle
- description: How to save barcode using Aspose.BarCode in C# and learn how to generate
    PDF417 with macro metadata. Follow step‑by‑step guide.
  name: How to save barcode and generate PDF417 with Aspose in C#
  steps:
  - name: '**Creating the generator** – The `BarcodeGenerator` constructor takes the
      barcode type (`EncodeTypes.MacroPdf417`) and the data to encode. Macro PDF417
      is a special variant that carries file‑transfer information, which is why we
      later fill macro fields.'
    text: '**Creating the generator** – The `BarcodeGenerator` constructor takes the
      barcode type (`EncodeTypes.MacroPdf417`) and the data to encode. Macro PDF417
      is a special variant that carries file‑transfer information, which is why we
      later fill macro fields.'
  - name: '**Appearance settings** – `XDimension.Pixels` controls the narrow bar width;
      adjusting it changes the overall image size without affecting data integrity.
      `Pdf417.Columns` defines the layout of the barcode matrix.'
    text: '**Appearance settings** – `XDimension.Pixels` controls the narrow bar width;
      adjusting it changes the overall image size without affecting data integrity.
      `Pdf417.Columns` defines the layout of the barcode matrix.'
  - name: '**Macro metadata** – These properties (`MacroPdf417FileID`, `MacroPdf417SegmentID`,
      etc.) are essential when you need to split a large file into multiple barcode
      segments. Setting them correctly ensures that a scanner can reconstruct the
      original file.'
    text: '**Macro metadata** – These properties (`MacroPdf417FileID`, `MacroPdf417SegmentID`,
      etc.) are essential when you need to split a large file into multiple barcode
      segments. Setting them correctly ensures that a scanner can reconstruct the
      original file.'
  - name: '**Saving the image** – The `Save` method writes the generated barcode to
      disk. You can choose any supported format (`Png`, `Jpeg`, `Bmp`, etc.). This
      line demonstrates the exact **how to save barcode** operation requested.'
    text: '**Saving the image** – The `Save` method writes the generated barcode to
      disk. You can choose any supported format (`Png`, `Jpeg`, `Bmp`, etc.). This
      line demonstrates the exact **how to save barcode** operation requested.'
  type: HowTo
tags:
- barcode
- PDF417
- Aspose
- C#
title: Cómo guardar el código de barras y generar PDF417 con Aspose en C#
url: /es/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo guardar códigos de barras y generar PDF417 con Aspose en C#

Cómo guardar un código de barras usando Aspose.BarCode en C# es un requisito común cuando necesitas incrustar datos en un archivo de imagen. Esta guía te lleva paso a paso por el proceso completo de generar un código de barras PDF417 con macro‑metadata y guardar el resultado como una imagen PNG. Al final sabrás **cómo generar PDF417**, **cómo establecer opciones de PDF417**, y, lo más importante, **cómo guardar archivos de códigos de barras** de forma programática.

Verás un ejemplo completo y ejecutable que cubre cada paso—desde agregar el paquete NuGet Aspose.BarCode hasta configurar los campos macro como ID de archivo, recuento de segmentos y suma de verificación. No se requiere documentación externa; el código puede copiarse en un nuevo proyecto de consola y ejecutarse de inmediato. El tutorial asume que tienes Visual Studio 2022 (o posterior) y .NET 6.0 instalados.

## Requisitos previos

- .NET 6.0 SDK (o cualquier versión de .NET compatible con Aspose.BarCode 23.11+)
- Visual Studio 2022, VS Code, o tu IDE favorito para C#
- **Aspose.BarCode for .NET** paquete NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Conocimientos básicos de sintaxis C# y aplicaciones de consola

> **Consejo:** Usa la licencia de evaluación gratuita para desarrolladores de Aspose si aún no dispones de una licencia comercial. La evaluación funciona sin cambios en el código.

## Cómo guardar códigos de barras – ejemplo completo

El siguiente código crea un código de barras **Macro PDF417**, completa todos los campos macro y guarda la imagen como `ExtPDF417Meta.png`. Todas las directivas `using` necesarias están incluidas para que puedas pegar el fragmento directamente en `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for Macro PDF417 with sample data
        using (BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MacroPdf417,          // EncodeTypes enum selects the barcode type
            "Åspóse.Barcóde©"))               // Sample data – Unicode characters are supported
        {
            // Step 2: Define basic barcode appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // narrow bar width (2 px)
            generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns per row

            // Step 3: Configure Macro PDF417 metadata
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Step 4: Save the generated barcode as a PNG image
            // This is the core of **how to save barcode** with Aspose.
            generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }

        Console.WriteLine("Barcode saved as ExtPDF417Meta.png");
    }
}
```

### Por qué cada paso es importante

1. **Crear el generador** – El constructor `BarcodeGenerator` recibe el tipo de código de barras (`EncodeTypes.MacroPdf417`) y los datos a codificar. Macro PDF417 es una variante especial que transporta información de transferencia de archivos, por eso más adelante rellenamos los campos macro.  
2. **Configuración de apariencia** – `XDimension.Pixels` controla el ancho de la barra estrecha; ajustarlo cambia el tamaño total de la imagen sin afectar la integridad de los datos. `Pdf417.Columns` define la disposición de la matriz del código de barras.  
3. **Metadatos macro** – Estas propiedades (`MacroPdf417FileID`, `MacroPdf417SegmentID`, etc.) son esenciales cuando necesitas dividir un archivo grande en varios segmentos de código de barras. Configurarlas correctamente garantiza que un escáner pueda reconstruir el archivo original.  
4. **Guardar la imagen** – El método `Save` escribe el código de barras generado en disco. Puedes elegir cualquier formato compatible (`Png`, `Jpeg`, `Bmp`, etc.). Esta línea muestra la operación exacta de **cómo guardar códigos de barras** solicitada.

> **Pregunta frecuente:** *¿Qué pasa si necesito un formato de imagen diferente?*  
> Cambia `BarCodeImageFormat.Png` a `BarCodeImageFormat.Jpeg` (o cualquier otro valor del enum soportado) y ajusta la extensión del archivo en consecuencia.

## Cómo generar PDF417 con metadatos macro

Si solo necesitas un PDF417 regular (sin datos macro), puedes omitir la sección macro y mantener el generador básico:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample data"))
{
    gen.Parameters.Barcode.XDimension.Pixels = 3;
    gen.Save("SimplePdf417.png", BarCodeImageFormat.Png);
}
```

El código anterior ilustra **cómo generar PDF417** rápidamente. Observa que el enum `EncodeTypes.Pdf417` selecciona la versión sin macro.

## Cómo configurar PDF417 – opciones avanzadas

Aspose.BarCode expone muchos parámetros específicos de PDF417. Aquí tienes algunos que podrías necesitar:

| Propiedad | Descripción | Valores típicos |
|-----------|-------------|-----------------|
| `Pdf417.Columns` | Número de columnas por fila | 1‑30 (predeterminado 3) |
| `Pdf417.Rows` | Número de filas (calculado automáticamente si es 0) | 0‑90 |
| `Pdf417.ErrorLevel` | Nivel de corrección de errores (0‑8) | 2‑4 para equilibrio entre tamaño y robustez |
| `Pdf417.RowsPerStrip` | Filas por tira para códigos de barras grandes | 0 (auto) |
| `Pdf417.Pdf417MacroFileID` | Identificador del archivo al usar macro | Cualquier entero de 32 bits |

Establecer estos valores sigue el mismo patrón mostrado en **Paso 2** del ejemplo principal. Ajústalos antes de llamar a `Save`.

## Salida esperada

Ejecutar el programa completo crea `ExtPDF417Meta.png` en el directorio de trabajo del ejecutable. La imagen contiene un código de barras PDF417 de alta resolución con todos los campos macro incrustados. Escanear la imagen con un lector compatible con PDF417 (o una aplicación móvil) devolverá la cadena de datos original `"Åspóse.Barcóde©"` junto con los metadatos macro (ID de archivo, ID de segmento, etc.).

![Barcode saved as PNG – how to save barcode example](ExtPDF417Meta.png "How to save barcode as PNG with macro PDF417 metadata")

*Texto alternativo de la imagen:* **cómo guardar código de barras como PNG con metadatos macro PDF417** (coincide con la palabra clave principal).

## Conclusión

En este tutorial aprendiste **cómo guardar códigos de barras** usando Aspose.BarCode, **cómo generar PDF417**, **cómo establecer parámetros de PDF417**, y **cómo generar códigos de barras con Aspose** tanto para escenarios regulares como habilitados con macro.

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo generar código de barras PDF417 con Aspose – Guía completa](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Cómo generar imagen de código de barras PDF417 en C# con Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Cómo generar código de barras en C# con Aspose.BarCode y agregar metadatos](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-in-c-with-aspose-barcode-and-add-met/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}