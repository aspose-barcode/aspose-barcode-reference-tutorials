---
category: general
date: 2026-07-27
description: Crear imagen de código de barras omnidireccional usando Aspose.BarCode.
  Aprende cómo generar códigos de barras con Aspose, ajustar la relación de aspecto
  y guardar archivos PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional barcode image
- generate barcode with aspose
language: es
lastmod: 2026-07-27
og_description: Crea una imagen de código de barras omnidireccional usando Aspose.
  Sigue esta guía para generar códigos de barras con Aspose, ajustar las proporciones
  y exportar PNG.
og_image_alt: Screenshot of two omnidirectional barcode images with different aspect
  ratios
og_title: Crear imagen de código de barras omnidireccional con Aspose – Paso a paso
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  headline: Create Omnidirectional Barcode Image with Aspose – Full Guide
  type: TechArticle
- description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  name: Create Omnidirectional Barcode Image with Aspose – Full Guide
  steps:
  - name: 1. Different Image Formats
    text: 'Aspose supports BMP, JPEG, TIFF, and SVG in addition to PNG. Swap the enum
      value:'
  - name: 2. Customizing Colors
    text: 'You might need a white barcode on a dark background. Set `ForeColor` and
      `BackColor`:'
  - name: 3. Handling Invalid Aspect Ratios
    text: 'Aspose validates the range (usually 5‑50). If you pass an out‑of‑range
      value, an `ArgumentException` is thrown. Wrap the save call in a try‑catch to
      give a friendly message:'
  - name: 4. Batch Generation
    text: When you have a list of GTINs, loop over them, update `CodeText`, and save
      each file with a unique name. The generator object can be reused, keeping memory
      usage low.
  type: HowTo
tags:
- barcode
- Aspose
- C#
- image-generation
title: Crear imagen de código de barras omnidireccional con Aspose – Guía completa
url: /es/python-java/general/create-omnidirectional-barcode-image-with-aspose-full-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear imagen de código de barras omnidireccional con Aspose – Guía completa

¿Alguna vez necesitaste **crear una imagen de código de barras omnidireccional** pero no sabías qué biblioteca elegir? No eres el único. En muchos proyectos de logística y retail, el formato DataBar Stacked Omnidirectional es la clave para una codificación compacta y de alta densidad.  

¿La buena noticia? Con **Aspose.BarCode** puedes generar ese código de barras en unas pocas líneas, ajustar su relación de aspecto y guardar el PNG directamente en disco. A continuación verás exactamente cómo **generar códigos de barras con Aspose**, por qué cada configuración es importante y a qué prestar atención al cambiar la relación de aspecto.

---

## Qué cubre este tutorial

Recorreremos todo el ciclo de vida:

1. Configurar la carpeta de salida.  
2. Instanciar un generador DataBar Stacked Omnidirectional.  
3. Configurar dimensiones de píxel y relaciones de aspecto.  
4. Guardar el código de barras como archivos PNG.  
5. Extender el ejemplo a otros formatos y casos límite.

Al final tendrás una aplicación de consola C# lista para ejecutar que genera dos imágenes de código de barras distintas. Sin herramientas externas, solo código puro de Aspose.

**Requisitos previos**

- SDK de .NET 6.0 o superior (el código también funciona en .NET Framework 4.7.2).  
- Paquete NuGet Aspose.BarCode for .NET (`Install-Package Aspose.BarCode`).  
- Una carpeta en disco donde se puedan escribir las imágenes.

Si ya cuentas con eso, vamos al grano.

---

## Paso 1: Preparar la carpeta de salida

Lo primero—indicar al programa dónde guardar los archivos PNG. Codificar una ruta funciona para una demostración, pero en producción probablemente la leerías de la configuración.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Define the folder where the images will be saved
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);   // ensures the folder exists
```

*Por qué es importante:* `Directory.CreateDirectory` es idempotente; no lanzará excepción si la carpeta ya existe, evitando la necesidad de un bloque try‑catch.

---

## Paso 2: Crear un generador DataBar Stacked Omnidirectional

Ahora iniciamos el generador con el tipo de codificación específico y datos de ejemplo. La cadena `"(01)12345678901231"` sigue la sintaxis del Identificador de Aplicación GS1 para un GTIN de 14 dígitos.

```csharp
        // Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

*Explicación:* `EncodeTypes.DatabarStackedOmniDirectional` indica a Aspose que use la variante omnidireccional, legible desde cualquier dirección—ideal para etiquetas pequeñas que pueden rotarse.

---

## Paso 3: Establecer parámetros comunes del código de barras

Antes de renderizar nada, definimos el tamaño del elemento más pequeño (X‑Dimension). Un valor de **2 píxeles** produce una imagen nítida sin inflar el tamaño del archivo.

