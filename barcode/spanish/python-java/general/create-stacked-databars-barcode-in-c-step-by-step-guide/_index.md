---
category: general
date: 2026-10-02
description: Crea códigos de barras de barras de datos apiladas en C# rápidamente.
  Aprende a establecer XDimension, ajustar la relación de aspecto y exportar imágenes
  PNG con un generador de códigos de barras.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create stacked databars barcode
- C# barcode generator
- DataBar stacked omnidirectional
- barcode aspect ratio
- XDimension pixel size
- BarCodeImageFormat PNG
language: es
lastmod: 2026-10-02
og_description: Crea códigos de barras de barras de datos apiladas en C# con un ejemplo
  completo de código. Ajusta XDimension, cambia la relación de aspecto y guarda archivos
  PNG en solo unas pocas líneas.
og_image_alt: Screenshot showing a create stacked databars barcode example generated
  with C#
og_title: Crear código de barras de barras de datos apiladas en C# – tutorial rápido
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create stacked databars barcode in C# quickly. Learn to set XDimension,
    adjust aspect ratio, and export PNG images with a barcode generator.
  headline: Create stacked databars barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- Aspose
- image generation
title: Crear código de barras de barras de datos apiladas en C# – guía paso a paso
url: /es/python-java/general/create-stacked-databars-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear código de barras DataBar apilado en C# – guía paso a paso

Si necesitas **crear un código de barras DataBar apilado** en un proyecto .NET, este tutorial te muestra exactamente cómo. Verás cómo configurar la X‑dimensión, cambiar las relaciones de aspecto y guardar el resultado como archivos PNG, todo con la biblioteca Aspose.BarCode.

Generar un código de barras DataBar apilado no requiere una canalización gráfica compleja. Al final de esta guía tendrás dos imágenes PNG listas para usar que ilustran diferentes relaciones de aspecto, y comprenderás por qué esos parámetros son importantes para la fiabilidad del escaneo.

## Lo que necesitarás

- .NET 6.0 o posterior (el código también funciona con .NET Framework 4.6+)
- Visual Studio 2022 o cualquier IDE de C#
- **Aspose.BarCode for .NET** paquete NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Permiso de escritura en una carpeta donde se guardarán los archivos PNG

## Paso 1: Configura el proyecto e importa los espacios de nombres

Crea una nueva aplicación de consola (o agrega el código a un proyecto existente) e importa los espacios de nombres requeridos:

```csharp
using System;
using Aspose.BarCode.Generation;   // BarcodeGenerator lives here
using Aspose.BarCode;               // BarCodeImageFormat enum
```

> **Por qué es importante:** `Aspose.BarCode.Generation` proporciona la clase `BarcodeGenerator`, mientras que `Aspose.BarCode` contiene la enumeración `BarCodeImageFormat` utilizada para guardar imágenes.

## Paso 2: Inicializa el generador para un DataBar omnidireccional apilado

El valor `EncodeTypes.DatabarStackedOmniDirectional` selecciona la simbología DataBar apilada. La cadena de datos debe seguir el formato del Identificador de Aplicación (AI) de GS1; aquí usamos un valor GTIN‑14 ficticio.

```csharp
// Initialise a generator for a stacked omnidirectional DataBar barcode
var barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

> **Por qué es importante:** El tipo de codificación elegido indica a la biblioteca que renderice un código de barras *apilado*, lo cual es esencial para etiquetas de alta densidad donde el espacio vertical es limitado.

## Paso 3: Define el tamaño del módulo (X‑dimensión) en píxeles

La X‑dimensión controla el ancho de la barra más pequeña (el “módulo”). Un valor de 2 píxeles funciona bien para la mayoría de salidas de resolución de pantalla.

```csharp
// Set the X‑dimension to 2 pixels (module width)
barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Por qué es importante:** Los escáneres interpretan el ancho del módulo como la unidad básica de medida. Un valor demasiado pequeño puede producir impresiones borrosas; uno demasiado grande desperdicia espacio.

## Paso 4: Guarda la primera imagen con una relación de aspecto de 15

La propiedad `AspectRatio` influye en la relación altura‑ancho de cada segmento apilado. Una relación de aspecto de 15 es un valor predeterminado común para aplicaciones minoristas.

