---
category: general
date: 2026-09-10
description: Genera códigos de barras PDF417 en C# rápidamente. Aprende cómo generar
  PDF417 y cómo cambiar el tamaño del código de barras con Aspose.BarCode en solo
  unas pocas líneas.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- how to generate PDF417
- how to change barcode size
language: es
lastmod: 2026-09-10
og_description: Genera códigos de barras PDF417 en C# al instante. Este tutorial muestra
  cómo generar PDF417 y cómo cambiar el tamaño del código de barras usando Aspose.BarCode.
og_image_alt: generate PDF417 barcode example showing 4 columns and 9 rows
og_title: Generar código de barras PDF417 en C# – guía completa de programación
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  headline: How to generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  name: How to generate PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Create a new console project:'
    text: 'Create a new console project:'
  - name: Add the Aspose.BarCode reference (see prerequisites).
    text: Add the Aspose.BarCode reference (see prerequisites).
  - name: Open `Program.cs` and replace its content with the full example below.
    text: Open `Program.cs` and replace its content with the full example below.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Cómo generar un código de barras PDF417 en C# – guía paso a paso
url: /es/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo generar un código de barras PDF417 en C# – guía paso a paso

Si necesitas **generar un código de barras PDF417** en una aplicación .NET, esta guía te muestra exactamente cómo hacerlo. Verás un ejemplo conciso y listo para ejecutar que crea un código de barras PDF417, te permite controlar su tamaño y guarda el resultado como una imagen PNG.

Generar un código de barras PDF417 es un requisito común para sistemas de inventario, tarjetas de embarque y seguimiento de documentos. En este tutorial también cubrimos **cómo cambiar el tamaño del código de barras** para que el código se adapte a diferentes necesidades de impresión o visualización en pantalla.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* .NET 6.0 o posterior (el código también funciona con .NET Framework 4.6+)
* Visual Studio 2022 o cualquier IDE de C#
* El paquete NuGet **Aspose.BarCode for .NET**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Familiaridad básica con aplicaciones de consola en C#

## Configuración del proyecto

1. Crea un nuevo proyecto de consola:

   ```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

2. Añade la referencia a Aspose.BarCode (ver requisitos previos).  

3. Abre `Program.cs` y reemplaza su contenido con el ejemplo completo a continuación.

## Paso 1: Generar código de barras PDF417

El primer paso es crear una instancia de `BarcodeGenerator` configurada para la simbología **PDF417**. Este objeto es el punto de entrada para todas las operaciones de códigos de barras.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");
```

*Por qué es importante* – El valor de enumeración `EncodeTypes.Pdf417` indica a Aspose.BarCode que use el estándar PDF417, mientras que el segundo argumento proporciona los datos que se codificarán. El generador ahora contiene un objeto de código de barras completo que puedes personalizar antes de guardarlo.

## Paso 2: Cómo cambiar el tamaño del código de barras (tamaño del módulo)

Los códigos de barras PDF417 están compuestos por pequeños módulos cuadrados. Ajustar el tamaño del módulo cambia las dimensiones generales de la imagen sin alterar los datos codificados.

```csharp
        // Step 2: Define the module size (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module
```

*Por qué es importante* – Un `XDimension` mayor produce un código de barras más grande, adecuado para impresión de alta resolución; un valor menor es mejor para la visualización en pantalla. El valor predeterminado suele ser 1 px, lo que puede verse apretado en monitores modernos.

## Paso 3: Configurar el diseño – columnas y filas

PDF417 permite definir el número de columnas y filas, lo que influye tanto en la forma del código de barras como en su capacidad de corrección de errores.

```csharp
        // Step 3: Configure the layout – set the number of columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

*Por qué es importante* – Más columnas hacen que el código de barras sea más ancho, mientras que más filas lo hacen más alto. Ajusta estos valores para que encajen en el espacio disponible en tu interfaz de usuario o etiqueta impresa.

## Paso 4: Guardar la imagen del código de barras

Finalmente, escribe el código de barras en un archivo. Aquí usamos PNG porque conserva bordes nítidos y soporta transparencia.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        string outputPath = "LayoutPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode saved to {outputPath}");
    }
}
```

Ejecutar el programa crea `LayoutPdf417.png` en la carpeta de salida del proyecto. La imagen se verá así:

![generate PDF417 barcode example showing 4 columns and 9 rows](https://example.com/images/pdf417-sample.png){#barcode-image alt="ejemplo de generación de código de barras PDF417 mostrando 4 columnas y 9 filas"}

*Consejo*: Si necesitas un formato de imagen diferente (JPEG, BMP, TIFF), reemplaza `BarCodeImageFormat.Png` con el valor de enumeración correspondiente.

## Cómo generar PDF417 – fuentes de datos alternativas

El código anterior usa una cadena codificada directamente `"Layout test"`. En escenarios reales a menudo obtienes datos de una base de datos, un archivo o la entrada del usuario.

```csharp
string dataFromDb = GetOrderNumber(); // your own method
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, dataFromDb);
```

El resto de los pasos (tamaño, diseño, guardado) permanecen sin cambios. Esto demuestra **cómo generar PDF417** a partir de fuentes dinámicas sin complejidad adicional.

## Errores comunes y cómo evitarlos

| Problema | Por qué ocurre | Solución |
|-------|----------------|-----|
| El código de barras aparece borroso | `XDimension` configurado demasiado bajo para la resolución de salida | Aumenta `XDimension.Pixels` o guarda en un formato vectorial como SVG (`BarCodeImageFormat.Svg`) |
| El texto no cabe en el diseño elegido | Demasiados caracteres para las filas/columnas seleccionadas | Reduce el número de filas/columnas o divide los datos en varios códigos de barras |
| No se crea el archivo de imagen | La carpeta de salida no existe o faltan permisos de escritura | Asegúrate de que el directorio exista (`Directory.CreateDirectory`) y que la aplicación se ejecute con los derechos adecuados |

## Verificando el código de barras

Después de generar la imagen, puedes verificarla usando cualquier aplicación escáner de PDF417 (los teléfonos móviles tienen escáneres gratuitos) o el lector integrado de Aspose.BarCode:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// Load the image we just saved
BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
if (reader.Read())
{
    Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
}
else
{
    Console.WriteLine("Failed to decode the barcode.");
}
```

Si la salida coincide con el texto original, el proceso de **generar código de barras PDF417** se completó con éxito.

## Ejemplo completo y ejecutable

A continuación se muestra el programa completo que puedes copiar y pegar en `Program.cs`. Incluye todas las directivas `using`, manejo de errores y comentarios.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Prepare output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);
        string outputPath = Path.Combine(outputDir, "LayoutPdf417.png");

        // 1️⃣ Create the generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");

        // 2️⃣ Change barcode size (module size)
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module

        // 3️⃣ Set layout – columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4;
        generator.Parameters.Barcode.Pdf417.Rows    = 9;

        // 4️⃣ Save as PNG
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"PDF417 barcode saved to {outputPath}");

        // 5️⃣ Verify the barcode by reading it back
        BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
        if (reader.Read())
        {
            Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
        }
        else
        {
            Console.WriteLine("Failed to decode the barcode.");
        }
    }
}
```

Ejecutar este programa imprime:

```
PDF417 barcode saved to C:\...\output\LayoutPdf417.png
Decoded text: Layout test
```

Ahora tienes una **solución completa y autónoma** para generar códigos de barras PDF417 y controlar su tamaño.

## Conclusión

En este tutorial aprendiste cómo **generar un código de barras PDF417** en C# usando Aspose.BarCode, cómo **cambiar el tamaño del código de barras** ajustando la X‑dimensión, y cómo configurar columnas y filas para controlar el diseño. También viste cómo verificar el resultado programáticamente y cómo adaptar el código para datos dinámicos.

A continuación, podrías explorar:

* **Cómo generar PDF417** con ajuste del nivel de corrección de errores (`generator.Parameters.Barcode.Pdf417.ErrorLevel`)
* Exportar a **formatos vectoriales** (SVG, EPS) para escalado infinito
* Incrustar el código de barras en un documento PDF con **Aspose.PDF**

¡Experimenta con diferentes tamaños de módulo y opciones de diseño para adaptarlos a tus requisitos específicos de UI o impresión. ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo generar código de barras PDF417 con Aspose – Guía completa](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [ajustar tamaño del código de barras – guía C# para generar códigos de barras PDF417](/barcode/english/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Cómo guardar código de barras en C# – Generar códigos de barras PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}