---
category: general
date: 2026-10-12
description: Aprende a crear códigos de barras micro PDF417 y a convertir el código
  de barras a PNG usando C#. Guía paso a paso con código completo y consejos.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro PDF417 barcode
- convert barcode to PNG
- micro PDF417 C# example
- GS1 micro PDF417 generation
- barcode image settings
language: es
lastmod: 2026-10-12
og_description: Crea un código de barras micro PDF417 y conviértelo a PNG con C#.
  Sigue esta guía completa para generar tanto la versión estándar como la versión
  GS1.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Crear código de barras micro PDF417 y convertirlo a PNG – tutorial de C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn to create micro PDF417 barcode and convert barcode to PNG using
    C#. Step‑by‑step guide with full code and tips.
  headline: How to create micro PDF417 barcode and convert it to PNG in C#
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Cómo crear un código de barras micro PDF417 y convertirlo a PNG en C#
url: /es/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-convert-it-to-png-in/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un código de barras micro PDF417 y convertirlo a PNG en C#

Si necesitas **crear un código de barras micro PDF417** en una aplicación .NET, este tutorial te muestra exactamente cómo hacerlo. Verás un ejemplo completo y ejecutable que genera tanto un código de barras Micro PDF417 estándar como una versión compatible con GS1, y luego **convertir el código de barras a PNG** para uso posterior, como impresión o visualización web.

Generar un código de barras es más que llamar a un solo método: elegir el tamaño de módulo correcto, la cantidad de columnas y el formato de codificación determina la fiabilidad del escaneo. Al final de esta guía comprenderás por qué cada configuración es importante y cómo ajustarlas para tus propios proyectos.

## Requisitos previos

