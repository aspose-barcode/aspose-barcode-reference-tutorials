---
category: general
date: 2026-11-14
description: Crear código de barras micro PDF417 en C# con Aspose.BarCode – guía paso
  a paso que cubre la configuración del generador, la dimensión X, las columnas y
  la exportación a PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- micro pdf417 barcode generator
- set XDimension pixels
- define barcode columns
- save barcode as PNG
- Aspose.BarCode C# example
language: es
lastmod: 2026-11-14
og_description: Crea un código de barras micro PDF417 en C# usando Aspose.BarCode.
  Aprende a configurar el generador, establecer XDimension, elegir columnas y exportar
  como PNG.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Crear código de barras micro PDF417 en C# – guía completa de programación
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  headline: How to create micro PDF417 barcode in C#
  type: TechArticle
- description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  name: How to create micro PDF417 barcode in C#
  steps:
  - name: Open the PNG in an image viewer.
    text: Open the PNG in an image viewer.
  - name: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
    text: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
  - name: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
    text: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
- image generation
title: Cómo crear un código de barras micro PDF417 en C#
url: /es/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear micro PDF417 barcode en C#  

Si necesitas **crear micro PDF417 barcode** rápidamente, esta guía te muestra una solución completa y lista‑para‑ejecutar. Verás cómo instanciar el generador de códigos de barras, configurar la X‑dimension, elegir el número de columnas y, finalmente, guardar el resultado como una imagen PNG, todo usando la biblioteca Aspose.BarCode para .NET.

Generar un micro PDF417 barcode no requiere una canalización de compilación compleja. Al final de este tutorial tendrás un único archivo C# que produce una imagen de código de barras de alta calidad que puedes incrustar en informes, etiquetas o aplicaciones móviles.

## Requisitos previos  

