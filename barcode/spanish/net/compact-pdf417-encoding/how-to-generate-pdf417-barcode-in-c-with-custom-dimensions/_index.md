---
category: general
date: 2026-09-07
description: Genera un código de barras PDF417 en C# y aprende cómo establecer las
  dimensiones del código de barras para un control preciso. Sigue esta guía paso a
  paso para crear una imagen PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- how to set barcode dimensions
language: es
lastmod: 2026-09-07
og_description: Genera códigos de barras PDF417 en C# y aprende a establecer sus dimensiones.
  Este tutorial muestra un ejemplo completo y ejecutable.
og_image_alt: Generated PDF417 barcode image with custom dimensions
og_title: Generar código de barras PDF417 en C# – guía completa con dimensiones
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  headline: How to generate PDF417 barcode in C# with custom dimensions
  type: TechArticle
- description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  name: How to generate PDF417 barcode in C# with custom dimensions
  steps:
  - name: Expected output
    text: '- **File:** `Pdf417Layout.png` (PNG, lossless) - **Dimensions:** Determined
      by `XDimension` (2 px) × (columns × rows) matrix - **Content:** A scannable
      PDF417 barcode encoding the Unicode string `Åspóse.Barcóde©`'
  - name: What if I need a larger image for printing?
    text: Increase `XDimension.Pixels` to 4 or 5. Larger values produce a higher‑resolution
      barcode but also increase file size.
  - name: Can I encode more data than the example string?
    text: Yes. PDF417 can hold up to 1,850 characters. Just replace the text argument
      in the `BarcodeGenerator` constructor. If the data exceeds the matrix capacity,
      the library automatically adds extra rows.
  - name: How does error correction work?
    text: 'PDF417 includes built‑in error correction. You can adjust its level via:'
  - name: What if the barcode appears blurry on screen?
    text: 'Make sure the output image’s DPI matches the display environment. You can
      set DPI when saving:'
  - name: Next steps
    text: '- Explore **how to generate PDF417 barcode** with different image formats
      (JPEG, BMP). - Learn **how to set barcode dimensions** dynamically based on
      user input or device DPI. - Integrate the barcode generation into an ASP.NET
      Core API to serve barcodes on demand.'
  type: HowTo
tags:
- barcode generation
- PDF417
- C#
title: Cómo generar un código de barras PDF417 en C# con dimensiones personalizadas
url: /es/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo generar un código de barras PDF417 en C# con dimensiones personalizadas

Si necesitas **generar un código de barras PDF417** en una aplicación .NET, esta guía te muestra exactamente cómo hacerlo. Verás un ejemplo completo y ejecutable que crea una imagen PNG mientras te permite controlar las dimensiones del código de barras.

Generar un código de barras PDF417 es un requisito común para sistemas de inventario, tarjetas de embarque y documentos seguros. En este tutorial también aprenderás **cómo establecer las dimensiones del código de barras** para que la salida coincida con tus necesidades de diseño.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

