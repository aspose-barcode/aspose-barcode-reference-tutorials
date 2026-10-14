---
category: general
date: 2026-09-29
description: Aprende a crear códigos de barras Databar omnidireccionales en C# con
  Aspose.BarCode. Ajusta la dimensión X, establece la relación de aspecto y guarda
  imágenes PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional databar barcode
- DataBar stacked omnidirectional barcode
- set barcode aspect ratio
- Aspose.BarCode C#
- generate barcode image
language: es
lastmod: 2026-09-29
og_description: Crea un código de barras Databar omnidireccional en C# usando Aspose.BarCode.
  Aprende a establecer la dimensión X, ajustar la relación de aspecto y exportar archivos
  PNG.
og_image_alt: Screenshot showing two PNG files of an omnidirectional Databar barcode
  with different aspect ratios
og_title: Crea un código de barras Databar omnidireccional en C# – guía paso a paso
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  headline: How to create omnidirectional Databar barcode in C#
  type: TechArticle
- description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  name: How to create omnidirectional Databar barcode in C#
  steps:
  - name: What if I need a different X‑dimension?
    text: You can assign any integer value to `XDimension.Pixels`. Values below `1`
      are ignored, and values above `10` may produce oversized modules that exceed
      printer margins. Test the visual output after each change.
  - name: How do I encode other AI‑generated data (e.g., UPC, EAN)?
    text: Replace the data string in the `BarcodeGenerator` constructor with the appropriate
      Application Identifier (AI). For a UPC‑A code, use `"012345678905"` without
      an AI prefix.
  - name: Can I export to formats other than PNG?
    text: Yes. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`,
      `BarCodeImageFormat.Tiff`, and `BarCodeImageFormat.Bmp`. Choose the format that
      matches your downstream workflow.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Cómo crear un código de barras Databar omnidireccional en C#
url: /es/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un código de barras Databar omnidireccional en C#

Si necesitas **crear un código de barras Databar omnidireccional** en una aplicación .NET, esta guía te muestra los pasos exactos. Verás cómo inicializar un código de barras DataBar apilado omnidireccional, configurar su X‑dimensión, cambiar la relación de aspecto y generar imágenes PNG con Aspose.BarCode.

Generar un **código de barras DataBar apilado omnidireccional** es común cuando debes codificar identificadores de productos para escáneres minoristas. En este tutorial aprenderás a **establecer la relación de aspecto del código de barras**, controlar el tamaño del módulo y exportar el resultado sin salir del IDE.

## Requisitos previos

- .NET 6.0 o posterior instalado
- Visual Studio 2022 (o cualquier IDE compatible con C#)
- El paquete NuGet **Aspose.BarCode for .NET** (versión 23.12 o más reciente)

Puedes agregar el paquete mediante el Administrador de paquetes NuGet:

```bash
dotnet add package Aspose.BarCode
```

## Paso 1: Inicializar el código de barras Databar omnidireccional

El primer paso es crear una instancia de `BarcodeGenerator` que apunte a la simbología **DataBar stacked omnidirectional**. El constructor recibe el tipo de codificación y la cadena de datos.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialise a DataBar stacked omnidirectional barcode with GTIN data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Por qué es importante:** El valor `EncodeTypes.DatabarStackedOmniDirectional` indica a Aspose.BarCode que renderice el formato Databar omnidireccional específico, que es necesario para escanear en ambas direcciones.

## Paso 2: Definir la X‑dimensión (tamaño del módulo)

La X‑dimensión controla el ancho de un solo módulo del código de barras en píxeles. Un valor de `2` píxeles funciona bien para la renderización en pantalla y la mayoría de las impresoras.

```csharp
        // Set the basic size of the barcode modules (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Por qué es importante:** Una X‑dimensión constante garantiza que el código de barras cumpla con las especificaciones de tamaño mínimo para los escáneres minoristas, al mismo tiempo que mantiene el tamaño del archivo de imagen manejable.

## Paso 3: Establecer la primera relación de aspecto y guardar la imagen

La **relación de aspecto** determina la relación altura‑ancho del DataBar. Una relación de aspecto de `15` produce un código de barras compacto y alto, ideal para espacios de etiquetas estrechas.