```csharp
        // Step 3: Set common barcode parameters (pixel size of the smallest element)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Consejo:* Si necesitas mayor resolución para impresión, aumenta esto a 3 o 4. Solo recuerda que dimensiones X mayores incrementan ancho y alto proporcionalmente.

---

## Paso 4: Generar y guardar con Relación de aspecto 15

La familia DataBar permite ajustar la **relación de aspecto**, que controla la proporción altura‑ancho. Una relación de **15** es el valor predeterminado más común para códigos omnidireccionales.

```csharp
        // Step 4: Generate a barcode with an aspect ratio of 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
```

*Lo que observarás:* Un código de barras relativamente alto que aún cabe cómodamente en una etiqueta de 2 × 1 cm. El formato PNG conserva calidad sin pérdida, ideal para procesamiento posterior o impresión.

---

## Paso 5: Cambiar la relación de aspecto a 30 y guardar de nuevo

¿Quieres un código más ancho? Simplemente modifica la propiedad `AspectRatio` y llama a `Save` nuevamente. No es necesario recrear el generador.

```csharp
        // Step 5: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
    }
}
```

*¿Por qué reutilizar el mismo generador?* Los objetos Aspose son ligeros; cambiar una propiedad y volver a guardar es más rápido que construir una nueva instancia, y garantiza que los mismos ajustes de codificación (p. ej., X‑Dimension) permanezcan consistentes.

---

## Ejemplo completo funcionando

Juntándolo todo, aquí tienes el programa completo y autónomo que puedes copiar‑pegar en un nuevo proyecto de consola.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // Initialize generator with omnidirectional DataBar
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Common settings
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // First image – aspect ratio 15
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio15.png");

        // Second image – aspect ratio 30
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio30.png");
    }
}
```

**Salida esperada**

Al ejecutar el programa se crea una subcarpeta `Barcodes` que contiene:

- `DatabarAspectRatio15.png` – aspecto más alto, estilo clásico.  
- `DatabarAspectRatio30.png` – más plano, mejor para etiquetas anchas.

Ambas imágenes codifican el mismo GTIN; solo difieren en sus proporciones visuales.

---

## Extender el ejemplo (casos límite y variaciones)

### 1. Diferentes formatos de imagen

Aspose admite BMP, JPEG, TIFF y SVG además de PNG. Cambia el valor del enum:

```csharp
barcodeGenerator.Save(Path.Combine(outputFolder, "Databar.svg"),
                      BarCodeImageFormat.Svg);
```

SVG es vectorial, lo que permite escalar sin perder nitidez—útil para aplicaciones web responsivas.

### 2. Personalizar colores

Puede que necesites un código de barras blanco sobre fondo oscuro. Configura `ForeColor` y `BackColor`:

```csharp
barcodeGenerator.Parameters.Barcode.ForeColor = System.Drawing.Color.White;
barcodeGenerator.Parameters.Barcode.BackColor = System.Drawing.Color.Black;
```

### 3. Manejo de relaciones de aspecto inválidas

Aspose valida el rango (usualmente 5‑50). Si pasas un valor fuera de ese rango, se lanza una `ArgumentException`. Envuelve la llamada a `Save` en un try‑catch para ofrecer un mensaje amigable:

```csharp
try
{
    barcodeGenerator.Save(...);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid aspect ratio: {ex.Message}");
}
```

### 4. Generación por lotes

Cuando tienes una lista de GTINs, recórrelos, actualiza `CodeText` y guarda cada archivo con un nombre único. El objeto generador puede reutilizarse, manteniendo bajo el consumo de memoria.

---

## Errores comunes y consejos profesionales

- **Nunca olvides establecer `XDimension`** antes de guardar; el valor predeterminado (0.33 mm) puede producir imágenes borrosas en pantallas de baja resolución.  
- **La relación de aspecto es altura‑ancho**, no al revés. Un número mayor hace que el código sea *más corto* verticalmente.  
- **Rutas de archivo:** Usa `Path.Combine` para evitar problemas con separadores específicos de la plataforma—especialmente si tu código se ejecuta en contenedores Linux.  
- **Licenciamiento:** Aspose.BarCode es comercial. En modo de prueba aparece una marca de agua en la imagen. Registra una licencia pronto para evitar sorpresas en producción.

---

## Conclusión

Ahora sabes cómo **crear una imagen de código de barras omnidireccional** usando Aspose, ajustar la relación de aspecto y exportar archivos PNG—todo en menos de 30 líneas de C#. Este tutorial mostró el proceso paso a paso, explicó por qué cada ajuste es relevante y cubrió extensiones como formatos diferentes, colores y procesamiento por lotes.

¿Listo para el siguiente reto? Prueba generar códigos QR, incrustar el código de barras en un PDF o integrar la salida en una API ASP.NET Core. Los mismos principios de **generar códigos de barras con Aspose** se aplican a todos los tipos de códigos, así que puedes reutilizar lo aprendido hoy.

¿Tienes preguntas o quieres compartir tus propias personalizaciones? Deja un comentario abajo—¡feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques alternativos en tus propios proyectos.

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Create Barcode Aspose Java - Adjust Image Quality](/barcode/english/java/image-manipulation/adjusting-image-quality-barcode/)
- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}