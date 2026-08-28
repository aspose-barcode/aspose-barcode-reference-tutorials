---
category: general
date: 2026-08-22
description: Cómo cambiar el tamaño del código de barras en C# usando el generador
  DataBar Stacked Omni‑Directional. Aprende a establecer la dimensión X y la relación
  de aspecto para la salida PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to change barcode size
- DataBar Stacked Omni‑Directional barcode
- C# barcode generator
- barcode aspect ratio
- X‑dimension pixels
- BarCodeImageFormat PNG
language: es
lastmod: 2026-08-22
og_description: Cómo cambiar el tamaño del código de barras en C# con el generador
  DataBar Stacked Omni‑Directional. Sigue la guía paso a paso para ajustar la dimensión
  X y la relación de aspecto.
og_image_alt: Screenshot showing how to change barcode size in C#
og_title: Cómo cambiar el tamaño del código de barras en C# – guía completa
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to change barcode size in C# using the DataBar Stacked Omni‑Directional
    generator. Learn to set X‑dimension and aspect ratio for PNG output.
  headline: How to change barcode size in C# with DataBar Stacked
  type: TechArticle
- description: How to change barcode size in C# using the DataBar Stacked Omni‑Directional
    generator. Learn to set X‑dimension and aspect ratio for PNG output.
  name: How to change barcode size in C# with DataBar Stacked
  steps:
  - name: Create a DataBar Stacked Omni‑Directional barcode generator
    text: The generator object holds all barcode settings. By passing `EncodeTypes.DatabarStackedOmniDirectional`
      and sample data, you create a valid barcode ready for further customization.
  - name: Set the basic module size (X‑dimension) in pixels
    text: The X‑dimension defines the width of a single barcode module. Adjusting
      it changes the overall width and height proportionally.
  - name: Change the barcode aspect ratio to 15 and save the image
    text: The **barcode aspect ratio** controls the height‑to‑width relationship.
      An aspect ratio of 15 yields a relatively tall barcode.
  - name: Change the barcode aspect ratio to 30 and save the new image
    text: Increasing the aspect ratio to 30 makes the barcode even taller, illustrating
      the flexibility of size adjustments.
  - name: Verify the generated images
    text: Open the PNG files in any image viewer. You should see two barcodes with
      identical width (controlled by the X‑dimension) but different heights (controlled
      by the aspect ratio). If the images appear blurry, increase the X‑dimension
      pixels; if they are too tall, lower the aspect ratio.
  - name: What to explore next
    text: '* **Custom colors** – experiment with `barcodeGenerator.Parameters.Barcode.ForeColor`
      and `BackColor` to match brand guidelines. * **Different barcode types** – replace
      `EncodeTypes.DatabarStackedOmniDirectional` with `EncodeTypes.QR` or `EncodeTypes.Code128`
      to see how size parameters differ across'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Cómo cambiar el tamaño del código de barras en C# con DataBar Stacked
url: /es/python-java/general/how-to-change-barcode-size-in-c-with-databar-stacked/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo cambiar el tamaño del código de barras en C# con DataBar Stacked

Si necesitas **cómo cambiar el tamaño del código de barras** en una aplicación .NET, esta guía muestra los pasos exactos usando el generador de códigos de barras DataBar Stacked Omni‑Directional. Verás cómo controlar la X‑dimension en píxeles, ajustar la relación de aspecto del código de barras y guardar el resultado como un archivo PNG.

Cambiar el tamaño del código de barras a menudo es necesario cuando el espacio de la etiqueta impresa es limitado o cuando se necesita una imagen de mayor resolución para canales digitales. Este tutorial cubre todo lo que necesitas, desde inicializar el generador hasta producir dos imágenes con diferentes tamaños.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* SDK .NET 6.0 o posterior instalado  
* Una referencia al paquete NuGet **Aspose.BarCode for .NET**  
* Familiaridad básica con la sintaxis de C#  

No se requiere configuración adicional; el código se ejecuta en Windows, Linux o macOS.

## Cómo cambiar el tamaño del código de barras en C# – paso a paso

Las siguientes secciones dividen el proceso en pasos discretos y reutilizables. Cada paso explica **por qué** se necesita el código, no solo **qué** hace.

### Paso 1: Crear un generador de código de barras DataBar Stacked Omni‑Directional

El objeto generador contiene todas las configuraciones del código de barras. Al pasar `EncodeTypes.DatabarStackedOmniDirectional` y datos de muestra, creas un código de barras válido listo para personalizaciones adicionales.

```csharp
// Step 1: Create a DataBar Stacked Omni‑Directional barcode generator with sample data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

*Por qué es importante* – La clase **C# barcode generator** encapsula el algoritmo de codificación. Comenzar con un generador válido garantiza que los cambios de tamaño posteriores afecten al tipo de código de barras correcto.

### Paso 2: Establecer el tamaño básico del módulo (X‑dimension) en píxeles

La X‑dimension define el ancho de un solo módulo del código de barras. Ajustarla cambia el ancho y la altura totales de forma proporcional.

```csharp
// Step 2: Define the basic module size (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Por qué es importante* – Una X‑dimension mayor produce un código de barras más grande, lo cual es útil para impresoras de baja resolución. Por el contrario, un valor menor crea un código de barras compacto adecuado para etiquetas pequeñas.

### Paso 3: Cambiar la relación de aspecto del código de barras a 15 y guardar la imagen

La **relación de aspecto del código de barras** controla la relación altura‑ancho. Una relación de aspecto de 15 produce un código de barras relativamente alto.

