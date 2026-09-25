---
category: general
date: 2026-08-22
description: Aprende a crear códigos de barras micro PDF417 en C# y generar una imagen
  PNG del código de barras. Incluye configurar las dimensiones del código de barras
  y guardar el archivo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- how to generate barcode png
- create barcode image c#
- how to set barcode dimensions
language: es
lastmod: 2026-08-22
og_description: Crea un código de barras micro PDF417 en C# y expórtalo como PNG.
  Sigue esta guía para establecer las dimensiones del código de barras y generar una
  imagen de código de barras rápidamente.
og_image_alt: Screenshot of a micro PDF417 barcode generated with C# code
og_title: Crear código de barras micro PDF417 en C# – tutorial completo de codificación
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  headline: How to create micro PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  name: How to create micro PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Build the project: `dotnet build`.'
    text: 'Build the project: `dotnet build`.'
  - name: 'Execute: `dotnet run`.'
    text: 'Execute: `dotnet run`.'
  - name: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
    text: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
  type: HowTo
tags:
- barcode
- C#
- MicroPdf417
- image generation
title: Cómo crear un código de barras micro PDF417 en C# – guía paso a paso
url: /es/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un código de barras micro PDF417 en C# – guía paso a paso

Si necesitas **crear un código de barras micro PDF417** para un sistema de tickets, una etiqueta de inventario o escaneo móvil, este tutorial te muestra exactamente cómo hacerlo. Verás el programa completo en C# que genera un PNG del código de barras, aprenderás a establecer las dimensiones del código y comprenderás cada opción de configuración.

Al final de esta guía podrás generar una imagen de código de barras de alta resolución, personalizar la X‑dimensión, elegir el número de columnas y guardar el resultado como un archivo PNG, todo con unas pocas líneas de código.

## Lo que necesitarás

- .NET 6.0 SDK o posterior (el código funciona con .NET Core y .NET Framework)
- Visual Studio 2022 o cualquier IDE compatible con C#
- El paquete NuGet **Aspose.BarCode for .NET** (o cualquier biblioteca que soporte `EncodeTypes.MicroPdf417`)
- Familiaridad básica con la sintaxis de C#

> **Consejo:** La edición comunitaria gratuita de Aspose.BarCode es suficiente para desarrollo y pruebas. Para producción, obtén una licencia para eliminar las marcas de agua de evaluación.

## Paso 1: Instalar la biblioteca de códigos de barras

Abre una terminal en la carpeta de tu proyecto y ejecuta:

```bash
dotnet add package Aspose.BarCode
```

Esto agrega el ensamblado `Aspose.BarCode`, que proporciona la clase `BarcodeGenerator` utilizada para **crear aplicaciones de imagen de código de barras en C#**.

## Paso 2: Inicializar el generador – crear código de barras micro PDF417

La primera línea ejecutable crea una instancia de `BarcodeGenerator` configurada para la simbología Micro PDF417 y suministra los datos que deseas codificar.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize a Micro PDF417 barcode generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");
```

*Por qué es importante*: El enumerado `EncodeTypes.MicroPdf417` indica a la biblioteca que use la versión compacta de PDF417, ideal para etiquetas pequeñas y pantallas móviles.

## Paso 3: Cómo establecer las dimensiones del código de barras en C#

Ajustar finamente el ancho del módulo (X‑dimensión) controla la densidad visual del código de barras. Un valor más pequeño produce una imagen más nítida, mientras que un valor mayor facilita la lectura a distancia.

```csharp
        // Step 3: Set the X‑dimension (module width) to 2 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Por qué deberías establecer dimensiones**: Sin ajustar la X‑dimensión, el valor predeterminado puede producir un código de barras que se ve borroso al renderizarse a alta DPI. Establecerlo en 2 píxeles es un buen equilibrio para la mayoría de los escaneos basados en pantalla.

## Paso 4: Elegir el número de columnas – controlar el ancho del código de barras

