---
category: general
date: 2026-09-19
description: Crear código de barras PDF417 en C# y aprender cómo generar la imagen
  del código de barras, establecer sus dimensiones y guardarla como PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to generate barcode image
- how to set barcode dimensions
- how to create barcode png
language: es
lastmod: 2026-09-19
og_description: Crea un código de barras PDF417 en C# y descubre cómo generar la imagen
  del código de barras, establecer sus dimensiones y guardarla como un archivo PNG.
og_image_alt: Sample PDF417 barcode generated with C# showing custom dimensions saved
  as PNG
og_title: Crear código de barras PDF417 y exportar PNG en C# – guía paso a paso
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: Create PDF417 barcode in C# and learn how to generate barcode image,
    set barcode dimensions, and save as PNG.
  headline: How to create PDF417 barcode and export PNG in C#
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- image generation
title: Cómo crear un código de barras PDF417 y exportar PNG en C#
url: /es/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un código de barras PDF417 y exportar PNG en C#

Si necesita **crear código de barras PDF417** en una aplicación .NET, esta guía le muestra cómo generar una imagen de código de barras, ajustar sus dimensiones y guardarla como archivo PNG. Verá un ejemplo completo y ejecutable que utiliza la biblioteca Aspose.BarCode, para que pueda copiar el código directamente en su propio proyecto.

Generar una imagen de código de barras es un requisito común para sistemas de emisión de boletos, seguimiento de inventario y pases de embarque móviles. Al final de este tutorial comprenderá **cómo generar una imagen de código de barras**, **cómo establecer las dimensiones del código de barras** y **cómo crear archivos PNG de código de barras** que cumplan con sus estándares de calidad visual.

## Requisitos previos

* .NET 6.0 SDK o posterior (el código también funciona con .NET Framework 4.7+).
* Un entorno de desarrollo como Visual Studio 2022 o VS Code.
* Una licencia válida para la biblioteca **Aspose.BarCode for .NET** (la prueba gratuita funciona para este ejemplo).
* Familiaridad básica con la sintaxis de C#.

Instale el paquete NuGet con el siguiente comando:

```bash
dotnet add package Aspose.BarCode
```

## Paso 1: Configurar el proyecto e importar espacios de nombres

Cree una nueva aplicación de consola o agregue el código a un proyecto existente. Importe los espacios de nombres requeridos al inicio del archivo:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Estos espacios de nombres le dan acceso a la clase `BarcodeGenerator` y a la enumeración `EncodeTypes`.

## Paso 2: Cómo crear un código de barras PDF417 – configuración básica del generador

La primera operación es instanciar un `BarcodeGenerator` con el tipo de codificación `Pdf417` y el texto que desea codificar. Este objeto representa el código de barras que más adelante renderizará.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");
```

*Por qué es importante*: `EncodeTypes.Pdf417` indica a la biblioteca que use la simbología PDF417, que es un código de barras lineal apilado capaz de almacenar grandes cantidades de datos. El segundo argumento (“Sample”) es la carga útil que aparecerá cuando se escanee el código de barras.

## Paso 3: Cómo establecer las dimensiones del código de barras – ajuste fino de densidad y diseño

Un código de barras PDF417 consta de filas y columnas de módulos. Ajustar la X‑dimensión (ancho del módulo) y el número de filas/columnas le permite controlar la densidad visual y el tamaño general de la imagen.

```csharp
// Step 3: Set the module (X) dimension in pixels – controls the barcode's density
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Define the barcode layout – number of columns and rows
generator.Parameters.Barcode.Pdf417.Columns = 4;   // up to 30 columns
generator.Parameters.Barcode.Pdf417.Rows    = 9;   // up to 90 rows
```

*Por qué es importante*:  
* **X‑dimension** determina qué tan ancho es cada pequeño cuadrado (módulo). Un valor menor produce un código de barras más compacto pero puede ser más difícil de leer para escáneres de baja resolución.  
* **Columns** y **Rows** afectan la capacidad de datos y la forma física. Incrementar las columnas hace que el código de barras sea más ancho; incrementar las filas lo hace más alto. Puede experimentar con valores hasta los límites mostrados en los comentarios.

**Consejo profesional**: Si el código de barras se ve demasiado denso en una pantalla de alta DPI, aumente `XDimension.Pixels` a 3 o 4. Por el contrario, para una etiqueta pequeña, podría establecerlo en 1 píxel y reducir el número de columnas.

## Paso 4: Cómo generar la imagen del código de barras – renderizado a un bitmap en memoria

Después de configurar el generador, puede renderizar el código de barras a un objeto de imagen. Este paso es opcional si solo necesita guardar el archivo directamente, pero exponer el bitmap le permite aplicar procesamiento adicional (p. ej., agregar un logotipo o dibujar un borde).

```csharp
// Step 4: Render the barcode to a bitmap (optional but useful for further manipulation)
using var barcodeImage = generator.GenerateBarCodeImage();
```

`GenerateBarCodeImage()` devuelve un `System.Drawing.Image` que puede manipular con GDI+ si lo desea.

## Paso 5: Cómo crear un PNG del código de barras – guardando el archivo de imagen final

Finalmente, escriba la imagen en disco en formato PNG. PNG conserva una calidad sin pérdidas, lo que es ideal para aplicaciones de escaneo.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"YOUR_DIRECTORY\Pdf417Custom.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

*Por qué es importante*: El método `Save` maneja la codificación y la entrada/salida de archivos por usted. Usar `BarCodeImageFormat.Png` garantiza que la salida sea una imagen portátil y sin pérdidas que funciona en navegadores y dispositivos móviles.

### Ejemplo completo ejecutable

A continuación se muestra el programa completo que puede pegar en `Program.cs` y ejecutar. Reemplace `YOUR_DIRECTORY` con una carpeta existente en su máquina.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1. Create the generator with PDF417 symbology
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");

        // 2. Adjust dimensions for desired visual density
        generator.Parameters.Barcode.XDimension.Pixels = 2;
        generator.Parameters.Barcode.Pdf417.Columns = 4; // up to 30
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // up to 90

        // 3. (Optional) Render to a bitmap if you need further processing
        // using var image = generator.GenerateBarCodeImage();

        // 4. Save as PNG
        string outputPath = @"YOUR_DIRECTORY\Pdf417Custom.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode created and saved to: {outputPath}");
    }
}
```

