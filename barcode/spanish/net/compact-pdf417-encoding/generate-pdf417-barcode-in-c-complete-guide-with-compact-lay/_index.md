---
category: general
date: 2026-08-19
description: Genere códigos de barras PDF417 en C# rápidamente. Aprenda cómo generar
  códigos de barras PDF417 en C# usando Aspose.BarCode con modo compacto y configuraciones
  personalizadas.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode c#
- Aspose.BarCode PDF417
- compact PDF417 barcode
- barcode X‑dimension
language: es
lastmod: 2026-08-19
og_description: Genere códigos de barras PDF417 en C# con Aspose.BarCode. Este tutorial
  muestra cómo generar códigos de barras PDF417 en C# en modo compacto, establecer
  la dimensión X y guardarlos como PNG.
og_image_alt: Screenshot of a compact PDF417 barcode saved as PNG
og_title: Generar código de barras PDF417 en C# – guía paso a paso
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  headline: Generate PDF417 barcode in C# – complete guide with compact layout
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  name: Generate PDF417 barcode in C# – complete guide with compact layout
  steps:
  - name: Why each line matters
    text: '* **`EncodeTypes.Pdf417`** – selects the PDF417 symbology, which supports
      up to ~1.1 KB of data. * **`XDimension.Pixels = 2`** – sets the basic bar width.
      Smaller values make the barcode thinner; larger values improve readability on
      low‑resolution devices. * **`Pdf417.Columns = 3`** – limits the num'
  - name: 4️⃣ Generate a high‑density PDF417 for printing
    text: 'If you need a barcode that fits on a small label, increase the column count
      and lower the X‑dimension:'
  - name: 5️⃣ Change the output format to SVG for vector scaling
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 6️⃣ Encode binary data (e.g., a byte array)
    text: 'If you need to embed binary payloads, convert them to a Base64 string first:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Generar código de barras PDF417 en C# – guía completa con diseño compacto
url: /es/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide-with-compact-lay/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generar código de barras PDF417 en C# – guía completa

Si necesitas **generar un código de barras PDF417** en una aplicación .NET, este tutorial te muestra exactamente cómo hacerlo. Verás un ejemplo conciso, listo para producción, que crea un código de barras PDF417 compacto, personaliza la dimensión X y guarda el resultado como una imagen PNG.

Generar un código de barras PDF417 es común cuando tienes que codificar grandes cantidades de datos —como información de tickets, manifiestos de envío o documentos de identidad— en un formato legible por máquinas. Usar Aspose.BarCode hace que el proceso sea sencillo, y el código funciona con .NET 6+ o .NET Framework 4.7.2 y posteriores.

En esta guía aprenderás a:

* Instalar el paquete NuGet Aspose.BarCode.
* Escribir un programa C# autónomo que **genere un código de barras PDF417** con un número reducido de columnas y modo compacto (truncado).
* Ajustar el ancho de barra (dimensión X) para una renderización más nítida.
* Guardar el código de barras como un archivo PNG.
* Explorar variaciones, casos límite y consejos de buenas prácticas.

## Requisitos previos

Antes de comenzar, asegúrate de contar con:

* Visual Studio 2022 (o cualquier IDE de C#) con el SDK de .NET 6 instalado.
* Acceso a Internet para descargar el paquete NuGet **Aspose.BarCode**.
* Permiso de escritura en una carpeta donde se guardará el archivo PNG.

No se requieren bibliotecas adicionales; Aspose.BarCode maneja la codificación de imágenes internamente.

## Paso 1: Añadir el paquete Aspose.BarCode

Abre tu proyecto en Visual Studio, haz clic derecho en la solución y selecciona **Manage NuGet Packages**. Busca `Aspose.BarCode` e instala la versión estable más reciente.

```bash
dotnet add package Aspose.BarCode
```

> **Consejo profesional:** Mantén el paquete actualizado. Las nuevas versiones suelen incluir mejoras de rendimiento y soporte para los últimos runtimes de .NET.

## Paso 2: Crear una aplicación de consola mínima

Crea un nuevo proyecto de consola C# si aún no tienes uno:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

Reemplaza el contenido de `Program.cs` con el ejemplo completo a continuación. Este programa demuestra **cómo generar un código de barras PDF417 en C#** de principio a fin.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Define the data you want to encode.
            // -----------------------------------------------------------------
            // The string can contain Unicode characters; Aspose.BarCode handles
            // encoding automatically. Here we use characters with diacritics to
            // prove Unicode support.
            string data = "Åspóse.Barcóde©";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarcodeGenerator for PDF417.
            // -----------------------------------------------------------------
            // EncodeTypes.Pdf417 tells the library which symbology to use.
            // The constructor also accepts the data to encode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // -----------------------------------------------------------------
            // 3️⃣  Configure visual parameters.
            // -----------------------------------------------------------------
            // • XDimension controls the bar width in pixels. A value of 2 gives
            //   a clear, readable barcode on most screens.
            // • Columns define how many data columns the barcode will use.
            //   Fewer columns produce a more compact image but increase the
            //   number of rows.
            // • Truncate enables “compact mode”, which removes the trailing
            //   stop pattern and reduces the overall size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true; // compact mode

            // -----------------------------------------------------------------
            // 4️⃣  Choose the output format and save the image.
            // -----------------------------------------------------------------
            // BarCodeImageFormat.Png yields a lossless PNG file that works
            // well for web, print, and further image processing.
            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to: {outputPath}");
        }
    }
}
```

### Por qué cada línea es importante

* **`EncodeTypes.Pdf417`** – selecciona la simbología PDF417, que soporta hasta ~1.1 KB de datos.
* **`XDimension.Pixels = 2`** – establece el ancho básico de la barra. Valores más pequeños hacen el código de barras más delgado; valores mayores mejoran la legibilidad en dispositivos de baja resolución.
* **`Pdf417.Columns = 3`** – limita el número de columnas, obligando al generador a usar más filas, lo que resulta en un código de barras más alto pero más estrecho.
* **`Pdf417.Truncate = true`** – activa el modo compacto, eliminando el patrón de parada y reduciendo la imagen sin perder la integridad de los datos.
* **`Save(..., BarCodeImageFormat.Png)`** – escribe un archivo PNG. También podrías elegir `Jpeg`, `Bmp` o `Svg` según las necesidades posteriores.

Ejecuta el programa:

```bash
dotnet run
```

Deberías ver en la consola la salida que confirma la ubicación del archivo, y la carpeta contendrá `CompactPdf417.png`. Al abrir el PNG verás un código de barras PDF417 claro y compacto que codifica la cadena Unicode.

## Paso 3: Verificar el código de barras (opcional pero recomendado)

Para asegurarte de que el código de barras sea legible, puedes usar cualquier aplicación escáner de PDF417 estándar en un smartphone o una biblioteca decodificadora de escritorio. El texto codificado debe coincidir exactamente con la cadena original `data`, incluidos los caracteres especiales.

Si encuentras problemas de decodificación:

* Aumenta `XDimension` a 3 o 4 píxeles.
* Reduce el número de columnas (p. ej., establece `Columns = 2`).
* Desactiva `Truncate` (`Truncate = false`) para añadir el patrón de parada.

Estos ajustes intercambian tamaño por legibilidad, lo cual es útil para impresoras o escáneres de baja resolución.

## Paso 4: Explorar variaciones comunes

### 4️⃣ Generar un PDF417 de alta densidad para impresión

Si necesitas un código de barras que quepa en una etiqueta pequeña, incrementa el número de columnas y disminuye la dimensión X:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 1;
generator.Parameters.Barcode.Pdf417.Columns = 6;
generator.Parameters.Barcode.Pdf417.Truncate = false; // keep full pattern
```

### 5️⃣ Cambiar el formato de salida a SVG para escalado vectorial

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

La salida SVG se escala sin pérdida de calidad, perfecta para páginas web responsivas.

### 6️⃣ Codificar datos binarios (p. ej., un arreglo de bytes)

Si necesitas incrustar cargas binarias, conviértelos primero a una cadena Base64:

```csharp
byte[] payload = new byte[] { 0x01, 0xFF, 0xA5 };
string base64 = Convert.ToBase64String(payload);
generator = new BarcodeGenerator(EncodeTypes.Pdf417, base64);
```

Ahora el código de barras transporta la información binaria, y el decodificador debe revertir el paso Base64.

## Preguntas frecuentes

| Pregunta | Respuesta |
|----------|-----------|
| **¿Puedo generar PDF417 sin Aspose?** | Sí, existen otras bibliotecas como ZXing.Net o Dynamsoft, pero Aspose.BarCode ofrece un control de diseño más rico (columnas, truncado) y mejor manejo de Unicode. |
| **¿Cuál es la longitud máxima de datos?** | PDF417 puede codificar hasta 1 108 bytes (≈ 1 KB) de datos binarios. Si superas este límite, considera dividir los datos en varios códigos de barras. |
| **¿El modo compacto cumple con los estándares?** | El PDF417 truncado forma parte de la especificación ISO/IEC 15438 y es ampliamente soportado, pero verifica que tu escáner objetivo lo admita explícitamente. |
| **¿Cómo cambio el color de fondo?** | Establece `generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;` y `generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;` antes de guardar. |

## Conclusión

Ahora sabes **cómo generar un código de barras PDF417 en C#** usando Aspose.BarCode, cómo afinar la dimensión X, habilitar el modo compacto y exportar el resultado como una imagen PNG. El ejemplo completo y ejecutable puede copiarse a cualquier proyecto .NET, y las variaciones mostradas te permiten adaptar el código de barras para impresión, web o escenarios de carga binaria.

Próximos pasos que podrías explorar:

* Integrar la generación de códigos de barras en una API ASP.NET Core que devuelva la imagen bajo demanda.
* Combinar PDF417 con códigos QR en la misma etiqueta para escaneo dual.
* Utilizar la clase `Reader` de Aspose.BarCode para decodificar la imagen generada y verificar los datos programáticamente.

¡Feliz codificación y disfruta de la flexibilidad que aportan las soluciones para **generar códigos de barras PDF417** en tus aplicaciones!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate Barcode Image with Supplemental Space Customization using Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}