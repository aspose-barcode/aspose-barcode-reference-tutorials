---
category: general
date: 2026-09-29
description: La guía del generador de códigos de barras en C# muestra cómo generar
  un código de barras MicroPdf417, cambiar dimensiones, establecer columnas y personalizar
  el tamaño del código de barras en solo unas pocas líneas.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- how to generate barcode
- how to change dimensions
- how to set columns
- customize barcode size
language: es
lastmod: 2026-09-29
og_description: La guía del generador de códigos de barras C# muestra cómo generar
  un código de barras MicroPdf417, cambiar dimensiones, establecer columnas y personalizar
  el tamaño del código de barras en solo unas pocas líneas.
og_image_alt: Screenshot of a MicroPdf417 barcode generated with a C# barcode generator
og_title: Guía del generador de códigos de barras C# – crear y personalizar MicroPdf417
schemas:
- author: GroupDocs
  dateModified: '2026-09-29'
  description: Barcode generator C# guide shows how to generate a MicroPdf417 barcode,
    change dimensions, set columns, and customize barcode size in just a few lines.
  headline: 'Barcode generator C# guide: create MicroPdf417'
  type: TechArticle
tags:
- barcode
- C#
- MicroPdf417
- barcode generation
title: 'Guía del generador de códigos de barras C#: crear MicroPdf417'
url: /es/net/compact-pdf417-encoding/barcode-generator-c-guide-create-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Guía del generador de códigos de barras C#: crear MicroPdf417

Si necesitas un **barcode generator C#** para tu proyecto .NET, este tutorial te guía paso a paso para crear un código de barras MicroPdf417 desde cero. Aprenderás **cómo generar códigos de barras**, cambiar dimensiones, establecer columnas y **personalizar el tamaño del código de barras** sin esfuerzo.

MicroPdf417 es una simbología 2‑D compacta que funciona bien para etiquetar piezas pequeñas, tickets o etiquetas de inventario. Al final de esta guía tendrás una aplicación de consola completa y ejecutable que genera una imagen PNG del código de barras, y comprenderás cómo cada parámetro influye en el tamaño final.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* .NET 6.0 SDK o posterior (el código también funciona con .NET Framework 4.7+)
* Un IDE compatible con C# (Visual Studio, VS Code, Rider, etc.)
* El paquete NuGet **GroupDocs.Barcode** – instálalo con  

  ```bash
  dotnet add package GroupDocs.Barcode
  ```

No se requieren herramientas externas adicionales; la biblioteca se encarga de la codificación, el renderizado y el guardado del archivo.

## Barcode generator C#: inicializando el generador

El primer paso es crear una instancia de `BarcodeGenerator` y especificar la simbología (`EncodeTypes.MicroPdf417`) junto con los datos que deseas codificar.

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1 – create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // Subsequent configuration steps go here...

            // Save the final image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

**Por qué es importante:**  
`BarcodeGenerator` es el punto de entrada para todas las operaciones de códigos de barras. El constructor vincula el **EncodeTypes** seleccionado (MicroPdf417) a la cadena de datos sin procesar. La biblioteca maneja automáticamente caracteres Unicode como “Å” y “©”, por lo que no necesitas lógica de codificación adicional.

## Cómo cambiar las dimensiones del código de barras

La legibilidad de un código de barras depende en gran medida del ancho del módulo (la dimensión X). Configurarlo a un recuento de píxeles mayor hace que las barras sean más anchas y la imagen más fácil de escanear, especialmente en pantallas de baja resolución.

```csharp
// Step 2 – adjust the X‑dimension (module width) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Explicación:**  
`XDimension.Pixels` controla el ancho de un solo módulo del código de barras. El valor predeterminado es 1 pixel, lo que puede parecer fino en monitores de alta DPI. Aumentarlo a 2 pixels duplica el ancho total sin afectar los datos codificados.

**Consejo:** Si planeas imprimir el código de barras a 300 dpi, un valor de 3 o 4 pixels suele ofrecer el mejor equilibrio entre tamaño y fiabilidad del escaneo.

## Cómo establecer columnas para controlar el tamaño

MicroPdf417 permite especificar el número de columnas (hasta 4). Menos columnas producen un código de barras más alto; más columnas lo hacen más ancho pero más bajo. Ajustar este valor es la forma principal de **personalizar el tamaño del código de barras**.

```csharp
// Step 3 – set the maximum number of columns (4 is the limit for MicroPdf417)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Por qué funciona:**  
La propiedad `Pdf417.Columns` se comparte entre todas las simbologías basadas en PDF417, incluida MicroPdf417. Configurar el máximo (4) distribuye los datos en el diseño más amplio posible, reduciendo la altura total. Si necesitas una altura más compacta, disminuye el número de columnas a 2 o 3.

