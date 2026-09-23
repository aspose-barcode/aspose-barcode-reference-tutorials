---
category: general
date: 2026-09-22
description: Aprende a crear códigos de barras PDF417 en C#, establecer el tamaño
  del código de barras y generar archivos de imagen del código de barras con ejemplos
  de código claros paso a paso.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to create PDF417
- set barcode size
- create barcode image c#
language: es
lastmod: 2026-09-22
og_description: Crea códigos de barras PDF417 en C# rápidamente. Este tutorial muestra
  cómo establecer el tamaño del código de barras, habilitar el modo compacto y generar
  imágenes PNG para cualquier proyecto .NET.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Crear código de barras PDF417 en C# – guía paso a paso
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to create PDF417 barcode in C#, set barcode size, and generate
    barcode image files with clear step‑by‑step code examples.
  headline: How to create PDF417 barcode and set its size in C#
  type: TechArticle
tags:
- PDF417
- C#
- Barcode
- Imaging
title: Cómo crear un código de barras PDF417 y establecer su tamaño en C#
url: /es/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un código de barras PDF417 y establecer su tamaño en C#

Si necesitas **crear un código de barras PDF417** en C#, esta guía te muestra cómo generar el código, controlar sus dimensiones y guardar el resultado como un archivo de imagen. Ya sea que estés construyendo un sistema de tickets, una etiqueta logística o una credencial segura, dominar el formato PDF417 te permite codificar grandes cantidades de datos en una forma visual compacta.

En este tutorial aprenderás a:

* **Crear un código de barras PDF417** con la biblioteca Aspose.BarCode (o cualquier compatible).  
* **Establecer el tamaño del código de barras** ajustando la X‑dimensión y el número de columnas.  
* Generar una **imagen del código de barras en C#** para salida PNG, JPEG o BMP.  

El ejemplo utiliza la edición comunitaria gratuita de Aspose.BarCode para .NET, pero los mismos conceptos se aplican a otras bibliotecas que expongan propiedades similares.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* .NET 6.0 SDK o posterior instalado.  
* Un IDE de C# (Visual Studio, Visual Studio Code, Rider, etc.).  
* El paquete NuGet `Aspose.BarCode` (`dotnet add package Aspose.BarCode`).  

No se requiere configuración adicional; la biblioteca funciona en Windows, Linux y macOS.

## Paso 1: Crear un código de barras PDF417 básico y establecer su tamaño

El primer paso es instanciar un `BarcodeGenerator` con el enum `EncodeTypes.Pdf417` y proporcionar el texto que deseas codificar. Luego ajusta la **X‑dimension** (ancho del módulo) y el número de **columnas** para controlar el tamaño general.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Define the text that the barcode will represent.
string data = "Sample text for PDF417 barcode";

// Create a basic PDF417 barcode generator.
var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Set the module width to 2 pixels (controls bar thickness).
basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Set the column count; 3 columns yields a compact visual but still readable.
basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image.
string basicPath = Path.Combine("YOUR_DIRECTORY", "Pdf417Basic.png");
basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
```

**Por qué importan estas configuraciones**

* `XDimension.Pixels` determina el ancho de la barra más estrecha. Valores más pequeños producen un código más compacto, mientras que valores mayores aumentan la legibilidad en escáneres de baja resolución.  
* `Pdf417.Columns` influye en la relación de aspecto del código. Menos columnas hacen el código más alto; más columnas lo aplanan. Ajustar las columnas es la forma principal de **establecer el tamaño del código de barras** sin cambiar los datos codificados.

Después de ejecutar el código, encontrarás `Pdf417Basic.png` en la carpeta especificada. La imagen se asemeja a la captura de pantalla a continuación:

<img src="images/pdf417-basic.png" alt="create PDF417 barcode example showing basic barcode layout">

## Paso 2: Crear un código de barras PDF417 compacto (modo truncate) con el mismo tamaño

A veces necesitas un código más corto para espacios limitados. PDF417 ofrece un modo *truncate* (compacto) que elimina el patrón de parada y reduce la altura total. La propiedad `Truncate` alterna este comportamiento.

```csharp
// Reuse the same data string.
var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Keep the same module width and column count for a fair size comparison.
compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Enable compact (truncate) mode – this removes the stop pattern.
compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version.
string compactPath = Path.Combine("YOUR_DIRECTORY", "CompactPdf417.png");
compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
```

**¿Qué cambia con `Truncate = true`?**

* El código se vuelve aproximadamente un 15‑20 % más corto verticalmente, lo que es útil para etiquetas pequeñas o pantallas móviles.  
* Los datos siguen siendo totalmente recuperables; la mayoría de los escáneres modernos entienden el modo truncate automáticamente.

El archivo resultante `CompactPdf417.png` aparece como una versión más delgada del código básico.

## Paso 3: Crear un código de barras Micro PDF417, ajustar columnas y guardarlo

Micro PDF417 es una variante de alta densidad diseñada para espacios muy reducidos (p. ej., tarjetas de identificación). Solo admite de 1 a 4 columnas, y la biblioteca expone la misma propiedad `XDimension` para el control de tamaño.

```csharp
// Create a Micro PDF417 generator.
var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);

