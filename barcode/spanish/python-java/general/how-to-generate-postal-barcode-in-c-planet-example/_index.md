---
category: general
date: 2026-10-28
description: Genera código de barras postal en C# usando el formato Planet. Este ejemplo
  de código de barras Planet muestra cómo establecer el ancho del código de barras
  y guardar tanto las barras llenas como las vacías.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- set barcode width
- planet barcode example
language: es
lastmod: 2026-10-28
og_description: Genera código de barras postal en C# con un ejemplo completo de código
  de barras planetario. Aprende a establecer el ancho del código de barras, producir
  barras rellenas y crear imágenes de barras vacías.
og_image_alt: Screenshot of a generated Planet postal barcode saved as PNG
og_title: Generar código de barras postal en C# – guía paso a paso
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  headline: How to generate postal barcode in C# – planet example
  type: TechArticle
- description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  name: How to generate postal barcode in C# – planet example
  steps:
  - name: Build the project (`dotnet build`).
    text: Build the project (`dotnet build`).
  - name: Run the executable (`dotnet run`).
    text: Run the executable (`dotnet run`).
  - name: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
    text: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
  - name: Open each image; you should see a series of vertical bars representing the
      numeric string
    text: Open each image; you should see a series of vertical bars representing the
      numeric string
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Cómo generar un código de barras postal en C# – ejemplo planet
url: /es/python-java/general/how-to-generate-postal-barcode-in-c-planet-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo generar un código de barras postal en C# – ejemplo Planet

Si necesitas generar un código de barras postal en C#, esta guía te lleva paso a paso por una solución completa. Verás un ejemplo práctico de código de barras Planet que codifica una cadena numérica, te permite establecer el ancho del código de barras y guarda tanto imágenes de barras rellenas como vacías.

Crear un código de barras postal no requiere una canalización de compilación compleja. Al final de este tutorial podrás integrar la generación de códigos de barras en cualquier aplicación .NET, personalizar la X‑dimensión y elegir si las barras aparecen rellenas o vacías.

## Requisitos previos

* SDK .NET 6.0 o posterior instalado  
* Un entorno de desarrollo C# (Visual Studio, VS Code o Rider)  
* El paquete NuGet **Aspose.BarCode for .NET** (versión 23.10 o más reciente)  

Puedes agregar el paquete con el siguiente comando:

```bash
dotnet add package Aspose.BarCode
```

Los fragmentos de código a continuación asumen que has agregado `using Aspose.BarCode.Generation;` al inicio de tu archivo.

## Generar código de barras postal con simbología Planet

El primer paso es crear una instancia de `BarcodeGenerator` que utilice la simbología Planet. Planet es un formato de código de barras postal usado por varios servicios postales nacionales.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a Planet barcode generator with the data to encode
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Additional configuration will be applied here (see next steps)

        // Save the filled‑bars image
        barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // Switch to empty bars and save the second image
        barcodeGenerator.Parameters.Barcode.FilledBars = false;
        barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

**Por qué es importante:**  
`EncodeTypes.Planet` indica a la biblioteca que use el estándar de código de barras Planet, que codifica datos numéricos en una serie de barras y espacios. El constructor recibe la cadena de datos (`"123456"` en este caso) que deseas codificar.

Ejecutar el programa genera dos archivos PNG en el directorio de trabajo del ejecutable:

* **PostalPlanetFilledBars.png** – las barras se renderizan como rectángulos negros sólidos.  
* **PostalPlanetEmptyBars.png** – las barras se renderizan como rectángulos blancos con un contorno negro, útil para imprimir sobre fondos oscuros.

## Establecer el ancho del código de barras (X‑dimensión) en píxeles

El tamaño visual de un código de barras se controla mediante la X‑dimensión, que define el ancho de una barra individual. Ajustar este valor garantiza que el código de barras se lea correctamente a la resolución de impresión prevista.

