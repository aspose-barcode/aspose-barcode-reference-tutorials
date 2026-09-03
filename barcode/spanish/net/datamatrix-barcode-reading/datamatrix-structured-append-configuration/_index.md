---
date: 2026-06-14
description: Aprenda cómo leer DataMatrix y generar códigos de barras Structured Append
  en .NET usando Aspose.BarCode, la biblioteca de códigos de barras rápida y confiable.
keywords:
- how to read datamatrix
- DataMatrix structured append
- Aspose.BarCode .NET
linktitle: Configuración de DataMatrix Structured Append
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to read datamatrix and generate structured append barcodes
    in .NET using Aspose.BarCode, the fast and reliable barcode library.
  headline: How to Read DataMatrix Append with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to read datamatrix and generate structured append barcodes
    in .NET using Aspose.BarCode, the fast and reliable barcode library.
  name: How to Read DataMatrix Append with Aspose.BarCode for .NET
  steps:
  - name: Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
    text: Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
  - name: You can also browse other Aspose products [here](https://releases.aspose.com/).
    text: You can also browse other Aspose products [here](https://releases.aspose.com/).
  - name: A .NET development environment such as Visual Studio 2022 or Visual Studio
      Code with the C# extension.
    text: A .NET development environment such as Visual Studio 2022 or Visual Studio
      Code with the C# extension.
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET.
    question: What library handles DataMatrix structured append?
  - answer: Up to 16 DataMatrix symbols.
    question: How many symbols can a single structured append sequence contain?
  - answer: A free trial works for development and testing.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes, you can decode from a byte array or stream.
    question: Can I read the barcode without an image file?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Cómo leer DataMatrix Append con Aspose.BarCode para .NET
url: /es/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configuración de Structured Append de DataMatrix con Aspose.BarCode para .NET

Si eres un desarrollador que busca **how to read datamatrix** usando structured append en tus aplicaciones .NET, Aspose.BarCode para .NET es tu solución ideal. En esta guía paso a paso, recorreremos la generación y decodificación de códigos de barras DataMatrix que se dividen en varios símbolos. Al final de este tutorial estarás cómodo creando, configurando y leyendo códigos de barras DataMatrix con structured append con Aspose.BarCode para .NET.

## Respuestas rápidas
- **¿Qué biblioteca maneja DataMatrix structured append?** Aspose.BarCode for .NET.
- **¿Cuántos símbolos puede contener una secuencia de structured append?** Hasta 16 símbolos DataMatrix.
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita funciona para desarrollo y pruebas.
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **¿Puedo leer el código de barras sin un archivo de imagen?** Sí, puedes decodificar desde un arreglo de bytes o stream.

## ¿Qué es how to read datamatrix?
**how to read datamatrix** se refiere al proceso de decodificar símbolos DataMatrix y, cuando corresponde, unir las piezas de una secuencia de structured‑append para recuperar la carga de datos original. Aspose.BarCode proporciona soporte integrado para este flujo de trabajo, gestionando el orden de los símbolos y la concatenación de datos automáticamente.

## ¿Por qué usar Aspose.BarCode para DataMatrix structured append?
Aspose.BarCode soporta **30+ simbologías de códigos de barras** y puede decodificar imágenes de hasta **10,000 × 10,000 px** en menos de **200 ms** en hardware de servidor típico. La biblioteca también ofrece **despliegue sin dependencias**, lo que significa que no necesitas DLLs nativas adicionales, y funciona en entornos .NET de Windows, Linux y macOS.

## Requisitos previos

Antes de sumergirte en el tutorial, necesitarás:

1. Aspose.BarCode for .NET Library – descárgala desde [here](https://releases.aspose.com/barcode/net/).
2. También puedes explorar otros productos de Aspose [here](https://releases.aspose.com/).
3. Un entorno de desarrollo .NET como Visual Studio 2022 o Visual Studio Code con la extensión C#.

Ahora, comencemos a crear y leer códigos de barras DataMatrix con structured append.

## Importar espacios de nombres

El primer paso es importar los espacios de nombres que exponen la API de códigos de barras.

La clase `BarCodeWriter` es el punto de entrada de Aspose.BarCode para crear códigos de barras, mientras que `BarCodeReader` se encarga de la decodificación.

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

Ahora que has importado los espacios de nombres requeridos, generemos un código de barras structured‑append.

## Cómo leer códigos de barras DataMatrix con structured append

Carga la imagen generada (o el stream) en un `BarCodeReader`, habilita la opción `ReadStructuredAppend` y llama a `ReadBarcode`. El lector devolverá automáticamente los datos combinados y expondrá detalles de la secuencia como `StructuredAppendFileId`, `StructuredAppendTotalCount` y `StructuredAppendSegmentId`. El resultado combinado se devuelve como una sola cadena, y también puedes obtener los identificadores de segmento individuales mediante la propiedad `StructuredAppendSegmentId` del lector para procesamiento personalizado.

```csharp
    using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
    {
        reader.ReadBarCodes();

        Console.WriteLine("Barcode ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodeId);
        Console.WriteLine("Barcodes count: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodesCount);
        Console.WriteLine("File ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendFileId);
    }
}
```

En este paso, usamos el lector para extraer el ID del código de barras, el recuento total y el ID de archivo, confirmando que la configuración de structured‑append se interpretó correctamente.

## Paso 1: Configurar Structured Append de DataMatrix

Para crear un código de barras DataMatrix structured append, necesitas configurar su configuración. Esto incluye definir la ruta del directorio, el ID del código de barras, la cantidad de códigos de barras y el ID del archivo.

```csharp
string path = "Your Directory Path";

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;

    // Set DataMatrix structured append mode
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodeId = 3;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodesCount = 5;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendFileId = 150;

    // Generate the barcode image
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

En este paso, hemos configurado el código de barras DataMatrix con los parámetros deseados.

## Problemas comunes y soluciones

- **Orden de segmento incorrecto:** Asegúrate de que los valores de `StructuredAppendSegmentId` sean secuenciales comenzando en 0; de lo contrario, el lector no podrá re‑ensamblar los datos correctamente.
- **Recuento total no coincidente:** `StructuredAppendTotalCount` debe ser el mismo en todos los símbolos; una discrepancia hará que el lector trate la secuencia como incompleta.
- **Calidad de la imagen:** Las imágenes de baja resolución pueden provocar fallos de decodificación. Apunta a al menos **300 dpi** al renderizar el código de barras a un bitmap.

## Preguntas frecuentes

### Q1: ¿Qué es DataMatrix structured append y por qué se utiliza?

A1: DataMatrix structured append es una función que permite dividir una gran cantidad de datos en varios códigos de barras más pequeños. Esto es particularmente útil cuando tienes espacio limitado para un solo código de barras o necesitas organizar los datos de manera eficiente. Se usa comúnmente en logística, salud y manufactura.

### Q2: ¿Puedo usar Aspose.BarCode para .NET en mi proyecto de código abierto?

A2: Sí, Aspose.BarCode para .NET ofrece una versión de prueba gratuita que puedes usar en proyectos de código abierto. Puedes encontrar la versión de prueba [here](https://releases.aspose.com/).

### Q3: ¿Existe soporte comunitario disponible para Aspose.BarCode para .NET?

A3: Sí, puedes buscar soporte comunitario e interactuar con otros usuarios en el foro de Aspose.BarCode [here](https://forum.aspose.com/c/barcode/13).

### Q4: ¿Cómo puedo obtener una licencia temporal para Aspose.BarCode para .NET?

A4: Si necesitas una licencia temporal para evaluación o pruebas, puedes obtener una [here](https://purchase.aspose.com/temporary-license/).

### Q5: ¿Aspose.BarCode para .NET soporta otros tipos de códigos de barras?

A5: Sí, Aspose.BarCode para .NET soporta una amplia gama de tipos de códigos de barras, incluidos QR codes, Code 128, EAN‑13 y muchos más. Puedes explorar la documentación completa [here](https://reference.aspose.com/barcode/net/) para ver la lista completa de tipos de códigos de barras soportados.

---

**Última actualización:** 2026-06-14  
**Probado con:** Aspose.BarCode 24.11 para .NET  
**Autor:** Aspose

## Tutoriales relacionados

- [Programación del lector DataMatrix con Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-reader-programming/)
- [Generar códigos de barras DataMatrix con Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-versions/)
- [Configuración maestra de macro DataMatrix con Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}