---
category: general
date: 2026-10-21
description: Aprenda cómo generar códigos de barras PDF417 en C# usando Aspose.BarCode.
  Los pasos detallados cubren la configuración del código de barras PDF417, la creación
  de códigos de barras macro PDF417 y el guardado como PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate PDF417 barcode
- PDF417 barcode settings
- Macro PDF417 barcode
- barcode generator C#
- BarCodeImageFormat PNG
- EncodeTypes.MacroPdf417
language: es
lastmod: 2026-10-21
og_description: Cómo generar un código de barras PDF417 en C# usando Aspose.BarCode.
  Sigue este tutorial paso a paso para configurar los ajustes del código de barras
  PDF417, crear un código de barras PDF417 macro y exportarlo a PNG.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C# code
og_title: Cómo generar un código de barras PDF417 en C# – guía completa
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Detailed
    steps cover PDF417 barcode settings, macro PDF417 barcode creation, and saving
    as PNG.
  headline: How to generate PDF417 barcode in C# with macro support
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Detailed
    steps cover PDF417 barcode settings, macro PDF417 barcode creation, and saving
    as PNG.
  name: How to generate PDF417 barcode in C# with macro support
  steps:
  - name: '**Create a `BarcodeGenerator` instance** using `EncodeTypes.MacroPdf417`.'
    text: '**Create a `BarcodeGenerator` instance** using `EncodeTypes.MacroPdf417`.'
  - name: '**Adjust basic barcode appearance** (module size, colors, etc.).'
    text: '**Adjust basic barcode appearance** (module size, colors, etc.).'
  - name: '**Configure PDF417‑specific settings**, including macro‑related fields.'
    text: '**Configure PDF417‑specific settings**, including macro‑related fields.'
  - name: '**Save the generated barcode image** with `BarCodeImageFormat PNG`.'
    text: '**Save the generated barcode image** with `BarCodeImageFormat PNG`.'
  type: HowTo
tags:
- PDF417
- barcode
- C#
- Aspose.BarCode
title: Cómo generar código de barras PDF417 en C# con soporte de macro
url: /es/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-macro-support/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo generar un código de barras PDF417 en C# con soporte de macro

Si necesitas generar un código de barras PDF417 en C#, esta guía te muestra una solución completa y lista para ejecutar. Ya sea que estés construyendo un sistema de etiquetas logísticas o codificando bloques de datos grandes, verás cómo configurar los ajustes del código de barras PDF417, crear un código de barras Macro PDF417 y guardar el resultado como una imagen PNG.

Generar un código de barras PDF417 no requiere manipulación de bits de bajo nivel. Al usar la clase **barcode generator C#** de Aspose.BarCode puedes centrarte en la lógica de negocio mientras la biblioteca se encarga de la codificación, corrección de errores y renderizado de la imagen.

## Lo que necesitarás

- **.NET 6.0** o posterior (el código también funciona con .NET Framework 4.6+)
- **Aspose.BarCode for .NET** paquete NuGet (`Install-Package Aspose.BarCode`)
- Un entorno de desarrollo como Visual Studio 2022 o Visual Studio Code
- Permiso de escritura en una carpeta donde se guardará la imagen PNG

Estos requisitos previos garantizan que el ejemplo compile y se ejecute sin configuración adicional.

## Cómo generar un código de barras PDF417 – visión general paso a paso

A continuación se muestra una hoja de ruta concisa del proceso:

1. **Crear una instancia de `BarcodeGenerator`** usando `EncodeTypes.MacroPdf417`.
2. **Ajustar la apariencia básica del código de barras** (tamaño del módulo, colores, etc.).
3. **Configurar los ajustes específicos de PDF417**, incluidos los campos relacionados con macro.
4. **Guardar la imagen del código de barras generado** con `BarCodeImageFormat PNG`.

Cada paso se explica en detalle, con fragmentos de código completos que puedes copiar directamente a una aplicación de consola.

## Paso 1: Configurar el entorno de desarrollo

Crea un nuevo proyecto de consola y agrega la referencia a Aspose.BarCode:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Abre `Program.cs` y agrega los espacios de nombres requeridos:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Estas importaciones te dan acceso a `BarcodeGenerator`, `EncodeTypes` y `BarCodeImageFormat`.

## Paso 2: Crear el generador de código de barras Macro PDF417

La primera línea de la implementación crea el objeto **Macro PDF417 barcode**. El enumerado `EncodeTypes.MacroPdf417` indica a la biblioteca que use la variante macro de PDF417.

```csharp
// Step 1: Create a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample Text"))
{
    // Subsequent configuration goes here
}
```

> **Por qué es importante:** Usar `EncodeTypes.MacroPdf417` habilita los campos macro (`FileID`, `SegmentID`, etc.) que te permiten dividir una carga útil grande en múltiples imágenes de código de barras mientras se preserva el orden.

## Paso 3: Ajustar la apariencia básica del código de barras

Antes de ajustar los parámetros específicos de PDF417, establece el ancho del módulo (píxel). Un valor de `2` produce una imagen clara y escaneable sin un tamaño de archivo excesivo.

```csharp
// Step 2: Adjust basic barcode appearance
generator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel width of a single module
```

También puedes cambiar los colores de primer plano/fondo aquí si tu UI requiere una paleta diferente.

## Paso 4: Configurar los ajustes específicos de PDF417

