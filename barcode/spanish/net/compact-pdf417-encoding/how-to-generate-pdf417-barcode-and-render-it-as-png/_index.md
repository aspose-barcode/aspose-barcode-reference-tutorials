---
category: general
date: 2026-11-17
description: Aprende cómo generar códigos de barras PDF417, establecer el tamaño del
  código de barras y renderizar el código de barras a una imagen usando C#. Guía completa
  paso a paso.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- how to generate PDF417
- render barcode to image
- how to set barcode size
language: es
lastmod: 2026-11-17
og_description: Genera un código de barras PDF417 en C# y renderiza el código de barras
  a una imagen. Sigue esta guía para establecer el tamaño del código de barras y guardar
  un archivo PNG.
og_image_alt: Screenshot of a generated PDF417 barcode saved as a PNG image
og_title: Generar código de barras PDF417 y renderizar como PNG – Guía de C#
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to generate PDF417 barcode, set barcode size, and render
    barcode to image using C#. Complete step‑by‑step guide.
  headline: How to generate PDF417 barcode and render it as PNG
  type: TechArticle
- description: Learn how to generate PDF417 barcode, set barcode size, and render
    barcode to image using C#. Complete step‑by‑step guide.
  name: How to generate PDF417 barcode and render it as PNG
  steps:
  - name: Open the PNG file in any image viewer.
    text: Open the PNG file in any image viewer.
  - name: Use a smartphone barcode scanning app that supports PDF417 (e.g., Google
      Lens, QR & Barcode Scanner).
    text: Use a smartphone barcode scanning app that supports PDF417 (e.g., Google
      Lens, QR & Barcode Scanner).
  - name: Scan the image; the app should return the text *Layout demo*.
    text: Scan the image; the app should return the text *Layout demo*.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- image generation
title: Cómo generar un código de barras PDF417 y renderizarlo como PNG
url: /es/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-and-render-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo generar un código de barras PDF417 y renderizarlo como PNG

Si necesitas **generar un código de barras PDF417** en una aplicación .NET, este tutorial te muestra exactamente cómo hacerlo. Verás cómo establecer el tamaño del código de barras, configurar el diseño y **renderizar el código de barras a una imagen** con solo unas pocas líneas de código C#.

Generar un código de barras PDF417 es común cuando deseas codificar grandes cantidades de datos para escanear en dispositivos móviles o impresoras. Al final de esta guía tendrás un archivo PNG listo para usar que podrás incrustar en informes, correos electrónicos o páginas web.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

- SDK de .NET 6.0 o posterior instalado  
- Un IDE de C# como Visual Studio 2022 (cualquier editor sirve)  
- El paquete NuGet **Aspose.BarCode for .NET** (o cualquier biblioteca compatible que proporcione `BarcodeGenerator`)  

Puedes añadir el paquete con:

```bash
dotnet add package Aspose.BarCode
```

## Paso 1: Crear un proyecto de consola C#

Primero, configura una aplicación de consola mínima que alojará el código de generación del código de barras.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // The barcode generation logic will be placed here.
        }
    }
}
```

> **Consejo profesional:** Mantén el método `Main` breve y delega el trabajo pesado a métodos auxiliares. Esto mejora la legibilidad y facilita las pruebas unitarias.

## Paso 2: Generar código de barras PDF417 con tamaño personalizado

Ahora **generaremos un código de barras PDF417** y especificaremos el tamaño del módulo (dimensión X). La dimensión X controla cuán ancho es cada pequeño cuadrado del código de barras, estableciendo efectivamente el tamaño total del código.

```csharp
static void GeneratePdf417(string text, string outputPath)
{
    // Initialize a PDF417 barcode generator with the desired text
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, text);

    // Set the size of a single barcode module (X‑dimension) in pixels
    generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module

    // Optional: adjust the number of columns and rows for layout control
    generator.Parameters.Barcode.Pdf417.Columns = 4;   // 4 columns
    generator.Parameters.Barcode.Pdf417.Rows    = 9;   // 9 rows

    // Render the barcode and save it as a PNG image
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

### ¿Por qué establecer la dimensión X?

El paso **cómo establecer el tamaño del código de barras** es importante porque una dimensión X demasiado pequeña puede hacer que el código sea ilegible en escáneres de baja resolución, mientras que un valor demasiado grande desperdicia espacio. Un valor de `2` píxeles funciona bien para la mayoría de pantallas y escenarios de impresión.

## Paso 3: Llamar al método de generación desde `Main`

Une todo invocando `GeneratePdf417` con el texto deseado y la ubicación de salida.

```csharp
static void Main(string[] args)
{
    string barcodeText = "Layout demo";
    string outputFile = @"C:\Barcodes\LayoutPdf417.png";

    GeneratePdf417(barcodeText, outputFile);

    Console.WriteLine($"PDF417 barcode saved to {outputFile}");
}
```

Ejecutar el programa crea `LayoutPdf417.png` que contiene el código de barras:

![Código de barras PDF417 generado](/images/layout-pdf417.png "Código de barras PDF417 generado por el código del tutorial"){: .align-center alt="Código de barras PDF417 generado guardado como PNG"}

> **Salida esperada:** Un archivo PNG de aproximadamente 200 × 100 px (dependiendo de la configuración de columnas/filas) que muestra un patrón PDF417 claro listo para escanear.

## Paso 4: Verificar que el código de barras funciona

Para asegurarte de que el código de barras es válido:

1. Abre el archivo PNG en cualquier visor de imágenes.  
2. Usa una aplicación de escaneo de códigos de barras en tu smartphone que admita PDF417 (por ejemplo, Google Lens, QR & Barcode Scanner).  
3. Escanea la imagen; la aplicación debería devolver el texto *Layout demo*.

Si el escaneo falla, verifica nuevamente la dimensión X y los valores de columnas/filas: módulos más grandes mejoran la legibilidad en cámaras de baja resolución.

## Variaciones comunes y casos límite

| Escenario | Ajuste |
|----------|------------|
| **Más datos** (p. ej., una URL) | Incrementa `Columns` o `Rows` para acomodar palabras de código adicionales. |
| **Impresión de alta resolución** | Aumenta `XDimension.Pixels` a 3‑4 px para barras más nítidas. |
| **Fondo transparente** | Usa `generator.Save(outputPath, BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })`. |
| **Formato de imagen diferente** | Reemplaza `BarCodeImageFormat.Png` por `Jpeg` o `Bmp` según sea necesario. |

Estas variaciones responden a la pregunta **cómo generar PDF417** para diferentes requisitos manteniendo la lógica central idéntica.

## Conclusión

Ahora sabes cómo **generar un código de barras PDF417**, **establecer el tamaño del código de barras** y **renderizar el código de barras a una imagen** usando C#. El ejemplo completo y ejecutable crea un archivo PNG que puede incrustarse donde necesites un código de barras legible por máquina.

A continuación, explora temas relacionados como **incrustar el PNG en un PDF** (busca *render barcode to PDF*), o **generar otros códigos 2‑D** como códigos QR. Ajusta los parámetros de diseño para que encajen con tu UI y experimenta con opciones de color para la marca.

¡Feliz codificación, y que tus códigos de barras hagan el trabajo pesado!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [How to generate PDF417 barcode in C# – complete step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [How to generate micro pdf417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}