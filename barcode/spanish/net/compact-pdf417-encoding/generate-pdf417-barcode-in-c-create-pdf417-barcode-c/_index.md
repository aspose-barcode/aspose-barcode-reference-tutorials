---
category: general
date: 2026-07-24
description: Genera código de barras PDF417 en C# usando Aspose.BarCode. Aprende a
  crear código de barras PDF417 en C# con modo compacto en minutos.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- create pdf417 barcode c#
- c# barcode generator pdf417
- how to generate pdf417 barcode
language: es
lastmod: 2026-07-24
og_description: Genere códigos de barras PDF417 en C# rápidamente con Aspose.BarCode.
  Este tutorial le muestra cómo crear códigos de barras PDF417 en C# en modo compacto,
  cubriendo la configuración, el código y la verificación.
og_image_alt: Screenshot of generated compact PDF417 barcode saved as PNG using C#
  code
og_title: Generar código de barras PDF417 en C# – Guía rápida
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Generate PDF417 barcode in C# using Aspose.BarCode. Learn how to create
    PDF417 barcode C# with compact mode in minutes.
  headline: Generate PDF417 Barcode in C# – Create PDF417 Barcode C#
  type: TechArticle
- description: Generate PDF417 barcode in C# using Aspose.BarCode. Learn how to create
    PDF417 barcode C# with compact mode in minutes.
  name: Generate PDF417 Barcode in C# – Create PDF417 Barcode C#
  steps:
  - name: '**Data definition** – PDF417 can store up to ~1850 characters, but we keep
      it short for the demo. Unicode support means those accented characters won’t
      break anything.'
    text: '**Data definition** – PDF417 can store up to ~1850 characters, but we keep
      it short for the demo. Unicode support means those accented characters won’t
      break anything.'
  - name: '**Generator construction** – The `EncodeTypes.Pdf417` enum value tells
      Aspose which symbology to use; swapping it for `EncodeTypes.QR` would give you
      a QR code instead.'
    text: '**Generator construction** – The `EncodeTypes.Pdf417` enum value tells
      Aspose which symbology to use; swapping it for `EncodeTypes.QR` would give you
      a QR code instead.'
  - name: '**X‑dimension** – This controls the width of each module (the tiny squares
      that make up the barcode). A value of `2` pixels yields a crisp image that’s
      still readable when printed at 300 dpi.'
    text: '**X‑dimension** – This controls the width of each module (the tiny squares
      that make up the barcode). A value of `2` pixels yields a crisp image that’s
      still readable when printed at 300 dpi.'
  - name: '**PDF417 options** – `Columns` influences the barcode’s aspect ratio; fewer
      columns make the image taller, which can be useful for receipts. `Truncate`
      (also called *Compact mode*) removes the start/stop pattern padding, reducing
      file size without sacrificing data integrity.'
    text: '**PDF417 options** – `Columns` influences the barcode’s aspect ratio; fewer
      columns make the image taller, which can be useful for receipts. `Truncate`
      (also called *Compact mode*) removes the start/stop pattern padding, reducing
      file size without sacrificing data integrity.'
  - name: '**Output path** – Using `Environment.CurrentDirectory` ensures the image
      lands next to the executable, making it easy to locate during development.'
    text: '**Output path** – Using `Environment.CurrentDirectory` ensures the image
      lands next to the executable, making it easy to locate during development.'
  - name: '**Saving** – `BarCodeImageFormat.Png` gives lossless quality, perfect for
      further processing or embedding in PDFs.'
    text: '**Saving** – `BarCodeImageFormat.Png` gives lossless quality, perfect for
      further processing or embedding in PDFs.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Generar código de barras PDF417 en C# – Crear código de barras PDF417 en C#
url: /es/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generar código de barras PDF417 en C# – Guía completa de programación

¿Alguna vez te has preguntado cómo **generar códigos de barras PDF417** en una aplicación C# sin tener que buscar en interminables hilos de foros? No eres el único. Ya sea que estés construyendo un sistema de tickets, una tarjeta de identificación segura, o simplemente necesites una forma rápida de incrustar datos en un formato imprimible, dominar el formato PDF417 puede ahorrarte horas de prueba y error.

En esta guía recorreremos un **ejemplo completo y listo‑para‑ejecutar** que te muestra exactamente cómo **crear códigos de barras PDF417 en C#** usando la popular biblioteca Aspose.BarCode. Cubriremos todo, desde la instalación del paquete NuGet hasta el ajuste del modo compacto, para que puedas copiar‑pegar el código y ver resultados al instante.

## Lo que aprenderás

- Cómo configurar la biblioteca Aspose.BarCode en un proyecto .NET.  
- Las declaraciones exactas de C# necesarias para **generar códigos de barras PDF417** con texto personalizado, tamaño de módulo y número de columnas.  
- Por qué activar la opción *Compact* (Truncate) es importante para datos densos.  
- Formas de guardar el código de barras como PNG y verificar la salida.  

No se requiere experiencia previa con códigos de barras; solo una comprensión básica de C# y Visual Studio (o cualquier IDE que prefieras). Al final tendrás un método reutilizable que puedes incorporar en cualquier proyecto que necesite una imagen PDF417.

## Requisitos previos

