---
category: general
date: 2026-09-13
description: Aprende cómo crear una imagen de código de barras PDF417 en C# usando
  BarcodeGenerator y las opciones Macro PDF417. Código paso a paso, consejos y ejemplo
  completo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode image
- macro PDF417 options
- BarcodeGenerator class
- C# barcode generation
- barcode image format
language: es
lastmod: 2026-09-13
og_description: Crea una imagen de código de barras PDF417 en C# con BarcodeGenerator.
  Sigue este tutorial detallado para configurar las opciones de Macro PDF417 y guardar
  un código de barras PNG.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Crear imagen de código de barras PDF417 en C# – guía completa
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  headline: How to create PDF417 barcode image in C# with Macro PDF417 options
  type: TechArticle
- description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  name: How to create PDF417 barcode image in C# with Macro PDF417 options
  steps:
  - name: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
    text: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
  - name: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
    text: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
  - name: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
    text: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
  - name: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
    text: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
  - name: Create a new .NET 6 (or later) console project.
    text: Create a new .NET 6 (or later) console project.
  - name: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
    text: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
  - name: Replace the generated `Program.cs` with the code above.
    text: Replace the generated `Program.cs` with the code above.
  - name: Adjust `outputPath` to a folder you have write access to.
    text: Adjust `outputPath` to a folder you have write access to.
  - name: Build and run – the console will confirm the image location.
    text: Build and run – the console will confirm the image location.
  type: HowTo
tags:
- PDF417
- C#
- Barcode
title: Cómo crear una imagen de código de barras PDF417 en C# con opciones Macro PDF417
url: /es/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear una imagen de código de barras PDF417 en C# con opciones Macro PDF417

Si necesita **crear una imagen de código de barras PDF417** en C#, esta guía le muestra exactamente cómo hacerlo usando la **clase BarcodeGenerator**. Ya sea que esté construyendo un sistema de seguimiento de documentos o codificando archivos grandes, las instrucciones paso a paso a continuación cubren todo, desde la configuración de las opciones Macro PDF417 hasta guardar el PNG final.

Generar un código de barras es sencillo una vez que comprende los parámetros clave. En este tutorial aprenderá a:

* Inicializar un `BarcodeGenerator` para **Macro PDF417**.  
* Ajustar el tamaño del módulo del código de barras (`XDimension`).  
* Configurar ajustes específicos del segmento como ID de archivo, ID de segmento y suma de verificación.  
* Guardar el resultado como un **formato de imagen de código de barras** (PNG) que puede mostrarse en cualquier UI.

El único requisito previo es un entorno de desarrollo .NET (Visual Studio 2022 o posterior) y el paquete NuGet Aspose.BarCode for .NET, que proporciona la API `BarcodeGenerator` utilizada en los ejemplos.

---

## Cómo crear una imagen de código de barras PDF417 en C# – visión general

Crear una imagen de código de barras PDF417 consta de cuatro pasos lógicos:

1. **Crear el generador** – instanciar `BarcodeGenerator` con `EncodeTypes.MacroPdf417` y los datos que desea codificar.  
2. **Definir el tamaño del módulo** – establecer `XDimension.Pixels` para controlar el ancho físico de cada elemento del código de barras.  
3. **Configurar opciones Macro PDF417** – especificar columnas, identificadores de archivo, números de segmento y suma de verificación opcional.  
4. **Guardar el código de barras** – escribir la imagen generada en disco usando un **formato de imagen de código de barras** compatible, como PNG.

Cada paso se explica en detalle a continuación, con código C# completo y ejecutable.

---

## Paso 1: Inicializar el BarcodeGenerator para Macro PDF417

La primera línea crea un objeto `BarcodeGenerator` que sabe que debe producir un código de barras **Macro PDF417**. El constructor recibe dos argumentos: el tipo de codificación y la cadena de datos sin procesar.

```csharp
using Aspose.BarCode.Generation;   // NuGet: Aspose.BarCode
using System.Drawing.Imaging;      // For ImageFormat if you prefer System.Drawing

// Step 1 – create a barcode generator for Macro PDF417
using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample data"))
{
    // Subsequent configuration goes here
}
```

**Por qué es importante:**  
`EncodeTypes.MacroPdf417` indica a la biblioteca que trate el código de barras como un contenedor multi‑segmento, lo cual es esencial cuando necesita dividir un archivo grande en varios símbolos. La instancia de `BarcodeGenerator` es desechable, por lo que el bloque `using` garantiza que todos los recursos no administrados se liberen después de guardar la imagen.

---

## Paso 2: Establecer el tamaño del módulo del código de barras (XDimension)

`XDimension` controla el ancho en píxeles de un solo módulo del código de barras (la barra negra o blanca más pequeña). Un valor de **2 píxeles** produce una imagen compacta pero legible.

