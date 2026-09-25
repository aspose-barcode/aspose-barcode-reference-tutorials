---
category: general
date: 2026-08-22
description: Aprende cómo generar códigos de barras PDF417 en C# con Aspose.BarCode,
  establecer el tamaño del código de barras, ajustar las columnas y habilitar el modo
  compacto.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- set barcode size
language: es
lastmod: 2026-08-22
og_description: Genera códigos de barras PDF417 en C# con Aspose.BarCode. Esta guía
  muestra cómo establecer el tamaño del código de barras, controlar las columnas y
  habilitar el modo compacto para una imagen más pequeña.
og_image_alt: Screenshot of a generated PDF417 barcode in C# showing compact mode
og_title: Generar código de barras PDF417 en C# – establecer tamaño, columnas y modo
  compacto
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to generate PDF417 barcode in C# with Aspose.BarCode, set
    barcode size, adjust columns, and enable compact mode.
  headline: How to generate PDF417 barcode in C# and set barcode size
  type: TechArticle
tags:
- pdf417
- barcode
- csharp
title: Cómo generar un código de barras PDF417 en C# y establecer su tamaño
url: /es/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo generar código de barras PDF417 en C# y establecer el tamaño del código de barras

Si necesitas **generar código de barras PDF417** en una aplicación .NET, esta guía te lleva a través del proceso completo. Verás exactamente **cómo generar PDF417** con Aspose.BarCode, ajustar el **tamaño del código de barras**, y producir un PNG compacto que puede incrustarse en informes o aplicaciones móviles.

Crear un código de barras no requiere un editor gráfico separado. Al final de este tutorial tendrás un método C# totalmente funcional que produce una imagen PDF417 con las dimensiones exactas que necesitas, lista para el procesamiento posterior.

## Lo que aprenderás

* Instalar y referenciar la biblioteca Aspose.BarCode.
* Crear un generador de código de barras PDF417 y especificar el texto codificado.
* **Establecer el tamaño del código de barras** configurando la X‑dimensión y la cantidad de columnas.
* Habilitar el modo compacto (truncado) para reducir el símbolo.
* Guardar el resultado como un archivo PNG.
* Solucionar problemas comunes como códigos ilegibles e imágenes demasiado grandes.

### Requisitos previos

* .NET 6.0 o posterior (la API también funciona con .NET Framework 4.6+).
* Familiaridad básica con C# y Visual Studio (o cualquier IDE de C#).
* Una licencia válida de Aspose.BarCode (la evaluación gratuita sirve para pruebas).

> **Consejo profesional:** Si planeas generar muchos códigos de barras en un bucle, reutiliza una única instancia de `BarcodeGenerator` y solo cambia la propiedad `CodeText`. Esto reduce las asignaciones de memoria.

## Generar código de barras PDF417 con Aspose.BarCode

El primer paso es instanciar el `BarcodeGenerator` para la simbología PDF417. Este objeto es el punto de entrada para todas las operaciones de códigos de barras.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.Pdf417,          // Symbology
    "Sample text for PDF417");   // Data to encode
```

*Por qué es importante*: `EncodeTypes.Pdf417` indica a la biblioteca que use el estándar PDF417, que soporta grandes volúmenes de datos y corrección de errores. El constructor también acepta los datos que deseas codificar, eliminando la necesidad de una asignación separada de `CodeText` más adelante.

## Establecer el tamaño del código de barras y la cantidad de columnas

Los símbolos PDF417 consisten en filas y columnas de pequeños módulos rectangulares. Controlar el ancho del módulo (X‑dimensión) y la cantidad de columnas te permite afinar las dimensiones generales.

```csharp
// Step 2: Adjust the module size (X‑dimension) – 2 pixels per module
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Define the number of columns for the PDF417 code
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

*Explicación*:  
* **X‑dimension** (`Pixels`) determina cuán ancho es cada módulo. Valores más pequeños producen un código de barras más compacto, mientras que valores más grandes aumentan la legibilidad en escáneres de baja resolución.  
* **Columns** controla el diseño horizontal. Menos columnas hacen que el código de barras sea más alto; más columnas lo hacen más ancho. Ajusta estas dos configuraciones juntas para lograr el **tamaño del código de barras** exacto que necesitas.

## Habilitar el modo compacto para un código de barras más pequeño

PDF417 incluye un modo “compacto” (o truncado) que elimina el relleno innecesario y reduce la huella total. Esto es especialmente útil cuando dispones de espacio de pantalla limitado.

