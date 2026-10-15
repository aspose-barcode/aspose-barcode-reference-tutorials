---
category: general
date: 2026-10-15
description: Crear un PNG de código de barras en C# con un ejemplo compacto de PDF417
  – aprende a configurar columnas, ajustar dimensiones y generar la imagen.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to create barcode
- how to set columns
- c# barcode example
language: es
lastmod: 2026-10-15
og_description: Crea un PNG de código de barras en C# con un ejemplo compacto de PDF417.
  Esta guía muestra cómo establecer columnas, ajustar dimensiones y guardar la imagen.
og_image_alt: Screenshot showing a generated barcode PNG created with C#
og_title: Crear código de barras PNG en C# – tutorial completo de programación
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  headline: How to create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  name: How to create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: Initialise the barcode generator with the desired text
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: Set the module (X) dimension in pixels
    text: '```csharp // Set the width of the smallest bar (module) to 2 pixels generator.Parameters.Barcode.XDimension.Pixels
      = 2; ```'
  - name: Define the number of columns for the PDF417 barcode
    text: '```csharp // Specify that the barcode should use 3 columns generator.Parameters.Barcode.Pdf417.Columns
      = 3; ```'
  - name: Enable the compact layout by truncating the barcode
    text: '```csharp // Truncate removes unnecessary empty rows, making the barcode
      shorter generator.Parameters.Barcode.Pdf417.Truncate = true; ```'
  - name: Save the barcode image as PNG
    text: '```csharp // Choose the output folder and file name string outputPath =
      Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");'
  - name: Full, runnable example
    text: 'Putting everything together, here is a self‑contained program you can copy,
      paste, and run:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: Cómo crear un PNG de código de barras en C# – guía paso a paso
url: /es/net/compact-pdf417-encoding/how-to-create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un PNG de código de barras en C# – guía paso a paso

Si necesitas **crear archivos PNG de código de barras** desde código C#, este tutorial te muestra una solución completa en solo unas pocas líneas. Verás cómo establecer columnas, ajustar el tamaño del módulo y guardar un código de barras PDF417 compacto como una imagen PNG, todo con un ejemplo sencillo y fácil de leer.

Generar códigos de barras programáticamente elimina el paso manual de usar un editor gráfico y te permite incrustar códigos de barras directamente en facturas, tickets o etiquetas de inventario. En las secciones siguientes cubriremos todo lo que necesitas saber para **cómo crear códigos de barras** en imágenes, por qué cada configuración es importante y cómo adaptar el código para diferentes casos de uso.

## Prerrequisitos

Antes de comenzar, asegúrate de tener:

* .NET 6.0 o posterior (el código también funciona con .NET Framework 4.7+)
* Una referencia a una biblioteca de códigos de barras que soporte PDF417, como **Aspose.BarCode for .NET** o **IronBarcode**. El ejemplo usa Aspose.BarCode, que puedes instalar vía NuGet:

```bash
dotnet add package Aspose.BarCode
```

* Familiaridad básica con la sintaxis de C# y Visual Studio (o cualquier IDE que prefieras).

> **Consejo:** Si prefieres una alternativa gratuita, la biblioteca de código abierto **ZXing.Net** también soporta PDF417, aunque los nombres de las propiedades difieren ligeramente. Los conceptos mostrados aquí siguen siendo los mismos.

## Cómo crear un PNG de código de barras en C# (paso principal)

El núcleo de la solución es un objeto `BarcodeGenerator` configurado para la codificación PDF417. Las siguientes secciones desglosan cada línea de código, explican **cómo establecer columnas** y muestran por qué los ajustes afectan el tamaño final del PNG.

### Paso 1: Inicializar el generador de códigos de barras con el texto deseado

```csharp
using Aspose.BarCode.Generation;

// The text you want to encode in the barcode
string barcodeText = "Compact example";

// Create a generator for PDF417 barcodes
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
{
    // Subsequent configuration goes here
}
```

*Por qué es importante*: El enumerado `EncodeTypes.Pdf417` indica a la biblioteca que produzca un código de barras bidimensional apilado. El constructor también acepta los datos que deseas codificar, por lo que no necesitas una llamada separada a `SetData`.

### Paso 2: Establecer la dimensión del módulo (X) en píxeles

```csharp
// Set the width of the smallest bar (module) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

La **dimensión X** controla la densidad visual del código de barras. Un valor más pequeño produce una imagen más compacta, lo que es útil cuando necesitas un PNG reducido para pantallas móviles o espacio de impresión limitado.

### Paso 3: Definir el número de columnas para el código de barras PDF417

```csharp
// Specify that the barcode should use 3 columns
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

Esta línea demuestra **cómo establecer columnas**. PDF417 puede elegir automáticamente el recuento óptimo de columnas, pero establecerlo explícitamente te brinda un ancho predecible, especialmente cuando incrustas el PNG en un diseño de tamaño fijo.

### Paso 4: Habilitar el diseño compacto truncando el código de barras

```csharp
// Truncate removes unnecessary empty rows, making the barcode shorter
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

Cuando `Truncate` es verdadero, la biblioteca elimina filas finales que no contienen datos, reduciendo la altura total de la imagen sin perder información.

### Paso 5: Guardar la imagen del código de barras como PNG

```csharp
// Choose the output folder and file name
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");