Los **ajustes del código de barras PDF417** se exponen a través de `generator.Parameters.Barcode.Pdf417`. Los campos macro más importantes se muestran a continuación:

```csharp
// Step 3: Configure PDF417‑specific settings
generator.Parameters.Barcode.Pdf417.Columns = 5;                     // number of columns (affects width)
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;     // unique file identifier
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // segment number within the file
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;  // total number of segments
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";  // optional human‑readable name
```

### Entendiendo cada propiedad

| Propiedad | Propósito | Rango típico |
|----------|-----------|--------------|
| `Columns` | Controla cuántas columnas de datos contiene cada fila. Más columnas reducen el número de filas pero aumentan el ancho. | 1 – 30 |
| `MacroPdf417FileID` | Identificador de 32 bits que agrupa todos los segmentos del mismo archivo lógico. Debe ser el mismo para cada segmento. | Cualquier entero positivo |
| `MacroPdf417SegmentID` | Índice basado en cero del segmento actual. Incrementar para cada código de barras subsiguiente. | 0 – `SegmentsCount`‑1 |
| `MacroPdf417SegmentsCount` | Número total de segmentos que componen el archivo completo. Todos los segmentos deben generarse. | ≥ 1 |
| `MacroPdf417FileName` | Nombre descriptivo opcional (máx. 255 caracteres). Útil para depuración. | Cadena alfanumérica |

> **Consejo profesional:** Mantén `Columns` entre 3 y 7 para la mayoría de impresoras de etiquetas. Valores mayores pueden exceder el ancho imprimible en dispositivos de baja resolución.

## Paso 5: Guardar el código de barras como una imagen PNG

Finalmente, escribe el código de barras en disco usando `BarCodeImageFormat PNG`. PNG conserva calidad sin pérdida, lo cual es esencial para un escaneo fiable.

```csharp
// Step 4: Save the generated barcode image
string outputPath = Path.Combine(Environment.CurrentDirectory, "MacroPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Cuando el programa termine, encontrarás `MacroPdf417.png` en la carpeta del proyecto. Al abrir el archivo se muestra un código de barras Macro PDF417 limpio listo para imprimir.

### Resultado esperado

La imagen generada se parece al ejemplo a continuación (solo ilustrativo):

![Ejemplo de código de barras Macro PDF417](macro-pdf417-barcode.png "Código de barras Macro PDF417 generado con código C#")

*El texto alternativo de la imagen es “Código de barras Macro PDF417 generado con código C#”, cumpliendo con los requisitos de accesibilidad y SEO.*

## Problemas comunes y solución de problemas

| Problema | Síntoma | Solución |
|----------|---------|----------|
| **Incorrect `EncodeTypes`** | El código de barras se renderiza como código QR o texto plano. | Asegúrate de usar `EncodeTypes.MacroPdf417` (no `EncodeTypes.Pdf417`). |
| **IDs de segmento no coincidentes** | El escáner informa “segmento faltante”. | Incrementa `MacroPdf417SegmentID` secuencialmente y mantén `SegmentsCount` consistente en todos los archivos. |
| **Tamaño de módulo demasiado grande** | El código de barras se vuelve demasiado ancho para la etiqueta. | Reduce `XDimension.Pixels` o disminuye `Columns`. |
| **Errores de ruta de archivo** | `UnauthorizedAccessException` al guardar. | Escribe en una carpeta que poseas, por ejemplo, `Environment.CurrentDirectory`. |
| **Paquete NuGet faltante** | Error de compilación: `BarcodeGenerator` no encontrado. | Ejecuta `dotnet add package Aspose.BarCode` antes de compilar. |

Abordar estos problemas temprano ahorra tiempo al integrar la generación de códigos de barras en flujos de trabajo más grandes.

## Extender el ejemplo

Ahora que puedes generar un solo código de barras Macro PDF417, considera los siguientes pasos:

- **Generación por lotes**: Recorrer una colección de fragmentos de datos, actualizando `MacroPdf417SegmentID` en cada iteración.
- **Diferentes formatos de imagen**: Reemplaza `BarCodeImageFormat.Png` por `Jpeg` o `Bmp` si tu sistema posterior prefiere esos.
- **Incrustar en PDFs**: Usa Aspose.PDF para colocar el PNG en un informe PDF para distribución.
- **Verificación de escaneo**: Prueba los códigos de barras generados con un escáner hardware o una aplicación móvil que soporte Macro PDF417.

Estas variaciones mantienen los **ajustes del código de barras PDF417** principales intactos mientras adaptan la salida a las necesidades de tu proyecto.

## Conclusión

Ahora sabes **cómo generar un código de barras PDF417** en C# usando Aspose.BarCode, desde crear un `BarcodeGenerator` con `EncodeTypes.MacroPdf417` hasta configurar los campos macro y guardar el resultado como `BarCodeImageFormat PNG`. El código completo y ejecutable demuestra el enfoque recomendado, explica por qué cada ajuste es importante y destaca los problemas comunes que podrías encontrar.

Siéntete libre de experimentar con el número de columnas, colores o formatos de salida, e integrar el generador en tus propias aplicaciones para una codificación de datos fiable y de alta densidad.

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo generar códigos de barras PDF417 en C# con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/)
- [Cómo crear un código de barras macro PDF417 en C# usando Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Cómo guardar el código de barras y generar PDF417 con Aspose en C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}