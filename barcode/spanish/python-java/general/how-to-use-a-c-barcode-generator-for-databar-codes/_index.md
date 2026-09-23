---
category: general
date: 2026-09-23
description: El tutorial de generador de códigos de barras en C# muestra cómo generar
  imágenes de códigos de barras con relaciones de aspecto personalizadas usando la
  biblioteca Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- DataBar barcode C#
- barcode aspect ratio
- Aspose.BarCode C#
- barcode image export
language: es
lastmod: 2026-09-23
og_description: La guía del generador de códigos de barras en C# le muestra cómo generar
  imágenes de códigos de barras, ajustar relaciones de aspecto y exportar archivos
  PNG usando Aspose.BarCode.
og_image_alt: Screenshot of a barcode created with a C# barcode generator
og_title: Crea códigos de barras de alta calidad con un generador de códigos de barras
  en C#
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  headline: How to use a C# barcode generator for DataBar codes
  type: TechArticle
- description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  name: How to use a C# barcode generator for DataBar codes
  steps:
  - name: Switching to another barcode type
    text: 'If you need a QR code, Code 128, or PDF417, replace the enum value in the
      constructor:'
  - name: Handling unsupported characters
    text: 'The `BarcodeGenerator` validates the input string against the selected
      symbology. Supplying an illegal character throws an `ArgumentException`. Wrap
      the creation in a try‑catch block to provide a friendly error message:'
  - name: Exporting to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the second argument
      of `Save` accordingly:'
  - name: High‑resolution output for printing
    text: 'When printing on high‑DPI printers, increase the X‑dimension and optionally
      set the `Resolution` property:'
  type: HowTo
tags:
- barcode
- c#
- Aspose
title: Cómo usar un generador de códigos de barras C# para códigos DataBar
url: /es/python-java/general/how-to-use-a-c-barcode-generator-for-databar-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo usar un generador de códigos de barras C# para códigos DataBar

Si necesitas un **c# barcode generator** que pueda producir símbolos DataBar apilados Omni‑Directional, esta guía te brinda una solución completa y lista para ejecutar. Verás cómo generar imágenes de códigos de barras, controlar la dimensión X y cambiar la relación de aspecto sin salir del IDE.

Generar códigos de barras es un requisito común para sistemas de inventario, etiquetas de envío y aplicaciones punto de venta. Al final de este tutorial podrás crear archivos PNG con cualquier relación de aspecto que elijas, y comprenderás cómo adaptar el código para otros tipos de códigos de barras.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* .NET 6.0 SDK o posterior instalado  
* Visual Studio 2022 (o cualquier editor C# que prefieras)  
* Una referencia NuGet a **Aspose.BarCode** – la biblioteca que impulsa la clase `BarcodeGenerator`  

No necesitas una biblioteca gráfica separada; Aspose.BarCode maneja la codificación de imágenes internamente.

## Paso 1: Instalar el paquete NuGet Aspose.BarCode

Abre una terminal en la carpeta de tu proyecto y ejecuta:

```bash
dotnet add package Aspose.BarCode
```

El comando agrega la versión estable más reciente de la biblioteca a tu archivo de proyecto, haciendo que la clase `BarcodeGenerator` esté disponible para su uso.

## Paso 2: Definir la carpeta de salida

Elige una carpeta donde se guardarán los archivos PNG generados. Usar una ruta absoluta o relativa funciona de la misma manera, pero una ruta relativa mantiene el proyecto portátil.

```csharp
// Define the output folder (relative to the project root)
string outputFolder = "GeneratedBarcodes/";
Directory.CreateDirectory(outputFolder); // Ensure the folder exists
```

Crear el directorio programáticamente evita errores en tiempo de ejecución si la carpeta falta.

## Paso 3: Instanciar el generador de códigos de barras C# con datos de ejemplo

El constructor `BarcodeGenerator` requiere dos argumentos: el tipo de código de barras y la cadena de datos. Para un símbolo DataBar apilado Omni‑Directional utilizas `EncodeTypes.DatabarStackedOmniDirectional`.

```csharp
// Create a barcode generator for a DataBar stacked Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

La cadena de datos sigue el formato del Identificador de Aplicación GS1. El enumerado `EncodeTypes` contiene más de 150 estándares de códigos de barras; puedes cambiar a otro tipo modificando el valor del enumerado.

## Paso 4: Establecer la dimensión X (tamaño en píxeles) para el código de barras

La dimensión X controla el ancho de la barra más estrecha. Un valor de píxel de 2 produce una imagen nítida y de alta resolución adecuada para la mayoría de pantallas.

```csharp
// Set the X‑dimension to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Ajustar la dimensión X es opcional, pero te brinda un control granular sobre la densidad visual del código de barras.

## Paso 5: Generar un código de barras con una relación de aspecto de 15 y guardarlo como PNG

La propiedad `AspectRatio` pertenece al sub‑objeto `DataBar`. Cambiar este valor estira o comprime el código de barras verticalmente mientras preserva los datos codificados.

```csharp
// Set aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

El método `Save` escribe el código de barras en la ruta de archivo especificada. El enumerado `BarCodeImageFormat.Png` garantiza compresión sin pérdida.

![c# barcode generator output example](generated_barcode_example.png)

*Imagen: código de barras generado con una relación de aspecto de 15.*

## Paso 6: Cambiar la relación de aspecto a 30 y generar una segunda imagen

Reutilizar la misma instancia de `BarcodeGenerator` evita asignar un nuevo objeto. Simplemente actualiza `AspectRatio` y llama a `Save` nuevamente.

```csharp
// Update aspect ratio to 30 and save a second image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

Ahora tienes dos archivos PNG que difieren solo en el escalado vertical. Esta técnica es útil cuando necesitas los mismos datos renderizados para diferentes tamaños de etiqueta.

## Variaciones comunes y casos límite

### Cambiar a otro tipo de código de barras

Si necesitas un código QR, Code 128 o PDF417, reemplaza el valor del enumerado en el constructor:

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(
    EncodeTypes.QR, "https://example.com");
```

Todos los demás pasos de configuración (dimensión X, guardado) permanecen idénticos.

### Manejo de caracteres no compatibles

El `BarcodeGenerator` valida la cadena de entrada contra la simbología seleccionada. Proporcionar un carácter ilegal lanza una `ArgumentException`. Envuelve la creación en un bloque try‑catch para ofrecer un mensaje de error amigable:

```csharp
try
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid data for the selected barcode type: {ex.Message}");
}
```

### Exportar a otros formatos de imagen

Aspose.BarCode admite BMP, JPEG, TIFF y SVG. Cambia el segundo argumento de `Save` en consecuencia:

```csharp
barcodeGenerator.Save($"{outputFolder}Databar.svg", BarCodeImageFormat.Svg);
```

### Salida de alta resolución para impresión

Al imprimir en impresoras de alta DPI, aumenta la dimensión X y, opcionalmente, establece la propiedad `Resolution`:

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.ImageResolution.Dpi = 300;
```

