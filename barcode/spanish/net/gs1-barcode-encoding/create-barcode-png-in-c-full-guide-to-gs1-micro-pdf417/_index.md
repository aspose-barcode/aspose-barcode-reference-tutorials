---
category: general
date: 2026-08-12
description: Crea un PNG de código de barras en C# rápidamente con Aspose.BarCode.
  Aprende cómo generar un código de barras PDF417 en C# y domina el uso del generador
  de códigos de barras en un solo tutorial.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode PNG
- generate PDF417 barcode C#
- barcode generator usage
- GS1 Micro PDF417 example
- Aspose.BarCode C#
language: es
lastmod: 2026-08-12
og_description: Crear código de barras PNG en C# con Aspose.BarCode. Este tutorial
  le muestra cómo generar un código de barras PDF417 en C# y usar el generador de
  códigos de barras de manera eficaz.
og_image_alt: create barcode PNG example showing a GS1 Micro PDF417 code
og_title: Crear código de barras PNG en C# – guía paso a paso
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create barcode PNG in C# quickly with Aspose.BarCode. Learn how to
    generate PDF417 barcode C# and master barcode generator usage in a single tutorial.
  headline: Create barcode PNG in C# – full guide to GS1 Micro PDF417
  type: TechArticle
- description: Create barcode PNG in C# quickly with Aspose.BarCode. Learn how to
    generate PDF417 barcode C# and master barcode generator usage in a single tutorial.
  name: Create barcode PNG in C# – full guide to GS1 Micro PDF417
  steps:
  - name: Why each line matters
    text: '| Line | Reason | |------|--------| | `EncodeTypes.Gs1MicroPdf417` | Selects
      the specific PDF417 variant required for GS1 applications. | | Data string `"(01)12345678901231(10)ABC123"`
      | Demonstrates the GS1 AI syntax for a GTIN (01) and a lot number (10). | |
      `XDimension.Pixels = 2` | Controls the '
  - name: Expected visual result
    text: The PNG contains a rectangular barcode with evenly spaced black modules.
      Scanning it with a GS1‑compatible scanner returns the string `(01)12345678901231(10)ABC123`,
      confirming that **generate PDF417 barcode C#** succeeded.
  - name: Changing the symbology
    text: 'If you need a regular PDF417 instead of the micro version, replace the
      encode type:'
  - name: Adjusting image format
    text: 'Aspose.BarCode supports many formats. To create a JPEG instead:'
  - name: Saving to a stream (useful for web APIs)
    text: '```csharp using (var ms = new MemoryStream()) { generator.Save(ms, BarCodeImageFormat.Png);
      // ms.ToArray() now contains the PNG bytes – return them from an API endpoint.
      } ```'
  - name: What’s next?
    text: '* Explore **barcode reader integration** to verify generated images automatically.
      * Experiment with **custom colors** and **logo embedding** for brand‑aware barcodes.
      * Review the Aspose.BarCode documentation for advanced error‑correction settings
      and multi‑page PDF417 generation.'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Crear PNG de código de barras en C# – guía completa de GS1 Micro PDF417
url: /es/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear PNG de código de barras en C# – guía completa de GS1 Micro PDF417

Si necesitas **crear PNG de código de barras** en una aplicación .NET, esta guía te muestra exactamente cómo hacerlo. Aprenderás a generar un código de barras PDF417 en C# y verás los patrones de **uso del generador de códigos de barras** que funcionan en producción.

Generar una imagen de código de barras es un requisito común para sistemas de inventario, etiquetas de envío y plataformas de tickets. Al final de este tutorial tendrás un programa de consola autónomo que escribe un archivo PNG que contiene un código de barras GS1 Micro PDF417, listo para el procesamiento posterior.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* SDK de .NET 6.0 o posterior instalado (el código también funciona con .NET Framework 4.7.2+).
* Una versión reciente del paquete NuGet **Aspose.BarCode for .NET**. Instálalo con  
  `dotnet add package Aspose.BarCode`.
* Familiaridad básica con proyectos de consola en C#.
* Permiso de escritura en una carpeta donde se guardará el PNG.

Estos requisitos mantienen el ejemplo ligero mientras reflejan una configuración del mundo real.

## Paso 1: Configurar el proyecto C#

Crea un nuevo proyecto de consola y agrega la referencia a Aspose.BarCode:

```bash
dotnet new console -n BarcodePngDemo
cd BarcodePngDemo
dotnet add package Aspose.BarCode
```

El CLI `dotnet` genera un archivo `Program.cs` y restaura el paquete NuGet. Este paso es esencial para el **uso del generador de códigos de barras** porque la biblioteca contiene la clase `BarcodeGenerator` que emplearemos.

## Paso 2: Escribir el código completo de generación de código de barras

Reemplaza el contenido de `Program.cs` con el siguiente código. Contiene cada línea que necesitas para **crear PNG de código de barras** de principio a fin.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodePngDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -------------------------------------------------
            // 1️⃣ Create a BarcodeGenerator for GS1 Micro PDF417
            // -------------------------------------------------
            // EncodeTypes.Gs1MicroPdf417 tells Aspose.BarCode to use the
            // GS1 Micro PDF417 symbology. The data string follows the
            // Application Identifier (AI) format required by GS1.
            var generator = new BarcodeGenerator(
                EncodeTypes.Gs1MicroPdf417,
                "(01)12345678901231(10)ABC123");

            // -------------------------------------------------
            // 2️⃣ Adjust the X‑dimension (module width)
            // -------------------------------------------------
            // XDimension controls the physical size of each barcode module.
            // Lower values produce a smaller image; higher values increase
            // readability on low‑resolution scanners.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // -------------------------------------------------
            // 3️⃣ (Optional) Set image resolution and background
            // -------------------------------------------------
            // Higher DPI yields a sharper PNG, useful when the image
            // will be printed. BackgroundColor can be set to Transparent.
            generator.Parameters.ImageResolution = 300;      // DPI
            generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent;

            // -------------------------------------------------
            // 4️⃣ Save the barcode as a PNG file
            // -------------------------------------------------
            // The Save method writes the image to disk. You can also
            // choose other formats such as Jpeg, Bmp, or Gif.
            string outputPath = "output.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode PNG created at: {outputPath}");
        }
    }
}
```

