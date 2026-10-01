---
category: general
date: 2026-08-03
description: Crea un PNG de código de barras en C# y aprende cómo cambiar la relación
  de aspecto de las imágenes DataBar. Sigue este ejemplo completo con código y consejos.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode PNG
- how to change aspect ratio
- Aspose.BarCode C#
- DataBar stacked omnidirectional
- barcode image format PNG
language: es
lastmod: 2026-08-03
og_description: Crea un PNG de código de barras en C# y descubre cómo cambiar la relación
  de aspecto de los códigos de barras DataBar. Esta guía te ofrece código listo para
  ejecutar y consejos prácticos.
og_image_alt: Sample barcode PNG generated with aspect ratio 15
og_title: Crear PNG de código de barras en C# – ejemplo completo con control de relación
  de aspecto
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  headline: Create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  name: Create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: How to change other visual properties?
    text: 'You can adjust foreground color, background color, or add human‑readable
      text through the `generator.Parameters.Barcode` object. For example:'
  - name: What if I need a different image format?
    text: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as needed.
      PNG remains the best choice for lossless barcode images.
  - name: Does the aspect ratio affect scanning speed?
    text: Higher aspect ratios increase the barcode’s height, which can improve scan
      reliability on devices that struggle with short stacked symbols. However, extremely
      tall barcodes may not fit on small labels, so test with your target hardware.
  - name: Can I generate multiple barcodes in a loop?
    text: Yes. Create a new `BarcodeGenerator` instance for each data string or reuse
      the same instance while updating `CodeText` and `DataBar.AspectRatio`. This
      approach reduces object allocation overhead.
  type: HowTo
tags:
- barcode
- C#
- PNG
- Aspose
title: Crear código de barras PNG en C# – guía paso a paso
url: /es/python-java/general/create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear código de barras PNG en C# – guía paso a paso

Si necesitas **crear código de barras PNG** en C#, este tutorial te muestra exactamente cómo hacerlo. Generarás un código de barras DataBar omnidireccional apilado, lo guardarás como un archivo PNG y aprenderás **cómo cambiar la relación de aspecto** para adaptarla a diferentes entornos de escaneo.

La guía cubre todo lo que necesitas: paquetes requeridos, un programa completo y ejecutable, y explicaciones de por qué cada configuración es importante. Al final tendrás dos archivos PNG—uno con una relación de aspecto de 15 y otro con 30—listos para pruebas o uso en producción.

## Prerrequisitos

Antes de comenzar, asegúrate de tener:

