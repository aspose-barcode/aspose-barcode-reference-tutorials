---
category: general
date: 2026-09-29
description: Cómo establecer el ancho de un código de barras GS1 DataBar Omni‑Directional
  y cómo cambiar la altura usando C#. Sigue una guía paso a paso con código completo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to change height
language: es
lastmod: 2026-09-29
og_description: Cómo establecer el ancho de un código de barras GS1 DataBar Omni‑Directional
  y cómo cambiar la altura en C#. Aprende las llamadas exactas a la API y ve un ejemplo
  completo y ejecutable.
og_image_alt: Screenshot of two GS1 DataBar barcodes with different heights
og_title: Cómo establecer el ancho de un código de barras GS1 DataBar – Guía de C#
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  headline: How to set width and adjust height for a GS1 DataBar Omni‑Directional
    barcode in C#
  type: TechArticle
- description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  name: How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode
    in C#
  steps:
  - name: Why the X‑dimension matters
    text: '* **Scanner tolerance** – Most scanners expect a minimum module width;
      too small a value can cause read errors. * **Print resolution** – When printing
      at 300 dpi, a 2 px module translates to ~0.17 mm, which is within the recommended
      range for GS1 DataBar. * **Image size** – Larger X‑dimension values'
  - name: Tips for reliable width settings
    text: '* **Never set XDimension below 1 px** – the library will clamp the value,
      but the resulting barcode may be unreadable. * **Match the target DPI** – if
      you render to a high‑resolution format (e.g., TIFF at 600 dpi), increase XDimension
      proportionally. * **Test with a real scanner** – after changing t'
  - name: Understanding bar height
    text: '* **Visual balance** – Taller bars improve readability on low‑contrast
      backgrounds but increase the image’s vertical footprint. * **Regulatory limits**
      – Some standards (e.g., retail labeling) specify a maximum bar height; adjust
      accordingly. * **Aspect ratio** – Changing height does not affect the '
  - name: Edge‑case handling for height adjustments
    text: '| Situation | Recommended approach | |-----------|----------------------|
      | Height < 10 px | Increase to at least 10 px; very short bars may be ignored
      by scanners. | | Very tall bars (≥ 100 px) | Verify that the output medium (paper,
      label) can accommodate the extra space. | | Need proportional sca'
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
- GS1 DataBar
title: Cómo establecer el ancho y ajustar la altura de un código de barras GS1 DataBar
  Omni‑Directional en C#
url: /es/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo establecer el ancho y ajustar la altura de un GS1 DataBar Omni‑Directional barcode en C#

Establecer el ancho de un GS1 DataBar Omni‑Directional barcode es una tarea frecuente cuando necesitas un tamaño exacto para el equipo de escaneo. En este tutorial también aprenderás **cómo cambiar la altura** para que el código de barras se ajuste perfectamente a tu diseño. La guía te lleva a través del proceso completo, desde la configuración del proyecto hasta un ejemplo de código totalmente ejecutable.

Cubrirá:

* El paquete NuGet requerido y la versión de .NET.
* Por qué la X‑dimension (ancho del módulo) es importante para la legibilidad del código de barras.
* Las llamadas exactas a la API para **cómo establecer el ancho** y **cómo cambiar la altura**.
* Manejo de casos límite como el ancho mínimo del módulo y la renderización en alta resolución.
* Un ejemplo completo, listo para copiar y pegar, que genera dos archivos PNG con diferentes alturas de barra.

## Requisitos previos

