---
category: general
date: 2026-11-20
description: Aprende a generar códigos de barras PDF417 en C# usando BarcodeGenerator.
  Esta guía paso a paso cubre la dimensión X, la configuración de columnas y la exportación
  a PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- PDF417 barcode in C#
- BarcodeGenerator EncodeTypes
- set XDimension pixels
- configure PDF417 columns
- save barcode as PNG
language: es
lastmod: 2026-11-20
og_description: Genera códigos de barras PDF417 en C# rápidamente. Sigue esta guía
  para establecer dimensiones, columnas y exportar el código de barras como una imagen
  PNG.
og_image_alt: Screenshot of C# code that generates a PDF417 barcode and saves it as
  a PNG file
og_title: Generar código de barras PDF417 en C# – guía completa paso a paso
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to generate PDF417 barcode in C# using BarcodeGenerator.
    This step‑by‑step guide covers X‑Dimension, column settings, and PNG export.
  headline: How to generate PDF417 barcode in C# with BarcodeGenerator
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using BarcodeGenerator.
    This step‑by‑step guide covers X‑Dimension, column settings, and PNG export.
  name: How to generate PDF417 barcode in C# with BarcodeGenerator
  steps:
  - name: '**Initialize the generator** – The `BarcodeGenerator` ties the chosen symbology
      (`EncodeTypes.Pdf417`) to the data you want to encode. Without this object you
      cannot access any further configuration.'
    text: '**Initialize the generator** – The `BarcodeGenerator` ties the chosen symbology
      (`EncodeTypes.Pdf417`) to the data you want to encode. Without this object you
      cannot access any further configuration.'
  - name: '**Set X‑Dimension** – PDF417 is built from tiny rectangular modules. Changing
      `XDimension.Pixels` lets you control the barcode’s visual density, which is
      crucial for readability on low‑resolution displays or printers.'
    text: '**Set X‑Dimension** – PDF417 is built from tiny rectangular modules. Changing
      `XDimension.Pixels` lets you control the barcode’s visual density, which is
      crucial for readability on low‑resolution displays or printers.'
  - name: '**Configure columns** – PDF417 can arrange its codewords in a variable
      number of columns. Fewer columns produce a taller barcode, while more columns
      flatten it. Adjust this to fit the space where the image will be placed.'
    text: '**Configure columns** – PDF417 can arrange its codewords in a variable
      number of columns. Fewer columns produce a taller barcode, while more columns
      flatten it. Adjust this to fit the space where the image will be placed.'
  - name: '**Save as PNG** – PNG is a loss‑less format, preserving the sharp edges
      required for accurate scanning. You could also choose JPEG or BMP, but PNG is
      the safest default.'
    text: '**Save as PNG** – PNG is a loss‑less format, preserving the sharp edges
      required for accurate scanning. You could also choose JPEG or BMP, but PNG is
      the safest default.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose.BarCode
title: Cómo generar código de barras PDF417 en C# con BarcodeGenerator
url: /es/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo generar código de barras PDF417 en C# con BarcodeGenerator

Si necesitas **generar código de barras PDF417** en una aplicación .NET, esta guía te muestra exactamente cómo hacerlo. Verás un ejemplo completo y ejecutable que establece la X‑Dimension, elige el número de columnas y guarda el resultado como una imagen PNG.

Generar un código de barras PDF417 es común cuando tienes que codificar una gran cantidad de datos —como una licencia de conducir, una tarjeta de embarque o un registro de inventario— en una imagen compacta y legible por máquinas. En este tutorial utilizamos la clase **BarcodeGenerator** de la biblioteca Aspose.BarCode, pero los conceptos se aplican a cualquier biblioteca que admita PDF417.

Al final de este artículo podrás:

* Inicializar un `BarcodeGenerator` para codificación PDF417.  
* Ajustar el tamaño del módulo con **set XDimension pixels**.  
* Controlar el diseño usando **configure PDF417 columns**.  
* **Guardar código de barras como PNG** para usar en páginas web, aplicaciones móviles o material impreso.  

