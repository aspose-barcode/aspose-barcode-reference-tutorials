---
category: general
date: 2026-08-22
description: Cómo generar códigos de barras en C# usando Aspose.BarCode. Aprende a
  crear una imagen de código de barras en C# paso a paso, desactivar el componente
  2‑D y guardar archivos PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode image c#
language: es
lastmod: 2026-08-22
og_description: Cómo generar códigos de barras en C# con Aspose.BarCode. Este tutorial
  le muestra cómo crear una imagen de código de barras en C# usando DataBar Expanded,
  activar el componente 2‑D y guardar archivos PNG.
og_image_alt: C# code screenshot generating a DataBar Expanded barcode image without
  the 2‑D component
og_title: Cómo generar códigos de barras en C# – guía completa para crear una imagen
  de código de barras en C#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode in C# using Aspose.BarCode. Learn to create
    barcode image c# step‑by‑step, disable the 2‑D component, and save PNG files.
  headline: How to generate barcode in C# – create barcode image c# with DataBar Expanded
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- image generation
title: Cómo generar códigos de barras en C# – crear imagen de código de barras en
  C# con DataBar Expanded
url: /es/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo generar códigos de barras en C# – crear imagen de código de barras c# con DataBar Expanded

Generar códigos de barras en C# es un requisito frecuente cuando necesitas incrustar datos legibles por máquina en tus aplicaciones. Esta guía te muestra cómo crear una imagen de código de barras c# usando la biblioteca Aspose.BarCode, desactivar el componente compuesto 2‑D y guardar el resultado como archivos PNG.

Verás un programa completo y ejecutable, una explicación de cada opción de configuración y consejos para personalizar la salida. No se requiere documentación externa—solo el código a continuación y un entorno de desarrollo .NET.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* SDK de .NET 6.0 o posterior instalado  
* Visual Studio 2022 (o cualquier IDE que soporte .NET)  
* Paquete NuGet Aspose.BarCode para .NET (`Aspose.BarCode`)  

Puedes agregar el paquete con el siguiente comando:

```bash
dotnet add package Aspose.BarCode
```

La biblioteca proporciona la clase `BarcodeGenerator` utilizada a lo largo de este tutorial.

## Paso 1: Configurar el proyecto e importar los espacios de nombres

