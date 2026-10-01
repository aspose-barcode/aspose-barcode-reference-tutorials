---
category: general
date: 2026-08-12
description: Crear imagen de código de barras en C# usando BarCodeGenerator. Aprende
  a generar DataBar, controlar el tamaño de la imagen del código de barras y crear
  múltiples códigos de barras de forma eficiente.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- create multiple barcodes
- how to generate databar
- barcode image size
language: es
lastmod: 2026-08-12
og_description: Crea una imagen de código de barras en C# con BarCodeGenerator. Este
  tutorial muestra paso a paso cómo generar códigos DataBar, ajustar el tamaño de
  la imagen del código de barras y producir múltiples códigos de barras.
og_image_alt: Screenshot of a generated DataBar barcode image saved as PNG
og_title: Crear imagen de código de barras en C# – guía completa de BarCodeGenerator
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  headline: Create barcode image in C# with BarCodeGenerator
  type: TechArticle
- description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  name: Create barcode image in C# with BarCodeGenerator
  steps:
  - name: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
    text: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
  - name: Adjusting **barcode image size** by changing X‑dimension and bar height.
    text: Adjusting **barcode image size** by changing X‑dimension and bar height.
  - name: Using a loop to **create multiple barcodes** with different heights.
    text: Using a loop to **create multiple barcodes** with different heights.
  - name: Saving the images as PNG files and verifying the output.
    text: Saving the images as PNG files and verifying the output.
  type: HowTo
tags:
- barcode
- csharp
- barcodegenerator
- databar
- image-processing
title: Crear imagen de código de barras en C# con BarCodeGenerator
url: /es/python-java/general/create-barcode-image-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear imagen de código de barras en C# con BarCodeGenerator

Si necesitas **crear una imagen de código de barras** en una aplicación .NET, esta guía te muestra exactamente cómo hacerlo con la clase `BarCodeGenerator`. Ya sea que estés construyendo un sistema POS minorista o una herramienta de seguimiento de inventario, aprenderás a generar símbolos DataBar, controlar el tamaño de la imagen del código de barras y producir varios códigos de barras en una sola ejecución.

También descubrirás cómo la API **barcode generator c#** te permite ajustar dimensiones, cambiar formatos de salida y manejar casos límite como cadenas de datos inválidas. Al final del tutorial podrás **crear múltiples códigos de barras** con confianza sin escribir código repetitivo.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

- .NET 6.0 o posterior instalado  
- Un entorno de desarrollo (Visual Studio, Rider o VS Code)  
- El paquete NuGet Aspose.BarCode for .NET (o cualquier biblioteca compatible que proporcione `BarCodeGenerator`)  

Puedes agregar el paquete con:

```bash
dotnet add package Aspose.BarCode
```

## Qué cubre este tutorial

1. Configurar una instancia de **barcode generator c#** para la codificación DataBar Omni‑directional.  
2. Ajustar el **barcode image size** cambiando la X‑dimension y la altura de la barra.  
3. Usar un bucle para **create multiple barcodes** con diferentes alturas.  
4. Guardar las imágenes como archivos PNG y verificar la salida.  

Todas las fragmentos de código están completos y listos para copiar y pegar en un nuevo proyecto de consola.

![Ejemplo de creación de imagen de código de barras](barcode-example.png){alt="Ejemplo de creación de imagen de código de barras"}

## Paso 1: Inicializar el generador – conceptos básicos de creación de imagen de código de barras

El primer paso es instanciar `BarCodeGenerator` con la simbología deseada. Para un símbolo DataBar Omni‑directional utilizas `EncodeTypes.DatabarOmniDirectional`.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for DataBar Omni‑directional.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarCodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // The rest of the steps are performed below.
        }
    }
}
```

**Por qué es importante:** Instanciar el generador define las reglas de codificación y la carga de datos. Si omites el valor correcto de `EncodeTypes`, la biblioteca producirá un código de barras no compatible o lanzará una excepción.

## Paso 2: Configurar X‑dimension y altura de la barra – controlar el tamaño de la imagen del código de barras

El tamaño visual de un código de barras está determinado por dos parámetros:

| Parámetro | Qué controla | Rango típico |
|-----------|--------------|--------------|
| `x_dimension.pixels` | Ancho del módulo más pequeño (el “punto”) | 1 – 4 px |
| `bar_height.pixels`  | Altura de las barras verticales | 30 – 150 px |

```csharp
// Set the module width to 2 px for a crisp, readable image.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set an initial bar height of 30 px.
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

**Consejo profesional:** Una X‑dimension más pequeña produce una imagen de mayor resolución pero puede ser más difícil de escanear en impresoras de baja calidad. Ajusta el valor según el equipo de escaneo objetivo.

## Paso 3: Guardar el primer código de barras – crear imagen de código de barras para altura de 30 px

