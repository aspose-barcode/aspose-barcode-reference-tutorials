---
category: general
date: 2026-07-27
description: Crea rápidamente una imagen de código de barras planetario. Aprende cómo
  generar códigos de barras planetarios con C# y personaliza las barras llenas o vacías.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode image
- how to generate planet barcode
- planet barcode C#
- barcode X‑dimension
- filled vs empty bars
language: es
lastmod: 2026-07-27
og_description: Crea una imagen de código de barras planetario en segundos. Sigue
  esta guía para aprender cómo generar el código de barras planetario, ajustar la
  dimensión X y cambiar entre barras llenas y vacías.
og_image_alt: Screenshot showing a create planet barcode image with filled bars
og_title: Crear imagen de código de barras planetario – Tutorial completo de C#
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: create planet barcode image quickly. Learn how to generate planet barcode
    with C# and customize filled or empty bars.
  headline: create planet barcode image – Step‑by‑Step Guide
  type: TechArticle
- description: create planet barcode image quickly. Learn how to generate planet barcode
    with C# and customize filled or empty bars.
  name: create planet barcode image – Step‑by‑Step Guide
  steps:
  - name: Why the X‑dimension matters
    text: The X‑dimension controls how wide each tiny bar (or “module”) is. A value
      of **4 pixels** yields a barcode that’s clear on screen and prints nicely on
      standard label printers. If you need a denser image for a high‑resolution print,
      bump the value up to 6 or 8.
  - name: Expected output
    text: Open the resulting `PostalPlanetFilledBars.png` and you should see a classic
      Planet barcode—solid vertical bars with a quiet zone on each side. It looks
      just like the example you’d find on a postal envelope.
  - name: What “FilledBars = false” does
    text: Setting `FilledBars` to `false` tells the rendering engine to draw only
      the bar outlines. This is useful when you need a lighter‑weight image for on‑screen
      display or when a printing guideline explicitly requires the empty style.
  - name: Expected output
    text: The `PostalPlanetEmptyBars.png` file shows the same pattern as before, but
      each bar is a thin line instead of a solid block. It’s perfect for low‑contrast
      printing on colored paper.
  - name: When to use RM4SCC
    text: RM4SCC is the Dutch “Postcode” barcode. If you’re building a multi‑country
      logistics platform, having both Planet and RM4SCC generators at hand saves you
      a lot of boilerplate code.
  - name: What if I need a different image format?
    text: Just swap `BarCodeImageFormat.Png` for `Jpeg`, `Bmp`, or `Gif`. The library
      handles the conversion automatically.
  - name: How do I change the barcode height?
    text: Use `planetFilled.Parameters.Barcode.BarHeight = 50; // height in points`
      (or pixels, depending on the library version). Higher values give you a taller
      barcode, which can improve scan reliability on low‑resolution scanners.
  - name: Can I embed the barcode directly into a PDF?
    text: Absolutely. The `Save` method returns a `byte[]` if you call the overload
      that writes to a stream. Feed that stream into a PDF generation library (e.g.,
      iTextSharp) and you’ve got a fully‑automated mailing label.
  - name: What if the data string contains non‑numeric characters?
    text: 'Planet and RM4SCC expect **numeric only** payloads. Passing letters will
      throw an `ArgumentException`. Validate your input first:'
  - name: Does the X‑dimension affect scanning speed?
    text: A larger X‑dimension creates a more robust barcode, which generally improves
      scanning speed, especially on low‑quality scanners. However, it also increases
      the physical size of the label, so balance readability with space constraints.
  type: HowTo
tags:
- barcode
- C#
- imaging
title: Crear imagen de código de barras planetario – Guía paso a paso
url: /es/python-java/general/create-planet-barcode-image-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# crear imagen de código de barras planet – Tutorial completo en C#

¿Alguna vez te has preguntado **cómo generar un código de barras planet** para un sistema de correo o una aplicación de logística? No eres el primero que se lo ha planteado. En este tutorial recorreremos todo lo que necesitas para **crear imágenes de código de barras planet**, desde los conceptos básicos de la clase `BarcodeGenerator` hasta ajustar la dimensión X y cambiar las barras rellenas por vacías.

