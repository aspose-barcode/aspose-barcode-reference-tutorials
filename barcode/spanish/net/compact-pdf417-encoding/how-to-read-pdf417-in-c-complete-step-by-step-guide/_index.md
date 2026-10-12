---
category: general
date: 2026-09-28
description: Lee código de barras PDF417 c# rápidamente con Aspose.BarCode. Decodifica
  varios códigos de barras de una imagen, extrae los campos Macro‑PDF417 y gestiona
  la rotación o el procesamiento por lotes.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read pdf417 barcode c#
- read multiple barcodes
- pdf417 c# decoding
- Aspose.BarCode PDF417
- barcode image c#
lastmod: 2026-09-28
og_description: Lee código de barras PDF417 c# rápidamente con Aspose.BarCode. Esta
  guía muestra cómo decodificar varios códigos de barras de una sola imagen, extraer
  todas las propiedades Macro‑PDF417 y gestionar imágenes rotadas o por lotes.
og_image_alt: Screenshot of C# console output displaying PDF417 barcode details
og_title: Lee código de barras PDF417 c# – ejemplo de código completo y guía
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Read PDF417 barcode c# and read multiple barcodes from an image. Learn
    to read barcode image C# with detailed code and tips.
  headline: Read PDF417 barcode c# – complete step‑by‑step guide
  type: TechArticle
- description: Read PDF417 barcode c# and read multiple barcodes from an image. Learn
    to read barcode image C# with detailed code and tips.
  name: Read PDF417 barcode c# – complete step‑by‑step guide
  steps:
  - name: Why This Code Works
    text: '* **`BarCodeReader`** is the core class that streams the image, detects
      barcodes, and returns a collection of `BarCodeResult` objects. * Passing **`DecodeType.MacroPdf417`**
      tells the library to treat Macro‑PDF417 specially; it still returns plain PDF417
      symbols, which satisfies the **read multiple '
  - name: What if the image has both Macro‑PDF417 and regular PDF417 symbols?
    text: The same `BarCodeReader` call will return both. You can differentiate them
      by checking `result.CodeType` (`MacroPdf417` vs `Pdf417`). The extended properties
      will be `null` for a plain PDF417, so the `if (macro != null)` guard prevents
      a `NullReferenceException`.
  - name: My barcode is rotated or skewed—will the reader still work?
    text: Aspose.BarCode includes built‑in rotation and distortion compensation. As
      long as the barcode is at least 30 % of the image width, the decoder will usually
      succeed. For extreme cases you can enable `reader.Options.AllowInvertedBarcodes
      = true;` before calling `ReadBarCodes()`.
  - name: How do I handle large batches of images?
    text: Wrap the reading logic in a `foreach (var file in Directory.GetFiles(folder,
      "*.png"))` loop. The `using` pattern ensures each image’s native resources are
      freed before the next iteration, keeping memory usage low.
  type: HowTo
tags:
- C#
- barcode
- PDF417
- Aspose
title: Cómo leer código de barras PDF417 c# – guía completa paso a paso
url: /es/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo leer código de barras PDF417 c# – guía completa paso a paso

¿Alguna vez te has preguntado **cómo leer PDF417** de una imagen usando C#? No eres el único. La mayoría de los desarrolladores se topan con un obstáculo cuando necesitan extraer los campos Macro‑PDF417 extendidos de un documento escaneado. ¿La buena noticia? Con solo unas pocas líneas de código puedes **leer código de barras PDF417 c#**, decodificar varios códigos de barras en la misma foto y obtener todas las propiedades ocultas que la especificación ofrece.

## Respuestas rápidas
- **¿Puede Aspose.BarCode decodificar Macro‑PDF417?** Sí – solo habilita `DecodeType.MacroPdf417` y la biblioteca devuelve todos los campos extendidos.  
- **¿Cuántos códigos de barras se pueden leer de una imagen?** Ilimitados; la API devuelve una colección de objetos `BarCodeResult`.  
- **¿Necesito una licencia para producción?** Se requiere una licencia comercial para uso en producción; una prueba gratuita funciona para evaluación.  
- **¿Se detectarán los códigos de barras rotados?** La compensación de rotación incorporada funciona para códigos que cubran al menos el 30 % del ancho de la imagen.  
- **¿Se admite el procesamiento por lotes?** Absolutamente – envuelve el lector en un bucle `foreach` y elimina cada instancia con `using`.

## ¿Qué es leer código de barras PDF417 c#?
`read pdf417 barcode c#` se refiere al proceso de usar una biblioteca .NET para decodificar símbolos PDF417 (incluido Macro‑PDF417) de archivos de imagen directamente en código C#. El SDK Aspose.BarCode ofrece una API de una sola llamada que maneja la carga de la imagen, la detección del código de barras y la extracción de todos los campos definidos por ISO.

