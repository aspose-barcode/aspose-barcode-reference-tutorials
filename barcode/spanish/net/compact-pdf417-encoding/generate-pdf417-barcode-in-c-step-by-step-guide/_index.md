---
category: general
date: 2026-08-09
description: Genera códigos de barras PDF417 en C# rápidamente. Aprende cómo generar
  PDF417 con modo compacto, control de columnas y salida PNG usando la API BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- create pdf417 barcode c#
- barcode generator c#
- compact pdf417 settings
- pdf417 png output
language: es
lastmod: 2026-08-09
og_description: Genera código de barras PDF417 en C# con un ejemplo conciso. Esta
  guía muestra cómo configurar el modo compacto, establecer columnas y guardar el
  resultado como una imagen PNG.
og_image_alt: Generated PDF417 barcode image saved as PNG
og_title: Generar código de barras PDF417 en C# – tutorial completo
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    with compact mode, column control, and PNG output using the BarcodeGenerator API.
  headline: Generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- C#
- Aspose.BarCode
title: Generar código de barras PDF417 en C# – guía paso a paso
url: /es/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generar código de barras PDF417 en C# – guía paso a paso

Si necesitas **generar un código de barras PDF417** en una aplicación .NET, este tutorial te muestra exactamente cómo hacerlo. Verás un programa completo y ejecutable que crea un código de barras PDF417 compacto, personaliza su tamaño y guarda la imagen como un archivo PNG.

Generar un código de barras PDF417 es un requisito común para la emisión de tickets móviles, el seguimiento de inventario y la seguridad de documentos. Esta guía cubre las opciones de configuración esenciales, explica por qué cada ajuste es importante y ofrece consejos prácticos para su uso en entornos reales.

## Prerrequisitos

Antes de comenzar, asegúrate de tener:

* SDK de .NET 6.0 o posterior instalado  
* Un IDE de C# como Visual Studio 2022 o Visual Studio Code  
* El paquete **Aspose.BarCode for .NET** de NuGet (versión 23.10 o más reciente)  

Puedes instalar el paquete con el siguiente comando CLI:

```bash
dotnet add package Aspose.BarCode
```

El código a continuación asume que el paquete está referenciado y que tienes permiso de escritura en el directorio de salida.

## Paso 1: Configurar el proyecto e importar espacios de nombres

Crea un nuevo proyecto de consola y agrega las directivas `using` requeridas. Estos espacios de nombres exponen la clase `BarcodeGenerator` y la enumeración de formatos de imagen.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;
```

**Por qué es importante:** Importar los espacios de nombres correctos garantiza que el compilador pueda localizar el tipo `BarcodeGenerator` y la enumeración `BarCodeImageFormat`. La falta de un espacio de nombres produce un error de compilación, lo que detiene el proceso de generación del código de barras.

## Paso 2: Inicializar el `BarcodeGenerator` con codificación PDF417

El constructor de `BarcodeGenerator` recibe dos argumentos: la simbología del código de barras (`EncodeTypes.Pdf417`) y el texto que deseas codificar. PDF417 admite una amplia gama de caracteres, incluidos símbolos Unicode.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

**Explicación:**  
* `EncodeTypes.Pdf417` indica a la biblioteca que use el estándar PDF417.  
* El texto de ejemplo contiene caracteres acentuados y un símbolo de copyright para demostrar el manejo de Unicode.  

Si solo necesitas codificar datos numéricos, puedes pasar una cadena simple como `"1234567890"`.

## Paso 3: Ajustar la dimensión X para mayor resolución

La dimensión X controla el ancho de un solo módulo del código de barras (el elemento negro o blanco más pequeño). Establecer un valor de píxel menor produce una imagen de mayor resolución.

```csharp
// Step 3: Adjust the module (X) dimension for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**¿Por qué ajustarla?** Una dimensión X predeterminada de 3–4 píxeles puede generar un código de barras que se ve grueso en pantallas de alta DPI. Reducirla a **2 píxeles** equilibra la legibilidad con el tamaño del archivo, especialmente cuando activas el modo compacto.

## Paso 4: Configurar el número de columnas

PDF417 permite especificar cuántas columnas debe contener el código de barras. Menos columnas hacen que el código sea más estrecho pero más alto, mientras que más columnas crean un código más ancho y corto.

