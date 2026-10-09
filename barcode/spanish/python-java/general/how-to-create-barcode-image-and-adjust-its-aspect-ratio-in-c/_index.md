---
category: general
date: 2026-10-08
description: Aprende cómo crear una imagen de código de barras en C# y descubre cómo
  ajustar la relación de aspecto para los códigos de barras DataBar apilados omni‑direccionales.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust aspect ratio
- Aspose.BarCode C#
- DataBar stacked omni‑directional
- barcode X‑dimension
language: es
lastmod: 2026-10-08
og_description: Crea una imagen de código de barras en C# y aprende a ajustar la relación
  de aspecto para códigos de barras DataBar apilados omnidireccionales con un ejemplo
  de código completo.
og_image_alt: Result of create barcode image with aspect ratio 15 using Aspose.BarCode
og_title: Crear imagen de código de barras en C# – guía paso a paso
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  headline: How to create barcode image and adjust its aspect ratio in C#
  type: TechArticle
- description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  name: How to create barcode image and adjust its aspect ratio in C#
  steps:
  - name: Expected output
    text: 'After running the program you will find two PNG files in the execution
      directory:'
  - name: What if I need a different X‑dimension?
    text: You can change `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` to
      any integer greater than zero. For very high‑resolution output (e.g., 300 dpi),
      a value of 3‑4 pixels often yields clearer results.
  - name: How do I choose the right aspect ratio?
    text: 'The optimal ratio depends on the scanning environment: * **Low‑profile
      labels** – use a smaller ratio (e.g., 10‑15) to keep the barcode compact. *
      **Large shipping containers** – a higher ratio (e.g., 25‑35) improves readability
      from a distance. * **Regulatory requirements** – some standards mandate'
  - name: Can I generate other barcode formats with the same code?
    text: Yes. Replace `EncodeTypes.DatabarStackedOmniDirectional` with any other
      `EncodeTypes` value (e.g., `EncodeTypes.Code128`). The rest of the code—X‑dimension,
      aspect ratio (if applicable), and saving—remains the same.
  - name: What if I need to create the image in a different format?
    text: '`BarCodeImageFormat` supports PNG, JPEG, BMP, GIF, and TIFF. Just change
      the second argument of `Save`, for example:'
  - name: Next steps
    text: '* Explore other symbologies such as **Code128** or **QR Code** by swapping
      the `EncodeTypes` value. * Combine the barcode generation with PDF creation
      (e.g., using Aspose.PDF) to embed barcodes directly into invoices. * Experiment
      with dynamic aspect‑ratio selection based on label size—this extends '
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Cómo crear una imagen de código de barras y ajustar su relación de aspecto
  en C#
url: /es/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear una imagen de código de barras y ajustar su relación de aspecto en C#

Si necesitas **crear una imagen de código de barras** programáticamente, esta guía te muestra una solución completa y lista para ejecutar. Verás exactamente **cómo ajustar la relación de aspecto** para un código de barras DataBar apilado omni‑direccional, un requisito que aparece a menudo en aplicaciones de retail y logística.

En este tutorial aprenderás a:
* Inicializar un `BarcodeGenerator` de Aspose.BarCode para la simbología DataBar apilado omni‑direccional.  
* Establecer la dimensión X (ancho del módulo) en píxeles para controlar el grosor de las barras.  
* Aplicar dos relaciones de aspecto diferentes y guardar cada resultado como un archivo PNG.  
* Verificar la salida y comprender por qué la relación de aspecto es importante.

No se requieren herramientas externas, solo la biblioteca Aspose.BarCode para .NET y un entorno de desarrollo .NET 6 (o posterior).

## Cómo crear una imagen de código de barras con Aspose.BarCode

El primer paso es instanciar el generador con la simbología y la cadena de datos deseadas. El enumerado `EncodeTypes.DatabarStackedOmniDirectional` indica a Aspose.BarCode que produzca un código de barras DataBar apilado omni‑direccional, que se usa ampliamente para aplicaciones GS1‑128.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a BarcodeGenerator for DataBar stacked omni‑directional.
        // The data string "(01)12345678901231" follows the GS1 Application Identifier format.
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Por qué es importante:** El objeto `BarcodeGenerator` es el punto de entrada para todas las tareas de creación de códigos de barras. Al especificar la simbología y los datos en bruto desde el principio, garantizas que la imagen generada cumpla con el estándar GS1.

## Configuración de la dimensión X (ancho del módulo)

La dimensión X define el ancho de la barra más estrecha (el módulo). Una dimensión X mayor produce un código de barras más grueso, lo que puede ser útil para impresoras de baja resolución.

