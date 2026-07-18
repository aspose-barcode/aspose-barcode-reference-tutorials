---
category: general
date: 2026-07-18
description: Aprende cómo generar imágenes de códigos de barras con un generador de
  códigos de barras .NET y cambia fácilmente la altura del código de barras para los
  símbolos GS1‑Databar Omni‑Directional.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- .net barcode generator
- how to generate barcode
- change barcode height
- GS1‑Databar Omni‑Directional
- barcode image export
language: es
lastmod: 2026-07-18
og_description: El generador de códigos de barras .net le permite crear rápidamente
  imágenes de códigos de barras. Esta guía muestra cómo generar códigos de barras,
  ajustar la altura de las barras y guardar archivos PNG.
og_image_alt: Screenshot of a .net barcode generator output showing different bar
  heights
og_title: Cambiar la altura del código de barras con el generador de códigos de barras
  .net
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  headline: .net barcode generator – change barcode height
  type: TechArticle
- description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  name: .net barcode generator – change barcode height
  steps:
  - name: Why each line matters
    text: '| Line | Reason | |------|--------| | `BarcodeGenerator generator = new
      BarcodeGenerator(...);` | Instantiates the **.net barcode generator** with the
      desired symbology and data payload. The `EncodeTypes.DatabarOmniDirectional`
      enum tells the library to use the GS1‑Databar Omni‑Directional format. |'
  - name: Adjusting the X‑dimension for larger prints
    text: '```csharp generator.Parameters.Barcode.XDimension.Pixels = 4; // Double
      the narrow bar width ``` Increasing the X‑dimension makes the whole barcode
      larger without altering the encoded data. This is handy when you print on large
      labels.'
  - name: Switching output formats
    text: '```csharp generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
      ``` SVG scales infinitely, which is perfect for web‑based scanners that need
      crisp vectors.'
  - name: Adding human‑readable text
    text: '```csharp generator.Parameters.Barcode.CodeTextVisible = true; generator.Parameters.Barcode.CodeTextAlignment
      = CodeLocation.Below; ``` Enabling `CodeTextVisible` appends the raw data under
      the barcode, useful for verification during testing.'
  type: HowTo
tags:
- barcode
- .net
- image export
title: .NET generador de códigos de barras – cambiar la altura del código de barras
url: /es/python-java/general/net-barcode-generator-change-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .net barcode generator – cambiar la altura del código de barras

¿Alguna vez te has preguntado **cómo generar códigos de barras** sin tener que manejar una docena de herramientas de terceros? En el mundo .NET hay una forma sorprendentemente sencilla de hacerlo, y la pieza clave es el **.net barcode generator**. Con solo unas pocas líneas de C# puedes crear un símbolo GS1‑Databar Omni‑Directional, ajustar la altura de la barra y guardar el resultado en un archivo PNG.

Si estás construyendo un sistema de inventario, una impresora de etiquetas de envío, o cualquier aplicación que necesite un código escaneable, este tutorial te llevará de cero a un código de barras funcional en minutos. Revisaremos el código completo, explicaremos por qué cada configuración es importante y te mostraremos cómo **cambiar la altura del código de barras** sin romper la especificación.

## Lo que necesitarás

- .NET 6.0 o posterior (la API funciona igual en .NET Framework 4.7+)
- Una referencia a la biblioteca de códigos de barras (por ejemplo, Aspose.BarCode for .NET – las mismas clases son usadas por muchos kits comerciales)
- Un entorno de desarrollo (Visual Studio, Rider o VS Code con la extensión C#)
- Una carpeta donde tengas permiso de escritura – el tutorial guardará archivos PNG allí

Eso es todo. No se requieren paquetes NuGet adicionales más allá de la propia biblioteca de códigos de barras.

## Usando el .net barcode generator para cambiar la altura del código de barras

A continuación tienes un **programa de consola completo y ejecutable**. Pégalo en un nuevo proyecto C#, ajusta la carpeta de salida y pulsa F5.

```csharp
using System;
using Aspose.BarCode.Generation;   // Namespace for the barcode generator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a barcode generator for a GS1‑Databar Omni‑Directional symbol.
            // The string "(01)12345678901231" follows the GS1 Application Identifier syntax.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Define common visual parameters.
            // X‑dimension controls the width of the narrowest bar; 2 pixels works well for screen display.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set the initial bar height to 30 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Save the first image – a compact barcode.
            string outFolder = @"YOUR_DIRECTORY"; // ← replace with a real path
            generator.Save($"{outFolder}/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 5️⃣ Increase the bar height to 60 pixels for a larger, more readable code.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the second image – a taller barcode.
            generator.Save($"{outFolder}/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two barcode images have been generated successfully.");
        }
    }
}
```

### Por qué cada línea es importante

| Línea | Razón |
|------|--------|
| `BarcodeGenerator generator = new BarcodeGenerator(...);` | Instancia el **.net barcode generator** con la simbología y los datos deseados. El enumerado `EncodeTypes.DatabarOmniDirectional` indica a la biblioteca que use el formato GS1‑Databar Omni‑Directional. |
| `XDimension.Pixels = 2;` | La X‑dimension es el ancho de la barra más delgada. Configurarla a *2 píxeles* produce una imagen nítida en la mayoría de monitores mientras mantiene bajo el tamaño del archivo. |
| `BarHeight.Pixels = 30;` | Este es el paso de **cambiar la altura del código de barras** que determina cuán alta será cada barra. Una altura de 30 píxeles es un buen valor predeterminado para etiquetas pequeñas. |
| `generator.Save(...);` | Guarda el código de barras en un archivo PNG. PNG es sin pérdida, lo que significa que los escáneres ven el patrón exacto que generaste. |
| `BarHeight.Pixels = 60;` | Aquí **cambiamos la altura del código de barras** nuevamente—esta vez a 60 píxeles. La biblioteca vuelve a renderizar automáticamente el símbolo con la nueva dimensión cuando llamas a `Save` por segunda vez. |
| `Console.WriteLine(...);` | Te brinda una respuesta rápida de que el proceso terminó sin lanzar una excepción. |

> **Consejo profesional:** Si necesitas una salida de mayor resolución para impresión, cambia `BarCodeImageFormat.Png` a `BarCodeImageFormat.Tiff` y aumenta la propiedad `Resolution` (p. ej., `generator.Parameters.ImageResolution = 300;`). La altura de la barra seguirá respetándose, solo se renderizará a un DPI más fino.

## Cómo generar imágenes de códigos de barras con diferentes configuraciones

El fragmento anterior cubre lo básico, pero los escenarios del mundo real a menudo requieren ajustes adicionales:

### Ajustando la X‑dimension para impresiones más grandes
```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // Double the narrow bar width
```
Aumentar la X‑dimension hace que todo el código de barras sea más grande sin alterar los datos codificados. Es útil cuando imprimes en etiquetas grandes.

### Cambiando formatos de salida
```csharp
generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
```
SVG escala infinitamente, lo que es perfecto para escáneres basados en web que necesitan vectores nítidos.

### Añadiendo texto legible por humanos
```csharp
generator.Parameters.Barcode.CodeTextVisible = true;
generator.Parameters.Barcode.CodeTextAlignment = CodeLocation.Below;
```
Activar `CodeTextVisible` agrega los datos sin procesar bajo el código de barras, útil para verificación durante pruebas.

## Errores comunes al **cambiar la altura del código de barras**

1. **Altura demasiado pequeña** – Algunos escáneres requieren una altura mínima de barra (a menudo 10 mm en unidades físicas). Si estableces `BarHeight.Pixels` demasiado bajo, la imagen generada podría ser ilegible en un escáner real. Siempre prueba con tu hardware objetivo.
2. **Dimensión X y altura desajustadas** – Una altura de barra enorme combinada con una X‑dimension diminuta puede verse estirada y causar errores de decodificación. Busca una proporción equilibrada (aproximadamente 3:1 a 5:1) a menos que la especificación indique lo contrario.
3. **Olvidar restablecer los parámetros** – El generador mantiene el estado entre guardados. Si cambias `BarHeight` para una imagen y luego reutilizas la misma instancia para otro código de barras, la altura anterior permanecerá. Restablece la propiedad o instancia un nuevo `BarcodeGenerator` para cada código de barras distinto.

## Ejemplo completo de extremo a extremo (incluyendo instalación de NuGet)

Si estás comenzando desde cero, sigue estos pasos para poner en marcha el proyecto:

```bash
dotnet new console -n BarcodeHeightDemo
cd BarcodeHeightDemo
dotnet add package Aspose.BarCode
```

Reemplaza el `Program.cs` autogenerado con el bloque de código mostrado anteriormente, **recuerda reemplazar `YOUR_DIRECTORY`** con algo como `Path.Combine(Environment.CurrentDirectory, "output")`. Luego:

```bash
dotnet run
```

Deberías ver dos archivos PNG en la carpeta `output`:

- `DatabarBarHeight30Pixels.png` – un código de barras compacto de 30 píxeles de altura.
- `DatabarBarHeight60Pixels.png` – una versión más alta de 60 píxeles.

Ambas imágenes se verán similares, pero la segunda tendrá barras notablemente más largas, facilitando la lectura para escáneres de baja resolución.

![Barcode height example](/images/barcode-height.png){alt=".net barcode generator output mostrando diferentes alturas de barra"}

## Recapitulación y próximos pasos

Hemos cubierto cómo **generar códigos de barras** usando un **.net barcode generator**, afinado la propiedad **cambiar la altura del código de barras**, y guardado los resultados en formato PNG. Los puntos clave son:

- Instanciar el generador con el `EncodeTypes` correcto.
- Controlar el tamaño visual mediante `XDimension` y `BarHeight`.
- Llamar a `Save` después de cada cambio para persistir una nueva imagen.
- Ajustar la resolución, el formato,

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo generar códigos de barras Aztec con relación de aspecto personalizada usando Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Cómo crear texto de código extendido dotcode con Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Cómo generar códigos de barras DataMatrix (ECC 200) con Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}