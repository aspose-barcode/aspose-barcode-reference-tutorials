---
category: general
date: 2026-09-26
description: Aprenda a crear códigos de barras en C# usando Aspose.BarCode. Esta guía
  paso a paso incluye un ejemplo de generador de códigos de barras y muestra cómo
  ajustar la altura de la barra.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode c#
- barcode generator example
- how to adjust bar height
- change barcode height
- generate barcode aspose
language: es
lastmod: 2026-09-26
og_description: Crear código de barras en C# con Aspose.BarCode. Sigue esta guía para
  generar un código de barras, ajustar su altura de barra y guardar imágenes PNG.
og_image_alt: Diagram illustrating how to create barcode in C# using Aspose.BarCode
og_title: Crear código de barras en C# con Aspose.BarCode – guía completa
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
    guide includes a barcode generator example and shows how to adjust bar height.
  headline: How to create barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
    guide includes a barcode generator example and shows how to adjust bar height.
  name: How to create barcode in C# with Aspose.BarCode
  steps:
  - name: Import required namespaces
    text: '```csharp using System; using Aspose.BarCode.Generation; using Aspose.BarCode;
      ```'
  - name: Initialise the barcode generator
    text: We’ll generate a **Databar Omni‑Directional** symbol that encodes a GTIN‑14
      value. The constructor takes the symbology and the raw data string.
  - name: Set common barcode parameters
    text: 'Two visual parameters are most often tweaked: the X‑dimension (the narrow
      bar width) and the overall bar height.'
  - name: Save the first image (30‑pixel height)
    text: '```csharp // Save the barcode as a 30‑pixel‑high PNG generator.Save("DatabarBarHeight30Pixels.png",
      BarCodeImageFormat.Png); ```'
  - name: Change the bar height to 60 pixels
    text: Now we demonstrate **how to adjust bar height** at runtime. The same `generator`
      instance is reused; only the `BarHeight` property changes.
  - name: Full source code
    text: 'Putting everything together yields a concise, runnable program:'
  - name: Switching to a different symbology
    text: 'If you need a QR code instead of a Databar, replace the `EncodeTypes` value:'
  - name: Using `BarHeight` in millimetres
    text: 'Aspose.BarCode also supports physical units. To set a height of 10 mm:'
  - name: Handling errors
    text: 'If the data string does not conform to the selected symbology, `BarcodeGenerator`
      throws an `ArgumentException`. Wrap the generation logic in a try‑catch block
      to provide a friendly message:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Cómo crear un código de barras en C# con Aspose.BarCode
url: /es/python-java/general/how-to-create-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear códigos de barras en C# con Aspose.BarCode  

Si necesita **crear códigos de barras en C#** proyectos rápidamente, Aspose.BarCode proporciona una API fluida que se encarga del trabajo pesado. En este tutorial verá un **ejemplo de generador de códigos de barras** completo, aprenderá **cómo ajustar la altura de la barra**, y exportará el resultado como archivos PNG.  

Ya sea que esté construyendo un sistema de caja minorista, generando etiquetas de inventario o automatizando etiquetas de envío, la capacidad de cambiar programáticamente el tamaño visual de un código de barras es esencial. Esta guía asume que tiene una comprensión básica de C# y un entorno de desarrollo como Visual Studio 2022.  

## Requisitos previos  

Antes de comenzar, asegúrese de tener:  

* .NET 6.0 SDK o posterior instalado.  
* Visual Studio 2022 (o cualquier IDE de C#).  
* Una licencia activa de Aspose.BarCode (la prueba gratuita funciona para aprendizaje).  

También necesitará agregar el paquete NuGet de Aspose.BarCode a su proyecto:

```bash
dotnet add package Aspose.BarCode
```

> **Consejo profesional:** Si planea generar muchos códigos de barras en un bucle, reutilice una única instancia de `BarcodeGenerator` y solo modifique los parámetros que cambian. Esto reduce las asignaciones de memoria y mejora el rendimiento.

## Cómo crear códigos de barras en C# con Aspose.BarCode  

Las siguientes secciones recorren cada paso del **ejemplo de generador de códigos de barras**. El código es autónomo; cópielo en una nueva aplicación de consola y ejecútelo.

### Paso 1: Importar los espacios de nombres requeridos  

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Estos espacios de nombres le dan acceso a la clase `BarcodeGenerator` y a la enumeración `EncodeTypes`.  

### Paso 2: Inicializar el generador de códigos de barras  

Generaremos un símbolo **Databar Omni‑Directional** que codifica un valor GTIN‑14. El constructor recibe la simbología y la cadena de datos sin procesar.

```csharp
// Initialise a generator for Databar Omni‑Directional
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

El valor `EncodeTypes.DatabarOmniDirectional` indica a Aspose.BarCode qué estándar de código de barras usar. La cadena de datos sigue el formato de Identificador de Aplicación GS1, que es común para códigos de barras minoristas.  

### Paso 3: Establecer los parámetros comunes del código de barras  

Dos parámetros visuales se ajustan con mayor frecuencia: la X‑dimension (el ancho de la barra estrecha) y la altura total de la barra.  