* .NET 6.0 SDK o posterior (el código también funciona con .NET Framework 4.7+).  
* Un entorno de desarrollo como Visual Studio 2022, VS Code o Rider.  
* Una licencia de Aspose.BarCode para .NET (o una clave de evaluación gratuita). Puedes obtenerla en el [Aspose website](https://purchase.aspose.com/barcode/net).  

> **Consejo profesional:** Si estás usando la versión de evaluación, el PNG generado contendrá una pequeña marca de agua “Evaluation”. Una versión con licencia la elimina automáticamente.

## Paso 1: Configurar el proyecto  

Crea un nuevo proyecto de consola y agrega el paquete NuGet Aspose.BarCode.

```bash
dotnet new console -n MicroPdf417Demo
cd MicroPdf417Demo
dotnet add package Aspose.BarCode --version 24.9.0
```

El comando `dotnet add package` descarga las dependencias del **Ejemplo Aspose.BarCode C#**, por lo que no tienes que gestionar los DLL manualmente.

## Paso 2: Escribir el código completo  

Reemplaza el `Program.cs` autogenerado con el siguiente código. Demuestra cómo **crear micro pdf417 barcode** de principio a fin.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text.
            // The text can contain Unicode characters; here we use a sample string.
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Åspóse.Barcóde©");

            // 2️⃣ Set the X‑dimension (module width) in pixels.
            // This determines the width of the smallest element (a bar or a space).
            generator.Parameters.Barcode.XDimension.Pixels = 2; // secondary keyword: set XDimension pixels

            // 3️⃣ Define the number of columns (allowed values: 1‑4 for MicroPDF417).
            // More columns mean a wider barcode but fewer rows, which can improve readability.
            generator.Parameters.Barcode.Pdf417.Columns = 4; // secondary keyword: define barcode columns

            // 4️⃣ Choose the output format and save the barcode as a PNG image.
            // PNG preserves the sharp edges of the barcode, which is ideal for scanning.
            string outputPath = "MicroPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png); // secondary keyword: save barcode as PNG

            Console.WriteLine($"Micro PDF417 barcode saved to {outputPath}");
        }
    }
}
```

### Por qué cada línea es importante  

* **BarcodeGenerator constructor** – Instancia el **micro pdf417 barcode generator** con el texto que deseas codificar.  
* **XDimension.Pixels** – Controla el ancho del módulo; establecerlo en `2` píxeles produce un código de barras denso y de alta resolución adecuado para la mayoría de los escáneres.  
* **Pdf417.Columns** – MicroPDF417 soporta solo 1‑4 columnas. Elegir `4` reduce la altura del código de barras, lo que es útil cuando tienes espacio vertical limitado.  
* **Save method** – Escribe el código de barras en un archivo PNG. PNG es sin pérdida, asegurando que el escáner lea el patrón exacto que generaste.

## Paso 3: Compilar y ejecutar  

Compila y ejecuta el programa:

```bash
dotnet run
```

Deberías ver la salida en la consola:

```
Micro PDF417 barcode saved to MicroPdf417.png
```

Un archivo llamado **MicroPdf417.png** aparece en la carpeta del proyecto. Ábrelo con cualquier visor de imágenes; verás un nítido micro PDF417 barcode que codifica la cadena `"Åspóse.Barcóde©"`.

![Ejemplo de micro PDF417 barcode generado](MicroPdf417.png "Ejemplo de micro PDF417 barcode generado"){.center-image width=400 alt="Ejemplo de imagen de micro PDF417 barcode generado"}

*La imagen anterior es el resultado del código mostrado en el Paso 2.*

## Paso 4: Variaciones comunes y casos límite  

| Situación | Cómo adaptar el código |
|-----------|------------------------|
| **Longitud de datos diferente** | MicroPDF417 puede codificar hasta 1 200 caracteres. Simplemente cambia el segundo argumento de `BarcodeGenerator`. |
| **Resolución más alta** | Aumenta `XDimension.Pixels` a `3` o `4`. Los módulos más grandes mejoran la legibilidad en escáneres de baja resolución pero aumentan el tamaño de la imagen. |
| **Colores personalizados** | Después de crear el generador, establece `generator.Parameters.Barcode.BarcodeColor = Color.Blue;` y `generator.Parameters.Barcode.BackgroundColor = Color.White;`. |
| **Guardar en otros formatos** | Reemplaza `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` o `Gif` según tus requisitos posteriores. |
| **Incrustar en un PDF** | Utiliza `generator.Save("barcode.pdf", BarCodeImageFormat.Pdf);` y luego combina el PDF con otros documentos usando Aspose.PDF. |

> **Cuidado con:** Establecer `XDimension.Pixels` por debajo de `1` lanza una `ArgumentOutOfRangeException`. Siempre mantenlo en `1` o superior.

## Paso 5: Verificar el código de barras  

Para asegurarte de que el código de barras se escanee correctamente:

1. Abre el PNG en un visor de imágenes.  
2. Usa cualquier aplicación de escaneo de códigos de barras para smartphone que soporte PDF417 (la mayoría de las apps “escáner de QR” lo incluyen).  
3. Escanea la imagen; la app debería mostrar el texto original `"Åspóse.Barcóde©"`.

Si el escaneo falla, verifica nuevamente la **X‑dimension** y la configuración de **columnas**: un ancho de módulo demasiado pequeño o un número de columnas no soportado pueden hacer que el patrón sea ilegible.

## Conclusión  

Ahora sabes cómo **crear micro pdf417 barcode** en C# usando Aspose.BarCode. El tutorial cubrió:

* Instanciar un **micro pdf417 barcode generator**.  
* **Establecer XDimension en píxeles** para controlar el ancho del módulo.  
* **Definir columnas del código de barras** para ajustar la forma.  
* **Guardar el código de barras como PNG** para una salida de imagen sin pérdida.  

A partir de aquí puedes explorar funciones adicionales como la personalización de colores, incrustar el código de barras en PDFs o generar códigos de barras sobre la marcha en APIs web ASP.NET Core. ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Crear código de barras PNG en C# – guía completa de GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [Cómo crear macro PDF417 barcode en C# usando Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Crear código de barras PDF417 en C# usando Aspose.BarCode – guía paso a paso](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}