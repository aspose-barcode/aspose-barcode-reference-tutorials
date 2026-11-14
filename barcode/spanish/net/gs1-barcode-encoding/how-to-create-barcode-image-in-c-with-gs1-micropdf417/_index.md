---
category: general
date: 2026-11-14
description: Aprende a crear una imagen de código de barras en C# usando Aspose.BarCode.
  Esta guía paso a paso cubre la configuración del generador de códigos de barras
  en C#, el formato GS1 y la exportación a PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to generate barcode
- barcode generator c#
- create gs1 barcode
- barcode image from data
language: es
lastmod: 2026-11-14
og_description: Crea rápidamente una imagen de código de barras en C#. Sigue esta
  guía para aprender a generar códigos de barras, usar el generador de códigos de
  barras en C# y exportar un PNG de GS1 MicroPDF417.
og_image_alt: Screenshot of a GS1 MicroPDF417 barcode generated in C#
og_title: Crear imagen de código de barras en C# – guía completa para GS1 MicroPDF417
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to create barcode image in C# using Aspose.BarCode. This
    step‑by‑step guide covers barcode generator c# setup, GS1 formatting and PNG export.
  headline: How to create barcode image in C# with GS1 MicroPDF417
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Cómo crear una imagen de código de barras en C# con GS1 MicroPDF417
url: /es/net/gs1-barcode-encoding/how-to-create-barcode-image-in-c-with-gs1-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear una imagen de código de barras en C# con GS1 MicroPDF417

Si necesitas **crear una imagen de código de barras** en C#, esta guía te muestra una solución completa y lista‑para‑ejecutar. Verás **cómo generar datos de código de barras** que siguen el estándar GS1, configurar el generador y exportar un archivo PNG de alta calidad.

El tutorial cubre todo, desde la instalación de la biblioteca requerida hasta el manejo de problemas comunes de formato de datos. Al final podrás producir una **imagen de código de barras a partir de datos** con solo unas pocas líneas de código, y comprenderás por qué cada configuración es importante.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* .NET 6.0 o posterior instalado (el código también funciona con .NET Framework 4.7+).
* Un IDE como Visual Studio 2022 o Visual Studio Code.
* El paquete NuGet **Aspose.BarCode for .NET**. Instálalo con:

```bash
dotnet add package Aspose.BarCode
```

* Familiaridad básica con la sintaxis de C# y el formato de Identificador de Aplicación (AI) de GS1.

> **Consejo:** Mantén la versión de la biblioteca actualizada; la última versión agrega soporte para nuevas simbologías de códigos de barras y mejoras de rendimiento.

## Crear imagen de código de barras con BarcodeGenerator

Esta sección contiene la implementación central. El código crea una instancia de **barcode generator c#**, configura la dimensión X para la legibilidad y guarda el resultado como un archivo PNG.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialise the generator with the GS1 MicroPDF417 symbology
// The data string follows the GS1 syntax: (01)GTIN(21)SerialNumber
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,
    "(01)12345678901234(21)ABC123");

// Step 2: Adjust the module width (X‑dimension) to improve scan reliability
// A value of 2 pixels works well for most screen‑displayed barcodes.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Export the barcode as a PNG image
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "GS1MicroPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
```

### Por qué cada línea es importante

* **EncodeTypes.MicroPdf417** indica a la biblioteca que use la simbología GS1 MicroPDF417, que es compacta e ideal para escaneo móvil.
* La **cadena de datos** debe comenzar con el AI de GS1 `(01)` para el Global Trade Item Number (GTIN) seguido de `(21)` para el número de serie. Si el formato es incorrecto, el generador lanza una excepción.
* **XDimension.Pixels** controla el ancho de la barra más pequeña. Un valor mayor aumenta la legibilidad en pantallas de baja resolución, mientras que un valor menor reduce el tamaño de la imagen.
* **BarCodeImageFormat.Png** produce una imagen sin pérdidas, preservando los bordes nítidos necesarios para un escaneo fiable.

Al ejecutar el programa se crea `GS1MicroPdf417.png` en tu escritorio. Al abrir el archivo se muestra un código de barras denso, negro‑sobre‑blanco, que codifica el GTIN `12345678901234` y el número de serie `ABC123`.

## Cómo generar un código de barras usando GS1 MicroPDF417

Si eres nuevo en el formato GS1, aquí tienes las reglas esenciales:

| GS1 AI | Significado                 | Ejemplo               |
|--------|-----------------------------|-----------------------|
| (01)   | Global Trade Item Number    | 12345678901234        |
| (21)   | Número de serie (opcional) | ABC123                |

Cuando concatenas los AI con sus valores, envuelve cada AI entre paréntesis y coloca los valores directamente después. La cadena resultante puede pasarse al **barcode generator c#** sin codificación adicional.

### Problemas comunes

* **Paréntesis faltantes** – El generador trata la cadena como datos sin procesar y no aplicará las verificaciones GS1.
* **Superar los límites de longitud** – MicroPDF417 admite hasta 155 caracteres. Elimina espacios en blanco innecesarios.
* **Caracteres no válidos** – Solo se permiten caracteres numéricos para el GTIN; el número de serie puede incluir letras mayúsculas y dígitos.

## Personalizando la imagen del código de barras a partir de datos

Más allá de la dimensión X básica, Aspose.BarCode ofrece muchos ajustes visuales. A continuación, algunos ajustes que podrías aplicar según los requisitos de tu proyecto.

```csharp
// Set background to transparent (useful for overlaying on UI)
generator.Parameters.ImageBackgroundColor = Color.Transparent;

