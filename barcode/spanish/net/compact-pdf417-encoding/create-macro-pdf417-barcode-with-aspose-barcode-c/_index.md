---
category: general
date: 2026-09-22
description: Crear código de barras macro PDF417 usando Aspose.BarCode en C#. Aprenda
  paso a paso cómo generar el código de barras con Aspose, configurar los metadatos
  y guardarlo como PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- generate barcode with Aspose
- Aspose.BarCode PDF417
- C# barcode generation
- barcode metadata configuration
language: es
lastmod: 2026-09-22
og_description: Crea un código de barras macro PDF417 usando Aspose.BarCode en C#.
  Esta guía te muestra cómo generar el código de barras con Aspose, establecer los
  metadatos macro y exportar la imagen.
og_image_alt: Screenshot of a created macro PDF417 barcode using Aspose.BarCode in
  C#
og_title: Crear código de barras macro PDF417 con Aspose.BarCode (C#) – guía paso
  a paso
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Create macro PDF417 barcode using Aspose.BarCode in C#. Learn step‑by‑step
    how to generate barcode with Aspose, configure metadata, and save as PNG.
  headline: Create macro PDF417 barcode with Aspose.BarCode (C#)
  type: TechArticle
tags:
- Aspose
- PDF417
- C#
- Barcode
title: Crear código de barras macro PDF417 con Aspose.BarCode (C#)
url: /es/net/compact-pdf417-encoding/create-macro-pdf417-barcode-with-aspose-barcode-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear código de barras macro PDF417 con Aspose.BarCode (C#)

Si necesitas **crear un código de barras macro PDF417** en una aplicación .NET, este tutorial te muestra exactamente cómo hacerlo con Aspose.BarCode. Verás un ejemplo completo y ejecutable que **genera el código de barras con Aspose**, configura todos los campos específicos del macro y guarda el resultado como una imagen PNG.

Los códigos de barras se usan a menudo para inventario, envío o seguimiento de documentos, y la variante Macro PDF417 permite incrustar metadatos a nivel de archivo dentro del propio código de barras. Al final de esta guía podrás generar un código de barras macro PDF417 totalmente funcional que cumple con la norma ISO/IEC 15438.

## Lo que necesitarás

Antes de comenzar, asegúrate de tener:

* .NET 6.0 SDK o posterior (el código funciona con .NET Core y .NET Framework)
* Visual Studio 2022 (o cualquier IDE de C#)
* Una conexión a Internet compatible con NuGet para obtener el paquete Aspose.BarCode
* Familiaridad básica con la sintaxis de C#

Estos requisitos previos garantizan que el código se compile sin configuraciones adicionales.

## Paso 1: Instalar el paquete NuGet Aspose.BarCode

La biblioteca Aspose.BarCode proporciona la clase `BarcodeGenerator` que se usa a lo largo de este tutorial.

```bash
dotnet add package Aspose.BarCode
```

Ejecutar el comando agrega la última versión estable a tu archivo de proyecto (`*.csproj`). El paquete incluye soporte para PDF417, Macro PDF417 y muchas otras simbologías.

## Paso 2: Crear un nuevo proyecto de consola (opcional)

Si prefieres comenzar con una base limpia, genera una aplicación de consola:

```bash
dotnet new console -n MacroPdf417Demo
cd MacroPdf417Demo
```

El `Program.cs` generado alojará el código de generación del código de barras.

## Paso 3: Inicializar el generador de códigos de barras

El generador se crea con el valor de enumeración `EncodeTypes.MacroPdf417` y el texto que deseas codificar. Aspose.BarCode maneja automáticamente los caracteres Unicode, por lo que puedes incluir letras acentuadas o símbolos directamente.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

class Program
{
    static void Main()
    {
        // Step 3: Create a Macro PDF417 barcode generator with the desired text
        using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // The rest of the configuration follows...
```

### Por qué es importante
`EncodeTypes.MacroPdf417` indica a la biblioteca que use la versión macro de PDF417, lo que añade la capacidad de incrustar metadatos a nivel de archivo (ID de archivo, recuento de segmentos, etc.). El texto `"Åspóse.Barcóde©"` demuestra que el generador codifica correctamente caracteres UTF‑8.

## Paso 4: Establecer dimensiones básicas del código de barras

PDF417 permite controlar el número de columnas y la dimensión X (el ancho de un módulo único). Ajustar estos valores influye en el tamaño físico del código de barras y en la fiabilidad del escaneo.

```csharp
            // Step 4: Set basic barcode dimensions
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // module width in pixels
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

* **XDimension** – Valores más pequeños producen un código de barras más denso; valores mayores facilitan la lectura con escáneres de baja resolución.
* **Columns** – Controla el número de columnas de datos; los valores típicos van de 1 a 30.

## Paso 5: Configurar los metadatos Macro PDF417

Macro PDF417 lleva campos adicionales que describen el archivo que representa el código de barras. Cada campo es opcional, pero configurarlos mejora la interoperabilidad con escáneres que entienden el formato macro.

```csharp
            // Step 5: Configure Macro PDF417 metadata
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // demo checksum
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // bytes
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### Explicación de cada campo

| Property | Propósito | Rango típico |
|----------|-----------|--------------|
| **MacroPdf417FileID** | Identificador único para el archivo lógico que puede dividirse en varios códigos de barras. | 0‑2³²‑1 |
| **MacroPdf417SegmentID** | Índice del segmento actual (comienza en 0). | 0‑(SegmentsCount‑1) |
| **MacroPdf417SegmentsCount** | Número total de segmentos que componen el archivo completo. | 1‑99 |
| **MacroPdf417FileName** | Nombre legible del archivo. | Hasta 255 caracteres |
| **MacroPdf417Checksum** | Suma de verificación opcional para detección de errores. | 0‑65535 |
| **MacroPdf417FileSize** | Tamaño del archivo original en bytes. | 0‑2³²‑1 |
| **MacroPdf417TimeStamp** | Marca de tiempo de creación o modificación del archivo. | Cualquier `DateTime` |
| **MacroPdf417Addressee** | Identificador del destinatario (p. ej., departamento o máquina). | Cadena libre |
| **MacroPdf417Sender** | Identificador del origen (p. ej., nombre de la empresa). | Cadena libre |
| **MacroPdf417Terminator** | Indica si este segmento es el último. | `Set` o `Unset` |

**Consejo profesional:** Si divides un archivo grande en varios códigos de barras, asegúrate de que el `SegmentID` de cada segmento sea secuencial y que `SegmentsCount` permanezca constante en todos los segmentos. Los escáneres dependen de estos valores para reconstruir el archivo original.

## Paso 6: Guardar la imagen del código de barras

Aspose.BarCode admite muchos formatos de salida (PNG, JPEG, BMP, SVG, etc.). PNG ofrece calidad sin pérdidas, lo que es ideal para pruebas y documentación.

```csharp
            // Step 6: Save the barcode image as PNG
            barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }
    }
}
```

Ejecutar el programa crea un archivo llamado `ExtPDF417Meta.png` en el directorio de salida del proyecto (`bin/Debug/net6.0/`). Abre la imagen con cualquier visor para verificar que el código de barras se renderiza correctamente.

## Paso 7: Verificar el código de barras generado (opcional)

Si dispones de una aplicación escáner PDF417 (móvil o de escritorio), escanea el PNG guardado. El escáner debería devolver:

* El texto codificado `"Åspóse.Barcóde©"`
* Todos los campos macro que configuraste (ID de archivo, ID de segmento, etc.)

Para verificación automatizada, Aspose.BarCode también ofrece la clase `BarCodeReader`:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

using (var reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Text: {result.CodeText}");
        Console.WriteLine($"Macro File ID: {result.GetMacroPdf417FileID()}");
        // Access other macro properties similarly
    }
}
```

Este fragmento muestra cómo leer de nuevo los metadatos macro programáticamente, confirmando que **generar código de barras con Aspose** funciona de extremo a extremo.

## Casos límite y buenas prácticas

| Situación | Manejo recomendado |
|-----------|--------------------|
| **Caracteres Unicode** | Asegúrate de que la cadena fuente sea UTF‑8 (predeterminado en .NET). Aspose.BarCode codifica Unicode automáticamente, pero verifica el conjunto de caracteres del escáner. |
| **Tamaño de archivo grande** | Macro PDF417 divide archivos en hasta 99 segmentos. Si el archivo supera los 400 KB, incrementa `SegmentsCount` y genera varios códigos de barras, cada uno con un `SegmentID` secuencial. |
| **Precisión de la marca de tiempo** | Usa `DateTime.UtcNow` para tiempo universal; algunos escáneres esperan UTC. |
| **Validación de suma de verificación** | Proporciona una suma de verificación correcta si planeas validar la integridad en el lado receptor. |
| **Diferentes formatos de imagen** | Usa `BarCodeImageFormat.Svg` para gráficos vectoriales cuando necesites códigos de barras escalables infinitamente. |
| **Rendimiento** | Reutiliza una única instancia de `BarcodeGenerator` al generar muchos códigos de barras; solo cambia los `Parameters` entre iteraciones. |

## Ejemplo completo y ejecutable

A continuación tienes el programa completo que puedes copiar, pegar y ejecutar sin modificaciones (suponiendo que el paquete NuGet está instalado).



## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Aspose barcode example: generate Macro PDF417 in C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [Create PDF417 Barcode Metadata in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}