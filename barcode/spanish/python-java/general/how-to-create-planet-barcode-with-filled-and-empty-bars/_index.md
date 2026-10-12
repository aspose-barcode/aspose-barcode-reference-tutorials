---
category: general
date: 2026-09-29
description: Crear código de barras planetario en C# con barras llenas y vacías –
  guía paso a paso usando Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode XDimension
- filled bars
- empty bars
- Aspose.Barcode C#
language: es
lastmod: 2026-09-29
og_description: Crea códigos de barras planet en C# rápidamente. Aprende a renderizar
  barras rellenas, cambiar a barras vacías y ajustar la dimensión X con Aspose.Barcode.
og_image_alt: 'Screenshot of two Planet barcodes: one with filled bars, one with empty
  bars'
og_title: Crear código de barras planetario con barras llenas y vacías – tutorial
  de C#
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  headline: How to create planet barcode with filled and empty bars
  type: TechArticle
- description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  name: How to create planet barcode with filled and empty bars
  steps:
  - name: Changing the bar width
    text: If your label printer expects a different bar width, modify the `XDimension.Pixels`
      value. For high‑resolution printers, a value of **2** or **3** pixels may be
      preferable; for low‑resolution printers, **5** or **6** pixels can improve scan
      reliability.
  - name: Using a different image format
    text: Aspose.Barcode supports PNG, JPEG, BMP, GIF, and TIFF. Swap `BarCodeImageFormat.Png`
      with another enum value to match your downstream workflow.
  - name: Generating multiple barcodes in a loop
    text: When you need a batch of Planet barcodes (e.g., for a mailing list), wrap
      the generator logic in a `foreach` loop and change the data string each iteration.
  - name: Handling invalid input
    text: The Planet symbology accepts only numeric strings of **5‑8** digits. Supplying
      an invalid value throws an `ArgumentException`. Guard against this with a simple
      validation method.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Cómo crear un código de barras planetario con barras llenas y vacías
url: /es/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear códigos de barras Planet con barras rellenas y vacías

Si necesitas **crear códigos de barras Planet** en C#, esta guía te muestra exactamente cómo generar versiones con barras rellenas y barras vacías. Verás cómo establecer el ancho de la barra (X‑dimension), alternar la propiedad `FilledBars` y guardar los resultados como archivos PNG, todo con la biblioteca Aspose.Barcode.

Generar códigos de barras postales es un requisito común para sistemas de envío, aplicaciones de listas de correo y paneles de logística. Al final de este tutorial tendrás dos archivos PNG listos para usar que podrás incrustar en informes, correos electrónicos o impresiones.

## Requisitos previos

