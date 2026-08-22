---
category: general
date: 2026-08-22
description: Cómo leer códigos de barras PDF417 en C# con una guía paso a paso, cubriendo
  cómo leer varios códigos de barras de una imagen y extraer los detalles de MacroPdf417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcodes image c#
language: es
lastmod: 2026-08-22
og_description: Cómo leer códigos de barras PDF417 en C# rápidamente. Este tutorial
  te muestra cómo leer varios códigos de barras de una imagen y obtener la información
  extendida MacroPdf417.
og_image_alt: Developer console displaying MacroPdf417 barcode details extracted by
  C# code
og_title: Cómo leer códigos de barras PDF417 en C# – guía completa de programación
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to read PDF417 barcodes in C# with a step‑by‑step guide, covering
    how to read multiple barcodes from an image and extract MacroPdf417 details.
  headline: How to read PDF417 barcodes in C# – complete guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Cómo leer códigos de barras PDF417 en C# – guía completa
url: /es/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo leer códigos de barras PDF417 en C# – guía completa

Si necesitas **cómo leer PDF417** en una aplicación .NET, este tutorial te brinda una solución lista para ejecutar. Aprenderás a leer varios códigos de barras de una sola imagen, extraer el conjunto completo de datos MacroPdf417 y mostrarlos en la consola. El enfoque funciona con la biblioteca Aspose.BarCode for .NET y requiere solo unas pocas líneas de código.

Leer códigos de barras a partir de una imagen es una tarea común en sistemas de inventario, validación de tickets y gestión de documentos. Al final de esta guía podrás decodificar cualquier código de barras PDF417 o MacroPdf417, manejar varios códigos en una sola foto y comprender los campos extendidos que proporciona MacroPdf417.

## Prerrequisitos

- SDK .NET 6.0 o posterior (el código también compila con .NET Framework 4.7+)
- Visual Studio 2022 o cualquier editor de C# que prefieras
- Paquete NuGet Aspose.BarCode for .NET (`Install-Package Aspose.BarCode`)
- Una imagen de muestra que contenga un código de barras MacroPdf417 (p. ej., `MacroPdf417.png`)

No se requiere configuración adicional; la biblioteca maneja la carga y decodificación de la imagen internamente.

## Cómo leer códigos de barras PDF417 a partir de una imagen en C#

El núcleo de la solución es la clase `BarCodeReader`. Abre la imagen, detecta todos los códigos de barras del tipo especificado y devuelve una colección de objetos `BarCodeResult`. El siguiente código muestra un programa de consola completo.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            // Path to the image that contains one or more MacroPdf417 barcodes
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            // 1️⃣ Initialize the reader for MacroPdf417 barcodes.
            // DecodeType.MacroPdf417 tells the engine to look for the extended PDF417 format.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // 2️⃣ Iterate over every barcode found in the image.
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // 3️⃣ Print basic information.
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // 4️⃣ Access MacroPdf417 extended fields.
                    // The Extended property contains format‑specific data; for PDF417 it is .Pdf417.
                    var macro = result.Extended.Pdf417;

                    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Por qué cada línea es importante

| Paso | Propósito |
|------|-----------|
| **1️⃣ Initialize** | Crea un `BarCodeReader` vinculado al archivo de imagen y restringe la detección a la simbología MacroPdf417, lo que acelera el procesamiento. |
| **2️⃣ Iterate** | `ReadBarCodes()` devuelve **todos** los códigos de barras que coinciden con el tipo solicitado, permitiéndote **leer varios códigos de barras** sin bucles adicionales. |
| **3️⃣ Basic output** | Muestra el `CodeTypeName` genérico y el `CodeText` legible por humanos. Esto es útil para registro o validación rápida. |
| **4️⃣ Extended data** | MacroPdf417 lleva metadatos adicionales (ID de archivo, recuento de segmentos, marcas de tiempo, etc.). El objeto `Extended.Pdf417` expone cada campo directamente, para que puedas almacenar o verificar todo el paquete de datos. |

Ejecutar el programa con una imagen MacroPdf417 válida produce una salida en consola similar a la siguiente:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345678
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x9A3F
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2024-07-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

