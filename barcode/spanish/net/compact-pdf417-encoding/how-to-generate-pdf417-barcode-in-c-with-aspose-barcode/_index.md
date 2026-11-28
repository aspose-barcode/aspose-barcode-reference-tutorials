---
category: general
date: 2026-11-27
description: Aprende a generar códigos de barras PDF417 en C# usando Aspose.BarCode.
  Ajusta las dimensiones, establece el número de columnas y guarda como PNG en unas
  pocas líneas de código.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode C#
- PDF417 barcode dimensions
- barcode image PNG
- BarcodeGenerator usage
language: es
lastmod: 2026-11-27
og_description: Genera códigos de barras PDF417 en C# al instante. Este tutorial muestra
  cómo configurar dimensiones, número de columnas y guardar el resultado como una
  imagen PNG.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: Generar código de barras PDF417 en C# – guía rápida con Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Adjust
    dimensions, set column count, and save as PNG in a few lines of code.
  headline: How to generate PDF417 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Adjust
    dimensions, set column count, and save as PNG in a few lines of code.
  name: How to generate PDF417 barcode in C# with Aspose.BarCode
  steps:
  - name: Why each line matters
    text: '* **BarcodeGenerator** – the core class that creates a barcode image. Passing
      `EncodeTypes.Pdf417` selects the PDF417 symbology. * **XDimension.Pixels** –
      determines the smallest bar width. Smaller values shrink the image; larger values
      improve readability on low‑resolution scanners. * **Pdf417.Colu'
  - name: Changing the encoded data
    text: 'Replace the second argument of `BarcodeGenerator` with any UTF‑8 string,
      e.g.:'
  - name: Adjusting image size without losing quality
    text: 'If you need a larger image for printing, increase `XDimension.Pixels`:'
  - name: Handling very long inputs
    text: 'PDF417 can encode up to 1 850 characters. For extremely long strings, you
      may want to increase the column count:'
  - name: Saving in other formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the format like
      this:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Cómo generar código de barras PDF417 en C# con Aspose.BarCode
url: /es/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo generar código de barras PDF417 en C# con Aspose.BarCode

Si necesita **generar código de barras PDF417** en una aplicación .NET, esta guía le muestra una solución concisa y completa. Verá cómo crear el código de barras, ajustar su tamaño y escribir el resultado en un archivo PNG, todo con la biblioteca Aspose.BarCode.

Generar un código de barras PDF417 es común cuando necesita codificar grandes cantidades de datos para escanear en dispositivos móviles, tarjetas de embarque o etiquetas de inventario. Al final de este tutorial tendrá un programa de consola listo para ejecutar que produce una imagen PNG de alta calidad.

## Requisitos previos

Antes de comenzar, asegúrese de tener:

* SDK .NET 6.0 o posterior instalado  
* Una versión reciente de **Aspose.BarCode for .NET** (el paquete NuGet `Aspose.BarCode`)  
* Un IDE o editor (Visual Studio, VS Code, Rider, etc.)  

El código funciona en Windows, Linux y macOS porque Aspose.BarCode es multiplataforma.

## Paso 1: Crear un nuevo proyecto de consola

Abra una terminal y ejecute:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Esto crea un proyecto C# mínimo llamado **Pdf417Demo** y agrega la dependencia `Aspose.BarCode`.

## Paso 2: Escribir el código de generación del código de barras

