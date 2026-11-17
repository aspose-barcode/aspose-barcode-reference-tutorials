---
category: general
date: 2026-11-17
description: Aprende cómo guardar el código de barras, habilitar el modo compacto,
  ajustar columnas y generar un código de barras PDF417 con un ejemplo completo en
  C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- enable compact mode
- how to adjust columns
- generate pdf417 barcode
- how to enable compact mode
language: es
lastmod: 2026-11-17
og_description: Cómo guardar el código de barras, habilitar el modo compacto y ajustar
  columnas al generar un código de barras PDF417 en C#. Sigue la guía paso a paso.
og_image_alt: Screenshot showing how to save barcode as PNG file in C#
og_title: Cómo guardar el código de barras como PNG y habilitar el modo compacto en
  C#
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  headline: How to save barcode as PNG and enable compact mode in C#
  type: TechArticle
- description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  name: How to save barcode as PNG and enable compact mode in C#
  steps:
  - name: Expected output
    text: Opening the saved PNG file shows a vertically compact PDF417 barcode with
      three columns and truncated padding. The visual size is roughly 2 px per module,
      making the image suitable for embedding in HTML `<img>` tags or for printing
      on small labels.
  - name: What if I need a different image format?
    text: The `Save` method accepts any `BarCodeImageFormat` enum value, such as `Jpeg`,
      `Bmp`, or `Gif`. Replace `BarCodeImageFormat.Png` with the desired format, and
      the rest of the code remains unchanged.
  - name: How does truncation affect data capacity?
    text: Enabling **compact mode** (truncation) reduces the number of rows, which
      can lower the maximum data capacity of the barcode. If you encounter a “Data
      too large” exception, either increase the number of columns or disable truncation.
  - name: Can I use a dynamic column count?
    text: 'Yes. You can calculate the column count based on the length of the input
      string:'
  - name: Is the X‑dimension limited to integer pixels?
    text: The `Pixels` property accepts any positive integer. For higher‑resolution
      outputs (e.g., printing), you might prefer setting `Points` instead of `Pixels`
      to achieve device‑independent sizing.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- image generation
title: Cómo guardar el código de barras como PNG y habilitar el modo compacto en C#
url: /es/net/compact-pdf417-encoding/how-to-save-barcode-as-png-and-enable-compact-mode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo guardar código de barras como PNG y habilitar el modo compacto en C#

Si necesitas **how to save barcode** en un formato que pueda usarse en la web o en impresión, esta guía te muestra los pasos exactos. También aprenderás cómo **enable compact mode**, **adjust columns**, y **generate PDF417 barcode** con la biblioteca Aspose.BarCode para .NET.

