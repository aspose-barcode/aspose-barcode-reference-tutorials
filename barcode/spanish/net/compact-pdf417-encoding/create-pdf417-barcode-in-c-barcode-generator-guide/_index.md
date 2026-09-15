---
category: general
date: 2026-07-18
description: Crear código de barras PDF417 en C# usando el generador de códigos de
  barras PDF417 para C#. Sigue un tutorial paso a paso para generar texto de código
  extendido, configurar la apariencia y guardar la imagen.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- c# pdf417 barcode generator
language: es
lastmod: 2026-07-18
og_description: Crea un código de barras PDF417 en C# al instante. Esta guía muestra
  cómo usar el generador de códigos de barras PDF417 en C#, configurar el modo extendido
  y exportar un PNG.
og_image_alt: Generated PDF417 barcode image created with C# PDF417 barcode generator
og_title: Crear código de barras PDF417 en C# – Guía completa del generador
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create PDF417 barcode in C# using the C# PDF417 barcode generator.
    Follow a step‑by‑step tutorial to build extended codetext, set appearance, and
    save the image.
  headline: Create PDF417 Barcode in C# – Barcode Generator Guide
  type: TechArticle
- description: Create PDF417 barcode in C# using the C# PDF417 barcode generator.
    Follow a step‑by‑step tutorial to build extended codetext, set appearance, and
    save the image.
  name: Create PDF417 Barcode in C# – Barcode Generator Guide
  steps:
  - name: 1. Install the barcode library
    text: 'Open your terminal in the project folder and run:'
  - name: 2. Build the extended codetext
    text: 'PDF417 supports **extended encoding**, allowing you to mix different character
      sets in a single barcode. Below we create three segments:'
  - name: 3. Initialise the **C# PDF417 barcode generator**
    text: Now that we have a valid codetext string, we hand it to the generator. The
      `using` statement ensures the underlying resources are released automatically.
  - name: 4. Configure appearance and encoding mode
    text: 'The default settings give you a tiny barcode that might be hard to read.
      Let’s tweak a few parameters:'
  - name: 5. Save the barcode image
    text: Finally, write the image to disk. The library supports PNG, JPEG, BMP, and
      several vector formats—PNG is a safe default because it preserves crisp edges.
  - name: Handling Unicode and special characters
    text: When you feed Unicode symbols directly into a plain‑text barcode, the generator
      may fall back to a fallback encoding, resulting in garbled output. By using
      `AddECICodetext` you explicitly tell the encoder which character set to apply,
      eliminating guesswork. If you ever need to support **Arabic**, **
  - name: Adjusting error correction level
    text: 'PDF417 offers four error‑correction levels (0‑8). Higher levels increase
      resilience but also enlarge the barcode. Adjust it via:'
  - name: Scaling for print vs. screen
    text: 'For on‑screen display you might keep the default 96 dpi. For high‑resolution
      printing (300 dpi or more), set:'
  - name: Common pitfalls
    text: '- **Missing `using` directive** – Forgetting `using Aspose.BarCode.Encoding;`
      will cause `ECIEncodings` to be undefined. - **Directory not found** – The `Save`
      method won’t create intermediate folders; create them beforehand or use `Path.Combine`
      with `Environment.CurrentDirectory`. - **Wrong encode'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Crear código de barras PDF417 en C# – Guía del generador de códigos de barras
url: /es/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-barcode-generator-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear código de barras PDF417 en C# – Guía del generador de códigos de barras

¿Alguna vez necesitaste **crear un código de barras PDF417** en una aplicación C# pero no sabías por dónde empezar? No estás solo—muchos desarrolladores se encuentran con el mismo obstáculo cuando abordan por primera vez los códigos de barras bidimensionales. ¿La buena noticia? Con el **generador de códigos de barras PDF417 para C#** incorporado puedes generar un código de barras totalmente funcional con solo unas pocas líneas.

En este tutorial recorreremos todo el proceso: crear un codetext extendido que mezcle diferentes conjuntos de caracteres, configurar el generador con el estilo visual adecuado y, finalmente, guardar el código de barras como un archivo PNG. Al final tendrás un fragmento listo para usar que puedes insertar en cualquier proyecto .NET, además de consejos para manejar casos especiales como caracteres Unicode o anchos de módulo personalizados.

---

## Lo que necesitarás

Antes de sumergirnos, asegúrate de tener lo siguiente en tu máquina:

- **.NET 6.0** o posterior (el ejemplo también funciona con .NET Framework 4.6+)
- **Aspose.BarCode for .NET** (o cualquier biblioteca compatible que exponga `BarcodeGenerator`, `EncodeTypes.Pdf417`, etc.)
- Un editor de código—Visual Studio, Rider o incluso VS Code sirve
- Una carpeta en la que puedas escribir, porque el generador guardará el PNG allí

Eso es todo—no se requieren paquetes NuGet adicionales más allá de la propia biblioteca de códigos de barras.

---

## Guía paso a paso para **crear código de barras PDF417**

### 1. Instalar la biblioteca de códigos de barras

Abre tu terminal en la carpeta del proyecto y ejecuta:

```bash
dotnet add package Aspose.BarCode
```

El paquete agrega el espacio de nombres `Aspose.BarCode`, que contiene la clase `BarcodeGenerator` que utilizaremos a lo largo del tutorial.

### 2. Construir el codetext extendido

PDF417 admite **codificación extendida**, lo que permite mezclar diferentes conjuntos de caracteres en un solo código de barras. A continuación creamos tres segmentos:

- Un segmento Windows‑1251 (cirílico)
- Un segmento UTF‑8 que contiene caracteres Unicode (los kanjis japoneses para “perro” y “derecha”)
- Un segmento de texto plano

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;