- SDK de .NET 6.0 o posterior instalado  
- Visual Studio 2022 (o cualquier IDE compatible con C#)  
- El paquete NuGet **Aspose.BarCode for .NET** (o cualquier biblioteca compatible que admita PDF417)  

Puedes añadir el paquete con el siguiente comando:

```bash
dotnet add package Aspose.BarCode
```

## Paso 1: Crear un generador de código de barras PDF417

El primer paso es instanciar un `BarcodeGenerator` con el tipo `EncodeTypes.Pdf417` y el texto que deseas codificar. El objeto generador contiene todas las configuraciones del código de barras.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");
```

**Por qué es importante:** El enumerado `EncodeTypes.Pdf417` indica a la biblioteca que use la simbología PDF417, que soporta grandes cargas de datos y corrección de errores. La cadena de texto puede contener caracteres Unicode, por lo que puedes codificar símbolos internacionales sin trabajo adicional.

## Paso 2: Cómo establecer las dimensiones del código de barras

Controlar el tamaño de cada módulo (el cuadrado negro/blanco más pequeño) determina la resolución general de la imagen. La propiedad `XDimension.Pixels` establece el ancho en píxeles de un módulo.

```csharp
        // Step 2: Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Por qué es importante:** Un `XDimension` mayor produce una imagen de mayor resolución, lo que es útil para impresión o escaneo a distancia. Por el contrario, un valor menor reduce el tamaño del archivo para uso web.

## Paso 3: Definir el diseño PDF417 (columnas y filas)

PDF417 te permite influir en la forma de la matriz especificando el número de columnas y filas. Esto puede afectar la legibilidad y el tamaño físico del código de barras.

```csharp
        // Step 3: Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

**Por qué es importante:** Ajustar columnas y filas te permite encajar el código de barras en un espacio específico o cumplir con los requisitos de relación de aspecto de un escáner. La biblioteca agrega automáticamente relleno si los datos no llenan completamente la matriz.

## Paso 4: Guardar el código de barras como imagen PNG

Finalmente, escribe el código de barras generado en un archivo. PNG conserva la calidad sin pérdidas, lo que lo hace ideal para procesamiento posterior.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

Al ejecutar el programa, `Pdf417Layout.png` aparecerá en la carpeta de salida del proyecto. La imagen se ve así:

![Imagen de código de barras PDF417 generado con dimensiones personalizadas](og_image_placeholder.png)

*Texto alternativo de la imagen: Imagen de código de barras PDF417 generado con dimensiones personalizadas*  

**Por qué es importante:** Guardar como PNG garantiza que se conserven las dimensiones exactas de los módulos que estableciste, lo cual es crucial para aplicaciones de escaneo posteriores.

## Ejemplo completo en un solo bloque

A continuación tienes el programa completo que puedes copiar, pegar y ejecutar sin modificaciones (excepto la ruta de salida si lo deseas).

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

### Salida esperada

- **Archivo:** `Pdf417Layout.png` (PNG, sin pérdidas)  
- **Dimensiones:** Determinadas por `XDimension` (2 px) × matriz (columnas × filas)  
- **Contenido:** Un código de barras PDF417 escaneable que codifica la cadena Unicode `Åspóse.Barcóde©`

## Preguntas frecuentes y casos límite

### ¿Qué pasa si necesito una imagen más grande para impresión?

Aumenta `XDimension.Pixels` a 4 o 5. Valores mayores generan un código de barras de mayor resolución pero también aumentan el tamaño del archivo.

### ¿Puedo codificar más datos que la cadena del ejemplo?

Sí. PDF417 puede contener hasta 1 850 caracteres. Simplemente reemplaza el argumento de texto en el constructor de `BarcodeGenerator`. Si los datos superan la capacidad de la matriz, la biblioteca agrega automáticamente filas extra.

### ¿Cómo funciona la corrección de errores?

PDF417 incluye corrección de errores incorporada. Puedes ajustar su nivel mediante:

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // 0‑8, higher = more correction
```

Niveles más altos aumentan la robustez a costa de códigos de barras más grandes.

### ¿Qué ocurre si el código de barras se ve borroso en pantalla?

Asegúrate de que el DPI de la imagen de salida coincida con el entorno de visualización. Puedes establecer el DPI al guardar:

```csharp
barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png, 300);
```

## Consejos profesionales

- **Consejo pro:** Siempre prueba el código de barras generado con el escáner real que planeas usar. Diferentes dispositivos tienen tolerancias variables para el tamaño del módulo y las zonas silenciosas.  
- **Cuidado con:** Valores de `XDimension` muy pequeños (< 1 px) pueden renderizarse como líneas invisibles en pantallas de alta DPI.  
- **Consejo para aplicaciones web:** Sirve el PNG con `Cache-Control: public, max-age=86400` para reducir la sobrecarga de generación repetida.

## Conclusión

Ahora sabes cómo **generar un código de barras PDF417** en C# y establecer **precisamente las dimensiones del código de barras** para adaptarlas a cualquier requisito. El ejemplo completo y ejecutable muestra cómo crear una imagen PNG con diseño de columnas/filas y tamaño de módulo personalizados, listo para impresión o distribución digital.

### Próximos pasos

- Explora **cómo generar códigos de barras PDF417** con diferentes formatos de imagen (JPEG, BMP).  
- Aprende **cómo establecer dimensiones del código de barras** de forma dinámica según la entrada del usuario o el DPI del dispositivo.  
- Integra la generación de códigos de barras en una API ASP.NET Core para servir códigos bajo demanda.

¡Siéntete libre de experimentar con otras configuraciones de PDF417 como corrección de errores, márgenes y color. Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo establecer el nivel de error en el código de barras PDF417 – Guía completa](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Cómo guardar un código de barras en C# – Generar códigos de barras PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Generar código de barras PDF417 en C# – Guía completa](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}