---
category: general
date: 2026-08-06
description: Genera una imagen de código de barras en C# usando Aspose.BarCode. Aprende
  a generar Databar, ajustar el tamaño personalizado del código de barras y cambiar
  la altura del código de barras con un código sencillo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- how to generate databar
- custom barcode size
- create databar barcode
- change barcode height
language: es
lastmod: 2026-08-06
og_description: Genera una imagen de código de barras en C# con Aspose.BarCode. Este
  tutorial te muestra cómo crear un código de barras Databar omnidireccional, personalizar
  su tamaño y cambiar la altura del código de barras de manera eficiente.
og_image_alt: Screenshot of a Databar barcode generated with custom height in C#
og_title: Generar imagen de código de barras en C# – guía completa de Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Generate barcode image in C# using Aspose.BarCode. Learn how to generate
    Databar, adjust custom barcode size, and change barcode height with simple code.
  headline: Generate barcode image in C# with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: The evaluation version of Aspose.BarCode works without a license but adds
      a small watermark. For production use, apply a purchased license using `License
      license = new License(); license.SetLicense("Aspose.BarCode.lic");`.
    question: Can I generate a barcode without installing a license?
  - answer: Yes. Very small X‑dimensions can make the barcode unreadable on low‑resolution
      printers. A minimum of 1 px for screen rendering is recommended; for print,
      use at least 0.25 mm.
    question: Does changing the X‑dimension affect readability?
  - answer: 'Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. You
      may also set `generator.Parameters.ImageQuality` to control compression. ##
      Conclusion You now know how to **generate barcode image** in C# using Aspose.BarCode,
      how to **create Databar barcode**, adjust a **custom barcode size**, '
    question: What if I need to generate a barcode in JPEG format?
  type: FAQPage
tags:
- barcode
- C#
- Aspose.BarCode
title: Generar imagen de código de barras en C# con Aspose.BarCode
url: /es/python-java/general/generate-barcode-image-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generar imagen de código de barras en C# con Aspose.BarCode

Si necesitas **generar una imagen de código de barras** de forma programática, esta guía te muestra exactamente cómo hacerlo. Ya sea que estés construyendo un sistema de inventario minorista o un portal de seguimiento logístico, verás el flujo completo para crear un código de barras Databar Omnidirectional, ajustar sus dimensiones y guardar el resultado como un archivo PNG.

