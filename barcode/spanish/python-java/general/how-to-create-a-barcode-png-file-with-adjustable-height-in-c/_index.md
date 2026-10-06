---
category: general
date: 2026-08-19
description: Aprende a generar un archivo PNG de código de barras en C# y a ajustar
  su altura, cubriendo cómo crear imágenes de códigos de barras y cambiar la altura
  del código de barras fácilmente.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode png file
- how to generate barcode
- adjust barcode height
- change barcode height
language: es
lastmod: 2026-08-19
og_description: Crea un archivo PNG de código de barras en C# y aprende a generar
  imágenes de códigos de barras, ajustar la altura del código de barras y cambiarla
  para obtener escaneos óptimos.
og_image_alt: barcode PNG file showing Databar OmniDirectional barcode at two heights
og_title: Crear un archivo PNG de código de barras en C# – guía paso a paso
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Learn how to generate a barcode PNG file in C# and adjust its height,
    covering how to generate barcode images and change barcode height easily.
  headline: How to create a barcode PNG file with adjustable height in C#
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`,
      `BarCodeImageFormat.Bmp`, etc.
    question: Can I generate other image formats (JPEG, BMP)?
  - answer: Serve the generated PNG via an HTTP endpoint or convert it to a Base64
      string and place it in an `<img>` tag’s `src` attribute.
    question: How do I embed the PNG in a web page?
  - answer: 'Use `generator.Parameters.Image.BackgroundColor = Color.White;` (or any
      `System.Drawing.Color`). ## Conclusion You now know how to **generate a barcode
      PNG file** in C# and precisely **adjust barcode height** to meet scanning or
      design requirements. By changing the `BarHeight.Pixels` property you ca'
    question: Is there a way to set the background color?
  type: FAQPage
tags:
- barcode
- C#
- image generation
title: Cómo crear un archivo PNG de código de barras con altura ajustable en C#
url: /es/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un archivo PNG de código de barras con altura ajustable en C#

Si necesitas crear un **archivo PNG de código de barras** en C#, esta guía te muestra exactamente cómo. Verás un ejemplo completo y ejecutable que demuestra **cómo generar códigos de barras** e **ajustar la altura del código de barras** para diferentes casos de uso.

Generar un archivo PNG de código de barras es un requisito común para sistemas de inventario, terminales punto de venta y cualquier aplicación que deba imprimir o mostrar datos legibles por máquina. Al final de este tutorial podrás cambiar la altura del código de barras, guardar varios archivos PNG y comprender el impacto de la altura en la fiabilidad del escaneo.

## Requisitos previos

* SDK .NET 6.0 o posterior instalado  
* Visual Studio 2022 (o cualquier IDE que soporte .NET)  
* El paquete NuGet **Aspose.BarCode for .NET** (el ejemplo de código usa esta biblioteca)  

Puedes agregar el paquete desde la línea de comandos:

```bash
dotnet add package Aspose.BarCode
```

> **Consejo profesional:** La versión de evaluación gratuita de Aspose.BarCode funciona para desarrollo y pruebas. Para producción, obtén una clave con licencia.

## Instalar la biblioteca de códigos de barras

El primer paso es referenciar la biblioteca en tu proyecto. Agrega las siguientes directivas `using` al inicio de tu archivo C#:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Estos espacios de nombres te dan acceso a `BarcodeGenerator`, `EncodeTypes` y `BarCodeImageFormat`.

## Crear el archivo PNG de código de barras

Ahora creamos una instancia de `BarcodeGenerator` que generará un **archivo PNG de código de barras**. El ejemplo usa la simbología Databar OmniDirectional, pero puedes reemplazar `EncodeTypes.DatabarOmniDirectional` por cualquier tipo compatible.

```csharp
// Step 1: Create a DataBar Omnidirectional generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

La cadena `"(01)12345678901231"` sigue el formato de Identificador de Aplicación GS1 para un GTIN de 14 dígitos. Ajusta los datos para que coincidan con los identificadores de tus productos.

## Establecer la dimensión X (opcional)

La dimensión X define el ancho de un solo módulo del código de barras. Un valor basado en píxeles te brinda un control preciso sobre el tamaño de la imagen.

```csharp
// Optional: Set the pixel size of the X‑dimension (module width)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Un valor de `2` píxeles funciona bien para la mayoría de pantallas. Auméntalo si necesitas un código de barras más grande al imprimir.

## Ajustar la altura del código de barras y guardar el archivo PNG

La propiedad **BarHeight** controla el tamaño vertical de las barras. Cambiar este valor te permite **ajustar la altura del código de barras** sin afectar los datos codificados.

```csharp
// Step 2: Generate a 30‑pixel‑high barcode and save it as PNG
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

