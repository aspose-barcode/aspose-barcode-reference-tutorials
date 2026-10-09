---
category: general
date: 2026-10-08
description: Genera códigos de barras PDF417 en C# y aprende cómo generar imágenes
  PDF417 de manera eficiente con Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- create barcode image c#
language: es
lastmod: 2026-10-08
og_description: Genera código de barras PDF417 en C# con una guía paso a paso. Aprende
  cómo generar PDF417 y guardar la imagen del código de barras como PNG.
og_image_alt: Generated PDF417 barcode saved as a PNG image
og_title: Generar código de barras PDF417 y crear imagen de código de barras en C#
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Generate PDF417 barcode in C# and learn how to generate PDF417 images
    efficiently with Aspose.BarCode.
  headline: Generate PDF417 barcode and create barcode image C#
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Generar código de barras PDF417 y crear imagen del código de barras en C#
url: /es/net/compact-pdf417-encoding/generate-pdf417-barcode-and-create-barcode-image-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generar código de barras PDF417 y crear imagen de código de barras C#

Si necesitas **generar código de barras PDF417** en una aplicación .NET, este tutorial te muestra exactamente cómo hacerlo. Verás un ejemplo completo y ejecutable que crea un código de barras, personaliza su diseño y guarda el resultado como una imagen PNG.

Generar un código de barras PDF417 es un requisito común para etiquetas de envío, tarjetas de embarque y sistemas de inventario. Al final de esta guía podrás **generar PDF417** con control granular sobre el tamaño y el diseño, y también aprenderás a **crear imagen de código de barras C#** que pueda mostrarse en una interfaz de usuario o enviarse a una impresora.

## Requisitos previos

- .NET 6.0 o posterior (el código también funciona con .NET Framework 4.7.2+)
- Visual Studio 2022 o cualquier IDE compatible con C#
- Aspose.BarCode for .NET (versión de prueba gratuita o con licencia)  
  Instálalo vía NuGet:

```bash
dotnet add package Aspose.BarCode
```

No se requiere configuración adicional; la biblioteca maneja la codificación PNG internamente.

## Paso 1: Configurar el proyecto e importar espacios de nombres

Crea un nuevo proyecto de consola y agrega las directivas `using` necesarias. Este bloque incluye todo lo que necesitas para compilar el ejemplo.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // All barcode generation code lives here
        }
    }
}
```

*Por qué este paso es importante*: Importar el espacio de nombres `Aspose.BarCode.Generation` te da acceso a `BarcodeGenerator`, `EncodeTypes` y a los objetos de parámetros usados para personalizar el código de barras.

## Paso 2: Generar código de barras PDF417 con el texto deseado

Dentro de `Main`, instancia `BarcodeGenerator` con `EncodeTypes.Pdf417`. El constructor recibe el tipo de código de barras y el texto que deseas codificar.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo");
```

*Explicación*: `EncodeTypes.Pdf417` indica a la biblioteca que produzca la simbología PDF417. La cadena `"Layout demo"` se convierte en la carga de datos codificada en el código de barras.

## Paso 3: Ajustar finamente el tamaño del código de barras usando la dimensión X

La dimensión X controla el ancho de un solo módulo (el cuadrado negro/blanco más pequeño). Configurarla en píxeles brinda un control preciso sobre el tamaño final de la imagen.

