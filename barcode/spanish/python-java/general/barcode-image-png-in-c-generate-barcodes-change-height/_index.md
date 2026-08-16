---
category: general
date: 2026-08-15
description: Imagen de código de barras PNG en C# – aprende cómo generar códigos de
  barras postales, crear un código de barras Planet y cambiar la altura del código
  de barras con un generador sencillo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode image png
- barcode generator c#
- generate postal barcode
- create planet barcode
- change barcode height
language: es
lastmod: 2026-08-15
og_description: El tutorial de imagen de código de barras PNG en C# muestra cómo generar
  códigos de barras postales, crear un código de barras Planet y cambiar la altura
  del código de barras usando la API BarcodeGenerator.
og_image_alt: Screenshot of generated PNG barcode with custom height using C# BarcodeGenerator
og_title: Imagen de código de barras PNG en C# – generar y ajustar códigos de barras
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Barcode image PNG in C# – learn how to generate postal barcodes, create
    a Planet barcode, and change barcode height with a simple generator.
  headline: Barcode image PNG in C# generate barcodes, change height
  type: TechArticle
tags:
- barcode
- C#
- PNG
- postal
- generator
title: Imagen PNG de código de barras en C# generar códigos de barras, cambiar altura
url: /es/python-java/general/barcode-image-png-in-c-generate-barcodes-change-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Imagen de código de barras PNG en C# – generar códigos de barras, cambiar altura

Si necesitas una **imagen de código de barras PNG** en C#, esta guía te lleva paso a paso por todo el proceso. Aprenderás a generar códigos de barras postales, crear un código de barras Planet y cambiar la altura del código de barras sin salir de tu IDE.

Generar códigos de barras PNG confiables es un requisito común para etiquetas de envío, sistemas de inventario y soluciones de correo automatizado. Al final de este tutorial tendrás un fragmento de código reutilizable que produce archivos PNG de alta calidad para los formatos Planet y RM4SCC, y comprenderás cómo ajustar la altura de la barra para cumplir con las especificaciones postales.

## Lo que necesitarás

- .NET 6+ o .NET Framework 4.7.2 (la API BarcodeGenerator funciona con cualquier runtime .NET reciente)  
- Una referencia al paquete NuGet **Aspose.BarCode for .NET** (o cualquier biblioteca compatible que proporcione `BarcodeGenerator`, `EncodeTypes` y `BarCodeImageFormat`)  
- Familiaridad básica con la sintaxis de C# y la E/S de archivos  

No se requieren herramientas adicionales; el código se ejecuta en Visual Studio, Rider o la CLI `dotnet`.

## Imagen de código de barras PNG – generación básica

El primer paso es crear una **imagen de código de barras PNG** con dimensiones predeterminadas. Esto establece el archivo base que luego podrás personalizar.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Define the output folder (replace with your own path)
string outputFolder = @"C:\Barcodes";

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);

// 1️⃣ Create a Planet barcode generator with default height
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width (X‑dimension) to 4 pixels – this defines the thin bar size
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG; this is the first **barcode image PNG** you’ll produce
planetGenerator.Save(Path.Combine(outputFolder, "PlanetBarHeightDefault.png"),
                     BarCodeImageFormat.Png);
```

**Por qué funciona esto:**  
- `EncodeTypes.Planet` indica al generador que use la simbología Planet, que es requerida por muchos servicios postales.  
- `XDimension.Pixels` controla el ancho de la barra más pequeña; un valor de 4 px produce un código de barras legible en tamaños típicos de etiquetas.  
- El método `Save` escribe un archivo **imagen de código de barras PNG** en disco, preservando toda la información vectorial como píxeles rasterizados.

## Cambiar la altura del código de barras – personalizando el peso visual

Las directrices postales a menudo exigen una altura de barra específica. El siguiente fragmento muestra cómo establecer una altura personalizada de 100 píxeles para el mismo código de barras Planet.

```csharp
// 2️⃣ Apply a custom 100‑pixel bar height
planetGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Overwrite or save as a new file to keep both versions
planetGenerator.Save(Path.Combine(outputFolder, "PlanetBarHeight100.png"),
                     BarCodeImageFormat.Png);
```

**Por qué cambias la altura:**  
Una barra más alta mejora la fiabilidad del escaneo en impresoras de baja resolución, mientras que una barra más corta reduce el espacio de la etiqueta. La propiedad `BarHeight.Pixels` te permite afinar este atributo sin afectar la dimensión X.

## Generar código de barras postal – creando un ejemplo RM4SCC

El formato RM4SCC es otro código de barras postal común utilizado en el Reino Unido. Los pasos de generación reflejan el ejemplo Planet, reforzando el patrón **barcode generator c#**.

```csharp
// 3️⃣ Create an RM4SCC barcode generator with default height
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Keep the same module width for consistency
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the default‑height PNG
rm4sccGenerator.Save(Path.Combine(outputFolder, "RM4SCCBarHeightDefault.png"),
                     BarCodeImageFormat.Png);
```

## Cambiar la altura del código de barras – variación RM4SCC

Al igual que con el código de barras Planet, puedes ajustar la altura de la barra RM4SCC. El código a continuación establece la altura en 100 px, produciendo una segunda **imagen de código de barras PNG** para la misma cadena de datos.

```csharp
// 4️⃣ Set a custom 100‑pixel bar height for RM4SCC
rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the customized PNG
rm4sccGenerator.Save(Path.Combine(outputFolder, "RM4SCCBarHeight100.png"),
                     BarCodeImageFormat.Png);
```

## Ejemplo completo y ejecutable

Unir todos los pasos produce un programa único y autónomo que crea cuatro archivos PNG:

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        string outputFolder = @"C:\Barcodes";
        Directory.CreateDirectory(outputFolder);

        // Planet barcode – default height
        var planet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planet.Parameters.Barcode.XDimension.Pixels = 4;
        planet.Save(Path.Combine(outputFolder, "PlanetBarHeightDefault.png"),
                    BarCodeImageFormat.Png);

        // Planet barcode – custom 100‑pixel height
        planet.Parameters.Barcode.BarHeight.Pixels = 100;
        planet.Save(Path.Combine(outputFolder, "PlanetBarHeight100.png"),
                    BarCodeImageFormat.Png);

        // RM4SCC barcode – default height
        var rm4scc = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4scc.Parameters.Barcode.XDimension.Pixels = 4;
        rm4scc.Save(Path.Combine(outputFolder, "RM4SCCBarHeightDefault.png"),
                    BarCodeImageFormat.Png);

        // RM4SCC barcode – custom 100‑pixel height
        rm4scc.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4scc.Save(Path.Combine(outputFolder, "RM4SCCBarHeight100.png"),
                    BarCodeImageFormat.Png);

        Console.WriteLine("All barcode PNG files have been generated in " +


## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Crear código de barras con altura personalizada – Códigos de barras unidimensionales](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [Crear código de barras PNG – Relación de aspecto DataMatrix – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [Crear imagen de código de barras C# – Ejemplo GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}