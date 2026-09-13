---
category: general
date: 2026-09-13
description: Aprende a generar códigos de barras en C#, personalizar el tamaño del
  código de barras y guardar la imagen del código de barras como PNG usando Aspose.BarCode.
  Guía completa paso a paso.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- custom barcode size
- save barcode image
- Aspose.BarCode C#
- barcode image format
language: es
lastmod: 2026-09-13
og_description: Cómo generar un código de barras en C# con tamaño de código de barras
  personalizado y guardar la imagen del código de barras como PNG. Sigue esta guía
  completa para Aspose.BarCode.
og_image_alt: Screenshot of a DataBar stacked omnidirectional barcode generated in
  C#
og_title: Cómo generar un código de barras, establecer un tamaño personalizado y guardar
  la imagen en C#
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to generate barcode in C#, customize barcode size, and save
    barcode image as PNG using Aspose.BarCode. Complete step‑by‑step guide.
  headline: How to generate barcode set custom size and save image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Cómo generar códigos de barras, establecer un tamaño personalizado y guardar
  la imagen en C#
url: /es/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo generar códigos de barras con tamaño personalizado y guardar la imagen en C#

Si necesitas **cómo generar códigos de barras** en una aplicación .NET, este tutorial te muestra una solución completa. Verás cómo ajustar el **tamaño personalizado del código de barras** y **guardar la imagen del código de barras** con solo unas pocas líneas de código C#.

Generar códigos de barras es un requisito común para sistemas de inventario, etiquetas de envío y aplicaciones de punto de venta. Al final de esta guía tendrás un programa ejecutable que crea dos códigos de barras DataBar‑Stacked‑Omnidirectional, cada uno con una relación de aspecto diferente, y los escribe en archivos PNG en el disco.

**Prerequisitos**

- .NET 6.0 o posterior (el código también funciona con .NET Framework 4.7+)
- Visual Studio 2022 o cualquier IDE de C#
- Aspose.BarCode for .NET (prueba gratuita o paquete NuGet con licencia)

---

## Cómo generar códigos de barras con Aspose.BarCode

La biblioteca Aspose.BarCode abstrae los detalles de bajo nivel de los estándares de códigos de barras, permitiéndote centrarte en los datos que deseas codificar y en la apariencia visual que necesitas.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar stacked omnidirectional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GS1‑128 format example

        // 2️⃣ Set a basic module width – this influences the overall **custom barcode size**
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First aspect ratio (15) → save the image
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // 4️⃣ Change aspect ratio to 30 → **save barcode image** again
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### Por qué cada línea importa

| Paso | Explicación |
|------|-------------|
| **1️⃣ Crear un generador** | El enum `EncodeTypes.DatabarStackedOmniDirectional` indica a Aspose qué simbología de código de barras usar. La cadena `"(01)12345678901231"` sigue el formato de datos GS1‑128, donde `(01)` es el Identificador de Aplicación para un GTIN. |
| **2️⃣ Establecer X‑dimension** | `XDimension.Pixels` define el ancho de un solo módulo del código de barras (la barra más pequeña). Cambiar este valor es la forma principal de lograr un **tamaño personalizado del código de barras** sin alterar los datos codificados. |
| **3️⃣ Establecer relación de aspecto y guardar** | `DataBar.AspectRatio` controla la relación altura‑ancho de los símbolos DataBar. Una relación de aspecto de 15 produce un código de barras relativamente corto y ancho, mientras que 30 lo hace más alto. `Save` escribe la representación visual en un archivo PNG, cumpliendo el requisito de **guardar la imagen del código de barras**. |
| **4️⃣ Cambiar la relación de aspecto y guardar de nuevo** | Reutilizar la misma instancia del generador te permite producir múltiples imágenes con diferentes características visuales manteniendo los datos constantes. |

---

## Ajustar el tamaño personalizado del código de barras más allá de X‑dimension

Aunque `XDimension.Pixels` establece el ancho del módulo, también puedes afinar las dimensiones generales del código de barras combinando dos propiedades:

1. **`BarHeight`** – altura explícita en píxeles.  
2. **`BarWidth`** – ancho explícito en píxeles (sobrescribe X‑dimension).

```csharp
// Example: make a larger, more readable barcode
generator.Parameters.Barcode.XDimension.Pixels = 4;      // wider modules
generator.Parameters.Barcode.BarHeight.Pixels = 120;    // taller bars
generator.Parameters.Barcode.DataBar.AspectRatio = 20; // balanced ratio
generator.Save("LargeCustomSize.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved large custom size barcode.");
```

> **Pro tip:** Al imprimir códigos de barras, siempre prueba la imagen generada al tamaño final de impresión. Un ancho de módulo de 2 px funciona para visualización en pantalla, pero las etiquetas impresas a menudo requieren al menos 4 px para seguir siendo escaneables.

---

## Elegir el formato de imagen correcto para guardar el código de barras

Aspose.BarCode admite PNG, JPEG, BMP, GIF y TIFF. PNG es sin pérdida y preserva bordes nítidos, lo que lo convierte en la opción más segura para la mayoría de las aplicaciones. Si necesitas un archivo más pequeño para la web, JPEG con una calidad del 90 funciona bien, pero ten en cuenta que los artefactos de compresión pueden afectar la fiabilidad del escaneo.

```csharp
generator.Save("DatabarAspectRatio15.jpg", BarCodeImageFormat.Jpeg, 90);
Console.WriteLine("Saved JPEG version with quality 90.");
```

---

## Ejemplo completo y ejecutable

A continuación se muestra una aplicación de consola autocontenida que puedes copiar, pegar y ejecutar. Demuestra **cómo generar códigos de barras**, modificar el **tamaño personalizado del código de barras** y **guardar la imagen del código de barras** en dos formatos diferentes.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with the desired symbology and data
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // ---- Custom size configuration ----
            generator.Parameters.Barcode.XDimension.Pixels = 2;      // module width
            generator.Parameters.Barcode.BarHeight.Pixels = 80;    // optional explicit height
            generator.Parameters.Barcode.DataBar.AspectRatio = 15; // first aspect ratio

            // Save first image as PNG
            string pngPath1 = "DatabarAspectRatio15.png";
            generator.Save(pngPath1, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath1}");

            // Change aspect ratio for a taller barcode
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string pngPath2 = "DatabarAspectRatio30.png";
            generator.Save(pngPath2, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath2}");

            // ---- Larger custom size example ----
            generator.Parameters.Barcode.XDimension.Pixels = 4;
            generator.Parameters.Barcode.BarHeight.Pixels = 120;
            generator.Parameters.Barcode.DataBar.AspectRatio = 20;
            string largePath = "LargeCustomSize.png";
            generator.Save(largePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {largePath}");

            // ---- Save as JPEG for web use ----
            string jpegPath = "DatabarAspectRatio15.jpg";
            generator.Save(jpegPath, BarCodeImageFormat.Jpeg, 90);
            Console.WriteLine($"Saved {jpegPath}");
        }
    }
}
```

**Salida esperada en la consola**

```
Saved DatabarAspectRatio15.png
Saved DatabarAspectRatio30.png
Saved LargeCustomSize.png
Saved DatabarAspectRatio15.jpg
```

Los cuatro archivos de imagen aparecerán en el programa


## ¿Qué deberías aprender a continuación?


Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo generar códigos de barras DataMatrix usando Aspose.BarCode para .NET – Guía paso a paso](/barcode/english/net/datamatrix-barcode-configuration/)
- [Cómo generar código de barras PDF417 con Aspose – Guía completa](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Cómo generar código de barras Aztec con relación de aspecto personalizada usando Aspose.BarCode para .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}