---
category: general
date: 2026-08-22
description: El tutorial del generador de códigos de barras en C# muestra cómo crear
  un código de barras Macro PDF417 con metadatos y guardarlo como PNG usando Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- Macro PDF417
- Aspose.BarCode
- C# barcode library
- PDF417 barcode
- barcode metadata
language: es
lastmod: 2026-08-22
og_description: El generador de códigos de barras C# le permite crear un código de
  barras Macro PDF417 con metadatos a nivel de archivo completos y exportarlo como
  PNG. Siga esta guía para implementar la solución.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C#
og_title: generador de códigos de barras C# – crea códigos de barras Macro PDF417
  paso a paso
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to create a Macro PDF417 barcode
    with metadata and save it as PNG using Aspose.BarCode.
  headline: How to use a barcode generator C# for Macro PDF417
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Cómo usar un generador de códigos de barras C# para Macro PDF417
url: /es/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo usar un generador de códigos de barras C# para Macro PDF417

Si necesita un **barcode generator C#** que pueda generar un símbolo Macro PDF417 con metadatos a nivel de archivo, esta guía le proporciona una solución completa y lista para ejecutar. Verá cómo configurar la apariencia del código de barras, incrustar información macro como el ID del archivo y el recuento de segmentos, y finalmente guardar el resultado como una imagen PNG.

El ejemplo utiliza la biblioteca Aspose.BarCode, una **C# barcode library** ampliamente adoptada que soporta el conjunto completo de funciones PDF417. No se requieren servicios externos, y el código funciona con .NET 6 o posterior.

## Requisitos previos

Antes de comenzar, asegúrese de contar con:

* SDK de .NET 6 (o cualquier versión posterior) instalado.
* Visual Studio 2022, VS Code, u otro IDE de C#.
* Una referencia NuGet a **Aspose.BarCode** (`dotnet add package Aspose.BarCode`).

Comprender la sintaxis básica de C# y el concepto de códigos de barras PDF417 le ayudará a seguir los pasos, pero el tutorial explica cada opción de configuración en detalle.

## Qué cubre el tutorial

* Inicializar una instancia de **barcode generator C#** para el formato Macro PDF417.  
* Ajustar parámetros visuales como X‑dimension y el recuento de columnas.  
* Proporcionar los campos a nivel de archivo de Macro PDF417: file ID, segment ID, segment count, file name, checksum, file size, timestamp, addressee, sender y terminator.  
* Guardar el símbolo generado como un archivo PNG.  
* Consejos para manejar casos límite como tamaños de archivo grandes o marcas de tiempo personalizadas.

Al final de este artículo tendrá un programa autónomo que produce un código de barras Macro PDF417 totalmente conforme.

## Paso 1: Crear la instancia del barcode generator C#

La primera operación es instanciar `BarcodeGenerator` con el valor enum `EncodeTypes.MacroPdf417` y el texto que desea codificar. El constructor también acepta la cadena de carga útil, que se convierte en la porción de datos del código macro.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for Macro PDF417
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent configuration goes here
}
```

**Por qué es importante** – La bandera `EncodeTypes.MacroPdf417` indica a Aspose.BarCode que trate el símbolo como un código macro, habilitando los campos adicionales que siguen. Sin esta bandera, la biblioteca generaría un código PDF417 regular sin metadatos a nivel de archivo.

## Paso 2: Ajustar la apariencia básica del código de barras (configuraciones visuales PDF417)

La claridad visual es crucial para un escaneo fiable. Dos parámetros comunes son el ancho del módulo (`XDimension`) y el número de columnas. Ajustar estos valores equilibra el tamaño y la legibilidad.

```csharp
    // Step 2: Adjust basic barcode appearance
    generator.Parameters.Barcode.XDimension.Pixels = 2;   // width of a single module
    generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol
```

* `XDimension.Pixels` controla el ancho de cada barra negra/blanca. Un valor de **2** funciona bien para la mayoría de impresoras de etiquetas.
* `Pdf417.Columns` define cuántas columnas usará el código de barras. Cinco columnas producen un símbolo compacto sin sacrificar la capacidad de datos.

## Paso 3: Definir la información a nivel de archivo de Macro PDF417

Macro PDF417 amplía el formato estándar PDF417 con campos que describen cómo un archivo grande se divide en varios segmentos de código de barras. Proporcionar estos campos asegura que los escáneres posteriores puedan reconstruir el archivo original.

```csharp
    // Step 3: Define Macro PDF417 file‑level information
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;          // unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;            // current segment number (0‑indexed)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;       // total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";      // optional logical file name
```

* `MacroPdf417FileID` debe ser el mismo para cada segmento que pertenezca al mismo archivo lógico.
* `MacroPdf417SegmentID` se incrementa de **0** a `SegmentsCount‑1`.
* `MacroPdf417SegmentsCount` indica al decodificador cuántas piezas esperar.
* `MacroPdf417FileName` es opcional pero útil para una identificación legible por humanos.

## Paso 4: Establecer metadatos macro adicionales

Más allá de la información básica del archivo, la especificación permite campos extra como checksum, file size, timestamp, addressee, sender y una bandera terminator. Completar estos campos mejora la integridad y trazabilidad de los datos.

```csharp
    // Step 4: Set additional macro metadata
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                     // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;                  // file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2024, 4, 1);
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

