---
category: general
date: 2026-10-15
description: Crea códigos de barras PNG rápidamente usando C#. Aprende cómo generar
  códigos de barras, cambiar filas, configurar los ajustes del código de barras y
  generar códigos de barras PDF417 en un solo tutorial.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to generate barcode
- how to change rows
- how to configure barcode
- generate pdf417 barcode
language: es
lastmod: 2026-10-15
og_description: Crear PNG de código de barras en C# rápidamente. Este tutorial muestra
  cómo generar el código de barras, cambiar filas, configurar el código de barras
  y generar un código de barras PDF417 con código claro.
og_image_alt: Generated PDF417 barcode saved as a PNG file
og_title: Crear código de barras PNG con PDF417 en C# – guía paso a paso
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode PNG quickly using C#. Learn how to generate barcode,
    change rows, configure barcode settings, and generate PDF417 barcode in a single
    tutorial.
  headline: Create barcode PNG with PDF417 in C# – complete guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Crear código de barras PNG con PDF417 en C# – guía completa
url: /es/net/compact-pdf417-encoding/create-barcode-png-with-pdf417-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear PNG de código de barras con PDF417 en C# – guía completa

Si necesitas **crear PNG de código de barras** desde código C#, esta guía te muestra exactamente cómo hacerlo. Recorreremos la generación de un código de barras PDF417, el cambio de filas y la configuración de todos los parámetros clave antes de guardar el resultado como una imagen PNG.

Aprenderás a **generar código de barras** de forma programática, ajustar el diseño para que coincida con tu proyecto y comprender las opciones para configurar la apariencia de un código de barras. No se requieren herramientas externas, solo la biblioteca Aspose.BarCode (o cualquier paquete .NET de códigos de barras compatible) y unas pocas líneas de código.

## Lo que necesitarás

- .NET 6.0 o posterior (el ejemplo usa .NET 6, pero cualquier versión reciente de .NET funciona)
- Una referencia al paquete NuGet `Aspose.BarCode` (`Install-Package Aspose.BarCode`)
- Familiaridad básica con C# y Visual Studio (o tu IDE preferido)

> **Consejo profesional:** Si prefieres una alternativa gratuita, la misma superficie de API está disponible en la biblioteca de código abierto `ZXing.Net`; sin embargo, los fragmentos de código a continuación están dirigidos a Aspose.BarCode porque ofrece controles directos del diseño PDF417.

## Paso 1: Configurar el proyecto y agregar la biblioteca de códigos de barras

Crea una nueva aplicación de consola y agrega el paquete NuGet:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Luego abre `Program.cs` y agrega las directivas `using` requeridas:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Estos espacios de nombres exponen la clase `BarcodeGenerator` y la enumeración `EncodeTypes` que usarás para **generar imágenes de código de barras PDF417**.

## Paso 2: Crear PNG de código de barras – generador básico

La primera línea ejecutable crea una instancia de `BarcodeGenerator` configurada para la codificación PDF417. Este es el núcleo de **cómo generar código de barras** en imágenes.

```csharp
// Step 2: Initialize the generator with PDF417 and the data to encode
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test"))
{
    // The rest of the configuration goes here
}
```

> **Por qué es importante:** La bandera `EncodeTypes.Pdf417` indica a la biblioteca qué simbología usar. El segundo argumento (`"Layout test"`) es el texto sin procesar que se codificará en el código de barras.

## Paso 3: Cómo configurar el código de barras – establecer el tamaño del módulo

Un módulo (o dimensión X) define el elemento imprimible más pequeño del código de barras. Ajustarlo cambia el tamaño total de la imagen sin afectar la densidad de datos.

```csharp
// Step 3: Set the module size (X dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Establecer `Pixels = 2` produce un resultado **crear PNG de código de barras** compacto y de alta resolución que funciona bien para miniaturas web e impresión.

## Paso 4: Cómo cambiar filas – personalizar el diseño PDF417

PDF417 permite controlar explícitamente el número de columnas y filas. Este es el paso que responde a **cómo cambiar filas** en un código de barras.

```csharp
// Step 4: Define a custom layout – 4 columns and 9 rows
generator.Parameters.Barcode.Pdf417.Columns = 4;   // number of data columns
generator.Parameters.Barcode.Pdf417.Rows    = 9;   // number of rows (the focus of “how to change rows”)
```

> **Caso límite:** Si solicitas más filas de las que los datos requieren, la biblioteca añadirá automáticamente filas de relleno. Por el contrario, solicitar muy pocas filas puede provocar una excepción porque los datos no caben.

## Paso 5: Guardar el código de barras generado como archivo PNG

Finalmente, escribe la imagen en disco. Esto completa el flujo de trabajo **crear PNG de código de barras**.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417_4x9.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode PNG saved to: {outputPath}");
```

