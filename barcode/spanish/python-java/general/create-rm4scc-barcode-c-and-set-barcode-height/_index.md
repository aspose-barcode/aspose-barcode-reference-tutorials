---
category: general
date: 2026-08-25
description: Crea un código de barras RM4SCC en C# con código paso a paso y aprende
  a establecer la altura del código de barras para un dimensionado preciso.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create rm4scc barcode c#
- how to set barcode height
language: es
lastmod: 2026-08-25
og_description: Crea códigos de barras RM4SCC en C# con Aspose.BarCode y aprende cómo
  establecer la altura del código de barras para un control preciso en tus aplicaciones
  .NET.
og_image_alt: Screenshot of an RM4SCC barcode generated with C#
og_title: Crear código de barras RM4SCC en C# – guía para establecer la altura del
  código de barras
schemas:
- author: Aspose
  dateModified: '2026-08-25'
  description: Create RM4SCC barcode C# with step‑by‑step code and learn how to set
    barcode height for precise sizing.
  headline: Create RM4SCC barcode C# and set barcode height
  type: TechArticle
tags:
- barcode
- C#
- RM4SCC
- Aspose.BarCode
title: Crear código de barras RM4SCC en C# y establecer la altura del código de barras
url: /es/python-java/general/create-rm4scc-barcode-c-and-set-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear código de barras RM4SCC C# y establecer la altura del código de barras

Cree código de barras RM4SCC C# rápidamente usando la biblioteca Aspose.BarCode. Este tutorial muestra **cómo establecer la altura del código de barras** y personalizar otras propiedades visuales para que el código de barras se ajuste exactamente a su diseño.

Verá un programa de consola completo y listo para ejecutar que genera tres archivos PNG:

* un código de barras Planet de altura predeterminada (para comparación)  
* un código de barras RM4SCC con una altura manual de 100 px  
* un código de barras Planet con barras vacías (no rellenadas)  

El ejemplo asume que tiene Visual Studio 2022 (o cualquier IDE .NET 6+) y una licencia válida de Aspose.BarCode para .NET o una copia de evaluación.

## Requisitos previos

| Requisito | Razón |
|-------------|--------|
| .NET 6 SDK (o posterior) | Proporciona el tiempo de ejecución para la aplicación de consola |
| Paquete NuGet Aspose.BarCode para .NET | Suministra `BarcodeGenerator`, `EncodeTypes` y APIs de exportación de imágenes |
| Conocimientos básicos de C# | Necesario para comprender el flujo del código |

Instale el paquete NuGet con:

```bash
dotnet add package Aspose.BarCode
```

> **Consejo profesional:** Si ejecuta el código sin una licencia, las imágenes generadas contendrán una pequeña marca de agua de Aspose.

## Paso 1: Configurar la estructura del proyecto

Cree un nuevo proyecto de consola y agregue las directivas `using` necesarias:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat; // optional, you can use the enum directly
```

Las declaraciones `using` le dan acceso a las clases del generador de códigos de barras y al enumerado de formato PNG.

## Paso 2: Definir la carpeta de salida

Elija una carpeta donde se guardarán los archivos PNG. La carpeta debe existir antes de llamar a `Save`.

```csharp
// Step 1: Define the output folder
string outputFolder = "GeneratedBarcodes/";

// Ensure the directory exists
System.IO.Directory.CreateDirectory(outputFolder);
```

Crear el directorio programáticamente evita una *FileNotFoundException* cuando el código se ejecuta en una máquina nueva.

## Paso 3: Generar un código de barras Planet con la altura predeterminada (línea base)

El código de barras Planet no es el foco de esta guía, pero proporciona una línea base visual para comparar con el código de barras RM4SCC de tamaño manual.

```csharp
// Step 2: Generate a Planet barcode with the default (auto) height
BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // controls bar width
planetAuto.Save($"{outputFolder}PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

*Por qué esto importa:*  
`XDimension` determina el ancho de una sola barra. Mantenerlo constante mientras se cambia `BarHeight` aísla el efecto de la altura.

## Paso 4: **Crear código de barras RM4SCC C#** – establecer una altura manual

Ahora abordamos la tarea principal: **crear código de barras RM4SCC C#** y controlar explícitamente su altura.

```csharp
// Step 3: Generate an RM4SCC barcode with a manual height of 100 px
BarcodeGenerator rm4sccManual = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccManual.Parameters.Barcode.XDimension.Pixels = 4;           // same bar width as Planet example
rm4sccManual.Parameters.Barcode.BarHeight.Pixels = 100;          // <-- how to set barcode height
rm4sccManual.Save($"{outputFolder}PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

### Cómo establecer la altura del código de barras

La propiedad `BarHeight` se encuentra bajo `Parameters.Barcode`. Acepta un valor `float` expresado en **píxeles**, **puntos** o **milímetros** según la `Unit` que elija (`Pixels`, `Points`, `Millimeters`). En el ejemplo usamos `Pixels` porque el formato de salida es PNG.

Si necesita una altura en milímetros, cambie la unidad primero:

```csharp
rm4sccManual.Parameters.Barcode.BarHeight.Unit = BarHeightUnit.Millimeters;
rm4sccManual.Parameters.Barcode.BarHeight.Value = 25; // 25 mm tall
```

## Paso 5: Generar un código de barras Planet con barras vacías (no rellenadas)

Este paso demuestra otra propiedad útil—`FilledBars`. Configurarla en `false` crea un código de barras “hueco”, lo que puede ser útil para propósitos de diseño.

```csharp
// Step 4: Generate a Planet barcode with empty (unfilled) bars
BarcodeGenerator planetEmptyBars = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetEmptyBars.Parameters.Barcode.XDimension.Pixels = 4;
planetEmptyBars.Parameters.Barcode.FilledBars = false; // makes bars transparent
planetEmptyBars.Save($"{outputFolder}PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

## Programa completo y ejecutable

Copie el siguiente código en `Program.cs`. Compile y ejecute el proyecto; tres archivos PNG aparecerán en la carpeta `GeneratedBarcodes`.



## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarle a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en sus propios proyectos.

- [Cómo crear código de barras code128 Java y establecer la altura de la barra](/barcode/english/java/barcode-configuration/setting-bars-height/)
- [Cómo crear zona silenciosa de código de barras .NET para Code 16K usando Aspose.BarCode](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Cómo crear código de barras Aztec con Aspose.BarCode para .NET](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}