Ejecutar el programa produce un archivo PNG que se ve así:

![Ejemplo de código de barras PDF417 generado](https://example.com/placeholder-image.png "Código de barras PDF417 generado con dimensiones personalizadas guardado como PNG")

*Texto alternativo*: **Código de barras PDF417 de ejemplo generado con C# que muestra dimensiones personalizadas guardado como PNG** – esto satisface el requisito de **crear código de barras PDF417** para la accesibilidad de la imagen.

## Variaciones comunes y casos límite

| Situación | Ajuste recomendado |
|-----------|--------------------|
| **Etiqueta muy pequeña** (p. ej., 1 cm × 2 cm) | Establezca `XDimension.Pixels = 1` y reduzca `Columns` a 2‑3. Verifique la legibilidad del escáner. |
| **Impresión de alta resolución** (300 dpi o más) | Aumente `XDimension.Pixels` a 3‑4 y opcionalmente eleve `Rows` para mayor capacidad de datos. |
| **Necesita un formato de imagen diferente** (JPEG, BMP) | Cambie `BarCodeImageFormat.Png` a `BarCodeImageFormat.Jpeg` o `BarCodeImageFormat.Bmp`. |
| **Incrustar en un PDF** | Use `generator.Save("output.pdf", BarCodeImageFormat.Pdf)` en lugar de PNG. |
| **Datos dinámicos** (entrada del usuario) | Reemplace la cadena estática `"Sample"` por una variable, p. ej., `userInput`. Asegúrese de que la longitud del texto no supere los límites de PDF417 (≈ 1 800 caracteres). |

## Lista de verificación de solución de problemas

* **Imagen en blanco** – Verifique que el directorio de salida exista y que la aplicación tenga permiso de escritura.  
* **Código de barras no escaneable** – Aumente `XDimension.Pixels` o añada más columnas/filas; los fondos de bajo contraste también pueden causar fallos.  
* **Tamaño inesperado** – Verifique nuevamente los valores de `Columns` y `Rows`; la biblioteca respeta los límites máximos mostrados en los comentarios.  

## Próximos pasos

Ahora que puede **crear código de barras PDF417**, considere explorar estos temas relacionados:

* **Cómo generar una imagen de código de barras** en otros formatos como SVG para gráficos web escalables.  
* **Cómo establecer las dimensiones del código de barras** para códigos QR y simbologías DataMatrix.  
* **Cómo crear un PNG de código de barras** con colores personalizados o logotipos incrustados usando `System.Drawing`.  

Estas extensiones le permiten crear un servicio de generación de códigos de barras completo que puede atender aplicaciones móviles, portales web y utilidades de escritorio por igual.

---

*Ha aprendido cómo crear un código de barras PDF417, personalizar sus dimensiones, renderizar una imagen de código de barras y guardarla como archivo PNG usando C#. Aplique los patrones mostrados aquí a otros tipos de códigos de barras y formatos de imagen para ampliar sus capacidades de automatización.*

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarle a dominar características adicionales de la API y explorar enfoques de implementación alternativos en sus propios proyectos.

- [Cómo generar una imagen de código de barras PDF417 en C# con Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Cómo crear un código de barras PDF417 con Aspose – Guía completa paso a paso](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Cómo guardar un código de barras en C# – Generar códigos de barras PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}