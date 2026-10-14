---
category: general
date: 2026-10-09
description: Aprenda cómo crear un código de barras PDF417 en C# usando Aspose.BarCode
  – genere un Macro PDF417 con soporte completo de metadata.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode c#
- macro pdf417 c#
- aspose barcode c#
- barcode generator c#
lastmod: 2026-10-09
og_description: Aprenda cómo crear un código de barras PDF417 en C# usando Aspose.BarCode
  – genere un Macro PDF417 con soporte completo de metadata, incluyendo file ID, segment
  data, timestamp y más.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: Cómo crear un código de barras PDF417 en C# con Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- aspose barcode
- pdf417 barcode
- c# barcode generation
- macro pdf417
title: Cómo crear un código de barras PDF417 en C# con Aspose.BarCode
url: /es/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un código de barras PDF417 en C# con Aspose.BarCode

## Respuestas rápidas
- **¿Qué biblioteca genera códigos de barras PDF417?** Aspose.BarCode for .NET.
- **¿Qué formato produce el ejemplo?** Una imagen PNG sin pérdida.
- **¿Necesito una licencia?** Una prueba gratuita funciona para el ejemplo; se requiere una licencia comercial para producción.
- **¿Qué versión de .NET es compatible?** .NET 6.0 o posterior.
- **¿Puedo añadir metadatos al código de barras?** Sí – Macro PDF417 admite ID de archivo, recuento de segmentos, marcas de tiempo y más.

## ¿Qué es un código de barras PDF417?
Un código de barras PDF417 es una simbología lineal apilada que puede codificar hasta aproximadamente 1 KB de datos por símbolo y admite metadatos macro opcionales para archivos multi‑segmento. Consiste en múltiples filas de patrones lineales apilados, lo que permite una alta capacidad de datos mientras sigue siendo legible por escáneres 2‑D estándar. El formato también incluye niveles de corrección de errores para mejorar la fiabilidad, y la función macro opcional permite dividir archivos grandes en varios códigos de barras con metadatos que ayudan a reensamblarlos.

## ¿Por qué usar Aspose.BarCode para PDF417?
Aspose.BarCode admite **más de 50 simbologías de códigos de barras** y puede generar códigos de barras Macro PDF417 con hasta **2 000 columnas**, manejando archivos de más de **10 MB** sin cargar toda la carga útil en memoria. Esta capacidad cuantificada garantiza que los escenarios empresariales de alto rendimiento funcionen sin problemas, y ofrece amplias opciones de personalización.

## Requisitos previos

Antes de comenzar, asegúrese de tener:

- .NET 6.0 (o posterior) instalado  
- Visual Studio 2022 o cualquier IDE compatible con C#  
- Una licencia válida para **Aspose.BarCode for .NET** (la prueba gratuita funciona para este ejemplo)  

Agregue el paquete NuGet Aspose.BarCode a su proyecto:

```bash
dotnet add package Aspose.BarCode
```

## ¿Cómo crear un código de barras PDF417 en C#?

`BarcodeGenerator` es la clase principal para crear imágenes de códigos de barras.  
`EncodeTypes.MacroPdf417` selecciona la simbología Macro PDF417 para la generación del código de barras.  
`Save` escribe el código de barras generado a un archivo de imagen.

Cargue el `BarcodeGenerator` con el enumerado `EncodeTypes.MacroPdf417` y su texto objetivo, luego llame a `Save`: ese es el flujo completo de creación en tres líneas. El generador maneja Unicode automáticamente, y la instrucción `using` garantiza que los recursos no administrados se liberen después de guardar la imagen.

### Paso 1: crear la instancia del generador de códigos de barras en C#

La clase `BarcodeGenerator` crea y configura imágenes de códigos de barras.  

Instancie `BarcodeGenerator` con el valor del enumerado `EncodeTypes.MacroPdf417` y el texto que desea codificar. El texto puede contener caracteres Unicode, que la biblioteca maneja automáticamente.

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*Por qué es importante*: `EncodeTypes.MacroPdf417` indica al motor que produzca un símbolo Macro PDF417, que admite datos segmentados y metadatos a nivel de archivo. La instrucción `using` garantiza que los recursos no administrados se liberen después de guardar la imagen.

### Paso 2: definir la apariencia básica del código de barras

`XDimension.Pixels` establece el tamaño de cada módulo del código de barras en píxeles.

Un código de barras Macro PDF417 consta de módulos cuadrados. Controlar el tamaño del módulo y el recuento de columnas influye tanto en la legibilidad como en el tamaño del archivo.

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*Por qué es importante*: `XDimension.Pixels` determina la densidad visual; un valor de 2 píxeles funciona bien para la visualización en pantalla mientras mantiene la imagen pequeña. Ajuste el recuento de columnas para adaptarse a sus limitaciones de diseño: más columnas crean un código de barras más ancho y corto.