// Set module width – 2 pixels works well for most printers.
microPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Micro PDF417 allows only 1 to 4 columns; choose 4 for a more square shape.
microPdf417.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode.
string microPath = Path.Combine("YOUR_DIRECTORY", "MicroPdf417.png");
microPdf417.Save(microPath, BarCodeImageFormat.Png);
```

**Puntos clave para Micro PDF417**

* El enum `EncodeTypes.MicroPdf417` selecciona automáticamente la variante micro.  
* Debido a que el símbolo es más denso, puede que necesites una impresora de mayor DPI (300 dpi o más) para mantener la legibilidad del código.  
* Ajustar el número de columnas es la única perilla de tamaño disponible; la biblioteca sigue respetando `XDimension`.

## Cómo establecer el tamaño del código de barras para diferentes formatos de salida

Los ejemplos anteriores usan PNG, pero el mismo método `Save` funciona con JPEG, BMP o TIFF. Si necesitas una dimensión de imagen específica (p. ej., 300 × 150 px), combina `XDimension` con `ResolutionX`/`ResolutionY`:

```csharp
basicPdf417.Parameters.ImageResolution = 300; // DPI
basicPdf417.Parameters.Barcode.XDimension.Pixels = 3; // larger modules for higher DPI
basicPdf417.Save("Pdf417HighRes.jpg", BarCodeImageFormat.Jpeg);
```

Incrementar `ImageResolution` mientras escalas `XDimension` preserva la calidad visual en impresiones de alta resolución.

## Errores comunes y consejos profesionales

| Problema | Por qué ocurre | Solución |
|----------|----------------|----------|
| El código se ve borroso en pantalla | DPI bajo combinado con XDimension pequeña | Aumenta `ImageResolution` y/o `XDimension.Pixels` |
| El escáner no lee el modo truncate | Firmware del escáner antiguo no lo soporta | Usa el modo completo (no truncado) para hardware legado |
| Micro PDF417 ilegible | Impreso a < 300 dpi o con contraste insuficiente | Imprime en papel mate a 300 dpi o más, asegura un fondo oscuro |
| Archivo de salida corrupto | Falta de permiso de escritura en la carpeta destino | Verifica que `YOUR_DIRECTORY` exista y tenga permisos de escritura |

**Consejo profesional:** Siempre genera el código de barras como PNG cuando necesites calidad sin pérdidas para procesamiento posterior (p. ej., incrustar en PDFs). PNG conserva los valores de píxel exactos, mientras que JPEG introduce artefactos de compresión que pueden afectar la legibilidad del código.

## Ejemplo completo y ejecutable

A continuación se muestra una aplicación de consola completa que demuestra los tres tipos de códigos de barras en una sola ejecución. Copia el código en un nuevo proyecto de consola .NET y ejecútalo.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // The text to encode – change this to whatever data you need.
        const string data = "Sample text for PDF417 barcode";

        // Directory where images will be saved.
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // ---------- Basic PDF417 ----------
        var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        string basicPath = Path.Combine(outputDir, "Pdf417Basic.png");
        basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Basic PDF417 saved to {basicPath}");

        // ---------- Compact (Truncate) PDF417 ----------
        var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;
        string compactPath = Path.Combine(outputDir, "CompactPdf417.png");
        compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Compact PDF417 saved to {compactPath}");

        // ---------- Micro PDF417 ----------
        var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);
        microPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        microPdf417.Parameters.Barcode.Pdf417.Columns = 4; // 1‑4 allowed
        string microPath = Path.Combine(outputDir, "MicroPdf417.png");
        microPdf417.Save(microPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Micro PDF417 saved to {microPath}");
    }
}
```

**Salida esperada**

Al ejecutar el programa se crean tres archivos PNG dentro de una carpeta `Barcodes`:

* `Pdf417Basic.png` – un código PDF417 estándar con tres columnas.  
* `CompactPdf417.png` – los mismos datos en modo truncate (compacto), ligeramente más corto.  
* `MicroPdf417.png` – una variante Micro PDF417 de alta densidad con cuatro columnas.

Abre cualquiera de las imágenes con un visor; deberías ver el distintivo patrón apilado.

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo crear código de barras – PDF417 compacto con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cómo establecer el nivel de error en el código de barras PDF417 – Guía completa](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Crear metadatos de código de barras PDF417 en C# – Guía paso a paso completa](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}