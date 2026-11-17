---
category: general
date: 2026-11-17
description: Aprende cómo crear códigos de barras PDF417 en C# – una guía completa
  sobre cómo generar códigos de barras a partir de una cadena usando un generador
  de códigos de barras en C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to generate barcode
- c# barcode generator
- generate barcode from string
- create gs1 barcode
language: es
lastmod: 2026-11-17
og_description: Crea un código de barras PDF417 en C# rápidamente. Este tutorial muestra
  cómo generar un código de barras a partir de una cadena con un generador de códigos
  de barras en C# e incluye el código fuente completo.
og_image_alt: Screenshot of a generated PDF417 barcode created with a C# barcode generator
og_title: Crear código de barras PDF417 en C# – guía paso a paso
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  headline: How to create PDF417 barcode in C# with a barcode generator
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  name: How to create PDF417 barcode in C# with a barcode generator
  steps:
  - name: Expected output
    text: '![Generated PDF417 barcode showing the GTIN (01)12345678901234](/images/pdf417-sample.png){:
      .center-image alt="Generated PDF417 barcode created with a C# barcode generator"}'
  - name: Changing the image format
    text: If you prefer JPEG or BMP, just replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`
      or `BarCodeImageFormat.Bmp`. The rest of the code stays identical.
  - name: Adjusting error correction level
    text: PDF417 supports error correction levels 0‑8. Higher levels increase redundancy
      but also enlarge the barcode.
  - name: Generating other GS1 barcodes
    text: 'The same `BarcodeGenerator` can produce **create GS1 barcode** for other
      symbologies, such as `EncodeTypes.Gs1DataMatrix` or `EncodeTypes.Gs1Qr`. Just
      swap the enum value:'
  - name: Handling empty or null data
    text: 'When you **generate barcode from string**, always validate the input:'
  type: HowTo
- questions:
  - answer: Yes. The Aspose.BarCode library targets .NET Standard 2.0, which is compatible
      with .NET Framework 4.6 and later.
    question: Can I use this code on .NET Framework 4.6?
  - answer: 'Set the `Resolution` property before saving: ```csharp generator.Parameters.ImageResolution.DpiX
      = 300; generator.Parameters.ImageResolution.DpiY = 300; ```'
    question: What if I need a higher‑resolution image?
  - answer: 'It will be a standard PDF417 barcode, but it won’t be recognized as a
      GS1‑compliant symbol. Include the `(01)` prefix when you need **create GS1 barcode**
      compliance. ## Conclusion You now know how to **create PDF417 barcode** in C#
      using a robust **c# barcode generator**. The tutorial covered: * In'
    question: Is the barcode still valid without the GS1 Application Identifier?
  type: FAQPage
tags:
- barcode
- C#
- PDF417
- GS1
- code generation
title: Cómo crear un código de barras PDF417 en C# con un generador de códigos de
  barras
url: /es/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-a-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un código de barras PDF417 en C# con un generador de códigos de barras

Si necesitas **crear un código de barras PDF417** en una aplicación .NET, esta guía muestra exactamente cómo hacerlo. Aprenderás **cómo generar un código de barras** a partir de una cadena simple, configurar el tamaño del símbolo y guardar el resultado como un archivo PNG, todo usando un generador de códigos de barras C# confiable.

Generar códigos de barras programáticamente elimina pasos manuales y garantiza una calidad constante. En este tutorial cubriremos todo, desde la configuración del proyecto hasta la imagen final, para que puedas integrar la creación de códigos de barras en cualquier solución C# hoy mismo.

## Requisitos previos

* .NET 6.0 SDK o posterior (el código funciona con .NET Core y .NET Framework)
* Visual Studio 2022 (o cualquier IDE que soporte C#)
* Una licencia o prueba gratuita de **Aspose.BarCode for .NET** – la biblioteca utilizada en los ejemplos
* Familiaridad básica con la sintaxis de C#

No se requieren paquetes adicionales; el paquete NuGet `Aspose.BarCode` contiene todas las clases que necesitarás.

## Paso 1 – Configurar el generador de códigos de barras C#

Lo primero que haces al **crear un código de barras PDF417** es instanciar un objeto `BarcodeGenerator`. Este objeto representa el **generador de códigos de barras c#** que se encargará de la codificación, renderizado y guardado.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for PDF417 with the data to encode
        // The data string follows the GS1 Application Identifier (01) for a GTIN
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417, "(01)12345678901234");
```

*Por qué es importante*: El enumerado `EncodeTypes.Pdf417` indica a la biblioteca que use la simbología PDF417, que es el mismo estándar utilizado para tarjetas de identificación y etiquetas de transporte. La cadena `"(01)12345678901234"` es un ejemplo de **generar código de barras a partir de una cadena** que también muestra cómo **crear datos de código de barras GS1**.

## Paso 2 – Configurar la dimensión X (ancho del módulo)

La dimensión X controla el ancho de la barra más pequeña (módulo). Un valor común para renderizado en pantalla es 2 píxeles.

```csharp
        // Step 2: Set the X‑dimension (module width) to 2 pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Establecer la dimensión X explícitamente evita que el generador use su valor predeterminado, lo que podría producir un código de barras demasiado pequeño para algunos escáneres.

## Paso 3 – Definir el número de columnas

PDF417 permite ajustar el número de columnas, lo que afecta tanto la forma del código de barras como la capacidad de datos. Para una etiqueta compacta, cuatro columnas funcionan bien.

```csharp
        // Step 3: Define the number of columns (e.g., 4) for a compact barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