Generar una imagen de código de barras es un requisito frecuente, pero los desarrolladores a menudo se preguntan **cómo generar Databar** con el tamaño exacto que necesitan. En este tutorial aprenderás a crear un código de barras Databar, personalizar su ancho y alto, y cambiar la altura del código sin reescribir todo el generador.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* SDK de .NET 6.0 o posterior (el código funciona con .NET Core y .NET Framework)
* Visual Studio 2022 (o cualquier IDE que soporte C#)
* Una licencia válida de Aspose.BarCode para .NET (la evaluación gratuita funciona para pruebas)
* Familiaridad básica con la sintaxis de C#

## Paso 1: Instalar Aspose.BarCode

Agrega el paquete NuGet Aspose.BarCode a tu proyecto:

```bash
dotnet add package Aspose.BarCode
```

El paquete contiene la clase `BarcodeGenerator` que se usa a lo largo de este tutorial. Después de la instalación, restaura el proyecto para descargar las dependencias.

## Paso 2: Crear un generador de código de barras básico

La primera línea de código crea un **generador de código de barras** que producirá un símbolo Databar Omnidirectional. El enumerado `EncodeTypes.DatabarOmniDirectional` indica a la biblioteca qué simbología usar, y la cadena de datos sigue la sintaxis del Identificador de Aplicación GS1.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a Databar Omnidirectional barcode
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231"); // GS1-14 data (example GTIN)
```

**Por qué es importante:** El objeto `BarcodeGenerator` es el punto de entrada para cualquier operación de código de barras. Al seleccionar `DatabarOmniDirectional` garantizas que la salida cumpla con el estándar GS1 para escaneo minorista.

## Paso 3: Establecer una X‑dimensión personalizada (ancho del módulo)

La X‑dimensión controla el ancho de la barra más estrecha. Configurarla a un valor pequeño en píxeles te da un código de barras compacto, mientras que valores mayores aumentan el ancho total.

```csharp
        // Step 3: Define a custom X‑dimension (module width) of 2 px
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Explicación:** Una X‑dimensión de 2 píxeles es una elección común para pantallas de alta resolución. Ajusta este valor si necesitas una densidad visual más estrecha o más suelta.

## Paso 4: Generar la primera imagen de código de barras con una altura específica

La altura del código de barras es independiente de la X‑dimensión. Aquí establecemos la altura de la barra en **30 px**, luego guardamos la imagen como PNG.

```csharp
        // Step 4: Set bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**Resultado:** Ahora tienes un archivo llamado `DatabarBarHeight30Pixels.png` que muestra un código de barras Databar de 30 px de alto. Esto demuestra la capacidad de **tamaño de código de barras personalizado** para un caso de uso específico, como una etiqueta pequeña.

## Paso 5: Cambiar la altura del código de barras para una versión más grande

Si el mismo código de barras debe aparecer en una etiqueta más grande, solo necesitas modificar la propiedad de altura y reutilizar la misma instancia del generador.

```csharp
        // Step 5: Increase the bar height to 60 px for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
    }
}
```

**Por qué puedes reutilizar el generador:** Cambiar `BarHeight.Pixels` actualiza el diseño interno sin recrear el objeto, lo que ahorra memoria y mantiene intacta la cadena de datos. Esta es la forma recomendada de **cambiar la altura del código de barras** sobre la marcha.

## Paso 6: Verificar la salida

Abre los dos archivos PNG en cualquier visor de imágenes. Deberías ver dos códigos de barras Databar Omnidirectional que codifican el mismo GTIN pero difieren en tamaño vertical:

* `DatabarBarHeight30Pixels.png` – 30 px de alto, adecuado para recibos compactos.
* `DatabarBarHeight60Pixels.png` – 60 px de alto, ideal para etiquetas de estantería más grandes.

Ambas imágenes conservan la misma X‑dimensión, por lo que la relación barra‑espacio permanece constante mientras la altura total se escala.

## Variaciones comunes y casos límite

| Situación | Cómo manejarla |
|-----------|----------------|
| **Diferente simbología de código de barras** | Reemplaza `EncodeTypes.DatabarOmniDirectional` por otro valor del enumerado (p. ej., `EncodeTypes.Code128`). El resto del código permanece sin cambios. |
| **Dimensiones no en píxeles** | Usa `generator.Parameters.Barcode.XDimension.Millimeters` o `BarHeight.Millimeters` si necesitas medidas físicas para una salida lista para imprimir. |
| **Fondo transparente** | Establece `generator.Parameters.ImageBackgroundColor = Color.Transparent;` antes de llamar a `Save`. |
| **Salida de alta resolución** | Incrementa tanto `XDimension.Pixels` como `BarHeight.Pixels` de forma proporcional, o guarda como `BarCodeImageFormat.Tiff` para calidad sin pérdidas. |
| **Múltiples códigos de barras en una sola imagen** | Crea instancias separadas de `BarcodeGenerator`, renderiza cada una a un `Bitmap`, y luego compónlas usando `Graphics.DrawImage`. |

**Consejo profesional:** Siempre prueba el código de barras generado con un escáner real antes de implementarlo en producción. Los escáneres pueden interpretar barras muy finas de manera diferente según la iluminación y la calidad del sensor.

## Código fuente completo para referencia

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator for a Databar Omnidirectional barcode
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231"); // Example GTIN

            // Custom X‑dimension (module width) – 2 px
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image: 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // Second image: 60 px height (larger barcode)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

Copia el código en un nuevo proyecto de consola, ejecútalo y verás los dos archivos PNG aparecer en la carpeta de salida.

## Preguntas frecuentes

**P: ¿Puedo generar un código de barras sin instalar una licencia?**  
R: La versión de evaluación de Aspose.BarCode funciona sin licencia pero agrega una pequeña marca de agua. Para uso en producción, aplica una licencia comprada con `License license = new License(); license.SetLicense("Aspose.BarCode.lic");`.

**P: ¿Cambiar la X‑dimensión afecta la legibilidad?**  
R: Sí. X‑dimensiones muy pequeñas pueden hacer que el código de barras sea ilegible en impresoras de baja resolución. Se recomienda un mínimo de 1 px para renderizado en pantalla; para impresión, utiliza al menos 0.25 mm.

**P: ¿Qué pasa si necesito generar un código de barras en formato JPEG?**  
R: Reemplaza `BarCodeImageFormat.Png` por `BarCodeImageFormat.Jpeg`. También puedes establecer `generator.Parameters.ImageQuality` para controlar la compresión.

## Conclusión

Ahora sabes cómo **generar una imagen de código de barras** en C# usando Aspose.BarCode, cómo **crear un código de barras Databar**, ajustar un **tamaño de código de barras personalizado** y **cambiar la altura del código de barras** bajo demanda. El ejemplo completo muestra el flujo de trabajo más común, y la tabla de variaciones te prepara para manejar casos reales.

A continuación, explora temas relacionados como **incrustar códigos de barras en documentos PDF**, **generar lotes de múltiples códigos de barras**, y **usar códigos QR para pagos móviles**. Cada uno de esos escenarios se basa en los mismos principios cubiertos aquí, por lo que puedes ampliar este conocimiento con confianza.

¡Feliz codificación y que tus códigos de barras se escaneen sin problemas!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}