También echaremos un vistazo a una simbología relacionada—RM4SCC—para que veas cómo funciona el mismo patrón con otros códigos de barras postales. Al final, tendrás tres fragmentos listos para ejecutar que generan archivos PNG que puedes incorporar directamente a tu proyecto.

## Lo que necesitarás

- .NET 6.0 o posterior (el código también funciona en .NET Framework 4.7+)
- Una referencia a **Aspose.BarCode** (o cualquier biblioteca que exponga `BarcodeGenerator`, `EncodeTypes`, `BarCodeImageFormat`)
- Un IDE con el que te sientas cómodo—Visual Studio, Rider o VS Code sirven
- Una carpeta donde puedas escribir imágenes (reemplaza `YOUR_DIRECTORY` en los ejemplos)

Eso es todo. No necesitas paquetes NuGet adicionales más allá de la propia biblioteca de códigos de barras.

---

## Paso 1: Configura el proyecto y las importaciones

Lo primero, creemos una pequeña aplicación de consola para poder ejecutar el código al instante.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll call helper methods here (see later)
            GeneratePlanetFilledBars();
            GeneratePlanetEmptyBars();
            GenerateRM4SCCFilledBars();
        }
```

> **Consejo profesional:** Mantén tu método `Main` ordenado; delega cada escenario a su propio método. Así el código es más fácil de leer y refleja los tres ejemplos del fragmento original.

---

## Paso 2: **crear imagen de código de barras planet** con barras rellenas por defecto

La simbología Planet es utilizada por muchos servicios postales para números de seguimiento. Para **crear una imagen de código de barras planet** con las habituales barras sólidas, sigue estas tres líneas:

```csharp
        static void GeneratePlanetFilledBars()
        {
            // 1️⃣ Create a generator for the Planet symbology with data "123456"
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Set the X‑dimension (module width) to 4 pixels for better visibility
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the barcode as a PNG image
            planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
        }
```

### Por qué la dimensión X es importante
La dimensión X controla cuán ancha es cada barra diminuta (o “módulo”). Un valor de **4 píxeles** produce un código de barras que se ve claro en pantalla y se imprime bien en impresoras de etiquetas estándar. Si necesitas una imagen más densa para una impresión de alta resolución, aumenta el valor a 6 u 8.

### Resultado esperado
Abre el archivo `PostalPlanetFilledBars.png` resultante y deberías ver un clásico código de barras Planet—barras verticales sólidas con una zona silenciosa a cada lado. Se ve exactamente como el ejemplo que encontrarías en un sobre postal.

---

## Paso 3: **crear imagen de código de barras planet** con barras vacías

A veces la especificación postal requiere un estilo de *barras vacías*, donde las barras son contornos en lugar de rellenos sólidos. Cambiar a ese modo es tan simple como modificar una propiedad.

```csharp
        static void GeneratePlanetEmptyBars()
        {
            // 1️⃣ Create the generator (same data as before)
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Keep the X‑dimension consistent
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Disable filled bars → we get an empty‑bar representation
            planetEmpty.Parameters.Barcode.FilledBars = false;

            // 4️⃣ Save the PNG
            planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
        }
```

### Qué hace “FilledBars = false”
Establecer `FilledBars` a `false` indica al motor de renderizado que dibuje solo los contornos de las barras. Esto es útil cuando necesitas una imagen más ligera para visualización en pantalla o cuando una directriz de impresión exige explícitamente el estilo vacío.

### Resultado esperado
El archivo `PostalPlanetEmptyBars.png` muestra el mismo patrón que antes, pero cada barra es una línea fina en lugar de un bloque sólido. Es perfecto para impresiones de bajo contraste sobre papel de color.

---

## Paso 4: Generar un código de barras RM4SCC (Bonus)

Aunque nuestro foco principal es la simbología Planet, la misma API te permite **crear imágenes de código de barras planet**‑like para otros códigos postales. Así es como **generar código de barras estilo planet** para RM4SCC:

```csharp
        static void GenerateRM4SCCFilledBars()
        {
            // 1️⃣ Create a generator for the RM4SCC symbology
            BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

            // 2️⃣ Align X‑dimension with the other examples
            rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the image
            rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
        }
    }
}
```

### Cuándo usar RM4SCC
RM4SCC es el código de barras “Postcode” de los Países Bajos. Si estás construyendo una plataforma logística multipaís, tener generadores tanto para Planet como para RM4SCC a mano te ahorra mucho código repetitivo.

---

## Preguntas frecuentes y casos límite

### ¿Y si necesito un formato de imagen diferente?
Simplemente cambia `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` o `Gif`. La biblioteca gestiona la conversión automáticamente.

### ¿Cómo cambio la altura del código de barras?
Usa `planetFilled.Parameters.Barcode.BarHeight = 50; // height in points` (o píxeles, según la versión de la biblioteca). Valores más altos generan un código de barras más alto, lo que puede mejorar la fiabilidad de escaneo en escáneres de baja resolución.

