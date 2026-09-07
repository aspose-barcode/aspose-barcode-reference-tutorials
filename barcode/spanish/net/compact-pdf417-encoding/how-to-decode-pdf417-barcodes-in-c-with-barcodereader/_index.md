---
category: general
date: 2026-09-07
description: Aprende a decodificar códigos de barras PDF417 en C# usando BarCodeReader.
  Esta guía paso a paso también explica cómo leer datos PDF417 de manera eficiente.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- how to read pdf417
- PDF417 barcode decoding C#
- MacroPdf417 extraction C#
- barcode reader BarCodeReader
- GroupDocs.Barcode tutorial
language: es
lastmod: 2026-09-07
og_description: Cómo decodificar códigos de barras PDF417 en C# usando BarCodeReader.
  Sigue este tutorial para aprender a leer datos PDF417 y extraer los campos MacroPdf417.
og_image_alt: Screenshot of C# code reading PDF417 barcode fields in the console
og_title: Cómo decodificar códigos de barras PDF417 en C# – guía completa
schemas:
- author: GroupDocs
  dateModified: '2026-09-07'
  description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  headline: How to decode PDF417 barcodes in C# with BarCodeReader
  type: TechArticle
- description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  name: How to decode PDF417 barcodes in C# with BarCodeReader
  steps:
  - name: Prepare the project and import namespaces
    text: '```csharp using System; using GroupDocs.Barcode; using GroupDocs.Barcode.Common;
      ```'
  - name: Define the image path
    text: '```csharp // Replace with the absolute or relative path to your barcode
      image string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png"; ```'
  - name: Initialize the barcode reader for MacroPdf417 decoding
    text: '```csharp using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
      { // Step 4 runs inside this block } ```'
  - name: Read every barcode found in the image
    text: '```csharp foreach (BarCodeResult result in reader.ReadBarCodes()) { //
      Step 5 extracts the MacroPdf417 fields } ```'
  - name: Retrieve and display Macro PDF417 specific data
    text: '```csharp Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
      Console.WriteLine'
  - name: Full runnable example
    text: 'Combine the snippets above into a single `Program.cs` file:'
  type: HowTo
tags:
- PDF417
- C#
- barcode decoding
title: Cómo decodificar códigos de barras PDF417 en C# con BarCodeReader
url: /es/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-with-barcodereader/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo decodificar códigos de barras PDF417 en C# con BarCodeReader

Si necesitas **cómo decodificar códigos de barras PDF417** en una aplicación .NET, esta guía te lleva paso a paso por todo el proceso. También descubrirás **cómo leer datos PDF417** como archivos MacroPdf417 e identificadores de segmento, todo con unas pocas líneas de C#.

Decodificar PDF417 es frecuente al trabajar con boletos de transporte, licencias de conducir o etiquetas de envío. Al final de este tutorial tendrás un programa de consola ejecutable que imprime cada campo MacroPdf417 expuesto por el SDK GroupDocs.Barcode.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* SDK de .NET 6.0 o posterior (el código compila con .NET Core y .NET Framework)
* Visual Studio 2022 o cualquier IDE que soporte C#
* El paquete NuGet **GroupDocs.Barcode** (`GroupDocs.Barcode` ≥ 23.3)
* Un archivo de imagen que contenga un código de barras Macro PDF417 (p. ej., `ExtPDF417Meta.png`)

> **Consejo profesional:** Instala el paquete vía CLI:  
> `dotnet add package GroupDocs.Barcode --version 23.3`

## Cómo decodificar códigos de barras PDF417 en C#

Las siguientes secciones dividen la solución en pasos lógicos. Cada paso incluye el código exacto que necesitas y una breve explicación de por qué es importante.

### Paso 1: Preparar el proyecto e importar espacios de nombres

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;
```

*¿Por qué?*  
`GroupDocs.Barcode` proporciona la clase `BarCodeReader`, mientras que `GroupDocs.Barcode.Common` contiene la enumeración `DecodeType` necesaria para la decodificación de PDF417.

### Paso 2: Definir la ruta de la imagen

```csharp
// Replace with the absolute or relative path to your barcode image
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
```

*¿Por qué?*  
El lector funciona con cualquier formato de imagen compatible con .NET (`.png`, `.jpg`, `.bmp`). Proporcionar la ruta correcta garantiza que el SDK pueda localizar el archivo.

### Paso 3: Inicializar el lector de códigos de barras para decodificar MacroPdf417

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Step 4 runs inside this block
}
```