Abra **Program.cs** y reemplace su contenido con lo siguiente:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Create a PDF417 barcode generator with the desired text
            // EncodeTypes.Pdf417 tells Aspose.BarCode which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417, "Sample text for PDF417 barcode");

            // 2️⃣ Adjust barcode dimensions and column count
            // XDimension controls the width of a single module (pixel size).
            // Setting it to 2 pixels yields a compact yet readable barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Columns define how many data columns the barcode will have.
            // A value of 3 works well for short strings; increase for longer data.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Optional: increase error correction level for more robust scanning.
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 2;

            // 3️⃣ Save the generated barcode as a PNG file
            // The output path can be absolute or relative to the project folder.
            string outputPath = "Pdf417Basic.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to '{outputPath}'.");
        }
    }
}
```

### Por qué cada línea es importante

* **BarcodeGenerator** – la clase principal que crea una imagen de código de barras. Pasar `EncodeTypes.Pdf417` selecciona la simbología PDF417.  
* **XDimension.Pixels** – determina el ancho de barra más pequeño. Valores más bajos reducen la imagen; valores más altos mejoran la legibilidad en escáneres de baja resolución.  
* **Pdf417.Columns** – controla el número de columnas de datos. Más columnas producen un código de barras más corto pero más alto; menos columnas lo hacen más ancho.  
* **ErrorCorrectionLevel** – niveles más altos añaden datos redundantes, haciendo que el código de barras sea tolerante a daños a costa de mayor tamaño.  
* **Save(..., BarCodeImageFormat.Png)** – escribe la imagen en disco en formato PNG, un formato sin pérdida ideal para procesamiento posterior o incrustación en documentos.

## Paso 3: Compilar y ejecutar el programa

Desde la terminal, ejecute:

```bash
dotnet run
```

Debería ver:

```
PDF417 barcode saved to 'Pdf417Basic.png'.
```

Un archivo llamado **Pdf417Basic.png** aparece en la carpeta del proyecto. Al abrirlo se muestra un código de barras PDF417 claro que codifica el texto *“Sample text for PDF417 barcode”*.

![Generated PDF417 barcode saved as a PNG file](pdf417-barcode-example.png "Generated PDF417 barcode in PNG format")

*Texto alternativo de la imagen: captura de pantalla de un código de barras PDF417 generado y guardado como archivo PNG, que demuestra el resultado del tutorial de generación de código de barras PDF417.*

## Paso 4: Variaciones comunes y casos límite

### Cambiar los datos codificados

Reemplace el segundo argumento de `BarcodeGenerator` con cualquier cadena UTF‑8, por ejemplo:

```csharp
new BarcodeGenerator(EncodeTypes.Pdf417, "https://example.com/checkout?order=12345")
```

El generador divide automáticamente los datos entre filas y columnas.

### Ajustar el tamaño de la imagen sin perder calidad

Si necesita una imagen más grande para impresión, aumente `XDimension.Pixels`:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // double the module width
```

### Manejo de entradas muy largas

PDF417 puede codificar hasta 1 850 caracteres. Para cadenas extremadamente largas, puede que desee aumentar el recuento de columnas:

```csharp
generator.Parameters.Barcode.Pdf417.Columns = 5; // more columns, less height
```

Si el contenido supera la capacidad máxima, Aspose.BarCode lanza una `ArgumentException`. Envuelva el código de generación en un bloque try‑catch para presentar un mensaje de error amigable.

### Guardar en otros formatos

Aspose.BarCode admite BMP, JPEG, TIFF y SVG. Cambie el formato de la siguiente manera:

```csharp
generator.Save("Pdf417Vector.svg", BarCodeImageFormat.Svg);
```

## Paso 5: Verificar el código de barras

Puede confirmar que el código de barras es válido escaneándolo con cualquier aplicación lectora de PDF417 (p. ej., aplicaciones de cámara de smartphone que soportan escaneo de códigos de barras). El texto decodificado debe coincidir con la cadena que pasó al generador.

Si el escaneo falla:

* Asegúrese de que la imagen no esté comprimida (use PNG o SVG sin pérdida).  
* Verifique que `ErrorCorrectionLevel` sea lo suficientemente alto para el entorno previsto.  
* Compruebe que las dimensiones del código de barras sean apropiadas para la resolución del escáner.

## Conclusión

Ahora sabe cómo **generar código de barras PDF417** en C# usando Aspose.BarCode, personalizar sus dimensiones, establecer el número de columnas y exportar el resultado como una imagen PNG. Este enfoque funciona para una amplia gama de escenarios, desde la emisión de boletos móviles hasta la gestión de inventario.

A continuación, podría explorar:

* **Lectura** de un código de barras PDF417 con `BarCodeReader`.  
* Generar otras simbologías como QR Code o DataMatrix.  
* Incrustar el PNG en PDFs, informes o páginas web.  

Siéntase libre de experimentar con diferentes niveles de corrección de errores, formatos de imagen y cargas de datos para adaptarse a las necesidades de su proyecto. ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarle a dominar características adicionales de la API y explorar enfoques de implementación alternativos en sus propios proyectos.

- [Cómo generar código de barras PDF417 en C# con Aspose.BarCode BarcodeGenerator](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcodegenerator/)
- [Cómo generar código de barras PDF417 y renderizarlo como PNG](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-and-render-it-as-png/)
- [Cómo generar código de barras PDF417 en C# y establecer el tamaño del código de barras](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}