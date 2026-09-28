---
category: general
date: 2026-07-21
description: Genera códigos de barras en C# rápidamente con Aspose.BarCode. Aprende
  a crear códigos de barras DataBar, personalizar el tamaño del código de barras y
  exportar la imagen del código de barras en solo unos pocos pasos.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode c#
- create databar barcode
- customize barcode size
- change barcode dimensions
- export barcode image
language: es
lastmod: 2026-07-21
og_description: Genera códigos de barras en C# usando Aspose.BarCode. Crea un código
  de barras DataBar, personaliza su tamaño y exporta la imagen al instante.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode saved as PNG
og_title: Generar código de barras C# – Crear códigos de barras DataBar con tamaño
  personalizado
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: Generate barcode C# quickly with Aspose.BarCode. Learn to create DataBar
    barcode, customize barcode size, and export barcode image in just a few steps.
  headline: Generate barcode C# – Create DataBar barcode
  type: TechArticle
- questions:
  - answer: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, `Gif`, or `Svg`.
      The API handles the conversion automatically.
    question: What if I need a different image format?
  - answer: Technically you can set both, but Aspose will prioritize the last property
      you modify. It's safer to set *one* dimension and let the library compute the
      other for a valid DataBar.
    question: Can I change both rows and columns simultaneously?
  - answer: 'Use `barcodeGen.Parameters.Barcode.ForegroundColor` and `BackgroundColor`.
      Example:'
    question: How do I apply a foreground/background color?
  - answer: DataBar Expanded Stacked supports up to 74 numeric characters (or 30 alphanumeric).
      Exceeding that throws an exception.
    question: Is there a size limit for the encoded data?
  type: FAQPage
tags:
- barcode
- csharp
- databar
- image-export
- aspnet
title: Generar código de barras C# – Crear código de barras DataBar
url: /es/python-java/general/generate-barcode-c-create-databar-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generar código de barras C# – Crear código de barras DataBar

¿Buscas **generar código de barras C#** sin tener que sumergirte en interminables documentos? Estás en el lugar correcto. En esta guía recorreremos la creación de un **código de barras DataBar**, ajustaremos sus dimensiones y, finalmente, **exportaremos la imagen del código de barras**, todo con unas pocas líneas de C#.

Imagina que necesitas una etiqueta de producto compacta que quepa en una pequeña etiqueta de estante. La simbología **DataBar Expanded Stacked** hace el truco, y con Aspose.BarCode puedes controlar exactamente cuántas columnas o filas utiliza. ¿Listo? Vamos a sumergirnos.

## Lo que lograrás

- **Crear un código de barras DataBar** (la variante “expanded stacked”) desde cero.  
- **Personalizar el tamaño del código de barras** estableciendo columnas o filas directamente.  
- **Cambiar las dimensiones del código de barras** sobre la marcha sin reconstruir el generador.  
- **Exportar la imagen del código de barras** a PNG (o cualquier formato que Aspose admita).  

Sin servicios externos, sin configuraciones complicadas—solo código C# limpio y ejecutable.

## Requisitos previos

- .NET 6.0 o posterior (el código también funciona en .NET Framework 4.7+).  
- Una licencia válida de Aspose.BarCode para .NET (o puedes usar el modo de prueba).  
- Un IDE de tu elección—Visual Studio, Rider o VS Code sirven.  

Si aún no has instalado el paquete NuGet, ejecuta:

```bash
dotnet add package Aspose.BarCode
```

Eso es todo—no hay otras dependencias.

## Paso 1: Configurar el generador de códigos de barras (Cómo **generar código de barras C#**)

Primero, necesitamos una instancia de `BarcodeGenerator` apuntando a la simbología **DataBar Expanded Stacked**. Este objeto es el motor que crea la imagen más adelante.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Initialize the generator with the desired symbology and data
BarcodeGenerator barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // Symbology
    "Databar Expanded Stacked long");    // Human‑readable text (optional)
```

*Por qué es importante*: El enum `EncodeTypes.DatabarExpandedStacked` le indica a Aspose que queremos la versión apilada, ideal para espacios estrechos. El texto que pasamos se convierte en el valor codificado; puedes reemplazarlo por cualquier cadena numérica que requiera tu aplicación.

## Paso 2: **Personalizar el tamaño del código de barras** – establecer columnas

Los códigos de barras DataBar te permiten influir en la densidad visual especificando ya sea el número de **columnas** *o* **filas**. Comencemos con columnas. El recuento de filas se calculará automáticamente para mantener el código de barras válido.

```csharp
// Set the number of columns; rows are computed automatically
barcodeGen.Parameters.Barcode.DataBar.Columns = 4;
```

*Consejo profesional*: Las columnas afectan el ancho del código de barras. Más columnas → código más ancho, lo que puede mejorar la fiabilidad de la lectura en impresoras de baja resolución.

## Paso 3: **Exportar la imagen del código de barras** con la configuración de columnas

Ahora escribimos la imagen en disco. Puedes elegir PNG, JPEG, BMP o incluso SVG. Aquí usamos PNG para obtener una salida nítida y sin pérdida.

```csharp
// Save the barcode image using the current column configuration
barcodeGen.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

