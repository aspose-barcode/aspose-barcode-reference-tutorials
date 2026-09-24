---
category: general
date: 2026-08-09
description: Ejemplo de Aspose Barcode que muestra cómo usar un generador de códigos
  de barras en C# para crear un Macro PDF417 con soporte completo de metadatos.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode example
- barcode generator c#
language: es
lastmod: 2026-08-09
og_description: El ejemplo de código de barras de Aspose muestra cómo usar un generador
  de códigos de barras en C# para producir un código de barras Macro PDF417 que incluye
  el ID del archivo, datos del segmento, marca de tiempo y otros metadatos.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: Ejemplo de código de barras Aspose – crear Macro PDF417 con C#
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- Macro PDF417
title: 'Ejemplo de código de barras Aspose: generar Macro PDF417 en C#'
url: /es/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ejemplo de Aspose barcode: generar Macro PDF417 en C#

Si necesita un **aspose barcode example** que cree un Macro PDF417 barcode, esta guía le muestra cómo hacerlo con un **barcode generator C#**. Verá cada configuración requerida, desde dimensiones básicas hasta el conjunto completo de campos de metadatos Macro PDF417, y obtendrá una imagen PNG lista para el procesamiento posterior.

El tutorial cubre el flujo de trabajo completo, explica por qué cada parámetro es importante y proporciona un ejemplo de código listo para ejecutar. No se requieren referencias externas; puede copiar el código, ajustar los valores y ejecutarlo de inmediato.

## Prerequisites

Antes de comenzar, asegúrese de tener:

- .NET 6.0 (o posterior) instalado  
- Visual Studio 2022 o cualquier IDE compatible con C#  
- Una licencia válida para **Aspose.BarCode for .NET** (la prueba gratuita funciona para este ejemplo)  

Add the Aspose.BarCode NuGet package to your project:

```bash
dotnet add package Aspose.BarCode
```

## Paso 1: Crear la instancia del generador de códigos de barras C# 

El primer paso es instanciar `BarcodeGenerator` con el valor enum `EncodeTypes.MacroPdf417` y el texto que desea codificar. El texto puede contener caracteres Unicode, que la biblioteca maneja automáticamente.

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*Por qué es importante*: `EncodeTypes.MacroPdf417` indica al motor que produzca un símbolo Macro PDF417, que admite datos segmentados y metadatos a nivel de archivo adicionales. La instrucción `using` garantiza que los recursos no administrados se liberen después de guardar la imagen.

## Paso 2: Definir la apariencia básica del código de barras

Un Macro PDF417 barcode consiste en módulos cuadrados. Controlar el tamaño del módulo y la cantidad de columnas influye tanto en la legibilidad como en el tamaño del archivo.

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*Por qué es importante*: `XDimension.Pixels` determina la densidad visual; un valor de 2 píxeles funciona bien para la visualización en pantalla mientras mantiene la imagen pequeña. Ajuste la cantidad de columnas para adaptarse a sus limitaciones de diseño—más columnas crean un código de barras más ancho y corto.

## Paso 3: Establecer los metadatos específicos de Macro PDF417

Macro PDF417 amplía el formato estándar PDF417 con campos que permiten la reconstrucción de archivos grandes a partir de múltiples segmentos de código de barras. Cada campo es opcional, pero configurarlos demuestra todas las capacidades de la API.

