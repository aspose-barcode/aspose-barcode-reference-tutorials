---
category: general
date: 2026-10-05
description: Aprende a crear códigos de barras PDF417 en C# y generar un PNG del código
  de barras con código paso a paso y consejos de buenas prácticas.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- generate barcode PNG
- how to generate PDF417
language: es
lastmod: 2026-10-05
og_description: Crea un código de barras PDF417 en C# y genera un PNG del código de
  barras al instante. Sigue este tutorial completo para una solución lista para producción.
og_image_alt: Example of a compact PDF417 barcode created with C#
og_title: Crear código de barras PDF417 en C# – guía completa para generar PNG
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
    step‑by‑step code and best‑practice tips.
  headline: How to create PDF417 barcode and save it as PNG in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
    step‑by‑step code and best‑practice tips.
  name: How to create PDF417 barcode and save it as PNG in C#
  steps:
  - name: Expected output
    text: When you open `CompactPdf417.png`, you should see a vertical, high‑density
      barcode that encodes the string *Åspóse.Barcóde©*. Scanning the image with any
      PDF417 reader returns the original text.
  - name: Generating other image formats
    text: 'If you prefer JPEG or BMP, change the `BarCodeImageFormat` enum:'
  - name: Adjusting error correction
    text: 'For harsh environments (e.g., outdoor signage), increase the error‑correction
      level:'
  - name: Encoding binary data
    text: 'PDF417 can encode binary payloads. Pass a `byte[]` instead of a string:'
  - name: Handling very long strings
    text: 'When the data exceeds the default capacity, the generator automatically
      creates additional rows. You can limit the row count to avoid oversized images:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- image generation
title: Cómo crear un código de barras PDF417 y guardarlo como PNG en C#
url: /es/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un código de barras PDF417 y guardarlo como PNG en C#

Si necesitas **crear un código de barras PDF417** en una aplicación .NET, esta guía te muestra exactamente cómo hacerlo. Obtendrás un fragmento de C# listo para usar que genera un archivo **PNG de código de barras** de alta calidad, y comprenderás cada configuración que influye en el resultado.

Generar códigos de barras es un requisito común para sistemas de tickets, seguimiento de inventario y codificación segura de documentos. Al final de este tutorial podrás responder a la pregunta “**cómo generar PDF417**” con un ejemplo completo y ejecutable.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* SDK .NET 6.0 o posterior instalado  
* Un entorno de desarrollo como Visual Studio 2022 o VS Code  
* El paquete NuGet **Aspose.BarCode for .NET** (o cualquier biblioteca compatible que soporte PDF417)  

Puedes agregar el paquete con el siguiente comando:

```bash
dotnet add package Aspose.BarCode
```

El código a continuación usa la API de Aspose porque brinda un control granular sobre los parámetros de PDF417 y soporta la exportación a PNG de forma nativa.

## Paso 1: Configurar el proyecto e importar espacios de nombres

Crea un nuevo proyecto de consola e importa los espacios de nombres requeridos:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

El espacio de nombres `Aspose.BarCode.Generation` contiene la clase `BarcodeGenerator`, que es el punto de entrada para **crear imágenes de código de barras PDF417**.

## Paso 2: Crear un código de barras PDF417 con el texto deseado

Instancia el generador con el enum `EncodeTypes.Pdf417` y los datos que deseas codificar. El ejemplo usa una cadena que contiene caracteres especiales para demostrar el manejo de Unicode:

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

El generador ahora contiene un objeto de código de barras que puedes configurar antes de renderizar.

## Paso 3: Configurar parámetros visuales

Ajustar finamente el código de barras mejora la legibilidad y reduce el tamaño de la imagen. Las configuraciones más frecuentemente ajustadas son **X‑dimension**, **columns** y **compact mode**.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 4: Define the number of columns for the PDF417 code
generator.Parameters.Barcode.Pdf417.Columns = 3;

// Step 5: Enable compact (truncated) mode to reduce the barcode size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

* **X‑dimension** controla el ancho de cada módulo; un valor de `2` píxeles produce un código de barras compacto pero legible.  
* **Columns** determina cuántas columnas de datos utiliza el código. Menos columnas hacen el código de barras más estrecho pero más alto.  
* **Truncate** activa el modo “compacto” definido por la especificación PDF417, que elimina filas de relleno innecesarias.

Puedes experimentar con `Rows` y `ErrorCorrectionLevel` si tu caso de uso requiere mayor resistencia al daño.

## Paso 4: Guardar el código de barras como una imagen PNG

Finalmente, exporta el código de barras a un archivo PNG. PNG conserva bordes nítidos y soporta transparencia, lo que lo hace ideal para escenarios web e impresión.

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Ejecutar el programa crea `CompactPdf417.png` en el directorio especificado. La imagen se ve así:

