---
category: general
date: 2026-10-18
description: Aprende a crear códigos de barras PDF417 en C# con Aspose.BarCode. Este
  tutorial cubre la generación básica, compacta, macro y micro de PDF417 con código
  completo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to create pdf417
language: es
lastmod: 2026-10-18
og_description: Crea códigos de barras PDF417 en C# con Aspose.BarCode. Sigue esta
  guía para generar códigos de barras PDF417 básicos, compactos, macro y micro paso
  a paso.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as an image file
og_title: Crear código de barras PDF417 en C# – tutorial completo de Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to create PDF417 barcode in C# with Aspose.BarCode. This
    tutorial covers basic, compact, macro and micro PDF417 generation with full code.
  headline: Create PDF417 barcode in C# using Aspose.BarCode – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
- aspose
title: Crear código de barras PDF417 en C# usando Aspose.BarCode – guía paso a paso
url: /es/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear código de barras PDF417 en C# usando Aspose.BarCode – guía paso a paso

Si necesitas **crear un código de barras PDF417** en una aplicación .NET, este tutorial te guía a través del proceso completo. Verás cómo generar un código de barras básico, habilitar el modo compacto, añadir metadatos macro y producir una variante micro, todo con explicaciones claras y código ejecutable.

Generar códigos de barras PDF417 es común en logística, emisión de tickets y gestión documental. Al final de esta guía podrás integrar la creación de códigos de barras en cualquier proyecto C# sin herramientas externas.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* .NET 6.0 o posterior (el código también funciona con .NET Framework 4.7+)
* Visual Studio 2022 o cualquier IDE de C#
* **Aspose.BarCode for .NET** paquete NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Permiso de escritura en una carpeta donde se guardarán los archivos PNG generados

No se requiere configuración adicional; la biblioteca maneja todos los detalles de codificación de bajo nivel.

## Paso 1: Crear un código de barras PDF417 básico

El primer paso establece un código de barras PDF417 regular con tamaño y número de columnas personalizados.

```csharp
using Aspose.BarCode.Generation;

// Initialize the generator for a standard PDF417 barcode
BarcodeGenerator basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

// Adjust the X‑dimension (module width) to 2 pixels for higher resolution
basicGen.Parameters.Barcode.XDimension.Pixels = 2;

// Set the number of columns – three columns keep the barcode compact yet readable
basicGen.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image
basicGen.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**Por qué importan estas configuraciones**

* `XDimension.Pixels` controla el tamaño físico de cada elemento del código de barras. Un valor de 2 produce una imagen nítida en la mayoría de pantallas e impresoras.
* `Pdf417.Columns` determina cuántas columnas de datos contiene el código de barras. Menos columnas reducen el ancho; más columnas aumentan la capacidad de datos.

Ejecutar el código crea `Pdf417Basic.png`, que se asemeja a un símbolo PDF417 típico con tres columnas de datos y una columna completa de metadatos a la derecha.

## Paso 2: Habilitar el modo compacto (truncado)

El modo compacto elimina la columna de metadatos derecha, haciendo el código de barras más estrecho. Esto es útil cuando el espacio es limitado pero los datos pueden reconstruirse a partir de las filas restantes.

```csharp
// Turn on truncated mode to omit the metadata column
basicGen.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version
basicGen.Save(@"YOUR_DIRECTORY\CompactPdf417.png", BarCodeImageFormat.Png);
```

**¿Por qué truncar?**  
Cuando `Truncate` es `true`, el generador omite la columna opcional derecha que almacena corrección de errores y metadatos a nivel de archivo. El código de barras resultante ocupa menos columnas y sigue siendo escaneable por la mayoría de lectores PDF417.

## Paso 3: Crear un código de barras Macro PDF417 con metadatos a nivel de archivo

Macro PDF417 amplía el formato estándar con identificadores de segmento, permitiendo que un documento grande se divida en varios códigos de barras. Esto es práctico para codificar cadenas largas o archivos multipágina.

```csharp
// Initialize a generator for Macro PDF417
BarcodeGenerator macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");

// Set column count for better readability
macroGen.Parameters.Barcode.Pdf417.Columns = 5;

// Assign macro-specific identifiers
macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Unique file identifier
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;      // Current segment number
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total segments

