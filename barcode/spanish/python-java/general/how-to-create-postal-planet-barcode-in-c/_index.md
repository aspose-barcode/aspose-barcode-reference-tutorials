---
category: general
date: 2026-11-23
description: Crear código de barras planetario postal en C# con Aspose.BarCode. Aprende
  cómo generar el código de barras planetario, establecer la dimensión X y guardar
  barras llenas o vacías.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal planet barcode
- how to generate planet barcode
- Aspose.BarCode C#
- postal barcode example
- Planet barcode settings
language: es
lastmod: 2026-11-23
og_description: Crea un código de barras planetario postal en C# y aprende a generar
  códigos de barras planetarios con Aspose.BarCode. Sigue el ejemplo completo para
  producir barras llenas y vacías.
og_image_alt: Example of a created postal planet barcode with filled bars
og_title: Cómo crear un código de barras Postal Planet en C# – guía paso a paso
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  headline: How to create postal planet barcode in C#
  type: TechArticle
- description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  name: How to create postal planet barcode in C#
  steps:
  - name: Changing the image format
    text: If your downstream system prefers JPEG, replace `BarCodeImageFormat.Png`
      with `BarCodeImageFormat.Jpeg`. JPEG introduces compression artifacts, so use
      it only when file size is a critical constraint.
  - name: Scaling the barcode
    text: 'You can enlarge the barcode while preserving the module width by adjusting
      the `Resolution` property:'
  - name: Using a custom background color
    text: 'The background can be set with:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Cómo crear un código de barras Postal Planet en C#
url: /es/python-java/general/how-to-create-postal-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un código de barras postal Planet en C#

Si necesitas **crear un código de barras postal Planet** en una aplicación .NET, esta guía te muestra exactamente **cómo generar un código de barras Planet** usando la biblioteca Aspose.BarCode. Verás cómo configurar la dimensión X, alternar entre barras rellenas y vacías, y guardar las imágenes en formato PNG.

