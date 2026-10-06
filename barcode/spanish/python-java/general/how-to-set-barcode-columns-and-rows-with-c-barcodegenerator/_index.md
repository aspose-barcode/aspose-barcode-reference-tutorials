---
category: general
date: 2026-09-16
description: Aprende a configurar columnas de códigos de barras en C# usando BarcodeGenerator
  y también a establecer filas para los códigos de barras DataBar Expanded Stacked.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- set barcode columns
- set barcode rows
- DataBar Expanded Stacked
- BarcodeGenerator C#
- barcode image format
- configure barcode dimensions
language: es
lastmod: 2026-09-16
og_description: Establezca columnas de códigos de barras en C# rápidamente. Esta guía
  le muestra cómo configurar columnas, filas y el formato de imagen con BarcodeGenerator.
og_image_alt: DataBar Expanded Stacked barcode showing custom columns and rows
og_title: Establecer columnas y filas de códigos de barras en C# – guía completa de
  BarcodeGenerator
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set barcode columns in C# using BarcodeGenerator and also
    set barcode rows for DataBar Expanded Stacked barcodes.
  headline: How to set barcode columns and rows with C# BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Cómo configurar columnas y filas de códigos de barras con C# BarcodeGenerator
url: /es/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo establecer columnas y filas de códigos de barras con C# BarcodeGenerator

Si necesitas establecer columnas de códigos de barras en una aplicación C#, este tutorial muestra los pasos exactos requeridos. Verás cómo configurar tanto columnas como filas para un código de barras DataBar Expanded Stacked, y luego guardar el resultado como una imagen PNG.

Generar códigos de barras programáticamente te ahorra el trabajo manual de diseño y garantiza consistencia en informes, facturas y etiquetas de producto. El ejemplo a continuación cubre todo el flujo de trabajo, desde la instalación de la biblioteca hasta la producción de dos imágenes: una con un recuento de columnas personalizado y otra con un recuento de filas personalizado.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* .NET 6.0 o posterior instalado.  
* Una referencia al paquete NuGet **Aspose.BarCode for .NET**. Instálalo con:

```bash
dotnet add package Aspose.BarCode
```

* Permiso de escritura en una carpeta donde se guardarán los archivos PNG generados.

Estos requisitos garantizan que el código compile y se ejecute sin configuración adicional.

## Cómo establecer columnas de códigos de barras en C#

El primer paso importante es crear una instancia de `BarcodeGenerator` para la simbología **DataBar Expanded Stacked** y asignar el número de columnas deseado.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize a DataBar Expanded Stacked barcode generator with the target text.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the number of columns. The DataBar object exposes a Columns property.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image using the PNG format.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**Por qué funciona esto:**  
`EncodeTypes.DatabarExpandedStacked` indica a la biblioteca qué simbología renderizar. Establecer `Parameters.Barcode.DataBar.Columns` cambia la disposición interna de los módulos, lo que influye directamente en el ancho visual del código de barras. El método `Save` escribe la imagen en disco en el `BarCodeImageFormat` solicitado.

### Resultado esperado
Abre `C:\Barcodes\DatabarCols4.png` en cualquier visor de imágenes. Deberías ver un código de barras DataBar Expanded Stacked más ancho que el predeterminado porque utiliza cuatro columnas.

## Cómo establecer filas de códigos de barras en C#

Después de haber guardado la imagen basada en columnas, puede que necesites un código de barras que varíe en altura ajustando filas. El proceso refleja la configuración de columnas pero utiliza la propiedad `Rows` en su lugar.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 4️⃣ Re‑initialize the generator for a fresh configuration.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 5️⃣ Set the number of rows. This property controls the vertical module count.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6️⃣ Save the barcode image with the row configuration.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**Por qué funciona esto:**  
Reinicializar el generador asegura que la configuración de columnas anterior no interfiera con la configuración de filas. Cambiar `Parameters.Barcode.DataBar.Rows` modifica la altura del código de barras, produciendo una imagen más alta cuando el recuento de filas supera el valor predeterminado.

### Resultado esperado
Abre `C:\Barcodes\DatabarRows3.png`. El código de barras aparecerá más alto, reflejando la configuración de tres filas.

## Ejemplo completo de extremo a extremo

A continuación se muestra un programa único que crea ambas imágenes en una sola ejecución. Mantener el código en un solo archivo demuestra cómo puedes alternar entre configuraciones de columnas y filas sin reiniciar la aplicación.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Common text for both barcodes.
        const string barcodeText = "Databar Expanded Stacked long";

        // ---------- Column configuration ----------
        var colGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        colGenerator.Parameters.Barcode.DataBar.Columns = 4;
        colGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Row configuration ----------
        var rowGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;
        rowGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

Ejecutar el programa genera dos archivos PNG:

* **DatabarCols4.png** – código de barras con cuatro columnas.  
* **DatabarRows3.png** – código de barras con tres filas.

Ambos archivos usan el **formato de imagen de código de barras** PNG, que preserva bordes nítidos y soporta compresión sin pérdida, ideal para impresión y visualización digital.

## Preguntas comunes y consejos

| Pregunta | Respuesta |
|----------|-----------|
| *¿Puedo usar JPEG en lugar de PNG?* | Sí. Reemplaza `BarCodeImageFormat.Png` por `BarCodeImageFormat.Jpeg`. JPEG es más pequeño pero introduce artefactos de compresión, lo que puede afectar la fiabilidad del escáner. |
| *¿Cuál es el número máximo de columnas o filas?* | La biblioteca valida los valores contra la especificación DataBar. Los valores fuera del rango permitido lanzan una `ArgumentException`. Consulta la documentación de Aspose.BarCode para conocer los límites exactos. |
| *¿Necesito disponer el `BarcodeGenerator`?* | La clase implementa `IDisposable`. Envuelve el generador en un bloque `using` si creas muchas instancias dentro de un bucle para liberar recursos no administrados rápidamente. |
| *¿Cómo cambio el tamaño del código de barras sin alterar columnas/filas?* | Usa `barcodeGenerator.Parameters.Image.Width` y `Height` para escalar la imagen de salida manteniendo la disposición de módulos sin cambios. |

**Consejo pro:** Cuando generes códigos de barras para impresión de alta resolución, aumenta las dimensiones de la imagen de salida (`Width`/`Height`) en lugar de incrementar el número de columnas o filas. Este enfoque mantiene el tamaño de módulo estándar definido por la simbología mientras te brinda una imagen más nítida.

## Conclusión

Ahora sabes cómo establecer columnas y filas de códigos de barras en C# usando la clase **BarcodeGenerator**. La guía cubrió la inicialización del generador, la configuración de los recuentos de columnas y filas, el guardado del código de barras en formato PNG y el manejo de variaciones comunes como cambios de formato de imagen y la liberación de recursos.

A continuación, explora temas relacionados como **personalizar colores de códigos de barras**, **agregar texto legible por humanos** y **incorporar códigos de barras en documentos PDF**. Todas estas extensiones se basan en el mismo patrón de configuración demostrado aquí, permitiéndote crear soluciones de códigos de barras totalmente funcionales para cualquier aplicación .NET.

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Ejemplo de generador de códigos de barras en C# – Establecer columnas, filas y exportar imagen](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Guía de código de barras DataBar Expanded Stacked – cómo generar y dimensionarlo en C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Ejemplo de generador de códigos de barras en C# – establecer ancho y alto](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}