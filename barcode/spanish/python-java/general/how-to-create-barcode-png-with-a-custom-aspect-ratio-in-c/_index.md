---
category: general
date: 2026-10-05
description: Crear PNG de código de barras en C# y aprender cómo establecer la relación
  de aspecto 15 para códigos de barras DataBar apilados omnidireccionales.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to set aspect ratio
- set aspect ratio 15
language: es
lastmod: 2026-10-05
og_description: Crea un PNG de código de barras en C# y descubre cómo establecer una
  relación de aspecto de 15 para códigos de barras DataBar apilados omnidireccionales
  en unos pocos pasos.
og_image_alt: Screenshot showing a generated barcode PNG with aspect ratio 15
og_title: Crear PNG de código de barras en C# – tutorial para establecer la relación
  de aspecto 15
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Create barcode PNG in C# and learn how to set aspect ratio 15 for stacked
    DataBar omnidirectional barcodes.
  headline: How to create barcode PNG with a custom aspect ratio in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Cómo crear un PNG de código de barras con una relación de aspecto personalizada
  en C#
url: /es/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un PNG de código de barras con una relación de aspecto personalizada en C#

Si necesitas **crear un PNG de código de barras** en C#, esta guía te muestra **cómo establecer la relación de aspecto** 15 para un código de barras DataBar apilado omnidireccional. Revisaremos cada llamada a la API, explicaremos por qué la relación de aspecto es importante y te proporcionaremos un ejemplo completo y ejecutable que puedes insertar en cualquier proyecto .NET.

Generar una imagen de código de barras es un requisito común para sistemas de inventario, etiquetas de envío y aplicaciones de punto de venta minorista. Al final de este tutorial tendrás un archivo PNG que cumple con las especificaciones visuales exactas requeridas por tu socio comercial. Sin herramientas externas, sin edición manual de imágenes—solo código.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* .NET 6.0 o posterior (el ejemplo usa .NET 6 pero funciona con .NET 5+)
* Visual Studio 2022 (o cualquier IDE que soporte .NET)
* El paquete NuGet **Aspose.BarCode for .NET**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Permiso de escritura en la carpeta donde deseas guardar el archivo PNG

Estos requisitos son mínimos; el mismo código funciona en .NET Core, .NET Framework o una aplicación de consola.

## Crear PNG de código de barras con Aspose.BarCode

El primer paso es instanciar la clase `BarcodeGenerator` con el tipo de código de barras correcto. En este caso usamos `EncodeTypes.DatabarStackedOmniDirectional`, que produce un DataBar apilado que puede leerse desde cualquier dirección.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

*Por qué es importante:* El constructor recibe dos argumentos—**la simbología del código de barras** y **la cadena de datos**. El formato DataBar espera un identificador de aplicación GS1, por eso los datos de ejemplo comienzan con `(01)`.

## Cómo establecer la relación de aspecto para un DataBar apilado

El ancho visual de un DataBar se controla mediante la propiedad **aspect ratio**. Una relación mayor hace que las barras sean más anchas, lo que puede mejorar la fiabilidad del escaneo en impresoras de baja resolución.

```csharp
// Step 2: Define the module width (X‑dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

El `XDimension` define el tamaño de un módulo único (la barra o espacio más pequeño). Mantenerlo en 2 px produce una imagen nítida y de alta densidad adecuada para la mayoría de impresoras de etiquetas.

## Establecer relación de aspecto 15 – recorrido del código

Ahora aplicamos el requisito de **establecer la relación de aspecto 15**. Este es el núcleo del tutorial y muestra la llamada exacta a la API que necesitas.

```csharp
// Step 3: Set the DataBar aspect ratio to 15 for a wider appearance
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

*¿Por qué 15?* La relación de aspecto predeterminada para DataBar apilado es 12. Incrementarla a 15 amplía el ancho de cada barra en un 25 %, lo que a menudo coincide con las especificaciones de los proveedores logísticos que requieren un código de barras más ancho para un escaneo más rápido.

## Guardar el código de barras como PNG

Con el generador configurado, el paso final es escribir la imagen en disco. El método `Save` acepta una ruta de archivo y un enumerado de formato de imagen.

```csharp
// Step 4: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
```

El formato PNG conserva la calidad sin pérdidas, garantizando que el código de barras se renderice exactamente como se diseñó en cualquier pantalla o impresora.

## Ejemplo completo y salida esperada

A continuación se muestra el programa completo que puedes copiar en el método `Main` de una aplicación de consola. Incluye todos los pasos descritos arriba, más un pequeño mensaje de verificación.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with stacked DataBar (omnidirectional) and sample GS1 data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Set the DataBar aspect ratio to 15 – this is the key to a wider barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;

        // Choose a folder you have write access to
        string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";

        // Save the barcode as a PNG file
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode PNG created at: {outputPath}");
    }
}
```

**Salida esperada**

Al ejecutar el programa se crea un archivo llamado `DatabarAspectRatio15.png` que contiene un código de barras DataBar apilado claro y ancho. Cuando abras el PNG, deberías ver un código de barras estirado horizontalmente que aún cumple con las especificaciones GS1 DataBar.

![PNG de código de barras con relación de aspecto 15](barcode-aspect15.png)

*Texto alternativo de la imagen:* **crear PNG de código de barras que muestra un DataBar apilado con relación de aspecto 15**

### Consejos y errores comunes

| Situación | Recomendación |
|-----------|----------------|
| **La imagen se ve borrosa** | Aumenta `XDimension.Pixels` a 3 px o más, pero mantén el tamaño total de la imagen por debajo de 500 px para evitar archivos demasiado grandes. |
| **El escáner no puede leer el código** | Verifica que la cadena de datos siga el formato GS1 (prefijo `(01)`). Además, asegúrate de que la resolución de la impresora sea al menos 300 dpi. |
| **Necesitas un formato de archivo diferente** | Reemplaza `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` o `Gif`—la API soporta todos los principales formatos raster. |
| **Ejecutando en una aplicación web** | Usa `generator.Save(Stream, BarCodeImageFormat.Png)` para escribir directamente en la respuesta HTTP sin tocar el sistema de archivos. |

### Extender el ejemplo

* **Múltiples códigos de barras en una imagen:** Crea instancias adicionales de `BarcodeGenerator` y dibújalas en un solo `Bitmap` usando `Graphics`.  
* **Agregar texto legible por humanos:** Establece `generator.Parameters.Caption.Visible = true` y personaliza la fuente mediante `generator.Parameters.Caption.Font`.  
* **Relación de aspecto dinámica:** Obtén el valor de la relación de un archivo de configuración o base de datos para generar códigos de barras con anchos variables sobre la marcha.

## Conclusión

En este tutorial aprendiste cómo **crear un PNG de código de barras** en C# y establecer con precisión la **relación de aspecto** 15 para un código de barras DataBar apilado omnidireccional. El código completo y ejecutable muestra cada llamada a la API requerida, explica por qué cada configuración es importante y brinda consejos prácticos para implementaciones en el mundo real.  

A continuación, podrías explorar **cómo establecer la relación de aspecto** para otros tipos de códigos de barras (p. ej., QR Code o Code 128) o integrar el generador en un servicio ASP .NET Core que devuelva imágenes de códigos de barras bajo demanda. ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo crear imágenes PNG de databar con C# y Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [Cómo crear un código de barras databar apilado en C# con Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [Personalizar la relación de aspecto del databar apilado omnidireccional en .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}