```csharp
// Set the narrow bar width to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set the initial bar height to 30 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

La **X‑dimension** controla la densidad del código de barras, mientras que **BarHeight** determina el tamaño vertical de cada barra. Ajustar **BarHeight** es exactamente lo que necesita cuando quiere **cambiar la altura del código de barras** para diferentes medios de impresión.  

### Paso 4: Guardar la primera imagen (altura de 30 píxeles)  

```csharp
// Save the barcode as a 30‑pixel‑high PNG
generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

El método `Save` escribe la imagen renderizada en disco. El nombre del archivo indica claramente la altura utilizada, lo que ayuda al comparar diferentes resultados.  

### Paso 5: Cambiar la altura de la barra a 60 píxeles  

Ahora demostramos **cómo ajustar la altura de la barra** en tiempo de ejecución. La misma instancia `generator` se reutiliza; solo cambia la propiedad `BarHeight`.  

```csharp
// Increase the bar height to 60 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the larger barcode
generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Como el generador conserva todas las demás configuraciones (simbología, datos, X‑dimension), la única diferencia visual entre los dos archivos PNG es el tamaño vertical de las barras.  

### Código fuente completo  

Unir todo produce un programa conciso y ejecutable:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for Databar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Configure visual parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // narrow bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // first height

            // 3️⃣ Save the 30‑pixel‑high image
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30‑pixel barcode.");

            // 4️⃣ Change the bar height to 60 pixels (how to adjust bar height)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 5️⃣ Save the 60‑pixel‑high image
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60‑pixel barcode.");

            // Optional: clean up resources
            generator.Dispose();
        }
    }
}
```

**Salida esperada**  

Ejecutar el programa crea dos archivos PNG en el directorio de trabajo del ejecutable:

* `DatabarBarHeight30Pixels.png` – un código de barras con altura de barra de 30 px.  
* `DatabarBarHeight60Pixels.png` – el mismo código de barras, pero cada barra es el doble de alta.

Abra las imágenes en cualquier visor; verá que el patrón general permanece idéntico mientras la dimensión vertical cambia, confirmando que la operación **cambiar la altura del código de barras** se completó con éxito.  

## Variaciones avanzadas  

### Cambiar a una simbología diferente  

Si necesita un código QR en lugar de un Databar, reemplace el valor `EncodeTypes`:  

```csharp
generator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

Todas las demás configuraciones de parámetros (X‑dimension, BarHeight) siguen aplicándose donde tengan sentido.  

### Usar `BarHeight` en milímetros  

Aspose.BarCode también admite unidades físicas. Para establecer una altura de 10 mm:  

```csharp
generator.Parameters.Barcode.BarHeight.Millimeters = 10;
```

Esto es útil cuando genera códigos de barras para diseños de impresión que requieren medidas exactas.  

### Manejo de errores  

Si la cadena de datos no se ajusta a la simbología seleccionada, `BarcodeGenerator` lanza una `ArgumentException`. Envuelva la lógica de generación en un bloque try‑catch para proporcionar un mensaje amigable:  

```csharp
try
{
    generator.Save("output.png", BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode data: {ex.Message}");
}
```

## Preguntas frecuentes respondidas  

* **¿Cambiar BarHeight afecta la escaneabilidad?**  
  El código de barras sigue siendo escaneable siempre que la X‑dimension y la zona silenciosa total cumplan con las especificaciones de la simbología. Aumentar la altura solo alarga las barras; nunca reduce el contraste.  

* **¿Puedo establecer diferentes alturas para barras individuales?**  
  No. La propiedad `BarHeight` se aplica uniformemente a todo el símbolo. Para diseños de altura variable necesitaría una rutina de renderizado personalizada fuera del alcance de Aspose.BarCode.  

* **¿Es PNG el mejor formato para imprimir?**  
  PNG conserva datos de píxel sin pérdida, lo que lo hace ideal para visualización en pantalla. Para trabajos de impresión de alta resolución, considere `BarCodeImageFormat.Tiff` o `Pdf` para mantener la información vectorial.  

## Conclusión  

Ahora sabe cómo **crear códigos de barras en C#** con Aspose.BarCode, ha visto un **ejemplo completo de generador de códigos de barras**, y entiende **cómo ajustar la altura de la barra** para cumplir con diferentes requisitos de diseño. Al reutilizar la misma instancia del generador y solo modificar `BarHeight`, puede **cambiar la altura del código de barras** de manera eficiente sin reconstruir todo el objeto.  

A partir de aquí podría explorar:

* Generar otras simbologías (`EncodeTypes.Code128`, `EncodeTypes.EAN13`).  
* Exportar a SVG o PDF para gráficos escalables.  
* Incrustar códigos de barras directamente en documentos Word o Excel usando Aspose.Words o Aspose.Cells.  

¡Feliz codificación y disfrute de la flexibilidad que Aspose.BarCode aporta a sus proyectos de códigos de barras en C#!  

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarle a dominar características adicionales de la API y explorar enfoques de implementación alternativos en sus propios proyectos.

- [Cómo generar y ajustar la altura del código de barras para Databar unidimensional usando Aspose.BarCode para .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Cómo crear un archivo PNG de código de barras con altura ajustable en C#](/barcode/english/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/)
- [Cómo generar códigos de barras en C# – Guía completa de Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}