---
category: general
date: 2026-11-20
description: Crea rápidamente una imagen de código de barras postal en C#. Aprende
  a generar códigos de barras Planet y RM4SCC con estilos de barra personalizables.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- postal barcode C#
- Aspose.BarCode example
- barcode image generation
language: es
lastmod: 2026-11-20
og_description: Crear imagen de código de barras postal en C# con Aspose.BarCode.
  Este tutorial muestra cómo generar códigos de barras Planet, personalizar estilos
  de barras y producir imágenes RM4SCC.
og_image_alt: Create postal barcode image example showing filled and empty bars
og_title: Crear imagen de código de barras postal en C# – guía paso a paso
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Create postal barcode image in C# quickly. Learn how to generate planet
    barcode and RM4SCC barcodes with customizable bar styles.
  headline: Create postal barcode image and generate planet barcode
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Crear imagen de código de barras postal y generar código de barras planetario
url: /es/python-java/general/create-postal-barcode-image-and-generate-planet-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear imagen de código de barras postal y generar código de barras Planet

Cree una imagen de código de barras postal en C# usando la biblioteca Aspose.BarCode. Si necesita generar códigos de barras Planet o RM4SCC para aplicaciones de envío, este tutorial ofrece una solución completa y lista para ejecutar.

Generar códigos de barras para servicios postales a menudo requiere dimensiones precisas y la opción de alternar entre estilos de barras llenas y vacías. Esta guía le muestra cómo configurar la carpeta de salida, crear códigos de barras Planet tanto llenos como vacíos, y producir un código de barras RM4SCC con la misma configuración visual. Al final tendrá cuatro archivos PNG que podrá usar directamente en su flujo de trabajo de envío.

## Prerequisites

Antes de comenzar, asegúrese de tener:

* .NET 6.0 o posterior instalado  
* Visual Studio 2022 (o cualquier IDE de C# que prefiera)  
* El paquete NuGet **Aspose.BarCode** (`Install-Package Aspose.BarCode`)  

No se requiere configuración adicional; el código usa solo la fuente predeterminada y el codificador PNG.

## Create postal barcode image – overview

El núcleo del proceso es la clase `BarcodeGenerator`. Acepta un valor `EncodeTypes` que determina la simbología del código de barras (por ejemplo, `EncodeTypes.Planet` para un código de barras Planet). Después de configurar el generador, llama a `Save` para escribir el archivo de imagen.

![Create postal barcode image example](/images/postal_barcode_example.png)

*Alt text: Ejemplo de creación de imagen de código de barras postal que muestra barras llenas y vacías.*

## Step 1: Set up the output folder

Primero defina una carpeta donde se guardarán los archivos PNG. Usar una ruta absoluta o relativa funciona igual; solo asegúrese de que la carpeta exista o permita que el código la cree.

```csharp
using System.IO;
using Aspose.BarCode.Generation;

// Define the output folder (change to your own path)
string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
```

Crear la carpeta programáticamente evita `DirectoryNotFoundException` cuando el tutorial se ejecuta en una máquina nueva.

## Step 2: Generate planet barcode with filled bars

Un código de barras Planet con barras llenas es el estilo visual predeterminado. El siguiente código crea el código de barras, establece la X‑dimension a 4 píxeles (un tamaño común para aplicaciones postales) y guarda la imagen.

```csharp
// Step 2: Generate a Planet barcode with filled bars
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save as PNG
string planetFilledPath = Path.Combine(outputFolder, "PostalPlanetFilledBars.png");
planetFilled.Save(planetFilledPath, BarCodeImageFormat.Png);
```

**Por qué funciona esto:**  
* `EncodeTypes.Planet` indica al generador que use la simbología Planet, que es requerida por muchos servicios postales.  
* `XDimension.Pixels` controla el ancho de cada barra; 4 px produce una imagen clara y escaneable sin un tamaño de archivo excesivo.  
* El método `Save` selecciona automáticamente el codificador PNG basado en el enum `BarCodeImageFormat`.

## Step 3: Generate planet barcode with empty bars

Algunas especificaciones postales prefieren barras vacías (blancas) sobre un fondo oscuro. Puede lograrlo configurando `FilledBars` a `false`.

```csharp
// Step 3: Generate a Planet barcode with empty bars
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for consistency
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars – the bars become transparent (empty)
planetEmpty.Parameters.Barcode.FilledBars = false;

// Save the result
string planetEmptyPath = Path.Combine(outputFolder, "PostalPlanetEmptyBars.png");
planetEmpty.Save(planetEmptyPath, BarCodeImageFormat.Png);
```

**Consejo:** Cuando `FilledBars` es `false`, el generador pinta las barras con el color de fondo (blanco por defecto) y los espacios con el color de primer plano (negro). Si necesita un esquema de colores diferente, ajuste `Parameters.Barcode.ForeColor` y `BackColor`.

## Step 4: Generate RM4SCC barcode with filled bars

RM4SCC es otra simbología postal utilizada en el Reino Unido. Los pasos de creación reflejan el ejemplo de Planet; solo cambia el valor de `EncodeTypes`.

```csharp
// Step 4: Generate an RM4SCC barcode with filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Reuse the same X‑dimension for a uniform look
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save the PNG file
string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png");
rm4sccFilled.Save(rm4sccPath, BarCodeImageFormat.Png);
```

**Qué esperar:** El PNG resultante muestra un código de barras RM4SCC compacto que cumple con las directrices postales del Reino Unido. El tamaño de la imagen será similar al de los códigos de barras Planet porque la X‑dimension es idéntica.

## Step 5: Verify the generated images

Después de ejecutar el programa, abra los cuatro archivos en la carpeta `Barcodes`. Debería ver:

* `PostalPlanetFilledBars.png` – barras oscuras sobre un fondo claro  
* `PostalPlanetEmptyBars.png` – barras claras sobre un fondo oscuro (inverso)  
* `PostalRM4SCCFilledBars.png` – patrón RM4SCC estándar  

Si alguna imagen se ve distorsionada, revise lo siguiente:

* **X‑dimension** – demasiado pequeña (< 2 px) puede causar desenfoque; demasiado grande (> 10 px) puede exceder los límites de tamaño de la etiqueta.  
* **Data string** – el valor `"123456"` debe cumplir con los requisitos de longitud de la simbología elegida (Planet requiere 6 dígitos, RM4SCC también requiere 6 dígitos).  
* **Folder permissions** – asegúrese de que la aplicación tenga permiso de escritura en el directorio de salida.

## Common variations and edge cases

| Scenario | Adjustment |
|----------|------------|
| **Datos de código de barras diferentes** | Reemplace `"123456"` por cualquier cadena numérica válida. Para Planet, la longitud debe ser exactamente 6 dígitos; RM4SCC también requiere 6 dígitos. |
| **Colores personalizados** | Establezca `planetFilled.Parameters.Barcode.ForeColor = System.Drawing.Color.DarkBlue;` y `BackColor = System.Drawing.Color.LightYellow;`. |
| **Mayor resolución** | Aumente `XDimension.Pixels` a 6 o 8 para impresiones más grandes. |
| **Otros formatos de imagen** | Use `BarCodeImageFormat.Jpeg` o `BarCodeImageFormat.Bmp` en la llamada a `Save`. |
| **Generación por lotes** | Recorra una colección de cadenas y llame a la misma lógica del generador dentro del bucle, reutilizando la ruta `outputFolder`. |

## Full, runnable example

Copie el código a continuación en un nuevo proyecto de consola C#. Compila con .NET 6.0 y produce automáticamente los cuatro imágenes de códigos de barras.



## What Should You Learn Next?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos con explicaciones paso a paso para ayudarle a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en sus propios proyectos.

- [Cómo crear una imagen de código de barras postal con alturas personalizadas en C#](/barcode/english/python-java/general/how-to-create-postal-barcode-image-with-custom-heights-in-c/)
- [Cómo crear un código de barras RM4SCC y generar un código de barras Planet en C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-generate-planet-barcode-in/)
- [Crear imagen de código de barras postal en C# – guía paso a paso](/barcode/english/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}