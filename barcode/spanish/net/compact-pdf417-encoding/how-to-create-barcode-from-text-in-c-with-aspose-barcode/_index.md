---
category: general
date: 2026-10-02
description: Crear código de barras a partir de texto en C# usando Aspose.BarCode.
  Aprende cómo generar un código de barras PDF417 y descubre cómo generar un código
  de barras PDF417 en modo compacto.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate pdf417 barcode
- how to generate pdf417 barcode
language: es
lastmod: 2026-10-02
og_description: Crea códigos de barras a partir de texto en C# con Aspose.BarCode.
  Esta guía muestra cómo generar códigos de barras PDF417 y cómo generar códigos de
  barras PDF417 en modo compacto.
og_image_alt: Screenshot showing create barcode from text output as a PNG image
og_title: Crear código de barras a partir de texto en C# – guía paso a paso
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  headline: How to create barcode from text in C# with Aspose.BarCode
  type: TechArticle
- description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  name: How to create barcode from text in C# with Aspose.BarCode
  steps:
  - name: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
    text: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
  - name: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
    text: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
  - name: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
    text: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Cómo crear un código de barras a partir de texto en C# con Aspose.BarCode
url: /es/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un código de barras a partir de texto en C# con Aspose.BarCode

Si necesitas **crear un código de barras a partir de texto** en una aplicación .NET, esta guía te lleva paso a paso por todo el proceso. Verás un ejemplo listo‑para‑ejecutar que **genera un código de barras PDF417** y también responde a **cómo generar un código de barras PDF417** en un diseño compacto.

Generar un código de barras programáticamente elimina pasos manuales y garantiza consistencia en todos los documentos. Al final de este tutorial tendrás un archivo PNG que contiene un código de barras PDF417 que podrás incrustar en facturas, tickets o tarjetas de identificación.

## Lo que necesitarás

- .NET 6.0 SDK o posterior (el código también funciona con .NET Framework 4.7.2+)
- Visual Studio 2022 o cualquier editor que soporte C#
- Una licencia NuGet para **Aspose.BarCode for .NET** (una prueba gratuita sirve para pruebas)

> **Consejo pro:** Añade el paquete NuGet vía la CLI para mantener el proyecto limpio:  
> `dotnet add package Aspose.BarCode`

## Paso 1: Configurar un proyecto de consola

Crea una nueva aplicación de consola y referencia la biblioteca Aspose.BarCode.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

El comando `dotnet new console` genera un archivo `Program.cs` que reemplazaremos con el ejemplo completo a continuación.

## Paso 2: Cómo crear un código de barras a partir de texto – código principal

Abre `Program.cs` y reemplaza su contenido con el siguiente código. Cada línea está comentada para explicar por qué existe.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Image;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Define the text that will be encoded.
            // The PDF417 symbology supports a wide range of Unicode characters.
            string textToEncode = "Åspóse.Barcóde©";

            // 2️⃣ Create a BarcodeGenerator for PDF417 using the desired text.
            // This object holds all settings and performs the rendering.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, textToEncode);

            // 3️⃣ Adjust module (X) dimension for better readability on screen.
            // XDimension defines the width of a single barcode column in pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Set the number of columns – a smaller column count yields a denser image.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 5️⃣ Enable compact mode by truncating the data.
            // Truncate = true removes padding, making the barcode smaller while preserving scannability.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 6️⃣ Choose the output path. Adjust the folder to match your environment.
            string outputPath = "CompactPdf417.png";

            // 7️⃣ Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Por qué cada configuración es importante

| Configuración | Propósito |
|---------------|-----------|
| `EncodeTypes.Pdf417` | Selecciona la simbología PDF417, que puede almacenar grandes cantidades de datos en una matriz bidimensional. |
| `XDimension.Pixels = 2` | Controla el ancho de cada módulo; un valor de 2 píxeles equilibra la legibilidad y el tamaño del archivo. |
| `Pdf417.Columns = 3` | Reduce el número de columnas, haciendo el código de barras más compacto sin perder datos. |
| `Pdf417.Truncate = true` | Activa el modo compacto, eliminando el relleno innecesario y acortando el código de barras. |
| `BarCodeImageFormat.Png` | PNG conserva calidad sin pérdidas, ideal para procesamiento adicional o impresión. |

## Paso 3: Generar código de barras PDF417 – ejecutando el ejemplo

Compila y ejecuta el proyecto:

```bash
dotnet run
```

Cuando la ejecución finalice verás:

```
Barcode saved to CompactPdf417.png
```

Abre `CompactPdf417.png` para ver el resultado. La imagen contiene un código de barras PDF417 que codifica la cadena **Åspóse.Barcóde©**.

![Crear código de barras a partir de texto ejemplo](barcode-example.png)

*Texto alternativo: crear código de barras a partir de texto – código de barras PDF417 guardado como PNG*

## Paso 4: Cómo generar código de barras PDF417 con corrección de errores personalizada (opcional)

Si tu entorno de escaneo es ruidoso, puedes aumentar el nivel de corrección de errores:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // Levels 0–5, higher = more redundancy
```

Incrementar el nivel de error hace que el código de barras sea más grande, pero mejora la resistencia frente a daños.

## Paso 5: Problemas comunes y manejo de casos límite

1. **Caracteres inválidos** – PDF417 soporta Unicode, pero algunos escáneres antiguos pueden rechazar símbolos no ASCII. Prueba con tu hardware objetivo.  
2. **Permisos de ruta de archivo** – Asegúrate de que el directorio donde escribes sea escribible; de lo contrario `Save` lanza una `UnauthorizedAccessException`.  
3. **Tamaño de imagen** – Valores muy altos de `XDimension` generan archivos PNG grandes. Mantén el tamaño de píxel entre 1 y 4 para la mayoría de escenarios de visualización en pantalla.

## Recapitulación

Ahora sabes cómo **crear un código de barras a partir de texto** en C# usando Aspose.BarCode, cómo **generar un código de barras PDF417** con un diseño compacto, y los pasos exactos para **cómo generar un código de barras PDF417** con configuraciones personalizadas. El código completo y ejecutable anterior puede copiarse a cualquier proyecto .NET y adaptarse a diferentes entradas de texto o formatos de salida (p. ej., JPEG, BMP).

## Próximos pasos

- Explora otras simbologías como QR Code o Code128 cambiando `EncodeTypes`.  
- Integra el PNG generado en un PDF usando Aspose.PDF para creación de documentos de extremo a extremo.  
- Experimenta con `generator.Parameters.Barcode.Pdf417.Rows` para controlar la densidad vertical.

Siéntete libre de modificar el ejemplo, incrustar el código de barras en tus propias aplicaciones y compartir tus resultados con la comunidad. ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo generar código de barras PDF417 en C# – ejemplo compacto](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-compact-example/)
- [Cómo crear código de barras PDF417 en C# con modo compacto](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [Cómo generar código de barras PDF417 en C# – guía paso a paso](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}