- .NET 6.0 SDK o posterior instalado
- Visual Studio 2022 (o cualquier IDE de C#)
- Una referencia NuGet a **Aspose.BarCode** (la biblioteca que proporciona `BarcodeGenerator`)
- Permiso de escritura en el directorio donde se guardarán los archivos PNG

Puedes agregar el paquete Aspose.BarCode con el siguiente comando:

```bash
dotnet add package Aspose.BarCode
```

## Paso 1: Configurar el proyecto e importar espacios de nombres

Crea una nueva aplicación de consola e importa los espacios de nombres necesarios para la generación de códigos de barras y la E/S de archivos.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodePngDemo
{
    class Program
    {
        static void Main()
        {
            // All subsequent steps are inside Main
```

**Por qué es importante:** Importar `Aspose.BarCode.Generation` te da acceso a `BarcodeGenerator`. Mantener el código dentro de `Main` hace que el ejemplo sea autocontenido y fácil de ejecutar.

## Paso 2: Crear un generador de código de barras para un DataBar omnidireccional apilado

Instancia `BarcodeGenerator` con el tipo `EncodeTypes.DatabarStackedOmniDirectional` y una cadena de datos de ejemplo GS1‑128.

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");
```

**Por qué es importante:** El tipo de codificación elegido produce un DataBar de alta densidad que puede ser leído por la mayoría de los escáneres modernos. La cadena de datos sigue el formato del Identificador de Aplicación GS1 (01), que es común para identificadores de productos.

## Paso 3: Definir la dimensión X (ancho del módulo) en píxeles

Establece el ancho del módulo para controlar el tamaño general del código de barras sin afectar su legibilidad.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Por qué es importante:** Una dimensión X de 2 píxeles produce un código de barras que no es ni demasiado pequeño para los escáneres ni demasiado grande para los espacios típicos de etiquetas.

## Paso 4: Guardar el primer PNG con una relación de aspecto de 15

Ajusta la relación de aspecto del DataBar y luego guarda la imagen como archivo PNG.

```csharp
            // Step 4: Set the DataBar aspect ratio to 15 and save the image
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;
            string outputPath15 = @"YOUR_DIRECTORY\DatabarAspectRatio15.png";
            generator.Save(outputPath15, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath15} (aspect ratio 15).");
```

**Por qué es importante:** La relación de aspecto controla la relación altura‑ancho del DataBar apilado. Una relación de 15 es un valor predeterminado común que equilibra la legibilidad y la altura de la etiqueta.

## Paso 5: Cambiar la relación de aspecto a 30 y guardar un segundo PNG

Modifica la misma instancia del generador para usar una relación de aspecto mayor y luego guarda la segunda imagen.

```csharp
            // Step 5: Change the aspect ratio to 30 and save another image
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string outputPath30 = @"YOUR_DIRECTORY\DatabarAspectRatio30.png";
            generator.Save(outputPath30, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath30} (aspect ratio 30).");
        }
    }
}
```

**Por qué es importante:** Incrementar la relación de aspecto estira el código de barras verticalmente, lo que puede mejorar la fiabilidad del escaneo en dispositivos de baja resolución o cuando la etiqueta se imprime en medios estrechos.

## Resultado esperado

Ejecutar el programa crea dos archivos PNG:

| Archivo                              | Relación de aspecto | Dimensiones aproximadas (píxeles) |
|--------------------------------------|---------------------|-----------------------------------|
| `DatabarAspectRatio15.png`           | 15                  | 200 × 300 (ancho × alto)           |
| `DatabarAspectRatio30.png`           | 30                  | 200 × 600 (ancho × alto)           |

Ambas imágenes contienen un código de barras DataBar claro y escaneable que codifica el identificador GS1 `(01)12345678901231`.

## Preguntas comunes y casos límite

### ¿Cómo cambiar otras propiedades visuales?

Puedes ajustar el color de primer plano, el color de fondo o añadir texto legible por humanos a través del objeto `generator.Parameters.Barcode`. Por ejemplo:

```csharp
generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
generator.Parameters.Barcode.CodeTextParameters.ShowCodeText = true;
```

### ¿Qué pasa si necesito un formato de imagen diferente?

Reemplaza `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` o `Gif` según sea necesario. PNG sigue siendo la mejor opción para imágenes de códigos de barras sin pérdida.

### ¿Afecta la relación de aspecto a la velocidad de escaneo?

Relaciones de aspecto mayores aumentan la altura del código de barras, lo que puede mejorar la fiabilidad del escaneo en dispositivos que tienen dificultades con símbolos apilados cortos. Sin embargo, códigos de barras extremadamente altos pueden no caber en etiquetas pequeñas, por lo que es necesario probar con el hardware objetivo.

### ¿Puedo generar varios códigos de barras en un bucle?

Sí. Crea una nueva instancia de `BarcodeGenerator` para cada cadena de datos o reutiliza la misma instancia actualizando `CodeText` y `DataBar.AspectRatio`. Este enfoque reduce la sobrecarga de asignación de objetos.

## Consejos profesionales

- **Reutiliza el generador**: Cambiar solo `CodeText` o `AspectRatio` evita volver a instanciar el objeto, lo que acelera el procesamiento por lotes.
- **Valida la salida**: Usa un escáner manual o una aplicación móvil para confirmar que el PNG generado se lee correctamente antes de desplegarlo en producción.
- **Nombrado de archivos**: Incluye la relación de aspecto en el nombre del archivo (como se muestra) para llevar un registro de las variantes durante las pruebas.

## Conclusión

Ahora sabes cómo **crear archivos PNG de códigos de barras** en C# y exactamente **cómo cambiar la relación de aspecto** para símbolos DataBar omnidireccionales apilados. El ejemplo completo muestra la inicialización, la configuración de la dimensión X, la manipulación de la relación de aspecto y el guardado de la imagen, todo en un solo programa ejecutable.

A partir de aquí puedes explorar tipos de códigos de barras adicionales, experimentar con colores o integrar el generador en un sistema de informes o de inventario más amplio. ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Customize Barcode - Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}