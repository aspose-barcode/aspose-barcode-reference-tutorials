---
date: 2026-05-30
description: Aprenda cómo generar código de barras DataMatrix en modo Bytes y leer
  código de barras DataMatrix usando Aspose.BarCode para .NET – una guía paso a paso
  de códigos de barras.
keywords:
- generate datamatrix barcode
- read datamatrix barcode
- barcode generator settings
- step by step barcode
- create barcode asp.net
linktitle: Modo de codificación DataMatrix (Bytes)
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to generate DataMatrix barcode in Bytes mode and read DataMatrix
    barcode using Aspose.BarCode for .NET – a step‑by‑step barcode guide.
  headline: Generate DataMatrix Barcode in Bytes Mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to generate DataMatrix barcode in Bytes mode and read DataMatrix
    barcode using Aspose.BarCode for .NET – a step‑by‑step barcode guide.
  name: Generate DataMatrix Barcode in Bytes Mode with Aspose.BarCode for .NET
  steps:
  - name: Initialize the BarcodeGenerator
    text: '`BarcodeGenerator` is the main class used to generate barcode images for
      a given symbology and data.'
  - name: Set DataMatrix Encode Mode to Bytes
    text: '`DataMatrixEncodeMode.Bytes` tells the generator to treat the input as
      raw binary bytes rather than text.'
  - name: Set Display Text
    text: '`CodeText` property sets the human‑readable text displayed below the barcode
      symbol.'
  - name: Save the Barcode Image
    text: '`Save` method writes the generated barcode to an image file in the specified
      format.'
  - name: Try to Recognize
    text: '`BarCodeReader` reads barcode images and extracts the encoded data.'
  - name: Iterate and Display Results
    text: Iterate over `reader.ReadBarCodes()` to access each detected barcode and
      its `CodeText`. With these steps, you have successfully **generated a DataMatrix
      barcode** in Bytes mode and verified it using Aspose.BarCode for .NET. The library
      abstracts the low‑level encoding details, so you can focus on b
  type: HowTo