![Código de barras PDF417 compacto creado con C#](compact-pdf417.png "Ejemplo de un código de barras PDF417 compacto creado con C#")

*El texto alternativo anterior contiene la palabra clave principal, cumpliendo tanto con los requisitos de SEO como de accesibilidad.*

## Ejemplo completo y ejecutable

Uniendo todas las piezas, aquí tienes un programa autónomo que puedes copiar, pegar y ejecutar:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1. Initialize the generator with PDF417 type and sample data
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

        // 2. Configure size and compactness
        generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
        generator.Parameters.Barcode.Pdf417.Columns = 3;           // number of columns
        generator.Parameters.Barcode.Pdf417.Truncate = true;       // enable compact mode

        // 3. Optional: increase error correction for damaged prints
        // generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;

        // 4. Export to PNG
        string outputPath = @"C:\Barcodes\CompactPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

### Resultado esperado

Al abrir `CompactPdf417.png`, deberías ver un código de barras vertical y de alta densidad que codifica la cadena *Åspóse.Barcóde©*. Escanear la imagen con cualquier lector PDF417 devuelve el texto original.

## Por qué estos ajustes son importantes

* **X‑dimension** influye tanto en el tamaño físico como en la velocidad de escaneo. Módulos más pequeños aumentan la densidad de datos pero pueden requerir escáneres de mayor resolución.  
* **Columns** afecta la relación de aspecto. Para recibos móviles, un número bajo de columnas mantiene el código de barras lo suficientemente estrecho para caber en papel estrecho.  
* **Truncate** reduce el número de filas, ahorrando tinta y espacio sin sacrificar la integridad de los datos, ya que PDF417 ya incluye palabras de corrección de errores.

Entender estos parámetros te permite adaptar el código de barras a las limitaciones de tu medio objetivo—ya sea una impresora de etiquetas, una página web o una aplicación móvil.

## Variaciones comunes y casos límite

### Generar otros formatos de imagen

Si prefieres JPEG o BMP, cambia el enum `BarCodeImageFormat`:

```csharp
generator.Save(@"C:\Barcodes\Pdf417.jpg", BarCodeImageFormat.Jpeg);
```

JPEG comprime la imagen pero puede introducir artefactos que afecten el escaneo en tamaños pequeños.

### Ajustar la corrección de errores

Para entornos duros (p. ej., señalización exterior), aumenta el nivel de corrección de errores:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 8; // max is 8
```

Niveles más altos añaden más redundancia, haciendo el código de barras más grande pero más robusto.

### Codificar datos binarios

PDF417 puede codificar cargas binarias. Pasa un `byte[]` en lugar de una cadena:

```csharp
byte[] binaryData = new byte[] { 0x01, 0xFF, 0xA5 };
generator = new BarcodeGenerator(EncodeTypes.Pdf417, binaryData);
```

La biblioteca cambia automáticamente al modo binario.

### Manejo de cadenas muy largas

Cuando los datos superan la capacidad predeterminada, el generador crea automáticamente filas adicionales. Puedes limitar el recuento de filas para evitar imágenes demasiado grandes:

```csharp
generator.Parameters.Barcode.Pdf417.Rows = 30; // max rows
```

Si el contenido aún no cabe, considera dividirlo en varios códigos de barras.

## Consejos profesionales

* **Cache the generator** si necesitas crear muchos códigos de barras con los mismos ajustes. Reutilizar el objeto evita la asignación repetida de recursos internos.  
* **Set `Resolution`** en `ImageOptions` si necesitas un DPI específico para impresión:

  ```csharp
  generator.Parameters.ImageResolution = 300; // DPI
  ```

* **Validate the output** programáticamente con `BarCodeReader` para asegurar que el PNG generado pueda decodificarse antes de enviarlo a los usuarios.

## Conclusión

Ahora sabes cómo **crear un código de barras PDF417** en C# y **generar archivos PNG de código de barras** con control total sobre el tamaño, columnas y modo compacto. El ejemplo completo muestra el enfoque estándar, explica por qué cada ajuste es importante y cubre variaciones como corrección de errores, formatos alternativos y datos binarios. Usa los consejos anteriores para adaptar la solución a tu flujo de trabajo específico, ya sea que estés construyendo un sistema de tickets, un generador de etiquetas logísticas o un codificador de documentos seguros.

---

**Próximos pasos**

* Explora otras simbologías 2D (DataMatrix, QR) usando la misma clase `BarcodeGenerator`.  
* Integra la creación del código de barras en una API ASP.NET Core para servir PNGs bajo demanda.  
* Combina la imagen del código de barras con bibliotecas de generación de PDF para incrustarla directamente en informes.

¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo crear un código de barras pdf417 en C# – guía paso a paso](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [Cómo generar un código de barras micro pdf417 en C# – guía paso a paso](/barcode/english/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/)
- [Cómo crear un código de barras PDF417 en C# con modo compacto](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}