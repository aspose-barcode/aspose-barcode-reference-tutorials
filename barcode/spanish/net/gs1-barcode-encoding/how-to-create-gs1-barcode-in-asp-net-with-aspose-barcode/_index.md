---
category: general
date: 2026-10-24
description: Aprende a crear códigos de barras GS1 en ASP.NET usando Aspose.BarCode.
  Guía paso a paso para generar el código de barras a partir de una cadena y renderizarlo
  en PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to create GS1 barcode
- generate barcode from string
- barcode generator asp.net
- create barcode with aspose
language: es
lastmod: 2026-10-24
og_description: Cómo crear un código de barras GS1 en ASP.NET usando Aspose.BarCode.
  Sigue este tutorial para generar el código de barras a partir de una cadena, configurar
  los ajustes visuales y guardar archivos PNG.
og_image_alt: Screenshot of a generated GS1 Micro PDF417 barcode saved as PNG
og_title: Cómo crear un código de barras GS1 en ASP.NET – guía completa de Aspose
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to create GS1 barcode in ASP.NET using Aspose.BarCode. Step‑by‑step
    guide to generate barcode from string and render PNG.
  headline: How to create GS1 barcode in ASP.NET with Aspose.BarCode
  type: TechArticle
- description: Learn how to create GS1 barcode in ASP.NET using Aspose.BarCode. Step‑by‑step
    guide to generate barcode from string and render PNG.
  name: How to create GS1 barcode in ASP.NET with Aspose.BarCode
  steps:
  - name: 4.1 Prepare the GS1 data string
    text: 'GS1 data must be wrapped in parentheses with the AI code. For a product
      identifier (01) and a batch number (10) the string looks like:'
  - name: 4.2 Build the GS1 Micro PDF417 generator
    text: '```csharp public static byte[] GenerateGs1MicroPdf417(string gs1Data, string
      outputFolder) { // Step 4.2.1: Create a generator for Micro PDF417 using the
      GS1 data. BarcodeGenerator gs1Generator = new BarcodeGenerator(EncodeTypes.MicroPdf417,
      gs1Data);'
  - name: 4.3 Expose the generator through an ASP.NET endpoint
    text: '```csharp app.MapGet("/gs1barcode", (HttpContext context) => { string outputFolder
      = Path.Combine(Directory.GetCurrentDirectory(), "wwwroot", "barcodes"); Directory.CreateDirectory(outputFolder);
      // Ensure the folder exists'
  type: HowTo
tags:
- Aspose.BarCode
- GS1
- ASP.NET
- C#
title: Cómo crear un código de barras GS1 en ASP.NET con Aspose.BarCode
url: /es/net/gs1-barcode-encoding/how-to-create-gs1-barcode-in-asp-net-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un código de barras GS1 en ASP.NET con Aspose.BarCode

Si necesitas **cómo crear un código de barras GS1** en una aplicación ASP.NET, esta guía te muestra los pasos exactos. Verás cómo generar un código de barras a partir de una cadena, configurar su apariencia visual y guardar el resultado como una imagen PNG.

Crear códigos de barras GS1 no requiere lógica de codificación personalizada. Al usar Aspose.BarCode obtienes una solución fiable y conforme a los estándares que funciona en .NET 6+ y versiones anteriores. Este tutorial cubre todo, desde la configuración del proyecto hasta la verificación del resultado, para que puedas copiar el código directamente a tu propio proyecto web.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* Visual Studio 2022 (o cualquier IDE que admita .NET)
* .NET 6 SDK (o .NET Framework 4.7.2 o superior)
* Conocimientos básicos de ASP.NET Core o ASP.NET Framework
* Una licencia de Aspose.BarCode (la evaluación gratuita funciona para pruebas)

No se requieren bibliotecas de terceros adicionales porque Aspose.BarCode maneja toda la codificación y renderizado internamente.

## Paso 1: Crear un nuevo proyecto ASP.NET

Abre Visual Studio y crea una **ASP.NET Core Web App** (elige la plantilla *Empty*). Para un proyecto clásico de Web Forms, el mismo código funciona dentro de un archivo code‑behind.

```csharp
// Program.cs (ASP.NET Core minimal API example)
using Microsoft.AspNetCore.Builder;
using Microsoft.Extensions.Hosting;

var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.MapGet("/", () => "GS1 barcode generator is ready.");
app.Run();
```

Ejecutar el proyecto debería mostrar *GS1 barcode generator is ready.* en el navegador. Esto confirma que el host web está operativo.

## Paso 2: Instalar Aspose.BarCode vía NuGet

Abre la **Package Manager Console** y ejecuta:

```powershell
Install-Package Aspose.BarCode
```

El paquete añade el espacio de nombres `Aspose.BarCode.Generation`, que contiene la clase `BarcodeGenerator` que usarás para **generar código de barras a partir de una cadena**. El comando NuGet también actualiza el archivo del proyecto con la referencia requerida.

## Paso 3: Generar un código de barras simple a partir de una cadena

Para ilustrar el uso básico, crea un método auxiliar que devuelva un arreglo de bytes PNG. Este método puede llamarse desde un controlador, una página Razor o cualquier endpoint.

```csharp
using Aspose.BarCode.Generation;
using System.IO;

/// <summary>
/// Generates a barcode image from the supplied text.
/// </summary>
/// <param name="text">The data to encode.</param>
/// <param name="encodeType">The barcode symbology.</param>
/// <returns>PNG image bytes.</returns>
public static byte[] GenerateBarcode(string text, EncodeTypes encodeType)
{
    // Step 3.1: Initialize the generator with the desired symbology and data.
    BarcodeGenerator generator = new BarcodeGenerator(encodeType, text);

    // Step 3.2: Set a modest module width – 2 pixels gives a clear image.
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Step 3.3: Render the barcode to a memory stream in PNG format.
    using MemoryStream ms = new MemoryStream();
    generator.Save(ms, BarCodeImageFormat.Png);
    return ms.ToArray();
}
```

Ahora puedes llamar a `GenerateBarcode("HelloWorld", EncodeTypes.Code128)` desde cualquier endpoint y escribir los bytes resultantes en la respuesta HTTP. Esto demuestra el patrón **barcode generator asp.net** para cadenas arbitrarias.

## Paso 4: Cómo crear un código de barras GS1 – ejemplo Micro PDF417

Los códigos de barras GS1 incorporan identificadores de aplicación (AIs) que transmiten información del producto. Aspose.BarCode admite la variante compatible con GS1 de Micro PDF417, ideal para representar datos de forma compacta.

### 4.1 Preparar la cadena de datos GS1

Los datos GS1 deben estar entre paréntesis con el código AI. Para un identificador de producto (01) y un número de lote (10) la cadena se ve así:

```csharp
string gs1Data = "(01)12345678901234(10)ABCD";
```

Los paréntesis forman parte del estándar; Aspose.BarCode los analiza automáticamente.

### 4.2 Construir el generador GS1 Micro PDF417

```csharp
public static byte[] GenerateGs1MicroPdf417(string gs1Data, string outputFolder)
{
    // Step 4.2.1: Create a generator for Micro PDF417 using the GS1 data.
    BarcodeGenerator gs1Generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);

    // Step 4.2.2: Apply the same visual settings used for other barcodes.
    gs1Generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Step 4.2.3: Micro PDF417 allows 1‑4 columns; 4 gives a more square shape.
    gs1Generator.Parameters.Barcode.Pdf417.Columns = 4;

    // Step 4.2.4: Save the image to the specified folder.
    string filePath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
    gs1Generator.Save(filePath, BarCodeImageFormat.Png);

    // Return the file bytes for immediate HTTP response if needed.
    return File.ReadAllBytes(filePath);
}
```

### 4.3 Exponer el generador a través de un endpoint ASP.NET

```csharp
app.MapGet("/gs1barcode", (HttpContext context) =>
{
    string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "wwwroot", "barcodes");
    Directory.CreateDirectory(outputFolder); // Ensure the folder exists

    byte[] pngBytes = GenerateGs1MicroPdf417("(01)12345678901234(10)ABCD", outputFolder);

    context.Response.ContentType = "image/png";
    return context.Response.Body.WriteAsync(pngBytes, 0, pngBytes.Length);
});
```

Visitar `https://localhost:5001/gs1barcode` ahora transmite el PNG generado. La imagen cumple con la especificación GS1, y el archivo también se guarda en disco para uso posterior.

## Paso 5: Renderizar tipos de códigos de barras adicionales

El mismo enfoque **create barcode with aspose** funciona para otras simbologías. A continuación, un ejemplo rápido que crea un código QR a partir de una URL:

```csharp
byte[] qrBytes = GenerateBarcode("https://example.com", EncodeTypes.QR);
File.WriteAllBytes(Path.Combine(outputFolder, "ExampleQR.png"), qrBytes);
```

Puedes cambiar `EncodeTypes.QR` por `EncodeTypes.Code128`, `EncodeTypes.DataMatrix` o cualquier otro tipo compatible. Los parámetros visuales (`XDimension`, `Resolution`, `Color`) son configurables mediante el objeto `Parameters`.

## Paso 6: Problemas comunes y consejos de buenas prácticas

| Problema | Por qué ocurre | Cómo evitarlo |
|----------|----------------|----------------|
| **Formato AI incorrecto** | Falta de paréntesis o longitud AI errónea causa errores de codificación. | Siempre construye la cadena GS1 exactamente como especifica el estándar. Usa un método auxiliar para concatenar AIs. |
| **Demasiadas columnas** | Micro PDF417 solo admite de 1 a 4 columnas; establecer 5 lanza una excepción. | Valida el valor de columnas antes de asignar: `if (columns < 1 || columns > 4) throw …` |
| **Baja resolución de imagen** | Valores pequeños de `XDimension` pueden hacer que el código de barras sea ilegible en impresoras. | Para códigos listos para imprimir, aumenta `Resolution` (p. ej., `generator.Parameters.Image.Resolution = 300`). |
| **Problemas de ruta de archivo en Linux** | Las barras invertidas codificadas rompen en hosts no Windows. | Usa `Path.Combine` para construir rutas de archivo; maneja los separadores según el SO. |
| **Licencia no aplicada** | La evaluación gratuita añade una marca de agua después de 30 días. | Aplica tu licencia pronto: `new License().SetLicense("Aspose.BarCode.lic");` |

## Paso 7: Verificar el código de barras generado

Después de ejecutar el endpoint, abre el PNG en cualquier visor de imágenes. Para confirmar que los datos GS1 están codificados correctamente, puedes usar un escáner móvil gratuito que admita GS1 Micro PDF417 (muchas apps de escáner listan esta simbología). Escanea la imagen; la app debería devolver:

```
(01)12345678901234
(10)ABCD
```

Si el escáner informa un error, revisa el formato AI y el número de columnas.

## Conclusión

Ahora sabes **cómo crear un código de barras GS1** en un entorno ASP.NET usando Aspose.BarCode. El tutorial cubrió:

* Configurar un proyecto ASP.NET e instalar el paquete NuGet Aspose.BarCode.  
* Usar **generate barcode from string** para códigos de barras genéricos.  
* Implementar **create barcode with aspose** para producir una imagen Micro PDF417 compatible con GS1.  
* Guardar la imagen en disco y transmitirla mediante un endpoint HTTP.  

A partir de aquí puedes explorar otras simbologías GS1 (p. ej., GS1 DataMatrix) o integrar el generador en un flujo de trabajo de procesamiento de pedidos más amplio. Experimenta con diferentes valores de `XDimension`, colores y niveles de corrección de errores para adaptarlos a tu marca y entorno de escaneo.

¡Feliz codificación, y que tus aplicaciones hablen el lenguaje universal de los códigos de barras!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo crear un código de barras code 128 con GS1 usando Aspose.BarCode](/barcode/english/net/gs1-barcode-encoding/gs1-code-128-example/)
- [Cómo crear una zona silenciosa para códigos de barras ITF-14 usando Aspose.BarCode para .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Cómo crear códigos de barras ITF-14 en .NET – Tutoriales completos de Aspose.BarCode](/barcode/english/net/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}