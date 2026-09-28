---
date: 2026-08-02
description: Aprenda a crear códigos de barras DataMatrix, generar datamatrix y explorar
  la generación de códigos de barras high density con Aspose.BarCode para proyectos
  .NET.
keywords:
- create datamatrix barcode
- high density barcode
- generate datamatrix barcode
- barcode generation asp.net
- temporary aspose license
lastmod: 2026-08-02
linktitle: Configuración de DataMatrix ECC 200
og_description: Crear código de barras DataMatrix con Aspose.BarCode para .NET. Este
  tutorial muestra la generación de códigos de barras high density, la configuración
  de una licencia temporal de Aspose y código C# paso a paso.
og_image_alt: Guide showing C# code to create a DataMatrix barcode using Aspose.BarCode
og_title: Crear código de barras DataMatrix – guía Aspose.BarCode .NET
schemas:
- author: Aspose
  dateModified: '2026-08-02'
  description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  headline: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  name: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  steps:
  - name: Initialize the Barcode Generator
    text: '`BarcodeGenerator` is Aspose.BarCode''s core class that creates and renders
      barcodes. It accepts the symbology type and the text to encode. Replace `"Your
      Directory Path"` with the folder where you’d like the image saved.'
  - name: Set XDimension and ECC Type
    text: '`XDimension` defines the pixel size of each DataMatrix module, while `DataMatrixEcc`
      selects the error‑correction level. ECC 200 provides the highest correction
      capability for this symbology. Adjust the pixel value if you need larger or
      smaller modules; typical values are 4‑6 px for on‑screen displa'
  - name: Generate and Save the Barcode Image
    text: The `Save` method writes the barcode to a file. You can choose PNG, JPEG,
      or TIFF by passing the corresponding `BarCodeImageFormat` enum value. Switch
      `BarCodeImageFormat.Png` to `BarCodeImageFormat.Jpeg` or `BarCodeImageFormat.Tiff`
      if your workflow requires a different format.
  type: HowTo
- questions:
  - answer: Yes, the same API works in .NET Core, .NET 5, and .NET 6 projects.
    question: Can I use this code in a .NET Core console application?
  - answer: Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg` in the
      `Save` call.
    question: How do I change the output format to JPEG?
  - answer: Yes – generate the image first, then add it to a PDF using Aspose.PDF
      or any PDF library.
    question: Is it possible to embed the barcode directly into a PDF?
  - answer: DataMatrix supports UTF‑8; simply pass the Unicode string to the generator
      as shown.
    question: What if I need to encode Unicode characters?
  - answer: Absolutely – place the generation code inside a loop and change the data/value
      for each iteration.
    question: Does the library support batch generation of multiple barcodes?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- .NET barcode generation
- C# barcode tutorial
title: Cómo crear un código de barras DataMatrix (ECC 200) con Aspose.BarCode para
  .NET
url: /es/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear código de barras DataMatrix (ECC 200) con Aspose.BarCode para .NET

## Introducción

En esta guía **creará un código de barras DataMatrix** (ECC 200) usando Aspose.BarCode para .NET. Ya sea que esté construyendo un rastreador de inventario, un sistema punto de venta o automatizando flujos de trabajo de documentos, un código de barras de alta densidad puede almacenar muchos datos en un espacio diminuto. Recorreremos cada paso de configuración, explicaremos por qué cada ajuste es importante y le daremos fragmentos de C# listos para ejecutar.

## Respuestas rápidas
- **¿Qué biblioteca es la mejor para DataMatrix en .NET?** Aspose.BarCode para .NET  
- **¿Qué nivel ECC proporciona ECC 200?** Corrección de errores de alta densidad para escaneo robusto.  
- **¿Necesito una licencia para ejecutar el ejemplo?** Una licencia temporal funciona para evaluación; se requiere una licencia completa para producción.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **¿Puedo generar PNG, JPEG o TIFF?** Sí – el método `Save` admite varios formatos de imagen.

## ¿Qué es DataMatrix ECC 200?

DataMatrix ECC 200 es un código de barras bidimensional de alta densidad que puede almacenar hasta 2 335 caracteres alfanuméricos o 1 556 bytes de datos binarios en un patrón cuadrado o rectangular compacto. Utiliza corrección de errores Reed‑Solomon para recuperar módulos perdidos o dañados, lo que lo hace ideal para aplicaciones como marcado de piezas aeroespaciales, etiquetado farmacéutico y logística donde la fiabilidad es crítica.

## ¿Por qué usar la generación de códigos de barras de Aspose?

Aspose.BarCode soporta **más de 30 simbologías**, puede renderizar imágenes de hasta 10 000 × 10 000 px sin cargar todo el archivo en memoria y proporciona una salida determinista en Windows, Linux y macOS. Su API le permite controlar cada parámetro de renderizado, convirtiéndola en la opción más flexible para escenarios de **generación de códigos de barras ASP.NET**.

## Requisitos previos

1. **Entorno de desarrollo** – Visual Studio con el framework .NET apropiado instalado.  
2. **Aspose.BarCode para .NET** – Descárguelo e instálelo desde el sitio web, [aquí](https://releases.aspose.com/barcode/net/).  
3. **Licencia** – Obtenga una licencia temporal para pruebas desde [aquí](https://purchase.aspose.com/temporary-license/).  
4. **Conceptos básicos de C#** – Familiaridad con la sintaxis de C# y la estructura de proyectos.

Ahora que cubrimos los conceptos básicos, pasemos a la configuración de DataMatrix ECC 200.

## Importar espacios de nombres

El espacio de nombres `Aspose.BarCode.Generation` contiene todas las clases necesarias para la creación de códigos de barras. Impórtelo al inicio de su archivo:

```csharp
using Aspose.BarCode.Generation;
```

## Cómo crear un código de barras DataMatrix (ECC 200) paso a paso

Para producir un código de barras DataMatrix ECC 200 simplemente cargue los datos que desea codificar, configure algunos parámetros clave en el `BarcodeGenerator` y luego llame a `Save` para escribir el archivo de imagen. Este flujo de tres pasos maneja la codificación, la corrección de errores y la selección del formato de salida, permitiéndole integrar la creación de códigos de barras en cualquier aplicación .NET con un código mínimo.

### Paso 1: Inicializar el generador de códigos de barras

`BarcodeGenerator` es la clase central de Aspose.BarCode que crea y renderiza códigos de barras. Acepta el tipo de simbología y el texto a codificar.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixEcc200:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Your code goes here
}
```

