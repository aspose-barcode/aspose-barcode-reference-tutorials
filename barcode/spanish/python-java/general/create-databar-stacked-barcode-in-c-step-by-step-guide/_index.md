---
category: general
date: 2026-08-06
description: Crea rápidamente un código de barras DataBar apilado en C#. Aprende a
  establecer la dimensión X, ajustar la relación de aspecto y exportar archivos PNG
  usando el generador DataBar Stacked Omnidirectional.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode aspect ratio
- BarcodeGenerator C#
- BarCodeImageFormat PNG
language: es
lastmod: 2026-08-06
og_description: Crea códigos de barras Databar apilados en C# con Aspose.BarCode.
  Este tutorial muestra cómo configurar la dimensión X, cambiar la relación de aspecto
  y guardar imágenes PNG.
og_image_alt: Screenshot of two PNG files generated from a DataBar Stacked Omnidirectional
  barcode with different aspect ratios
og_title: Crear código de barras Databar apilado en C# – guía completa de programación
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Create databar stacked barcode in C# quickly. Learn to set X dimension,
    adjust aspect ratio, and export PNG files using the DataBar Stacked Omnidirectional
    generator.
  headline: Create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Crear código de barras Databar apilado en C# – guía paso a paso
url: /es/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear databar stacked barcode en C# – guía paso a paso

Si necesitas **create databar stacked barcode** imágenes en C#, esta guía te muestra exactamente cómo hacerlo usando la biblioteca Aspose.BarCode. Aprenderás a establecer la dimensión X, cambiar la relación de aspecto del código de barras y guardar el resultado como archivos PNG, todo en unos pocos pasos concisos.

Generar un DataBar Stacked barcode es común cuando debes codificar datos GS1‑128 para escaneo minorista o seguimiento logístico. En las secciones siguientes cubrimos todo, desde la configuración del proyecto hasta la verificación del resultado, para que puedas integrar la solución en cualquier aplicación .NET sin perder detalle.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* **.NET 6.0** (o posterior) instalado – el código apunta al SDK moderno.
* Una copia **licenciada** de **Aspose.BarCode for .NET**. La evaluación gratuita funciona para pruebas pero agrega una marca de agua.
* Un IDE como **Visual Studio 2022** o **VS Code** con la extensión C#.
* Familiaridad básica con la sintaxis **C#** y el concepto de Identificadores de Aplicación GS1.

> **Consejo profesional:** Si usas el administrador de paquetes NuGet, el comando `dotnet add package Aspose.BarCode` resuelve todas las dependencias automáticamente.

## Paso 1: Crear un nuevo proyecto de consola

Abre una terminal o la Consola del Administrador de Paquetes y ejecuta:

```bash
dotnet new console -n DatabarStackedDemo
cd DatabarStackedDemo
dotnet add package Aspose.BarCode
```

El comando `dotnet new console` genera un archivo **Program.cs** mínimo. Añadir el paquete **Aspose.BarCode** hace que la clase `BarcodeGenerator` esté disponible.

## Paso 2: Inicializar el generador DataBar Stacked Omnidirectional

Abre **Program.cs** y reemplaza el contenido predeterminado con el siguiente código. La primera línea crea un **BarcodeGenerator** configurado para la simbología **DataBar Stacked Omnidirectional** y suministra una carga útil GS1‑128.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a DataBar Stacked Omnidirectional barcode
        // "(01)12345678901231" encodes a GTIN‑14 with Application Identifier (01)
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Continue with configuration...
```

**Por qué es importante:** El valor del enum `EncodeTypes.DatabarStackedOmniDirectional` indica a la biblioteca que produzca un **databar stacked barcode**, que es la variante apilada de la familia DataBar omnidireccional. Esta simbología puede contener hasta 14 caracteres numéricos, lo que la hace ideal para códigos GTIN‑14.

## Paso 3: Establecer la dimensión X (ancho del módulo)

La dimensión X controla el ancho de la barra más pequeña (el módulo). Un valor demasiado bajo puede renderizarse pobremente en impresoras de baja resolución, mientras que un valor demasiado alto puede exceder el espacio de la etiqueta.

```csharp
        // Step 3: Define the module width – 2 pixels gives a crisp, printable barcode
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Consejo:** La propiedad `Pixels` es conveniente para pruebas en pantalla. Para escenarios enfocados en impresión, usa `generator.Parameters.Barcode.XDimension.Millimeters` en su lugar.

## Paso 4: Ajustar la relación de aspecto y guardar la primera imagen

