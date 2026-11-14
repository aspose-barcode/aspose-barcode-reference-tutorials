---
category: general
date: 2026-11-14
description: Aprende a crear códigos de barras PDF417 en C# rápidamente. Esta guía
  también muestra cómo generar PDF417 y cómo personalizar la configuración de PDF417
  para un control preciso.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417
- how to customize pdf417
language: es
lastmod: 2026-11-14
og_description: Crea códigos de barras PDF417 en C# con instrucciones paso a paso.
  Aprende cómo generar PDF417 y cómo personalizar los parámetros de PDF417 para obtener
  resultados exactos.
og_image_alt: Screenshot showing a generated PDF417 barcode created with C# code
og_title: Crear código de barras PDF417 en C# – guía completa con diseño personalizado
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  headline: How to create PDF417 barcode with custom layout in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  name: How to create PDF417 barcode with custom layout in C#
  steps:
  - name: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
    text: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
  - name: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
    text: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
  - name: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
    text: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
  type: HowTo
tags:
- barcode
- pdf417
- C#
title: Cómo crear un código de barras PDF417 con diseño personalizado en C#
url: /es/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-custom-layout-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un código de barras PDF417 con diseño personalizado en C#

Si necesitas **create pdf417 barcode** para un sistema de tickets, una etiqueta de inventario o escaneo desde una aplicación móvil, este tutorial muestra el proceso completo. Verás cómo generar PDF417 rápidamente y cómo personalizar la configuración de PDF417, como columnas y filas, para que el código de barras se ajuste a tus restricciones de diseño.

Generar un código de barras no requiere una biblioteca gráfica compleja—solo Aspose.BarCode para .NET (o cualquier API compatible). Al final de esta guía tendrás un archivo PNG listo para usar que puedes incrustar en PDFs, páginas web o imprimir directamente desde tu aplicación.

## Prerrequisitos

- .NET 6.0 o posterior (el código también funciona con .NET Framework 4.7+)
- Aspose.BarCode para .NET (paquete NuGet `Aspose.BarCode`)
- Familiaridad básica con C# y Visual Studio (o cualquier IDE)

> **Pro tip:** Si utilizas una canalización CI/CD, agrega la referencia al paquete NuGet en tu archivo de proyecto para que las compilaciones permanezcan reproducibles.

## Paso 1: Instalar la biblioteca de códigos de barras

Abre la carpeta de tu proyecto en una terminal y ejecuta:

```bash
dotnet add package Aspose.BarCode
```

El paquete incluye la clase `BarcodeGenerator` que se usa a lo largo de este tutorial. No se requieren dependencias nativas adicionales.

## Paso 2: Crear un código de barras PDF417 básico

