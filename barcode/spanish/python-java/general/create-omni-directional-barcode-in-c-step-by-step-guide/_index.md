---
category: general
date: 2026-07-15
description: Crea un código de barras omnidireccional en C# rápidamente con Aspose.BarCode
  – aprende cómo generar códigos de barras en C# con altura de barra ajustable y dimensión
  X.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni-directional barcode
- how to generate barcode c#
- GS1 DataBar Omni-Directional
- barcode XDimension
- barcode BarHeight
language: es
lastmod: 2026-07-15
og_description: crea un código de barras omnidireccional en C# con Aspose.BarCode.
  Domina cómo generar códigos de barras en C# ajustando XDimension y BarHeight para
  obtener resultados perfectos.
og_image_alt: Screenshot showing a create omni-directional barcode generated in C#
  with 60 px bar height
og_title: Crear código de barras omnidireccional en C# – Guía completa de programación
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  headline: create omni-directional barcode in C# – Step‑by‑Step Guide
  type: TechArticle
- description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  name: create omni-directional barcode in C# – Step‑by‑Step Guide
  steps:
  - name: Expected output
    text: '- `DatabarBarHeight30Pixels.png` – a 30 px tall omni‑directional barcode.
      - `DatabarBarHeight60Pixels.png` – the same data, but with a 60 px tall barcode.'
  - name: What if I need a different X‑dimension?
    text: Simply assign a new value before calling `Save`. For ultra‑high‑density
      printing you might go down to 1 px, but test with your scanner first—some devices
      struggle with sub‑2 px bars.
  - name: Can I add human‑readable text below the barcode?
    text: Yes. Set `barcodeGenerator.Parameters.Barcode.CodeText` to a string and
      optionally adjust `barcodeGenerator.Parameters.Barcode.CodeLocation` to `BarCodeTextLocation.Below`.
      This is handy for retail environments where the numeric GTIN must be visible.
  - name: Is PNG the best format for printing?
    text: PNG is lossless, which preserves the sharp edges needed for barcode scanners.
      If your downstream system expects a different format (TIFF, BMP), just change
      the `BarCodeImageFormat` enum.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- GS1
- DataBar
title: Crear código de barras omnidireccional en C# – Guía paso a paso
url: /es/python-java/general/create-omni-directional-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# crear código de barras omnidireccional en C# – Guía paso a paso

¿Alguna vez te has preguntado cómo generar un código de barras C# que cumpla con la simbología GS1 DataBar Omni‑Directional? No estás solo. En este tutorial **crearemos imágenes de código de barras omnidireccional** desde cero, ajustaremos la X‑dimension y jugaremos con la altura de las barras, todo usando la biblioteca Aspose.BarCode.

Recorreremos un escenario del mundo real: necesitas un código de barras compacto y de alta densidad para una etiqueta de venta al por menor, y deseas control total sobre su tamaño visual. Al final tendrás dos archivos PNG—uno con una altura de barra de 30 px y otro con 60 px—listos para integrarse en cualquier flujo de trabajo de impresión.

## Requisitos previos

- .NET 6 (o cualquier runtime reciente de .NET) instalado en tu máquina.  
- Visual Studio 2022 o VS Code—cualquier IDE que prefieras servirá.  
- Un paquete NuGet gratuito Aspose.BarCode for .NET (`Aspose.BarCode`).

No se requieren otras dependencias. Si nunca has usado NuGet, simplemente abre la Consola del Administrador de paquetes y ejecuta:

```powershell
Install-Package Aspose.BarCode
```

## crear código de barras omnidireccional – Entendiendo los conceptos básicos

La simbología **GS1 DataBar Omni‑Directional** está diseñada para escanearse en cualquier orientación, lo que la hace perfecta para etiquetas de borde de estantería. Cuando llamas a `new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data)`, la biblioteca realiza el trabajo pesado: codifica los datos, aplica las reglas de la simbología y prepara una imagen raster.

> **Consejo profesional:** Siempre envuelve los datos sin procesar en el formato de Identificador de Aplicación (AI) apropiado, por ejemplo `"(01)12345678901231"` para un GTIN‑14. Esto indica al escáner lo que representan los dígitos.

## Paso 1 – Configurar el generador de códigos de barras (how to generate barcode c#)

Primero creamos el objeto generador. Este es la piedra angular de **how to generate barcode c#** con Aspose.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for the GS1 DataBar Omni‑Directional symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

El valor del enum `EncodeTypes.DatabarOmniDirectional` indica al motor qué simbología usar. El segundo argumento es la cadena de datos sin procesar, ya envuelta en el AI de GTIN.

## Paso 2 – Ajustar la X‑Dimension (barcode XDimension)