```csharp
// Define the width of each bar (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

**Por qué deberías configurarlo:**  
Una X‑dimensión mayor hace que el código de barras sea más fácil de escanear con escáneres de baja resolución, mientras que un valor menor reduce el tamaño total de la imagen para impresiones de alta densidad. El ancho predeterminado es de 2 píxeles; 4 píxeles es un compromiso común para la mayoría de impresoras de escritorio.

Puedes experimentar con diferentes valores:

| Píxeles | Caso de uso típico |
|--------|---------------------|
| 2      | Etiquetas de alta densidad |
| 4      | Impresión estándar de oficina |
| 6‑8    | Señalización de gran formato |

**Consejo:** Siempre prueba el código de barras generado con tu escáner objetivo después de cambiar la X‑dimensión.

## Ejemplo de código de barras Planet – barras rellenas vs vacías

Un código de barras Planet puede renderizarse con barras sólidas (rellenas) o con contornos (vacías). La propiedad `FilledBars` alterna este comportamiento.

```csharp
// Save the barcode with the default filled bars
barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// Configure the generator to produce empty (unfilled) bars
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the barcode with empty bars
barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**Por qué podrías elegir barras vacías:**  
Las barras vacías mejoran el contraste en empaques de tono oscuro, porque el interior blanco de cada barra resalta contra un fondo oscuro. Las barras rellenas son el valor predeterminado y funcionan bien en medios de color claro.

**Salida esperada:**  

*Ambas imágenes muestran los mismos datos codificados (`123456`).* La única diferencia visual es el estilo de las barras. A continuación se muestra una descripción textual de lo que verás:

* **Imagen de barras rellenas:** Barras verticales negras sólidas sobre fondo blanco.  
* **Imagen de barras vacías:** Contornos negros formando el mismo patrón, con interiores blancos.

Puedes abrir los archivos PNG en cualquier visor de imágenes para verificar que el patrón coincide con la especificación Planet.

## Personalizar propiedades adicionales del código de barras (opcional)

Aunque los pasos principales anteriores cubren la mayoría de los escenarios, puede que desees afinar otras configuraciones:

| Propiedad | Descripción | Valor típico |
|----------|-------------|---------------|
| `Barcode.Color` | Color de primer plano de las barras | `System.Drawing.Color.Black` |
| `Barcode.BackgroundColor` | Color de relleno del fondo | `System.Drawing.Color.White` |
| `Barcode.CodeText` | Texto legible por humanos que se muestra debajo del código de barras | Igual que los datos codificados o una etiqueta personalizada |
| `Barcode.ImageFormat` | Formato de salida (PNG, JPEG, BMP, etc.) | `BarCodeImageFormat.Png` |

Ejemplo de configuración de un color de primer plano personalizado:

```csharp
barcodeGenerator.Parameters.Barcode.Color = System.Drawing.Color.DarkBlue;
```

Estos ajustes opcionales te ayudan a coincidir con la identidad corporativa o a cumplir requisitos de impresión específicos.

## Errores comunes y cómo evitarlos

| Problema | Causa | Solución |
|----------|-------|----------|
| El código de barras es ilegible | X‑dimensión demasiado pequeña para el DPI de la impresora | Incrementa `XDimension.Pixels` a 4 o más |
| El archivo de imagen está corrupto | Falta de permisos de escritura en la carpeta de destino | Usa una ruta absoluta o asegura que el directorio exista |
| Se usó la simbología incorrecta | Pasar `EncodeTypes.Code128` en lugar de `EncodeTypes.Planet` | Verifica que el argumento `EncodeTypes` coincida con el formato postal |

**Consejo profesional:** Siempre genera un código de barras de prueba y escanéalo con el hardware previsto antes de desplegar a producción.

## Ejemplo completo y ejecutable

A continuación se muestra una aplicación de consola autónoma que incorpora todos los pasos descritos. Copia el código en un nuevo proyecto de consola .NET y ejecútalo para ver los dos archivos PNG aparecer en la carpeta de salida.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a Planet barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Set the width of each bar (X‑dimension) to 4 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the barcode with the default filled bars
            generator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved filled‑bars barcode as PostalPlanetFilledBars.png");

            // 4️⃣ Configure the generator to produce empty (unfilled) bars
            generator.Parameters.Barcode.FilledBars = false;

            // 5️⃣ Save the barcode with empty bars
            generator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved empty‑bars barcode as PostalPlanetEmptyBars.png");
        }
    }
}
```

**Pasos de verificación:**  

1. Compila el proyecto (`dotnet build`).  
2. Ejecuta el ejecutable (`dotnet run`).  
3. Ubica `PostalPlanetFilledBars.png` y `PostalPlanetEmptyBars.png` en la carpeta `bin/Debug/net6.0`.  
4. Abre cada imagen; deberías ver una serie de barras verticales que representan la cadena numérica

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo crear un código de barras Planet con barras rellenas y vacías](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [Cómo establecer el ancho y generar un código de barras Planet en C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Crear código de barras postal en C# – ejemplo completo del generador](/barcode/english/python-java/general/create-postal-barcode-in-c-full-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}