```csharp
// Step 3: Define the module (X) dimension in pixels for finer control over barcode size
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Por qué es importante*: Una dimensión X más pequeña produce un código de barras más compacto, lo cual es útil cuando dispones de espacio limitado en una etiqueta o elemento de UI.

## Paso 4: Personalizar el diseño PDF417 (columnas y filas)

PDF417 permite especificar el número de columnas y filas. Ajustar estos valores cambia la relación de aspecto del código de barras.

```csharp
// Step 4: Set the layout – 4 columns and 9 rows for this example
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9;
```

*Explicación*: Con 4 columnas y 9 filas, el código de barras se vuelve más alto que ancho, coincidiendo con muchos formatos de impresión de tickets.

## Paso 5: Guardar el código de barras generado como imagen PNG

Finalmente, escribe el código de barras en un archivo. El enumerado `BarCodeImageFormat.Png` garantiza una compresión sin pérdidas.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"YOUR_DIRECTORY\LayoutPdf417.png";
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

*Qué ocurre aquí*: `Save` crea el archivo de imagen en disco. Puedes reemplazar `BarCodeImageFormat.Png` por `Jpeg` o `Bmp` si necesitas otro formato.

### Ejemplo completo en un solo bloque

A continuación tienes el programa completo, listo para ejecutar. Sustituye `YOUR_DIRECTORY` por una ruta de carpeta real en tu máquina.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create a PDF417 barcode generator with the desired text
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo");

            // Define the module (X) dimension in pixels for finer control over barcode size
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Set the layout – 4 columns and 9 rows for this example
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
            barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9;

            // Save the generated barcode as a PNG image
            string outputPath = @"YOUR_DIRECTORY\LayoutPdf417.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Ejecuta el programa (`dotnet run`) y abre el archivo `LayoutPdf417.png` resultante. Deberías ver un código de barras PDF417 limpio que codifica el texto *Layout demo*.

![Ejemplo de código de barras PDF417 generado](image-placeholder.png){: .responsive-img alt="Código de barras PDF417 generado y guardado como PNG"}

*Salida esperada*: Un archivo PNG de aproximadamente 150 × 300 píxeles (el tamaño varía con la dimensión X) que contiene un código de barras PDF417 escaneable.

## Variaciones comunes y casos límite

| Escenario | Cómo adaptar el código |
|----------|----------------------|
| **Carga de datos diferente** | Cambia el segundo argumento de `BarcodeGenerator` (`"Layout demo"` → cualquier cadena, hasta 1 800 caracteres). |
| **Resolución más alta** | Incrementa `XDimension.Pixels` (p. ej., `4`) o establece `Resolution` mediante `barcodeGenerator.Parameters.ImageResolution.Dpi = 300;`. |
| **Fondo transparente** | Usa `barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent });`. |
| **Incrustar en un PictureBox de Windows Forms** | En lugar de `Save`, llama `barcodeGenerator.Save(pictureBox1.CreateGraphics(), BarCodeImageFormat.Png);`. |
| **Manejo de errores** | Envuelve el código de generación en un bloque `try…catch` para capturar `BarCodeException` por caracteres no compatibles. |

## Consejos profesionales

- **Validar el código de barras**: Después de guardar, puedes cargar el PNG con un SDK de escáner de códigos de barras para asegurar que los datos coincidan con la cadena original.
- **Rendimiento**: Reutilizar una única instancia de `BarcodeGenerator` para varios códigos de barras reduce la sobrecarga de asignación.
- **Seguridad**: Si los datos codificados contienen información sensible, considera encriptarlos antes de pasarlos al generador.

## Conclusión

Ahora sabes cómo **generar código de barras PDF417** en C# y **crear imagen de código de barras C#** que cumpla con requisitos de diseño personalizados. El ejemplo completo muestra cómo inicializar el generador, ajustar tamaño y diseño, y guardar el resultado como PNG. Desde aquí puedes explorar funciones adicionales como personalización de colores, incrustación de logotipos o generación por lotes de múltiples códigos de barras para impresión masiva.

---

*Próximos pasos*:  
- Experimenta con otras simbologías (Code128, QR) usando la misma clase `BarcodeGenerator`.  
- Aprende a leer códigos de barras PDF417 con `BarCodeReader` de Aspose.BarCode.  
- Integra el PNG generado en vistas de ASP.NET Core MVC para renderizado de códigos de barras bajo demanda.

## ¿Qué deberías aprender a continuación?


Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [How to save barcode and generate PDF417 with Aspose in C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [How to generate PDF417 barcode in C# with custom dimensions](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}