```csharp
// Apply aspect ratio 15 and save the first PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

> **Por qué es importante:** Una relación de aspecto menor produce un código de barras más plano, lo que puede facilitar el escaneo en ciertos materiales de etiqueta. El formato PNG conserva la calidad sin pérdidas para pruebas.

## Paso 5: Cambia la relación de aspecto a 30 y guarda la segunda imagen

Aumentar la relación de aspecto hace que cada segmento apilado sea más alto, lo que puede mejorar la fiabilidad del escaneo en fondos de bajo contraste.

```csharp
// Apply aspect ratio 30 and save the second PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

> **Por qué es importante:** Diferentes minoristas o socios logísticos pueden requerir dimensiones específicas del código de barras. Proporcionar ambas versiones te permite comparar rápidamente el rendimiento del escaneo.

## Ejemplo completo y ejecutable

A continuación tienes el programa completo que puedes copiar y pegar en `Program.cs`. Compila y ejecuta sin modificaciones después de instalar el paquete NuGet Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace StackedDataBarDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for stacked omnidirectional DataBar
            var barcodeGen = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Define the module (X‑dimension) size in pixels
            barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Save first image with aspect ratio 15
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio15.png");

            // 4️⃣ Save second image with aspect ratio 30
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio30.png");
        }
    }
}
```

### Resultado esperado

Al ejecutar el programa se crean dos archivos en la carpeta de ejecución:

| Nombre del archivo               | Relación de aspecto | Descripción visual |
|----------------------------------|---------------------|--------------------|
| `DatabarAspectRatio15.png`       | 15                  | Código de barras apilado más corto y plano |
| `DatabarAspectRatio30.png`       | 30                  | Código de barras apilado más alto y alargado |

Puedes abrir los archivos PNG con cualquier visor de imágenes para verificar que el código de barras se renderiza correctamente.

![Crear código de barras DataBar apilado ejemplo](placeholder-image.png){alt="Crear código de barras DataBar apilado ejemplo"}

## Preguntas frecuentes y casos límite

| Pregunta | Respuesta |
|----------|-----------|
| **¿Puedo usar una X‑dimensión diferente?** | Sí. Los valores típicos van de 1 a 4 píxeles. Valores mayores aumentan el tamaño del código de barras pero pueden mejorar la legibilidad en impresoras de baja resolución. |
| **¿Qué pasa si necesito una simbología distinta?** | Reemplaza `EncodeTypes.DatabarStackedOmniDirectional` por otro valor de `EncodeTypes`, como `DatabarStacked` (no omnidireccional) o `DatabarLimited`. |
| **¿Cómo cambio el formato de salida?** | Usa `BarCodeImageFormat.Jpeg`, `Gif` o `Bmp` en la llamada a `Save`. |
| **¿Es obligatorio el formato GTIN‑14?** | La simbología DataBar espera una cadena numérica con el AI apropiado (p. ej., `(01)` para GTIN‑14). Ajusta los datos según tu caso de uso. |
| **¿Qué pasa con la configuración de DPI?** | El generador respeta la propiedad `Resolution`. Para impresiones de alta resolución, establece `barcodeGen.Parameters.ImageResolution.DpiX` y `DpiY` según corresponda. |

## Consejos profesionales

- **Generación por lotes:** Envuelve la lógica de guardado en un bucle y pásale una lista de GTINs para producir miles de códigos de barras automáticamente.
- **Validación:** Usa `barcodeGen.Validate()` antes de guardar para detectar datos mal formados temprano.
- **Rendimiento:** Reutilizar la misma instancia de `BarcodeGenerator` (cambiando solo los parámetros) es más rápido que crear un nuevo objeto para cada imagen.

## Próximos pasos

Ahora que puedes **crear códigos de barras DataBar apilados** con relaciones de aspecto personalizadas, considera explorar:

- Añadir texto legible por humanos bajo el código de barras (`barcodeGen.Parameters.Barcode.CodeText`).
- Exportar a **PDF** para hojas de etiquetas imprimibles (`BarCodeImageFormat.Pdf`).
- Integrar el generador en una API web para servir códigos de barras bajo demanda.
- Experimentar con otras **palabras clave secundarias** como *generador de códigos de barras C#* y *relación de aspecto del código de barras* para afinar tu implementación según el hardware específico.

¡Feliz codificación y disfruta de la flexibilidad que Aspose.BarCode aporta a tus proyectos de códigos de barras en C#!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Crear código de barras DataBar apilado en C# – guía paso a paso](/barcode/english/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/)
- [Código de barras DataBar omnidireccional apilado en C# – Guía completa](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [Cómo crear imágenes PNG de DataBar con C# y Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}