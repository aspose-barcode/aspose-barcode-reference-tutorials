---
category: general
date: 2026-07-18
description: Crea códigos de barras PDF417 rápidamente con C#. Aprende a generar el
  código de barras, establecer parámetros y guardar archivos de imagen – incluye manejo
  de AI 10.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate barcode
- how to set parameters
- how to save image
- barcode ai 10
language: es
lastmod: 2026-07-18
og_description: Crea un código de barras PDF417 en C# con una guía completa. Descubre
  cómo generar el código de barras, ajustar la configuración y guardar imágenes mientras
  manejas AI 10.
og_image_alt: Screenshot illustrating create pdf417 barcode code in C#
og_title: Crear código de barras PDF417 en C# – Ejemplo completo, rápido y flexible
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create PDF417 barcode quickly with C#. Learn how to generate barcode,
    set parameters, and save image files – includes AI 10 handling.
  headline: Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: Create PDF417 barcode quickly with C#. Learn how to generate barcode,
    set parameters, and save image files – includes AI 10 handling.
  name: Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  steps:
  - name: '**X‑dimension** – controls the width of the smallest bar (in pixels)'
    text: '**X‑dimension** – controls the width of the smallest bar (in pixels)'
  - name: '**Column count** – influences the overall shape; fewer columns = taller
      barcode'
    text: '**Column count** – influences the overall shape; fewer columns = taller
      barcode'
  - name: '**IsLinked** – enables the optional link module that ties the barcode to
      the data string'
    text: '**IsLinked** – enables the optional link module that ties the barcode to
      the data string'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspnet
- barcode-generation
title: Crear código de barras PDF417 en C# – Guía completa paso a paso
url: /es/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear código de barras PDF417 en C# – Guía completa paso a paso

¿Alguna vez necesitaste **crear código de barras pdf417** pero no estabas seguro de qué biblioteca o configuración elegir? No estás solo—muchos desarrolladores se topan con ese obstáculo cuando se aventuran por primera vez con GS1‑Micro‑PDF417. La buena noticia es que con unas pocas líneas de C# puedes generar un código de barras perfectamente formateado, ajustar su apariencia y guardar la imagen directamente en el disco.

En este tutorial recorreremos **cómo generar código de barras** usando la biblioteca Aspose.BarCode, mostraremos **cómo establecer parámetros** como X‑dimension y el recuento de columnas, y demostraremos **cómo guardar imagen** archivos para ambas variaciones AI 10 y AI 21. Al final tendrás un fragmento reutilizable que puedes insertar en cualquier proyecto .NET.

## Requisitos previos

- .NET 6+ o .NET Framework 4.7.2 (cualquier runtime reciente funciona)
- Visual Studio 2022 o tu editor favorito de C#
- El paquete NuGet **Aspose.BarCode for .NET** (`Install-Package Aspose.BarCode`)
- Una carpeta con permisos de escritura en el disco donde se guardarán los archivos PNG

Eso es todo—sin herramientas extra, sin configuración compleja. ¿Listo? Vamos.

## Paso 1: Crear código de barras PDF417 con formato GS1‑Micro

Lo primero que hacemos es crear el objeto **crear código de barras pdf417** y alimentarlo con los datos AI iniciales. En GS1‑Micro‑PDF417 el AI 10 (número de lote) suele ser el punto de partida, así que lo codificaremos de inmediato.

```csharp
using Aspose.BarCode.Generation;

// Define where the PNGs will be saved
string outputDir = @"C:\Barcodes\";

// Instantiate the generator for GS1‑Micro‑PDF417
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.GS1MicroPdf417,
    "(10)ABCD12345(240)ABCD");   // AI 10 + additional data
```

> **Por qué es importante:** El `EncodeTypes.GS1MicroPdf417` indica a la biblioteca que siga la especificación GS1‑Micro, lo que agrega automáticamente los corchetes del AI. Si omites esto, terminarás con un PDF417 genérico que puede no ser escaneable en entornos minoristas.

## Paso 2: Cómo establecer parámetros para el código de barras

Ahora que tenemos una instancia del código de barras, necesitamos afinar sus características visuales. Aquí es donde **cómo establecer parámetros** entra en juego. Ajustaremos tres configuraciones comunes:

1. **X‑dimension** – controla el ancho de la barra más pequeña (en píxeles)
2. **Column count** – influye en la forma general; menos columnas = código de barras más alto
3. **IsLinked** – habilita el módulo de enlace opcional que une el código de barras con la cadena de datos

```csharp
// X‑dimension: 2 pixels per module (good balance of size vs readability)
barcode.Parameters.Barcode.XDimension.Pixels = 2;

// Columns: 3 columns makes the barcode compact yet readable
barcode.Parameters.Barcode.Pdf417.Columns = 3;

// Enable linking (adds a special pattern that some scanners use)
barcode.Parameters.Barcode.Pdf417.IsLinked = true;
```

