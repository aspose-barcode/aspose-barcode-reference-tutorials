---
category: general
date: 2026-08-22
description: Crea un código de barras FCC 11 en C# usando Aspose.BarCode. Aprende
  el código paso a paso, configura las dimensiones y genera imágenes PNG para Australia
  Post.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create fcc 11 barcode
- Australia Post barcode
- Aspose.BarCode C#
- FCC 59 barcode
- FCC 62 barcode
- N‑Table encoding
- C‑Table encoding
language: es
lastmod: 2026-08-22
og_description: Crea el código de barras FCC 11 en C# con Aspose.BarCode. Sigue este
  tutorial conciso para generar códigos de barras PNG para Australia Post, incluidas
  las variantes FCC 59 y FCC 62.
og_image_alt: Screenshot showing a generated FCC 11 barcode image
og_title: Crear código de barras FCC 11 en C# – guía completa de Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  headline: How to create FCC 11 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  name: How to create FCC 11 barcode in C# with Aspose.BarCode
  steps:
  - name: 4.1 FCC 59 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)'
  - name: 4.2 FCC 62 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)'
  - name: 4.3 FCC 62 with C‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix'
  - name: 4.4 FCC 62 with Other encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567321032103210"); // Long payload for "Other" table'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- AustraliaPost
title: Cómo crear un código de barras FCC 11 en C# con Aspose.BarCode
url: /es/python-java/general/how-to-create-fcc-11-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un código de barras FCC 11 en C# con Aspose.BarCode

Si necesita **crear un código de barras FCC 11** en una aplicación .NET, esta guía le muestra el código exacto necesario. Verá cómo configurar las dimensiones del código de barras, elegir la tabla de codificación adecuada y guardar el resultado como un archivo PNG.

Generar códigos de barras de Australia Post es un requisito común para logística, sistemas de correo y seguimiento de inventario. Este tutorial cubre el formato FCC 11 y también muestra cómo producir códigos de barras FCC 59 y FCC 62 con diferentes tablas de codificación, para que pueda reutilizar el mismo patrón para otros servicios postales.

## Lo que necesitará

Antes de comenzar, asegúrese de tener:

