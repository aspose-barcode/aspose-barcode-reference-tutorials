---
category: general
date: 2026-10-08
description: Aprende a redimensionar imágenes de códigos de barras con un ejemplo
  de generador de códigos de barras en C#, ajustando la altura de la barra de 30 px
  a 60 px en solo unas pocas líneas de código.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to resize barcode
- barcode generator example c#
language: es
lastmod: 2026-10-08
og_description: Cómo redimensionar rápidamente un código de barras con un ejemplo
  de generador de códigos de barras en C#. Ajusta la altura de las barras, guarda
  archivos PNG y evita errores comunes.
og_image_alt: Screenshot showing a resized barcode generated with C# code
og_title: Cómo redimensionar el código de barras en C# – ejemplo de generador paso
  a paso
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  headline: How to resize barcode using a barcode generator example in C#
  type: TechArticle
- description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  name: How to resize barcode using a barcode generator example in C#
  steps:
  - name: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
    text: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
  - name: Print the images at 100 % scale.
    text: Print the images at 100 % scale.
  - name: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
    text: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
  type: HowTo
tags:
- barcode
- C#
- image processing
title: Cómo redimensionar un código de barras usando un ejemplo de generador de códigos
  de barras en C#
url: /es/python-java/general/how-to-resize-barcode-using-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo cambiar el tamaño del código de barras usando un ejemplo de generador de códigos de barras en C#

Si necesitas **cambiar el tamaño del código de barras** en un proyecto .NET, esta guía muestra la solución completa. Verás un conciso **ejemplo de generador de códigos de barras C#** que cambia la altura de la barra de 30 px a 60 px y guarda cada versión como un archivo PNG.

Redimensionar un código de barras suele ser necesario cuando los mismos datos deben aparecer en recibos, etiquetas o páginas de producto a diferentes escalas visuales. En lugar de editar la imagen rasterizada con un editor externo, puedes ajustar las dimensiones del código de barras programáticamente, manteniendo la integridad de los datos.

En este tutorial aprenderás a:

* Configurar un generador de código de barras DataBar Omni‑Directional.
* Modificar los parámetros de X‑dimension y altura de barra.
* Guardar dos imágenes con alturas distintas.
* Entender por qué cambiar la altura de la barra funciona y qué casos límite vigilar.

> **Requisito previo** – Tienes un entorno de desarrollo .NET (Visual Studio 2022 o posterior) y la biblioteca de códigos de barras que proporciona `BarcodeGenerator`, `EncodeTypes` y `BarCodeImageFormat`. El código funciona con la última versión de la biblioteca a partir de octubre 2026.

## Requisitos previos para el ejemplo de generador de códigos de barras C#

Antes de comenzar, asegúrate de contar con:

| Elemento | Razón |
|------|--------|
| .NET 6.0 SDK o posterior | Proporciona el runtime y las características del lenguaje usadas en el ejemplo. |
| Biblioteca de códigos de barras (p. ej., Aspose.BarCode, Dynamsoft, o cualquier biblioteca que exponga `BarcodeGenerator`) | Suministra el enum `EncodeTypes.DatabarOmniDirectional` y los métodos de exportación de imágenes. |
| Una carpeta a la que puedas escribir (p. ej., `C:\Temp\Barcodes\`) | El ejemplo guarda los archivos PNG en esta ubicación. |
| Conocimientos básicos de C# | El tutorial asume familiaridad con clases, propiedades e interpolación de cadenas. |

Instala la biblioteca vía NuGet si aún no lo has hecho:

```bash
dotnet add package Aspose.BarCode
```

Reemplaza el nombre del paquete por el que realmente uses; la superficie de la API mostrada a continuación es común en la mayoría de los SDK de códigos de barras.

## Cómo cambiar el tamaño del código de barras – paso 1: crear el generador

El primer paso es instanciar un `BarcodeGenerator` con la simbología deseada y la carga de datos. En este ejemplo generamos un código de barras **DataBar Omni‑Directional** que codifica un valor GTIN‑14.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a DataBar Omni‑Directional barcode generator with the desired data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

**Por qué es importante:** El enum `EncodeTypes.DatabarOmniDirectional` indica a la biblioteca qué estándar de código de barras usar. La cadena de datos sigue el Identificador de Aplicación GS1 `(01)` para un GTIN de 14 dígitos, asegurando que el código cumpla con los estándares de comercio global.

## Cómo cambiar el tamaño del código de barras – paso 2: definir el ancho del módulo y la altura inicial de la barra

El tamaño visual de un código de barras depende de dos parámetros:

* **X‑dimension** – el ancho de la barra más pequeña (módulo). Se mide en píxeles o milímetros.
* **Altura de barra** – la longitud vertical de las barras.

Establecer estos valores antes de guardar garantiza que la imagen renderizada coincida con las dimensiones que necesitas.

```csharp
// Step 2: Define the X‑dimension (module width) and set the bar height to 30 px
generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2 px per module
generator.Parameters.Barcode.BarHeight.Pixels = 30; // 30 px tall bars
```

**Explicación:** Una X‑dimension de 2 px produce un código de barras compacto que aún escanea de forma fiable. La altura de 30 px es un valor predeterminado común para etiquetas pequeñas. Puedes ajustar la X‑dimension de forma independiente de la altura si necesitas un patrón más denso o más espaciado.

## Cómo cambiar el tamaño del código de barras – paso 3: guardar la primera imagen (altura 30 px)

Ahora exporta el código de barras a un archivo PNG. El método `Save` acepta una ruta de archivo y un enum de formato de imagen.

```csharp
// Step 3: Save the barcode image with a 30 px height
string outputPath = @"C:\Temp\Barcodes\";
generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**Resultado:** `DatabarBarHeight30Pixels.png` contiene un código de barras de 30 px de altura. Puedes abrir el archivo en cualquier visor de imágenes para verificar las dimensiones.

## Cómo cambiar el tamaño del código de barras – paso 4: cambiar la altura de la barra a 60 px

Para crear una versión más grande, simplemente modifica la propiedad `BarHeight`. El generador reutiliza los mismos datos y la misma X‑dimension, por lo que el patrón del código de barras permanece idéntico—solo cambia el tamaño visual.

```csharp
// Step 4: Change the bar height to 60 px for a larger barcode
generator.Parameters.Barcode.BarHeight.Pixels = 60;
```

**Por qué funciona:** El motor de renderizado del código de barras calcula la geometría de cada barra bajo demanda. Actualizar la propiedad de altura antes de la siguiente llamada a `Save` desencadena una nueva rasterización con las dimensiones actualizadas.

## Cómo cambiar el tamaño del código de barras – paso 5: guardar la segunda imagen (altura 60 px)

```csharp
// Step 5: Save the barcode image with a 60 px height
generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Ahora tienes dos archivos PNG, uno pequeño (30 px) y otro más grande (60 px), listos para usarse en diferentes tamaños de etiqueta.

## Código fuente completo para el ejemplo de generador de códigos de barras C#

A continuación se muestra el programa completo y ejecutable. Cópialo en un nuevo proyecto de consola para probarlo de inmediato.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeResizeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with DataBar Omni‑Directional symbology
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension and initial bar height (30 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 3️⃣ Define output folder (ensure it exists)
            string outputPath = @"C:\Temp\Barcodes\";
            System.IO.Directory.CreateDirectory(outputPath);

            // 4️⃣ Save the 30 px version
            generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30 px barcode.");

            // 5️⃣ Increase bar height to 60 px
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the 60 px version
            generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60 px barcode.");
        }
    }
}
```

**Salida esperada en la consola:**

```
Saved 30 px barcode.
Saved 60 px barcode.
```

Después de ejecutar, abre los dos archivos PNG para ver la diferencia visual. Ambos códigos de barras codifican el mismo valor GTIN‑14 y se escanearán idénticamente, sin importar la altura.

## Por qué ajustar la altura de la barra es seguro para el escaneo

Los escáneres de códigos de barras leen el patrón de módulos claros y oscuros, no el recuento absoluto de píxeles. Mientras la **X‑dimension** permanezca dentro de la tolerancia del escáner (usualmente de 0.5 mm a 2 mm en unidades físicas), cambiar la altura no afecta la legibilidad. La biblioteca escala automáticamente los módulos, preservando las zonas silenciosas y los patrones de alineación requeridos.

## Trampas comunes y cómo evitarlas

| Trampa | Cómo solucionarla |
|---------|------------|
| **La carpeta de salida no existe** | Llama a `Directory.CreateDirectory(outputPath)` antes de guardar. |
| **X‑dimension incorrecta que produce escaneos borrosos** | Mantén `XDimension.Pixels` entre 1 px y 4 px para la mayoría de impresoras; prueba con un escáner físico. |
| **Usar un formato raster para códigos de barras muy grandes** | Cambia a `BarCodeImageFormat.Svg` para escalabilidad infinita sin pixelación. |
| **Olvidar restablecer `BarHeight` antes del segundo guardado** | Asegúrate de asignar la nueva altura **antes** de volver a llamar a `Save`. |

## Consejo profesional: generar múltiples tamaños en un bucle

Si necesitas un rango de alturas (p. ej., 30 px, 45 px, 60 px), un simple bucle `foreach` reduce la duplicación:

```csharp
int[] heights = { 30, 45, 60 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputPath}DatabarBarHeight{h}Pixels.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {h} px barcode.");
}
```

Este patrón escala bien para el procesamiento por lotes de catálogos de productos.

## Casos límite: diferentes formatos de imagen y configuraciones DPI

* **Salida SVG** – Usa `BarCodeImageFormat.Svg` para producir un archivo vectorial que pueda redimensionarse sin pérdida de calidad.
* **PNG de alta DPI** – Configura `generator.Parameters.Image.DpiX` y `DpiY` a 300 o 600 para imágenes listas para impresión; la altura de barra seguirá midiéndose en píxeles, por lo que deberás aumentarla proporcionalmente.
* **Simbologías no estándar** – Algunos tipos de código de barras (p. ej., QR Code) tienen una propiedad `Size` separada en lugar de `BarHeight`. Consulta la documentación de la biblioteca para esos casos.

## Probando el código de barras redimensionado

1. Abre cada PNG en un visor de imágenes y verifica las dimensiones en píxeles (p. ej., 150 × 30 px vs. 150 × 60 px).  
2. Imprime las imágenes al 100 % de escala.  
3. Escanea con un escáner de código de barras de mano o una aplicación móvil. Los datos decodificados deben ser

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [How to resize barcode in C# with Aspose.BarCode – step‑by‑step guide](/barcode/english/python-java/general/how-to-resize-barcode-in-c-with-aspose-barcode-step-by-step/)
- [How to save barcode images with Barcode Generator C# – step‑by‑step guide](/barcode/english/python-java/general/how-to-save-barcode-images-with-barcode-generator-c-step-by/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}