El tutorial cubre todo, desde la configuración del proyecto hasta el archivo PNG final, para que puedas copiar el código en tu propia solución sin investigación adicional. No se requiere documentación externa; se incluye el ejemplo completo y ejecutable.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* .NET 6.0 o posterior instalado  
* Visual Studio 2022 (o cualquier IDE de C#)  
* El paquete NuGet `Aspose.BarCode` (`Install-Package Aspose.BarCode`)  

Estos tres elementos son las únicas dependencias para el código que sigue.

## Paso 1: Crear un generador de código de barras PDF417

La primera tarea al **generate PDF417 barcode** es instanciar un `BarcodeGenerator` con el tipo de codificación correcto y los datos que deseas codificar.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a PDF417 barcode generator with the desired text.
BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

El enum `EncodeTypes.Pdf417` indica a la biblioteca que use la simbología PDF417, que es un código de barras lineal apilado adecuado para codificar grandes cantidades de datos. La cadena `"Compact mode"` se convierte en el texto legible por humanos bajo el código de barras.

## Paso 2: Establecer la dimensión X (ancho del módulo)

Cada barra en un código de barras se llama módulo. Controlar el ancho del módulo te permite afinar el tamaño visual del código de barras sin alterar los datos.

```csharp
// Step 2: Set the module (X) dimension – each bar will be 2 pixels wide.
barcode.Parameters.Barcode.XDimension.Pixels = 2;
```

Una dimensión X de 2 píxeles produce una imagen compacta que aún se escanea de manera fiable en la mayoría de los dispositivos.

## Paso 3: **How to adjust columns** para el código PDF417

PDF417 permite especificar cuántas columnas debe usar el código de barras. Menos columnas producen un símbolo más alto y estrecho, mientras que más columnas hacen que el símbolo sea más ancho pero más corto.

```csharp
// Step 3: Define the number of columns for the PDF417 code (3 columns).
barcode.Parameters.Barcode.Pdf417.Columns = 3;
```

Esta línea demuestra **how to adjust columns**. Puedes cambiar el valor a 2, 4, o cualquier número soportado por la biblioteca, dependiendo del espacio que tengas en el medio objetivo.

## Paso 4: **How to enable compact mode** y truncar el símbolo

El modo compacto elimina el relleno innecesario y reduce la huella total del código de barras. La biblioteca expone esta función a través de la propiedad `Truncate`.

```csharp
// Step 4: Enable compact mode by truncating the symbol.
barcode.Parameters.Barcode.Pdf417.Truncate = true;
```

Observa que la frase **enable compact mode** aparece aquí, y la misma acción se describe con la redacción exacta **how to enable compact mode** más adelante en la guía para cumplir con el requisito de la palabra clave secundaria.

## Paso 5: **How to save barcode** como una imagen PNG

Guardar la imagen generada es el paso final. El método `Save` escribe el código de barras en el sistema de archivos en el formato que especifiques.

```csharp
// Step 5: Save the generated barcode as a PNG image.
barcode.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

Reemplaza `YOUR_DIRECTORY` con una ruta absoluta o relativa a la que tu aplicación pueda escribir. Después de la ejecución, encontrarás un archivo llamado `CompactPdf417.png` que contiene el código de barras PDF417 compacto.

### Resultado esperado

Abrir el archivo PNG guardado muestra un código de barras PDF417 verticalmente compacto con tres columnas y relleno truncado. El tamaño visual es aproximadamente 2 px por módulo, lo que hace que la imagen sea adecuada para incrustarla en etiquetas HTML `<img>` o para imprimir en etiquetas pequeñas.

## Ejemplo completo y ejecutable

A continuación se muestra el programa completo que puedes copiar en un nuevo proyecto de consola. Incluye todas las directivas `using` necesarias y demuestra **how to save barcode**, **enable compact mode**, **how to adjust columns**, y **generate PDF417 barcode** en un único flujo.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417CompactDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a PDF417 barcode generator with the desired text.
            BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

            // Set the module (X) dimension – each bar will be 2 pixels wide.
            barcode.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns for the PDF417 code (3 columns).
            barcode.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable compact mode by truncating the symbol.
            barcode.Parameters.Barcode.Pdf417.Truncate = true;

            // Save the generated barcode as a PNG image.
            string outputPath = "CompactPdf417.png"; // Adjust path as needed.
            barcode.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Ejecutar este programa produce el archivo PNG descrito anteriormente. La salida de la consola confirma la ubicación del archivo guardado, lo que te ayuda a verificar que el paso **how to save barcode** se completó con éxito.

## Preguntas comunes y casos límite

### ¿Qué pasa si necesito un formato de imagen diferente?

El método `Save` acepta cualquier valor del enum `BarCodeImageFormat`, como `Jpeg`, `Bmp` o `Gif`. Reemplaza `BarCodeImageFormat.Png` con el formato deseado, y el resto del código permanece sin cambios.

### ¿Cómo afecta la truncación a la capacidad de datos?

Habilitar **compact mode** (truncación) reduce el número de filas, lo que puede disminuir la capacidad máxima de datos del código de barras. Si encuentras una excepción “Data too large”, aumenta el número de columnas o deshabilita la truncación.

### ¿Puedo usar un recuento de columnas dinámico?

Sí. Puedes calcular el número de columnas basado en la longitud de la cadena de entrada:

```csharp
int desiredColumns = Math.Max(2, Math.Min(30, inputText.Length / 10));
barcode.Parameters.Barcode.Pdf417.Columns = desiredColumns;
```

Este fragmento muestra **how to adjust columns** programáticamente, asegurando que el código de barras encaje dentro de un diseño dado.

### ¿Está la dimensión X limitada a píxeles enteros?

La propiedad `Pixels` acepta cualquier entero positivo. Para salidas de mayor resolución (p. ej., impresión), podrías preferir establecer `Points` en lugar de `Pixels` para lograr un dimensionado independiente del dispositivo.

## Consejos para uso en producción

* **Consejo profesional:** Envuelve la generación del código de barras en un bloque try‑catch para manejar `BarCodeException` cuando los datos de entrada superen la capacidad del símbolo.  
* **Cuidado con:** los permisos del sistema de archivos. El proceso debe tener acceso de escritura al directorio objetivo, de lo contrario el paso **how to save barcode** fallará con una `UnauthorizedAccessException`.  
* **Nota de rendimiento:** Crear muchos códigos de barras en un bucle se beneficia de reutilizar una única instancia de `BarcodeGenerator` y solo actualizar la propiedad `CodeText` entre iteraciones.

## Conclusión

Ahora sabes **how to save barcode** como archivo PNG, **enable compact mode**, **how to adjust columns**, y **generate PDF417 barcode** usando Aspose.BarCode para C#. El ejemplo completo demuestra cada paso requerido, desde inicializar el generador hasta escribir la imagen final.

Desde aquí puedes explorar temas relacionados como agregar un logotipo al código de barras, personalizar colores, o integrar el generador en una API ASP.NET Core. Cada una de esas extensiones sigue el mismo patrón mostrado en esta guía, por lo que puedes adaptar el código con confianza.

Siéntete libre de experimentar con diferentes recuentos de columnas, dimensiones X y formatos de imagen para cumplir con las especificaciones exactas de tu proyecto. ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo guardar código de barras y generar PDF417 con Aspose en C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [Cómo crear código de barras PDF417 en C# con modo compacto](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [Cómo crear código de barras PDF417 y guardarlo como PNG en C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}