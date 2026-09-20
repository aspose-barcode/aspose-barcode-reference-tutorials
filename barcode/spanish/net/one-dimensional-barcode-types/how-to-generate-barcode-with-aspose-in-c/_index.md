---
category: general
date: 2026-09-19
description: Cómo generar códigos de barras usando Aspose en C# – una guía paso a
  paso para crear códigos de barras con Aspose de forma rápida y fiable.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode with aspose
language: es
lastmod: 2026-09-19
og_description: Cómo generar códigos de barras con Aspose en C#. Sigue esta guía para
  crear códigos de barras con Aspose, configurar MacroPdf417 y guardarlos como PNG.
og_image_alt: Screenshot showing a MacroPdf417 barcode generated with Aspose in C#
og_title: Cómo generar códigos de barras con Aspose – guía completa de C#
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to generate barcode using Aspose in C# – a step‑by‑step guide to
    create barcode with Aspose quickly and reliably.
  headline: How to generate barcode with Aspose in C#
  type: TechArticle
- description: How to generate barcode using Aspose in C# – a step‑by‑step guide to
    create barcode with Aspose quickly and reliably.
  name: How to generate barcode with Aspose in C#
  steps:
  - name: What if I need a different image format?
    text: Aspose supports `BarCodeImageFormat.Jpeg`, `Bmp`, `Tiff`, `Svg`, and `Pdf`.
      Just replace `BarCodeImageFormat.Png` with the desired enum value.
  - name: How do I generate multiple segments automatically?
    text: You can place the code above inside a loop, incrementing `MacroPdf417SegmentID`
      on each iteration and updating the data string. Remember to keep `MacroPdf417SegmentsCount`
      constant across all segments.
  - name: What if the data exceeds the capacity of a single MacroPdf417 symbol?
    text: MacroPdf417 is designed for large payloads, but every barcode has a theoretical
      maximum (≈ 1.1 KB per segment). Split the source file into chunks that fit this
      limit, then encode each chunk as a separate segment.
  - name: Does the checksum need to be calculated manually?
    text: Aspose can generate the CCITT‑16 checksum automatically if you set `MacroPdf417Checksum`
      to `0`. In the example we supplied a hard‑coded value for illustration; in production
      code you’d typically let the library compute it.
  - name: How can I change the barcode’s foreground/background colors?
    text: 'Use the `BarColor` and `BackColor` properties:'
  type: HowTo
tags:
- barcode
- Aspose
- C#
- .NET
title: Cómo generar códigos de barras con Aspose en C#
url: /es/net/one-dimensional-barcode-types/how-to-generate-barcode-with-aspose-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo generar códigos de barras con Aspose en C#

Generar un código de barras en C# es sencillo cuando utilizas la biblioteca Aspose.BarCode. Este tutorial te muestra cómo **crear códigos de barras con Aspose** paso a paso, cubriendo el formato MacroPdf417, configuraciones comunes de apariencia y cómo guardar el resultado como una imagen PNG.

Aprenderás a:

* Instalar y referenciar Aspose.BarCode para .NET  
* Configurar propiedades específicas de MacroPdf417 como ID de archivo, ID de segmento y suma de verificación  
* Ajustar opciones visuales como la dimensión X y el número de columnas  
* Exportar el código de barras a un archivo de imagen  

No se requiere experiencia previa con Aspose, solo un conocimiento básico de C# y Visual Studio.

## Requisitos previos

Antes de comenzar, asegúrate de contar con:

| Requisito | Detalle |
|-----------|---------|
| Runtime de .NET | .NET 6.0 o posterior (el código también funciona con .NET Framework 4.7+) |
| IDE | Visual Studio 2022, Rider o cualquier editor que admita C# |
| Aspose.BarCode | Paquete NuGet `Aspose.BarCode` (versión de prueba gratuita o con licencia) |
| Conocimientos básicos de C# | Familiaridad con sentencias `using` e inicialización de objetos |

Puedes añadir Aspose.BarCode a tu proyecto mediante el Administrador de paquetes NuGet:

```bash
dotnet add package Aspose.BarCode
```

## Cómo generar códigos de barras en C# – flujo de trabajo general

El proceso consta de cuatro pasos lógicos:

1. **Crear una instancia de `BarcodeGenerator`** con el tipo de codificación deseado (MacroPdf417) y el texto que deseas codificar.  
2. **Establecer opciones comunes de apariencia** como la dimensión X y el número de columnas.  
3. **Configurar propiedades específicas de MacroPdf417** como ID de archivo, ID de segmento y marca de tiempo.  
4. **Guardar el código de barras** en el formato de archivo que prefieras (PNG en este ejemplo).

Cada paso se explica en detalle a continuación.

## Paso 1: Crear un generador de códigos de barras para MacroPdf417

La clase `BarcodeGenerator` es el punto de entrada para todas las tareas de creación de códigos de barras. Al instanciarla, pasas dos argumentos:

* `EncodeTypes.MacroPdf417` – indica a Aspose que use la simbología MacroPdf417.  
* La cadena de datos – el texto que se codificará dentro del código de barras.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1 – instantiate the generator with MacroPdf417 and sample data
            using (BarcodeGenerator generator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Sample"))
            {
                // Subsequent steps go here
            }
        }
    }
}
```

> **Por qué es importante:** MacroPdf417 es un código de barras bidimensional que puede transportar grandes cantidades de datos y admite funciones macro como la segmentación de archivos, lo que resulta útil para transmitir archivos grandes en partes.

## Paso 2: Establecer opciones comunes de apariencia del código de barras

Aunque MacroPdf417 tiene muchas configuraciones especializadas, aún deseas controlar la densidad visual y el diseño. Los parámetros más comunes son:

* **X‑dimension** – el ancho del módulo más pequeño (píxel). Valores menores producen una imagen más densa.  
* **Columns** – el número de columnas de datos por fila; números mayores reducen la altura del código de barras.

```csharp
// Step 2 – adjust appearance
generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2‑pixel modules
generator.Parameters.Barcode.Pdf417.Columns = 5;    // 5 columns per row
```

> **Consejo:** Mantén `XDimension` entre 2 y 4 píxeles para la mayoría de los escenarios de visualización en pantalla. Valores mayores mejoran la legibilidad en impresoras de baja resolución pero aumentan el tamaño total de la imagen.

## Paso 3: Configurar propiedades específicas de MacroPdf417

MacroPdf417 añade un conjunto de campos de metadatos que permiten dividir un archivo grande en varios segmentos de código de barras. Las siguientes propiedades son las más habituales:

| Propiedad | Propósito |
|-----------|-----------|
| `MacroPdf417FileID` | Identificador único para todo el archivo (máx. 8 dígitos). |
| `MacroPdf417SegmentID` | Índice del segmento actual (comienza en 0). |
| `MacroPdf417SegmentsCount` | Número total de segmentos en el archivo. |
| `MacroPdf417FileName` | Nombre legible del archivo original. |
| `MacroPdf417Checksum` | Suma de verificación CCITT‑16 opcional para detección de errores. |
| `MacroPdf417FileSize` | Tamaño del archivo original en bytes. |
| `MacroPdf417TimeStamp` | Marca de tiempo cuando se generó el archivo. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Cadenas opcionales para identificar al destinatario/remitente. |
| `MacroPdf417Terminator` | Determina si el código de barras es el último segmento (`Set`) o uno intermedio (`Unset`). |

```csharp
// Step 3 – set macro‑specific data
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // in bytes
generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

> **Por qué estos campos son útiles:**  
> *Cuando necesitas enviar un documento grande a través de un canal de bajo ancho de banda, puedes dividir el documento en varios códigos de barras MacroPdf417. El receptor reconstruye el archivo original leyendo los metadatos de cada segmento.*

## Paso 4: Guardar el código de barras generado como imagen

Aspose admite muchos formatos de salida: PNG, JPEG, BMP, TIFF, SVG y PDF. PNG es un formato sin pérdida ideal para la web o la visualización en UI.

```csharp
// Step 4 – export the barcode
string outputPath = @"C:\Barcodes\MacroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Al ejecutar el programa, encontrarás un archivo PNG que se asemeja a la ilustración a continuación.

![Código de barras MacroPdf417 generado con Aspose en C#](placeholder-image.png){.img-fluid alt="cómo generar códigos de barras con Aspose en C#"}

> **Salida esperada:** Un PNG de 300 × 150 píxeles que muestra un código de barras MacroPdf417 que codifica el texto “Sample” junto con los metadatos macro que proporcionaste.

## Ejemplo completo y ejecutable

Uniendo todo, aquí tienes el programa completo que puedes copiar, pegar y ejecutar:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for MacroPdf417
            using (BarcodeGenerator generator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Sample"))
            {
                // Appearance settings
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // MacroPdf417 specific data
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputPath = @"C:\Barcodes\MacroPdf417.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode saved to {outputPath}");
            }
        }
    }
}
```

Ejecuta el programa con `dotnet run` (o pulsa **F5** en Visual Studio). Tras la ejecución, verifica que el archivo PNG exista y se abra sin errores.

## Preguntas frecuentes y manejo de casos límite

### ¿Qué pasa si necesito un formato de imagen diferente?
Aspose admite `BarCodeImageFormat.Jpeg`, `Bmp`, `Tiff`, `Svg` y `Pdf`. Simplemente reemplaza `BarCodeImageFormat.Png` por el valor del enum que desees.

### ¿Cómo genero varios segmentos automáticamente?
Puedes colocar el código anterior dentro de un bucle, incrementando `MacroPdf417SegmentID` en cada iteración y actualizando la cadena de datos. Recuerda mantener `MacroPdf417SegmentsCount` constante en todos los segmentos.

### ¿Qué ocurre si los datos superan la capacidad de un solo símbolo MacroPdf417?
MacroPdf417 está diseñado para cargas útiles grandes, pero cada código de barras tiene un máximo teórico (≈ 1.1 KB por segmento). Divide el archivo fuente en fragmentos que se ajusten a este límite y codifica cada fragmento como un segmento separado.

### ¿Es necesario calcular la suma de verificación manualmente?
Aspose puede generar la suma de verificación CCITT‑16 automáticamente si estableces `MacroPdf417Checksum` a `0`. En el ejemplo suministramos un valor codificado para ilustrar; en código de producción normalmente dejarías que la biblioteca lo calcule.

### ¿Cómo puedo cambiar los colores de primer plano/fondo del código de barras?
Utiliza las propiedades `BarColor` y `BackColor`:

```csharp
generator.Parameters.Barcode.BarColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
```

## Conclusión

Ahora sabes **cómo generar códigos de barras** en C# usando Aspose.BarCode y, específicamente, **cómo crear códigos de barras con Aspose** para la simbología MacroPdf417. El tutorial cubrió la instalación, la configuración de apariencia y los campos específicos de macro.

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales abordan temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [How generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}