// Change foreground color to dark blue for branding
generator.Parameters.Barcode.BarColor = Color.FromArgb(0, 0, 139);

// Increase image resolution to 300 dpi for print‑ready output
generator.Parameters.ImageResolution = 300;
```

Cada configuración es opcional; los valores predeterminados ya generan una **imagen de código de barras** limpia y escaneable. Experimenta con colores y resoluciones solo después de confirmar que los escáneres aún pueden leer el código.

## Guardando el código de barras en otros formatos

Aunque PNG es el formato más común para web y móvil, puede que necesites JPEG, BMP o SVG. El método `Save` acepta cualquier valor de `BarCodeImageFormat`.

```csharp
generator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
generator.Save("barcode.svg", BarCodeImageFormat.Svg);
```

* JPEG reduce el tamaño del archivo pero introduce artefactos de compresión que pueden afectar la legibilidad.
* SVG preserva la calidad vectorial y es ideal para diseños web responsivos.

## Verificando el código de barras generado

Una forma rápida de confirmar que el paso de **crear imagen de código de barras** se completó con éxito es usar una aplicación de escáner móvil que soporte GS1 MicroPDF417. Escanea el PNG guardado; la aplicación debería mostrar:

```
GTIN: 12345678901234
Serial: ABC123
```

Si el escáner reporta un error, verifica nuevamente el formato de los AI y el valor de X‑dimension.

## Ejemplo completo – un programa de consola autónomo

A continuación tienes un programa completo que puedes copiar, pegar y ejecutar sin modificaciones (excepto el paso de instalación de NuGet).

```csharp
using System;
using System.IO;
using System.Drawing;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with GS1 MicroPDF417 and sample data
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "(01)12345678901234(21)ABC123");

            // Improve readability by setting module width
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Optional visual customisation
            generator.Parameters.ImageBackgroundColor = Color.Transparent;
            generator.Parameters.Barcode.BarColor = Color.FromArgb(0, 0, 139);
            generator.Parameters.ImageResolution = 300;

            // Define output path (Desktop folder)
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "GS1MicroPdf417.png");

            // Save the barcode as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to: {outputPath}");
        }
    }
}
```

Al ejecutar el programa, la consola muestra la ruta completa del archivo y el PNG aparece en tu escritorio. Este ejemplo demuestra **cómo generar datos de código de barras**, personalizar su apariencia y exportar una **imagen de código de barras a partir de datos** en un flujo de trabajo único y coherente.

## Preguntas frecuentes

| Pregunta | Respuesta |
|----------|-----------|
| *¿Puedo generar otras simbologías GS1?* | Sí. Reemplaza `EncodeTypes.MicroPdf417` por `EncodeTypes.Pdf417`, `EncodeTypes.DataMatrix`, etc., y ajusta la cadena de datos en consecuencia. |
| *¿Qué pasa si mis datos superan la capacidad de MicroPDF417?* | Cambia a la simbología PDF417 regular, que admite cargas útiles más largas. |
| *¿Necesito una licencia para Aspose.BarCode?* | Una licencia de evaluación gratuita funciona para desarrollo. Para producción, compra una licencia para eliminar la marca de agua de evaluación. |
| *¿Es el PNG adecuado para imprimir en etiquetas?* | Aumenta `ImageResolution` a 300 dpi o más, y considera guardarlo como TIFF para impresoras industriales. |

## Conclusión

Ahora sabes cómo **crear una imagen de código de barras** en C# usando el enfoque **barcode generator c#**, formatear los datos para un escenario **create gs1 barcode**, y exportar el resultado como PNG u otro tipo de imagen. El ejemplo completo muestra cada paso—desde la preparación de datos hasta la personalización visual—para que puedas integrar la creación de códigos de barras en cualquier aplicación .NET.

A continuación, explora temas relacionados como **imagen de código de barras a partir de datos** para códigos QR, agregar múltiples códigos de barras a un solo PDF, o automatizar la generación por lotes para sistemas de inventario. Experimenta con diferentes valores de X‑dimension y formatos de imagen para encontrar el punto óptimo para tu entorno de escaneo específico.

¡Feliz codificación, y permite que tus aplicaciones comiencen a **crear imágenes de códigos de barras** que funcionen de manera fiable en el mundo real!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [How to create barcode image with Aspose.Barcode in C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [How to create postal barcode image in C# using Aspose.BarCode](/barcode/english/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/)
- [How to create PDF417 barcode image in C# – complete guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}