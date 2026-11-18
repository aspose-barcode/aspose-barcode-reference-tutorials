---
category: general
date: 2026-11-17
description: Crear imagen de código de barras en C# usando la biblioteca Barcode Generator.
  Sigue esta guía para aprender cómo generar códigos DataBar apilados omnidireccionales
  paso a paso.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- how to generate databar
language: es
lastmod: 2026-11-17
og_description: Crea una imagen de código de barras en C# con un ejemplo conciso.
  Aprende a generar códigos de barras DataBar apilados omnidireccionales usando la
  biblioteca Barcode Generator.
og_image_alt: Screenshot showing a generated barcode image created with C# code
og_title: Crear imagen de código de barras en C# – guía completa para códigos DataBar
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Create barcode image in C# using the Barcode Generator library. Follow
    this guide to learn how to generate DataBar stacked omnidirectional codes step‑by‑step.
  headline: How to create barcode image in C# with DataBar stacked omnidirectional
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Cómo crear una imagen de código de barras en C# con DataBar apilado omnidireccional
url: /es/python-java/general/how-to-create-barcode-image-in-c-with-databar-stacked-omnidi/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear una imagen de código de barras en C# con DataBar apilado omnidireccional

Si necesita **crear imagen de código de barras** en una aplicación .NET, este tutorial le muestra una solución completa, lista‑para‑ejecutar. Verá exactamente cómo usar la API **Barcode Generator C#** para producir un DataBar apilado omnidireccional, que es el formato cubierto por la consulta *how to generate databar*.

La guía recorre cada paso necesario—desde la instalación de la biblioteca hasta el ajuste fino de la relación de aspecto—para que pueda copiar el código, ejecutarlo y obtener inmediatamente un archivo PNG. No es necesario consultar documentación externa.

## Requisitos previos

Antes de comenzar, asegúrese de tener:

* .NET 6.0 SDK o posterior instalado (el ejemplo también funciona con .NET Framework 4.7+)
* Un entorno de desarrollo como Visual Studio 2022 o VS Code
* El paquete NuGet **Aspose.BarCode for .NET** (la biblioteca que proporciona `BarcodeGenerator`)

Puede agregar el paquete con el siguiente comando:

```bash
dotnet add package Aspose.BarCode
```

> **Consejo profesional:** Use el indicador `--version` para fijar el paquete a la última versión estable, por ejemplo, `dotnet add package Aspose.BarCode --version 23.9`.

## Paso 1: Configurar el proyecto e importar espacios de nombres

Cree un nuevo proyecto de consola y haga referencia a los espacios de nombres requeridos. Este paso prepara el entorno para el código **barcode generator c#** que sigue.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // All barcode generation logic lives here
```

El espacio de nombres `Aspose.BarCode.Generation` contiene la clase `BarcodeGenerator`, que es el núcleo del flujo de trabajo **crear imagen de código de barras**.

## Paso 2: Inicializar el BarcodeGenerator para un DataBar apilado omnidireccional

El generador necesita dos piezas de información: el tipo de código de barras y los datos a codificar. El valor de enumeración `EncodeTypes.DatabarStackedOmniDirectional` selecciona la variante exacta de DataBar requerida por los escenarios *how to generate databar*.

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // Example GTIN-14 payload
```

*Por qué es importante:* Seleccionar el valor correcto de `EncodeTypes` garantiza que la imagen resultante cumpla con las especificaciones industriales para el escaneo en el comercio minorista.

## Paso 3: Definir el tamaño del módulo (dimensión X) en píxeles

La densidad visual de un código de barras se controla mediante la dimensión X. Configurarla a un valor de píxeles razonable garantiza que la imagen sea legible tanto en pantalla como en impresión.

```csharp
            // Step 3: Define the module size (X‑dimension) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Si necesita un código de barras más grande para impresión de baja resolución, aumente el valor de píxeles en consecuencia.

## Paso 4: Ajustar la relación de aspecto del DataBar para alargar las filas

El DataBar apilado omnidireccional consta de dos filas. Modificar el `AspectRatio` le permite controlar la altura de cada fila, lo que puede ser útil cuando el tamaño predeterminado se ve estrecho.

```csharp
            // Step 4: Adjust the DataBar aspect ratio to make rows taller
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

