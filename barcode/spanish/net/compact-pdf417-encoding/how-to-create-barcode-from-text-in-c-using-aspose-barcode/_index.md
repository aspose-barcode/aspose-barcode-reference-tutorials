---
category: general
date: 2026-10-28
description: Crear código de barras a partir de texto en C# con Aspose.BarCode. Aprende
  a generar una imagen de código de barras PDF417, establecer columnas, ajustar la
  dimensión X y habilitar el modo compacto.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate barcode c#
- generate pdf417 barcode
- pdf417 barcode image
language: es
lastmod: 2026-10-28
og_description: Cree un código de barras a partir de texto en C# usando Aspose.BarCode.
  Este tutorial muestra cómo generar una imagen de código de barras PDF417, personalizar
  el tamaño, las columnas y el modo compacto.
og_image_alt: Screenshot showing a compact PDF417 barcode created from text using
  C#
og_title: Crear un código de barras a partir de texto en C# – guía paso a paso
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode from text in C# with Aspose.BarCode. Learn to generate
    PDF417 barcode image, set columns, adjust X‑dimension, and enable compact mode.
  headline: How to create barcode from text in C# using Aspose.BarCode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- image generation
title: Cómo crear un código de barras a partir de texto en C# usando Aspose.BarCode
url: /es/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear código de barras a partir de texto en C# usando Aspose.BarCode

Si necesita **crear código de barras a partir de texto** en una aplicación .NET, esta guía le proporciona una solución lista para ejecutar. Verá cómo **generar códigos de barras PDF417** en imágenes, controlar el ancho del módulo, la cantidad de columnas y habilitar el modo compacto sin salir de su IDE.

El tutorial cubre todo lo necesario para **generar código de barras C#**, desde la instalación de la biblioteca hasta guardar el archivo PNG final. Al final podrá incrustar un código de barras PDF417 de alta densidad en informes, tickets o etiquetas de inventario.

## Requisitos previos

Antes de comenzar, asegúrese de tener:

* SDK .NET 6.0 o posterior instalado  
* Visual Studio 2022 (o cualquier editor que soporte .NET)  
* Acceso a Internet para descargar el paquete NuGet Aspose.BarCode para .NET  

Estos elementos son suficientes para compilar y ejecutar el ejemplo en Windows, Linux o macOS.

## Paso 1: Instalar el paquete NuGet Aspose.BarCode

La biblioteca que impulsa la generación de códigos de barras es **Aspose.BarCode for .NET**. Instálela con la CLI de .NET:

```bash
dotnet add package Aspose.BarCode
```

El paquete agrega el espacio de nombres `Aspose.BarCode`, que contiene la clase `BarcodeGenerator` utilizada a lo largo de este tutorial.

## Paso 2: Crear un proyecto de consola y agregar el código

Cree un nuevo proyecto de consola y reemplace el `Program.cs` generado con el siguiente código. El programa muestra cómo **crear código de barras a partir de texto** y guardarlo como una **imagen de código de barras PDF417**.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 2.1: Define the text to encode.
            // Unicode characters such as Å, ó, and © are supported out of the box.
            string data = "Åspóse.Barcóde©";

            // Step 2.2: Initialize the PDF417 generator with the desired text.
            // EncodeTypes.Pdf417 tells the generator which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // Step 2.3: Set the X‑dimension (module width) to 2 pixels for a denser barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 2.4: Define the number of columns in the PDF417 symbol.
            // Fewer columns produce a taller barcode; three columns keep it compact.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Step 2.5: Enable compact mode by truncating the right‑hand column.
            // Truncate reduces the overall width while preserving data integrity.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Step 2.6: Choose the output folder and file name.
            string outputPath = "CompactPdf417.png";

            // Step 2.7: Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

### Por qué cada línea es importante

* **`EncodeTypes.Pdf417`** selecciona la simbología PDF417, que es ideal para codificar grandes cantidades de datos en un formato bidimensional.  
* **`XDimension.Pixels = 2`** reduce el ancho del módulo, haciendo el código de barras más denso y más adecuado para espacios limitados.  
* **`Pdf417.Columns = 3`** controla el número de columnas de datos verticales; un recuento menor produce un código de barras más alto pero más estrecho.  
* **`Pdf417.Truncate = true`** activa el modo compacto, recortando columnas no usadas en el lado derecho. Esta es la configuración clave que convierte un PDF417 regular en una **imagen de código de barras PDF417 compacto**.  

