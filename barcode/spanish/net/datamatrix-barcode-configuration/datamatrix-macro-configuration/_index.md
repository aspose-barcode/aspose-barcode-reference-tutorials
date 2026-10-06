---
date: 2026-08-17
description: Aprenda a crear DataMatrix barcode con macro characters usando Aspose.BarCode
  para .NET y descubra cómo usar DataMatrix en sus aplicaciones.
keywords:
- create datamatrix barcode
- datamatrix barcode error correction
- aspose barcode macro
- .net barcode generation
lastmod: 2026-08-17
linktitle: Configuración de macro characters DataMatrix
og_description: Aprenda a crear DataMatrix barcode con macro characters usando Aspose.BarCode
  para .NET. Esta guía proporciona código paso a paso, opciones de personalización
  y consejos de verificación para una generación fiable de DataMatrix barcode.
og_image_alt: Guide showing creation of DataMatrix barcode with macro characters in
  .NET using Aspose.BarCode
og_title: Crear DataMatrix barcode con macro characters usando Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-17'
  description: Learn how to create DataMatrix barcode with macro characters using
    Aspose.BarCode for .NET and discover how to use DataMatrix in your applications.
  headline: How to create DataMatrix barcode with macro characters in .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode with macro characters using
    Aspose.BarCode for .NET and discover how to use DataMatrix in your applications.
  name: How to create DataMatrix barcode with macro characters in .NET
  steps:
  - name: setting up your project
    text: Create a new Console Application (or any .NET project) in Visual Studio.
      Add a reference to the Aspose.BarCode DLLs that you obtained from the download.
  - name: DataMatrix macro configuration
    text: The core of the tutorial – here we actually **create DataMatrix barcode**
      with a macro character. > **Pro tip:** Replace `"ASPOSE"` with any string you
      need to encode. The macro character (`Macro05`) tells scanners that this barcode
      is part of a macro sequence.
  - name: customize barcode parameters for error correction
    text: 'Before saving, you can tweak additional settings: - **XDimension** – controls
      the size of each module (pixel). - **Margin**, **ErrorCorrection**, and **EncodingMode**
      – all accessible via `gen.Parameters.Barcode.DataMatrix`.'
  - name: save the barcode
    text: The snippet above saves the image as `DataMatrixMacro.png` in the folder
      you specified. PNG is loss‑less, making it ideal for further processing.
  - name: recognize the barcode
    text: '`BarCodeReader` is Aspose.BarCode''s class for decoding barcodes from images.
      Using `BarCodeReader` we immediately read back the generated image to confirm
      that the macro character and data are correct. This round‑trip validation is
      especially handy during automated testing.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET is a powerful library that allows .NET developers
      to generate and recognize barcodes in various formats, including DataMatrix,
      QR, and more.
    question: What is Aspose.BarCode for .NET?
  - answer: DataMatrix barcodes are compact, highly reliable, and can store large
      amounts of data, making them ideal for manufacturing, logistics, and healthcare.
    question: Why should I use DataMatrix barcodes?
  - answer: You can find the documentation at [the Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).
    question: Where can I find the documentation for Aspose.BarCode for .NET?
  - answer: Yes, you can download a free trial from [the free trial link](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: If you have any questions or need support, you can visit the Aspose.BarCode
      for .NET forum at [the support forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- aspose.barcode
- c# barcode generation
- macro barcode
- barcode error correction
title: Cómo crear DataMatrix barcode con macro characters en .NET
url: /es/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un código de barras DataMatrix con caracteres macro en .NET

## Introducción

Generar un **código de barras DataMatrix** que incluya caracteres macro le permite empaquetar información de referencia adicional en un pequeño símbolo cuadrado. En este tutorial aprenderá cómo **crear un código de barras DataMatrix** con caracteres macro usando Aspose.BarCode para .NET, personalizar el tamaño y la corrección de errores, y verificar el resultado al instante. Al final estará listo para incrustar códigos de barras con macro en etiquetas de productos, documentos o dispositivos médicos.

## Respuestas rápidas
- **¿Cuál es la biblioteca principal?** Aspose.BarCode for .NET  
- **¿Puedo crear un código de barras DataMatrix con caracteres macro?** Sí – establezca la propiedad `MacroCharacters`.  
- **¿Necesito una licencia para producción?** Se requiere una licencia válida de Aspose para uso en producción.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **¿Está disponible una prueba gratuita?** Absolutamente – descárguela desde el sitio oficial de Aspose.

## Requisitos previos

Antes de sumergirse en la configuración macro, asegúrese de tener lo siguiente:

1. **Visual Studio** – cualquier edición reciente funcionará.  
2. **Aspose.BarCode for .NET** – descárguelo desde [the download link](https://releases.aspose.com/barcode/net/).  
3. **Conocimientos básicos de .NET** – familiaridad con C# y el ecosistema .NET.

## Importar espacios de nombres

Comenzamos importando los espacios de nombres necesarios para la generación y reconocimiento de códigos de barras.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

## ¿Qué es “generar código de barras DataMatrix” con caracteres macro?

`MacroCharacters` permite que los códigos de barras DataMatrix incluyan símbolos macro que hacen referencia a datos adicionales. Usando caracteres macro como Macro05 o Macro06, un solo código de barras puede apuntar a un conjunto de datos más grande o a una secuencia de códigos de barras relacionados, lo cual es valioso en logística, fabricación y seguimiento de documentos donde se requiere una codificación compacta de información vinculada.

## ¿Por qué usar Aspose.BarCode para generar códigos de barras DataMatrix?

Aspose.BarCode le brinda un control preciso sobre el tamaño del DataMatrix, el nivel de corrección de errores y la configuración macro, soportando más de 30 simbologías de códigos de barras y manejando archivos de hasta 10 MB sin cargar la imagen completa en memoria. Su implementación multiplataforma .NET funciona en .NET Framework, .NET Core y .NET 5/6, e incluye reconocimiento incorporado para que pueda validar el código de barras al instante.

## Guía paso a paso

### Paso 1: configurar su proyecto

Cree una nueva Aplicación de Consola (o cualquier proyecto .NET) en Visual Studio. Añada una referencia a los DLL de Aspose.BarCode que obtuvo de la descarga.

### Paso 2: configuración macro de DataMatrix

El núcleo del tutorial – aquí realmente **creamos un código de barras DataMatrix** con un carácter macro.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixMacro:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE"))
{
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    // Set the macro character to 05
    gen.Parameters.Barcode.DataMatrix.MacroCharacters = MacroCharacter.Macro05;
    gen.Save($"{path}DataMatrixMacro.png", BarCodeImageFormat.Png);

    // Try to recognize it
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixMacro:" + result.CodeText);
    }
}
```

> **Consejo profesional:** Reemplace `"ASPOSE"` con cualquier cadena que necesite codificar. El carácter macro (`Macro05`) indica a los escáneres que este código de barras forma parte de una secuencia macro.

### Paso 3: personalizar los parámetros del código de barras para la corrección de errores

Antes de guardar, puede ajustar configuraciones adicionales:

- **XDimension** – controla el tamaño de cada módulo (píxel).  
- **Margin**, **ErrorCorrection** y **EncodingMode** – todos accesibles a través de `gen.Parameters.Barcode.DataMatrix`.

### Paso 4: guardar el código de barras

El fragmento anterior guarda la imagen como `DataMatrixMacro.png` en la carpeta que especificó. PNG es sin pérdida, lo que lo hace ideal para procesamiento posterior.

### Paso 5: reconocer el código de barras

`BarCodeReader` es la clase de Aspose.BarCode para decodificar códigos de barras a partir de imágenes. Usando `BarCodeReader` leemos inmediatamente la imagen generada para confirmar que el carácter macro y los datos son correctos. Esta validación de ida y vuelta es especialmente útil durante pruebas automatizadas.

## ¿Cómo usar DataMatrix en escenarios del mundo real?

Puede aplicar códigos de barras DataMatrix con caracteres macro al etiquetado de productos, vinculando números de serie a una base de datos central, al seguimiento de documentos mediante la inserción de una referencia a un registro digital, y a etiquetas de equipos médicos que almacenan datos de pacientes o dispositivos en un símbolo pequeño y escaneable. Estos casos de uso reducen la entrada manual de datos y mejoran la trazabilidad.

## Problemas comunes y soluciones

| Problema | Razón | Solución |
|----------|-------|----------|
| Código de barras no reconocido | `XDimension` incorrecto o baja resolución de la imagen | Aumente `XDimension.Pixels` a 4‑6 y guarde como PNG o TIFF |
| Carácter macro ignorado | El lector no soporta el modo macro | Utilice un escáner/lector que soporte explícitamente macro DataMatrix (p. ej., versiones más recientes de ZXing) |
| Ruta no encontrada | Variable `path` inválida | Asegúrese de que el directorio exista o use `Path.Combine` con `Environment.CurrentDirectory` |

## Preguntas frecuentes

**Q: ¿Qué es Aspose.BarCode para .NET?**  
A: Aspose.BarCode para .NET es una biblioteca potente que permite a los desarrolladores .NET generar y reconocer códigos de barras en varios formatos, incluidos DataMatrix, QR y más.

**Q: ¿Por qué debería usar códigos de barras DataMatrix?**  
A: Los códigos de barras DataMatrix son compactos, altamente fiables y pueden almacenar grandes cantidades de datos, lo que los hace ideales para la fabricación, la logística y la atención sanitaria.

**Q: ¿Dónde puedo encontrar la documentación de Aspose.BarCode para .NET?**  
A: Puede encontrar la documentación en [the Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).

**Q: ¿Hay una prueba gratuita disponible para Aspose.BarCode para .NET?**  
A: Sí, puede descargar una prueba gratuita desde [the free trial link](https://releases.aspose.com/).

**Q: ¿Dónde puedo obtener soporte para Aspose.BarCode para .NET?**  
A: Si tiene alguna pregunta o necesita soporte, puede visitar el foro de Aspose.BarCode para .NET en [the support forum](https://forum.aspose.com/c/barcode/13).

---

**Last Updated:** 2026-08-17  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose

## Tutoriales relacionados

- [Crear código de barras aspose .net - Configuración del texto del código DataMatrix](/barcode/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Cómo generar códigos de barras DataMatrix (ECC 200) con Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Configuración de Structured Append de DataMatrix con Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}