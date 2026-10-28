---
category: general
date: 2026-10-28
description: Crea una imagen de código de barras en C# rápidamente. Aprende el uso
  del generador de códigos de barras en C#, cómo establecer el tamaño de píxel y cómo
  cambiar la relación de aspecto para DataBar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- how to set pixel size
- how to change aspect ratio
- how to generate databar
language: es
lastmod: 2026-10-28
og_description: Crea una imagen de código de barras en C# con un generador de códigos
  de barras. Sigue esta guía para establecer el tamaño de píxel, cambiar la relación
  de aspecto y generar códigos de barras DataBar.
og_image_alt: Screenshot of a generated barcode image created with C#
og_title: Crear imagen de código de barras en C# – guía paso a paso
schemas:
- author: GroupDocs
  dateModified: '2026-10-28'
  description: Create barcode image in C# quickly. Learn barcode generator c# usage,
    how to set pixel size, and how to change aspect ratio for DataBar.
  headline: How to create barcode image with C# using Barcode Generator
  type: TechArticle
tags:
- barcode
- C#
- imaging
title: Cómo crear una imagen de código de barras con C# usando Barcode Generator
url: /es/python-java/general/how-to-create-barcode-image-with-c-using-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear una imagen de código de barras con C# usando Barcode Generator

Si necesitas **crear una imagen de código de barras** en una aplicación .NET, esta guía te muestra exactamente cómo hacerlo. Verás un ejemplo completo y ejecutable que utiliza la biblioteca Barcode Generator C# para generar un código de barras DataBar apilado omnidireccional, establecer el tamaño de píxel y cambiar la relación de aspecto.

Generar códigos de barras programáticamente elimina la necesidad de herramientas externas y te permite incrustar la imagen directamente en PDFs, informes o controles de UI. En los pasos a continuación también cubrimos **cómo establecer el tamaño de píxel** y **cómo cambiar la relación de aspecto**, dos requisitos comunes cuando necesitas un código de barras nítido y correctamente escalado.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* SDK de .NET 6.0 o posterior instalado  
* Un IDE compatible con C# (Visual Studio, Rider o VS Code)  
* El paquete NuGet `BarcodeGenerator` (por ejemplo, `GroupDocs.Barcode` o `Aspose.Barcode`) instalado en tu proyecto  

Puedes agregar el paquete con el siguiente comando:

```bash
dotnet add package GroupDocs.Barcode
```

> **Consejo profesional:** Verifica que la versión del paquete coincida con tu framework de destino para evitar incompatibilidades en tiempo de ejecución.

## Crear una imagen de código de barras con Barcode Generator C#

El primer paso es instanciar el generador con el tipo de código de barras y los datos deseados. El ejemplo a continuación crea un código de barras **DataBar apilado omnidireccional**, ideal para escenarios de escaneo en retail.

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // Step 1: Create a BarcodeGenerator for DataBar stacked omnidirectional
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example data

        // Step 2: Set the pixel size of the X‑dimension (how to set pixel size)
        barcode.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 3: Save an image with the first aspect ratio (how to generate databar)
        barcode.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcode.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // Step 4: Change the aspect ratio (how to change aspect ratio) and save a second image
        barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcode.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### Por qué cada línea es importante

* **Instanciar `BarcodeGenerator`** – El constructor recibe una simbología de código de barras (`EncodeTypes.DatabarStackedOmniDirectional`) y la cadena de datos sin procesar. Elegir la simbología correcta garantiza que el escáner pueda leer el código.  
* **Establecer `XDimension.Pixels`** – Esta propiedad controla el ancho del elemento de barra más pequeño. Un valor de `2` produce una imagen de gran detalle que sigue siendo legible en la mayoría de pantallas. Aumenta el valor si necesitas un código de barras más grande para impresoras de baja resolución.  
* **Configurar `AspectRatio`** – La familia DataBar admite varias relaciones de aspecto que afectan la relación altura‑ancho. Los valores `15` y `30` son comunes; `15` genera un código de barras más corto, mientras que `30` produce uno más alto.  
* **Método `Save`** – Guarda el código de barras generado en un archivo PNG. Puedes reemplazar `BarCodeImageFormat.Png` por `Jpeg` o `Bmp` si tu sistema downstream requiere otro formato.

## Cómo establecer el tamaño de píxel para diferentes contextos de renderizado

El tamaño de píxel determina la densidad visual del código de barras. Si el código se mostrará en un monitor de alta DPI, podrías aumentar el tamaño de píxel a `3` o `4`. Por el contrario, para impresoras térmicas de baja resolución, un tamaño de píxel más pequeño (p. ej., `1`) reduce el consumo de tinta.

