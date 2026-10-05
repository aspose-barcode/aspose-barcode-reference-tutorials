---
category: general
date: 2026-09-19
description: Cómo generar códigos de barras en C# con una guía paso a paso. Aprende
  a personalizar la configuración del código de barras PDF417 y crea una imagen de
  código de barras que los desarrolladores de C# puedan usar al instante.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- customize pdf417 barcode
- create barcode image c#
language: es
lastmod: 2026-09-19
og_description: Cómo generar códigos de barras en C# con instrucciones detalladas.
  Personaliza los parámetros del código de barras PDF417 y crea una imagen de código
  de barras que los proyectos en C# pueden usar hoy.
og_image_alt: Screenshot of a generated MicroPDF417 barcode image created with C#
  code
og_title: Cómo generar códigos de barras y personalizar el código de barras PDF417
  en C#
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  headline: How to generate barcode and customize PDF417 barcode in C#
  type: TechArticle
- description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  name: How to generate barcode and customize PDF417 barcode in C#
  steps:
  - name: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
    text: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
  - name: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
    text: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
  - name: Increase `ErrorLevel` to improve tolerance.
    text: Increase `ErrorLevel` to improve tolerance.
  type: HowTo
tags:
- barcode
- C#
- pdf417
title: Cómo generar códigos de barras y personalizar el código de barras PDF417 en
  C#
url: /es/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo generar códigos de barras y personalizar códigos de barras PDF417 en C#

Si necesitas **how to generate barcode** en una aplicación .NET, este tutorial te muestra una solución completa, lista para ejecutar. Aprenderás cómo personalizar las dimensiones del código de barras PDF417, elegir el número de columnas y, finalmente, **create barcode image C#** que los proyectos pueden incrustar directamente.

Generar un código de barras no requiere una canalización de compilación compleja. Al final de esta guía tendrás un archivo PNG que contiene un código de barras MicroPDF417 que coincide con el tamaño y la resolución exactos que necesitas.

## Requisitos previos

Deberías tener lo siguiente instalado antes de comenzar:

* .NET 6.0 SDK o posterior (el código también funciona con .NET Framework 4.6+)
* Visual Studio 2022 (o cualquier editor de C# que prefieras)
* Paquete NuGet Aspose.BarCode para .NET – instalar con  
  `dotnet add package Aspose.BarCode`

No se requieren herramientas externas adicionales.

## Paso 1: Configurar el proyecto e importar espacios de nombres

Crea un nuevo proyecto de consola y agrega la referencia a Aspose.BarCode.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Abre `Program.cs` y agrega las directivas `using` requeridas:

```csharp
using System;
using Aspose.BarCode.Generation;   // Provides BarcodeGenerator and EncodeTypes
using Aspose.BarCode;               // Contains BarCodeImageFormat enum
```

Estos espacios de nombres exponen las clases que te permiten **how to generate barcode** y controlar opciones específicas de PDF417.

## Paso 2: Inicializar el generador MicroPDF417 con el texto deseado

La primera línea crea una instancia de `BarcodeGenerator` configurada para la simbología MicroPDF417. El constructor recibe el tipo de codificación y la cadena de datos que deseas codificar.

```csharp
// Step 2: Create a MicroPDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");
```

**Por qué es importante:** MicroPDF417 es una variante compacta del estándar PDF417 completo, ideal para etiquetas pequeñas o pantallas móviles. Inicializar el generador con el `EncodeTypes` correcto garantiza que la biblioteca use el algoritmo de codificación adecuado.

## Paso 3: Personalizar la X‑dimensión (ancho del módulo) para mayor resolución

La X‑dimensión controla el ancho de un solo módulo del código de barras (la barra negra o blanca más pequeña). Configurarla a un valor bajo en píxeles produce una imagen de mayor resolución.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Por qué es importante:** Una X‑dimensión mayor facilita la lectura del código de barras por escáneres de baja resolución, mientras que un valor menor empaqueta más datos en un espacio limitado. Ajusta este valor según el entorno de escaneo.

## Paso 4: Definir el número de columnas para controlar el tamaño del código de barras

MicroPDF417 permite de 1 a 4 columnas. Más columnas generan un código de barras más corto y ancho; menos columnas crean uno más alto y estrecho.

```csharp
// Step 4: Define the number of columns (1‑4 are allowed) to control barcode size
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Por qué es importante:** Elegir la cantidad adecuada de columnas te permite adaptar el código de barras a un elemento UI específico o a una etiqueta impresa sin necesidad de escalar manualmente.

## Paso 5: Guardar el código de barras como imagen PNG

Finalmente, escribe el código de barras generado en disco. PNG conserva calidad sin pérdida, lo cual es importante para una escaneado nítido.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\MicroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Si el directorio de destino no existe, el método `Save` lanza una `ArgumentException`. Puedes protegerte de esto con una verificación simple:

```csharp
if (!System.IO.Directory.Exists(@"C:\Barcodes"))
{
    System.IO.Directory.CreateDirectory(@"C:\Barcodes");
}
```

### Código fuente completo

Uniendo las piezas, aquí tienes el programa completo y ejecutable:

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
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");

            // 2️⃣ Set the X‑dimension (module width) in pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Define the number of columns (1‑4 are allowed) to control barcode size
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Ensure the output folder exists
            string folder = @"C:\Barcodes";
            if (!System.IO.Directory.Exists(folder))
                System.IO.Directory.CreateDirectory(folder);

            // 4️⃣ Save the generated barcode as a PNG image
            string outputPath = System.IO.Path.Combine(folder, "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Ejecutar este programa genera un archivo llamado **MicroPdf417.png** que se parece a la captura de pantalla a continuación (imagen omitida por brevedad). El código de barras codifica el texto *Sample* y respeta la X‑dimensión y la configuración de columnas que definiste.

## Personalizando otras opciones de PDF417

Aunque esta guía se centra en los parámetros de **customize pdf417 barcode** que afectan el tamaño, Aspose.BarCode ofrece muchas configuraciones adicionales que podrías necesitar:

| Propiedad | Propósito | Valores típicos |
|----------|-----------|-----------------|
| `generator.Parameters.Barcode.Pdf417.Rows` | Controla el número de filas (altura) | 3‑30 |
| `generator.Parameters.Barcode.Pdf417.ErrorLevel` | Establece el nivel de corrección de errores (más alto = más tolerante) | 0‑8 |
| `generator.Parameters.Barcode.Pdf417.Truncated` | Genera un código de barras truncado (sin patrón de parada) | `true`/`false` |
| `generator.Parameters.Barcode.Pdf417.CompactionMode` | Elige la compactación numérica, de texto o de bytes | `CompactionModes.Numeric`, etc. |

**Consejo profesional:** Cuando necesites un código de barras que se ajuste a un ancho fijo, comienza aumentando `Columns` y disminuyendo `XDimension`. Si el escáner informa símbolos perdidos, incrementa `ErrorLevel` para mejorar la redundancia.

## Manejo de casos límite

* **Texto demasiado largo para MicroPDF417:** La variante Micro admite hasta 1 KB de datos. Si tu cadena supera este límite, cambia a la simbología completa `Pdf417` modificando `EncodeTypes.MicroPdf417` a `EncodeTypes.Pdf417`.
* **Formato de imagen no compatible:** `BarCodeImageFormat` también admite `Jpeg`, `Bmp` y `Gif`. Elige un formato que coincida con tu canal de procesamiento posterior.
* **Rutas multiplataforma:** Usa `Path.Combine` en lugar de barras invertidas codificadas cuando apuntas a Linux o macOS.

## Verificando el código de barras

Puedes verificar la imagen generada con cualquier aplicación estándar de escáner de códigos de barras (móvil o de escritorio). El escáner debería devolver el texto original **Sample**. Si falla:

1. Verifica que la X‑dimensión no esté establecida por debajo de 1 píxel (algunos escáneres no pueden resolver módulos subpíxel).
2. Asegúrate de que el archivo de salida no esté corrupto—vuelve a ejecutar el programa y compara los tamaños de archivo.
3. Incrementa `ErrorLevel` para mejorar la tolerancia.

## Conclusión

Ahora sabes **how to generate barcode** en C# usando Aspose.BarCode, cómo **customize pdf417 barcode** dimensiones y número de columnas, y cómo **create barcode image C#** que los proyectos pueden incrustar directamente. El ejemplo completo demuestra un flujo de trabajo práctico desde la configuración del proyecto hasta la salida final en PNG.

A continuación, explora otras simbologías como QR, Code128 o DataMatrix cambiando el valor del enum `EncodeTypes`. Ajustar parámetros adicionales como `Resolution` o `Margin` te permite afinar cada código de barras para tu aplicación específica.

¡Feliz codificación, y que tus códigos de barras potencien tu próximo proyecto de automatización!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo generar una imagen de código de barras PDF417 en C# con Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Cómo crear un código de barras PDF417 con Aspose – Guía completa paso a paso](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Cómo guardar códigos de barras en C# – Generar códigos de barras PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}