```csharp
// Step 4: Set the number of columns to control the barcode width
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

**Consejo práctico:** Para tickets móviles que deben caber en una etiqueta estrecha, un recuento de columnas de **3–5** funciona bien. Incrementa el recuento si tienes muchos datos y deseas un código de barras más corto.

## Paso 5: Habilitar el modo compacto para truncar filas vacías

El modo compacto elimina filas innecesarias de la matriz del código de barras, reduciendo el tamaño total de la imagen sin perder datos codificados.

```csharp
// Step 5: Enable compact mode to truncate the barcode and reduce size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

**Cuándo usarlo:** Si generas códigos de barras para almacenamiento o transmisión por red, el modo compacto puede reducir el archivo PNG hasta en un 30 %. Sin embargo, algunos escáneres heredados pueden no soportar PDF417 truncado; pruébalo con tu hardware objetivo.

## Paso 6: Guardar el código de barras como imagen PNG

Elige una ruta de salida e invoca `Save`. La enumeración `BarCodeImageFormat.Png` produce una imagen sin pérdida adecuada para la mayoría de las aplicaciones.

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

**Verificación del resultado:** Abre el archivo PNG en cualquier visor de imágenes. Deberías ver un código de barras denso y de alto contraste que coincide con el texto de ejemplo. Escanear la imagen con un lector PDF417 (p. ej., ZXing o una aplicación móvil) devuelve la cadena original `"Åspóse.Barcóde©"`.

![Imagen generada del código de barras PDF417 guardada como PNG](compact-pdf417.png "Código de barras PDF417 generado en C#")

*La imagen anterior muestra la salida final del código del tutorial.*

## Ejemplo completo y ejecutable

Uniendo todas las piezas, aquí tienes un programa de consola completo que puedes copiar, pegar y ejecutar.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;

namespace Pdf417GeneratorDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with PDF417 encoding
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // 2️⃣ Fine‑tune module size for sharper output
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set a narrow column count to keep the barcode slim
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Activate compact mode to drop empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define where the PNG will be written
            string outputPath = @"C:\Barcodes\CompactPdf417.png";

            // 6️⃣ Save the image
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Salida esperada

Al ejecutar el programa se imprime:

```
Barcode saved to C:\Barcodes\CompactPdf417.png
```

El archivo `CompactPdf417.png` contiene un código de barras PDF417 compacto que codifica la cadena Unicode proporcionada. Escanear la imagen con un lector PDF417 estándar devuelve el texto exacto.

## Variaciones comunes y casos límite

| Situación | Ajuste | Razón |
|-----------|--------|-------|
| **Carga de datos más larga** (p. ej., > 150 caracteres) | Incrementar `generator.Parameters.Barcode.Pdf417.Columns` a 6‑8 | Más columnas evitan que el código de barras se vuelva excesivamente alto. |
| **Necesidad de fondo transparente** | Usar `generator.Save(outputPath, BarCodeImageFormat.Png, new ImageSaveOptions { BackgroundColor = Color.Transparent })` | PNG transparente se integra mejor en superposiciones de UI. |
| **Generar JPEG para web** | Cambiar el formato a `BarCodeImageFormat.Jpeg` y opcionalmente establecer `ImageQuality` | JPEG reduce el tamaño del archivo a costa de la fidelidad sin pérdida. |
| **Manejo de entrada nula o vacía** | Validar la entrada antes de crear el generador: `if (string.IsNullOrEmpty(text)) throw new ArgumentException("Text cannot be empty.");` | Previene excepciones en tiempo de ejecución y asegura códigos de barras significativos. |

## Consejos para uso en producción

* **Manejo de excepciones:** Envuelve la lógica de generación en un bloque `try/catch` para registrar errores como espacio insuficiente en disco o parámetros inválidos.  
* **Rendimiento:** Reutiliza una única instancia de `BarcodeGenerator` cuando generes muchos códigos de barras con la misma configuración; solo actualiza la propiedad `CodeText` entre guardados.  
* **Seguridad:** Cuando el texto codificado contiene información sensible, considera encriptarlo antes de pasarlo al generador y desencriptarlo después de escanearlo.  

## Conclusión

Ahora sabes cómo **generar un código de barras PDF417** en C# usando la biblioteca Aspose.BarCode, configurar el modo compacto, controlar el número de columnas y exportar el resultado como una imagen PNG. Este tutorial cubrió cada paso, desde la configuración del proyecto hasta el manejo de casos límite, brindándote una solución lista para usar en aplicaciones impulsadas por códigos de barras.

A continuación, explora temas relacionados como **crear códigos QR en C#**, **generación masiva de códigos de barras** e **integración de escaneo de códigos de barras con aplicaciones móviles**. Cada uno de estos se basa en los mismos fundamentos de `BarcodeGenerator` que acabas de dominar.

¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}