```csharp
        // 2️⃣ Define the X‑dimension in pixels.
        // A value of 2 pixels provides a good balance between readability and file size.
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Por qué es importante:** Ajustar la dimensión X forma parte del proceso de afinación visual. No afecta a los datos codificados, pero influye en la fiabilidad del escaneo en diferentes dispositivos.

## Cómo ajustar la relación de aspecto – primera versión (15)

La relación de aspecto controla la relación altura‑ancho del código de barras DataBar. La propiedad `DataBar.AspectRatio` acepta valores enteros; los números mayores generan barras más altas.

```csharp
        // 3️⃣ Set the aspect ratio to 15 and save the first image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Por qué es importante:** Una relación de aspecto de 15 es un valor predeterminado común para escáneres de retail. El PNG resultante (`DatabarAspectRatio15.png`) tendrá una apariencia más alta, lo que puede mejorar el éxito del escaneo en dispositivos portátiles.

## Cómo ajustar la relación de aspecto – segunda versión (30)

Podrías necesitar un código de barras más alto para formatos de etiqueta específicos. Cambiar la relación de aspecto es tan simple como asignar un nuevo valor entero antes de volver a llamar a `Save`.

```csharp
        // 4️⃣ Change the aspect ratio to 30 and save a second image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Por qué es importante:** Al demostrar **cómo ajustar la relación de aspecto**, puedes generar múltiples imágenes de códigos de barras a partir de la misma fuente de datos sin recrear el generador. Esto reduce el uso de memoria y acelera el procesamiento por lotes.

### Salida esperada

Después de ejecutar el programa encontrarás dos archivos PNG en el directorio de ejecución:

| Nombre de archivo               | Relación de aspecto | Descripción visual |
|---------------------------------|---------------------|--------------------|
| `DatabarAspectRatio15.png`      | 15                  | Altura estándar, adecuada para la mayoría de escáneres de punto de venta. |
| `DatabarAspectRatio30.png`      | 30                  | Barras más altas, útil para etiquetas grandes o impresoras de baja resolución. |

Ambas imágenes contienen el mismo GTIN codificado `(01)12345678901231`, pero las proporciones visuales difieren según la relación de aspecto que hayas establecido.

## Preguntas comunes y manejo de casos límite

### ¿Qué pasa si necesito una dimensión X diferente?

Puedes cambiar `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` a cualquier entero mayor que cero. Para una salida de muy alta resolución (p. ej., 300 dpi), un valor de 3‑4 píxeles suele producir resultados más claros.

### ¿Cómo elijo la relación de aspecto adecuada?

La relación óptima depende del entorno de escaneo:
* **Etiquetas de bajo perfil** – usa una relación menor (p. ej., 10‑15) para mantener el código de barras compacto.
* **Contenedores de envío grandes** – una relación mayor (p. ej., 25‑35) mejora la legibilidad a distancia.
* **Requisitos regulatorios** – algunas normas exigen una altura mínima; consulta la especificación GS1 para obtener los valores exactos.

### ¿Puedo generar otros formatos de código de barras con el mismo código?

Sí. Reemplaza `EncodeTypes.DatabarStackedOmniDirectional` por cualquier otro valor de `EncodeTypes` (p. ej., `EncodeTypes.Code128`). El resto del código—dimensión X, relación de aspecto (si corresponde) y guardado—permanece igual.

### ¿Qué pasa si necesito crear la imagen en otro formato?

`BarCodeImageFormat` admite PNG, JPEG, BMP, GIF y TIFF. Simplemente cambia el segundo argumento de `Save`, por ejemplo:

```csharp
barcodeGenerator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
```

## Consejo profesional: reutilizar el generador para procesamiento por lotes

Cuando debas crear decenas de códigos de barras con la misma configuración visual, instancia el generador una sola vez, actualiza solo la propiedad `CodeText` y llama a `Save` repetidamente. Esto evita la sobrecarga de asignar repetidamente buffers internos.

```csharp
// Example of batch creation
string[] gtins = { "(01)12345678901231", "(01)98765432109876", "(01)55555555555555" };
foreach (var gtin in gtins)
{
    barcodeGenerator.CodeText = gtin;
    barcodeGenerator.Save($"Barcode_{gtin.Substring(4, 6)}.png", BarCodeImageFormat.Png);
}
```

## Conclusión

Ahora sabes cómo **crear una imagen de código de barras** en C# usando Aspose.BarCode y **cómo ajustar la relación de aspecto** para símbolos DataBar apilados omni‑direccionales. Al controlar la dimensión X y la relación de aspecto, puedes producir códigos de barras que cumplan cualquier requisito de escaneo o diseño manteniendo la implementación simple y mantenible.

### Próximos pasos

* Explora otras simbologías como **Code128** o **QR Code** cambiando el valor de `EncodeTypes`.  
* Combina la generación de códigos de barras con la creación de PDF (p. ej., usando Aspose.PDF) para incrustar códigos de barras directamente en facturas.  
* Experimenta con la selección dinámica de la relación de aspecto según el tamaño de la etiqueta; esto extiende el patrón **cómo ajustar la relación de aspecto** a un motor de diseño de etiquetas completo.

¡Siéntete libre de adaptar el ejemplo, compartir tus resultados o hacer preguntas de seguimiento en los comentarios! ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [How to create databar stacked barcode in C# with Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [How to create barcode image with Aspose.Barcode in C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}