// Step 1: Build the extended codetext for the PDF417 barcode
Pdf417ExtCodetextBuilder builder = new Pdf417ExtCodetextBuilder();

// Add a Win1251‑encoded segment
builder.AddECICodetext(ECIEncodings.Win1251, "Will");

// Add a UTF‑8 segment with Unicode characters
builder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");

// Add a plain‑text segment
builder.AddPlainCodetext("Plain text");

// Retrieve the combined codetext string
string extendedCodetext = builder.GetExtendedCodetext();
```

**Por qué es importante:**  
Si solo usas texto plano, estás limitado al subconjunto ASCII predeterminado. Al declarar explícitamente segmentos ECI (Extended Channel Interpretation) garantizas que los escáneres interpreten cada parte correctamente, sin importar el idioma o los símbolos involucrados.

### 3. Inicializar el **generador de códigos de barras PDF417 para C#**

Ahora que tenemos una cadena de codetext válida, la pasamos al generador. La instrucción `using` garantiza que los recursos subyacentes se liberen automáticamente.

```csharp
// Step 2: Create a PDF417 barcode generator using the extended codetext
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, extendedCodetext))
{
    // Configuration goes here (see next step)
}
```

### 4. Configurar apariencia y modo de codificación

Los ajustes predeterminados te dan un código de barras diminuto que puede ser difícil de leer. Ajustemos algunos parámetros:

- **X‑Dimension** – controla el ancho de cada módulo (tamaño de píxel)
- **EncodeMode** – indica al motor que trate la entrada como modo extendido
- **TwoDDisplayText** – texto legible opcional que se muestra debajo del código de barras

```csharp
    // Step 3: Configure barcode appearance and encoding mode
    generator.Parameters.Barcode.XDimension.Pixels = 15; // Wider modules for better scannability
    generator.Parameters.Barcode.Pdf417.EncodeMode = Pdf417EncodeMode.Extended; // Activate extended encoding
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended mode"; // Display text under the symbol
```

**Consejo profesional:** Si imprimes el código de barras en una impresora de etiquetas, aumenta `XDimension` a 20 px o más; a la mayoría de los escáneres les gusta un poco de espacio adicional.

### 5. Guardar la imagen del código de barras

Finalmente, escribe la imagen en disco. La biblioteca admite PNG, JPEG, BMP y varios formatos vectoriales—PNG es una opción segura porque conserva bordes nítidos.

```csharp
    // Step 4: Save the generated barcode image
    generator.Save("YOUR_DIRECTORY/Pdf417Extended.png", BarCodeImageFormat.Png);
}
```

Asegúrate de que `YOUR_DIRECTORY` exista y sea escribible. Después de ejecutar el programa deberías ver un archivo similar a la captura de pantalla a continuación.

![Código de barras PDF417 generado con el generador de códigos de barras PDF417 para C#](https://example.com/images/pdf417-extended.png "Código de barras PDF417 generado con el generador de códigos de barras PDF417 para C#")

---

## Uso del **generador de códigos de barras PDF417 para C#** – análisis profundo

### Manejo de Unicode y caracteres especiales

Cuando introduces símbolos Unicode directamente en un código de barras de texto plano, el generador puede recurrir a una codificación de respaldo, lo que produce una salida distorsionada. Al usar `AddECICodetext` le indicas explícitamente al codificador qué conjunto de caracteres aplicar, eliminando la conjetura. Si alguna vez necesitas soportar **árabe**, **hebreo** o **emoji**, simplemente elige el valor apropiado de `ECIEncodings`.

### Ajustar el nivel de corrección de errores

PDF417 ofrece cuatro niveles de corrección de errores (0‑8). Los niveles más altos aumentan la resistencia pero también agrandan el código de barras. Ajústalo mediante:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // Balanced level
```

### Escalado para impresión vs. pantalla

Para la visualización en pantalla puedes mantener los 96 dpi predeterminados. Para impresión de alta resolución (300 dpi o más), establece:

```csharp
generator.Parameters.ImageResolution = 300;
```

Eso asegura que el PNG guardado mantenga suficiente detalle para impresoras láser.

### Errores comunes

- **Falta la directiva `using`** – Olvidar `using Aspose.BarCode.Encoding;` hará que `ECIEncodings` no esté definido.
- **Directorio no encontrado** – El método `Save` no creará carpetas intermedias; créalas previamente o usa `Path.Combine` con `Environment.CurrentDirectory`.
- **Modo de codificación incorrecto** – Si dejas `EncodeMode` en `Pdf417EncodeMode.Auto`, la biblioteca puede tratar tu codetext extendido como texto plano, eliminando los marcadores ECI.

---

## Ejemplo completo, listo para ejecutar

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;

class Program
{
    static void Main()
    {
        // 1️⃣ Build extended codetext
        Pdf417ExtCodetextBuilder builder = new Pdf417ExtCodetextBuilder();
        builder.AddECICodetext(ECIEncodings.Win1251, "Will");
        builder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
        builder.AddPlainCodetext("Plain text");
        string extendedCodetext = builder.GetExtendedCodetext();

        // 2️⃣ Initialise generator with the extended codetext
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, extendedCodetext))
        {
            // 3️⃣ Configure appearance
            generator.Parameters.Barcode.XDimension.Pixels = 15;
            generator.Parameters.Barcode.Pdf417.EncodeMode = Pdf417EncodeMode.Extended;
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;
            generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended mode";

            // 4️⃣ Save to PNG (ensure the folder exists)
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "Pdf417Extended.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }

        Console.WriteLine("PDF417 barcode generated successfully!");
    }
}
```

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo crear un código de barras – PDF417 compacto con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cómo crear codetext extendido para dotcode con Aspose.BarCode para .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Crear imagen de código de barras c# – Configurar filas y columnas de Codablock F](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}