## ¿Por qué usar Aspose.BarCode para decodificar PDF417?
Aspose.BarCode soporta **más de 30 simbologías de códigos de barras** y puede procesar imágenes de hasta **5000 × 5000 px** en menos de **0.1 s** en hardware de servidor típico. También ofrece rotación, distorsión y manejo de códigos de barras invertidos listos para usar, eliminando la necesidad de pre‑procesamiento de imágenes personalizado. Además, la biblioteca incluye soporte incorporado para leer los campos extendidos de Macro‑PDF417, convirtiéndola en una solución integral para escenarios de escaneo complejos.

## Requisitos previos

Antes de profundizar, asegúrate de tener:

* .NET 6.0 SDK o posterior (el código funciona también con .NET Core y .NET Framework).  
* Visual Studio 2022 (o cualquier editor que prefieras).  
* El paquete NuGet **Aspose.BarCode for .NET** – es la biblioteca que realmente analiza PDF417.  
* Una imagen de muestra que contenga un código de barras Macro‑PDF417 (por ejemplo `ExtPDF417Meta.png`).  

No se requiere configuración adicional; la biblioteca incluye todos los decodificadores que necesitas.

## ¿Cómo leer código de barras PDF417 c#?

Carga la imagen con `BarCodeReader`, especifica `DecodeType.MacroPdf417` y recorre la colección `BarCodeResult` devuelta – esa es la solución completa en menos de diez líneas de código. El lector extrae automáticamente tanto los símbolos PDF417 simples como los datos extendidos de Macro‑PDF417, por lo que obtienes identificadores de archivo, números de segmento, marcas de tiempo y sumas de verificación sin análisis adicional.

### Paso 1: instalar Aspose.BarCode

Abre la carpeta de tu proyecto en una terminal y ejecuta:

```bash
dotnet add package Aspose.BarCode
```

Ese comando obtiene la última versión estable (a julio 2026 es la 23.12). Si prefieres la Consola del Administrador de Paquetes dentro de Visual Studio, usa:

```powershell
Install-Package Aspose.BarCode
```

> **Consejo profesional:** bloquea la versión (`23.12.0`) en tu `.csproj` para evitar cambios incompatibles accidentales más adelante.

### Paso 2: crear la estructura de una aplicación de consola

Crea un nuevo proyecto de consola si aún no tienes uno:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Reemplaza el `Program.cs` autogenerado con el código que aparece a continuación. Explicaremos cada bloque en las siguientes secciones.

### Paso 3: escribir el código completo “cómo leer PDF417”

`BarCodeReader` es la clase central que procesa la imagen, detecta los códigos de barras y devuelve una colección de objetos `BarCodeResult`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Set the path to the image that contains one or more PDF417 codes
            // -----------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarCodeReader for MacroPdf417 decoding
            // -----------------------------------------------------------------
            // The DecodeType flag tells Aspose to look specifically for Macro‑PDF417,
            // but it will also pick up plain PDF417 symbols that happen to be in the
            // same image – perfect for the “read multiple barcodes” scenario.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // -----------------------------------------------------------------
                // 3️⃣  Iterate over every barcode found in the image
                // -----------------------------------------------------------------
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // -------------------------------------------------------------
                    // 4️⃣  Basic barcode information – works for any barcode type
                    // -------------------------------------------------------------
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // -------------------------------------------------------------
                    // 5️⃣  Macro‑PDF417 extended properties (the real reason you’re here)
                    // -------------------------------------------------------------
                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40)); // visual separator
                }
            }

            // -----------------------------------------------------------------
            // 6️⃣  Keep the console window open when running from VS
            // -----------------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

* `BarCodeReader` — la clase principal responsable de leer y decodificar códigos de barras desde imágenes.  
* `DecodeType.MacroPdf417` — una bandera que indica al SDK que trate Macro‑PDF417 de forma especial mientras sigue devolviendo símbolos PDF417 simples.  
* `Extended.Pdf417.MacroPdf417` — el objeto que contiene todos los campos opcionales definidos por ISO/IEC 15438, como `FileID`, `SegmentID` y `Checksum`.

El bloque `using` garantiza que los recursos nativos se liberen, evitando fugas de memoria en servicios de larga ejecución.

### Paso 4: ejecutar la aplicación y verificar la salida

Desde la terminal:

```bash
dotnet run
```

Deberías ver algo como:

```
Code Type : MacroPdf417
Code Text : 1234567890...
File ID          : 12
Segment ID       : 1
Segments Count   : 3
File Name        : invoice2024.pdf
Checksum         : 9A3F
File Size        : 245760
Time Stamp       : 2024-11-02T14:23:00Z
Addressee        : Acme Corp
Sender           : Logistics Dept
Terminator       : 1
----------------------------------------
Done. Press any key to exit...
```

Si la imagen contiene más de un código de barras, el bucle imprime una línea separadora (`----------------------------------------`) y continúa con el siguiente resultado—exactamente lo que **leer varios códigos de barras** implica en la práctica.

