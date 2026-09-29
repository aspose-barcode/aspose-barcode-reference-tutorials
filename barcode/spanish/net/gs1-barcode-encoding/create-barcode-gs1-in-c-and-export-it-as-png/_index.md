---
category: general
date: 2026-09-29
description: Crear código de barras GS1 en C# y generar imágenes PNG de códigos de
  barras usando BarcodeGenerator. Sigue una guía paso a paso para exportar la imagen
  del código de barras de manera eficiente.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode gs1
- generate barcode png
- barcode generator c#
- how to generate barcode
- export barcode image
language: es
lastmod: 2026-09-29
og_description: Crea códigos de barras GS1 en C# y genera archivos PNG de códigos
  de barras con BarcodeGenerator. Sigue esta guía completa para exportar la imagen
  del código de barras rápidamente.
og_image_alt: Generated GS1 MicroPDF417 barcode saved as a PNG file
og_title: Crear código de barras GS1 en C# – exportar a PNG en minutos
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create barcode GS1 in C# and generate barcode PNG images using BarcodeGenerator.
    Follow a step‑by‑step guide to export barcode image efficiently.
  headline: Create barcode GS1 in C# and export it as PNG
  type: TechArticle
tags:
- barcode
- C#
- GS1
- PNG
- Aspose
title: Crear código de barras GS1 en C# y exportarlo como PNG
url: /es/net/gs1-barcode-encoding/create-barcode-gs1-in-c-and-export-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear código de barras GS1 en C# y exportarlo como PNG

Si necesitas **crear código de barras GS1** en una aplicación .NET, esta guía te muestra exactamente cómo hacerlo. Verás una solución concisa que genera una imagen PNG de código de barras y exporta la imagen del código de barras al disco, todo con la clase `BarcodeGenerator` de Aspose.BarCode .

Generar un código de barras GS1 es un requisito común para sistemas de inventario, envío y punto de venta. Al final de este tutorial podrás escribir un pequeño programa en C# que crea un código de barras MicroPDF417 compatible con GS1 y lo guarda como un archivo PNG de alta calidad.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* **.NET 6** (o cualquier versión posterior de .NET) instalado.
* **Visual Studio 2022** o cualquier IDE que soporte C#.
* El paquete NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`) – proporciona la API `BarcodeGenerator` utilizada en los ejemplos.
* Familiaridad básica con la sintaxis de C#.

> **Consejo profesional:** Usa la edición comunitaria gratuita de Aspose.BarCode al experimentar; la versión completa elimina cualquier marca de agua de evaluación.

## Paso 1 – Crear código de barras GS1 con BarcodeGenerator

Lo primero que necesitas es instanciar el `BarcodeGenerator` para el formato *MicroPDF417* y proporcionarle una cadena de datos GS1. Los Identificadores de Aplicación (AI) de GS1 se envuelven entre paréntesis, por ejemplo `(01)` para GTIN‑14 y `(21)` para un número de serie.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// GS1 data: (01) – GTIN‑14, (21) – serial number
string gs1Data = "(01)12345678901234(21)ABC123";

// Initialise the generator for MicroPDF417 (GS1 compatible)
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);
```

**Por qué es importante:**  
`EncodeTypes.MicroPdf417` trata automáticamente la entrada como datos GS1 cuando la cadena contiene AI válidos. Esto garantiza que el código de barras generado cumpla con la especificación GS1 sin configuración adicional.

## Paso 2 – Establecer dimensiones del código de barras para un tamaño óptimo

El tamaño visual de un código de barras está controlado por su **X‑dimension** (el ancho de un módulo único). Ajustar `XDimension.Pixels` te permite afinar el tamaño final de la imagen mientras se preserva la legibilidad.

```csharp
// Set the module width to 2 pixels – a good balance for screen and print
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Cómo generar un PNG de código de barras** – La X‑dimension no afecta los datos codificados; solo cambia las dimensiones físicas de la imagen generada. Si necesitas un código de barras más grande para impresión de alta resolución, incrementa este valor (p. ej., `3` o `4`).

## Paso 3 – Generar PNG del código de barras y exportar la imagen del código de barras

Ahora puedes renderizar el código de barras y escribirlo en un archivo PNG. El método `Save` recibe la ruta de destino y el formato de imagen deseado.

```csharp
// Define the output folder (ensure it exists)
string outputFolder = Path.Combine(Environment.CurrentDirectory, "output");
Directory.CreateDirectory(outputFolder);