```csharp
// Example: increase pixel size for a high‑resolution display
barcode.Parameters.Barcode.XDimension.Pixels = 4;
```

**Caso límite:** Establecer el tamaño de píxel demasiado bajo (< 1) lanza una `ArgumentOutOfRangeException`. Siempre valida el valor antes de asignarlo.

## Cómo cambiar la relación de aspecto sin recrear el generador

Cambiar la relación de aspecto es una simple actualización de propiedad; **no** necesitas recrear la instancia de `BarcodeGenerator`. Esto ahorra memoria y mejora el rendimiento cuando necesitas varias imágenes con diferentes formas.

```csharp
// Switch from a short to a tall barcode
barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
barcode.Save("TallDatabar.png", BarCodeImageFormat.Png);
```

Si necesitas más de dos relaciones, puedes iterar sobre un arreglo:

```csharp
int[] ratios = { 15, 20, 25, 30 };
foreach (int ratio in ratios)
{
    barcode.Parameters.Barcode.DataBar.AspectRatio = ratio;
    string fileName = $"DatabarAspectRatio{ratio}.png";
    barcode.Save(fileName, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {fileName}");
}
```

## Resultado esperado

Al ejecutar el programa se crean dos archivos PNG (o más, si usas el bucle). Ábrelos en cualquier visor de imágenes; deberías ver un código de barras DataBar limpio:

* **DatabarAspectRatio15.png** – código de barras corto y ancho, adecuado para espacios de etiqueta estrechos.  
* **DatabarAspectRatio30.png** – código de barras más alto que mejora la fiabilidad de escaneo en escáneres angulados.

Ambas imágenes comparten el mismo tamaño de píxel (2 px por módulo) pero difieren solo en la altura, demostrando **cómo cambiar la relación de aspecto** manteniendo constantes los demás parámetros.

## Problemas comunes y cómo evitarlos

| Síntoma | Causa | Solución |
|---------|-------|----------|
| El código de barras aparece borroso | `XDimension.Pixels` configurado demasiado bajo para la resolución de salida | Aumenta el tamaño de píxel al menos a `2` para pantalla, `3` para impresión |
| El escáner no puede leer el código | `EncodeTypes` incorrecto para el formato de datos | Verifica que los datos GTIN‑14 coincidan con la simbología elegida |
| `ArgumentOutOfRangeException` en la relación de aspecto | Valor de relación no soportado por la biblioteca (rango válido: 15‑30) | Usa solo los valores documentados por la biblioteca, o captura la excepción y recurre a un valor predeterminado |
| Archivo no encontrado después de `Save` | La ruta relativa apunta a un directorio inexistente | Usa una ruta absoluta o asegura que se llame `Directory.CreateDirectory` primero |

```csharp
// Ensure the output folder exists
string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputDir);
barcode.Save(Path.Combine(outputDir, "DatabarAspectRatio15.png"), BarCodeImageFormat.Png);
```

## Próximos pasos – ampliando el flujo de trabajo del código de barras

Ahora que puedes **crear una imagen de código de barras**, podrías querer:

* **Incrustar el PNG en un PDF** usando una biblioteca como `PdfSharp` o `iTextSharp`.  
* **Generar otras simbologías** (QR, Code128, PDF417) cambiando el enum `EncodeTypes`.  
* **Aplicar transformaciones de color** accediendo a `barcode.Parameters.Barcode.Image.Color`.  
* **Servir la imagen mediante un endpoint ASP.NET Core** para generación bajo demanda en aplicaciones web.

Cada uno de estos temas se basa en los mismos conceptos centrales cubiertos en este tutorial, como el uso de **barcode generator c#**, control del tamaño de píxel y manipulación de la relación de aspecto.

## Conclusión

Ahora sabes cómo **crear una imagen de código de barras** en C# con Barcode Generator, cómo establecer el tamaño de píxel, cómo cambiar la relación de aspecto y cómo generar códigos DataBar de manera eficiente. El ejemplo completo y ejecutable puede copiarse en cualquier proyecto .NET, adaptarse a otras simbologías y ampliarse para ajustarse a flujos de trabajo del mundo real.

Siéntete libre de experimentar con diferentes valores de `XDimension`, relaciones de aspecto y formatos de salida. Si encuentras problemas, revisa la tabla “Problemas comunes” o consulta la documentación oficial de la biblioteca para opciones de configuración más avanzadas. ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [How to create barcode image and adjust its aspect ratio in C#](/barcode/english/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/)
- [How to generate barcode set custom size and save image in C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [How to use a barcode generator C# to create DataBar barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}