> **Prerequisitos**  
> * .NET 6.0 o posterior (el código también funciona con .NET Framework 4.7+).  
> * Una referencia al paquete NuGet **Aspose.BarCode** (`Install-Package Aspose.BarCode`).  
> * Familiaridad básica con C# y Visual Studio (o cualquier IDE que prefieras).

---

## Cómo generar código de barras PDF417 en C#

El núcleo de la solución es un proceso breve de cuatro pasos. Cada paso está encapsulado en un método dedicado para que puedas reutilizar la lógica en proyectos más grandes.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialize the generator with the desired text
            var generator = CreateGenerator("Åspóse.Barcóde©");

            // 2️⃣ Adjust the X‑Dimension (module size)
            SetXDimension(generator, 2);

            // 3️⃣ Define how many columns the barcode should have
            SetPdf417Columns(generator, 3);

            // 4️⃣ Save the barcode as a PNG file
            SaveAsPng(generator, @"YOUR_DIRECTORY\Pdf417Basic.png");

            Console.WriteLine("PDF417 barcode generated successfully.");
        }

        // ---------------------------------------------------------
        // Step 1: Create a BarcodeGenerator for PDF417
        // ---------------------------------------------------------
        private static BarcodeGenerator CreateGenerator(string text)
        {
            // EncodeTypes.Pdf417 tells the library to use the PDF417 symbology.
            return new BarcodeGenerator(EncodeTypes.Pdf417, text);
        }

        // ---------------------------------------------------------
        // Step 2: Set the X‑Dimension (size of a single module)
        // ---------------------------------------------------------
        private static void SetXDimension(BarcodeGenerator generator, int pixels)
        {
            // XDimension controls the width of the smallest black/white bar.
            // A value of 2 pixels works well for most screen resolutions.
            generator.Parameters.Barcode.XDimension.Pixels = pixels;
        }

        // ---------------------------------------------------------
        // Step 3: Configure the number of columns in the PDF417 barcode
        // ---------------------------------------------------------
        private static void SetPdf417Columns(BarcodeGenerator generator, int columns)
        {
            // Columns affect the barcode’s aspect ratio.
            // Small numbers (e.g., 3) produce a tall barcode; larger numbers make it wider.
            generator.Parameters.Barcode.Pdf417.Columns = columns;
        }

        // ---------------------------------------------------------
        // Step 4: Export the barcode as a PNG image
        // ---------------------------------------------------------
        private static void SaveAsPng(BarcodeGenerator generator, string outputPath)
        {
            // BarCodeImageFormat.Png ensures lossless quality.
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Por qué importan estos cuatro pasos

1. **Initialize the generator** – El `BarcodeGenerator` vincula la simbología elegida (`EncodeTypes.Pdf417`) con los datos que deseas codificar. Sin este objeto no puedes acceder a ninguna configuración adicional.  
2. **Set X‑Dimension** – PDF417 se construye a partir de pequeños módulos rectangulares. Cambiar `XDimension.Pixels` te permite controlar la densidad visual del código de barras, lo cual es crucial para la legibilidad en pantallas o impresoras de baja resolución.  
3. **Configure columns** – PDF417 puede organizar sus codewords en un número variable de columnas. Menos columnas generan un código de barras más alto, mientras que más columnas lo aplanan. Ajusta esto para que encaje en el espacio donde se colocará la imagen.  
4. **Save as PNG** – PNG es un formato sin pérdida, que preserva los bordes nítidos necesarios para un escaneo preciso. También podrías elegir JPEG o BMP, pero PNG es la opción predeterminada más segura.

---

## Configurar dimensiones del código de barras (X‑Dimension)

El paso **set XDimension pixels** influye directamente en cómo los escáneres interpretan el código de barras. Si el módulo es demasiado pequeño, cámaras de baja calidad pueden pasar por alto barras individuales; si es demasiado grande, el código de barras puede volverse innecesariamente grande.

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 2; // 2‑pixel modules
```

**Mejor práctica:** Prueba la imagen generada al tamaño de impresión previsto. Para impresión de alta densidad (300 dpi o más), un valor de `1` o `2` funciona bien. Para visualización en pantalla a 96 dpi, `2`–`3` brinda una visual clara.

---

## Establecer columnas PDF417

El paso **configure PDF417 columns** te permite decidir la forma del código de barras.

```csharp
generator.Parameters.Barcode.Pdf417.Columns = 3; // three columns → tall barcode
```

### Cuándo cambiar el número de columnas

| Columnas | Forma resultante | Caso de uso típico |
|----------|------------------|--------------------|
| 1–3      | Alto, estrecho   | Etiquetas con ancho limitado |
| 4–9      | Equilibrado      | Escaneo de propósito general |
| 10+      | Ancho, corto     | Señalización grande o gráficos web |

Si la carga de datos supera la capacidad predeterminada, la biblioteca agrega automáticamente filas extra, pero aún puedes influir en la relación de aspecto ajustando el número de columnas.

---

## Exportar código de barras a PNG

Guardar el código de barras como una imagen PNG es sencillo:

```csharp
generator.Save(@"C:\Barcodes\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**¿Por qué PNG?**  
* La compresión sin pérdida conserva los bordes nítidos necesarios para los lectores de códigos de barras.  
* PNG soporta transparencia, lo que puede ser útil si superpones el código de barras sobre un fondo de color más adelante.

Si necesitas un formato diferente, reemplaza `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` o `Svg`; la API maneja la conversión automáticamente.

---

## Problemas comunes y solución de errores

| Problema | Causa probable | Solución |
|----------|----------------|----------|
| El código de barras aparece borroso | X‑Dimension demasiado pequeño para la resolución de salida | Aumenta `XDimension.Pixels` a 3 o 4. |
| El escáner no puede leer el código | Caracteres Unicode no soportados por la fuente elegida | Asegúrate de que la fuente de la biblioteca soporte los caracteres, o reemplázalos por equivalentes ASCII. |
| El archivo de salida no se crea | Ruta inválida o permisos de escritura faltantes | Usa una ruta absoluta y verifica el acceso de escritura a la carpeta. |
| Demasiadas filas, el código de barras se vuelve alto | Número de columnas demasiado bajo para la longitud de los datos | Aumenta `Pdf417.Columns` a un número mayor (p.ej., 6). |

---

## Recapitulación del ejemplo completo

A continuación se muestra el **programa completo** que puedes copiar y pegar en un nuevo proyecto de consola. No se requiere código adicional más allá de las sentencias `using` y el paquete Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
            Console.WriteLine("PDF417 barcode generated and saved as PNG.");
        }
    }
}
```

**Salida esperada:** Un archivo llamado `Pdf417Basic.png` que contiene un código de barras PDF417 claro que codifica la cadena `Åspóse.Barcóde©`. Al abrirlo, la imagen debe mostrar una serie de barras rectangulares apiladas con una densidad mayor en el lado izquierdo (debido al diseño de tres columnas).

---

## Conclusión

Ahora sabes cómo **generar código de barras PDF417** en C# usando la clase `BarcodeGenerator`. El tutorial cubrió la inicialización del generador, **set XDimension pixels**, **configure PDF417 columns**, y **save barcode as PNG**, los pasos esenciales para cualquier flujo de trabajo de códigos de barras listo para producción.

Desde aquí puedes:

* Experimentar con diferentes `EncodeTypes` (p.ej., QR, Code128).  
* Añadir niveles de corrección de errores mediante `generator.Parameters.Barcode.Pdf417.ErrorLevel`.  
* Renderizar el código de barras directamente a un `MemoryStream` para APIs web.  

Siéntete libre de adaptar el código a tu propio proyecto y compartir tus resultados en los comentarios o en Stack Overflow usando la etiqueta `#pdf417`. ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Generar código de barras PDF417 como PNG en C# – guía paso a paso](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-as-png-in-c-step-by-step-guide/)
- [Cómo generar código de barras PDF417 en C# – guía paso a paso](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [Cómo generar código de barras PDF417 en C# con dimensiones personalizadas](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}