```csharp
        // Apply aspect ratio 15 and save the first PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Por qué es importante:** Ajustar la relación de aspecto te permite encajar el código de barras en diferentes diseños de etiquetas sin sacrificar la legibilidad. El PNG guardado puede inspeccionarse en cualquier visor de imágenes.

## Paso 4: Cambiar la relación de aspecto y generar una segunda imagen

A veces se necesita un código de barras más ancho, por ejemplo, cuando la etiqueta tiene más espacio horizontal. Cambiar la relación a `30` crea una apariencia más plana.

```csharp
        // Change aspect ratio to 30 and save a second PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Por qué es importante:** Al exponer la propiedad **set barcode aspect ratio**, puedes producir múltiples variaciones del código de barras a partir de una única base de código, simplificando los flujos de generación automática de etiquetas.

## Resultado esperado

Ejecutar el programa genera dos archivos PNG en la carpeta de salida de la aplicación:

| Nombre de archivo                | Relación de aspecto | Descripción visual |
|----------------------------------|---------------------|--------------------|
| `DatabarAspectRatio15.png`       | 15                  | Código de barras alto y estrecho adecuado para etiquetas estrechas |
| `DatabarAspectRatio30.png`       | 30                  | Código de barras más ancho que llena más espacio horizontal |

Puedes incrustar estas imágenes en informes, imprimirlas en el empaquetado del producto o enviarlas a un servicio web para procesamiento adicional.

![Crear ejemplo de código de barras Databar omnidireccional](databar-example.png "Crear ejemplo de código de barras Databar omnidireccional")

*La captura de pantalla muestra los dos archivos PNG generados lado a lado.*

## Preguntas comunes y casos límite

### ¿Qué pasa si necesito una X‑dimensión diferente?

Puedes asignar cualquier valor entero a `XDimension.Pixels`. Los valores por debajo de `1` se ignoran, y los valores superiores a `10` pueden producir módulos demasiado grandes que exceden los márgenes de la impresora. Prueba la salida visual después de cada cambio.

### ¿Cómo codifico otros datos generados por AI (p. ej., UPC, EAN)?

Reemplaza la cadena de datos en el constructor de `BarcodeGenerator` con el Identificador de Aplicación (AI) apropiado. Para un código UPC‑A, usa `"012345678905"` sin un prefijo AI.

### ¿Puedo exportar a formatos diferentes de PNG?

Sí. El método `Save` acepta `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`, `BarCodeImageFormat.Tiff` y `BarCodeImageFormat.Bmp`. Elige el formato que coincida con tu flujo de trabajo posterior.

## Consejo profesional: reutilizar el generador para procesamiento por lotes

Si necesitas generar docenas de códigos de barras con diferentes relaciones de aspecto, mantén viva la instancia de `BarcodeGenerator` y solo modifica `DataBar.AspectRatio` antes de cada `Save`. Esto evita la sobrecarga de volver a instanciar el generador para cada imagen.

```csharp
var ratios = new[] { 10, 15, 20, 30 };
foreach (var ratio in ratios)
{
    generator.Parameters.Barcode.DataBar.AspectRatio = ratio;
    generator.Save($"DatabarAspectRatio{ratio}.png", BarCodeImageFormat.Png);
}
```

## Conclusión

Ahora sabes cómo **crear un código de barras Databar omnidireccional** en C# usando Aspose.BarCode. Al inicializar un `BarcodeGenerator`, establecer la X‑dimensión, ajustar la **set barcode aspect ratio**, y guardar archivos PNG, puedes producir imágenes de códigos de barras que cumplen con diversos requisitos de etiquetas.  

A continuación, explora temas relacionados como **generar imagen de código de barras** para códigos QR, la validación del **código de barras DataBar stacked omnidirectional**, o la integración de los PNG generados en facturas PDF con Aspose.PDF. Experimenta con diferentes relaciones de aspecto y tamaños de módulo para encontrar la configuración óptima para tu hardware de impresión específico.

---

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo usar un generador de códigos de barras C# para crear códigos de barras DataBar omnidireccionales](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [Código de barras Databar apilado omnidireccional en C# – Guía completa](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [Cómo generar un código de barras en C# – crear imagen de código de barras C# con DataBar Expanded](/barcode/english/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}