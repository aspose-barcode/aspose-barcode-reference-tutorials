---
category: general
date: 2026-10-21
description: Genera códigos de barras PDF417 rápidamente en C#. Aprende a generar
  códigos de barras PDF417 con diseño personalizado, columnas, filas y salida PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- pdf417 barcode layout
- barcode generator C#
- save barcode as PNG
language: es
lastmod: 2026-10-21
og_description: Genera código de barras pdf417 en C#. Sigue este tutorial para aprender
  cómo generar un código de barras pdf417 con columnas y filas personalizadas y salida
  PNG.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: Generar código de barras pdf417 en C# – guía completa paso a paso
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  headline: Generate pdf417 barcode in C# with custom columns and rows
  type: TechArticle
- description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  name: Generate pdf417 barcode in C# with custom columns and rows
  steps:
  - name: Open the PNG file in any image viewer.
    text: Open the PNG file in any image viewer.
  - name: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
    text: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
  - name: Confirm that the decoded text matches the original input.
    text: Confirm that the decoded text matches the original input.
  type: HowTo
tags:
- barcode
- pdf417
- C#
- image generation
title: Generar código de barras pdf417 en C# con columnas y filas personalizadas
url: /es/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-with-custom-columns-and-rows/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generar código de barras pdf417 en C# – guía completa de programación

Si necesitas **generar pdf417 barcode** en una aplicación .NET, esta guía te muestra cómo hacerlo con unas pocas líneas de código. Verás un ejemplo práctico que configura el número de columnas y filas, y luego guarda el resultado como una imagen PNG. El mismo enfoque funciona para cualquier texto que desees codificar, por lo que puedes adaptarlo a facturas, tickets o tarjetas de identificación.

Generar un **pdf417 barcode** a menudo se siente como una tarea separada del resto de tu base de código. Al final de este tutorial comprenderás por qué los parámetros de diseño son importantes, cómo controlar la calidad de la imagen y qué llamadas a la biblioteca son necesarias para **generar pdf417 barcode** de forma fiable.

## Lo que necesitarás

* .NET 6.0 SDK o posterior instalado  
* Un IDE compatible con C# (Visual Studio, VS Code, Rider, etc.)  
* El paquete NuGet **Aspose.BarCode for .NET** (o cualquier biblioteca de códigos de barras compatible)  

Puedes agregar la biblioteca con el siguiente comando:

```bash
dotnet add package Aspose.BarCode
```

La biblioteca proporciona la clase `BarcodeGenerator` utilizada a lo largo de este tutorial.

## Paso 1: Crear una instancia del generador de códigos de barras

La primera línea crea un objeto que sabe cómo **generar pdf417 barcode**. Debes especificar el tipo de codificación (`EncodeTypes.Pdf417`) y el texto que deseas codificar.

```csharp
using Aspose.BarCode.Generation;

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample Text");
```

*Por qué este paso es importante* – El `BarcodeGenerator` encapsula todas las configuraciones del código de barras. Instanciarlo con el `EncodeTypes` correcto indica al motor que use la simbología PDF417 en lugar de QR, Code128 u otros formatos.

## Paso 2: Configurar el diseño PDF417

PDF417 te permite controlar el número de columnas y filas, lo que influye directamente en el tamaño y densidad del código de barras. Ajustar estos valores es el núcleo de **how to generate pdf417 barcode** con un diseño personalizado.

```csharp
// Set the number of data columns (valid range: 2‑30)
generator.Parameters.Barcode.Pdf417.Columns = 4;

// Set the number of rows (up to 90 rows)
generator.Parameters.Barcode.Pdf417.Rows = 9;
```

*Por qué podrías cambiar estos valores* – Más columnas reducen la altura del código de barras, mientras que más filas aumentan el ancho. Elige valores que se ajusten al dispositivo de escaneo objetivo y al área de impresión disponible.

> **Consejo profesional:** Si omites las filas, la biblioteca calcula automáticamente el recuento óptimo basado en la longitud de los datos. Establecer explícitamente las filas es útil cuando necesitas un tamaño de imagen fijo para diseños de UI.

## Paso 3: Elegir un formato de imagen y guardar el archivo

Después de configurar el diseño, puedes renderizar el código de barras a una imagen. El ejemplo a continuación guarda el código de barras como un archivo PNG, pero también puedes seleccionar JPEG, BMP o TIFF.

