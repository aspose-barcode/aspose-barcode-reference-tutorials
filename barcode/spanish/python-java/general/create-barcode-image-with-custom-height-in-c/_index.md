---
category: general
date: 2026-10-28
description: Crea una imagen de código de barras en C# y aprende cómo ajustar la altura
  usando la API BarcodeGenerator. Guía paso a paso para personalizar la altura del
  código de barras y cambiar la altura de las barras.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust height
- c# barcode generator
- custom barcode height
- change barcode height
language: es
lastmod: 2026-10-28
og_description: Crea una imagen de código de barras en C# y ve al instante cómo ajustar
  la altura. Sigue este ejemplo completo para establecer una altura personalizada
  del código de barras con el BarcodeGenerator.
og_image_alt: Screenshot showing a generated barcode image with a custom height
og_title: Crear imagen de código de barras con altura personalizada en C# – guía completa
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode image in C# and learn how to adjust height using the
    BarcodeGenerator API. Step‑by‑step guide for custom barcode height and changing
    bar height.
  headline: Create barcode image with custom height in C#
  type: TechArticle
tags:
- barcode
- C#
- image generation
- GS1‑Databar
title: Crear imagen de código de barras con altura personalizada en C#
url: /es/python-java/general/create-barcode-image-with-custom-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear imagen de código de barras con altura personalizada en C#

Si necesitas **crear imagen de código de barras** y controlar sus dimensiones, esta guía te muestra exactamente cómo hacerlo. Usando la biblioteca Aspose.BarCode .NET puedes generar un código de barras GS1‑Databar Omni‑Directional, y luego **cómo ajustar la altura** para cumplir cualquier requisito de diseño.

Recorrerás un programa completo y ejecutable que demuestra un **c# barcode generator**, explica cada propiedad que configuras y muestra dos salidas diferentes: una con una altura de barra de 30 píxeles y otra con una altura de barra de 60 píxeles. Al final podrás **cambiar la altura del código de barras** programáticamente para cualquier tipo de código de barras soportado por la biblioteca.

## Requisitos previos

- .NET 6.0 SDK o posterior (el código también funciona con .NET Framework 4.6+)
- Visual Studio 2022 o cualquier editor que pueda compilar proyectos C#
- Paquete NuGet Aspose.BarCode para .NET (`Install-Package Aspose.BarCode`)
- Familiaridad básica con la sintaxis de C#

> **Consejo profesional:** Si estás usando una canalización CI, agrega el paquete NuGet a tu archivo `csproj` para que la compilación lo restaure automáticamente.

## Paso 1: Configurar el proyecto e importar espacios de nombres

Crea un nuevo proyecto de consola y agrega las declaraciones `using` requeridas. Los espacios de nombres te dan acceso a `BarcodeGenerator`, `EncodeTypes` y a los ayudantes de formato de imagen.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // The rest of the tutorial code lives here.
        }
    }
}
```

> **Por qué es importante:** Importar los espacios de nombres correctos evita errores en tiempo de compilación y hace que la API sea descubrible en IntelliSense.

## Paso 2: Inicializar el **c# barcode generator** para un código GS1‑Databar Omni‑Directional

El constructor recibe dos argumentos: el tipo de código de barras (`EncodeTypes.DatabarOmniDirectional`) y la cadena de datos. La cadena de datos debe seguir el formato de Identificador de Aplicación GS1, por ejemplo, `(01)12345678901231`.

```csharp
// Create a barcode generator for a GS1‑Databar Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional,
    "(01)12345678901231");
```

> **Explicación:** El objeto `BarcodeGenerator` es el punto de entrada para todas las configuraciones relacionadas con códigos de barras. Una vez que tienes esta instancia, puedes ajustar dimensiones, colores y el formato de salida.

## Paso 3: Definir una X‑dimension común (ancho en píxeles de la barra más estrecha)

Una X‑dimension de 2 píxeles es un buen punto de partida para la mayoría de los escenarios de visualización en pantalla.

```csharp
// Set a 2‑pixel X‑dimension (width of the smallest bar)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **¿Por qué establecer la X‑dimension?** Controla el ancho total del código de barras. Mantenerla constante asegura que cambiar la altura de la barra no distorsione el equilibrio visual.

## Paso 4: **Create barcode image** con una altura de barra de 30 píxeles

Ahora configuramos la altura de la barra, guardamos la primera imagen y luego cambiamos la altura para la segunda.

```csharp
// Configure a 30‑pixel bar height
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

// Save the first image
string output30 = "DatabarBarHeight30Pixels.png";
barcodeGenerator.Save(output30, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 30 px height to {output30}");
```