La salida confirma que la biblioteca leyó correctamente el código de barras, extrajo el texto y proporcionó cada campo de MacroPdf417.

## Lectura de varios códigos de barras a partir de una sola imagen

Muchos escenarios del mundo real colocan varios símbolos PDF417 en una etiqueta—piensa en un manifiesto de envío que contiene un código de transportista, un número de seguimiento y una declaración de aduanas. El mismo bloque de código anterior ya **lee varios códigos de barras** porque `ReadBarCodes()` devuelve un enumerable con todas las coincidencias. No se necesita configuración adicional; solo tienes que iterar sobre los resultados, como se muestra.

Si deseas limitar el lector a PDF417 estándar (no macro) mientras manejas varios códigos, reemplaza `DecodeType.MacroPdf417` por `DecodeType.Pdf417`. El resto de la lógica permanece sin cambios.

## Comprensión de los datos extendidos de MacroPdf417

MacroPdf417 es una extensión de la especificación PDF417 regular. Divide cargas útiles grandes en varios segmentos y añade un pequeño encabezado que describe todo el archivo. Los campos más relevantes son:

- **MacroPdf417FileID** – un identificador único compartido por todos los segmentos del mismo archivo.
- **MacroPdf417SegmentID** – el número de secuencia del segmento actual.
- **MacroPdf417SegmentsCount** – número total de segmentos esperados.
- **MacroPdf417FileName** – nombre de archivo opcional transmitido con el código de barras.
- **MacroPdf417Checksum** – valor de verificación de errores para el archivo completo.
- **MacroPdf417FileSize** – tamaño de la carga binaria original.
- **MacroPdf417TimeStamp** – marca de tiempo ISO‑8601 cuando se generó el código de barras.
- **MacroPdf417Addressee / Sender** – campos de texto opcionales para el enrutamiento.
- **MacroPdf417Terminator** – indica si este segmento es el final.

Cuando recibas todos los segmentos, puedes reconstruir el archivo original ordenándolos por `MacroPdf417SegmentID` y concatenando los valores de `CodeText`. Esta lógica es sencilla de implementar una vez que tienes los campos disponibles.

## Trucos comunes y consejos profesionales

- **Image quality matters** – los archivos PNG/JPEG de baja resolución o fuertemente comprimidos pueden provocar detecciones fallidas. Usa al menos 300 dpi para códigos de barras impresos.  
- **Mixed symbologies** – si la imagen contiene tanto MacroPdf417 como PDF417 regular, instancia dos lectores (uno para cada `DecodeType`) o usa `DecodeType.AllSupported` y filtra los resultados por `result.CodeTypeName`.  
- **Memory usage** – la instrucción `using` elimina rápidamente el `BarCodeReader`, evitando que grandes búferes de imagen permanezcan en memoria.  
- **Thread safety** – `BarCodeReader` no es seguro para subprocesos. Crea una instancia separada por subproceso si decodificas imágenes en paralelo.  
- **Error handling** – envuelve la llamada a `ReadBarCodes()` en un bloque try/catch para capturar `BarCodeException` en caso de imágenes corruptas.  

## Recapitulación del ejemplo completo funcionando

A continuación tienes el programa completo que puedes copiar en un nuevo proyecto de consola. Incluye todas las directivas `using`, una constante para la ruta de la imagen y el patrón de disposición.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    var macro = result.Extended.Pdf417;
                    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

Compila con `dotnet build` y ejecuta con `dotnet run`. La consola imprime los datos básicos de cada código de barras y la carga completa de MacroPdf417.

## Próximos pasos

- **Reconstruir archivos multipartes** – recopila todos los segmentos, ordénalos por `MacroPdf417SegmentID` y concatena `CodeText` to

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo generar código de barras PDF417 – Codificación Compacta PDF417](/barcode/english/net/compact-pdf417-encoding/)
- [Cómo leer códigos de barras PDF417 con caracteres turcos en Java](/barcode/english/java/multilingual-support/recognizing-pdf417-turkish-characters/)
- [Cómo usar Aspose para código de barras PDF417 (chino) en Java](/barcode/english/java/multilingual-support/recognizing-pdf417-chinese-characters/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}