El archivo `DatabarBarHeight30Pixels.png` es ahora un **archivo PNG de código de barras** de 30 píxeles de alto.  

Para **cambiar la altura del código de barras** y crear una segunda imagen, simplemente asigna un nuevo valor y llama a `Save` nuevamente:

```csharp
// Step 3: Change the height to 60 pixels and save the new image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
barcodeGenerator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Ahora tienes dos archivos PNG—uno de 30 px y otro de 60 px—que demuestran cómo **ajustar la altura del código de barras** sobre la marcha.

### Por qué la altura de la barra es importante

* **Legibilidad:** Los escáneres esperan una altura mínima para una detección fiable. Un código de barras demasiado corto puede pasar desapercibido, especialmente en cámaras de baja resolución.
* **Estética:** Igualar la altura del código de barras con los elementos de diseño circundantes crea una UI más limpia.
* **Restricciones de impresión:** Algunas impresoras de etiquetas tienen ranuras de altura fija; ajustar la altura del código de barras asegura que encaje.

**Mejor práctica:** Mantén la altura como múltiplo de la dimensión X (p.ej., 30 px cuando la dimensión X es 2 px) para mantener la proporción y evitar distorsiones.

## Ejemplo completo

A continuación se muestra el programa completo y autónomo que puedes pegar en una aplicación de consola y ejecutar de inmediato.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator with Databar OmniDirectional data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set a reasonable X‑dimension (module width)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First height: 30 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode as DatabarBarHeight30Pixels.png");

        // 4️⃣ Second height: 60 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode as DatabarBarHeight60Pixels.png");
    }
}
```

**Salida esperada**

Ejecutar el programa crea dos archivos en el directorio de trabajo del ejecutable:

* `DatabarBarHeight30Pixels.png` – un archivo PNG de código de barras de 30 píxeles de alto  
* `DatabarBarHeight60Pixels.png` – un archivo PNG de código de barras de 60 píxeles de alto  

Abre cualquiera de los PNG con cualquier visor de imágenes; verás un código de barras Databar OmniDirectional claro listo para escanear.

## Casos límite y solución de problemas

| Situación | Qué verificar | Solución recomendada |
|-----------|---------------|----------------------|
| El código de barras aparece borroso | Dimensión X demasiado baja para la altura elegida | Aumentar `XDimension.Pixels` (p.ej., de 2 a 3) |
| El escáner falla con un código de barras de baja altura | Altura por debajo del mínimo del escáner | Establecer `BarHeight.Pixels` al menos en 30 px (o según especificaciones del escáner) |
| El archivo PNG está vacío o corrupto | Ruta de salida inválida o permiso de escritura denegado | Usar una ruta absoluta o asegurarse de que la aplicación tenga acceso de escritura |
| Necesito una simbología diferente | `EncodeTypes` actual no es adecuada | Reemplazar `EncodeTypes.DatabarOmniDirectional` por otro valor del enum (p.ej., `EncodeTypes.Code128`) |

## Preguntas frecuentes

**P: ¿Puedo generar otros formatos de imagen (JPEG, BMP)?**  
R: Sí. Reemplaza `BarCodeImageFormat.Png` por `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp`, etc.

**P: ¿Cómo incrusto el PNG en una página web?**  
R: Sirve el PNG generado a través de un endpoint HTTP o conviértelo a una cadena Base64 y colócalo en el atributo `src` de una etiqueta `<img>`.

**P: ¿Hay una forma de establecer el color de fondo?**  
R: Usa `generator.Parameters.Image.BackgroundColor = Color.White;` (o cualquier `System.Drawing.Color`).

## Conclusión

Ahora sabes cómo **generar un archivo PNG de código de barras** en C# y **ajustar la altura del código de barras** con precisión para cumplir con los requisitos de escaneo o diseño. Cambiando la propiedad `BarHeight.Pixels` puedes **cambiar la altura del código de barras** sobre la marcha y producir múltiples recursos PNG desde una única base de código.

A continuación, explora otras opciones de personalización como el color de primer plano, los márgenes y la adición de texto legible por humanos. También puedes experimentar con diferentes simbologías (`EncodeTypes.Code128`, `EncodeTypes.QR`) para ampliar el rango de datos que puedes codificar.

¡Feliz codificación, y que tus códigos de barras siempre se lean en el primer intento!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo generar y ajustar la altura del código de barras para Databar unidimensional usando Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Cómo generar códigos de barras - Tipos de códigos de barras unidimensionales](/barcode/english/net/one-dimensional-barcode-types/)
- [Cómo generar un código de barras Aztec con relación de aspecto personalizada usando Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}