> **Resultado:** Obtienes un archivo PNG donde cada barra vertical tiene 30 píxeles de altura. La X‑dimension sigue siendo de 2 píxeles, por lo que el ancho total no cambia.

## Paso 5: **How to adjust height** – cambia la altura de la barra a 60 píxeles

Para demostrar **altura de código de barras personalizada**, simplemente asigna un nuevo valor a la misma propiedad y guarda de nuevo.

```csharp
// Change the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second image
string output60 = "DatabarBarHeight60Pixels.png";
barcodeGenerator.Save(output60, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 60 px height to {output60}");
```

> **Idea clave:** La propiedad `BarHeight` es mutable; no necesitas recrear la instancia `BarcodeGenerator`. Esto hace que sea barato generar múltiples tamaños en un bucle o proceso por lotes.

## Paso 6: Verificar la salida

Ejecuta el programa de consola (`dotnet run`). Después de la ejecución deberías ver dos archivos PNG en la carpeta de salida del proyecto:

- `DatabarBarHeight30Pixels.png` – barras cortas (30 px)
- `DatabarBarHeight60Pixels.png` – barras altas (60 px)

Ambas imágenes contienen los mismos datos codificados, pero la altura visual difiere, lo cual es útil al integrar códigos de barras en formularios, etiquetas de productos o componentes de UI con diferentes limitaciones de espacio.

![Crear imagen de código de barras con altura personalizada](barcode-example.png){.align-center width="600" alt="Crear imagen de código de barras con altura personalizada"}

> **Consejo:** Abre los archivos PNG en cualquier visor de imágenes. El código de barras más alto debería ser exactamente el doble del tamaño vertical del más corto, mientras que el espaciado horizontal permanece idéntico.

## Paso 7: Variaciones comunes y casos límite

| Situación | Configuración recomendada |
|-----------|---------------------------|
| **Impresión en una impresora de etiquetas de alta resolución** | Usa una X‑dimension mayor (p.ej., 4 px) y aumenta `BarHeight` proporcionalmente. |
| **Visualización en una pantalla de baja resolución (low‑dpi)** | Mantén `XDimension` en 1 px y `BarHeight` entre 20‑40 px para legibilidad. |
| **Generación de códigos QR o códigos de barras 2‑D** | La propiedad `BarHeight` se ignora; usa `EncodeTypes.QR` y ajusta `ImageHeight` en su lugar. |
| **Generación por lotes de múltiples alturas** | Recorre un arreglo de alturas y llama a `Save` dentro del bucle; no es necesario recrear el generador en cada iteración. |

### Manejo de alturas inválidas

La biblioteca lanza una `ArgumentOutOfRangeException` si estableces `BarHeight` a un valor no positivo. Protege contra esto con una verificación simple:

```csharp
int desiredHeight = 0; // example invalid value
if (desiredHeight <= 0)
{
    throw new ArgumentException("Bar height must be greater than zero.");
}
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = desiredHeight;
```

## Código fuente completo (listo para copiar)

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the barcode generator for GS1‑Databar Omni‑Directional
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set a common 2‑pixel X‑dimension
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = "DatabarBarHeight30Pixels.png";
            barcodeGenerator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 30 px height to {path30}");

            // 4️⃣ Second image – 60 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = "DatabarBarHeight60Pixels.png";
            barcodeGenerator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 60 px height to {path60}");
        }
    }
}
```

> **Por qué funciona:** Todas las configuraciones requeridas (`EncodeTypes`, `XDimension`, `BarHeight`) se aplican antes de cada llamada a `Save`. La misma instancia `BarcodeGenerator` se reutiliza, lo que es eficiente en memoria y fácil de leer.

## Conclusión

Ahora sabes cómo **crear imágenes de códigos de barras** en C# y cambiar **la altura del código de barras** de forma precisa usando la API `BarcodeGenerator`. Al ajustar `BarHeight.Pixels` obtienes una **altura de código de barras personalizada** sin reconstruir el generador, lo que hace que la solución sea ideal para la creación dinámica de etiquetas, renderizado de UI o pipelines de procesamiento por lotes.

A continuación, explora temas relacionados como **cómo ajustar el ancho**, **agregar texto legible por humanos**, o **exportar a SVG para uso web escalable**. El mismo patrón—establecer una propiedad, llamar a `Save`—se aplica en esos escenarios, permitiéndote ampliar este ejemplo con confianza.

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo cambiar la altura del código de barras en C# – Guía completa](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Ejemplo de generador de códigos de barras – crear códigos Planet y RM4SCC con altura personalizada](/barcode/english/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/)
- [Cómo crear un código de barras rm4scc y controlar su altura en C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-control-its-height-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}