---
category: general
date: 2026-11-14
description: Tutorial de generador de códigos de barras en C# que muestra cómo crear
  códigos de barras DataBar Omnidirectional, establecer la dimensión X y ajustar la
  altura de la barra en píxeles.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c# tutorial
- DataBar Omnidirectional
- set bar height
- XDimension pixels
- BarCodeImageFormat PNG
language: es
lastmod: 2026-11-14
og_description: El tutorial de generador de códigos de barras en C# explica paso a
  paso cómo generar un código de barras DataBar Omnidirectional, definir la XDimension
  en píxeles y cambiar la altura de la barra para la salida PNG.
og_image_alt: Screenshot of barcode generator C# tutorial output showing a DataBar
  barcode
og_title: Tutorial de generador de códigos de barras en C# – crear códigos de barras
  DataBar
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Barcode generator C# tutorial that shows how to create DataBar Omnidirectional
    barcodes, set X‑dimension, and adjust bar height in pixels.
  headline: 'Barcode generator C# tutorial: DataBar Omnidirectional'
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- tutorial
title: 'Generador de códigos de barras C# tutorial: DataBar omnidireccional'
url: /es/python-java/general/barcode-generator-c-tutorial-databar-omnidirectional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tutorial de generador de códigos de barras C# – crear códigos de barras DataBar omnidireccionales

Si estás buscando un **tutorial de generador de códigos de barras C#**, has llegado al lugar correcto. Esta guía te muestra cómo crear un código de barras DataBar Omnidirectional, configurar la XDimension en píxeles y ajustar la altura de las barras para generar imágenes PNG.

Verás un ejemplo completo y ejecutable que cubre todo, desde la inicialización del generador hasta guardar múltiples imágenes con diferentes alturas de barra. No se requiere documentación externa—simplemente copia el código, ejecútalo y tendrás dos archivos de códigos de barras listos para usar.

## Requisitos previos

* .NET 6.0 o posterior instalado  
* Una referencia a la biblioteca de códigos de barras que proporciona `BarcodeGenerator`, `EncodeTypes` y `BarCodeImageFormat` (por ejemplo, Aspose.BarCode para .NET)  
* Familiaridad básica con la sintaxis de C# y Visual Studio o tu IDE preferido  

> **Consejo profesional:** Si estás usando Aspose.BarCode, agrega el paquete NuGet `Aspose.BarCode` a tu proyecto.

## Tutorial de generador de códigos de barras C# – paso 1: crear el generador

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Omnidirectional barcode generator with the desired data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

*Por qué es importante:* `EncodeTypes.DatabarOmniDirectional` indica a la biblioteca que produzca un código de barras que pueda leerse desde cualquier dirección, lo cual es ideal para empaques minoristas y logística.

## Establecer píxeles XDimension para el código de barras

```csharp
        // Step 2: Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Explicación:* Un valor de `2` píxeles produce un código de barras lo suficientemente nítido para la mayoría de los escáneres mientras mantiene el tamaño del archivo de imagen moderado.

## Ajustar la altura de la barra y guardar imágenes

```csharp
        // Step 3: Set the bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        string outputPath = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
```

El valor del enumerado `BarCodeImageFormat.Png` garantiza que la salida sea un archivo PNG sin pérdida, que es el formato recomendado para gráficos de códigos de barras porque preserva las dimensiones exactas.

## Cambiar la altura de la barra para crear múltiples imágenes

```csharp
        // Step 4: Change the bar height to 60 px and save a second image
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        outputPath = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
    }
}
```

*Caso límite:* Si la altura de la barra se establece demasiado baja (p. ej., por debajo de 10 px), algunos escáneres pueden tener dificultades para leer el código. Siempre prueba las imágenes generadas con el hardware de escáner objetivo.

## Código fuente completo

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a DataBar Omnidirectional barcode generator
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Set XDimension to 2 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image – 30 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
            generator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 30 px barcode to {path30}");

            // Second image – 60 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
            generator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 60 px barcode to {path60}");
        }
    }
}
```

Ejecuta el programa, reemplaza `YOUR_DIRECTORY` con una ruta de carpeta válida, y encontrarás dos archivos PNG:

* `DatabarBarHeight30Pixels.png` – barras de 30 px de altura  
* `DatabarBarHeight60Pixels.png` – barras de 60 px de altura  

![resultado del tutorial de generador de códigos de barras C#](images/databar-example.png "Tutorial de generador de códigos de barras C# mostrando dos imágenes DataBar")

## Preguntas comunes

| Pregunta | Respuesta |
|----------|----------|
| **¿Puedo cambiar el formato de imagen?** | Sí. Reemplaza `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` o `Gif` según sea necesario. PNG es el formato preferido por su calidad sin pérdida. |
| **¿Qué pasa si necesito una XDimension diferente?** | Ajusta `generator.Parameters.Barcode.XDimension.Pixels` a cualquier entero. Valores mayores aumentan el ancho total del código de barras. |
| **¿Es el DataBar Omnidirectional adecuado para escaneo móvil?** | Sí, siempre que el tamaño impreso cumpla con el tamaño mínimo de módulo del escáner (usualmente 0.33 mm). La XDimension basada en píxeles te ayuda a cumplir ese requisito. |
| **¿Cómo incrusto el código de barras en un PDF?** | Después de guardar el PNG, usa una biblioteca PDF (p. ej., iTextSharp) para insertar la imagen en una página PDF. |

## Conclusión

Este **tutorial de generador de códigos de barras C#** te mostró cómo crear un código de barras DataBar Omnidirectional, establecer la XDimension en píxeles y generar archivos PNG con diferentes alturas de barra. Ahora tienes un fragmento de código reutilizable que puedes adaptar a cualquier proyecto C# que requiera creación de códigos de barras.

### ¿Qué sigue?

* Explora otros `EncodeTypes` como `Code128` o `QR` para ampliar tu repertorio de códigos de barras.  
* Combina el PNG generado con una biblioteca de generación de PDF para producir facturas imprimibles.  
* Experimenta con `generator.Parameters.Barcode.Color` para añadir colores personalizados sin salir de las especificaciones del escáner.

¡Siéntete libre de modificar el ejemplo, probar alturas de barra adicionales o cambiar el formato de salida. ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo establecer el ancho y ajustar la altura para un código de barras GS1 DataBar omnidireccional](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [Cómo establecer la altura del código de barras, generar código de barras DataBar en C#](/barcode/english/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/)
- [Cómo crear un código de barras Databar omnidireccional en C#](/barcode/english/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}