La **barcode XDimension** controla el ancho de la barra más pequeña. Un valor de 2 px es un buen equilibrio entre legibilidad y compacidad para la mayoría de impresoras de etiquetas.

```csharp
// Step 2: Define common barcode parameters (2 px X‑dimension)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Si necesitas un aspecto más fino o más grueso, simplemente cambia el número. Recuerda: la X‑dimension es la unidad fundamental; todas las demás anchuras de barra son múltiplos de este valor.

## Paso 3 – Crear la primera imagen con una altura de barra de 30 px (barcode BarHeight)

Ahora establecemos la **barcode BarHeight** a 30 px y guardamos la imagen. Esto produce un código de barras de tamaño modesto que encaja perfectamente en una etiqueta estándar.

```csharp
// Step 3: Set a 30 px bar height and save the first image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

El método `Save` escribe un archivo PNG en disco. Puedes cambiar `BarCodeImageFormat.Jpeg` si prefieres salida JPEG.

## Paso 4 – Incrementar la altura de la barra a 60 px para etiquetas más grandes (barcode BarHeight)

A veces se requiere un código de barras más grande—quizá para una etiqueta de estantería que está más alejada del escáner. Duplicaremos la altura.

```csharp
// Step 4: Increase the bar height to 60 px for a larger barcode
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

Observa que **no** necesitamos recrear el generador; solo ajustamos el parámetro y reutilizamos el mismo objeto. Esto ahorra memoria y mantiene el código ordenado.

## Paso 5 – Guardar la segunda imagen (how to generate barcode c#)

Finalmente, guardamos el segundo PNG. Ahora tienes dos archivos que difieren solo en la altura de la barra.

```csharp
// Step 5: Save the second image with the updated height
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

### Resultado esperado

- `DatabarBarHeight30Pixels.png` – un código de barras omnidireccional de 30 px de altura.  
- `DatabarBarHeight60Pixels.png` – los mismos datos, pero con un código de barras de 60 px de altura.

Abre los archivos en cualquier visor de imágenes; verás barras nítidas y escaneables que respetan la especificación GS1 DataBar Omni‑Directional.

## Preguntas frecuentes y casos límite

### ¿Qué pasa si necesito una X‑dimension diferente?

Simplemente asigna un nuevo valor antes de llamar a `Save`. Para impresiones de ultra‑alta densidad podrías bajar a 1 px, pero prueba primero con tu escáner—algunos dispositivos tienen dificultades con barras de menos de 2 px.

### ¿Puedo añadir texto legible por humanos debajo del código de barras?

Sí. Configura `barcodeGenerator.Parameters.Barcode.CodeText` con una cadena y, opcionalmente, ajusta `barcodeGenerator.Parameters.Barcode.CodeLocation` a `BarCodeTextLocation.Below`. Esto es útil en entornos minoristas donde el GTIN numérico debe ser visible.

```csharp
barcodeGenerator.Parameters.Barcode.CodeText = "(01)12345678901231";
barcodeGenerator.Parameters.Barcode.CodeLocation = BarCodeTextLocation.Below;
```

### ¿Es PNG el mejor formato para imprimir?

PNG es sin pérdida, lo que conserva los bordes nítidos necesarios para los escáneres de códigos de barras. Si tu sistema posterior espera un formato diferente (TIFF, BMP), simplemente cambia el enum `BarCodeImageFormat`.

## Ejemplo completo (create omni-directional barcode)

A continuación se muestra el programa completo, listo para ejecutar. Copia‑pega el código en un nuevo proyecto de consola y pulsa **F5**.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace OmniDirectionalDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create generator for GS1 DataBar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension (2 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ Second image – 60 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two omni‑directional barcodes created successfully.");
        }
    }
}
```

Ejecuta el programa, revisa la carpeta de salida y verás los dos archivos PNG exactamente como se describió.

## Recapitulación

Hemos demostrado **how to generate barcode C#** código que crea un **create omni-directional barcode** usando Aspose.BarCode. Al ajustar la **barcode XDimension** y la **barcode BarHeight**, obtienes un control fino sobre el tamaño visual sin sacrificar la fiabilidad del escaneo.

## ¿Qué sigue?

- Experimenta con otras configuraciones de **GS1 DataBar Omni-Directional** como `Color` o `Margin`.  
- Combina varios códigos de barras en un mismo lienzo usando `Graphics` para diseños de etiquetas complejas.  
- Integra el generador en una API web para que tu plataforma de comercio electrónico pueda emitir códigos de barras bajo demanda.

¿Tienes alguna variante que quieras compartir? Deja un comentario y sigamos la conversación. ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo generar código de barras – Configuración Code 39 con Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Cómo crear zona silenciosa de código de barras para ITF-14 usando Aspose.BarCode para .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Cómo crear zona silenciosa de código de barras para Code 16K usando Aspose.BarCode para .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}