> **Consejo profesional:** Si apuntas a escaneo móvil, aumenta la X‑dimension a 3‑4 píxeles; los módulos más grandes sobreviven mejor a cámaras de baja resolución.

## Paso 3: Cómo guardar imagen – Primera versión (AI 10)

Con el generador configurado, finalmente podemos **cómo guardar imagen**. El método `Save` escribe el código de barras en un archivo con el formato que especifiques. Aquí usamos PNG porque preserva bordes nítidos sin artefactos de compresión.

```csharp
// Save the barcode that encodes AI 10
barcode.Save($"{outputDir}GS1MicroPdf417_AI10.png", BarCodeImageFormat.Png);
```

En este punto deberías ver un archivo llamado `GS1MicroPdf417_AI10.png` en tu `outputDir`. Ábrelo con cualquier visor de imágenes—verás un PDF417 limpio y de alto contraste listo para imprimir.

## Paso 4: Cambiar a un AI diferente (AI 21) y guardar de nuevo

A menudo necesitas codificar un identificador de aplicación diferente, como AI 21 (número de serie). Cambiar la propiedad `CodeText` es todo lo que se requiere. Esto demuestra el manejo de **barcode ai 10** frente a **barcode ai 21** en una sola operación.

```csharp
// Change the encoded data – now using AI 21
barcode.CodeText = "(21)ABCD12345(240)ABCD";

// Save the new variant
barcode.Save($"{outputDir}GS1MicroPdf417_AI21.png", BarCodeImageFormat.Png);
```

> **¿Qué pasa si necesitas más AIs?** Simplemente concaténalos en la misma cadena, por ejemplo, `"(10)ABCD(21)12345(240)XYZ"`. La biblioteca analiza los corchetes automáticamente.

## Ejemplo completo funcional

Juntándolo todo, aquí tienes un programa autocontenido que puedes copiar y pegar en una aplicación de consola:

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Output folder – change to suit your environment
        string outputDir = @"C:\Barcodes\";

        // 2️⃣ Create generator with initial AI 10 data
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.GS1MicroPdf417,
            "(10)ABCD12345(240)ABCD");

        // 3️⃣ Set visual parameters
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // how to set parameters
        barcode.Parameters.Barcode.Pdf417.Columns = 3;
        barcode.Parameters.Barcode.Pdf417.IsLinked = true;

        // 4️⃣ Save first image (AI 10)
        barcode.Save($"{outputDir}GS1MicroPdf417_AI10.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved AI 10 barcode.");

        // 5️⃣ Switch to AI 21 and save second image
        barcode.CodeText = "(21)ABCD12345(240)ABCD";
        barcode.Save($"{outputDir}GS1MicroPdf417_AI21.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved AI 21 barcode.");
    }
}
```

**Salida esperada:** Aparecen dos archivos PNG en `C:\Barcodes\`—`GS1MicroPdf417_AI10.png` y `GS1MicroPdf417_AI21.png`. Ambos contienen un PDF417 escaneable; el primero codifica AI 10, el segundo AI 21.

## Errores comunes y cómo evitarlos

- **Missing folder permissions:** Si `Save` lanza una `UnauthorizedAccessException`, verifica que la ruta exista y que tu aplicación tenga permisos de escritura.
- **Incorrect AI formatting:** Olvidar los paréntesis (`(10)`) hará que el código de barras se trate como datos simples, rompiendo la validación GS1.
- **Too small X‑dimension:** Barras más delgadas que 1 píxel pueden desaparecer al redimensionar la imagen. Mantén al menos 2 píxeles para visualización en pantalla.

## Próximos pasos y temas relacionados

Ahora que sabes **cómo generar código de barras**, **cómo establecer parámetros**, y **cómo guardar imagen**, podrías querer explorar:

- Añadir **texto legible por humanos** debajo del código de barras (`barcode.Parameters.Barcode.CodeTextLocation = CodeLocation.BelowBarcode`)
- Exportar a **PDF** en lugar de PNG (`BarCodeImageFormat.Pdf`)
- Integrar la generación de códigos de barras en una **ASP.NET Core API** para crear imágenes sobre la marcha

Cada uno de esos temas se basa directamente en la base que establecimos en esta guía.

---

### Resumen rápido

- **Create pdf417 barcode** usando `BarcodeGenerator` con `EncodeTypes.GS1MicroPdf417`
- **How to set parameters** como X‑dimension, columnas y enlace
- **How to save image** como PNG para ambas variantes AI 10 y AI 21
- Se manejó **barcode ai 10** y se cambió a **barcode ai 21** con un solo cambio de propiedad

Pruébalo, ajusta la configuración, y tendrás un motor de códigos de barras robusto listo para producción. ¿Tienes preguntas o necesitas profundizar? Deja un comentario abajo—¡feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo crear código de barras – PDF417 compacto con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cómo crear zona silenciosa de código de barras ITF-14 usando Aspose.BarCode para .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Cómo crear código de barras Aztec con corrección de errores en .NET](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}