### Paso 3: establecer metadatos específicos de Macro PDF417

`MacroPdf417FileID` identifica el archivo al que pertenecen todos los segmentos del código de barras.

Macro PDF417 amplía el formato PDF417 estándar con campos que permiten la reconstrucción de archivos grandes a partir de múltiples segmentos de código de barras. Cada campo es opcional, pero configurarlos demuestra todas las capacidades de la API.

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
- `MacroPdf417FileID` vincula todos los segmentos que pertenecen al mismo archivo lógico.  
- `MacroPdf417SegmentID` y `MacroPdf417SegmentsCount` permiten al decodificador reordenar los fragmentos correctamente.  
- `MacroPdf417Checksum` proporciona una verificación rápida de integridad sin decodificar toda la carga.  
- `MacroPdf417FileSize` y `MacroPdf417TimeStamp` permiten a los sistemas posteriores verificar que el archivo reconstruido coincide con el original.  
- `MacroPdf417Addressee` / `MacroPdf417Sender` son útiles en escenarios de logística o intercambio de documentos.  
- Establecer `MacroPdf417Terminator` a `Set` marca este código de barras como el segmento final, lo que simplifica el algoritmo de reconstrucción.

### Paso 4: guardar la imagen del código de barras generado

`Save` escribe la imagen del código de barras en la ruta de archivo especificada.

Finalmente, escriba el código de barras en un archivo PNG. Puede elegir cualquier formato compatible (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`).

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Por qué es importante*: PNG conserva los datos de píxeles sin pérdida, asegurando que los escáneres lean el patrón de módulos exacto que configuró. Cambiar el formato puede afectar la calidad visual y el tamaño del archivo.

#### Resultado esperado

Ejecutar el programa completo crea un archivo llamado **ExtPDF417Meta.png**. Al abrir la imagen se muestra un código de barras rectangular Macro PDF417 con el texto “Åspóse.Barcóde©” codificado, y la densidad visual coincide con la dimensión X de 2 píxeles que estableció. Escanear la imagen con un lector compatible con PDF417 devuelve todos los campos de metadatos definidos en el Paso 3.

## Ejemplo completo funcionando

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

- **Diferentes formatos de imagen**: Reemplace `BarCodeImageFormat.Png` con `Jpeg`, `Bmp` o `Tiff` si su sistema posterior prefiere otro formato.  
- **Cambiar el tamaño del módulo**: Valores mayores de `XDimension.Pixels` mejoran la fiabilidad del escaneo en escáneres de baja resolución pero aumentan el tamaño de la imagen.  
- **Múltiples segmentos**: Para producir un archivo multi‑segmento, genere una serie de códigos de barras, incremente `MacroPdf417SegmentID` para cada uno y mantenga `MacroPdf417FileID` constante. Sólo el último segmento debe tener `MacroPdf417Terminator` establecido.  
- **Compatibilidad Unicode**: El generador codifica automáticamente caracteres Unicode; asegúrese de que su cadena fuente use codificación UTF‑8 si la lee de un archivo externo.  
- **Manejo de errores**: Envuélvase el bloque `using` en un try‑catch para capturar `BarCodeException` por parámetros inválidos (p. ej., recuento de columnas fuera de rango).

## Consejos profesionales

- **Rendimiento**: Reutilice una única instancia de `BarcodeGenerator` al crear muchos códigos de barras con la misma configuración; solo cambie la propiedad `CodeText` entre guardados.  
- **Estimación del tamaño de archivo**: El campo `MacroPdf417FileSize` debe coincidir con el recuento de bytes de la carga original; las discrepancias pueden causar fallas de validación posteriores.  
- **Pruebas**: Valide los códigos de barras generados tanto con el decodificador incorporado de Aspose (`BarCodeReader`) como con un escáner de terceros para garantizar la interoperabilidad.

## Conclusión

Este ejemplo de **Aspose.BarCode** le muestra cómo **crear un código de barras PDF417 en C#** con soporte completo de metadatos Macro, brindándole una base sólida para construir pipelines de intercambio de datos basados en códigos de barras robustos.

## ¿Qué deberías aprender a continuación?

Los tutoriales siguientes cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos con explicaciones paso a paso para ayudarle a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en sus propios proyectos.

- [Cómo crear código de barras – PDF417 compacto con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cómo crear zona silenciosa de código de barras para Code 16K usando Aspose.BarCode para .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Cómo crear zona silenciosa de código de barras para ITF-14 usando Aspose.BarCode para .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

---  

**Última actualización:** 2026-10-09  
**Probado con:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose

## Tutoriales relacionados

- [Cómo generar imagen de código de barras Pdf417 en C con Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Cómo crear código de barras – PDF417 compacto con Aspose.BarCode](/barcode/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Tutorial del generador de códigos de barras: cómo generar código de barras Pdf417 en](/barcode/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}