| Requisito | Por qué es importante |
|-------------|----------------|
| .NET 6.0 o posterior (o .NET Framework 4.7+) | Aspose.BarCode es compatible con ambos; los entornos de ejecución más recientes ofrecen mejor rendimiento. |
| Visual Studio 2022 (o VS Code con extensiones C#) | Proporciona IntelliSense y depuración sencilla. |
| Conexión a Internet (para la primera restauración de NuGet) | La biblioteca se descarga de NuGet.org. |
| Conocimientos básicos de C# | Necesario para entender la estructura de clases y llamadas a métodos. |

Si ya los tienes, genial—¡vamos a sumergirnos!

## Instalar el paquete NuGet Aspose.BarCode

Abre la carpeta de tu proyecto en una terminal y ejecuta:

```bash
dotnet add package Aspose.BarCode
```

O, dentro de Visual Studio, haz clic derecho en **Dependencies → Manage NuGet Packages**, busca *Aspose.BarCode* y haz clic en **Install**. Esta única línea incorpora todos los tipos que utilizaremos, incluyendo `BarcodeGenerator`, `EncodeTypes` y `BarCodeImageFormat`.

> **Consejo profesional:** Después de la instalación, limpia y recompila la solución para asegurarte de que el ensamblado está referenciado correctamente.

## Generar código de barras PDF417 – Configuración y dependencias

Lo primero: necesitamos un bloque `using` que importe los espacios de nombres relevantes.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Estos espacios de nombres nos dan acceso a la clase generadora y a la enumeración de tipos de códigos de barras. Nada complicado—solo tres líneas, y estamos listos para comenzar a crear el código de barras.

## Crear código de barras PDF417 en C# – Implementación paso a paso

A continuación hay un **programa de consola autónomo** que crea un código de barras PDF417 compacto a partir de la cadena `"Åspóse.Barcóde©"` y lo guarda como `CompactPdf417.png`. Siéntete libre de reemplazar el texto con lo que necesites; el generador manejará los caracteres Unicode sin problemas.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Define the data you want to encode.
            string data = "Åspóse.Barcóde©";

            // 2️⃣ Initialise the generator for PDF417.
            //    EncodeTypes.Pdf417 tells Aspose we want a PDF417 barcode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // 3️⃣ Adjust the module (X‑dimension) size.
            //    Smaller values give a tighter image; 2 pixels works well for most screens.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Configure PDF417‑specific options.
            //    • Columns = 3 → fewer columns, taller barcode.
            //    • Truncate = true → enables Compact mode, which removes unnecessary padding.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Choose the output folder – adjust as needed.
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "CompactPdf417.png");

            // 6️⃣ Save the image as PNG.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ PDF417 barcode saved to: {outputPath}");
        }
    }
}
```

### Por qué cada paso es importante

1. **Definición de datos** – PDF417 puede almacenar hasta ~1850 caracteres, pero lo mantenemos corto para la demostración. El soporte Unicode significa que esos caracteres acentuados no romperán nada.  
2. **Construcción del generador** – El valor de enumeración `EncodeTypes.Pdf417` indica a Aspose qué simbología usar; cambiarlo por `EncodeTypes.QR` generaría un código QR en su lugar.  
3. **X‑dimensión** – Controla el ancho de cada módulo (los pequeños cuadrados que forman el código de barras). Un valor de `2` píxeles produce una imagen nítida que sigue siendo legible al imprimirse a 300 dpi.  
4. **Opciones de PDF417** – `Columns` influye en la relación de aspecto del código de barras; menos columnas hacen la imagen más alta, lo que puede ser útil para recibos. `Truncate` (también llamado *modo compacto*) elimina el relleno del patrón de inicio/fin, reduciendo el tamaño del archivo sin sacrificar la integridad de los datos.  
5. **Ruta de salida** – Usar `Environment.CurrentDirectory` garantiza que la imagen se guarde junto al ejecutable, facilitando su ubicación durante el desarrollo.  
6. **Guardado** – `BarCodeImageFormat.Png` ofrece calidad sin pérdidas, perfecta para procesamiento adicional o incrustación en PDFs.  

Ejecuta el programa (`dotnet run` o presiona **F5** en Visual Studio). Después de unos segundos deberías ver un mensaje en la consola confirmando la ubicación del archivo, y el PNG aparecerá en la carpeta de tu proyecto.

![Ejemplo de generación de código de barras PDF417](generated-pdf417.png)

*Texto alternativo de la imagen: ejemplo de generación de código de barras pdf417 – Imagen PNG de un código de barras PDF417 compacto creado con C#.*

## Configurar el modo compacto – Opciones del generador de códigos de barras PDF417 en C#

Si necesitas un código de barras más grande (quizás para escanear a distancia), ajusta las propiedades `Columns` y `Rows`. Aquí tienes un fragmento rápido que muestra configuraciones alternativas:

```csharp
// Increase columns for a wider, shorter barcode.
generator.Parameters.Barcode.Pdf417.Columns = 6;

// Disable Compact mode if the scanning hardware struggles with it.
generator.Parameters.Barcode.Pdf417.Truncate = false;

// Optionally set error correction level (0–8). Higher values increase redundancy.
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;
```

> **Pregunta frecuente:** *¿Desactivar Truncate romperá los escáneres existentes?*  
> Normalmente no. La mayoría de los escáneres modernos entienden tanto PDF417 de tamaño completo como compacto. Sin embargo, si apuntas a hardware heredado, deja `Truncate` en `false`.

## Guardar y verificar – cómo generar la salida del código de barras pdf417

Después de guardar, puedes abrir el PNG con cualquier visor de imágenes. Para verificar que el código de barras codifica los datos previstos, usa `BarCodeReader` de Aspose:



## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo crear códigos de barras – PDF417 compacto con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cómo generar código de barras Aztec con relación de aspecto personalizada usando Aspose.BarCode para .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [biblioteca de códigos de barras java – Añadir código de barras a PDF usando Aspose](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}