## Paso 3: Compilar y ejecutar el proyecto

Ejecute los siguientes comandos en el directorio del proyecto:

```bash
dotnet build
dotnet run
```

Cuando el programa termine, verá un mensaje en la consola confirmando la ubicación del archivo. Abra `CompactPdf417.png` con cualquier visor de imágenes para verificar el resultado.

**Salida esperada** – un PNG de alto contraste que muestra un código de barras PDF417 compacto que codifica la cadena `Åspóse.Barcóde©`. Escanear la imagen con un lector de códigos de barras estándar devuelve el texto original, confirmando que **generar código de barras pdf417** tuvo éxito.

## Paso 4: Personalizar el código de barras para diferentes escenarios

Aunque el ejemplo usa un recuento de columnas y una X‑dimensión fijos, puede adaptar el generador a otros requisitos:

| Escenario | Ajuste |
|----------|------------|
| Mayor carga de datos | Incrementar `Pdf417.Columns` o establecer `Pdf417.Rows` manualmente |
| Mayor fiabilidad de escaneo | Aumentar `XDimension.Pixels` a 3 o 4 |
| Formato de imagen diferente | Reemplazar `BarCodeImageFormat.Png` por `Jpeg` o `Bmp` |
| Fondo transparente | Establecer `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent` |

Estas opciones le permiten **generar código de barras C#** soluciones que se adaptan a aplicaciones móviles, informes de escritorio o servicios web.

## Paso 5: Manejo de casos límite y mejores prácticas

* **Compatibilidad Unicode** – El generador codifica automáticamente caracteres Unicode, pero asegúrese de que su cadena fuente esté codificada en UTF‑8 si la lee de un archivo.  
* **Texto extenso** – PDF417 puede codificar hasta 1.850 caracteres alfanuméricos. Si supera este límite, la biblioteca lanza una excepción; divida los datos en varios códigos de barras o cambie a una simbología de mayor capacidad.  
* **Manejo de errores** – Envuelva el código de generación en un bloque `try/catch` para capturar `BarCodeException` y proporcionar un mensaje de error amigable.  
* **Rendimiento** – Generar muchos códigos de barras en un bucle se beneficia de reutilizar una única instancia de `BarcodeGenerator` y solo actualizar `CodeText` entre iteraciones.

```csharp
try
{
    generator.CodeText = nextText;
    generator.Save($"barcode_{i}.png", BarCodeImageFormat.Png);
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

## Listado completo del código fuente

A continuación se muestra el programa completo y autocontenido que puede copiar en `Program.cs`. No se requieren archivos adicionales.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            string data = "Åspóse.Barcóde©";

            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

Ejecutar este programa crea la **imagen de código de barras pdf417** mostrada en la ilustración a continuación.

![Código de barras PDF417 compacto creado a partir de texto usando C#](/images/compact-pdf417.png){.img-fluid alt="ejemplo de crear código de barras a partir de texto que muestra una imagen de código de barras PDF417 compacto"}

*Descripción de la imagen: El archivo PNG muestra un código de barras PDF417 compacto que codifica la cadena “Åspóse.Barcóde©”.*  

## Conclusión

Ahora sabe cómo **crear código de barras a partir de texto** en C# y producir una **imagen de código de barras PDF417** con dimensiones personalizadas y modo compacto. El ejemplo muestra los pasos esenciales para **generar código de barras C#**, manejar datos Unicode y ajustar los parámetros visuales para diferentes escenarios de implementación.

A continuación, explore temas relacionados como **generar código QR en C#**, **agregar código de barras a documentos PDF**, o **incrustar códigos de barras en APIs ASP.NET Core**. Cada uno de estos se basa en los mismos fundamentos de `BarcodeGenerator` cubiertos aquí.

¡Feliz codificación y disfrute integrando códigos de barras en sus soluciones .NET!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarle a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en sus propios proyectos.

- [Generar código de barras PDF417 en C# – Crear código de barras PDF417 C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/)
- [Cómo generar código de barras PDF417 con Aspose.BarCode en C#](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/)
- [Cómo crear imagen de código de barras PDF417 en C# – guía completa](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}