Crea una nueva aplicación de consola e importa los espacios de nombres requeridos:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The rest of the code lives here
        }
    }
}
```

El espacio de nombres `Aspose.BarCode.Generation` contiene todas las clases necesarias para configurar y renderizar códigos de barras.

## Paso 2: Inicializar el generador de códigos de barras DataBar Expanded

La primera línea funcional crea un `BarcodeGenerator` para la simbología **DataBar Expanded** y suministra la cadena de datos sin procesar. La cadena de datos sigue el formato de Identificador de Aplicación GS1 `(01)12345678901231`.

```csharp
// Step 2: Create a DataBar Expanded barcode generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpanded, "(01)12345678901231");
```

Crear el generador asigna el lienzo interno de mapa de bits, de modo que puedes ajustar el tamaño y la apariencia antes de renderizar.

## Paso 3: Definir el ancho del módulo (dimensión X)

La dimensión X controla el ancho del elemento más pequeño del código de barras. Configurarla en píxeles te brinda un control preciso sobre el tamaño final de la imagen.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Un valor de `2` píxeles funciona bien para la visualización en pantalla; aumentalo para impresiones de mayor resolución.

## Paso 4: Desactivar el componente compuesto 2‑D

DataBar Expanded puede incluir opcionalmente un componente 2‑D que lleva información adicional. Para generar un código de barras **sin** este componente, establece la bandera a `false`.

```csharp
// Step 4: Disable the 2‑D composite component of the DataBar barcode
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
```

Desactivar el componente reduce la complejidad visual y produce un archivo PNG más pequeño.

## Paso 5: Guardar la imagen del código de barras sin el componente 2‑D

Elige un directorio de salida y escribe la imagen en disco. El enumerado `BarCodeImageFormat.Png` garantiza un archivo PNG sin pérdida.

```csharp
// Step 5: Save the barcode image without the 2‑D component
string outputDir = "YOUR_DIRECTORY/"; // replace with your actual path
barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png", BarCodeImageFormat.Png);
```

Después de esta llamada, `Databar2DComponentDisabled.png` contiene un código de barras DataBar Expanded limpio.

## Paso 6: Activar el componente compuesto 2‑D

Si necesitas la capa de datos adicional, vuelve a activar la bandera. La misma instancia del generador puede reutilizarse, lo que evita crear un segundo objeto.

```csharp
// Step 6: Enable the 2‑D composite component
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
```

## Paso 7: Guardar la imagen del código de barras con el componente 2‑D activado

Renderiza la segunda imagen usando la misma configuración, excepto por la bandera 2‑D.

```csharp
// Step 7: Save the barcode image with the 2‑D component enabled
barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png", BarCodeImageFormat.Png);
```

Ahora `Databar2DComponentEnabled.png` muestra el código de barras con el patrón 2‑D adicional.

## Código fuente completo

Copia el fragmento completo a continuación en `Program.cs` y ejecuta el proyecto. El programa crea ambos archivos PNG en la carpeta que especifiques.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Create a DataBar Expanded barcode generator with the desired data
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpanded, "(01)12345678901231");

            // Set the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the output directory (change to a valid path on your machine)
            string outputDir = "YOUR_DIRECTORY/";

            // ---------- First image: 2‑D component disabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png",
                                 BarCodeImageFormat.Png);

            // ---------- Second image: 2‑D component enabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png",
                                 BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

### Salida esperada

Ejecutar el programa imprime:

```
Barcode images generated successfully.
```

y crea dos archivos:

* `Databar2DComponentDisabled.png` – código de barras sin el componente 2‑D  
* `Databar2DComponentEnabled.png` – código de barras con el componente 2‑D  

Abre los PNG en cualquier visor de imágenes para verificar la diferencia visual.

## Variaciones comunes y casos límite

| Situación | Ajuste |
|-----------|--------|
| **Different symbology** | Reemplaza `EncodeTypes.DatabarExpanded` por otro valor, por ejemplo, `EncodeTypes.Code128`. |
| **Higher resolution** | Incrementa `XDimension.Pixels` a 4 o 5, o establece `Resolution` en `barcodeGenerator.Parameters.Image`. |
| **Other image formats** | Usa `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp` o `BarCodeImageFormat.Svg`. |
| **Running in a web app** | Transmite los bytes de la imagen directamente a la respuesta HTTP en lugar de guardarlos en disco. |
| **Memory management** | Envuelve el generador en un bloque `using` si apuntas a .NET Framework para asegurar que se liberen los recursos no administrados. |

## Consejos profesionales

* **Reuse the generator** – Cambiar solo la bandera 2‑D evita volver a instanciar el objeto, lo que ahorra ciclos de CPU.  
* **Validate data** – Los datos GS1 deben seguir la longitud exacta y las reglas de checksum; una entrada inválida lanza `ArgumentException`.  
* **Batch processing** – Itera sobre una colección de cadenas de datos, alterna la bandera 2‑D según sea necesario y guarda cada imagen con un nombre de archivo único.  

## Conclusión

Ahora sabes cómo generar códigos de barras en C# y crear imágenes de códigos de barras c# con control total sobre el componente compuesto 2‑D. El ejemplo muestra cómo inicializar el generador, configurar la dimensión X, alternar el componente y guardar archivos PNG. Desde aquí puedes explorar otras simbologías, incrustar las imágenes en PDFs o integrar la generación de códigos de barras en servicios ASP.NET Core.

--- 

*Próximos pasos*: intenta generar códigos QR, experimenta con diferentes resoluciones de imagen, o incrusta los PNG generados en un PDF usando Aspose.PDF. Estas extensiones se basan en la misma API `BarcodeGenerator` y mantienen tu flujo de trabajo consistente.

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}