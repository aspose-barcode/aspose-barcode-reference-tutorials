---
category: general
date: 2026-11-27
description: Crear imagen de código de barras en C# y guardar la imagen en formato
  PNG con Aspose.BarCode – guía paso a paso.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- save image PNG format
- Aspose.BarCode C#
- Macro PDF417 barcode
- barcode generation .NET
language: es
lastmod: 2026-11-27
og_description: Crea una imagen de código de barras en C# y guarda la imagen en formato
  PNG usando Aspose.BarCode. Sigue este tutorial para generar un código de barras
  Macro PDF417 paso a paso.
og_image_alt: Screenshot of a created barcode image saved as PNG
og_title: Crear imagen de código de barras y guardar en formato PNG en C# – guía completa
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Create barcode image in C# and save image PNG format with Aspose.BarCode
    – step‑by‑step guide.
  headline: Create barcode image and save PNG format in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Crear imagen de código de barras y guardar en formato PNG en C#
url: /es/net/one-dimensional-barcode-types/create-barcode-image-and-save-png-format-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear imagen de código de barras y guardar en formato PNG en C#

Si necesitas **crear una imagen de código de barras** en una aplicación .NET, esta guía te muestra cómo generar un código de barras Macro PDF417 y **guardar la imagen en formato PNG** usando Aspose.BarCode. Obtendrás un ejemplo completo y ejecutable, así como una explicación de cada configuración para que puedas adaptar el código a tus propios requisitos.

Generar un código de barras es más que llamar a un solo método; debes configurar el tamaño del módulo, los parámetros macro y el formato de salida. Al final de este tutorial comprenderás por qué cada propiedad es importante, cómo manejar casos límite comunes y cómo verificar que el archivo PNG se haya escrito correctamente.

## Lo que necesitarás

- .NET 6.0 o posterior (el código también funciona con .NET Framework 4.6+)
- Aspose.BarCode para .NET (disponible vía NuGet: `Install-Package Aspose.BarCode`)
- Un IDE como Visual Studio 2022 o Visual Studio Code
- Permiso de escritura en una carpeta donde se guardará el archivo PNG

## Paso 1: Inicializar el generador de códigos de barras

El primer paso es crear una instancia de `BarcodeGenerator` especificando la simbología `EncodeTypes.MacroPdf417` y el texto que deseas codificar.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Initialize a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent steps go here
}
```

**Por qué es importante:**  
`EncodeTypes.MacroPdf417` indica a la biblioteca que use la variante macro de PDF417, que soporta segmentación de archivos y metadatos adicionales. El constructor también recibe el texto legible por humanos que se codificará en el código de barras.

## Paso 2: Definir el tamaño del módulo (dimensión X)

La dimensión X controla el ancho de un solo módulo del código de barras (el elemento negro/blanco más pequeño). Un valor de `2` píxeles funciona bien para PNGs mostrados en pantalla.

```csharp
    // Step 2: Define the module size (X‑dimension) in pixels
    generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Consejo práctico:**  
Si planeas imprimir el código de barras, aumenta el valor de píxeles (p. ej., `4` o `5`) para evitar una salida borrosa en impresoras de baja resolución.

## Paso 3: Configurar los parámetros macro PDF417

Macro PDF417 añade varios campos opcionales que ayudan a identificar el archivo origen, el orden de los segmentos y verificaciones de integridad. A continuación se muestra un conjunto completo de parámetros típicos; puedes omitir cualquiera que no necesites.