| Requirement | Reason |
|-------------|--------|
| .NET 6.0 SDK or later | Proporciona el runtime para la aplicación de consola C# |
| Visual Studio 2022 (or any C# IDE) | Facilita la edición y depuración |
| **Aspose.BarCode for .NET** NuGet package | Suministra las clases `BarcodeGenerator`, `EncodeTypes` y `BarCodeImageFormat` |
| Write permission to the output folder | Requerido para las llamadas `Save` que crean archivos PNG |

Puedes añadir el paquete Aspose.BarCode mediante la CLI:

```bash
dotnet add package Aspose.BarCode
```

## Paso 1: Configurar un proyecto de consola mínimo

Crea un nuevo proyecto de consola y referencia la biblioteca de códigos de barras. El siguiente `Program.cs` contiene todo el código que necesitas; no se requieren archivos externos.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace MicroPdf417Demo
{
    internal class Program
    {
        static void Main()
        {
            // Define the folder where PNG files will be saved
            string outputFolder = Environment.CurrentDirectory;

            // ------------------------------------------------------------
            // 1️⃣ Create a Micro PDF417 barcode generator with plain data
            // ------------------------------------------------------------
            BarcodeGenerator microGen = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,          // Micro PDF417 symbology
                "Micro data");                    // Simple alphanumeric payload

            // ------------------------------------------------------------
            // 2️⃣ Adjust the X dimension (module size) and set column count
            // ------------------------------------------------------------
            // XDimension controls the physical size of each barcode module.
            // A value of 2 pixels gives a compact yet readable barcode.
            microGen.Parameters.Barcode.XDimension.Pixels = 2;

            // For Micro PDF417 you can limit the number of columns.
            // Four columns keep the barcode small enough for labels.
            microGen.Parameters.Barcode.Pdf417.Columns = 4;

            // ------------------------------------------------------------
            // 3️⃣ Convert barcode to PNG and save the image
            // ------------------------------------------------------------
            string microPath = System.IO.Path.Combine(outputFolder, "MicroPdf417.png");
            microGen.Save(microPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Standard Micro PDF417 saved to: {microPath}");

            // ------------------------------------------------------------
            // 4️⃣ Create a GS1 Micro PDF417 barcode with AI‑encoded data
            // ------------------------------------------------------------
            // GS1 syntax requires Application Identifiers (AIs) wrapped in parentheses.
            // Example: (01) – GTIN, (21) – serial number.
            BarcodeGenerator gs1MicroGen = new BarcodeGenerator(
                EncodeTypes.Gs1MicroPdf417,
                "(01)12345678901231(21)ABC123");

            // ------------------------------------------------------------
            // 5️⃣ Set the X dimension for the GS1 barcode (same as step 2)
            // ------------------------------------------------------------
            gs1MicroGen.Parameters.Barcode.XDimension.Pixels = 2;

            // ------------------------------------------------------------
            // 6️⃣ Convert barcode to PNG and save the GS1 image
            // ------------------------------------------------------------
            string gs1Path = System.IO.Path.Combine(outputFolder, "GS1MicroPdf417.png");
            gs1MicroGen.Save(gs1Path, BarCodeImageFormat.Png);
            Console.WriteLine($"GS1 Micro PDF417 saved to: {gs1Path}");

            // End of demo
            Console.WriteLine("Barcode generation complete.");
        }
    }
}
```

### Por qué cada línea es importante

* **`EncodeTypes.MicroPdf417` vs `EncodeTypes.Gs1MicroPdf417`** – La primera crea un código de barras Micro PDF417 simple, mientras que la segunda sigue los estándares GS1, incrustando Identificadores de Aplicación (AIs). Elige según si tu sistema posterior espera datos GS1.
* **`XDimension.Pixels = 2`** – Controla el ancho del módulo. Valores menores crean una imagen más densa pero pueden volverse ilegibles en escáneres de baja resolución. Dos píxeles es un valor seguro para la mayoría de impresoras de etiquetas.
* **`Pdf417.Columns = 4`** – Micro PDF417 permite limitar las columnas, reduciendo el ancho total. Cuatro columnas mantienen el código compacto sin sacrificar la capacidad de datos para cargas cortas.
* **`BarCodeImageFormat.Png`** – PNG conserva calidad sin pérdidas, esencial para la claridad del código de barras. Por eso **convertimos el código de barras a PNG** en lugar de JPEG.

## Paso 2: Ejecutar el programa y verificar la salida

1. Compila el proyecto: `dotnet build`.  
2. Ejecuta: `dotnet run`.

Deberías ver mensajes en la consola similares a:

```
Standard Micro PDF417 saved to: C:\Path\To\Project\MicroPdf417.png
GS1 Micro PDF417 saved to: C:\Path\To\Project\GS1MicroPdf417.png
Barcode generation complete.
```

Abre los archivos PNG generados con cualquier visor de imágenes. Ambas imágenes muestran un código de barras nítido y de alto contraste listo para escanear.

### Resultado visual esperado

| Barcode type | Appearance |
|--------------|------------|
| **Micro PDF417** | Pequeño patrón rectangular con 4 columnas, legible por la mayoría de escáneres 2‑D. |
| **GS1 Micro PDF417** | Mismo tamaño pero codifica AIs de GS1; un escáner que entienda GS1 devolverá el GTIN y el número de serie. |

Si un escáner no logra leer la imagen, prueba aumentando `XDimension.Pixels` a **3** o **4**, o reduce la cantidad de columnas para el Micro PDF417 estándar.

## Problemas comunes y cómo evitarlos

| Issue | Cause | Fix |
|-------|-------|-----|
| Blurry barcode after printing | Low DPI printer settings | Exporta PNG a 300 dpi o más, o permite que el controlador de la impresora maneje el escalado. |
| Scanner returns “invalid data” | Missing or malformed GS1 AI format | Asegúrate de que cada AI esté entre paréntesis y siga la especificación GS1 (p. ej., `(01)` para GTIN‑14). |
| Image file not created | Output folder lacks write permission | Ejecuta el programa con privilegios elevados o elige una carpeta como `Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments)`. |
| Barcode too large for label | Default column count too high | Reduce `Pdf417.Columns` (p. ej., a **3**) o aumenta `XDimension` para disminuir el tamaño total. |

## Extender el ejemplo

* **Different image formats** – Reemplaza `BarCodeImageFormat.Png` por `Jpeg` o `Bmp` si tu flujo de trabajo lo requiere. PNG sigue siendo la mejor opción para calidad sin pérdidas.  
* **Dynamic data** – Pasa la entrada del usuario o valores de base de datos al constructor `BarcodeGenerator` para crear códigos de barras sobre la marcha.  
* **Batch generation** – Envuelve la lógica de creación en un bucle que lea filas de un archivo CSV y guarde cada código de barras con un nombre de archivo único.

## Conclusión

Ahora sabes cómo **crear un código de barras micro PDF417** en C# y **convertir el código de barras a PNG** para escenarios tanto estándar como compatibles con GS1. El código completo y ejecutable muestra las configuraciones esenciales—dimensión X, número de columnas y tipo de codificación—para que puedas adaptar la solución a cualquier proyecto .NET que necesite códigos de barras 2‑D compactos y de alta calidad.

*Próximos pasos*: explora otras simbologías soportadas por Aspose.BarCode (p. ej., QR, DataMatrix), experimenta con diferentes valores de `XDimension` para impresión de alta resolución, o integra los PNG generados en una API web que sirva códigos de barras bajo demanda.

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo crear un código de barras micro pdf417 en C# y guardarlo como PNG](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-and-save-it-as-png/)
- [Crear PNG de código de barras en C# – guía completa de GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [Generar código de barras Micro PDF417 en C# – Guía completa](/barcode/english/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}