---
category: general
date: 2026-08-09
description: Cómo leer PDF417 en C# usando BarCodeReader. Aprende a leer archivos
  PNG de códigos de barras, manejar múltiples códigos de barras y extraer metadatos
  extendidos.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- c# barcode reader
- read multiple barcodes
- read barcode png
- read barcode extended
language: es
lastmod: 2026-08-09
og_description: Cómo leer PDF417 en C# con Aspose.BarCode. Este tutorial le muestra
  cómo leer archivos PNG de códigos de barras, procesar varios códigos de barras en
  una sola imagen y obtener metadatos extendidos de PDF417.
og_image_alt: Screenshot of C# BarCodeReader console output displaying PDF417 metadata
og_title: Cómo leer PDF417 en C# – tutorial de lector de códigos de barras
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  headline: How to read PDF417 in C# – complete barcode reader guide
  type: TechArticle
- description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  name: How to read PDF417 in C# – complete barcode reader guide
  steps:
  - name: Verify the file exists before creating the reader.
    text: Verify the file exists before creating the reader.
  - name: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
    text: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
  - name: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
    text: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Cómo leer PDF417 en C# – guía completa del lector de códigos de barras
url: /es/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo leer PDF417 en C# – guía completa del lector de códigos de barras

Si necesitas **cómo leer PDF417** en una aplicación .NET, esta guía te ofrece una solución lista para ejecutar. Verás cómo leer un PNG de código de barras, procesar varios códigos en la misma imagen y extraer los campos extendidos de PDF417 que muchos escáneres ocultan.

Leer códigos de barras PDF417 es común en logística, emisión de entradas y gestión documental. Al final de este tutorial podrás decodificar una imagen Macro PDF417, mostrar cada resultado y usar la información adicional (ID de archivo, recuento de segmentos, marcas de tiempo, etc.) en tu propia lógica de negocio.

## Requisitos previos

- .NET 6.0 o posterior (el código también funciona con .NET Framework 4.7+)
- Visual Studio 2022 o cualquier IDE de C#
- **Aspose.BarCode for .NET** (prueba gratuita o paquete NuGet con licencia)
- Una imagen PNG que contenga un código de barras Macro PDF417 (el archivo de ejemplo se llama `ExtPDF417Meta.png`)

> **Consejo profesional:** Instala la biblioteca con la consola NuGet:  
> `dotnet add package Aspose.BarCode`

## Cómo leer PDF417 con BarCodeReader en C#

El núcleo de la solución es la clase `BarCodeReader`. Acepta una ruta de imagen y un enumerado `DecodeType` que indica al motor qué simbología buscar.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.ReadEngine;

class Pdf417Demo
{
    static void Main()
    {
        // Step 1: Create a BarCodeReader for a Macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Display Macro PDF417 extended metadata
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

### Por qué funciona

- **`DecodeType.MacroPdf417`** indica al lector que busque la variante Macro PDF417, que almacena los campos extra que ves en el paso 4.
- El bloque `using` elimina automáticamente el lector, liberando los manejadores de archivo.
- `ReadBarCodes()` devuelve **todos** los códigos de barras que coinciden con el tipo solicitado, cumpliendo el requisito de *leer varios códigos de barras* incluso si la imagen contiene solo uno.

Ejecutar el programa muestra una salida similar a:

```
CodeType: MacroPdf417
CodeText: 1234567890
Pdf417MacroFileID: 1
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: invoice_2023.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 254321
Pdf417MacroTimeStamp: 2023-03-15T10:45:00Z
Pdf417MacroAddressee: ACME Corp.
Pdf417MacroSender: Warehouse 7
MacroPdf417Terminator: True
----------------------------------------
```

## Uso del lector de códigos de barras en C# para leer múltiples códigos

Si una imagen contiene varios símbolos Macro PDF417 (por ejemplo, una página escaneada con un lote de entradas), el mismo bucle `foreach` procesa cada uno. No se requiere código adicional; el lector agrega los resultados internamente.

```csharp
// Example: processing a batch image
using (BarCodeReader batchReader = new BarCodeReader(
    "batch.png", DecodeType.MacroPdf417))
{
    int index = 0;
    foreach (BarCodeResult item in batchReader.ReadBarCodes())
    {
        Console.WriteLine($"--- Barcode #{++index} ---");
        Console.WriteLine($"Text: {item.CodeText}");
        // extended fields are accessed the same way
    }
}
```

### Trampas comunes

- **Formato de imagen:** El lector admite PNG, JPEG, BMP y TIFF. Si intentas un formato que no puede decodificar, obtendrás una colección vacía. Por eso el tutorial destaca *leer código de barras PNG*.
- **Resolución:** Las imágenes de baja resolución (< 300 dpi) pueden provocar segmentos perdidos. Aumenta la escala o solicita un escaneo de mayor calidad cuando sea posible.
- **Bandera Macro:** Olvidar `DecodeType.MacroPdf417` limita el motor a PDF417 simple y descarta los datos extendidos. Siempre especifica el tipo macro cuando necesites *leer campos extendidos del código de barras*.

## Lectura de archivos PNG de códigos de barras – mejores prácticas

Trabajar con archivos PNG es sencillo porque el formato conserva datos de píxeles sin pérdida. Aquí tienes una lista de verificación rápida:

1. Verifica que el archivo exista antes de crear el lector.  
   ```csharp
   if (!File.Exists(path))
       throw new FileNotFoundException($"File not found: {path}");
   ```
2. Usa `Image.FromFile` solo cuando necesites pre‑procesar (rotar, recortar). El `BarCodeReader` puede abrir el archivo directamente, lo que evita asignaciones de memoria extra.
3. Si el PNG contiene transparencia, el lector sigue funcionando porque el código de barras se renderiza sobre píxeles opacos.

## Acceso a los metadatos extendidos de PDF417

El objeto `Extended.Pdf417` expone cada campo opcional definido por la especificación PDF417. Puedes mapear estos campos a un modelo de dominio, almacenarlos en una base de datos o utilizarlos para validación.

```csharp
public class Pdf417Metadata
{
    public int FileID { get; set; }
    public int SegmentID { get; set; }
    public int SegmentsCount { get; set; }
    public string FileName { get; set; }
    public string Checksum { get; set; }
    public long FileSize { get; set; }
    public DateTime TimeStamp { get; set; }
    public string Addressee { get; set; }
    public string Sender { get; set; }
    public bool Terminator { get; set; }
}
```

Poblar el modelo:



## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo leer códigos de barras DataMatrix con Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Cómo crear códigos de barras – PDF417 compacto con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Leer código de barras DataMatrix C# – Generar modo DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}