---
category: general
date: 2026-09-19
description: Ejemplo de generador de códigos de barras que muestra cómo cambiar la
  altura, crear DataBar Omni‑Directional y ajustar las dimensiones del código de barras
  para la salida de imagen en C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to change height
- how to create databar
- adjust barcode dimensions
- create barcode image c#
language: es
lastmod: 2026-09-19
og_description: Ejemplo de generador de códigos de barras que enseña cómo cambiar
  la altura, crear DataBar omnidireccional y ajustar las dimensiones del código de
  barras para una imagen PNG en C#.
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode generated in C#
og_title: Ejemplo de generador de códigos de barras en C# – guía paso a paso
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator example showing how to change height, create DataBar
    Omni‑Directional, and adjust barcode dimensions for C# image output
  headline: How to build a barcode generator example in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Cómo crear un ejemplo de generador de códigos de barras en C#
url: /es/python-java/general/how-to-build-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ejemplo de generador de códigos de barras en C# – guía completa de programación

Si necesitas un **ejemplo de generador de códigos de barras** para un proyecto .NET, esta guía te muestra exactamente cómo crear, configurar y guardar un código de barras DataBar Omni‑Directional usando C#. Aprenderás a cambiar la altura, ajustar las dimensiones del código de barras y generar una imagen PNG de alta calidad, todo en una única aplicación de consola ejecutable.

Los pasos a continuación cubren todo, desde la instalación del SDK necesario hasta el ajuste de la dimensión X y la altura de la barra. Al final del tutorial tendrás un generador de códigos de barras listo para usar que podrás integrar en facturación, inventario o cualquier flujo de trabajo de escaneo.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* SDK .NET 6.0 o posterior instalado  
* Visual Studio 2022 (o cualquier IDE que soporte .NET)  
* Una licencia activa de **Aspose.BarCode for .NET** (la prueba gratuita funciona para pruebas)  

Si prefieres una biblioteca diferente, los conceptos de ajuste de dimensiones y guardado de la imagen siguen siendo los mismos; simplemente reemplaza las llamadas a la API según corresponda.

## Paso 1: Configurar el proyecto y añadir el paquete Aspose.BarCode

Crea un nuevo proyecto de consola y referencia la biblioteca de códigos de barras.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

El comando `dotnet add package` descarga la última versión estable de Aspose.BarCode, que incluye soporte completo para símbolos DataBar Omni‑Directional.

## Paso 2: Escribir el ejemplo completo del generador de códigos de barras

Abre **Program.cs** y reemplaza su contenido con el siguiente código. Este bloque contiene el **ejemplo completo de generador de códigos de barras**, sin piezas faltantes.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a barcode generator for a DataBar Omni‑Directional symbol
            // The GTIN‑14 value "(01)12345678901231" is encoded as a numeric string.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Adjust barcode dimensions
            // Set the X‑dimension (module width) to 2 pixels – this controls the thin bar width.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ How to change height
            // Set the bar height to 30 pixels. Height influences readability on larger scanners.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Optional: fine‑tune additional properties (quiet zone, color, etc.)
            generator.Parameters.Barcode.QrCodeErrorLevel = QRErrorLevel.LevelM; // example property
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // 5️⃣ Create barcode image C#
            // Save the generated barcode as a PNG file in the output folder.
            string outputPath = "DatabarOmniDirectional.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Por qué cada línea es importante

* **Crear un generador de códigos de barras** – El constructor `BarcodeGenerator` asocia el tipo de codificación (`EncodeTypes.DatabarOmniDirectional`) con los datos que deseas incrustar. Este es el núcleo del paso **cómo crear databar**.  
* **Ajustar dimensiones del código de barras** – La propiedad `XDimension.Pixels` define el ancho de la barra más estrecha. Cambiar este valor influye en el tamaño total y la fiabilidad del escaneo.  
* **Cómo cambiar la altura** – La propiedad `BarHeight.Pixels` controla el tamaño vertical. Incrementar la altura mejora la legibilidad para escáneres de mano, mientras que reducirla ahorra espacio en etiquetas pequeñas.  
* **Ajustes opcionales** – Configurar colores de primer plano/fondo o niveles de corrección de errores es opcional, pero demuestra cómo ampliar el concepto **ajustar dimensiones del código de barras**.  
* **Crear imagen de código de barras C#** – El método `Save` escribe el código de barras en disco. Usar `BarCodeImageFormat.Png` garantiza compresión sin pérdidas, ideal para la mayoría de las aplicaciones.

## Paso 3: Compilar y ejecutar el ejemplo

Compila y ejecuta el programa:

```bash
dotnet run
```

Deberías ver la salida en la consola:

```
Barcode saved to DatabarOmniDirectional.png
```

Aparece un archivo llamado **DatabarOmniDirectional.png** en la carpeta del proyecto. Al abrir la imagen verás un código de barras DataBar Omni‑Directional nítido, listo para escanear.

## Cómo cambiar la altura después de generar

Si necesitas generar códigos de barras con alturas variables, envuelve la asignación de altura en un método:

```csharp
static void SetBarHeight(BarcodeGenerator gen, int heightPixels)
{
    gen.Parameters.Barcode.BarHeight.Pixels = heightPixels;
}
```

Llama a `SetBarHeight(generator, 45);` antes de `Save`. Este enfoque te permite **cambiar la altura** dinámicamente según la entrada del usuario o archivos de configuración.

## Cómo crear códigos de barras DataBar Omni‑Directional con datos diferentes

La simbología DataBar Omni‑Directional admite GTIN‑14, GTIN‑13 y otros identificadores numéricos. Para codificar un valor distinto, simplemente reemplaza la cadena en el constructor:

```csharp
new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)98765432109876");
```

Recuerda mantener los datos numéricos y con el formato correcto; de lo contrario el generador lanzará una `BarcodeException`.

## Ajustar dimensiones del código de barras para diferentes escenarios de impresión

Diferentes impresoras y tamaños de etiqueta requieren distintas dimensiones X y alturas. Usa la siguiente tabla como referencia rápida:

| Escenario                     | X‑Dimensión (píxeles) | Altura de barra (píxeles) |
|------------------------------|-----------------------|---------------------------|
| Etiqueta pequeña (25 mm × 15 mm)  | 1                     | 20                        |
| Etiqueta mediana (50 mm × 30 mm) | 2                     | 30                        |
| Etiqueta grande (100 mm × 50 mm) | 3                     | 45                        |

Aplica estos valores estableciendo `generator.Parameters.Barcode.XDimension.Pixels` y `BarHeight.Pixels` según corresponda.

## Consejo profesional: validar el código de barras generado

Antes de enviar una etiqueta, puedes verificar su legibilidad programáticamente:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.DatabarOmniDirectional);
if (reader.Read())
{
    Console.WriteLine("Validation succeeded: " + reader.GetCodeText());
}
else
{
    Console.WriteLine("Validation failed – barcode may be unreadable.");
}
```

Este fragmento muestra una rápida comprobación de **ajustar dimensiones del código de barras**, asegurando que el código cumpla con los requisitos de escaneo.

## Problemas comunes y cómo evitarlos

| Problema                              | Por qué ocurre                              | Solución                                                                 |
|--------------------------------------|---------------------------------------------|--------------------------------------------------------------------------|
| Usar datos no numéricos para DataBar    | DataBar espera formatos GTIN numéricos        | Asegúrate de que la cadena coincida con el patrón `(01)XXXXXXXXXXXXX`. |
| Establecer X‑dimensión a 0 o negativo  | La biblioteca lanza `ArgumentOutOfRangeException`| Usa un mínimo de 1 píxel; prueba primero en la impresora objetivo.      |
| Guardar en una carpeta de solo lectura          | `UnauthorizedAccessException` al ejecutar `Save`     | Elige un directorio con permisos de escritura o ejecuta la app con los derechos adecuados.|
| Olvidar disponer `BarCodeReader` | Fuga de memoria en servicios de larga ejecución        | Envuelve el lector en un bloque `using` o llama a `Dispose()` manualmente.   |

Abordar estos problemas temprano ahorra tiempo de depuración y mejora la estabilidad en producción.

## Recapitulación del código fuente completo

A continuación se muestra el programa completo, listo para copiar, que implementa el **ejemplo de generador de códigos de barras** de principio a fin.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create generator – how to create databar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Adjust barcode dimensions
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // how to change height

            // Optional visual tweaks
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // Save image – create barcode image c#
            string filePath = "DatabarOmniDirectional.png";
            generator.Save(filePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {filePath}");

            // Validate barcode (optional)
            using (BarCodeReader reader = new BarCodeReader(filePath, DecodeType.DatabarOmniDirectional))
            {
                if (reader.Read())
                    Console.WriteLine($"Validation succeeded: {reader.GetCodeText()}");
                else
                    Console.WriteLine("Validation failed – barcode may be unreadable.");
            }
        }
    }
}
```

Ejecutar este programa produce un archivo PNG que se ve así (ilustrativo):

![DataBar Omni‑Directional barcode generated in C#](https://example.com/og-image.png "DataBar Omni‑Directional barcode generated in C#")

*Texto alternativo de la imagen*: **Código de barras DataBar Omni‑Directional generado en C#** (coincide con `og_image_alt`).

## Conclusión

Ahora dispones de un **ejemplo de generador de códigos de barras** que muestra cómo cambiar la altura, cómo crear símbolos DataBar Omni‑Directional y cómo **ajustar dimensiones del código de barras** para un escaneo óptimo. El código C# completo guarda una imagen PNG, la valida y puede ampliarse para generación masiva o integración en servicios web.

A continuación, explora temas relacionados como **creación de códigos QR con Aspose.BarCode**, **procesamiento por lotes de múltiples valores de códigos de barras**, o **incrustar códigos de barras en documentos PDF**. Cada uno de estos se basa en los mismos fundamentos cubiertos en esta guía.

¡Feliz codificación, y que tus códigos de barras siempre sean escaneables!


## ¿Qué deberías aprender a continuación?


Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Barcode Generator Example – Build DataBar Image in C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}