> **Resultado esperado** – Abre `DatabarCols4.png` y deberías ver un DataBar apilado ordenadamente con cuatro columnas. Aparece como una pila densa de barras verticales, perfecta para una etiqueta pequeña.

## Paso 4: **Cambiar dimensiones del código de barras** – establecer filas en su lugar

A veces necesitas un código de barras más alto en lugar de más ancho. Cambia al control por filas; Aspose recalculará las columnas automáticamente.

```csharp
// Switch to row control – columns will be derived automatically
barcodeGen.Parameters.Barcode.DataBar.Rows = 3;
```

*¿Por qué cambiar?* Las filas afectan la altura del código de barras. Más filas hacen el símbolo más alto, lo que puede ser útil cuando dispones de espacio vertical pero ancho limitado.

## Paso 5: **Exportar la imagen del código de barras** con la configuración de filas

Guarda la segunda variación. Observa que el nombre del archivo refleja el cambio; también podrías mantener ambas imágenes para compararlas.

```csharp
// Save the barcode image using the new row configuration
barcodeGen.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

> **Resultado** – `DatabarRows3.png` muestra ahora una versión más alta de los mismos datos, aún perfectamente escaneable.

## Ejemplo completo funcionando

Juntándolo todo, aquí tienes una aplicación de consola autocontenida que puedes copiar‑pegar y ejecutar de inmediato:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator for DataBar Expanded Stacked
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Customize size – set columns (width)
        barcodeGen.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Export image with column setting
        string colPath = @"C:\Barcodes\DatabarCols4.png";
        barcodeGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column‑based barcode to {colPath}");

        // 4️⃣ Change dimensions – set rows (height)
        barcodeGen.Parameters.Barcode.DataBar.Rows = 3;

        // 5️⃣ Export image with row setting
        string rowPath = @"C:\Barcodes\DatabarRows3.png";
        barcodeGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row‑based barcode to {rowPath}");
    }
}
```

Ejecuta el programa y luego abre los dos archivos PNG. Ahora has **generado código de barras C#**, **personalizado el tamaño del código de barras**, **cambiado las dimensiones del código de barras** y **exportado la imagen del código de barras**, todo en menos de un minuto.

## Preguntas comunes y casos límite

- **¿Qué pasa si necesito un formato de imagen diferente?**  
  Reemplaza `BarCodeImageFormat.Png` por `Jpeg`, `Bmp`, `Gif` o `Svg`. La API maneja la conversión automáticamente.

- **¿Puedo cambiar filas y columnas simultáneamente?**  
  Técnicamente puedes establecer ambos, pero Aspose priorizará la última propiedad que modifiques. Es más seguro establecer *una* dimensión y dejar que la biblioteca calcule la otra para obtener un DataBar válido.

- **¿Cómo aplico un color de primer plano/fondo?**  
  Usa `barcodeGen.Parameters.Barcode.ForegroundColor` y `BackgroundColor`. Ejemplo:  
  ```csharp
  barcodeGen.Parameters.Barcode.ForegroundColor = Color.DarkBlue;
  barcodeGen.Parameters.Barcode.BackgroundColor = Color.White;
  ```

- **¿Existe un límite de tamaño para los datos codificados?**  
  DataBar Expanded Stacked admite hasta 74 caracteres numéricos (o 30 alfanuméricos). Superar ese límite lanza una excepción.

## Próximos pasos

Ahora que dominas los conceptos básicos de **crear código de barras databar**, considera:

- Añadir **anotaciones de texto** bajo el código de barras (`barcodeGen.Parameters.CaptionAbove.Text`).  
- Incrustar el PNG directamente en un PDF usando Aspose.PDF.  
- Generar códigos de barras en lote iterando sobre un CSV de IDs de producto.  

Cada uno de estos temas se basa en el mismo objeto `BarcodeGenerator`, por lo que no tendrás que comenzar desde cero.

---

**En conclusión**: ahora sabes cómo **generar código de barras C#**, **personalizar el tamaño del código de barras**, **cambiar las dimensiones del código de barras** y **exportar la imagen del código de barras** con Aspose.BarCode. Juega con los valores de columna/fila, cambia los formatos de imagen e integra el código en tu sistema de inventario o POS. ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}