Reemplace `"Your Directory Path"` con la carpeta donde desea guardar la imagen.

### Paso 2: Establecer XDimension y tipo ECC

`XDimension` define el tamaño en píxeles de cada módulo de DataMatrix, mientras que `DataMatrixEcc` selecciona el nivel de corrección de errores. ECC 200 proporciona la mayor capacidad de corrección para esta simbología.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 4;
gen.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

Ajuste el valor de píxeles si necesita módulos más grandes o más pequeños; los valores típicos son 4‑6 px para visualización en pantalla y 8‑10 px para etiquetas impresas.

### Paso 3: Generar y guardar la imagen del código de barras

El método `Save` escribe el código de barras en un archivo. Puede elegir PNG, JPEG o TIFF pasando el valor correspondiente del enumerado `BarCodeImageFormat`.

```csharp
gen.Save($"{path}DataMatrixEcc200.png", BarCodeImageFormat.Png);
```

Cambie `BarCodeImageFormat.Png` a `BarCodeImageFormat.Jpeg` o `BarCodeImageFormat.Tiff` si su flujo de trabajo requiere un formato diferente.

## Problemas comunes y solución de errores

| Síntoma | Causa probable | Solución |
|---------|----------------|----------|
| El código de barras aparece borroso | XDimension demasiado bajo | Aumente `XDimension.Pixels` a 6‑8 |
| El escaneo falla en dispositivos móviles | Nivel ECC incorrecto | Asegúrese de que `DataMatrixEcc = DataMatrixEccType.Ecc200` |
| No se crea el archivo | Cadena de ruta inválida | Use una ruta absoluta o asegúrese de que la carpeta exista |

## Preguntas frecuentes

**P: ¿Puedo usar este código en una aplicación de consola .NET Core?**  
R: Sí, la misma API funciona en .NET Core, .NET 5 y .NET 6.

**P: ¿Cómo cambio el formato de salida a JPEG?**  
R: Reemplace `BarCodeImageFormat.Png` por `BarCodeImageFormat.Jpeg` en la llamada a `Save`.

**P: ¿Es posible incrustar el código de barras directamente en un PDF?**  
R: Sí – genere primero la imagen y luego añádala a un PDF usando Aspose.PDF o cualquier biblioteca PDF.

**P: ¿Qué pasa si necesito codificar caracteres Unicode?**  
R: DataMatrix soporta UTF‑8; simplemente pase la cadena Unicode al generador como se muestra.

**P: ¿La biblioteca soporta generación por lotes de múltiples códigos de barras?**  
R: Absolutamente – coloque el código de generación dentro de un bucle y cambie los datos/valor para cada iteración.

## Conclusión

Hemos cubierto todo lo que necesita para **crear un código de barras DataMatrix** (ECC 200) con Aspose.BarCode para .NET: desde los requisitos previos y la importación de espacios de nombres hasta la configuración de la X‑dimension, la selección del nivel ECC y el guardado de la imagen en el formato que prefiera. Experimente con las muchas propiedades adicionales —como margen, color de fondo y rotación— para afinar la salida según su caso de uso específico.

Si encuentra algún desafío, la comunidad está lista para ayudar en el [foro de Aspose.BarCode](https://forum.aspose.com/c/barcode/13). ¡Feliz codificación!

---

**Última actualización:** 2026-08-02  
**Probado con:** Aspose.BarCode 24.11 para .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Cómo generar códigos de barras DataMatrix ECC 000-140 con Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-000-140-configuration/)
- [Cómo leer códigos de barras DataMatrix con Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-reading/)
- [Crear PNG de código de barras – Relación de aspecto DataMatrix – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}