Una relación de aspecto de `15` es una elección común para etiquetas minoristas; puede experimentar con valores entre `10` y `20` para cumplir requisitos de diseño específicos.

## Paso 5: Guardar el código de barras generado como una imagen PNG

Finalmente, escriba la imagen en disco. PNG es sin pérdida, lo que la hace ideal para procesamiento posterior o incrustación en PDFs.

```csharp
            // Step 5: Save the generated barcode as a PNG image
            string outputPath = "DatabarAspectRatio15.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to {outputPath}");
        }
    }
}
```

Ejecutar el programa genera un archivo llamado **DatabarAspectRatio15.png** en el directorio de salida del proyecto. Abrir el archivo muestra un código de barras limpio y de alto contraste listo para escanear.

### Resultado esperado

La imagen guardada se parece a la ilustración a continuación (el visual real se omite por brevedad).

*Texto alternativo para la imagen de ejemplo:* **crear imagen de código de barras** – un archivo PNG que muestra un DataBar apilado omnidireccional con una relación de aspecto de 15.

## Variaciones comunes y casos límite

| Situación | Ajuste |
|-----------|--------|
| **Longitud de carga útil diferente** | Reemplace la cadena GTIN con cualquier contenido válido de DataBar (p. ej., `(01)01234567890123`). |
| **Mayor resolución para impresiones grandes** | Aumente `XDimension.Pixels` a 4 o 5 y opcionalmente establezca `Resolution` en `Parameters.Image`. |
| **Otros formatos de DataBar** | Use `EncodeTypes.DatabarStacked` para una variante apilada de dos filas sin capacidad omnidireccional. |
| **Guardar como JPEG** | Cambie `BarCodeImageFormat.Png` a `BarCodeImageFormat.Jpeg` y opcionalmente establezca `Quality`. |

Estas variaciones responden a la pregunta más amplia *how to generate databar* al mostrar que el mismo generador puede reconfigurarse para múltiples familias de DataBar.

## Recapitulación del código fuente completo

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // Define the module size (X‑dimension) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Adjust the DataBar aspect ratio to make rows taller
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;

            // Save the generated barcode as a PNG image
            string outputPath = "DatabarAspectRatio15.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to {outputPath}");
        }
    }
}
```

Copie el código en `Program.cs`, restaure los paquetes NuGet y ejecute `dotnet run`. La consola confirmará la ubicación de la imagen, y podrá abrir el PNG para verificar el resultado de **crear imagen de código de barras**.

## Conclusión

Ahora sabe cómo **crear imagen de código de barras** en C# usando la biblioteca Barcode Generator y cómo **generar DataBar** con control preciso sobre el tamaño y la relación de aspecto. El ejemplo completo muestra cada configuración requerida—desde la inicialización de `BarcodeGenerator` hasta la exportación de un archivo PNG—para que pueda integrar la creación de códigos de barras en cualquier aplicación .NET sin necesidad de más investigación.

### ¿Qué sigue?

* Explorar otras simbologías de códigos de barras con `EncodeTypes` (p. ej., QR, Code128) – una extensión natural del flujo de trabajo **barcode generator c#**.  
* Combinar la imagen generada con informes PDF o Excel usando Aspose.PDF o Aspose.Cells.  
* Ajustar el color, agregar márgenes o incrustar el código de barras en una API web para generación bajo demanda.

Siéntase libre de experimentar con los parámetros, y deje que el código sirva como una base fiable para todos sus futuros proyectos relacionados con códigos de barras. ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarle a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en sus propios proyectos.

- [Cómo usar un generador de códigos de barras C# para crear códigos de barras DataBar](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)
- [Cómo usar un generador de códigos de barras C# para crear códigos de barras DataBar omnidireccional](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [Cómo crear un código de barras DataBar apilado en C# – guía paso a paso](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}