Generar un código de barras Planet es habitual para los servicios postales que requieren símbolos de alta densidad y legibles por máquina. Al final de este tutorial tendrás dos archivos PNG—uno con barras sólidas y otro con barras huecas—listos para integrarse en cualquier flujo de trabajo de envío.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* .NET 6.0 SDK o posterior instalado.
* Visual Studio 2022 (o cualquier editor de C#) configurado para desarrollo .NET.
* Una licencia activa de NuGet para **Aspose.BarCode for .NET**. Instala el paquete con:

```bash
dotnet add package Aspose.BarCode
```

No se requieren servicios externos adicionales; la biblioteca realiza todo el codificado localmente.

## Paso 1 – crear código de barras postal Planet

La primera operación es instanciar un `BarcodeGenerator` para la simbología **Planet** y proporcionar los datos a codificar. La cadena de datos debe ser numérica y de hasta 12 dígitos según la especificación postal.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

Crear el generador asigna todas las estructuras internas necesarias para el renderizado. El valor de enumeración `EncodeTypes.Planet` selecciona el algoritmo de codificación correcto para el formato postal.

## Paso 2 – establecer la dimensión X para mejor visibilidad

La dimensión X define el ancho de un solo módulo (el elemento de barra más pequeño). Un valor de 4 píxeles proporciona una representación visual clara sin ampliar la imagen completa.

```csharp
// Step 2: Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
```

Ajustar la dimensión X es esencial cuando el código de barras se imprimirá en medios de baja resolución. La misma configuración se reutilizará para la versión de barras vacías para mantener ambas imágenes consistentes.

## Paso 3 – guardar el código de barras con barras rellenas

Por defecto el generador renderiza **barras rellenas** (módulos negros sólidos). Guardar la imagen es una única llamada a método que escribe el archivo PNG en disco.

```csharp
// Step 3: Save the barcode with the default setting (filled bars)
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

Reemplaza `YOUR_DIRECTORY` con la ruta real donde deseas que se guarden los archivos de salida. La enumeración `BarCodeImageFormat.Png` garantiza una compresión sin pérdida, lo cual es ideal para el procesamiento posterior.

## Paso 4 – crear otro generador de código de barras Planet para barras vacías

Para producir una versión que use **barras vacías** (módulos blancos sobre fondo negro), necesitas una segunda instancia de `BarcodeGenerator`. Reutilizar la misma cadena de datos asegura que ambas imágenes representen el mismo código postal.

```csharp
// Step 4: Create another Planet barcode generator for the same data
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

Crear un generador separado aísla la propiedad `FilledBars`, permitiéndote cambiar el estilo visual sin afectar la primera imagen.

## Paso 5 – configurar el generador para renderizar barras vacías

El indicador `FilledBars` invierte el modo de renderizado. Establecerlo en `false` indica a la biblioteca que dibuje las barras como vacías (transparentes) mientras mantiene el fondo sólido.

```csharp
// Step 5: Apply the same X‑dimension and configure empty bars
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
planetEmpty.Parameters.Barcode.FilledBars = false;
```

Mantener la dimensión X idéntica a la versión rellena garantiza que ambos archivos PNG tengan las mismas dimensiones, lo que simplifica los cálculos de diseño en plantillas de impresión.

## Paso 6 – guardar el código de barras que renderiza barras vacías

Finalmente, escribe la imagen de barras vacías en disco. Se usa el mismo formato PNG, pero podrías cambiar a JPEG o BMP modificando el valor de `BarCodeImageFormat`.

```csharp
// Step 6: Save the barcode that renders empty bars
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

En este punto tienes dos archivos:

* `PostalPlanetFilledBars.png` – barras negras sólidas.
* `PostalPlanetEmptyBars.png` – barras huecas sobre fondo negro.

Ambos cumplen con la especificación postal para la simbología Planet.

## Código fuente completo

Unir todos los pasos produce una aplicación de consola compacta que puedes ejecutar directamente.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a Planet barcode with filled bars
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
            planetFilled.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

            // Create a Planet barcode with empty bars
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
            planetEmpty.Parameters.Barcode.FilledBars = false;
            planetEmpty.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcodes generated successfully.");
        }
    }
}
```

Compila y ejecuta el programa:

```bash
dotnet run
```

La consola muestra *Barcodes generated successfully.* y los dos archivos PNG aparecen en la carpeta del proyecto.

## Resultado esperado

A continuación se muestra una representación visual de la imagen con barras rellenas. La contraparte de barras vacías es idéntica, salvo que las barras son transparentes.

![Ejemplo de un código de barras postal Planet creado con barras rellenas](postal-planet-filled.png)

*Texto alternativo de la imagen:* **Ejemplo de un código de barras postal Planet creado con barras rellenas** (contiene la palabra clave principal).

Ambas imágenes son de 150 × 150 píxeles por defecto, pero puedes controlar el tamaño total con los parámetros `ImageWidth` y `ImageHeight` si se requiere una resolución diferente.

## Variaciones opcionales

### Cambiar el formato de imagen

Si tu sistema posterior prefiere JPEG, reemplaza `BarCodeImageFormat.Png` por `BarCodeImageFormat.Jpeg`. JPEG introduce artefactos de compresión, así que úsalo solo cuando el tamaño del archivo sea una restricción crítica.

### Escalar el código de barras

Puedes ampliar el código de barras manteniendo el ancho del módulo ajustando la propiedad `Resolution`:

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI
```

Valores de DPI más altos mejoran la calidad de impresión en impresoras láser.

### Usar un color de fondo personalizado

El fondo puede establecerse con:

```csharp
planetEmpty.Parameters.Barcode.BackColor = System.Drawing.Color.LightGray;
```

Esto es útil para pruebas visuales, pero debería evitarse en etiquetas postales de producción, que requieren un fondo blanco.

## Preguntas frecuentes

**¿Esto funciona con .NET Core?**  
Sí. La biblioteca Aspose.BarCode apunta a .NET Standard 2.0, que es compatible con .NET 5, .NET 6 y .NET Core 3.1.

**¿Qué pasa si la cadena de datos contiene caracteres no numéricos?**  
Los códigos de barras Planet solo aceptan entrada numérica. Proporcionar letras o símbolos genera una `BarcodeException`. Valida la entrada antes de crear el generador.

**¿Puedo generar un código de barras en memoria sin escribirlo en disco?**  
Utiliza el método `GenerateBarCodeImage` para obtener un objeto `System.Drawing.Image`, y luego envíalo directamente a una respuesta o base de datos.

## Conclusión

Ahora sabes cómo **crear un código de barras postal Planet** en C# y entiendes **cómo generar un código de barras Planet** con estilos de barras rellenas y vacías. El tutorial cubrió todo el flujo de trabajo—desde inicializar el generador, configurar la dimensión X, alternar el indicador `FilledBars`, hasta guardar archivos PNG. Experimenta con formatos de imagen, configuraciones de DPI y colores de fondo para adaptar el código de barras a tu sistema de envío específico.

Para el siguiente paso, explora otras simbologías postales como **POSTNET** o **Intelligent Mail** usando la misma API de Aspose.BarCode. Ajustar parámetros como `EncodeTypes.Postnet` sigue el mismo patrón demostrado aquí, permitiéndote crear una suite completa de generación de códigos de barras en una única base de código.

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Create empty planet barcode, generate postal barcode in C#](/barcode/english/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/)
- [How to set width and generate a Planet barcode in C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Generate Postal Barcode in C# – Complete Guide with Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}