---
category: general
date: 2026-09-07
description: Crea códigos de barras planetarios PNG en C# rápidamente. Aprende cómo
  generar imágenes de códigos de barras planetarios usando Aspose.BarCode con barras
  rellenas y vacías.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode png
- how to generate planet barcode
language: es
lastmod: 2026-09-07
og_description: Crea códigos de barras planetarios PNG en C# rápidamente. Sigue esta
  guía para aprender a generar imágenes de códigos de barras planetarios con barras
  llenas y vacías usando Aspose.BarCode.
og_image_alt: Planet barcode PNG image showing filled bars and empty‑bars version
og_title: Crear código de barras planetario PNG en C# – tutorial completo de codificación
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  headline: How to create planet barcode PNG with C# – step‑by‑step guide
  type: TechArticle
- description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  name: How to create planet barcode PNG with C# – step‑by‑step guide
  steps:
  - name: What if I need a different data format?
    text: 'Planet barcodes accept numeric strings up to 12 digits. If you pass a non‑numeric
      value, Aspose throws an `ArgumentException`. Validate the input before creating
      the generator:'
  - name: How do I change the image size without altering bar thickness?
    text: 'Use the `Resolution` property or scale the resulting bitmap after saving:'
  - name: Can I generate other image formats?
    text: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`, `Bmp`,
      or `Gif`. The API supports all common raster formats.
  - name: What about color customization?
    text: 'Set `BarColor` and `BackColor` on the `Barcode` parameters:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Cómo crear un código de barras planetario PNG con C# – guía paso a paso
url: /es/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear planet barcode PNG con C# – guía paso a paso

Si necesitas **crear planet barcode PNG** en C#, esta guía te muestra los pasos exactos. Ya sea que estés construyendo una integración de servicio postal o un panel de logística, aprenderás **cómo generar planet barcode** imágenes con barras rellenas y vacías usando la biblioteca Aspose.BarCode.

En este tutorial aprenderás:

* Configurar la carpeta de salida para tus imágenes.  
* Configurar un `BarcodeGenerator` para la simbología Planet.  
* Generar un PNG con el estilo predeterminado de barras rellenas.  
* Generar un PNG con barras vacías para contraste visual.  

No se requieren servicios externos—todo se ejecuta localmente en .NET 6 o posterior.

## Prerequisites

Antes de comenzar, asegúrate de tener:

| Requisito | Por qué es importante |
|-------------|----------------|
| .NET 6 SDK (or newer) | Proporciona el runtime para la aplicación de consola C#. |
| Visual Studio 2022 or VS Code | Cualquier IDE que pueda compilar proyectos C#. |
| Aspose.BarCode for .NET (NuGet package `Aspose.BarCode`) | Proporciona la clase `BarcodeGenerator` utilizada para renderizar códigos de barras Planet. |
| Write permission to a folder on disk | Los archivos PNG se guardarán en esta ubicación. |

Instala el paquete NuGet con el siguiente comando:

```bash
dotnet add package Aspose.BarCode
```

## Paso 1: Crear un nuevo proyecto de consola

Abre una terminal y ejecuta:

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
```

Esto genera una aplicación de consola C# mínima llamada **PlanetBarcodeDemo**.

## Paso 2: Definir el directorio de salida