* `MacroPdf417Checksum` proporciona un checksum CCITT de 16 bits para todo el archivo; el decodificador puede verificar la integridad después de la reconstrucción.
* `MacroPdf417FileSize` debe reflejar el recuento exacto de bytes del archivo original; valores mayores que `2^31‑1` requieren un campo de 64 bits, que Aspose maneja automáticamente.
* `MacroPdf417TimeStamp` registra cuándo se generó el código de barras. Use UTC para evitar ambigüedades de zona horaria.
* `MacroPdf417Addressee` y `MacroPdf417Sender` son cadenas de texto libre que pueden almacenar información de enrutamiento.
* `MacroPdf417Terminator` indica que este es el segmento final; configúrelo a `Set` para la última pieza, de lo contrario deje el valor predeterminado (`NotSet`).

**Consejo para casos límite** – Si el tamaño de su archivo supera los 4 GB, divida el contenido en varios segmentos macro y ajuste `SegmentsCount` en consecuencia. La biblioteca gestionará el campo de gran tamaño sin desbordamiento.

## Paso 5: Guardar el código de barras como una imagen PNG

El paso final escribe el símbolo generado en disco. PNG conserva las dimensiones exactas de píxeles y es ampliamente soportado por el hardware de escaneo.

```csharp
    // Step 5: Save the generated barcode as a PNG image
    generator.Save("YOUR_DIRECTORY/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

Reemplace `YOUR_DIRECTORY` con una ruta absoluta o relativa a la que el proceso en ejecución pueda escribir. El enum `BarCodeImageFormat.Png` garantiza una salida sin pérdidas.

**¿Por qué PNG?** – Los formatos raster como PNG mantienen los bordes de los módulos nítidos, lo cual es esencial para los escáneres que dependen de bordes de alto contraste. Si necesita un formato vectorial, Aspose también soporta `Pdf` y `Svg`.

## Ejemplo completo ejecutable

A continuación se muestra el programa completo que puede copiar en una aplicación de consola. Incluye las directivas `using` necesarias y un método `Main`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for Macro PDF417 with sample payload
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
            {
                // Adjust visual appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // Define macro file‑level fields
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Add optional metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2024, 4, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Export to PNG
                generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

### Salida esperada

Ejecutar el programa crea un archivo llamado **MacroPdf417.png** en el directorio de trabajo del proyecto. Al abrir la imagen se muestra un código PDF417 compacto con los campos macro incrustados. Escanear la imagen con un lector compatible con PDF417 (p. ej., ZXing, decodificador Aspose.BarCode) devuelve la carga útil original `"Sample text"` junto con los metadatos macro.

## Preguntas comunes y solución de problemas

| Pregunta | Respuesta |
|----------|-----------|
| *¿Qué pasa si el código de barras es demasiado grande para la etiqueta objetivo?* | Reduzca `XDimension.Pixels` o aumente `Pdf417.Columns`. Ambos parámetros afectan el tamaño total. |
| *¿Puedo generar una imagen vectorial en lugar de PNG?* | Sí. Llame a `generator.Save("MacroPdf417.svg", BarCodeImageFormat.Svg);` para una salida escalable. |
| *¿Cómo verifico el checksum después de escanear?* | El decodificador Aspose.BarCode valida automáticamente `MacroPdf417Checksum` y reporta discrepancias en el objeto `MacroPdf417Result`. |
| *¿Es la biblioteca compatible con .NET Core?* | El paquete NuGet soporta .NET Standard 2.0+, lo que cubre .NET Core, .NET 5, .NET 6 y versiones posteriores. |
| *¿Qué pasa si necesito incrustar datos binarios en lugar de texto?* | Convierta la carga binaria a Base64 o use la sobrecarga `EncodeTypes.MacroPdf417` que acepta un arreglo de bytes. |

## Consejos profesionales para uso en producción

* **Cache the generator** –

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarle a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en sus propios proyectos.

- [Cómo crear un código de barras – PDF417 compacto con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cómo leer códigos de barras de PDF en Java usando Aspose.BarCode](/barcode/english/java/document-barcode-recognition/recognizing-barcodes-from-pdf/)
- [Crear código de barras Codabar con Aspose.Barcode – API de generador y lector](/barcode/english/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}