### Por qué cada línea es importante

| Línea | Razón |
|------|--------|
| `EncodeTypes.Gs1MicroPdf417` | Selecciona la variante específica de PDF417 requerida para aplicaciones GS1. |
| Cadena de datos `"(01)12345678901231(10)ABC123"` | Demuestra la sintaxis AI de GS1 para un GTIN (01) y un número de lote (10). |
| `XDimension.Pixels = 2` | Controla el tamaño físico del código de barras; un valor predeterminado común para visualización en pantalla. |
| `ImageResolution = 300` | Aumenta DPI, asegurando que el PNG se vea nítido al imprimirse. |
| `BackgroundColor = Transparent` | Hace que el PNG sea amigable para superposiciones en UI. |
| `Save(..., BarCodeImageFormat.Png)` | Persiste el código de barras como PNG, cumpliendo el objetivo de **crear PNG de código de barras**. |

## Paso 3: Ejecutar el programa y verificar la salida

Ejecuta la aplicación de consola:

```bash
dotnet run
```

Deberías ver el mensaje de confirmación y encontrar `output.png` en la carpeta del proyecto. Al abrir el archivo se mostrará un código de barras GS1 Micro PDF417 que codifica los datos de ejemplo.

![create barcode PNG example](barcode-example.png)

*Texto alternativo: ejemplo de crear PNG de código de barras que muestra un código GS1 Micro PDF417.*

### Resultado visual esperado

El PNG contiene un código de barras rectangular con módulos negros espaciados uniformemente. Escanearlo con un lector compatible con GS1 devuelve la cadena `(01)12345678901231(10)ABC123`, confirmando que **generar PDF417 barcode C#** se completó con éxito.

## Paso 4: Explorar variaciones comunes

### Cambiar la simbología

Si necesitas un PDF417 regular en lugar de la versión micro, reemplaza el tipo de codificación:

```csharp
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Your data here");
```

### Ajustar el formato de imagen

Aspose.BarCode admite muchos formatos. Para crear un JPEG en su lugar:

```csharp
generator.Save("output.jpg", BarCodeImageFormat.Jpeg);
```

### Guardar en un stream (útil para APIs web)

```csharp
using (var ms = new MemoryStream())
{
    generator.Save(ms, BarCodeImageFormat.Png);
    // ms.ToArray() now contains the PNG bytes – return them from an API endpoint.
}
```

Estos fragmentos ilustran un **uso flexible del generador de códigos de barras** más allá del escenario básico de guardado en archivo.

## Consejos profesionales y trampas comunes

* **Validar la longitud de los datos** – GS1 Micro PDF417 tiene una capacidad máxima de datos; superarla lanza una excepción. Usa `generator.Parameters.Barcode.IsValidData(data)` para pre‑verificar.
* **Evitar valores de XDimension muy pequeños** – valores por debajo de 1 píxel pueden producir códigos de barras ilegibles en dispositivos de baja resolución.
* **Establecer `QuietZone`** si incrustas el PNG en un gráfico más grande; la zona silenciosa predeterminada asegura que los escáneres localicen los patrones de inicio/fin.
* **Seguridad en hilos** – Las instancias de `BarcodeGenerator` no son seguras para subprocesos. Crea un nuevo generador por solicitud en un servicio web.

## Conclusión

Ahora sabes cómo **crear PNG de código de barras** en C# usando Aspose.BarCode, cómo **generar PDF417 barcode C#** con la variante GS1 Micro, y los patrones esenciales para un **uso efectivo del generador de códigos de barras**. El ejemplo completo y ejecutable puede incorporarse en cualquier proyecto .NET, y puedes ampliarlo con diferentes simbologías, formatos de imagen o salidas en streaming.

### ¿Qué sigue?

* Explora la **integración del lector de códigos de barras** para verificar automáticamente las imágenes generadas.  
* Experimenta con **colores personalizados** y **incrustación de logotipos** para códigos de barras con identidad de marca.  
* Revisa la documentación de Aspose.BarCode para configuraciones avanzadas de corrección de errores y generación de PDF417 multipágina.

¡Feliz codificación, y que tus aplicaciones hablen el lenguaje de las máquinas con PNG de códigos de barras nítidos y fiables!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo crear código de barras – Compact PDF417 con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cómo guardar PNG usando DataMatrix C40 con Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [Cómo generar código de barras – Configuración Code 39 con Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}