El primer objetivo es **create pdf417 barcode** con la configuración predeterminada. El siguiente programa configura el generador, codifica una cadena de ejemplo y guarda el resultado como una imagen PNG.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417Demo
{
    static void Main()
    {
        // Step 2.1: Initialise the generator for PDF417 with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample text for PDF417");

        // Step 2.2: Save the barcode as PNG
        string outputPath = "Pdf417Default.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

**Por qué funciona:**  
`EncodeTypes.Pdf417` indica a la biblioteca que use la simbología PDF417. El constructor crea automáticamente un objeto `Barcode` con valores predeterminados de columna/fila que garantizan la escaneabilidad para la mayoría de los casos de uso.

Ejecuta el programa (`dotnet run`). Encontrarás `Pdf417Default.png` en la carpeta del proyecto. Al abrir la imagen verás un código de barras PDF417 estándar listo para escanear.

![Create PDF417 barcode example](https://example.com/images/pdf417-default.png){:alt="Create PDF417 barcode example showing default layout"}

## Paso 3: Cómo generar PDF417 con dimensiones personalizadas

A veces una etiqueta de tamaño fijo o un componente de UI requiere una huella de código de barras específica. Ahí es donde **how to generate pdf417** con columnas y filas personalizadas se vuelve esencial.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417CustomDemo
{
    static void Main()
    {
        // Initialise generator with the same text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Custom layout text");

        // ---- Customization begins here ----
        // Set the number of columns (2‑30). Fewer columns make the barcode taller.
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // Set the number of rows (1‑90). More rows make the barcode wider.
        generator.Parameters.Barcode.Pdf417.Rows = 9;
        // ------------------------------------

        // Save the customized barcode
        string outputPath = "Pdf417CustomLayout.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Custom barcode saved to {outputPath}");
    }
}
```

**Por qué podrías querer esto:**  
- **Ancho limitado:** Reducir columnas y aumentar filas crea un código más ancho pero más corto, perfecto para etiquetas estrechas.  
- **Altura limitada:** Aumentar columnas y disminuir filas produce un código más alto y estrecho, útil cuando dispones de espacio vertical.

Tanto `Columns` como `Rows` aceptan solo valores dentro de los rangos documentados (2‑30 para columnas, 1‑90 para filas). Proporcionar un valor fuera de rango lanza una `ArgumentOutOfRangeException`, así que siempre valida la entrada del usuario si expones estas configuraciones en una UI.

## Paso 4: Cómo personalizar PDF417 más allá

Además de columnas y filas, la simbología PDF417 ofrece muchos parámetros opcionales:

| Propiedad | Propósito | Valores típicos |
|-----------|-----------|-----------------|
| `ErrorLevel` | Controls error‑correction capability | 0‑8 (higher = more robust) |
| `MacroPdf417` | Enables macro PDF417 for multi‑segment data | `true`/`false` |
| `CompactPdf417` | Produces a more compact barcode at the cost of reduced error correction | `true`/`false` |
| `SecurityLevel` | Adds a security check digit | 0‑2 |

Aquí tienes un ejemplo rápido que también establece el nivel de error al máximo (8) para un entorno ruidoso:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 8;
generator.Parameters.Barcode.Pdf417.CompactPdf417 = true;
```

**Por qué es importante:**  
Una mayor corrección de errores permite a los escáneres recuperar datos incluso si parte del código está dañada. Sin embargo, también aumenta el tamaño del código, por lo que debes equilibrar este ajuste con tus limitaciones de diseño.

## Paso 5: Verificar que el código de barras funciona

Después de generar el PNG, pruébalo con cualquier aplicación escáner de códigos de barras (la mayoría de los smartphones tienen lectores PDF417 gratuitos). Si el escáner devuelve el texto original (`Custom layout text`), el código de barras es válido.

Si encuentras problemas de escaneo:

1. **Revisa dimensiones:** Asegúrate de que columnas/filas se mantengan dentro del rango permitido.  
2. **Ajusta el nivel de error:** Incrementa `ErrorLevel` para medios dañados.  
3. **Revisa la calidad de la imagen:** Guarda con un DPI mayor (`generator.Save(outputPath, BarCodeImageFormat.Png, 300)`) si planeas imprimir.

## Código fuente completo para un helper reutilizable

A continuación tienes una clase compacta y reutilizable que puedes agregar a cualquier proyecto .NET. Encapsula **how to generate pdf417** y **how to customize pdf417** en un solo método.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

public static class Pdf417Helper
{
    /// <summary>
    /// Creates a PDF417 barcode image with optional layout parameters.
    /// </summary>
    /// <param name="text">The data to encode.</param>
    /// <param name="outputPath">Full file path for the PNG output.</param>
    /// <param name="columns">Number of columns (2‑30). Pass null to use default.</param>
    /// <param name="rows">Number of rows (1‑90). Pass null to use default.</param>
    /// <param name="errorLevel">Error correction level (0‑8). Null = default.</param>
    public static void CreatePdf417(string text, string outputPath,
                                    int? columns = null,
                                    int? rows = null,
                                    int? errorLevel = null)
    {
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, text);

        // Apply optional customizations
        if (columns.HasValue) generator.Parameters.Barcode.Pdf417.Columns = columns.Value;
        if (rows.HasValue)    generator.Parameters.Barcode.Pdf417.Rows    = rows.Value;
        if (errorLevel.HasValue) generator.Parameters.Barcode.Pdf417.ErrorLevel = errorLevel.Value;

        // Save as high‑resolution PNG (300 DPI) for printing scenarios
        generator.Save(outputPath, BarCodeImageFormat.Png, 300);
    }
}
```

Puedes llamar a este helper así:

```csharp
Pdf417Helper.CreatePdf417(
    text: "Order #12345",
    outputPath: "OrderBarcode.png",
    columns: 5,
    rows: 12,
    errorLevel: 6);
```

El método abstrae la lógica repetitiva, permitiéndote centrarte en la lógica de negocio.

## Problemas comunes y cómo evitarlos

- **Valores fuera de rango:** Siempre valida `columns` y `rows` antes de asignarlos.  
- **Formato de imagen incorrecto:** Algunos escáneres heredados solo aceptan BMP o JPEG. Usa `BarCodeImageFormat.Bmp` si es necesario.  
- **DPI bajo para impresión:** El DPI predeterminado es 96. Para impresiones de alta calidad, establece explícitamente un DPI mayor (p. ej., 300) al llamar a `Save`.  
- **Falta de soporte de fuentes:** PDF417 codifica datos binarios, por lo que generalmente no necesitas especificar una fuente. Sin embargo, si superpones texto sobre la imagen, asegúrate de que la fuente esté instalada en la máquina destino.

## Conclusión

Ahora sabes cómo **create pdf417 barcode** de principio a fin, cómo **generate pdf417** con configuraciones personalizadas de columna/fila, y cómo **customize pdf417** para corrección de errores y compacidad. Siguiendo el patrón del helper reutilizable puedes generar códigos de barras bajo demanda, adaptarlos a cualquier restricción de diseño y garantizar un escaneo fiable en entornos de producción.

**Próximos pasos**

- Explora otras simbologías como QR o Code128 usando la misma clase `BarcodeGenerator`.  
- Combina la salida PNG con una biblioteca de generación de PDF (p. ej., iText7) para incrustar códigos de barras en facturas.  
- Experimenta con `MacroPdf417` para transmisión de datos multi‑segmento, una característica útil en aplicaciones de logística y transporte.

¡Feliz codificación, y que tus códigos de barras siempre se escaneen al primer intento!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [How to generate PDF417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [How to generate barcode and customize PDF417 barcode in C#](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/)
- [How to create PDF417 barcode and export PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}