La **relación de aspecto** influye en la relación altura‑ancho del código de barras apilado. El tipo DataBar Stacked Omnidirectional admite relaciones de 10 a 30. Generaremos dos imágenes para ilustrar el impacto visual.

```csharp
        // Step 4a: Set aspect ratio to 15 (default is 15) and save as PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

La llamada a `generator.Save` escribe un archivo **PNG** en el directorio de trabajo actual. El enum `BarCodeImageFormat.Png` garantiza compresión sin pérdidas, ideal para procesamiento posterior o incrustación en PDFs.

## Paso 5: Cambiar la relación de aspecto a 30 y guardar la segunda imagen

Ahora aumentamos la altura de las barras apiladas cambiando la relación de aspecto a **30**. Esto hace que el código de barras sea más alto sin alterar la dimensión X.

```csharp
        // Step 5a: Increase aspect ratio to 30 for a taller barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been generated:");
        Console.WriteLine(" • DatabarAspectRatio15.png");
        Console.WriteLine(" • DatabarAspectRatio30.png");
    }
}
```

Al ejecutar el programa ahora se generan dos archivos PNG:

* **DatabarAspectRatio15.png** – un código de barras compacto adecuado para etiquetas pequeñas.
* **DatabarAspectRatio30.png** – un código de barras más alto que mejora la fiabilidad del escaneo en superficies de bajo contraste.

Puedes abrir las imágenes en cualquier visor para verificar que las barras están correctamente apiladas y que los datos codificados coinciden con la cadena GS1 original.

## Paso 6: Verificar el valor codificado (opcional)

Si necesitas confirmar que el código de barras representa realmente la cadena de entrada, puedes decodificarlo con la misma biblioteca:

```csharp
        // Optional: Decode the generated PNG to ensure correctness
        var decoder = new BarCodeReader("DatabarAspectRatio15.png", DecodeType.DatabarStackedOmniDirectional);
        foreach (BarCodeResult result in decoder.ReadBarCodes())
        {
            Console.WriteLine($"Decoded text: {result.CodeText}");
        }
```

El decodificador debería devolver `(01)12345678901231`, demostrando que el proceso de **create databar stacked barcode** preservó los datos.

## Problemas comunes y cómo evitarlos

| Problema | Por qué ocurre | Solución |
|----------|----------------|----------|
| El código de barras aparece borroso | Dimensión X establecida demasiado baja para la resolución de salida | Incrementa `XDimension.Pixels` o usa `Millimeters` para impresión |
| El escáner informa “símbolo no encontrado” | Relación de aspecto fuera del rango soportado 10‑30 | Mantén la relación entre 10 y 30; 15 y 30 son valores seguros |
| PNG contiene una marca de agua | Uso de la licencia de evaluación gratuita de Aspose.BarCode | Compra una licencia completa o usa la prueba solo para testing |
| La decodificación falla en la segunda imagen | El decodificador se configuró con la simbología incorrecta | Usa `DecodeType.DatabarStackedOmniDirectional` al leer códigos apilados |

## Próximos pasos

Ahora que puedes **create databar stacked barcode** imágenes, quizás quieras:

* **Incrustar los PNG en facturas PDF** usando una biblioteca PDF como **Aspose.PDF**.
* **Generar códigos de barras bajo demanda en una API web** – devuelve los bytes PNG directamente desde un controlador ASP.NET Core.
* **Experimentar con otras variantes DataBar** (p. ej., `DatabarExpanded`, `DatabarLimited`) cambiando el enum `EncodeTypes`.
* **Ajustar colores** estableciendo `generator.Parameters.Barcode.ForeColor` y `BackColor` para diseños específicos de marca.

Cada uno de estos temas se basa en los conceptos centrales cubiertos aquí: inicializar `BarcodeGenerator`, configurar parámetros visuales y guardar el resultado con `BarCodeImageFormat`.

---

### Conclusión

Este tutorial demostró cómo **create databar stacked barcode** imágenes en C# usando Aspose.BarCode. Aprendiste a establecer la **dimensión X**, modificar la **relación de aspecto del código de barras** y exportar el resultado como archivos **PNG** con `BarcodeGenerator`. Con el paso opcional de decodificación, también puedes verificar que los datos GS1 codificados son precisos. Aplica estos patrones a tus propias aplicaciones de inventario, envío o punto de venta, y explora las numerosas opciones de personalización que ofrece la biblioteca. ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los tutoriales siguientes cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [One-Dimensional Databar Barcode Height Adjustment](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}