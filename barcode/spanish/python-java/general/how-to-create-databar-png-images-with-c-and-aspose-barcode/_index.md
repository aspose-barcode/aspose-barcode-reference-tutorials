---
category: general
date: 2026-08-19
description: Cree archivos PNG de databar en C# con Aspose.BarCode. Aprenda a generar
  imágenes databar, configurar los parámetros de databar y guardar la salida PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar png
- how to generate databar
- configure databar parameters
language: es
lastmod: 2026-08-19
og_description: Crea archivos PNG de databar en C# usando Aspose.BarCode. Este tutorial
  te guía paso a paso sobre cómo generar imágenes databar, configurar parámetros de
  databar como la dimensión X y la relación de aspecto, y guardar archivos PNG de
  alta calidad para impresión o uso web.
og_image_alt: create databar PNG example
og_title: Crear imágenes PNG de databar en C# – guía paso a paso
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Create databar PNG files in C# with Aspose.BarCode. Learn how to generate
    databar images, configure databar parameters, and save PNG output.
  headline: How to create databar PNG images with C# and Aspose.BarCode
  type: TechArticle
tags:
- barcode
- databar
- C#
- PNG
- Aspose.BarCode
title: Cómo crear imágenes PNG de databar con C# y Aspose.BarCode
url: /es/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear imágenes PNG de databar con C# y Aspose.BarCode

Si necesitas **crear archivos PNG de databar** en una aplicación .NET, esta guía te muestra exactamente cómo hacerlo. Verás un ejemplo completo y ejecutable que genera códigos DataBar omnidireccionales apilados, configura parámetros clave y guarda dos archivos PNG con diferentes relaciones de aspecto.

Generar una imagen DataBar no consiste solo en llamar a un único método. También debes **configurar los parámetros del databar** como la dimensión X (ancho del módulo) y la relación de aspecto para cumplir con las especificaciones de impresión o escaneo. Al final de este tutorial comprenderás **cómo generar gráficos databar** que funcionen de manera fiable en escenarios del mundo real.

## Prerrequisitos

- .NET 6.0 o posterior (el código también funciona con .NET Framework 4.7+)
- Visual Studio 2022 o cualquier IDE compatible con C#
- Una licencia válida de **Aspose.BarCode for .NET** (la evaluación gratuita sirve para pruebas)
- Familiaridad básica con la sintaxis de C#

> **Consejo profesional:** Si aún no tienes una licencia, puedes solicitar una clave de evaluación temporal desde el portal de Aspose. La API se comporta de la misma forma; solo cambia la marca de agua.

## Paso 1: Instalar el paquete NuGet Aspose.BarCode

Abre tu proyecto en Visual Studio, haz clic con el botón derecho en la solución y selecciona **Manage NuGet Packages**. Busca `Aspose.BarCode` e instala la versión estable más reciente.

```bash
dotnet add package Aspose.BarCode
```

Este comando agrega el ensamblado `Aspose.BarCode` a tu proyecto y pone a disposición la clase `BarcodeGenerator`.

## Paso 2: Inicializar el generador de códigos de barras para un DataBar omnidireccional apilado

El constructor de `BarcodeGenerator` recibe dos argumentos: el tipo de código de barras y la cadena de datos sin formato. Para un DataBar omnidireccional apilado utilizas `EncodeTypes.DatabarStackedOmniDirectional`.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace DatabarPngDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Initialize the generator with the desired DataBar type
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // GS1 Application Identifier for a 14‑digit GTIN
```

**Por qué es importante:** La constante `EncodeTypes.DatabarStackedOmniDirectional` indica a la biblioteca que produzca un código de barras que pueda leerse desde cualquier orientación, lo cual es ideal para etiquetas de estanterías en retail.

## Paso 3: Configurar la dimensión X (ancho del módulo) en píxeles

La dimensión X controla el tamaño del elemento de barra más pequeño. Configurarla en píxeles te brinda un control preciso sobre el tamaño final de la imagen.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Un valor de **2 píxeles** es un buen equilibrio entre legibilidad y compacidad para la mayoría de impresoras de etiquetas. Ajusta este valor si necesitas módulos más grandes o más pequeños.

## Paso 4: Establecer la primera relación de aspecto y guardar el PNG

La relación de aspecto influye en la altura del DataBar apilado. Una relación de aspecto de **15** produce un código de barras relativamente corto, mientras que **30** lo hace más alto.

```csharp
            // Step 4: Set an aspect ratio of 15 and save the image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

El método `Save` escribe el código de barras generado en un archivo PNG. PNG es sin pérdida, lo que preserva los bordes nítidos requeridos por los escáneres de códigos de barras.

## Paso 5: Cambiar la relación de aspecto y guardar un segundo PNG

Puedes reutilizar la misma instancia de `BarcodeGenerator` para producir variaciones simplemente cambiando la relación de aspecto.

```csharp
            // Step 5: Change the aspect ratio to 30 and save a new image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        }
    }
}
```

Ahora tienes dos archivos PNG —`DatabarAspectRatio15.png` y `DatabarAspectRatio30.png`— cada uno con una densidad visual diferente.

## Paso 6: Verificar la salida

Abre los archivos PNG generados en cualquier visor de imágenes. Deberías ver un código de barras DataBar limpio y de alto contraste. Escanear las imágenes con una aplicación de escáner de códigos de barras en el smartphone confirma que ambas relaciones de aspecto decodifican el valor GTIN original `12345678901231`.

![create databar PNG example](databar_example.png)

*La imagen anterior muestra los dos archivos PNG uno al lado del otro. La imagen de la izquierda usa la relación de aspecto 15, la de la derecha usa la relación de aspecto 30.*

## Variaciones comunes y casos límite

| Escenario | Qué cambiar | Razón |
|----------|----------------|--------|
| **Datos diferentes** | Reemplaza la cadena `(01)12345678901231` por cualquier Identificador de Aplicación GS1 válido y sus datos | Permite codificar IDs de producto, números de serie, etc. |
| **Resolución mayor** | Incrementa `XDimension.Pixels` a 3 o 4 | Necesario cuando el código de barras se imprimirá en tamaños grandes o se escaneará desde distancia. |
| **Otros tipos de DataBar** | Usa `EncodeTypes.DatabarStacked` o `EncodeTypes.DatabarExpanded` | Elige el tipo que mejor se adapte al diseño de tu etiqueta. |
| **Fondo transparente** | Pasa `BarCodeImageFormat.Png` con `barcodeGenerator.Save(..., BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })` | Útil para superponer el código de barras sobre etiquetas de colores. |

> **Cuidado con:** Configurar una dimensión X demasiado pequeña (< 1 pixel) puede producir un código de barras que se vea borroso después

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Create One-Dimensional Databar GS1 Encoding with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Generate Aspose.BarCode Databar barcode using .NET API – Row & Column Configuration](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}