```csharp
using Aspose.BarCode;
using System.IO;

// Define the output path – replace with your actual directory
string outputPath = Path.Combine("C:\\Barcodes", "CustomLayout.png");

// Save the barcode image as PNG
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Cuando el código se ejecuta, `CustomLayout.png` contendrá un **pdf417 barcode** claro que coincide con la configuración de columnas/filas que proporcionaste.

### Resultado esperado

Al abrir `CustomLayout.png` se muestra un código de barras rectangular con cuatro columnas de datos y nueve filas. Escanear la imagen con cualquier lector PDF417 devuelve el texto original **“Sample Text”**.

![Generated PDF417 barcode example](generated-pdf417.png){: .center-image alt="Código de barras pdf417 generado guardado como archivo PNG"}

## Paso 4: Ejemplo completo y ejecutable

A continuación se muestra una aplicación de consola autónoma que reúne todas las piezas. Copia el código en un nuevo proyecto `.csproj` y ejecútalo—no se requieren archivos adicionales.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample Text for PDF417 barcode");

            // 2️⃣ Configure layout – custom columns and rows
            generator.Parameters.Barcode.Pdf417.Columns = 4; // 2‑30
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // up to 90

            // Optional: increase image resolution for sharper output
            generator.Parameters.ImageResolution = 300; // DPI

            // 3️⃣ Define the output location
            string folder = Path.Combine(Environment.CurrentDirectory, "output");
            Directory.CreateDirectory(folder);
            string filePath = Path.Combine(folder, "CustomLayout.png");

            // 4️⃣ Save as PNG
            generator.Save(filePath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode generated at: {filePath}");
        }
    }
}
```

Ejecutar el programa imprime una línea de confirmación y crea el archivo PNG en una subcarpeta `output`. La imagen puede incrustarse en informes, imprimirse en etiquetas o enviarse a un dispositivo móvil para escanear.

## Variaciones comunes y casos límite

| Escenario | Qué cambiar | Por qué es importante |
|----------|----------------|----------------|
| **Codificar una cadena larga** | Incrementa `Rows` o permite que la biblioteca calcule automáticamente omitiendo la asignación de `Rows` | PDF417 puede contener hasta 1,850 caracteres; filas insuficientes provocan truncamiento |
| **Mayor calidad visual** | Establece `generator.Parameters.ImageResolution` a 600 DPI | Útil para imprimir en impresoras de alta resolución |
| **Formato de imagen diferente** | Reemplaza `BarCodeImageFormat.Png` por `Jpeg` o `Tiff` | JPEG reduce el tamaño del archivo; TIFF conserva datos sin pérdida para archivado |
| **Agregar zona silenciosa** | `generator.Parameters.Barcode.XDimension = 2;` (o ajusta `Margins`) | Las zonas silenciosas mejoran la fiabilidad del escáner en entornos ruidosos |
| **Texto dinámico de entrada del usuario** | Reemplaza la cadena codificada con `Console.ReadLine()` | Permite la generación en tiempo de ejecución basada en datos del usuario |

### Cómo generar pdf417 barcode en una API web

Si necesitas exponer la generación de códigos de barras a través de un endpoint ASP.NET Core, devuelve la imagen como un arreglo de bytes:

```csharp
[HttpGet("api/barcode/pdf417")]
public IActionResult GetPdf417([FromQuery] string data)
{
    var generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
    generator.Parameters.Barcode.Pdf417.Columns = 5;
    generator.Parameters.Barcode.Pdf417.Rows = 10;

    using var ms = new MemoryStream();
    generator.Save(ms, BarCodeImageFormat.Png);
    return File(ms.ToArray(), "image/png");
}
```

Este fragmento responde **how to generate pdf417 barcode** al vuelo sin escribir en disco, lo cual es ideal para microservicios o back‑ends móviles.

## Probar el código de barras generado

Para verificar que el código de barras se creó correctamente:

1. Abre el archivo PNG en cualquier visor de imágenes.  
2. Utiliza una aplicación escáner PDF417 gratuita (p.ej., ZXing, PDF417 Decoder) para escanear la imagen.  
3. Confirma que el texto decodificado coincide con la entrada original.

Si el escáner reporta errores, verifica nuevamente los valores de columna/fila y asegura que la resolución de la imagen sea lo suficientemente alta para tu dispositivo.

## Conclusión

Ahora sabes cómo **generar pdf417 barcode** en C# con control total sobre columnas, filas y formato de salida. El ejemplo completo muestra todo el flujo de trabajo—desde crear el `BarcodeGenerator` hasta guardar un archivo PNG—para que puedas integrar la creación de códigos de barras en cualquier proyecto .NET.

A continuación, explora temas relacionados como la optimización del **pdf417 barcode layout**, incrustar códigos de barras en informes PDF o decodificar códigos de barras en dispositivos móviles. Ajustar los niveles de corrección de errores y experimentar con diferentes resoluciones de imagen te ayudará a afinar la solución para tu caso de uso específico. ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo generar código de barras PDF417 en C# – guía paso a paso](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [Cómo guardar códigos de barras en C# – Generar códigos de barras PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Cómo generar código de barras PDF417 – Guía completa de programación](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}