- questions:
  - answer: DataMatrix encoding mode defines how input data is transformed into the
      two‑dimensional pattern; Bytes mode stores raw binary bytes directly.
    question: What is DataMatrix encoding mode?
  - answer: You can obtain a free trial of Aspose.BarCode for .NET from [here](https://releases.aspose.com/).
    question: How can I get a free trial of Aspose.BarCode for .NET?
  - answer: The documentation for Aspose.BarCode for .NET is available [here](https://reference.aspose.com/barcode/net/).
    question: Where can I find documentation for Aspose.BarCode for .NET?
  - answer: Yes, Aspose.BarCode for .NET is suitable for commercial use. You can purchase
      a license from [here](https://purchase.aspose.com/buy).
    question: Is Aspose.BarCode for .NET suitable for commercial use?
  - answer: Yes, you can obtain a temporary license for Aspose.BarCode for .NET from
      [here](https://purchase.aspose.com/temporary-license/).
    question: Can I use a temporary license for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Generar código de barras DataMatrix en modo Bytes con Aspose.BarCode para .NET
url: /es/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generar código de barras DataMatrix en modo Bytes con Aspose.BarCode para .NET

En este tutorial aprenderá cómo **generar código de barras DataMatrix** usando el modo de codificación Bytes y luego **leer el código de barras DataMatrix** con Aspose.BarCode para .NET. Ya sea que esté construyendo un sistema de gestión de almacenes o una aplicación móvil de tickets, la guía paso a paso de códigos de barras a continuación le muestra exactamente cómo configurar los ajustes del generador de códigos de barras, producir una imagen de alta calidad y decodificarla nuevamente, todo en solo unas pocas líneas de C#.

## Respuestas rápidas
- **¿Puedo generar un código de barras DataMatrix en .NET?** Sí, use `BarcodeGenerator` con `EncodeTypes.DataMatrix` y establezca `DataMatrixEncodeMode.Bytes`.
- **¿Qué método lee el código de barras?** `BarCodeReader` lee la imagen y devuelve el texto codificado.
- **¿Necesito una licencia para producción?** Se requiere una licencia comercial; hay una prueba gratuita disponible.
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **¿Cuántos bytes puedo codificar?** Hasta 1,555 bytes en un solo símbolo DataMatrix.

## Qué es generar código de barras DataMatrix?
**Generar código de barras DataMatrix** significa crear un código de barras bidimensional, de forma cuadrada, que puede almacenar datos binarios. Aspose.BarCode renderiza el símbolo como una imagen PNG, JPG o SVG que cualquier escáner puede decodificar. Se utiliza ampliamente para el seguimiento de inventario, la gestión de documentos y la autenticación porque ofrece alta densidad de datos y capacidades de corrección de errores, lo que lo hace fiable incluso en impresiones de baja calidad.

## ¿Por qué usar el modo de codificación Bytes?
El modo Bytes le permite incrustar datos binarios sin procesar (hasta 1,555 bytes) sin convertirlos a texto, lo que es ideal para números de serie, GUIDs o cargas útiles encriptadas. Aspose.BarCode admite **más de 30 simbologías de códigos de barras** y puede procesar **documentos de varios cientos de páginas** sin cargar todo el archivo en memoria, garantizando un rendimiento rápido incluso en escenarios de alto rendimiento.

## Requisitos previos

Antes de sumergirnos en el proceso de codificación, necesitará tener los siguientes requisitos previos:

1. Aspose.BarCode for .NET: Para comenzar, debe tener la biblioteca Aspose.BarCode for .NET instalada. Puede descargarla desde [aquí](https://releases.aspose.com/barcode/net/). También puede encontrar otros productos Aspose en [aquí](https://releases.aspose.com/).
2. Your Development Environment: Asegúrese de tener un entorno de desarrollo configurado, incluido Visual Studio o cualquier otro IDE de su elección.
3. Basic Knowledge of C#: Este tutorial asume que tiene un conocimiento básico de programación en C#.

Para obtener ayuda, visite [Aspose.BarCode Support](https://forum.aspose.com/c/barcode/13).

Con estos requisitos previos en su lugar, está listo para comenzar a codificar datos en el formato DataMatrix usando el modo Bytes.

## Importar espacios de nombres

Para usar Aspose.BarCode para .NET, importe los espacios de nombres requeridos al inicio de su archivo C#:

```csharp
using System;
using System.Text;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

Ahora que el entorno está listo, recorramos los pasos exactos para **generar código de barras DataMatrix** y luego leerlo.

## Cómo generar código de barras DataMatrix en modo Bytes?

Cargue el `BarcodeGenerator`, establezca el modo de codificación a Bytes, configure el texto de visualización opcional, guarde la imagen y, finalmente, use `BarCodeReader` para verificar el resultado, todo en seis pasos concisos. Este enfoque garantiza un código de barras fiable que se adhiere al estándar ISO/IEC 16022.

### Paso 1: Inicializar el BarcodeGenerator

`BarcodeGenerator` es la clase principal utilizada para generar imágenes de códigos de barras para una simbología y datos dados.

```csharp
string path = "Your Directory Path";
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, strBld.ToString()))
{
    // Set the XDimension in Pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
```

### Paso 2: Establecer el modo de codificación DataMatrix a Bytes

`DataMatrixEncodeMode.Bytes` indica al generador que trate la entrada como bytes binarios sin procesar en lugar de texto.

```csharp
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Bytes;
```

### Paso 3: Establecer el texto de visualización

La propiedad `CodeText` establece el texto legible por humanos que se muestra debajo del símbolo del código de barras.

```csharp
    gen.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Bytes mode";
```

### Paso 4: Guardar la imagen del código de barras

El método `Save` escribe el código de barras generado en un archivo de imagen en el formato especificado.

```csharp
    gen.Save($"{path}DataMatrixEncodeModeBytes.png", BarCodeImageFormat.Png);
```

### Paso 5: Intentar reconocer

`BarCodeReader` lee imágenes de códigos de barras y extrae los datos codificados.

```csharp
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
```

### Paso 6: Iterar y mostrar resultados

Itere sobre `reader.ReadBarCodes()` para acceder a cada código de barras detectado y su `CodeText`.

```csharp
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixEncodeModeBytes:" + BitConverter.ToString(result.CodeBytes));
    }
}
```

Con estos pasos, ha generado con éxito **un código de barras DataMatrix** en modo Bytes y lo ha verificado usando Aspose.BarCode para .NET. La biblioteca abstrae los detalles de codificación de bajo nivel, por lo que puede centrarse en la lógica de negocio en lugar de en la matemática del código de barras.

## Problemas comunes y soluciones

- **Los datos codificados están truncados** – Asegúrese de que la matriz de bytes no exceda los 1,555 bytes; de lo contrario, la biblioteca cambiará automáticamente a un tamaño de símbolo mayor o lanzará una excepción.
- **La imagen aparece borrosa** – Guarde la imagen a una mayor resolución (p. ej., 300 dpi) configurando `generator.Parameters.ImageResolution` antes de llamar a `Save`.
- **El lector devuelve null** – Verifique que la ruta de la imagen sea correcta y que el archivo no esté dañado; también confirme que `BarCodeReader` se instancia con `DecodeType.DataMatrix`.

## Preguntas frecuentes

**Q: ¿Qué es el modo de codificación DataMatrix?**  
A: El modo de codificación DataMatrix define cómo los datos de entrada se transforman en el patrón bidimensional; el modo Bytes almacena directamente los bytes binarios sin procesar.

**Q: ¿Cómo puedo obtener una prueba gratuita de Aspose.BarCode para .NET?**  
A: Puede obtener una prueba gratuita de Aspose.BarCode para .NET desde [aquí](https://releases.aspose.com/).

**Q: ¿Dónde puedo encontrar la documentación de Aspose.BarCode para .NET?**  
A: La documentación de Aspose.BarCode para .NET está disponible [aquí](https://reference.aspose.com/barcode/net/).

**Q: ¿Es Aspose.BarCode para .NET adecuado para uso comercial?**  
A: Sí, Aspose.BarCode para .NET es adecuado para uso comercial. Puede comprar una licencia desde [aquí](https://purchase.aspose.com/buy).

**Q: ¿Puedo usar una licencia temporal para Aspose.BarCode para .NET?**  
A: Sí, puede obtener una licencia temporal para Aspose.BarCode para .NET desde [aquí](https://purchase.aspose.com/temporary-license/).

---

**Última actualización:** 2026-05-30  
**Probado con:** Aspose.BarCode 24.12 para .NET  
**Autor:** Aspose

## Tutoriales relacionados

- [Dominar la codificación DataMatrix en ASCII con Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Leer código de barras DataMatrix C# – Generar modo DataMatrix (Auto)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Cómo generar códigos de barras DataMatrix (ECC 200) con Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}