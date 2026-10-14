---
category: general
date: 2026-10-08
description: Crea un código de barras planetario vacío con C# y aprende cómo generar
  un código de barras postal usando Aspose.BarCode. Código paso a paso y consejos
  incluidos.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create empty planet barcode
- how to generate postal barcode
- Aspose.BarCode C#
- postal barcode example
- barcode XDimension setting
language: es
lastmod: 2026-10-08
og_description: Crear un código de barras planetario vacío con Aspose.BarCode en C#
  y ver cómo generar imágenes de códigos de barras postales para aplicaciones de envío.
og_image_alt: Screenshot of generated empty Planet barcode and filled RM4SCC barcode
og_title: Crear código de barras planeta vacío – Guía de código de barras postal en
  C#
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Create empty planet barcode with C# and learn how to generate postal
    barcode using Aspose.BarCode. Step‑by‑step code and tips included.
  headline: Create empty planet barcode, generate postal barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- postal
title: Crear código de barras de planeta vacío, generar código de barras postal en
  C#
url: /es/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear código de barras planetario vacío, generar código de barras postal en C#

Si necesita **crear un código de barras planetario vacío** para un sistema de correo, esta guía le muestra exactamente cómo hacerlo con Aspose.BarCode para .NET. También aprenderá **cómo generar códigos de barras postales** en imágenes como Planet y RM4SCC, personalizar el ancho de las barras y controlar la opción de barras rellenas.

Generar códigos de barras postales no requiere una biblioteca gráfica separada. El SDK de Aspose.BarCode proporciona una única API que maneja la codificación, el renderizado de imágenes y la selección del formato de imagen. Al final de este tutorial tendrá tres archivos PNG listos para usar:

* `PostalPlanetEmptyBars.png` – un código de barras Planet con barras vacías  
* `PostalPlanetFilledBars.png` – el código de barras Planet con barras rellenas por defecto  
* `PostalRM4SCCFilledBars.png` – un código de barras RM4SCC con barras rellenas  

Puede colocar estos archivos en cualquier plantilla de etiqueta de correo, imprimirlos en sobres o enviarlos a un servicio de terceros.

## Requisitos previos

* .NET 6.0 o posterior (el código también funciona con .NET Framework 4.7+).  
* Visual Studio 2022 o cualquier IDE de C#.  
* Aspose.BarCode for .NET – instalar vía NuGet:

```bash
dotnet add package Aspose.BarCode
```

No se requieren dependencias adicionales.

## Crear código de barras planetario vacío con Aspose.BarCode

La simbología Planet forma parte de la familia de códigos de barras del Servicio Postal de los Estados Unidos (USPS). De forma predeterminada el SDK dibuja barras **rellenas**. Para **crear un código de barras planetario vacío**, desactive la bandera `FilledBars`.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 1 – instantiate a Planet barcode generator with the data to encode.
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Step 2 – set the width of a single bar. XDimension defines the pixel size of one bar.
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Step 3 – disable the FilledBars option to get empty (hollow) bars.
planetEmpty.Parameters.Barcode.FilledBars = false;

// Step 4 – save the image. The PNG format is widely supported by printers and browsers.
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**Por qué funciona esto:**  
`EncodeTypes.Planet` indica al generador que use la simbología Planet. `XDimension.Pixels` controla el ancho físico de cada barra, lo cual es crucial para los escáneres postales que esperan un tamaño de módulo específico. Establecer `FilledBars` en `false` indica al renderizador que dibuje solo el contorno de cada barra, produciendo la apariencia *vacía* requerida por algunos estándares de correo.

### Salida esperada

Encontrará `PostalPlanetEmptyBars.png` en la carpeta de destino. La imagen muestra un código de barras Planet donde cada barra es un contorno en lugar de un rectángulo sólido.

![Ejemplo de código de barras Planet vacío](empty-planet.png){: .align-center alt="Crear código de barras planetario vacío – ejemplo de un código de barras Planet con barras vacías"}

## Cómo generar imágenes de códigos de barras postales (versión rellena)

La mayoría de los flujos de trabajo postales utilizan la versión de barras rellenas por defecto. La misma API puede generar un código de barras Planet relleno y un código de barras RM4SCC con solo unas pocas líneas de código.

```csharp
// Filled Planet barcode (default behavior)
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// RM4SCC barcode – another USPS format that always uses filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
```

**Por qué podría necesitar RM4SCC:**  
RM4SCC es el código de barras USPS más reciente que codifica los mismos datos que Planet pero con mayor densidad. Algunos transportistas requieren RM4SCC para obtener descuentos por envíos masivos. El código anterior demuestra cómo **generar códigos de barras postales** para ambos estándares sin cambiar el flujo de trabajo general.

### Salida esperada

* `PostalPlanetFilledBars.png` – un clásico código de barras Planet con barras rellenas.  
* `PostalRM4SCCFilledBars.png` – un código de barras RM4SCC con barras rellenas, visualmente similar pero con un espaciado más estrecho.

Ambos archivos pueden abrirse en cualquier visor de imágenes para verificar los patrones de barras.

## Ajustar el ancho de la barra para diferentes resoluciones de impresión

Los escáneres postales a menudo especifican un ancho mínimo de módulo (p. ej., 0.013 pulgadas). Si su impresora funciona a 300 dpi, un módulo de 4 píxeles corresponde a 0.013 pulgadas. Ajuste el valor `XDimension.Pixels` para que coincida con su hardware:

| Módulo deseado (pulgadas) | DPI | Píxeles necesarios (`XDimension`) |
|---------------------------|-----|-----------------------------------|
| 0.013                     | 300 | 4                                 |
| 0.013                     | 600 | 8                                 |
| 0.015                     | 300 | 5                                 |

**Consejo profesional:** Siempre pruebe un

## ¿Qué debería aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos con explicaciones paso a paso para ayudarle a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en sus propios proyectos.

- [Cómo crear código de barras Planet PNG con C# – guía paso a paso](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/)
- [Generar código de barras postal en C# – guía completa con código de barras Planet](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)
- [Cómo generar código de barras postal en C# con Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}