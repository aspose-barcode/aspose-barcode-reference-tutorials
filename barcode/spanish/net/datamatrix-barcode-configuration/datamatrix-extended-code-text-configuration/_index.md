---
date: 2026-09-23
description: Aprenda cómo usar Aspose.BarCode para generar un código de barras DataMatrix
  con texto de código ampliado en .NET, ideal para aplicaciones de inventario y logística.
keywords:
- how to use aspose
- create barcode for inventory
- barcode generation .net core
- generate barcode image c#
lastmod: 2026-09-23
linktitle: Configuración del texto de código ampliado de DataMatrix
og_description: Cómo usar Aspose.BarCode para generar un código de barras DataMatrix
  con texto de código ampliado en .NET. Siga una guía rápida paso a paso para soluciones
  de inventario y logística.
og_image_alt: Screenshot of a DataMatrix barcode generated with Aspose.BarCode in
  a .NET console app
og_title: Cómo usar Aspose.BarCode para crear texto de código DataMatrix en .NET
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  headline: How to use Aspose.BarCode to create DataMatrix code text in .NET
  type: TechArticle
- description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  name: How to use Aspose.BarCode to create DataMatrix code text in .NET
  steps:
  - name: Define the output folder
    text: Specify where the generated barcode image will be saved. Replace the placeholder
      with a valid path on your machine.
  - name: Build the extended code text
    text: '`DataMatrixExtCodetextBuilder` is a helper class that assembles the extended
      code text according to the DataMatrix specification. It automatically inserts
      the required ECI (Extended Channel Interpretation) markers. This mix demonstrates
      how you can combine Unicode characters, C40 encoding, plain tex'
  - name: Generate the final codetext string
    text: After configuring all parts, retrieve the combined string that Aspose.BarCode
      will embed into the barcode.
  - name: Create the DataMatrix barcode
    text: '`BarcodeGenerator` is the core class that produces barcode images. Instantiate
      it with `EncodeTypes.DataMatrix` and the extended codetext, then set visual
      parameters such as X‑dimension, image format, and optional human‑readable text.
      The above code **creates barcode aspose .net** with the desired e'
  - name: Verify the barcode by reading it back
    text: '`BarCodeReader` validates that the generated symbol can be decoded correctly,
      which is essential for automated test pipelines and quality assurance. If everything
      is set up properly, the console will output the exact extended code text you
      built earlier.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET
    question: What library is needed?
  - answer: DataMatrix with extended code text
    question: Which barcode type?
  - answer: Yes, the API is cross‑platform
    question: Can I use .NET Core / .NET 6?
  - answer: A free trial works for development; a license is required for production
    question: Do I need a license for testing?
  - answer: About 10‑15 minutes for a basic example
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- Aspose.BarCode
- DataMatrix
- .NET barcode
- C# barcode generation
- inventory labeling
title: Cómo usar Aspose.BarCode para crear texto de código DataMatrix en .NET
url: /es/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo usar Aspose.BarCode para crear texto de código DataMatrix en .NET

Integrar códigos de barras en aplicaciones .NET modernas ya no es una tarea de nicho; es un requisito esencial para inventario, logística y soluciones de escaneo móvil. En esta guía **aprenderá cómo usar Aspose.BarCode** para configurar un código de barras DataMatrix con texto de código extendido, generar la imagen y verificarla programáticamente. Verá por qué este enfoque es ideal para crear códigos de barras para inventario y cómo encaja en proyectos .NET Core o .NET 6.

## Respuestas rápidas
- **¿Qué biblioteca se necesita?** Aspose.BarCode for .NET  
- **¿Qué tipo de código de barras?** DataMatrix con texto de código extendido  
- **¿Puedo usar .NET Core / .NET 6?** Sí, la API es multiplataforma  
- **¿Necesito una licencia para pruebas?** Una versión de prueba gratuita funciona para desarrollo; se requiere una licencia para producción  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10‑15 minutos para un ejemplo básico  

## Qué es Aspose.BarCode para .NET?
Aspose.BarCode for .NET es una biblioteca comercial que permite a los desarrolladores generar y reconocer más de 30 simbologías de códigos de barras, incluyendo DataMatrix, QR y Code 128, y producir imágenes de hasta 10,000 × 10,000 píxeles sin dependencias externas. Es compatible con .NET Framework 4.5+, .NET Core 3.1+ y .NET 5/6/7.

## Por qué usar texto de código extendido de DataMatrix?
El texto de código extendido de DataMatrix le permite incrustar varios esquemas de codificación—UTF‑8, C40, Text, X12—en un solo símbolo, permitiendo hasta **3116 codewords** (aproximadamente 155 KB de datos) en un cuadrado compacto. Esta capacidad es perfecta para etiquetado de productos multilingüe, seguimiento de dispositivos médicos y empaques inteligentes donde necesita combinar identificadores alfanuméricos con cargas binarias.

## Requisitos previos

Antes de comenzar, verifique que tiene lo siguiente:

1. **Aspose.BarCode for .NET** – descárguela desde el sitio oficial **[página de descarga de Aspose.BarCode .NET](https://releases.aspose.com/barcode/net/)**.  
2. **Un entorno de desarrollo .NET** – Visual Studio, Rider o VS Code con el SDK de .NET.  
3. **Conocimientos básicos de C#** – debe estar cómodo con clases, espacios de nombres y la directiva `using`.

## Importar espacios de nombres

Agregue los espacios de nombres requeridos al inicio de su archivo C# para que el compilador sepa dónde encontrar las clases de códigos de barras.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

Estos espacios de nombres le dan acceso tanto a la generación como al reconocimiento de códigos de barras.

## Cómo configurar el texto de código extendido de DataMatrix?

Cargue el constructor, añada los segmentos deseados y deje que Aspose.BarCode maneje los marcadores ECI automáticamente. Este párrafo de respuesta directa le indica los pasos exactos: crear un `DataMatrixExtCodetextBuilder`, agregar segmentos Unicode, C40, texto plano y modo Text, y luego obtener la cadena combinada para el generador.

### Paso 1: Definir la carpeta de salida

Especifique dónde se guardará la imagen del código de barras generado. Reemplace el marcador de posición con una ruta válida en su máquina.

```csharp
string path = "Your Directory Path";
```

### Paso 2: Construir el texto de código extendido

`DataMatrixExtCodetextBuilder` es una clase auxiliar que ensambla el texto de código extendido según la especificación DataMatrix. Inserta automáticamente los marcadores ECI (Extended Channel Interpretation) requeridos.

```csharp
DataMatrixExtCodetextBuilder codetextBuilder = new DataMatrixExtCodetextBuilder();
codetextBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
codetextBuilder.AddECICodetextWithEncodeMode(ECIEncodings.UTF8, DataMatrixEncodeMode.C40, "ABCDE");
codetextBuilder.AddPlainCodetext("test");
codetextBuilder.AddCodetextWithEncodeMode(DataMatrixEncodeMode.Text, "abcde");
```

Esta combinación demuestra cómo puede combinar caracteres Unicode, codificación C40, texto plano y modo Text en un solo símbolo DataMatrix.

### Paso 3: Generar la cadena de texto de código final

Después de configurar todas las partes, obtenga la cadena combinada que Aspose.BarCode incrustará en el código de barras.

```csharp
string codetext = codetextBuilder.GetExtendedCodetext();
```

### Paso 4: Crear el código de barras DataMatrix

`BarcodeGenerator` es la clase principal que produce imágenes de códigos de barras. Instánciela con `EncodeTypes.DataMatrix` y el texto de código extendido, luego configure parámetros visuales como la dimensión X, el formato de imagen y el texto legible opcional.

```csharp
using (var generator = new BarcodeGenerator(EncodeTypes.DataMatrix, codetext))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended Codetext";
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ExtendedCodetext;

    generator.Save($"{path}DataMatrixExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

El código anterior **crea un código de barras aspose .net** con el texto de código extendido deseado y lo guarda como un archivo PNG.

### Paso 5: Verificar el código de barras leyendo de nuevo

`BarCodeReader` valida que el símbolo generado pueda decodificarse correctamente, lo cual es esencial para pipelines de pruebas automatizadas y aseguramiento de calidad.

```csharp
using (var reader = new BarCodeReader(generator.GenerateBarCodeImage(), DecodeType.DataMatrix))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
        Console.WriteLine("DataMatrixExtendedCodetext:" + result.CodeText);
}
```

Si todo está configurado correctamente, la consola mostrará el texto de código extendido exacto que construyó anteriormente.

## Problemas comunes y solución de errores

| Problema | Razón | Solución |
|----------|-------|----------|
| Código de barras no legible | Dimensión X demasiado baja | Aumente `XDimension.Pixels` (p.ej., 4 → 6) |
| Caracteres corruptos | Codificación ECI incorrecta | Asegúrese de que `ECIEncodings.UTF8` coincida con el conjunto de caracteres |
| Archivo no guardado | Ruta inválida | Utilice una ruta absoluta o asegúrese de que la carpeta exista |
| Excepción de licencia | Periodo de prueba expirado | Aplique una licencia temporal o completa (ver FAQ) |

## Preguntas frecuentes

### Q1: ¿Qué es Aspose.BarCode para .NET?
A1: Aspose.BarCode for .NET es una biblioteca potente que permite a los desarrolladores generar y reconocer una amplia variedad de simbologías de códigos de barras, incluyendo DataMatrix, QR, Code128 y más.

### Q2: ¿Dónde puedo encontrar la documentación de Aspose.BarCode para .NET?
A2: Puede acceder a la referencia completa de la API **[referencia de API de Aspose.BarCode .NET](https://reference.aspose.com/barcode/net/)**.

### Q3: ¿Hay una versión de prueba gratuita disponible para Aspose.BarCode para .NET?
A3: Sí, una versión de prueba gratuita se puede descargar desde **[descarga de prueba gratuita de Aspose.BarCode](https://releases.aspose.com/)**.

### Q4: ¿Cómo obtener una licencia temporal para pruebas?
A4: Las licencias temporales se proporcionan para propósitos de evaluación y pueden solicitarse en **[página de solicitud de licencia temporal de Aspose](https://purchase.aspose.com/temporary-license/)**.

### Q5: ¿Dónde puedo obtener soporte o hacer preguntas sobre Aspose.BarCode para .NET?
A5: El foro oficial de Aspose.BarCode es el mejor lugar para buscar ayuda: **[foro de Aspose.BarCode](https://forum.aspose.com/c/barcode/13)**.

---

**Última actualización:** 2026-09-23  
**Probado con:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose

## Tutoriales relacionados

- [Cómo generar códigos de barras DataMatrix usando Aspose.BarCode para .NET – Guía paso a paso](/barcode/net/datamatrix-barcode-configuration/)
- [Generar un código de barras DataMatrix en modo ASCII con Aspose.BarCode para .NET (C#)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Generar código de barras Aztec con codificación de texto usando Aspose.BarCode para .NET](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}