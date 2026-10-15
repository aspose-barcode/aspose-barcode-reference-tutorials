---
category: general
date: 2026-10-12
description: Cómo establecer la altura del código de barras y generar un código de
  barras DataBar en C# usando Aspose.BarCode. Sigue una guía paso a paso con código
  completo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- generate barcode c#
- how to create databar
- create databar barcode
- change barcode height
language: es
lastmod: 2026-10-12
og_description: Cómo establecer la altura del código de barras en C# y generar un
  código de barras DataBar con Aspose.BarCode. Aprende el código completo, por qué
  cada paso es importante y cómo cambiar la altura del código de barras.
og_image_alt: Screenshot showing how to set barcode height in a C# barcode generator
og_title: Cómo establecer la altura del código de barras y generar un código de barras
  DataBar en C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to set barcode height and generate a DataBar barcode in C# using
    Aspose.BarCode. Follow a step‑by‑step guide with complete code.
  headline: How to set barcode height, generate DataBar barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Cómo establecer la altura del código de barras, generar un código de barras
  DataBar en C#
url: /es/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo establecer la altura del código de barras, generar un código de barras DataBar en C#

Si necesitas **how to set barcode** dimensiones de forma programática, esta guía te muestra los pasos exactos. Aprenderás a generar un código de barras DataBar omnidireccional, ajustar su altura y guardar ambas versiones como archivos PNG.

Cambiar la altura de las barras de un código de barras es un requisito común al integrar códigos de barras en recibos, etiquetas de productos o pantallas móviles. El ejemplo a continuación utiliza la biblioteca Aspose.BarCode, que admite toda la gama de simbologías GS1 DataBar.

## Lo que lograrás

* **how to set barcode** altura para un código de barras DataBar omnidireccional  
* **generate barcode c#** código que crea dos imágenes con diferentes alturas  
* entender **how to create databar** símbolos y por qué la altura de la barra es importante  
* aplicar la lógica de **change barcode height** sin recrear el generador  

No se requieren herramientas externas más allá del paquete NuGet Aspose.BarCode y un runtime .NET 6+.

## Requisitos previos

* SDK .NET 6 o posterior instalado  
* Visual Studio 2022 (o cualquier editor C#)  
* Aspose.BarCode para .NET – instalar mediante `dotnet add package Aspose.BarCode`  

> **Consejo profesional:** Usa la licencia de prueba gratuita de Aspose si no tienes una clave comercial; la API funciona de la misma manera.

## Paso 1: Instalar el paquete Aspose.BarCode

Abre una terminal en la carpeta de tu proyecto y ejecuta:

```bash
dotnet add package Aspose.BarCode
```

El paquete agrega el espacio de nombres `Aspose.BarCode`, que contiene la clase `BarcodeGenerator` que usaremos para crear imágenes **generate barcode c#**.

## Paso 2: Crear un generador de código de barras DataBar

La primera acción concreta para los parámetros **how to set barcode** es instanciar `BarcodeGenerator` con la simbología y cadena de datos deseadas.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 2: Initialize the generator for a DataBar Omni‑directional barcode
var barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, // symbology
    "(01)12345678901231");               // GS1 data payload
```

*Por qué es importante:* `EncodeTypes.DatabarOmniDirectional` produce un DataBar compacto y omnidireccional que puede escanearse desde cualquier ángulo—ideal para etiquetas pequeñas.

## Paso 3: Establecer parámetros comunes del código de barras (incluyendo la altura inicial de la barra)

Ahora respondemos **how to set barcode** X‑dimension y la altura de la barra antes de guardar la primera imagen.

```csharp
// Step 3: Configure X‑dimension (module width) and initial bar height
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;    // 2‑pixel modules
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;   // 30‑pixel height
```

La X‑dimension controla el ancho total de cada barra; una configuración de 2 píxeles produce una imagen legible y nítida en la mayoría de pantallas. El paso **change barcode height** posterior reutilizará el mismo generador, ahorrando tiempo y memoria.

## Paso 4: Guardar la primera imagen del código de barras (altura de 30 píxeles)

```csharp
// Step 4: Save the 30‑pixel barcode image
barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
```

El archivo `DatabarHeight30.png` ahora contiene un código de barras DataBar con una altura de barra de 30 píxeles.

## Paso 5: Cambiar solo la altura de la barra a 60 píxeles

Para demostrar **change barcode height**, modificamos solo la propiedad `BarHeight`. Todas las demás configuraciones permanecen sin cambios, lo que es la forma más eficiente de producir varios tamaños a partir de un solo generador.

```csharp
// Step 5: Update the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

## Paso 6: Guardar la segunda imagen del código de barras (altura de 60 píxeles)

```csharp
// Step 6: Save the 60‑pixel barcode image
barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
```

Ahora tienes dos archivos PNG, cada uno con una altura de barra diferente pero con datos e X‑dimension idénticos.

## Ejemplo completo y ejecutable

A continuación se muestra el programa completo que puedes copiar y pegar en una nueva aplicación de consola (`dotnet new console`) y ejecutar de inmediato.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator for a DataBar Omni‑directional barcode
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");

        // Set X‑dimension and initial bar height (30 pixels)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image (30‑pixel height)
        barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight30.png");

        // Change only the bar height to 60 pixels
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image (60‑pixel height)
        barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight60.png");
    }
}
```

### Salida esperada

Ejecutar el programa genera dos archivos en el directorio de trabajo del ejecutable:

* `DatabarHeight30.png` – un código de barras DataBar con barras de 30 píxeles de altura.  
* `DatabarHeight60.png` – el mismo código de barras, pero cada barra es el doble de alta.

Ambas imágenes pueden abrirse en cualquier visor de imágenes o incrustarse directamente en PDFs, páginas HTML o etiquetas impresas.

## Por qué ajustar la altura de la barra es importante

* **Confiabilidad de escaneo:** Algunos escáneres tienen dificultades con barras muy cortas en medios de baja resolución; aumentar la altura mejora la detección.  
* **Restricciones de diseño:** Una aplicación móvil puede necesitar un código de barras compacto (30 px) mientras que un recibo impreso puede requerir uno más grande (60 px).  
* **Cumplimiento normativo:** Algunas industrias exigen una altura mínima de barra para los símbolos GS1 DataBar.

Al reutilizar la misma instancia de `BarcodeGenerator`, evitas la sobrecarga de volver a analizar la cadena de datos, lo que es especialmente beneficioso en entornos de alto rendimiento.

## Variaciones comunes y casos límite

| Situación | Ajuste recomendado |
|-----------|--------------------|
| Necesitas una X‑dimension diferente | Cambia `XDimension.Pixels` antes del primer `Save`. |
| Quieres una simbología diferente (p.ej., DataBar Stacked) | Usa `EncodeTypes.DatabarStacked` al crear `BarcodeGenerator`. |
| Debes incrustar el código de barras en un PDF | Usa `barcodeGenerator.Save(stream, BarCodeImageFormat.Png)` y agrega el stream a una biblioteca PDF. |
| Ejecutando en .NET Framework 4.6 | El mismo código funciona; solo referencia el ensamblado Aspose.BarCode apropiado. |

## Consejos profesionales para una generación de códigos de barras confiable

* **Cache the generator** cuando generas muchos códigos de barras con los mismos datos pero diferentes tamaños.  
* **

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo generar y ajustar la altura del código de barras para One-Dimensional Databar usando Aspose.BarCode para .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Cómo crear imágenes PNG de databar con C# y Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [Cómo generar códigos de barras con tamaño personalizado y guardar la imagen en C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}