Ahora puedes generar la imagen y escribirla en disco. El método `Save` acepta una ruta de archivo y un enum de formato de imagen.

```csharp
// Save the 30 px high barcode as a PNG file.
string outputFolder = @"C:\Barcodes";
generator.Save($"{outputFolder}\\Databar30.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar30.png (30 px height)");
```

**Resultado esperado:** Aparece un archivo PNG llamado `Databar30.png` en `C:\Barcodes`. Al abrir el archivo se muestra un símbolo DataBar Omni‑directional con un patrón claro y de alto contraste.

## Paso 4: Cambiar la altura y generar imágenes adicionales – crear múltiples códigos de barras

Para **create multiple barcodes** con diferentes dimensiones solo necesitas modificar la propiedad `BarHeight` y llamar a `Save` nuevamente. Esto evita volver a instanciar el generador, lo que ahorra memoria y tiempo de CPU.

```csharp
// Increase the bar height to 60 px for a larger barcode.
generator.Parameters.Barcode.BarHeight.Pixels = 60;
generator.Save($"{outputFolder}\\Databar60.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar60.png (60 px height)");

// You can repeat the process for any height you need.
int[] heights = { 90, 120 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputFolder}\\Databar{h}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved Databar{h}.png ({h} px height)");
}
```

**Por qué funciona:** El objeto `BarCodeGenerator` mantiene todo el estado de configuración. Cambiar una sola propiedad actualiza el motor de renderizado para la siguiente llamada a `Save`, permitiéndote **create multiple barcodes** de manera eficiente.

## Paso 5: Avanzado – cómo generar DataBar con datos personalizados

El ejemplo anterior usa una carga útil GS1 estática. En escenarios del mundo real a menudo necesitas incrustar identificadores de producto variables. La biblioteca acepta cualquier cadena que coincida con la especificación DataBar.

```csharp
string[] gtins = { "01234567890123", "98765432109876", "12345678901234" };
foreach (var gtin in gtins)
{
    // GS1 Application Identifier (01) + GTIN
    generator.CodeText = $"(01){gtin}";
    generator.Parameters.Barcode.BarHeight.Pixels = 50; // uniform height
    generator.Save($"{outputFolder}\\Databar_{gtin}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode for GTIN {gtin}");
}
```

**Punto clave:** Establecer `generator.CodeText` actualiza los datos codificados sin recrear el objeto. Este es el patrón recomendado de **how to generate databar** al manejar grandes conjuntos de datos.

## Paso 6: Verificar y solucionar problemas – asegurando el tamaño correcto de la imagen del código de barras

Después de generar las imágenes, puede que quieras confirmar programáticamente que las dimensiones coinciden con tus expectativas. La clase `Image` de `System.Drawing` puede leer el archivo y reportar su tamaño.

```csharp
using System.Drawing;

// Verify image dimensions
string[] files = { "Databar30.png", "Databar60.png", "Databar90.png" };
foreach (var file in files)
{
    using var img = Image.FromFile($"{outputFolder}\\{file}");
    Console.WriteLine($"{file}: {img.Width}px × {img.Height}px");
}
```

Si la altura no refleja el valor que estableciste, verifica:

- **X‑dimension**: Un valor muy pequeño puede hacer que el renderizador redondee la altura.
- **Image format**: Algunos formatos (p.ej., JPEG) aplican compresión que puede alterar las dimensiones de píxeles al guardar. PNG conserva las dimensiones exactas.

## Paso 7: Mejores prácticas para el tamaño de la imagen del código de barras y el rendimiento

| Recomendación | Razón |
|----------------|--------|
| Mantener `x_dimension.pixels` entre 2 – 3 px para la mayoría de los escáneres. | Equilibra legibilidad y tamaño de archivo. |
| Usar PNG para salida sin pérdida cuando la imagen será impresa. | Garantiza dimensiones exactas y bordes nítidos. |
| Reutilizar una única instancia de `BarCodeGenerator` al generar muchos códigos de barras. | Reduce la sobrecarga de asignación de objetos. |
| Validar la cadena de entrada contra el estándar GS1 antes de asignarla a `CodeText`. | Previene excepciones en tiempo de ejecución y escaneos inválidos. |
| Almacenar las imágenes generadas en una carpeta dedicada con una convención de nombres clara (p.ej., `Databar_{GTIN}.png`). | Simplifica el procesamiento posterior y los registros de auditoría. |

## Ejemplo completo en funcionamiento

A continuación se muestra el programa completo que incorpora todos los pasos desde la inicialización hasta la verificación. Copia el código en un nuevo proyecto de consola y ejecútalo.



## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Generar imagen de código de barras – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Crear imagen de código de barras DotCode – filas y columnas (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Cómo crear zona silenciosa de código de barras para ITF-14 usando Aspose.BarCode para .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}