```csharp
// Step 4: Enable compact mode to truncate the barcode data
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

*¿Por qué habilitar la truncación?*  
Cuando `Truncate` es `true`, el generador omite el patrón de parada y algunos codewords de corrección de errores que no son necesarios para la mayoría de los escenarios de escaneo. La imagen resultante es aproximadamente un 15‑20 % más pequeña sin sacrificar la integridad de los datos para casos de uso típicos.

## Guardar el código de barras como una imagen PNG

Después de configurar el tamaño y el modo, escribe el código de barras en disco. PNG es sin pérdida, garantizando que los bordes de los módulos permanezcan nítidos.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save(
    "YOUR_DIRECTORY/CompactPdf417.png",
    BarCodeImageFormat.Png);
```

El archivo `CompactPdf417.png` contendrá un símbolo PDF417 nítido que coincide con las dimensiones que configuraste en los pasos anteriores.

### Resultado esperado

Abrir el PNG guardado debería mostrar un código de barras PDF417 orientado verticalmente que consiste en tres columnas, cada módulo de 2 px de ancho, y un tamaño total de aproximadamente **120 × 240 px** (ancho × alto). Escanear la imagen con cualquier lector estándar de PDF417 devuelve el texto original “Sample text for PDF417”.

## Errores comunes y cómo evitarlos

| Síntoma | Causa probable | Solución |
|---------|----------------|----------|
| El código de barras es ilegible | X‑dimension demasiado pequeña para el escáner | Incrementar `XDimension.Pixels` a 3 o 4 |
| La imagen es demasiado ancha para la UI | Se establecieron demasiadas columnas | Reducir `Pdf417.Columns` o habilitar `Truncate` |
| Excepción `ArgumentOutOfRangeException` | Conteo de columnas negativo o cero | Asegurarse de que `Columns` sea un entero positivo (mínimo 1) |
| El archivo PNG está vacío | La ruta de salida no existe o carece de permisos de escritura | Verificar que el directorio exista y la aplicación tenga derechos de escritura |

> **Consejo profesional:** Usa `barcodeGenerator.ValidateParameters()` antes de llamar a `Save()` para detectar errores de configuración temprano.

## Ejemplo completo y ejecutable

A continuación se muestra un programa de consola autónomo que incorpora todos los pasos anteriores. Cópialo en un nuevo proyecto C#, restaura el paquete NuGet de Aspose.BarCode y ejecútalo para ver el resultado.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create the generator with the data to encode
            var generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample text for PDF417");

            // Set module width (X‑dimension) – 2 px per module
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Choose a small number of columns to keep the barcode compact
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable truncation for a smaller image
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Optional: validate parameters before saving
            generator.ValidateParameters();

            // Save as PNG
            const string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

**Ejecutar el programa** produce `CompactPdf417.png` en el directorio de trabajo del ejecutable. Escanea la imagen con una aplicación móvil (p. ej., “Barcode Scanner”) para verificar que el texto codificado coincide con la cadena original.

## Próximos pasos y temas relacionados

* **Incrementar el nivel de corrección de errores** – ajustar `Pdf417.ErrorLevel` para entornos con escaneos ruidosos.  
* **Cambiar la orientación** – establecer `Pdf417.Rotate` a `RotationAngle.Rotate90` si necesitas un diseño horizontal.  
* **Incrustar el código de barras en un PDF** – combinar Aspose.PDF con Aspose.BarCode para colocar la imagen directamente en un documento.  
* **Generar otros códigos de barras 2‑D** – la misma clase `BarcodeGenerator` soporta códigos DataMatrix, QR y Aztec; solo cambia `EncodeTypes.Pdf417` por la simbología deseada.

Al dominar las técnicas para **generar código de barras PDF417**, puedes automatizar la emisión de boletos, el etiquetado de inventario y la transmisión segura de datos en una amplia gama de aplicaciones .NET.

## Conclusión

Ahora sabes cómo **generar código de barras PDF417** en C#, establecer **precisamente el tamaño del código de barras**, configurar columnas, habilitar el modo compacto y guardar el resultado como PNG. Aplica estas configuraciones para adaptarse a cualquier restricción de UI o requisito de escaneo, y extiende el enfoque a otros formatos de códigos de barras según sea necesario. ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo generar código de barras PDF417 – Codificación Compacta PDF417](/barcode/english/net/compact-pdf417-encoding/)
- [Cómo crear código de barras – PDF417 compacto con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cómo generar códigos de barras DataMatrix usando Aspose.BarCode para .NET – Guía paso a paso](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}