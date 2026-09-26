---
category: general
date: 2026-09-26
description: Aprende a crear códigos de barras Planet en C# rápidamente. Esta guía
  cubre códigos de barras Planet rellenos y vacíos, configuraciones de dimensión X
  y exportación de imágenes.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode C#
- filled planet barcode
- empty planet barcode
- barcode generator parameters
language: es
lastmod: 2026-09-26
og_description: Crear código de barras Planet en C# con un ejemplo completo. Generar
  códigos de barras Planet tanto rellenos como vacíos, establecer el ancho de la barra
  y guardarlos como PNG.
og_image_alt: Screenshot showing generated filled and empty planet barcode PNG files
og_title: Crear imágenes de códigos de barras planetarios en C# – guía paso a paso
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create planet barcode in C# quickly. This guide covers
    filled and empty Planet barcodes, X‑dimension settings, and image export.
  headline: How to create planet barcode images in C# with BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Cómo crear imágenes de códigos de barras planetarios en C# con BarcodeGenerator
url: /es/python-java/general/how-to-create-planet-barcode-images-in-c-with-barcodegenerat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear imágenes de códigos de barras Planet en C# con BarcodeGenerator

Si necesita **crear códigos de barras planet** en una aplicación .NET, este tutorial le muestra los pasos exactos. Aprenderá cómo generar tanto un código de barras Planet relleno como uno vacío, ajustar el ancho de las barras y exportar los resultados como archivos PNG, todo con la biblioteca Aspose.BarCode para .NET.

Generar una solución **Planet barcode C#** es sencillo una vez que comprende los **parámetros del generador de códigos de barras** clave. En las secciones siguientes, recorreremos el código completo y ejecutable, explicaremos por qué cada configuración es importante y señalaremos los errores comunes para que pueda evitarlos en el primer intento.

## Requisitos previos