| Requisito | Razón |
|------------|--------|
| .NET 6.0 SDK o posterior | El ejemplo usa características modernas de C# y se ejecuta en Windows, Linux o macOS. |
| Visual Studio 2022 (o cualquier IDE de C#) | Proporciona IntelliSense para la API de Aspose.Barcode. |
| **Aspose.Barcode for .NET** paquete NuGet | Contiene `BarcodeGenerator`, `EncodeTypes` y soporte de formatos de imagen. Instálalo con `dotnet add package Aspose.Barcode`. |
| Permiso de escritura en una carpeta donde se guardarán los archivos PNG | El generador escribe las imágenes de salida en el disco. |

## Cómo establecer el ancho del código de barras

El paso de **cómo establecer el ancho** se realiza configurando la propiedad `XDimension` de los parámetros del código de barras. `XDimension` representa el ancho del módulo (la barra o espacio más pequeño) en píxeles, puntos o milímetros. Configurarlo correctamente garantiza que el código de barras cumpla con las especificaciones del escáner.

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a generator for a GS1 DataBar Omni‑Directional barcode.
            // The value "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ **How to set width**: define the module width (X‑dimension) in pixels.
            // A value of 2 px is a common choice that balances readability and image size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // The remaining steps (height, saving) are shown in the next section.
```

### Por qué la X‑dimension es importante

* **Tolerancia del escáner** – La mayoría de los escáneres esperan un ancho mínimo del módulo; un valor demasiado pequeño puede causar errores de lectura.
* **Resolución de impresión** – Al imprimir a 300 dpi, un módulo de 2 px se traduce en ~0.17 mm, lo cual está dentro del rango recomendado para GS1 DataBar.
* **Tamaño de la imagen** – Valores mayores de X‑dimension aumentan el ancho total del código de barras, lo que puede afectar las restricciones de diseño.

### Consejos para configuraciones de ancho confiables

* **Nunca establezcas XDimension por debajo de 1 px** – la biblioteca limitará el valor, pero el código de barras resultante puede ser ilegible.
* **Coincide con el DPI objetivo** – si renderizas a un formato de alta resolución (p.ej., TIFF a 600 dpi), aumenta XDimension proporcionalmente.
* **Prueba con un escáner real** – después de cambiar el ancho, valida el código de barras en el dispositivo que lo leerá.

## Cómo cambiar la altura del código de barras

Una vez definido el ancho, puedes controlar el tamaño vertical con la propiedad `BarHeight`. El siguiente código muestra **cómo cambiar la altura** de 30 px a 60 px y guardar dos imágenes separadas.

```csharp
            // 3️⃣ Set the first bar height to 30 pixels and save the image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ **How to change height**: increase the bar height to 60 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            // The program ends here; two PNG files are written to the execution folder.
        }
    }
}
```

### Comprendiendo la altura de la barra

* **Equilibrio visual** – Barras más altas mejoran la legibilidad en fondos de bajo contraste pero aumentan la huella vertical de la imagen.
* **Límites regulatorios** – Algunas normas (p.ej., etiquetado minorista) especifican una altura máxima de barra; ajústala según sea necesario.
* **Relación de aspecto** – Cambiar la altura no afecta el ancho del módulo; puedes afinar ambos de forma independiente.

### Manejo de casos límite para ajustes de altura

| Situación | Enfoque recomendado |
|-----------|----------------------|
| Altura < 10 px | Aumenta a al menos 10 px; barras muy cortas pueden ser ignoradas por los escáneres. |
| Barras muy altas (≥ 100 px) | Verifica que el medio de salida (papel, etiqueta) pueda acomodar el espacio adicional. |
| Necesidad de escalado proporcional | Calcula `BarHeight = XDimension * desiredRatio` para mantener la consistencia visual. |

## Ejemplo completo y ejecutable

A continuación se muestra el programa completo que combina los pasos de **cómo establecer el ancho** y **cómo cambiar la altura**. Copia el código en un nuevo proyecto de consola, restaura el paquete NuGet Aspose.Barcode y ejecútalo. Aparecerán dos archivos PNG en la carpeta `bin/Debug/net6.0`.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // Initialize the barcode generator (GS1 DataBar Omni‑Directional)
            // ------------------------------------------------------------
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // ------------------------------------------------------------
            // **How to set width** – define the module width (X‑dimension)
            // ------------------------------------------------------------
            generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px = ~0.17 mm at 300 dpi

            // ------------------------------------------------------------
            // First image: bar height = 30 px
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight30Pixels.png");

            // ------------------------------------------------------------
            // **How to change height** – increase to 60 px and save again
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight60Pixels.png");

            // ------------------------------------------------------------
            // End of demo
            // ------------------------------------------------------------
        }
    }
}
```

**Expected output**

Ejecutar el programa produce dos archivos PNG:

* `DatabarBarHeight30Pixels.png` – un código de barras de 30 px de altura, módulos de 2 px de ancho.
* `DatabarBarHeight60Pixels.png` – el mismo código de barras con el doble de tamaño vertical.

Abre cualquiera de las imágenes en cualquier visor; verás un símbolo limpio de GS1 DataBar Omni‑Directional listo para escanear.

## Preguntas frecuentes respondidas

| Pregunta | Respuesta |
|----------|-----------|
| *¿Puedo usar milímetros en lugar de píxeles?* | Sí. Establece `generator.Parameters.Barcode.XDimension.Millimeters` y `BarHeight.Millimeters`. La biblioteca convierte a píxeles del dispositivo según el DPI de la imagen. |
| *¿Qué pasa si necesito un tipo de código de barras diferente?* | Reemplaza `EncodeTypes.DatabarOmniDirectional` por cualquier otro valor de `EncodeTypes` (p.ej., `EncodeTypes.QR`). Las propiedades de ancho y altura funcionan de la misma manera. |
| *¿Hay una forma de generar SVG en lugar de PNG?* | Usa `BarCodeImageFormat.Svg` en la llamada `Save`. Los ajustes de ancho/altura siguen siendo aplicables. |
| *¿Necesito llamar a `generator.Dispose()`?* | El `BarcodeGenerator` implementa `IDisposable`. En una aplicación de consola puedes envolverlo en un bloque `using`, pero para ejemplos de corta duración es opcional. |

## Conclusión

Ahora sabes **cómo establecer el ancho** de un GS1 DataBar Omni‑Directional barcode y **cómo cambiar la altura** usando la API Aspose.Barcode en C#. El ejemplo completo muestra cómo crear un generador, configurar `XDimension` y `BarHeight`, y guardar archivos PNG con diferentes tamaños verticales.

A partir de aquí puedes:

* Experimentar con otros `EncodeTypes` (p.ej., QR, Code128).
* Renderizar a formatos de alta resolución como TIFF para impresión.
* Integrar el generador en una API web que devuelva códigos de barras al instante.

¡Feliz codificación, y que tus códigos de barras siempre se lean sin problemas!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo cambiar la altura del código de barras en C# – Guía completa](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Ejemplo de generador de códigos de barras en C# – establecer ancho y altura](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [Cómo usar un generador de códigos de barras C# para crear códigos de barras DataBar Omni‑directional](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}