```csharp
    // Step 2 – define the size of each barcode module (pixel width)
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Consejo práctico:**  
Si su impresora objetivo tiene una DPI baja, aumente el recuento de píxeles (p. ej., `3` o `4`) para evitar manchas. Por el contrario, para visualización en pantalla puede mantenerlo bajo para reducir el tamaño del archivo.

---

## Paso 3: Configurar opciones específicas de Macro PDF417

Macro PDF417 agrega metadatos que permiten a un escáner reconstruir el archivo original a partir de varios segmentos de código de barras. Las opciones más comunes son:

| Propiedad | Significado |
|----------|-------------|
| `Columns` | Número de columnas en cada símbolo (afecta el ancho). |
| `MacroPdf417FileID` | Identificador único para todo el archivo. |
| `MacroPdf417SegmentID` | Índice del segmento actual (comienza en 1). |
| `MacroPdf417SegmentsCount` | Cantidad total de segmentos que forman el archivo. |
| `MacroPdf417FileName` | Nombre original del archivo (opcional, para mostrar). |
| `MacroPdf417Checksum` | Suma de verificación opcional de 16 bits para validar la integridad. |

```csharp
    // Step 3 – configure Macro PDF417 specific options
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns in the symbol
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf"; // Original file name
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;    // Optional checksum
```

**Por qué estos ajustes son importantes:**  
- **Columns** afecta la legibilidad y las dimensiones generales de la imagen.  
- **FileID** debe ser el mismo en todos los segmentos para que el decodificador sepa que pertenecen juntos.  
- **SegmentID** y **SegmentsCount** permiten al escáner ordenar correctamente las piezas.  
- **FileName** y **Checksum** son opcionales pero mejoran la experiencia del usuario y la integridad de los datos.

**Caso límite:** Si genera más de 999 segmentos, el campo `SegmentID` se desborda; en ese caso divida los datos en varios archivos.

---

## Paso 4: Guardar el código de barras generado como imagen PNG

El paso final escribe el código de barras en disco. `BarCodeImageFormat.Png` produce una imagen sin pérdidas que funciona en plataformas web, de escritorio y móviles.

```csharp
    // Step 4 – save the generated barcode as a PNG image
    barcodeGenerator.Save("YOUR_DIRECTORY/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

**Formatos alternativos:**  
Puede reemplazar `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` o `Gif` si su sistema downstream requiere un formato específico. Tenga en cuenta que JPEG introduce artefactos de compresión que pueden reducir la fiabilidad del escaneo.

**Salida esperada:**  
El archivo `MacroPdf417.png` contendrá un código de barras PDF417 multi‑segmento de alto contraste. Al abrirlo, debería verse similar a la ilustración a continuación.

![Create PDF417 barcode image example](image.png){: .align-center alt="Ejemplo de creación de imagen de código de barras PDF417 generado por código C#"}

---

## Código fuente completo – listo para copiar y ejecutar

A continuación se muestra el programa completo y autocontenido. Incluye las directivas `using` necesarias, el método `Main` y comentarios que explican cada línea no obvia.

```csharp
using System;
using Aspose.BarCode.Generation;   // Install-Package Aspose.BarCode
// No other external dependencies are required.

namespace Pdf417BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Data to encode – can be any UTF‑8 string up to 1,800 characters.
            const string dataToEncode = "Sample data";

            // Output directory – change this to a valid path on your machine.
            const string outputPath = @"C:\Barcodes\MacroPdf417.png";

            // Create a BarcodeGenerator for Macro PDF417.
            using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, dataToEncode))
            {
                // 1️⃣ Define module size (pixel width of each bar).
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // 2️⃣ Configure Macro PDF417 options.
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;

                // 3️⃣ Save the barcode as a PNG image.
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
            }

            Console.WriteLine($"PDF417 barcode image created at: {outputPath}");
        }
    }
}
```

**Ejecutar el programa:**  

1. Crear un nuevo proyecto de consola .NET 6 (o posterior).  
2. Añadir el paquete NuGet Aspose.BarCode (`dotnet add package Aspose.BarCode`).  
3. Reemplazar el `Program.cs` generado con el código anterior.  
4. Ajustar `outputPath` a una carpeta donde tenga permisos de escritura.  
5. Compilar y ejecutar – la consola confirmará la ubicación de la imagen.

---

## Preguntas frecuentes y solución de problemas

| Pregunta | Respuesta |
|----------|-----------|
| *¿Qué pasa si el código de barras es demasiado ancho para mi etiqueta?* | Reduzca `Columns` o aumente `XDimension.Pixels` para equilibrar ancho y legibilidad. |
| *¿Necesito establecer una suma de verificación?* | La suma de verificación es opcional |

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarle a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en sus propios proyectos.

- [Crear código de barras PDF417 en C# – Guía completa paso a paso](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [Crear metadatos de código de barras PDF417 en C# – Guía completa paso a paso](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [Generar código de barras con texto – Guía completa de Macro PDF417](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}