```csharp
// Step 3: Set the DataBar aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

*Por qué es importante* – Diferentes dispositivos de escaneo tienen requisitos óptimos de relación de aspecto. Establecer la relación a 15 demuestra cómo **cambiar el tamaño del código de barras** modificando la altura mientras se mantiene el ancho definido por la X‑dimension.

#### Resultado esperado

El archivo `DatabarAspectRatio15.png` muestra un código de barras DataBar Stacked Omni‑Directional que es más alto que el predeterminado. El ancho del código de barras refleja la X‑dimension de 2 píxeles, y la altura sigue la relación 15.

### Paso 4: Cambiar la relación de aspecto del código de barras a 30 y guardar la nueva imagen

Incrementar la relación de aspecto a 30 hace que el código de barras sea aún más alto, ilustrando la flexibilidad de los ajustes de tamaño.

```csharp
// Step 4: Change the DataBar aspect ratio to 30 and save the new image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

*Por qué es importante* – Al cambiar el valor de la **relación de aspecto del código de barras**, ves instantáneamente cómo **cambiar el tamaño del código de barras** sin recrear el generador. Esto ahorra tiempo de procesamiento en escenarios por lotes.

#### Resultado esperado

El archivo `DatabarAspectRatio30.png` es visiblemente más alto que la imagen anterior, confirmando que la relación de aspecto influye directamente en la altura del código de barras.

### Paso 5: Verificar las imágenes generadas

Abre los archivos PNG en cualquier visor de imágenes. Deberías ver dos códigos de barras con el mismo ancho (controlado por la X‑dimension) pero diferentes alturas (controladas por la relación de aspecto). Si las imágenes aparecen borrosas, aumenta los píxeles de la X‑dimension; si son demasiado altas, reduce la relación de aspecto.

```csharp
// Optional verification code – load images and print dimensions
using (var img15 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio15.png"))
using (var img30 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio30.png"))
{
    Console.WriteLine($"15‑ratio size: {img15.Width}×{img15.Height}");
    Console.WriteLine($"30‑ratio size: {img30.Width}×{img30.Height}");
}
```

*Por qué es importante* – La verificación programática asegura que los cambios de tamaño se hayan aplicado correctamente, lo cual es crucial para pipelines de compilación automatizados.

## Variaciones comunes y casos límite

| Situación | Ajuste | Razón |
|-----------|--------|-------|
| **Etiquetas muy pequeñas** | Set `XDimension.Pixels = 1` and `AspectRatio = 10` | Reduce la huella total manteniendo la legibilidad |
| **Impresión de alta resolución** | Set `XDimension.Pixels = 4` and `AspectRatio = 20` | Aumenta la densidad de píxeles para una salida nítida |
| **Formato de imagen diferente** | Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg` | Útil cuando el soporte PNG es limitado |
| **Datos dinámicos** | Pass a variable string to the `BarcodeGenerator` constructor | Genera códigos de barras para cada producto automáticamente |

Cuando necesites generar muchos códigos de barras con tamaños variables, envuelve los pasos en un método:

```csharp
void GenerateDatabar(string data, int xDim, int aspectRatio, string filePath)
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
    generator.Parameters.Barcode.XDimension.Pixels = xDim;
    generator.Parameters.Barcode.DataBar.AspectRatio = aspectRatio;
    generator.Save(filePath, BarCodeImageFormat.Png);
}
```

Llamar a `GenerateDatabar("(01)98765432109876", 3, 25, "output.png")` produce un código de barras con un tamaño personalizado en una sola línea de código.

## Consejos profesionales para cambios de tamaño fiables

* **Siempre establece la X‑dimension antes de la relación de aspecto.** Cambiar primero la relación de aspecto puede provocar un escalado inesperado si la X‑dimension tiene un valor predeterminado no ideal.  
* **Utiliza una carpeta de salida consistente.** Codificar directamente `"YOUR_DIRECTORY"` funciona para demostraciones, pero en producción prefiere `Path.Combine(Environment.CurrentDirectory, "Barcodes")`.  
* **Valida el tamaño de la imagen generada.** Cambios pequeños en la X‑dimension pueden no ser perceptibles en pantalla; comprobar las dimensiones en píxeles garantiza que el cambio se haya aplicado.

## Conclusión

Ahora sabes **cómo cambiar el tamaño del código de barras** en C# usando el generador de códigos de barras DataBar Stacked Omni‑Directional. Ajustando los **píxeles de la X‑dimension** y la **relación de aspecto del código de barras**, puedes producir imágenes PNG que se adapten a cualquier tamaño de etiqueta o requisito de resolución. El ejemplo completo y ejecutable anterior demuestra el flujo de trabajo completo desde la creación del generador hasta la verificación del tamaño.

### Qué explorar a continuación

- **Colores personalizados** – experimenta con `barcodeGenerator.Parameters.Barcode.ForeColor` y `BackColor` para coincidir con las directrices de la marca.  
- **Tipos de código de barras diferentes** – reemplaza `EncodeTypes.DatabarStackedOmniDirectional` con `EncodeTypes.QR` o `EncodeTypes.Code128` para ver cómo difieren los parámetros de tamaño entre simbologías.  
- **Procesamiento por lotes** – combina el método `GenerateDatabar` con una importación CSV para crear miles de códigos de barras automáticamente.

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo ajustar el tamaño del código de barras – Relación de aspecto Codablock F con Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [Cómo generar código de barras Aztec con relación de aspecto personalizada usando Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Cómo generar y ajustar la altura del código de barras para Databar unidimensional usando Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}