Al ejecutar el programa, verás un archivo llamado `Pdf417_4x9.png` en la carpeta del proyecto. La imagen contiene un código de barras PDF417 con exactamente 4 columnas y 9 filas, renderizado con módulos de 2 píxeles.

### Ejemplo completo ejecutable

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the generator for PDF417
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test"))
        {
            // Configure module size
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Custom layout: 4 columns, 9 rows
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows    = 9;

            // Save as PNG
            string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417_4x9.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode PNG saved to: {outputPath}");
        }
    }
}
```

**Salida esperada** (consola):

```
Barcode PNG saved to: C:\Path\To\BarcodeDemo\Pdf417_4x9.png
```

Abre el archivo PNG y verás un código de barras PDF417 limpio listo para escanear.

## Cómo generar código de barras con datos diferentes

Si necesitas **generar código de barras** para otra cadena, simplemente reemplaza el segundo argumento del constructor `BarcodeGenerator`:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Pdf417, "New data payload"))
{
    // Keep the same configuration or adjust as needed
}
```

Los mismos pasos de configuración (tamaño del módulo, filas, columnas) se aplican, lo que te permite reutilizar el código para múltiples cargas útiles.

## Cómo cambiar filas dinámicamente según la longitud del contenido

A veces el número de filas debe adaptarse a la longitud del texto codificado. Puedes calcular un recuento de filas seguro antes de crear el generador:

```csharp
int estimatedRows = (int)Math.Ceiling(text.Length / (double)(columns * 2)); // rough estimate
generator.Parameters.Barcode.Pdf417.Rows = Math.Max(3, estimatedRows);
```

Este fragmento garantiza que nunca solicites menos de tres filas (el mínimo de la biblioteca) mientras escalas para datos más extensos.

## Cómo configurar el código de barras para diferentes formatos de imagen

Aunque el tutorial se centra en PNG, puedes cambiar a JPEG, BMP o TIFF modificando la enumeración `BarCodeImageFormat`:

```csharp
generator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
```

PNG sigue siendo la mejor opción para calidad sin pérdidas, especialmente cuando el código de barras se imprimirá.

## Problemas comunes y solución de errores

| Síntoma | Causa probable | Solución |
|---------|----------------|----------|
| El código de barras aparece borroso | Dimensión X demasiado grande o escalado de la imagen después de guardar | Mantén `XDimension.Pixels` ≤ 3 para uso en pantalla, o aumenta la resolución con un formato vectorial (PDF) |
| El escáner no puede leer el código de barras | Muy pocas filas para la longitud de los datos | Incrementa `Pdf417.Rows` o permite que la biblioteca ajuste automáticamente omitiendo la configuración explícita de filas |
| `ArgumentOutOfRangeException` al guardar | El directorio de salida no existe | Asegúrate de que `outputPath` apunte a una carpeta válida o créala con `Directory.CreateDirectory` |

## Resumen

Este tutorial demostró cómo **crear PNG de código de barras** en C# usando la simbología PDF417. Aprendiste:

- **Cómo generar código de barras** con la clase `BarcodeGenerator`  
- **Cómo cambiar filas** y columnas para controlar el diseño  
- **Cómo configurar el código de barras** (tamaño del módulo, formato de imagen)  
- Cómo **generar código de barras PDF417** y guardarlo como una imagen PNG

Ahora dispones de un bloque de código reutilizable que puedes adaptar para diferentes cargas útiles, formatos de imagen o requisitos de diseño.

## Próximos pasos

- Experimenta con `Pdf417.ErrorCorrectionLevel` para mejorar la fiabilidad de escaneo en impresiones de baja calidad.  
- Combina varios códigos de barras en un único PDF usando Aspose.PDF para generación masiva de etiquetas.  
- Explora otras simbologías (`EncodeTypes.Code128`, `EncodeTypes.QR`) cambiando el valor de la enumeración; esto se alinea con la palabra clave secundaria **generate pdf417 barcode** mientras muestra capacidades más amplias.

¡Feliz codificación y disfruta creando PNG de códigos de barras nítidos para cualquier aplicación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques alternativos en tus propios proyectos.

- [How to create PDF417 barcode and export PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/)
- [How to generate PDF417 barcodes in C# with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/)
- [How to create barcode PNG with a custom aspect ratio in C#](/barcode/english/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}