Estas configuraciones producen archivos más grandes pero mantienen bordes nítidos en medios físicos.

## Salida esperada

Ejecutar el programa completo crea los siguientes archivos dentro de `GeneratedBarcodes/`:

* `DatabarAspectRatio15.png` – un código DataBar de altura estándar  
* `DatabarAspectRatio30.png` – una versión estirada verticalmente  

Ambas imágenes contienen los mismos datos GS1 codificados, y puedes verificarlas con cualquier aplicación escáner de códigos de barras.

## Código fuente completo

Copia el código a continuación en un nuevo proyecto de consola (`dotnet new console`) y ejecútalo. El programa imprime mensajes de estado en la consola y escribe los archivos PNG en disco.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Define the output folder
        string outputFolder = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputFolder);

        // Step 3: Create a C# barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Step 4: Set common barcode properties (pixel size of X‑dimension)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 5: Generate a barcode with aspect ratio 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        string file15 = Path.Combine(outputFolder, "DatabarAspectRatio15.png");
        barcodeGenerator.Save(file15, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

        // Step 6: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        string file30 = Path.Combine(outputFolder, "DatabarAspectRatio30.png");
        barcodeGenerator.Save(file30, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
    }
}
```

Ejecutar el programa produce una salida en consola similar a:

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

## Conclusión

Ahora tienes un **c# barcode generator** que puede crear símbolos DataBar apilados Omni‑Directional, ajustar la dimensión X y exportar archivos PNG con relaciones de aspecto personalizadas. El mismo patrón funciona para cualquier otra simbología de código de barras soportada por Aspose.BarCode, facilitando la integración de la generación de códigos de barras en soluciones de inventario, envío o punto de venta.

Si deseas explorar más, prueba:

* Generar códigos QR o símbolos PDF417 (`how to generate barcode` para aplicaciones móviles)  
* Exportar a SVG para gráficos web escalables  
* Incrustar las imágenes generadas directamente en facturas PDF usando Aspose.PDF  

Experimenta con diferentes valores de `AspectRatio`, tamaños de dimensión X y formatos de salida para coincidir exactamente con lo que necesitas


## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo generar códigos de barras Aztec con relación de aspecto personalizada usando Aspose.BarCode para .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Cómo ajustar el tamaño del código de barras – Relación de aspecto Codablock F con Aspose.BarCode para .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [Cómo generar y ajustar la altura del código de barras One-Dimensional Databar usando Aspose.BarCode para .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}