| Requisito | Por qué es importante |
|-------------|----------------|
| .NET 6.0 o posterior | Proporciona el tiempo de ejecución para el ejemplo en C#. |
| Visual Studio 2022 (o cualquier IDE de C#) | Te permite compilar y ejecutar el código. |
| **Aspose.Barcode for .NET** paquete NuGet | Proporciona la clase `BarcodeGenerator` y `EncodeTypes.Planet`. Instálalo con `dotnet add package Aspose.Barcode`. |
| Permiso de escritura en una carpeta del disco | El método `Save` escribe archivos PNG en la ruta que especifiques. |

## Paso 1: Configurar el proyecto e importar espacios de nombres

Crea un nuevo proyecto de consola (o agrega el código a uno existente) y referencia el espacio de nombres Aspose.Barcode.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;
```

Estas directivas `using` te dan acceso a `BarcodeGenerator`, `EncodeTypes` y los enums de formato de imagen necesarios para el tutorial.

## Paso 2: Crear un código de barras Planet con barras predeterminadas (rellenas)

El primer código de barras usa la representación predeterminada de la biblioteca, que rellena las barras.

```csharp
// Initialise a generator for the Planet (postal) barcode with sample data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Optional: adjust the bar width (X dimension) to 4 pixels for clearer printing.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image with filled bars.
string filledPath = @"C:\Barcodes\PlanetFilledBars.png";
barcodeGenerator.Save(filledPath, BarCodeImageFormat.Png);

Console.WriteLine($"Filled Planet barcode saved to: {filledPath}");
```

**Por qué funciona:**  
`EncodeTypes.Planet` indica a Aspose.Barcode que use la simbología **Planet**, que es un código de barras postal utilizado por el United States Postal Service. La propiedad `XDimension` controla el ancho de cada barra; establecerla en 4 píxeles produce un código de barras que se imprime bien en impresoras de etiquetas estándar. Por defecto, `FilledBars` es `true`, por lo que las barras aparecen sólidas.

## Paso 3: Crear un código de barras Planet con barras vacías

Para generar los mismos datos con barras *vacías*, solo necesitas cambiar la bandera `FilledBars` mientras mantienes los demás ajustes idénticos.

```csharp
// Re‑use the same variable for clarity.
barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for visual consistency.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Render empty bars instead of filled ones.
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the image with empty bars.
string emptyPath = @"C:\Barcodes\PlanetEmptyBars.png";
barcodeGenerator.Save(emptyPath, BarCodeImageFormat.Png);

Console.WriteLine($"Empty Planet barcode saved to: {emptyPath}");
```

**Por qué es importante:**  
Algunos sistemas de correo requieren el estilo de **barras vacías** para mejorar la legibilidad cuando el código de barras se imprime sobre fondos oscuros o cuando se usa un esquema de colores contrastante. Al establecer `FilledBars = false`, el generador dibuja solo los contornos de las barras, dejando el interior transparente.

## Resultado esperado

Después de ejecutar el programa, la carpeta `C:\Barcodes` (o la ruta que hayas elegido) contiene dos archivos PNG:

| Archivo | Descripción visual |
|------|---------------------|
| `PlanetFilledBars.png` | Barras son rectángulos negros sólidos sobre un fondo blanco. |
| `PlanetEmptyBars.png`  | Barras son contornos negros; el interior de cada barra es transparente (muestra el fondo). |

Ambas imágenes codifican la misma cadena numérica `"123456"` y comparten un ancho de barra de 4 píxeles, asegurando que se vean consistentes excepto por el estilo de relleno.

## Variaciones comunes y casos límite

### Cambiar el ancho de la barra

Si tu impresora de etiquetas espera un ancho de barra diferente, modifica el valor `XDimension.Pixels`. Para impresoras de alta resolución, un valor de **2** o **3** píxeles puede ser preferible; para impresoras de baja resolución, **5** o **6** píxeles pueden mejorar la fiabilidad del escaneo.

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 5; // example for coarse printers
```

### Usar un formato de imagen diferente

Aspose.Barcode soporta PNG, JPEG, BMP, GIF y TIFF. Cambia `BarCodeImageFormat.Png` por otro valor de enum para que coincida con tu flujo de trabajo posterior.

```csharp
barcodeGenerator.Save("Planet.tiff", BarCodeImageFormat.Tiff);
```

### Generar múltiples códigos de barras en un bucle

Cuando necesites un lote de códigos de barras Planet (p.ej., para una lista de correo), envuelve la lógica del generador en un bucle `foreach` y cambia la cadena de datos en cada iteración.

```csharp
string[] postalCodes = { "123456", "654321", "112233" };
int index = 1;
foreach (var code in postalCodes)
{
    var gen = new BarcodeGenerator(EncodeTypes.Planet, code);
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    gen.Save($@"C:\Barcodes\Planet_{index}_filled.png", BarCodeImageFormat.Png);
    gen.Parameters.Barcode.FilledBars = false;
    gen.Save($@"C:\Barcodes\Planet_{index}_empty.png", BarCodeImageFormat.Png);
    index++;
}
```

### Manejo de entradas inválidas

La simbología Planet acepta solo cadenas numéricas de **5‑8** dígitos. Proporcionar un valor inválido lanza una `ArgumentException`. Protege contra esto con un método de validación simple.

```csharp
bool IsValidPlanet(string value) => System.Text.RegularExpressions.Regex.IsMatch(value, @"^\d{5,8}$");

string data = "ABC123";
if (!IsValidPlanet(data))
{
    Console.WriteLine("Invalid Planet data – must be 5 to 8 digits.");
    return;
}
```

## Consejo profesional: Verificar el código de barras con un emulador de escáner

Aspose.Barcode incluye una clase `BarcodeReader` que puedes usar para confirmar que la imagen generada decodifica de nuevo a los datos originales.

```csharp
using Aspose.Barcode.Reader;

// Verify filled barcode
using (BarCodeReader reader = new BarCodeReader(filledPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from filled image: {reader.GetCodeText()}");
}

// Verify empty barcode
using (BarCodeReader reader = new BarCodeReader(emptyPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from empty image: {reader.GetCodeText()}");
}
```

Si la salida muestra `"123456"` para ambos archivos, el código de barras se generó correctamente.

## Conclusión

Ahora sabes cómo **crear imágenes de códigos de barras Planet** en C# con estilos de barras rellenas y vacías, controlar la **XDimension del código de barras Planet**, y guardar los resultados en formato PNG usando la biblioteca **Aspose.Barcode**. Ajusta el ancho de la barra, cambia los formatos de imagen o itera sobre una colección de valores para adaptarte a cualquier flujo de trabajo de códigos postales.

A continuación, podrías explorar:

* **Agregar texto legible por humanos** debajo del código de barras (`barcodeGenerator.Parameters.Caption.Show = true`).
* **Incrustar códigos de barras en documentos PDF** con Aspose.PDF.
* **Generar otras simbologías postales** como **USPS POSTNET** o **Intelligent Mail**.

¡Siéntete libre de experimentar con los parámetros e integrar el código en tu sistema de envío o correo! ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Crear código de barras Planet en C# – Guía completa paso a paso](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Crear código de barras Planet en C# – guía de programación completa](/barcode/english/python-java/general/create-planet-barcode-in-c-complete-programming-guide/)
- [Generador de códigos de barras C# – crear código de barras Planet y ejemplo RM4SCC](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}