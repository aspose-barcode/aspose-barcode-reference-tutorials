---
category: general
date: 2026-08-22
description: El tutorial del generador de códigos de barras en C# muestra cómo generar
  archivos PNG de códigos de barras, crear códigos de barras DataBar y ajustar la
  altura del código de barras en solo unos pocos pasos.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- how to generate barcode
- generate barcode PNG
- create DataBar barcode
- adjust barcode height
language: es
lastmod: 2026-08-22
og_description: La guía del generador de códigos de barras en C# le muestra cómo generar
  PNG de códigos de barras, crear códigos de barras DataBar y ajustar la altura del
  código de barras de manera eficiente.
og_image_alt: Screenshot of two DataBar Omni‑directional barcodes with different heights
  saved as PNG files
og_title: generador de códigos de barras C# – crear códigos de barras DataBar y ajustar
  la altura
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to generate barcode PNG files,
    create DataBar barcodes, and adjust barcode height in just a few steps.
  headline: How to use a barcode generator C# to create DataBar Omni‑directional barcodes
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Cómo usar un generador de códigos de barras C# para crear códigos de barras
  DataBar omnidireccionales
url: /es/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo usar un generador de códigos de barras C# para crear códigos de barras DataBar Omni‑directional

Si necesitas un **barcode generator C#** que pueda producir imágenes PNG de alta calidad, esta guía te cubre. Aprenderás a generar archivos PNG de códigos de barras, crear un código de barras DataBar Omni‑directional y ajustar la altura del código de barras sin salir de tu IDE.

Generar códigos de barras programáticamente elimina el paso manual de usar un editor gráfico. Al final de este tutorial tendrás dos archivos PNG—uno con una altura de barra de 30 píxeles y otro con una altura de barra de 60 píxeles—listos para incluirse en facturas, etiquetas o sistemas de inventario.

**Prerequisites**

- .NET 6.0 o posterior (el código también funciona con .NET Framework 4.7+)
- Una referencia al paquete NuGet `Aspose.BarCode` (o cualquier biblioteca que exponga una API similar)
- Familiaridad básica con C# y Visual Studio o tu IDE preferido

---

## Paso 1: Configurar el proyecto del barcode generator C#

Crear una instancia de **barcode generator C#** es lo primero que haces. El constructor recibe dos argumentos: el tipo de código de barras (`EncodeTypes.DatabarOmniDirectional`) y la carga de datos. En este ejemplo la carga sigue el formato de Identificador de Aplicación GS1 para un GTIN de 14 dígitos.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the barcode generator for a DataBar Omni‑directional code
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

**Por qué es importante:** El enum `EncodeTypes.DatabarOmniDirectional` indica a la biblioteca que renderice un DataBar que pueda leerse desde cualquier dirección, lo cual es ideal para etiquetas minoristas pequeñas.

---

## Paso 2: Definir la dimensión del módulo (X‑dimension)

La X‑dimension controla el ancho de un solo módulo del código de barras. Configurarla en 2 píxeles produce una imagen nítida y legible mientras mantiene bajo el tamaño del archivo.

```csharp
        // Set the module (X) dimension to 2 pixels per module
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Consejo:** Si necesitas un código de barras más compacto por espacio limitado, reduce el valor a 1 pixel, pero prueba la legibilidad con un escáner.

---

## Paso 3: Generar el primer PNG con una altura de barra de 30 píxeles

La altura de la barra determina cuán altas aparecen las barras. Una altura de 30 píxeles es un valor predeterminado común para etiquetas estándar.

```csharp
        // Set bar height to 30 pixels
        generator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image as PNG
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png",
                       BarCodeImageFormat.Png);