// Export the barcode image as PNG
string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
generator.Save(pngPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode image saved to: {pngPath}");
```

**Qué ocurre internamente:**  
`BarcodeGenerator.Save` rasteriza el código de barras en un bitmap, aplica la X‑dimension que configuraste antes y codifica el bitmap como un archivo PNG. El archivo resultante puede usarse directamente en páginas web, imprimirse en etiquetas o incrustarse en PDFs.

## Ejemplo completo de código fuente

A continuación se muestra una aplicación de consola completa y autónoma que puedes copiar, pegar y ejecutar. Demuestra **cómo generar archivos PNG de código de barras**, **exportar la imagen del código de barras**, e incluye manejo básico de errores.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Gs1BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // 1️⃣ Initialise the barcode generator for GS1 MicroPDF417
                string gs1Data = "(01)12345678901234(21)ABC123";
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.MicroPdf417, gs1Data);

                // 2️⃣ Adjust X‑dimension to control the visual size
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // 3️⃣ Prepare output folder
                string outputFolder = Path.Combine(
                    Environment.CurrentDirectory, "output");
                Directory.CreateDirectory(outputFolder);

                // 4️⃣ Save the barcode as PNG (export barcode image)
                string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
                generator.Save(pngPath, BarCodeImageFormat.Png);

                Console.WriteLine($"✅ Barcode created and saved as PNG:");
                Console.WriteLine(pngPath);
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Error: {ex.Message}");
            }
        }
    }
}
```

### Salida esperada

Al ejecutar el programa, deberías ver:

```
✅ Barcode created and saved as PNG:
C:\Path\To\Your\App\output\GS1MicroPdf417.png
```

Abrir el archivo PNG muestra un código de barras **GS1 MicroPDF417** claro que codifica el GTIN‑14 `12345678901234` y el número de serie `ABC123`. Escanearlo con cualquier lector compatible con GS1 devolverá la cadena de datos original.

## Problemas comunes y buenas prácticas

| Problema | Por qué ocurre | Cómo evitarlo |
|----------|----------------|---------------|
| **Formato de AI incorrecto** | Falta de paréntesis o orden incorrecto hace que el código de barras no sea GS1. | Siempre envuelve cada AI entre paréntesis, p. ej., `(01)`. |
| **X‑dimension demasiado pequeña** | El código de barras se vuelve ilegible en dispositivos de baja resolución. | Mantén `XDimension.Pixels` ≥ 2 para la mayoría de impresoras; aumenta para salida de alta DPI. |
| **La carpeta de salida no existe** | `Save` lanza `DirectoryNotFoundException`. | Usa `Directory.CreateDirectory` antes de llamar a `Save`. |
| **Uso del EncodeType incorrecto** | Algunos tipos (p. ej., `Code128`) no soportan datos GS1 por defecto. | Elige `EncodeTypes.MicroPdf417` o cualquier tipo compatible con GS1. |
| **Falta la referencia NuGet** | Errores de compilación como `The type or namespace name 'Aspose' could not be found`. | Instala el paquete `Aspose.BarCode` mediante NuGet. |

## Extender el ejemplo

* **Diferentes formatos de imagen** – Reemplaza `BarCodeImageFormat.Png` con `Jpeg`, `Gif` o `Bmp` si necesitas otro formato.
* **Salida de mayor resolución** – Configura `generator.Parameters.ImageResolution.DpiX` y `DpiY` antes de guardar.
* **Incrustar en PDF** – Usa `Aspose.Pdf` para colocar el PNG en una factura o etiqueta PDF.

## Conclusión

Ahora sabes cómo **crear código de barras GS1** en C# usando el `BarcodeGenerator` de Aspose.BarCode, **generar PNG de código de barras**, y **exportar la imagen del código de barras** al sistema de archivos. La guía cubrió cada paso—desde inicializar el generador con datos GS1, ajustar la X‑dimension, hasta guardar el archivo PNG final—mientras abordaba errores comunes y ofrecía ideas de extensión.

Siéntete libre de experimentar con otros Identificadores de Aplicación GS1, diferentes simbologías de códigos de barras o imágenes de mayor resolución. Cuando domines estos conceptos básicos, generar códigos de barras compatibles para inventario, envío o venta minorista se convertirá en una parte rutinaria de tu caja de herramientas .NET.

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Crear imágenes de código de barras GS1 en C# – Cómo generar código de barras C# rápidamente](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [Crear PNG de código de barras en C# – guía paso a paso](/barcode/english/python-java/general/create-barcode-png-in-c-step-by-step-guide/)
- [Crear imagen de código de barras en C# – guía completa de programación](/barcode/english/python-java/general/create-barcode-image-in-c-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}