---
category: general
date: 2026-10-24
description: Aprende cómo generar códigos de barras PDF417 usando Aspose.BarCode en
  C# con configuraciones compactas y control de XDimension del código de barras.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode
- compact PDF417
- barcode XDimension
- PDF417 columns
language: es
lastmod: 2026-10-24
og_description: Genera códigos de barras PDF417 en C# con Aspose.BarCode. Sigue esta
  guía completa para crear imágenes PDF417 compactas, controlar XDimension y establecer
  columnas.
og_image_alt: Screenshot of generated PDF417 barcode using Aspose.BarCode
og_title: Generar código de barras PDF417 con Aspose.BarCode – paso a paso en C#
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  headline: How to generate PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  name: How to generate PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: 1. Changing the image format
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 2. Encoding large amounts of data
    text: 'PDF417 can store up to ~1.1 KB of text. When the payload exceeds the capacity
      of three columns, the library automatically adds rows. To keep the barcode compact,
      you can:'
  - name: 3. Using a license to remove the trial watermark
    text: '```csharp Aspose.BarCode.License license = new Aspose.BarCode.License();
      license.SetLicense("Aspose.BarCode.lic"); ```'
  - name: 4. Handling exceptions
    text: '```csharp try { generator.Save(outputPath, BarCodeImageFormat.Png); } catch
      (Exception ex) { Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
      } ```'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- PDF417
- C#
title: Cómo generar un código de barras PDF417 con Aspose.BarCode en C#
url: /es/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo generar código de barras PDF417 con Aspose.BarCode en C#

Si necesita **generar código de barras PDF417** en una aplicación .NET, esta guía le muestra una solución completa, lista‑para‑ejecutar. Verá cómo Aspose.BarCode hace que el proceso sea sencillo mientras le brinda un control granular sobre **PDF417 compacto**, **XDimension del código de barras** y **columnas PDF417**.

Crear un código de barras es un requisito común para sistemas de inventario, plataformas de tickets y flujos de trabajo de documentos. Al final de este tutorial tendrá un programa C# autónomo que produce una imagen PNG nítida de un código de barras PDF417, lista para incrustarse en cualquier interfaz de usuario o imprimirse en una etiqueta.

## Lo que necesitará

- .NET 6.0 SDK o posterior (el código también funciona con .NET Framework 4.6+)
- Visual Studio 2022 o cualquier editor de C# que prefiera
- Una licencia válida de Aspose.BarCode para .NET (la prueba gratuita funciona para desarrollo)
- Familiaridad básica con la sintaxis de C#

> **Consejo profesional:** Si está evaluando Aspose.BarCode, descargue la versión de prueba del sitio oficial y añada el paquete NuGet `Aspose.BarCode` a su proyecto. La versión de prueba agrega una pequeña marca de agua a la imagen generada, que desaparece una vez que aplique una licencia.

## Paso 1: Instalar el paquete NuGet Aspose.BarCode

Abra una terminal en la carpeta de su solución y ejecute:

```bash
dotnet add package Aspose.BarCode
```

El comando descarga la última versión estable (a partir de octubre 2026, versión 23.12). Añadir el paquete restaura el espacio de nombres `Aspose.BarCode.Generation` que usará para **generar imágenes de código de barras PDF417**.

## Paso 2: Crear un proyecto de consola C# básico

Si aún no tiene un proyecto, cree uno:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

Abra `Program.cs`. El esqueleto ya contiene un método `Main` donde colocaremos el código de generación del código de barras.

## Paso 3: Inicializar el generador de códigos de barras

Primero, importe el espacio de nombres requerido:

```csharp
using Aspose.BarCode.Generation;
```

Luego, dentro de `Main`, instancie `BarcodeGenerator` con la simbología PDF417 y los datos que desea codificar:

```csharp
// Step 3: Initialize the generator for a PDF417 barcode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

La cadena incluye caracteres Unicode para demostrar que Aspose.BarCode maneja correctamente la entrada no ASCII. Si solo necesita ASCII, reemplace el texto por cualquier cadena simple.

## Paso 4: Ajustar la XDimension del código de barras (tamaño del módulo)

La **XDimension del código de barras** determina el ancho del módulo más pequeño (la barra). Configurarla en píxeles le brinda un control pixel‑perfecto sobre el tamaño final de la imagen:

```csharp
// Step 4: Set the module size – XDimension in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Un valor de `2` píxeles produce una imagen compacta sin sacrificar la fiabilidad del escaneo. Aumente el valor para códigos de barras más grandes o disminúyalo para diseños muy densos.

## Paso 5: Configurar opciones de PDF417 compacto

Dos configuraciones específicas de PDF417 afectan drásticamente la huella visual:

| Configuración | Significado | Valor típico para salida compacta |
|---------------|-------------|-----------------------------------|
| `Columns` | Número de columnas de datos | `3` |
| `Truncate` (modo compacto) | Omite la zona silenciosa derecha y reduce el número de filas | `true` |

Aplíquelas de la siguiente manera:

```csharp
// Step 5: Use a small number of columns and enable compact mode
generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417
```

Usar **columnas PDF417** establecidas en `3` junto con `Truncate = true` crea un código de barras *PDF417 compacto* que cabe perfectamente en una etiqueta estándar y sigue siendo legible por la mayoría de los escáneres.

## Paso 6: Guardar la imagen del código de barras

Finalmente, escriba el código de barras en disco. El ejemplo guarda un PNG, pero Aspose.BarCode también admite BMP, JPEG, GIF, TIFF y SVG:

```csharp
// Step 6: Save the barcode as a PNG file
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

La constante `BarCodeImageFormat.Png` indica a la biblioteca que produzca un PNG sin pérdida, lo cual es ideal para procesamiento posterior o impresión.

## Código fuente completo y ejecutable

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator for PDF417 with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size – barcode XDimension in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Configure compact PDF417 options
        generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
        generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417

        // 4️⃣ Save as PNG
        string outputPath = Path.Combine(
            Environment.CurrentDirectory,
            "CompactPdf417.png");

        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

Ejecutar el programa genera `CompactPdf417.png` en la carpeta raíz del proyecto. Abra el archivo con cualquier visor de imágenes; verá un código de barras PDF417 densamente empaquetado que codifica la cadena *Åspóse.Barcóde©*.

![Captura de pantalla del código de barras PDF417 generado con Aspose.BarCode](placeholder-image.png "Código de barras PDF417 generado")

*Texto alternativo de la imagen: Captura de pantalla del código de barras PDF417 generado con Aspose.BarCode* – este texto alternativo contiene la palabra clave principal para accesibilidad y SEO.

## Verificando el resultado

1. Abra el archivo PNG. El código de barras debe consistir en tres columnas de datos verticales con un diseño compacto (sin zonas silenciosas adicionales en el lado derecho).
2. Escanee la imagen con un escáner de códigos de barras de smartphone que admita PDF417. El texto decodificado debe coincidir con la cadena de entrada original.
3. Si el escáner falla, intente aumentar `XDimension.Pixels` a `3` o `4`. Los módulos más grandes mejoran la legibilidad en dispositivos de baja resolución.

## Variaciones comunes y casos límite

### 1. Cambiar el formato de imagen

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

SVG es basado en vectores, lo que mantiene el código de barras nítido a cualquier nivel de zoom—útil para páginas web.

### 2. Codificar grandes cantidades de datos

PDF417 puede almacenar hasta ~1,1 KB de texto. Cuando la carga útil supera la capacidad de tres columnas, la biblioteca agrega filas automáticamente. Para mantener el código de barras compacto, puede:

- Reducir la longitud de los datos (p. ej., usar un identificador en lugar de un mensaje completo)
- Aumentar el número de **columnas PDF417** (p. ej., `generator.Parameters.Barcode.Pdf417.Columns = 5;`)

### 3. Usar una licencia para eliminar la marca de agua de prueba

```csharp
Aspose.BarCode.License license = new Aspose.BarCode.License();
license.SetLicense("Aspose.BarCode.lic");
```

Coloque el archivo de licencia junto al ejecutable. Después de aplicar la licencia, la imagen generada no contiene marca de agua.

### 4. Manejo de excepciones

```csharp
try
{
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

Los fallos típicos incluyen permisos de escritura insuficientes o un formato de imagen no compatible.

## Por qué importan los ajustes

- **XDimension del código de barras** – Controla el peso visual de cada barra. Si es demasiado pequeña, el código de barras es ilegible; si es demasiado grande, desperdicia espacio.
- **columnas PDF417** – Menos columnas producen un código de barras más estrecho pero aumentan el número de filas


## ¿Qué debería aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarle a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en sus propios proyectos.

- [Cómo generar código de barras PDF417 con Aspose – Guía completa](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Generar código de barras PDF417 con configuraciones compactas en C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-with-compact-settings-in-c/)
- [Cómo guardar el código de barras y generar PDF417 con Aspose en C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}