* SDK de .NET 6.0 o posterior instalado.
* Visual Studio 2022 (o cualquier IDE de C# que prefiera).
* El paquete NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`) añadido a su proyecto.

Puede agregar el paquete mediante la consola del Administrador de paquetes NuGet:

```bash
dotnet add package Aspose.BarCode
```

## Paso 1: Configurar el BarcodeGenerator

La clase `BarcodeGenerator` es el punto de entrada para todas las tareas de creación de códigos de barras. Requiere dos argumentos: el tipo de código de barras (`EncodeTypes.Planet`) y los datos a codificar.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PlanetBarcodeDemo
{
    static void Main()
    {
        // Create a generator for a filled Planet barcode
        BarcodeGenerator filledPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*Por qué es importante:* Instanciar el generador con `EncodeTypes.Planet` indica a la biblioteca que use la simbología **Planet barcode**, que se utiliza comúnmente para servicios postales en algunos países. La cadena `"123456"` es la carga útil que aparecerá en el código de barras.

## Paso 2: Configurar la dimensión X (ancho de barra)

La dimensión X controla el ancho físico de cada barra. Un valor típico para renderizado en pantalla es 4 píxeles, pero puede ajustarlo para cumplir con los requisitos de impresión.

```csharp
        // Define the bar width (X dimension) in pixels
        filledPlanet.Parameters.Barcode.XDimension.Pixels = 4;
```

*Por qué es importante:* Configurar `XDimension.Pixels` garantiza que el código de barras generado no sea ni demasiado delgado (causando fallos de escaneo) ni demasiado grueso (desperdiciando espacio). La misma configuración se reutilizará para el código de barras vacío.

## Paso 3: Guardar el código de barras Planet relleno

Exporte el código de barras a un archivo PNG usando el método `Save`. El enumerado `BarCodeImageFormat.Png` indica a la biblioteca que produzca una imagen sin pérdida adecuada para procesamiento posterior.

```csharp
        // Save the filled barcode as a PNG image
        filledPlanet.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

Después de ejecutar el programa, encontrará `PostalPlanetFilledBars.png` en la carpeta de salida. Ábralo para verificar que las barras estén sólidas (rellenas).

## Paso 4: Crear un generador para un código de barras Planet vacío

Un **código de barras planet vacío** muestra los mismos datos pero con barras sin rellenar (blancas). Esto es útil para diseños visuales que superponen el código de barras sobre fondos de color.

```csharp
        // Create a generator for an empty Planet barcode (unfilled bars)
        BarcodeGenerator emptyPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

La llamada al constructor es idéntica a la versión rellena; la diferencia está en el parámetro que cambiaremos a continuación.

## Paso 5: Reutilizar la misma dimensión X

Para mantener el tamaño visual consistente, aplique el mismo ancho de barra al código de barras vacío.

```csharp
        // Use the same bar width as before
        emptyPlanet.Parameters.Barcode.XDimension.Pixels = 4;
```

Reutilizar los **parámetros del generador de códigos de barras** garantiza que ambas imágenes se alineen perfectamente cuando se coloquen lado a lado.

## Paso 6: Cambiar a barras sin rellenar

La bandera `FilledBars` determina si las barras se renderizan como negro sólido (predeterminado) o blanco transparente.

```csharp
        // Configure the generator to produce empty (unfilled) bars
        emptyPlanet.Parameters.Barcode.FilledBars = false;
```

*Por qué es importante:* Configurar `FilledBars = false` invierte el modo de renderizado, que es la diferencia clave entre un código de barras Planet relleno y uno vacío.

## Paso 7: Guardar el código de barras Planet vacío

Finalmente, exporte la versión vacía a PNG.

```csharp
        // Save the empty barcode as a PNG image
        emptyPlanet.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

Al ejecutar el programa, aparecen dos archivos:

* `PostalPlanetFilledBars.png` – barras negras sólidas.
* `PostalPlanetEmptyBars.png` – barras transparentes (sin rellenar).

Ambas imágenes contienen los mismos datos (`123456`) y comparten la misma dimensión X, lo que las hace intercambiables en la mayoría de los escenarios de UI.

## Ejemplo completo y ejecutable

Juntando todo, aquí está el archivo fuente completo que puede copiar y pegar en un nuevo proyecto de consola:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PlanetBarcodeDemo
{
    static void Main()
    {
        // ----------- Filled Planet barcode -----------
        BarcodeGenerator filledPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        filledPlanet.Parameters.Barcode.XDimension.Pixels = 4;
        filledPlanet.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // ----------- Empty Planet barcode ------------
        BarcodeGenerator emptyPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        emptyPlanet.Parameters.Barcode.XDimension.Pixels = 4;
        emptyPlanet.Parameters.Barcode.FilledBars = false;
        emptyPlanet.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

**Salida esperada**

Ejecutar el programa crea dos archivos PNG en el directorio de trabajo del ejecutable. Ábralos con cualquier visor de imágenes:

* **Versión rellena** – barras oscuras y sólidas que son fácilmente legibles por escáneres estándar.
* **Versión vacía** – las barras aparecen como huecos blancos sobre un fondo negro, útil para efectos de superposición.

## Problemas comunes y consejos profesionales

| Problema | Por qué ocurre | Cómo solucionarlo |
|----------|----------------|-------------------|
| Las barras se ven demasiado finas | Dimensión X dejada en el valor predeterminado (1 píxel) | Establezca `XDimension.Pixels` a 3‑5 píxeles para uso en pantalla; aumente para impresiones de alta resolución. |
| El código de barras vacío aparece completamente negro | `FilledBars` no se establece en `false` | Asegúrese de que `emptyPlanet.Parameters.Barcode.FilledBars = false;` se ejecute **después** de configurar la dimensión X. |
| Falta el archivo PNG | La ruta de salida es incorrecta o el directorio no existe | Proporcione una ruta completa (`@"C:\Barcodes\PostalPlanetFilledBars.png"`) o cree el directorio previamente con `Directory.CreateDirectory`. |
| El código de barras no se escanea | La cadena de datos contiene caracteres ilegales para la simbología Planet | Los códigos de barras Planet aceptan solo cargas numéricas; valide la entrada con `int.TryParse`. |

**Consejo profesional:** Si necesita incrustar el código de barras en un PDF, puede cargar el PNG generado en un `PdfDocument` usando Aspose.PDF, o agregar directamente el código de barras como un flujo de imagen sin escribirlo en disco.

## Próximos pasos

Ahora que puede **crear imágenes de códigos de barras planet**, considere explorar estos temas relacionados:

* **Planet barcode C#** – personalizar colores, agregar texto legible por humanos o incrustar el código de barras en un PDF.
* **Barcode generator parameters** – ajustar el nivel de corrección de errores, zona silenciosa o rotación.
* **Batch generation** – iterar sobre una lista de códigos postales para producir un archivo zip de PNGs.
* **Alternative formats** – exportar a SVG o JPEG para entrega amigable en la web.

Experimente con diferentes valores de `XDimension` y la bandera `FilledBars` para ver cómo afectan la fiabilidad del escaneo y el estilo visual. Cuando esté listo, integre el código de generación en su API web o aplicación de escritorio para automatizar la creación de códigos de barras postales al instante.

---

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarle a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en sus propios proyectos.

- [Crear código de barras Planet en C# – Guía completa paso a paso](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Generador de códigos de barras C# – crear código de barras Planet y ejemplo RM4SCC](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)
- [Generar código de barras postal en C# – Guía completa con código de barras Planet](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}