### ¿Puedo incrustar el código de barras directamente en un PDF?
Claro. El método `Save` devuelve un `byte[]` si llamas a la sobrecarga que escribe en un stream. Pasa ese stream a una biblioteca de generación de PDF (p. ej., iTextSharp) y tendrás una etiqueta de correo totalmente automatizada.

### ¿Qué pasa si la cadena de datos contiene caracteres no numéricos?
Planet y RM4SCC esperan **solo datos numéricos**. Pasar letras lanzará una `ArgumentException`. Valida tu entrada primero:

```csharp
if (!Regex.IsMatch(data, @"^\d+$"))
    throw new ArgumentException("Planet barcode data must be numeric.");
```

### ¿Afecta la dimensión X a la velocidad de escaneo?
Una dimensión X mayor crea un código de barras más robusto, lo que generalmente mejora la velocidad de escaneo, especialmente en escáneres de baja calidad. Sin embargo, también aumenta el tamaño físico de la etiqueta, así que equilibra legibilidad y limitaciones de espacio.

---

## Ejemplo completo (Los tres métodos)

A continuación tienes el programa completo que puedes copiar‑pegar en un nuevo proyecto de consola. Sustituye `YOUR_DIRECTORY` por una ruta absoluta o relativa a la que tu aplicación pueda escribir.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            GeneratePlanetFilledBars();
            GeneratePlanetEmptyBars();
            GenerateRM4SCCFilledBars();

            Console.WriteLine("All barcode images have been saved.");
        }

        static void GeneratePlanetFilledBars()
        {
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
            planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
        }

        static void GeneratePlanetEmptyBars()
        {
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
            planetEmpty.Parameters.Barcode.FilledBars = false;
            planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
        }

        static void GenerateRM4SCCFilledBars()
        {
            BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
        }
    }
}
```

Ejecuta el programa, abre los tres archivos PNG y verás exactamente las imágenes descritas anteriormente. No se requiere configuración adicional.

---

## Resumen y próximos pasos

Hemos cubierto **cómo generar imágenes de código de barras planet** desde cero, alternando entre estilos sólido y contorno, y extendiendo el mismo enfoque a RM4SCC. Los puntos clave:

1. Instanciar `BarcodeGenerator` con el `EncodeTypes` y los datos correctos.  
2. Ajustar `XDimension.Pixels` para controlar el ancho de las barras.  
3. Usar `FilledBars = false` para la variante de barra vacía.  
4. Guardar el resultado en el formato de imagen que prefieras.

Ahora que puedes **crear imágenes de código de barras planet**, considera estas ideas de seguimiento:

- **Generación por lotes**: Recorrer un CSV de números de seguimiento y generar un PNG para cada uno.  
- **Tamaño dinámico**: Exponer la dimensión X y la altura de la barra como parámetros de configuración en una API web.  
- **Integración con impresoras de etiquetas**: Enviar los bytes PNG directamente a una impresora compatible con ZPL para crear etiquetas al vuelo.

Siéntete libre de experimentar—cambia la cadena de datos, prueba distintas dimensiones o combina el código de barras con un código QR en la misma etiqueta. La biblioteca de códigos de barras es lo suficientemente flexible para manejar todo eso.

¿Tienes un escenario complicado y no sabes cómo abordarlo? Deja un comentario abajo y lo resolveremos juntos. ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Create barcode image c# – Configure Codablock F Rows & Columns](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}