// Save the macro barcode
macroGen.Save(@"YOUR_DIRECTORY\MacroPdf417.png", BarCodeImageFormat.Png);
```

**Explicación de los campos macro**

| Propiedad | Propósito |
|-----------|-----------|
| `MacroPdf417FileID` | Identificador único para todo el archivo; todos los segmentos comparten este valor. |
| `MacroPdf417SegmentID` | Índice del segmento actual (comienza en 1). |
| `MacroPdf417SegmentsCount` | Número total de segmentos que componen el conjunto completo de datos. |

Un escáner que entienda Macro PDF417 puede volver a ensamblar los datos originales leyendo todos los segmentos y usando estos identificadores.

## Paso 4: Crear un código de barras Micro PDF417 para datos cortos

Micro PDF417 es una versión compacta diseñada para cargas útiles pequeñas (hasta 90 caracteres). Limita el rango de columnas a 1‑4, haciendo el código de barras adecuado para etiquetas diminutas o dispositivos con área de visualización limitada.

```csharp
// Initialize a generator for Micro PDF417
BarcodeGenerator microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");

// Set a fine X‑dimension for crisp rendering
microGen.Parameters.Barcode.XDimension.Pixels = 2;

// Choose a column count within the allowed range (1‑4)
microGen.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode
microGen.Save(@"YOUR_DIRECTORY\MicroPdf417.png", BarCodeImageFormat.Png);
```

**Cuándo usar Micro PDF417**  
Utiliza esta variante cuando la carga de datos sea corta y necesites el código de barras más pequeño posible. Es ideal para etiquetas de inventario, tarjetas de acceso o cualquier escenario donde el espacio en pantalla sea escaso.

## Ejemplo completo funcional

A continuación se muestra una aplicación de consola autónoma que genera los cuatro tipos de códigos de barras en una sola ejecución. Copia el código en un nuevo proyecto C#, reemplaza `YOUR_DIRECTORY` por una ruta de carpeta existente y ejecútalo.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Adjust this path to a writable folder on your machine
            string outputPath = @"C:\Barcodes";

            // ---------- Basic PDF417 ----------
            var basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            basicGen.Parameters.Barcode.XDimension.Pixels = 2;
            basicGen.Parameters.Barcode.Pdf417.Columns = 3;
            basicGen.Save($"{outputPath}\\Pdf417Basic.png", BarCodeImageFormat.Png);

            // ---------- Compact PDF417 ----------
            basicGen.Parameters.Barcode.Pdf417.Truncate = true;
            basicGen.Save($"{outputPath}\\CompactPdf417.png", BarCodeImageFormat.Png);

            // ---------- Macro PDF417 ----------
            var macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");
            macroGen.Parameters.Barcode.Pdf417.Columns = 5;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
            macroGen.Save($"{outputPath}\\MacroPdf417.png", BarCodeImageFormat.Png);

            // ---------- Micro PDF417 ----------
            var microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");
            microGen.Parameters.Barcode.XDimension.Pixels = 2;
            microGen.Parameters.Barcode.Pdf417.Columns = 4; // valid range: 1‑4
            microGen.Save($"{outputPath}\\MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("All PDF417 barcodes have been generated successfully.");
        }
    }
}
```

**Salida esperada**

Al ejecutar el programa se crean cuatro archivos PNG en la carpeta especificada:

* `Pdf417Basic.png` – código de barras estándar con tres columnas
* `CompactPdf417.png` – mismos datos, columna derecha truncada
* `MacroPdf417.png` – código macro que contiene metadatos de segmento
* `MicroPdf417.png` – código micro compacto para cadenas cortas

Abre cualquier imagen con un visor; verás los patrones PDF417 distintivos. Escanearlos con un lector de códigos de barras móvil (p. ej., ZXing, Scandit) devuelve las cadenas de texto originales.

## Preguntas frecuentes y consejos

* **¿Qué pasa si el código de barras se ve borroso?**  
  Aumenta `XDimension.Pixels` a 3 o 4. Los módulos más grandes generan imágenes de mayor resolución, a costa de un archivo más grande.

* **¿Puedo generar SVG en lugar de PNG?**  
  Sí. Reemplaza `BarCodeImageFormat.Png` por `BarCodeImageFormat.Svg` en las llamadas a `Save`.

* **¿Necesito establecer manualmente el nivel de corrección de errores?**  
  Aspose.BarCode elige automáticamente un nivel óptimo. Para casos de uso especializados puedes ajustar `Pdf417.ErrorCorrectionLevel`.

* **¿Cómo incrustar el código de barras en un documento PDF?**  
  Usa `Aspose.Pdf` para añadir el PNG o SVG generado como un elemento de imagen en una página PDF.

* **¿La biblioteca es segura para hilos?**  
  Cada instancia de `BarcodeGenerator` es independiente; puedes crear generadores en múltiples hilos sin compartir estado.

## Conclusión

Ahora sabes cómo **crear un código de barras PDF417** en C# usando Aspose.BarCode, cubriendo variantes básica, compacta, macro y micro.

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [How to create pdf417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}