## Preguntas comunes y casos límite

### ¿Qué pasa si la imagen tiene símbolos Macro‑PDF417 y PDF417 regulares?

La misma llamada a `BarCodeReader` devolverá ambos. Puedes diferenciarlos comprobando `result.CodeType` (`MacroPdf417` vs `Pdf417`). Las propiedades extendidas serán `null` para un PDF417 simple, por lo que la condición `if (macro != null)` evita una `NullReferenceException`.

### Mi código de barras está rotado o sesgado—¿el lector seguirá funcionando?

Aspose.BarCode incluye compensación de rotación y distorsión incorporada. Mientras el código de barras ocupe al menos el 30 % del ancho de la imagen, el decodificador suele tener éxito. En casos extremos puedes habilitar `reader.Options.AllowInvertedBarcodes = true;` antes de llamar a `ReadBarCodes()`.

### ¿Cómo manejo lotes grandes de imágenes?

Envuelve la lógica de lectura en un bucle `foreach (var file in Directory.GetFiles(folder, "*.png"))`. El patrón `using` asegura que los recursos nativos de cada imagen se liberen antes de la siguiente iteración, manteniendo bajo el consumo de memoria.

## Listado completo del código (listo para copiar y pegar)

A continuación tienes todo el programa en un solo bloque para copiar y pegar rápidamente. No hay dependencias ocultas—solo el paquete NuGet Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

## Resumen – lo que cubrimos

* **Cómo leer código de barras PDF417 c#** usando Aspose.BarCode.  
* Los pasos exactos para **leer varios códigos de barras** de una sola imagen.  
* Cómo **leer imagen de código de barras c#** y extraer cada campo Macro‑PDF417.  
* Consejos para rotación, procesamiento por lotes y manejo de datos extendidos ausentes.

## Próximos pasos y temas relacionados

* **Codificar PDF417** – genera tus propios códigos Macro‑PDF417 con `BarCodeBuilder`.  
* **Leer otras simbologías 2‑D** – QR, DataMatrix, Aztec – usando la misma clase `BarCodeReader`.  
* **Integrar con ASP.NET Core** – expón un endpoint web que acepte una imagen subida y devuelva JSON con los campos decodificados.  

### Enlaces útiles adicionales
- [Cómo leer códigos DataMatrix con Aspose.BarCode para .NET](/barcode/english/net/datamatrix-barcode-reading/)  
- [Cómo crear código de barras – PDF417 compacto con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)  
- [Leer código de barras DataMatrix C# – Generar modo DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

Siéntete libre de experimentar: cambia la ruta de la imagen, coloca un PDF417 simple en la misma carpeta o ajusta las banderas `DecodeType` para ver cómo se comporta la biblioteca. Cuanto más juegues, más cómodo te sentirás con escenarios de **leer imagen de código de barras c#**.

¿Tienes una imagen complicada que se niega a decodificar? Deja un comentario abajo o abre un issue en el repositorio GitHub del proyecto de ejemplo. ¡Feliz codificación!

## Preguntas frecuentes

**P: ¿Puedo usar esto en una aplicación comercial?**  
R: Sí, puedes usar Aspose.BarCode en proyectos comerciales siempre que cuentes con una licencia válida; hay una prueba gratuita disponible para evaluación.

**P: ¿El lector soporta imágenes protegidas con contraseña?**  
R: El SDK funciona con cualquier formato de imagen estándar; la protección con contraseña no se aplica a imágenes raster, solo a PDFs, que son manejados por un componente separado Aspose.PDF.

**P: ¿Qué versiones de .NET son compatibles?**  
R: .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ y .NET 6+ son totalmente compatibles con la versión actual de Aspose.BarCode.

**P: ¿Cómo puedo mejorar el rendimiento para lotes de imágenes muy grandes?**  
R: Habilita `reader.Options.Quality = QualityMode.HighPerformance` y procesa las imágenes en paralelo usando `Parallel.ForEach` mientras mantienes cada `BarCodeReader` dentro de un bloque `using`.

**P: ¿Existe una forma de obtener solo los campos Macro‑PDF417 sin iterar todos los resultados?**  
R: Sí – después de llamar a `ReadBarCodes()`, filtra la colección con `result => result.CodeType == DecodeType.MacroPdf417` y luego accede a la propiedad `Extended.Pdf417.MacroPdf417`.

---

**Última actualización:** 2026-09-28  
**Probado con:** Aspose.BarCode 23.12 for .NET  
**Autor:** Aspose

## Tutoriales relacionados

- [Cómo generar imagen de código de barras Pdf417 en C con Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Crear código de barras Pdf417 con Aspose Barcode Guía paso a paso](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-barcode-step-by-step-guide/)
- [Leer múltiples códigos de barras C Guía completa con Pdf417](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}