*¿Por qué?*  
`DecodeType.MacroPdf417` indica al SDK que busque el formato extendido Macro PDF417, que lleva metadatos adicionales como IDs de archivo y de segmento. Usar la instrucción `using` asegura que los recursos no administrados se liberen rápidamente.

### Paso 4: Leer todos los códigos de barras encontrados en la imagen

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Step 5 extracts the MacroPdf417 fields
}
```

*¿Por qué?*  
Una imagen puede contener varios códigos de barras. El método `ReadBarCodes()` devuelve una colección, lo que permite procesar cada uno individualmente.

### Paso 5: Obtener y mostrar los datos específicos de Macro PDF417

```csharp
Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
```

*¿Por qué?*  
El objeto `Extended.Pdf417` expone todos los campos Macro PDF417 definidos por la especificación. Imprimirlos te permite verificar que la operación de decodificación fue exitosa y te brinda los datos necesarios para el procesamiento posterior.

### Ejemplo completo ejecutable

Combina los fragmentos anteriores en un único archivo `Program.cs`:

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // 1️⃣ Path to the image that contains the Macro PDF417 barcode
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 2️⃣ Create a reader configured for MacroPdf417 decoding
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // 3️⃣ Iterate over all detected barcodes
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // 4️⃣ Output Macro PDF417 metadata
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
                Console.WriteLine(); // Blank line for readability
            }
        }
    }
}
```

**Salida esperada en la consola** (los valores variarán según el contenido del código de barras):

```
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentCount: 3
Pdf417MacroFileName: shipment_data
Pdf417MacroTimestamp: 2024-07-15T10:23:45Z
```

Si la imagen no contiene un código de barras Macro PDF417, la colección `ReadBarCodes()` estará vacía y no se imprimirá nada.

## Variaciones comunes y casos límite

| Situación | Cómo adaptar el código |
|-----------|------------------------|
| **PDF417 estándar (no macro)** | Cambia `DecodeType.MacroPdf417` a `DecodeType.Pdf417`. El objeto `Extended.Pdf417` será `null`, así que protege contra referencias nulas. |
| **Múltiples imágenes** | Envuelve la inicialización del lector en un bucle `foreach (var path in imagePaths)`. |
| **Imágenes grandes** | Establece `reader.Options.ImageProcessingOptions.MaxImageDimension = 2000;` para limitar el uso de memoria. |
| **Lote crítico de rendimiento** | Reutiliza una única instancia de `BarCodeReader` con `reader.SetImage(path)` en lugar de crear un nuevo objeto para cada archivo. |

## Lista de verificación de solución de problemas

* **Sin salida:** Verifica que `imagePath` apunte a un archivo válido y que la imagen realmente contenga un código de barras PDF417. |
* **`Extended.Pdf417` nulo:** Probablemente usaste `DecodeType.Pdf417` en lugar de `MacroPdf417`. |
* **Excepción `FileNotFoundException`:** Asegúrate de que el directorio de trabajo coincida con la ruta o usa una ruta absoluta. |
* **Puntuación de confianza baja:** Mejora la calidad de la imagen o ajusta la configuración `reader.Options.Quality`. |

## Conclusión

Ahora sabes **cómo decodificar códigos de barras PDF417** en C# y **cómo leer metadatos PDF417** como IDs de archivo Macro, IDs de segmento y marcas de tiempo. El ejemplo completo muestra cómo inicializar `BarCodeReader`, seleccionar el tipo de decodificación correcto, iterar sobre los resultados y extraer cada campo MacroPdf417 disponible.

Desde aquí puedes:

* Integrar los datos extraídos en un sistema de logística o validación de boletos.
* Extender la aplicación de consola para escribir los resultados en una base de datos o archivo JSON.
* Explorar otros formatos de códigos de barras soportados por GroupDocs.Barcode (QR, DataMatrix, Code128, etc.) cambiando la enumeración `DecodeType`.

¡Feliz codificación, y siéntete libre de experimentar con diferentes imágenes y configuraciones de códigos de barras para dominar la decodificación de PDF417 en tus proyectos .NET!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [How to Read PDF417 in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [How to Read PDF417 in C# – Complete Barcode Reader Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [How to Generate PDF417 Barcode – Complete Programming Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}