```csharp
    // Step 3: Set PDF417 macro parameters
    generator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;      // Current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01"; // Logical file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;     // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;  // Approximate file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**Por qué estos campos son útiles:**  

| Parámetro | Propósito |
|-----------|-----------|
| `Columns` | Controla el ancho del código de barras; menos columnas producen un código más alto. |
| `MacroPdf417FileID` | Identificador único que une todos los segmentos. |
| `MacroPdf417SegmentID` | Posición de este segmento dentro del archivo completo. |
| `MacroPdf417SegmentsCount` | Número total de segmentos; necesario para la reconstrucción. |
| `MacroPdf417FileName` | Nombre legible por humanos que pueden mostrar las aplicaciones de escaneo. |
| `MacroPdf417Checksum` | Ayuda a los receptores a verificar la integridad de los datos (CCITT‑16). |
| `MacroPdf417FileSize` | Pista opcional del tamaño del archivo original. |
| `MacroPdf417TimeStamp` | Marca de tiempo de la creación del archivo original. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Metadatos para enrutamiento o propiedad. |
| `MacroPdf417Terminator` | Indica si este es el segmento final (`Set`) o uno intermedio (`Unset`). |

**Caso límite:** Si generas un código de barras de un solo segmento, establece `MacroPdf417SegmentsCount` en `1` y `MacroPdf417Terminator` en `Unset`. La biblioteca omitirá automáticamente los campos relacionados con segmentos que no son aplicables.

## Paso 4: Guardar el código de barras generado como una imagen PNG

Finalmente, llama a `Save` con una ruta de archivo y el valor del enumerado `BarCodeImageFormat.Png`. El método escribe la imagen en disco en formato PNG sin pérdidas.

```csharp
    // Step 4: Save the generated barcode as a PNG image
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

**¿Por qué PNG?**  
PNG conserva los valores exactos de píxeles, lo cual es esencial para los escáneres de códigos de barras que dependen de un contraste nítido. La compresión JPEG puede introducir artefactos que rompen el patrón del código.

### Verificando la salida

Después de ejecutar el programa, deberías ver un archivo llamado `ExtPDF417Meta.png` en la carpeta de ejecución. Abrirlo con cualquier visor de imágenes mostrará un código de barras rectangular y denso. Puedes verificar la corrección escaneando la imagen con un lector de códigos de barras móvil que soporte PDF417 macro; la aplicación mostrará típicamente los metadatos incrustados (ID de archivo, número de segmento, etc.).

## Problemas comunes y cómo evitarlos

| Síntoma | Causa probable | Solución |
|---------|----------------|----------|
| El código de barras aparece borroso | Dimensión X demasiado baja para la DPI elegida | Aumenta `XDimension.Pixels` o renderiza a una DPI mayor (`generator.Parameters.ImageResolution`). |
| El escáner informa “error de checksum” | Valor incorrecto de `MacroPdf417Checksum` | Deja que Aspose calcule el checksum automáticamente omitiendo la propiedad, o asegura que el valor coincida con el algoritmo CCITT‑16. |
| El archivo PNG está vacío o no se crea | Ruta de salida inválida o falta de permiso de escritura | Usa `Path.Combine` con una carpeta conocida y escribible (p. ej., `Environment.GetFolderPath(Environment.SpecialFolder.Desktop)`). |
| Los campos macro se ignoran | `EncodeTypes` configurado como `Pdf417` regular en lugar de `MacroPdf417` | Verifica que se use `EncodeTypes.MacroPdf417` en el constructor. |

## Ejemplo completo y ejecutable

A continuación tienes el programa completo que puedes copiar en una aplicación de consola. Compila con .NET 6.0 y produce el archivo PNG descrito anteriormente.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize a Macro PDF417 barcode generator with the desired text
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
        {
            // Define the module size (X-dimension) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Set PDF417 macro parameters
            generator.Parameters.Barcode.Pdf417.Columns = 5;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 checksum
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to: {outputPath}");
        }
    }
}
```

**Salida esperada (consola):**

```
Barcode image saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

Abrir `ExtPDF417Meta.png` muestra un código de barras Macro PDF417 claro, listo para escanear.

## Próximos pasos

- **Cambiar el formato de imagen** – reemplaza `BarCodeImageFormat.Png` por `Jpeg` o `Bmp` si necesitas otro tipo de archivo. Recuerda que JPEG introduce artefactos de compresión, lo que puede afectar la fiabilidad del escaneo.
- **Ajustar la resolución** – usa

## ¿Qué deberías aprender a continuación?


Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [How to create barcode image with Aspose.Barcode in C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [How to create PDF417 barcode image in C# with Macro PDF417 options](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [How to read barcodes from image using C# with Aspose.BarCode – step‑by‑step guide](/barcode/english/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}