**Caso límite:** Cuando la cadena de datos es larga, la biblioteca puede aumentar automáticamente las filas para acomodar el contenido, sin importar el recuento de columnas. Mantén la carga útil por debajo de 50 caracteres para un dimensionado predecible.

## Personalizar el tamaño del código de barras para diferentes salidas

Más allá de la dimensión X y las columnas, puedes influir en el tamaño final de la imagen seleccionando un formato de imagen y DPI adecuados. PNG es sin pérdida, perfecto para la visualización web, mientras que BMP o TIFF pueden ser preferibles para impresión de alta calidad.

```csharp
// Step 4 – save as PNG (lossless) with default 96 dpi
generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
```

Si necesitas un DPI más alto, puedes establecerlo explícitamente:

```csharp
generator.Parameters.Image.DpiX = 300;
generator.Parameters.Image.DpiY = 300;
generator.Save("MicroPdf417_300dpi.png", BarCodeImageFormat.Png);
```

**Resultado:** El archivo PNG guardado contiene un código de barras MicroPdf417 nítido que respeta las dimensiones que configuraste. Abre el archivo en cualquier visor de imágenes para verificar el tamaño visual.

### Resultado esperado

Ejecutar el programa genera un archivo llamado **MicroPdf417.png** (o **MicroPdf417_300dpi.png** si estableciste DPI). El código de barras se verá similar a la ilustración a continuación:

![Salida del generador de códigos de barras C# mostrando un PNG MicroPdf417](barcode-micro-pdf417.png)

*Alt text:* *Salida del generador de códigos de barras C# mostrando un PNG MicroPdf417*

Escanear la imagen con un lector de códigos de barras 2‑D estándar devuelve la cadena original `Åspóse.Barcóde©`.

## Código fuente completo para copiar y pegar rápidamente

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // 2️⃣ Change dimensions – make modules 2 pixels wide
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set columns – use the maximum of 4 for a wider, shorter barcode
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // (Optional) Increase DPI for high‑resolution output
            // generator.Parameters.Image.DpiX = 300;
            // generator.Parameters.Image.DpiY = 300;

            // 4️⃣ Save the barcode as a PNG image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

Copia el código en un nuevo proyecto de consola, restaura los paquetes NuGet y ejecuta `dotnet run`. La consola confirmará la ubicación de la imagen, y verás el código de barras generado en la carpeta de tu proyecto.

## Preguntas comunes y solución de problemas

| Pregunta | Respuesta |
|----------|-----------|
| **¿Qué pasa si el código de barras se ve borroso?** | Aumenta `XDimension.Pixels` o el DPI (`Parameters.Image.DpiX/Y`). Ambos amplían los módulos y mejoran la fidelidad visual. |
| **¿Puedo usar un formato de imagen diferente?** | Sí. Reemplaza `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` o `Tiff`. PNG sigue siendo la opción más segura para calidad sin pérdida. |
| **Mi datos contienen emojis—¿se codificarán?** | MicroPdf417 admite UTF‑8, por lo que la mayoría de los emojis se codifican correctamente. Si encuentras errores, verifica que la cadena esté correctamente normalizada (`System.Text.Encoding.UTF8`). |
| **¿Cómo genero otras simbologías?** | Cambia `EncodeTypes.MicroPdf417` por cualquier otro valor de `EncodeTypes` ( |

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo generar una imagen de código de barras en C# – Guía MicroPdf417](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/)
- [Cómo generar un código de barras PDF417 en C# con dimensiones personalizadas](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}