Si necesitas un código de barras más alto, aumenta el recuento de columnas; la biblioteca calculará automáticamente las filas necesarias.

## Paso 4 – Guardar el código de barras como una imagen

Finalmente, exporta el código de barras a un archivo PNG. PNG conserva bordes nítidos y soporta transparencia.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("output/Gs1Pdf417.png", BarCodeImageFormat.Png);
    }
}
```

Ejecutar el programa crea `output/Gs1Pdf417.png`. Abre el archivo en cualquier visor de imágenes; verás un **código de barras PDF417** limpio que codifica los datos GS1 que proporcionaste.

### Resultado esperado

![Código de barras PDF417 generado que muestra el GTIN (01)12345678901234](/images/pdf417-sample.png){: .center-image alt="Código de barras PDF417 generado con un generador de códigos de barras C#"}

*La imagen anterior muestra el resultado del ejemplo de código completo. El código de barras puede ser escaneado por cualquier lector compatible con PDF417.*

## Opciones adicionales y variaciones comunes

### Cambiar el formato de imagen

Si prefieres JPEG o BMP, simplemente reemplaza `BarCodeImageFormat.Png` por `BarCodeImageFormat.Jpeg` o `BarCodeImageFormat.Bmp`. El resto del código permanece idéntico.

### Ajustar el nivel de corrección de errores

PDF417 soporta niveles de corrección de errores del 0 al 8. Niveles más altos aumentan la redundancia pero también agrandan el código de barras.

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // medium redundancy
```

### Generar otros códigos de barras GS1

El mismo `BarcodeGenerator` puede producir **crear códigos de barras GS1** para otras simbologías, como `EncodeTypes.Gs1DataMatrix` o `EncodeTypes.Gs1Qr`. Simplemente cambia el valor del enumerado:

```csharp
BarcodeGenerator gs1Generator = new BarcodeGenerator(
    EncodeTypes.Gs1DataMatrix, "(01)12345678901234");
```

### Manejo de datos vacíos o nulos

Cuando **generas un código de barras a partir de una cadena**, siempre valida la entrada:

```csharp
string data = GetUserInput();
if (string.IsNullOrWhiteSpace(data))
{
    throw new ArgumentException("Data to encode cannot be null or empty.");
}
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
```

Esto evita excepciones en tiempo de ejecución y garantiza que el código de barras cumpla con las reglas de formato GS1.

## Ejemplo completo y ejecutable

A continuación se muestra el programa completo que puedes copiar y pegar en un nuevo proyecto de consola. Incluye todas las directivas `using` necesarias, la creación de carpetas y el manejo de errores.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Input data – GS1 GTIN with Application Identifier (01)
        const string gs1Data = "(01)12345678901234";

        // Validate input
        if (string.IsNullOrWhiteSpace(gs1Data))
        {
            Console.WriteLine("Error: Barcode data cannot be empty.");
            return;
        }

        // Ensure output directory exists
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);

        // Create the generator for PDF417 (GS1 optional)
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417, gs1Data);

        // Configure appearance
        generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
        generator.Parameters.Barcode.Pdf417.Columns = 4;    // compact layout
        generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // optional

        // Save as PNG
        string outputPath = Path.Combine(outputDir, "Gs1Pdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

**Ejecuta el programa** (`dotnet run`) y encontrarás `Gs1Pdf417.png` dentro de la carpeta *output*. Escanéalo con cualquier lector PDF417 para verificar que el GTIN `(01)12345678901234` está codificado correctamente.

## Preguntas frecuentes

**Q: ¿Puedo usar este código en .NET Framework 4.6?**  
A: Sí. La biblioteca Aspose.BarCode está dirigida a .NET Standard 2.0, que es compatible con .NET Framework 4.6 y versiones posteriores.

**Q: ¿Qué pasa si necesito una imagen de mayor resolución?**  
A: Establece la propiedad `Resolution` antes de guardar:

```csharp
generator.Parameters.ImageResolution.DpiX = 300;
generator.Parameters.ImageResolution.DpiY = 300;
```

**Q: ¿Sigue siendo válido el código de barras sin el Identificador de Aplicación GS1?**  
A: Será un código de barras PDF417 estándar, pero no será reconocido como un símbolo compatible con GS1. Incluye el prefijo `(01)` cuando necesites **crear códigos de barras GS1** conforme.

## Conclusión

Ahora sabes cómo **crear un código de barras PDF417** en C# usando un robusto **generador de códigos de barras c#**. El tutorial cubrió:

* Instanciar `BarcodeGenerator` con datos GS1  
* Configurar la dimensión X y el número de columnas  
* Guardar el resultado como una imagen PNG  
* Ampliar la solución con corrección de errores, diferentes formatos y validación de entrada  

Con esta base puedes generar cualquier código de barras PDF417 o GS1 directamente a partir de una cadena, incrustarlo en informes o enviarlo a impresoras. Explora la API de Aspose.BarCode para añadir colores, márgenes o combinar varios códigos de barras en una sola imagen.

**Próximos pasos**: intenta generar un **crear código de barras GS1** para DataMatrix, experimenta con cálculos dinámicos de columnas, o integra el generador en un servicio web ASP.NET Core que devuelva imágenes de códigos de barras bajo demanda.

¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo generar un código de barras PDF417 en C# – guía completa](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-complete-guide/)
- [Cómo crear un código de barras micro PDF417 y generar PNG en C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-generate-png-in-c/)
- [Cómo crear un código de barras macro PDF417 en C# usando Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}