// Save the generated barcode as a PNG file
generator.Save(outputPath, BarCodeImageFormat.Png);
```

El método `Save` escribe el código de barras en disco en el formato que especificas. PNG es sin pérdida, lo que lo hace ideal para aplicaciones de escaneo que requieren detección de bordes precisa.

### Ejemplo completo y ejecutable

Juntando todo, aquí tienes un programa autónomo que puedes copiar, pegar y ejecutar:

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise the generator with the data to encode
        string barcodeText = "Compact example";

        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
        {
            // 2️⃣ Set module width to 2 pixels for a tighter image
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Explicitly set the number of columns (how to set columns)
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Enable compact layout by truncating empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define the output path and save as PNG (create barcode PNG)
            string outputPath = Path.Combine(Directory.GetCurrentDirectory(), "CompactPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode PNG saved to: {outputPath}");
        }
    }
}
```

**Salida esperada** – Después de ejecutar el programa, encontrarás `CompactPdf417.png` en la carpeta de ejecución. La imagen contiene un código de barras PDF417 de tres columnas que es lo suficientemente compacto como para caber en una etiqueta estándar de 2 × 2 cm y sigue siendo totalmente escaneable.

![Create barcode PNG example](placeholder.png){alt="Crear PNG de código de barras usando C#"}

## Cómo establecer columnas para diferentes tamaños de datos (palabra clave secundaria)

El número de columnas influye tanto en el ancho como en la legibilidad del código de barras:

| Columnas | Ancho aproximado (px) | Caso de uso típico |
|----------|-----------------------|--------------------|
| 1‑2      | Estrecho, alto        | Etiquetas pequeñas, impresiones tipo RFID |
| 3‑5      | Equilibrado           | Etiquetas de uso general |
| 6‑9      | Ancho, corto          | Pósters grandes o empaques |

Si tu cadena de datos crece, la biblioteca puede aumentar automáticamente el recuento de filas para mantener el código de barras dentro del límite de columnas. Sin embargo, forzar un recuento de columnas demasiado bajo puede hacer que el código de barras sea excesivamente alto, lo que podría no caber en una impresora de recibos. Ajusta el número de columnas según las limitaciones físicas de tu medio de salida.

## Cómo crear imágenes de código de barras en otros formatos (palabra clave secundaria)

Aunque PNG es el formato más común para web y móvil, podrías necesitar **cómo crear códigos de barras** en JPEG, BMP o SVG para flujos de trabajo especializados:

```csharp
// Save as JPEG with 90 % quality
generator.Save("CompactPdf417.jpg", BarCodeImageFormat.Jpeg, 90);

// Save as SVG (vector, infinite scaling)
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

Elegir el formato adecuado depende del consumidor final:

* **PNG** – sin pérdida, ideal para escáneres.
* **JPEG** – tamaño de archivo menor, aceptable cuando se toleran ligeros artefactos de compresión.
* **SVG** – perfecto para impresión de alta resolución o escalado de UI.

## Ejemplo de código de barras en C#: manejo de errores y casos límite

Un **c# barcode example** robusto debe anticipar problemas en tiempo de ejecución:

```csharp
try
{
    // All configuration steps as shown earlier
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode parameter: {ex.Message}");
}
catch (IOException ex)
{
    Console.Error.WriteLine($"Failed to write file: {ex.Message}");
}
```

*¿Por qué envolver en `try/catch`?* Caracteres inválidos en el texto, dimensiones no soportadas o problemas de permisos de escritura lanzarán excepciones. Manejar estas situaciones de forma elegante evita que tu aplicación se bloquee durante el procesamiento por lotes.

## Ampliando el ejemplo: añadiendo un logotipo o fondo

Muchos escenarios del mundo real requieren una superposición de logotipo o un fondo coloreado. La API de Aspose.BarCode te permite combinar el código de barras con un bitmap:

```csharp
// Load a logo image
using (Bitmap logo = (Bitmap)Image.FromFile("logo.png"))
{
    generator.Parameters.Barcode.ImageFormat = BarCodeImageFormat.Png;
    generator.Parameters.Barcode.Pdf417.EnablePdf417CodewordCount = true; // optional

    // Merge the logo with the barcode (centered)
    generator.Save("BarcodeWithLogo.png", BarCodeImageFormat.Png, logo);
}
```

Esta técnica mantiene intacto el flujo **create barcode PNG** mientras enriquece la marca visual de la imagen final.

## Resumen

En esta guía demostramos cómo **crear archivos PNG de código de barras** en C# usando una configuración compacta de PDF417. Aprendiste:

* El código exacto necesario para inicializar un `BarcodeGenerator`.
* **Cómo establecer columnas** y por qué el recuento de columnas importa para el tamaño y la legibilidad.
* Cómo ajustar la dimensión X y habilitar el truncado para obtener un PNG más ajustado.
* Formas de guardar la imagen en PNG, JPEG o SVG.
* Patrones de manejo de errores para un **c# barcode example** listo para producción.
* Extensiones opcionales como superposición de logotipo y personalización de fondo.

Ahora dispones de un fragmento listo para ejecutar que puedes integrar en generadores de facturas, sistemas de tickets o herramientas de gestión de inventario. Experimenta con diferentes valores de columna, tamaños de módulo o tipos de códigos de barras (p. ej., QR, Code128) para ver cómo cambia la imagen.

## Próximos pasos

* Explora otros tipos de codificación (`EncodeTypes.QR`, `EncodeTypes.Code128`) para cubrir más casos de uso.
* Combina la generación de códigos de barras con bibliotecas de creación de PDF (p. ej., **iTextSharp**) para incrustar el PNG directamente en documentos.
* Investiga el dimensionado dinámico: calcula el recuento óptimo de columnas basado en la longitud de la cadena de entrada y las dimensiones de la etiqueta objetivo.

¡Feliz codificación y disfruta de la simplicidad de generar programáticamente PNGs nítidos de códigos de barras en C#!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [How to create PDF417 barcode and save it as PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)
- [How to create PDF417 barcode and set its size in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}