El primer fragmento de código determina dónde se almacenarán los archivos PNG generados. Funciona usar una ruta absoluta o relativa; solo asegúrate de que la carpeta exista o permite que el programa la cree.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Define the output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputDir); // Guarantees the folder exists
```

*¿Por qué este paso?* Separar la salida del código fuente mantiene tu proyecto ordenado y evita sobrescrituras accidentales.

## Paso 3: Generar un código de barras Planet con barras rellenas

Un código de barras Planet consiste en círculos concéntricos (rellenos por defecto). Configuramos la X‑dimension (ancho en píxeles de cada barra) y luego guardamos la imagen como PNG.

```csharp
        // Step 3: Create a Planet barcode with the default (filled) bars
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4; // Controls bar thickness

        // Save the filled‑bars barcode as PNG
        string filledPath = Path.Combine(outputDir, "PostalPlanetFilledBars.png");
        planetFilled.Save(filledPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Filled‑bars barcode saved to: {filledPath}");
```

**Explicación**

* `EncodeTypes.Planet` indica a Aspose que use la simbología Planet, que es común para los servicios postales.  
* `XDimension.Pixels = 4` produce un tamaño claro e imprimible sin escalado manual.  
* El método `Save` escribe un archivo PNG; también podrías elegir JPEG o BMP cambiando `BarCodeImageFormat`.

## Paso 4: Generar un código de barras Planet con barras vacías

A veces se requiere una visualización con barras vacías (transparentes), por ejemplo, cuando el código de barras se superpone sobre un fondo de color. Configurar `FilledBars` a `false` produce este estilo.

```csharp
        // Step 4: Create a Planet barcode with empty bars
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        planetEmpty.Parameters.Barcode.FilledBars = false; // Switch to empty‑bars mode

        // Save the empty‑bars barcode as PNG
        string emptyPath = Path.Combine(outputDir, "PostalPlanetEmptyBars.png");
        planetEmpty.Save(emptyPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Empty‑bars barcode saved to: {emptyPath}");
```

**Explicación**

* `FilledBars = false` desactiva los círculos sólidos, dejando solo los contornos.  
* Todas las demás configuraciones (X‑dimension, cadena de datos) permanecen idénticas, garantizando que ambas imágenes representen los mismos datos.

## Paso 5: Ejecutar el programa y verificar la salida

Compila y ejecuta:

```bash
dotnet run
```

Deberías ver mensajes en la consola confirmando los archivos guardados, y la carpeta `Barcodes` contendrá:

* `PostalPlanetFilledBars.png` – un clásico código de barras Planet con barras rellenas.  
* `PostalPlanetEmptyBars.png` – los mismos datos renderizados con barras vacías.

Abre los PNG en cualquier visor de imágenes. Ambas imágenes codifican la cadena numérica **123456** y pueden ser leídas por lectores estándar de códigos de barras postales.

## Preguntas comunes y manejo de casos límite

### ¿Qué pasa si necesito un formato de datos diferente?

Los códigos de barras Planet aceptan cadenas numéricas de hasta 12 dígitos. Si pasas un valor no numérico, Aspose lanza una `ArgumentException`. Valida la entrada antes de crear el generador:

```csharp
if (!Regex.IsMatch(data, @"^\d{1,12}$"))
    throw new ArgumentException("Planet barcode data must be numeric and up to 12 digits.");
```

### ¿Cómo cambio el tamaño de la imagen sin alterar el grosor de la barra?

Utiliza la propiedad `Resolution` o escala el bitmap resultante después de guardarlo:

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI for high‑resolution print
```

### ¿Puedo generar otros formatos de imagen?

Sí. Reemplaza `BarCodeImageFormat.Png` por `BarCodeImageFormat.Jpeg`, `Bmp` o `Gif`. La API soporta todos los formatos raster comunes.

### ¿Qué hay de la personalización de color?

Configura `BarColor` y `BackColor` en los parámetros de `Barcode`:

```csharp
planetFilled.Parameters.Barcode.BarColor = Color.DarkBlue;
planetFilled.Parameters.Barcode.BackColor = Color.LightYellow;
```

Estas opciones funcionan tanto para versiones con barras rellenas como vacías.

## Consejos profesionales para uso en producción

* **Cachea el generador** cuando necesites renderizar muchos códigos de barras con la misma configuración—inicializar el objeto repetidamente agrega sobrecarga.  
* **Descarta** los objetos `BarcodeGenerator` si creas muchos en un bucle (implementan `IDisposable`).  
* **Valida la carpeta de salida** temprano para evitar excepciones en tiempo de ejecución en directorios protegidos contra escritura.  

## Conclusión

Ahora sabes cómo **crear planet barcode PNG** en C# y entiendes **cómo generar planet barcode** imágenes con estilos de barras rellenas y vacías. El ejemplo completo y ejecutable muestra cómo configurar el directorio de salida, configurar el `BarcodeGenerator` y guardar los resultados como archivos PNG.

A continuación, podrías explorar:

* Agregar **texto legible** debajo del código de barras (`planetFilled.Parameters.Caption.Visible = true`).  
* Integrar los PNG generados en una **factura PDF** usando Aspose.PDF.  
* Cambiar a otras simbologías postales como **IMB** o **ITF** (`EncodeTypes.IMB`, `EncodeTypes.ITF`).  

Siéntete libre de experimentar con el grosor de las barras, colores y resoluciones de imagen para adaptarlos a los requisitos específicos de tu aplicación. ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Create Planet Barcode Image in C# – How to Generate Postal Barcode](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Create Planet Barcode in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Generate PNG Barcode with Aspose.BarCode for .NET: One-Dimensional Filled Bars](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-filled-bars-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}