```csharp
    // Unique identifier for the entire file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (zero‑based)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the file
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Logical name of the source file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // 16‑bit CCITT checksum for error detection
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate size of the original file in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;

    // Timestamp when the file was generated
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields for routing information
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the last segment
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Por qué es importante*:  
- `MacroPdf417FileID` enlaza todos los segmentos que pertenecen al mismo archivo lógico.  
- `MacroPdf417SegmentID` y `MacroPdf417SegmentsCount` permiten al decodificador reordenar los fragmentos correctamente.  
- `MacroPdf417Checksum` proporciona una verificación rápida de integridad sin decodificar toda la carga útil.  
- `MacroPdf417FileSize` y `MacroPdf417TimeStamp` permiten a los sistemas posteriores verificar que el archivo reconstruido coincide con el original.  
- `MacroPdf417Addressee` / `MacroPdf417Sender` son útiles en escenarios de logística o intercambio de documentos.  
- Configurar `MacroPdf417Terminator` a `Set` marca este código de barras como el segmento final, lo que simplifica el algoritmo de reconstrucción.

## Paso 4: Guardar la imagen del código de barras generado

Finalmente, guarde el código de barras en un archivo PNG. Puede elegir cualquier formato compatible (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`).

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Por qué es importante*: PNG conserva los datos de píxeles sin pérdida, garantizando que los escáneres lean el patrón de módulos exacto que configuró. Cambiar el formato puede afectar la calidad visual y el tamaño del archivo.

### Salida esperada

Ejecutar el programa completo crea un archivo llamado **ExtPDF417Meta.png**. Al abrir la imagen se muestra un código de barras rectangular Macro PDF417 con el texto “Åspóse.Barcóde©” codificado, y la densidad visual coincide con la dimensión X de 2 píxeles que estableció. Escanear la imagen con un lector compatible con PDF417 devuelve todos los campos de metadatos definidos en el Paso 3.

## Ejemplo completo funcional

Copie el código a continuación en un nuevo proyecto de consola (`dotnet new console`) y reemplace `YOUR_DIRECTORY` con una ruta absoluta o relativa que exista en su máquina.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a barcode generator for Macro PDF417 with the desired text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the basic barcode appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // pixel size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol

                // Step 3: Set Macro PDF417 specific metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the generated barcode image
                generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

Ejecute el programa (`dotnet run`). Después de la ejecución, verifique que el archivo PNG aparezca en la ubicación que especificó. Use cualquier aplicación de lectura de códigos de barras que admita Macro PDF417 para confirmar que los metadatos están incrustados correctamente.

## Variaciones comunes y casos límite

- **Diferentes formatos de imagen**: Reemplace `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` o `Tiff` si su sistema posterior prefiere otro formato.  
- **Cambiar el tamaño del módulo**: Valores mayores de `XDimension.Pixels` mejoran la fiabilidad del escaneo en escáneres de baja resolución pero aumentan el tamaño de la imagen.  
- **Múltiples segmentos**: Para producir un archivo multi‑segmento, genere una serie de códigos de barras, incremente `MacroPdf417SegmentID` para cada uno y mantenga `MacroPdf417FileID` constante. Sólo el último segmento debe tener `MacroPdf417Terminator` configurado.  
- **Soporte Unicode**: El generador codifica automáticamente caracteres Unicode; asegúrese de que su cadena fuente use codificación UTF‑8 si la lee de un archivo externo.  
- **Manejo de errores**: Envuelva el bloque `using` en un try‑catch para capturar `BarCodeException` por parámetros inválidos (p. ej., recuento de columnas fuera de rango).

## Consejos profesionales

- **Rendimiento**: Reutilice una única instancia de `BarcodeGenerator` al crear muchos códigos de barras con la misma configuración; solo cambie la propiedad `CodeText` entre guardados.  
- **Estimación del tamaño de archivo**: El campo `MacroPdf417FileSize` debe coincidir con el recuento de bytes de la carga útil original; las discrepancias pueden causar fallas de validación posteriores.  
- **Pruebas**: Valide los códigos de barras generados tanto con el decodificador incorporado de Aspose (`BarCodeReader`) como con un escáner de terceros para garantizar la interoperabilidad.

## Conclusión

Este **aspose barcode example

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarle a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en sus propios proyectos.

- [Cómo crear códigos de barras – Compact PDF417 con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cómo crear zona silenciosa de código de barras para Code 16K usando Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Cómo crear zona silenciosa de código de barras para ITF-14 usando Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}