```

El archivo `DatabarBarHeight30Pixels.png` ahora contiene un **generate barcode PNG** que puede usarse directamente en páginas web o imprimirse bajo demanda.

---

## Paso 4: Ajustar la altura del código de barras a 60 píxeles y guardar un segundo PNG

Cambiar la altura de la barra es tan simple como asignar un nuevo valor a la misma propiedad. Esto demuestra la capacidad de **adjust barcode height** del generador.

```csharp
        // Change bar height to 60 pixels for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png",
                       BarCodeImageFormat.Png);
    }
}
```

Ahora tienes `DatabarBarHeight60Pixels.png`, ideal para empaques más grandes donde el código de barras debe escanearse a distancia.

**Salida esperada**

- `DatabarBarHeight30Pixels.png` – un código de barras DataBar Omni‑directional compacto, de 30 px de alto.
- `DatabarBarHeight60Pixels.png` – el mismo código de barras, duplicado en altura para mejor visibilidad.

Ambas imágenes son archivos PNG, conservando calidad sin pérdidas y soportando transparencia si se necesita.

---

## Cómo generar archivos PNG de códigos de barras en diferentes formatos

Aunque este tutorial se centra en PNG, el método `Save` acepta otros formatos como `Jpeg`, `Bmp` y `Svg`. Para **how to generate barcode** en otro formato, simplemente reemplaza `BarCodeImageFormat.Png` por el valor del enum deseado:

```csharp
generator.Save(@"path\barcode.svg", BarCodeImageFormat.Svg);
```

Elegir SVG es útil cuando necesitas una imagen vectorial que escale sin pixelación.

---

## Problemas comunes al **create DataBar barcode** imágenes

| Issue | Cause | Fix |
|-------|-------|-----|
| El código de barras aparece borroso | X‑dimension demasiado baja para la resolución objetivo | Incrementa `XDimension.Pixels` a 3 o 4 |
| El escáner no puede leer el código | Altura de barra demasiado corta para la óptica del escáner | Usa un mínimo de 30 píxeles o sigue las especificaciones del escáner |
| La cadena de datos es rechazada | Formato GS1 incorrecto | Asegúrate de que la cadena comience con el Identificador de Aplicación correcto, por ejemplo, `(01)` para GTIN‑14 |

Abordar estos puntos temprano ahorra tiempo al integrar códigos de barras en pipelines de producción.

---

## Consejo avanzado: Reutilizar el mismo generador para varios códigos de barras

Si necesitas **generate barcode PNG** para un lote de productos, reutiliza la misma instancia de `BarcodeGenerator` y solo actualiza la propiedad `CodeText`:

```csharp
string[] gtins = { "(01)12345678901231", "(01)98765432109876" };
int[] heights = { 30, 60 };

foreach (var gtin in gtins)
{
    generator.CodeText = gtin;          // Change data payload
    foreach (var h in heights)
    {
        generator.Parameters.Barcode.BarHeight.Pixels = h;
        string fileName = $"Databar_{gtin.Substring(4)}_{h}Px.png";
        generator.Save($@"YOUR_DIRECTORY\{fileName}", BarCodeImageFormat.Png);
    }
}
```

Este patrón minimiza la sobrecarga de creación de objetos y mantiene tu código conciso.

---

## Conclusión

Ahora tienes un flujo de trabajo completo de **barcode generator C#** que **creates DataBar barcodes**, **generates barcode PNG** files y te permite **adjust barcode height** con un solo cambio de propiedad. El ejemplo cubre todo, desde la configuración del proyecto hasta el manejo de casos límite, para que puedas integrar la creación de códigos de barras en cualquier aplicación .NET con confianza.

**Próximos pasos**

- Explora otras simbologías de códigos de barras (`EncodeTypes.QR`, `EncodeTypes.Code128`) para ampliar tu solución.
- Combina el generador con ASP.NET Core para servir códigos de barras bajo demanda mediante un endpoint API.
- Experimenta con opciones de color (`generator.Parameters.Barcode.ForeColor`) para propósitos de branding.

¡Feliz codificación, y que tus escaneos siempre sean rápidos!

## What Should You Learn Next?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generate One-Dimensional Databar 2D Barcodes Using Aspose.BarCode .NET API](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}