Micro PDF417 permite entre 1 y 4 columnas. Más columnas comprimen los datos horizontalmente, reduciendo el ancho total de la imagen.

```csharp
        // Step 4: Define the number of columns (allowed values: 1‑4)
        generator.Parameters.Barcode.Pdf417.Columns = 4;
```

*Caso límite*: Si solicitas 5 columnas la biblioteca lanza una `ArgumentOutOfRangeException`. Mantente siempre dentro del rango documentado.

## Paso 5: Cómo generar un PNG del código de barras – guardar la imagen

Ahora puedes exportar el código de barras generado a un archivo PNG. PNG conserva calidad sin pérdidas, lo cual es esencial para un escaneo fiable.

```csharp
        // Step 5: Save the generated barcode as a PNG image
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "MicroPdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

Al ejecutar el programa, verás un mensaje en la consola confirmando la ubicación del archivo. El `MicroPdf417.png` resultante se ve así:

![Captura de pantalla que muestra un código de barras micro PDF417 generado con C#](micro-pdf417-example.png "Código de barras micro PDF417 generado")

*Texto alternativo de la imagen*: **código de barras micro PDF417 generado en C#** – muestra la salida final después de aplicar las dimensiones y la configuración de columnas.

## Paso 6: Ejecutar y verificar la salida

1. Compila el proyecto: `dotnet build`.
2. Ejecuta: `dotnet run`.
3. Abre `MicroPdf417.png` en tu escritorio y escanéalo con una aplicación móvil de escáner de códigos de barras.

Deberías ver el texto **“Sample text”** decodificado. Si el escáner informa un error, verifica la X‑dimensión y el número de columnas – valores extremos pueden hacer que el código sea demasiado denso para algunos dispositivos.

## Variaciones comunes y solución de problemas

| Situación | Ajuste |
|-----------|--------|
| **Necesitas un código de barras más grande para impresoras de baja resolución** | Aumenta `XDimension.Pixels` a 3 o 4. |
| **Quieres un código de barras más alto sin cambiar el ancho** | Establece `generator.Parameters.Barcode.Pdf417.Rows` (rango de filas 3‑90). |
| **Generar varios códigos de barras en un bucle** | Reutiliza la misma instancia de `BarcodeGenerator` y solo cambia `CodeText` antes de cada `Save`. |
| **Guardar como JPEG en lugar de PNG** | Reemplaza `BarCodeImageFormat.Png` por `BarCodeImageFormat.Jpeg`. |
| **Ejecutar en .NET Framework 4.7** | El mismo código funciona; solo referencia el `Aspose.BarCode.dll` apropiado. |

## Listado completo del código fuente (ejecutable)

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialize a Micro PDF417 barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");

            // Set the X‑dimension (module width) to 2 pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns (allowed values: 1‑4)
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

**Salida esperada** – un archivo PNG de 200 × 100 píxeles que contiene un código de barras Micro PDF417 nítido que decodifica “Sample text”.

## Conclusión

Ahora sabes cómo **crear un código de barras micro PDF417** en C#, **establecer las dimensiones del código** y **generar una imagen PNG del código de barras**. El ejemplo completo muestra cada paso necesario, desde la instalación de la biblioteca hasta el guardado del archivo final, para que puedas integrar la generación de códigos de barras directamente en tus propias aplicaciones.

A continuación, explora temas relacionados como **crear códigos QR con Aspose.BarCode**, **personalizar colores** o **incorporar códigos de barras en documentos PDF**. Cada uno de ellos se basa en los mismos fundamentos de `BarcodeGenerator` presentados aquí.

Siéntete libre de experimentar con distintas cadenas de datos, números de columnas y valores de X‑dimensión para adaptarlos a tu entorno de escaneo específico. ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo crear códigos de barras – PDF417 compacto con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cómo generar códigos de barras PDF417 – Codificación PDF417 compacto](/barcode/english/net/compact-pdf417-encoding/)
- [Cómo crear códigos de barras Aztec con Aspose.BarCode para .NET](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}