* .NET 6.0 SDK o posterior instalado  
* Visual Studio 2022 (o cualquier IDE compatible con C#)  
* Una licencia válida para **Aspose.BarCode for .NET** – la edición comunitaria funciona para evaluación  
* Permiso de escritura en una carpeta donde se guardarán los archivos PNG  

Estos requisitos previos garantizan que el código compile y se ejecute sin configuración adicional.

## Paso 1: Instalar el paquete NuGet Aspose.BarCode

Abra una terminal en la carpeta del proyecto y ejecute:

```bash
dotnet add package Aspose.BarCode
```

El comando agrega la última versión estable de la biblioteca a su archivo de proyecto. El paquete contiene la clase `BarcodeGenerator` utilizada a lo largo de este tutorial.

## Paso 2: Definir la carpeta de salida

Cree una carpeta donde se almacenarán las imágenes generadas. La ruta puede ser absoluta o relativa al ejecutable.

```csharp
// Step 2: Define the output folder
string outputPath = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputPath);
```

`Directory.CreateDirectory` garantiza que la carpeta exista, evitando errores en tiempo de ejecución cuando el método `Save` escribe el archivo.

## Paso 3: Generar el código de barras FCC 11

El formato FCC 11 es la codificación predeterminada para los códigos de barras postales de Australia Post. El siguiente código crea un código de barras que codifica la cadena numérica `1101234567`.

```csharp
// Step 3: Create a BarcodeGenerator for FCC 11
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,      // Use the Australia Post symbology
    "1101234567");                  // Data for FCC 11

// Configure visual appearance
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;   // Width of a single module
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50; // Height of the barcode

// Save as PNG
string fcc11Path = Path.Combine(outputPath, "PostalAustraliaPostFCC11.png");
barcodeGenerator.Save(fcc11Path, BarCodeImageFormat.Png);
```

**Por qué funciona:**  
* `EncodeTypes.AustraliaPost` indica a la biblioteca que aplique las reglas de codificación de Australia Post.  
* La cadena de datos `1101234567` sigue la especificación FCC 11: los dos primeros dígitos (`11`) identifican el formato, seguidos de una referencia de cliente de 7 dígitos.  
* `XDimension` y `BarHeight` controlan el tamaño del código de barras impreso, lo cual es importante para la legibilidad del escáner.  

Después de ejecutar el programa, encontrará `PostalAustraliaPostFCC11.png` en la carpeta `Barcodes`. La imagen se ve así:

![create fcc 11 barcode example](https://example.com/fcc11.png "FCC 11 barcode generated by Aspose.BarCode")

## Paso 4: Crear códigos de barras adicionales de Australia Post (opcional)

Aunque el objetivo principal es **crear un código de barras FCC 11**, a menudo necesita códigos de barras FCC 59 o FCC 62 para diferentes clases de correo. El código a continuación reutiliza la misma instancia de `BarcodeGenerator`, cambiando solo la cadena de datos y la tabla de codificación opcional.

### 4.1 FCC 59 con codificación N‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;

// Use N‑Table for customer information interpretation
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc59Path = Path.Combine(outputPath, "PostalAustraliaPostFCC59NTable.png");
barcodeGenerator.Save(fcc59Path, BarCodeImageFormat.Png);
```

### 4.2 FCC 62 con codificación N‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc62NPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62NTable.png");
barcodeGenerator.Save(fcc62NPath, BarCodeImageFormat.Png);
```

### 4.3 FCC 62 con codificación C‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.CTable;

string fcc62CPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62CTable.png");
barcodeGenerator.Save(fcc62CPath, BarCodeImageFormat.Png);
```

### 4.4 FCC 62 con codificación Other

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567321032103210"); // Long payload for "Other" table

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.Other;

string fcc62OtherPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62OtherTable.png");
barcodeGenerator.Save(fcc62OtherPath, BarCodeImageFormat.Png);
```

Las cuatro imágenes se guardan una al lado de la otra en la misma carpeta, lo que facilita comparar las diferencias visuales.

## Paso 5: Entender las tablas de codificación

Australia Post define tres tablas de codificación:

* **N‑Table** – interpreta información numérica del cliente. Úsela cuando la carga útil contenga solo dígitos.  
* **C‑Table** – admite caracteres alfanuméricos, útil para números de referencia que incluyen letras.  
* **Other** – una alternativa para formatos de datos personalizados o extendidos.  

Elegir la tabla correcta garantiza que el escáner de códigos de barras decodifique la información exactamente como se pretende. Si omite la propiedad `AustralianPostEncodingTable`, la biblioteca usa por defecto la N‑Table, lo que puede truncar caracteres no numéricos.

## Consejos, casos límite y errores comunes

| Situación | Enfoque recomendado |
|-----------|----------------------|
| La longitud de la cadena de datos es más corta de lo requerido | Rellene la parte numérica con ceros a la izquierda para cumplir con la especificación FCC. |
| El código de barras aparece borroso al imprimir | Aumente `XDimension` a 5 o 6 píxeles y verifique la configuración DPI de la impresora. |
| El escáner devuelve “formato inválido” | Verifique que la tabla de codificación correcta (N‑Table, C‑Table, Other) coincida con la carga de datos. |
| Ejecutando en Linux sin GUI | Asegúrese de que el paquete `System.Drawing.Common` esté referenciado, o use el método `Save` con `BarCodeImageFormat.Png` que no requiere un contexto de pantalla. |
| Necesita un formato de imagen diferente | Reemplace `BarCodeImageFormat.Png` por `BarCodeImageFormat.Jpeg` o `BarCodeImageFormat.Tiff` según sea necesario. |

Estos consejos prácticos provienen de implementaciones reales de soluciones de códigos de barras postales.

## Ejemplo completo ejecutable

A continuación se muestra un programa autónomo que puede copiar en un nuevo proyecto de consola (`dotnet new console`) y ejecutar sin modificaciones.



## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarle a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en sus propios proyectos.

- [Cómo generar código de barras java – Código de barras Australia Post con Aspose](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)
- [Crear codificación Databar unidimensional GS1 con Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Cómo crear zona silenciosa de código de barras .NET para Code 16K usando Aspose.BarCode](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}