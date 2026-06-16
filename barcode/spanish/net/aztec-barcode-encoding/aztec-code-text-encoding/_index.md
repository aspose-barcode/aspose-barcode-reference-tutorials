---
date: 2026-05-19
description: Aprenda cómo generar códigos de barras Aztec con codificación de texto
  y cómo instalar Aspose.BarCode .NET – guía paso a paso para desarrolladores .NET.
keywords:
- generate aztec barcode
- install aspose barcode .net
- aztec code encoding .net
- aspose barcode tutorial
linktitle: Codificación de texto del código Aztec
schemas:
- author: Aspose
  dateModified: '2026-05-19'
  description: Learn how to generate aztec barcode with text encoding and how to install
    aspose barcode .net – step‑by‑step guide for .NET developers.
  headline: Generate Aztec Barcode with Text Encoding using Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to generate aztec barcode with text encoding and how to install
    aspose barcode .net – step‑by‑step guide for .NET developers.
  name: Generate Aztec Barcode with Text Encoding using Aspose.BarCode for .NET
  steps:
  - name: Define Your Directory Path
    text: Choose a folder where the barcode image will be stored. Replace **Your Directory
      Path** with an absolute or relative path on your machine.
  - name: Initialize Aztec Code Generator
    text: The `BarcodeGenerator` class is the core object that creates barcodes. `BarcodeGenerator`
      **is Aspose.BarCode's primary class for barcode creation**, handling all encoding
      options internally.
  - name: Set Barcode Parameters
    text: Here we configure the visual and encoding settings. `XDimension` defines
      pixel size per module, and `CodeTextEncoding` ensures UTF‑8 handling for international
      characters.
  - name: Save the Aztec Code Image
    text: Calling `Save` writes the barcode to the file system. The format can be
      PNG, JPEG, BMP, or TIFF – PNG is used in this example for lossless quality.
  - name: Recognize the Aztec Code
    text: '`BarCodeReader` **is the class that reads and decodes barcodes** from images
      or streams. It validates that the generated Aztec code contains the expected
      text.'
  type: HowTo
- questions:
  - answer: Up to 3 832 characters for text mode, or 2 880 bytes for binary mode,
      depending on error correction level.
    question: What is the maximum amount of data an Aztec barcode can hold?
  - answer: Yes, set the `ForeColor` and `BackColor` properties on the `BarcodeGenerator`
      before saving.
    question: Can I generate colored Aztec barcodes?
  - answer: The library can generate images up to 10 000 × 10 000 pixels; larger sizes
      may increase memory usage.
    question: Is there a limit on image size?
  - answer: Absolutely – the NuGet package targets .NET Standard 2.0, making it compatible
      with .NET 5, .NET 6, and later.
    question: Does Aspose.BarCode support .NET 6?
  - answer: 'Download the trial from [here](https://releases.aspose.com/). Community
      support and discussions are available on the Aspose Barcode forum: [https://forum.aspose.com/c/barcode/13](https://forum.aspose.com/c/barcode/13).'
    question: Where can I get a free trial?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Generar código de barras Aztec con codificación de texto usando Aspose.BarCode
  para .NET
url: /es/net/aztec-barcode-encoding/aztec-code-text-encoding/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generar código de barras Aztec con codificación de texto usando Aspose.BarCode para .NET

## Introducción

¿Listo para **generar códigos de barras Aztec** con codificación de texto en un proyecto .NET? Este tutorial lo guía paso a paso, desde la instalación de la biblioteca hasta la creación y reconocimiento de un símbolo Aztec. Verá por qué Aspose.BarCode es una opción principal para los desarrolladores que necesitan una generación fiable de códigos de barras 2‑D, y obtendrá fragmentos de código prácticos que puede copiar directamente en Visual Studio. ¡Convirtamos sus datos en una imagen Aztec compacta y escaneable!

## Respuestas rápidas
- **¿Qué biblioteca crea códigos de barras Aztec?** Aspose.BarCode for .NET.
- **¿Cuántas líneas de código se necesitan?** Solo dos líneas para generar y una línea para leer.
- **¿Necesito una licencia para producción?** Sí, se requiere una licencia comercial; hay una prueba gratuita disponible.
- **¿Puedo personalizar el tamaño y la codificación?** Absolutamente: XDimension, nivel de corrección de errores y texto UTF‑8 son configurables.
- **¿Es compatible con .NET Core y .NET 6?** Sí, la biblioteca soporta .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## ¿Qué es generar código de barras Aztec?
**Generar código de barras Aztec** significa crear un símbolo de matriz bidimensional que almacena texto o datos binarios usando la simbología Aztec. El resultado es una imagen cuadrada que puede ser escaneada por dispositivos móviles o lectores dedicados sin una zona silenciosa alrededor.

## ¿Por qué usar Aspose.BarCode para .NET?
Aspose.BarCode soporta **más de 70 simbologías de códigos de barras**, incluidos códigos Aztec de hasta **151 × 151 módulos** y puede codificar **hasta 3 832 caracteres** en un solo símbolo. La biblioteca procesa documentos de cientos de páginas en modo de bajo consumo de memoria, lo que permite generar grandes lotes sin cargar archivos completos. Para una referencia detallada de la API, consulte la [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/).

## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

1. **instalar Aspose.BarCode .NET** – descargue el paquete NuGet o el instalador MSI desde el sitio oficial. Los pasos detallados de instalación están en la documentación en [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/).
2. **Visual Studio** – cualquier edición reciente (2019, 2022 o posterior) con soporte para .NET.
3. **Conocimientos básicos de C#** – debe sentirse cómodo creando un proyecto de consola o Windows Forms, pero el código está completamente comentado para principiantes.

## ¿Cómo generar código de barras Aztec con codificación de texto?
Cargue sus datos, configure el generador y guarde la imagen en dos líneas de código. Primero, cree una instancia de `BarcodeGenerator`, establezca `EncodeType` a **Aztec**, asigne el texto y llame a `Save`. Luego, use `BarCodeReader` para verificar el símbolo generado.

### Importar espacios de nombres

Las directivas `using` le dan acceso a las clases de Aspose.BarCode. Colóquelas al inicio de su archivo `.cs`:

```csharp
using System;
using System.Text;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

### Paso 1: Definir la ruta de su directorio

Elija una carpeta donde se almacenará la imagen del código de barras. Reemplace **Your Directory Path** con una ruta absoluta o relativa en su máquina.

```csharp
string path = "Your Directory Path";
```

### Paso 2: Inicializar el generador de código Aztec

La clase `BarcodeGenerator` es el objeto principal que crea códigos de barras.  
`BarcodeGenerator` **es la clase principal de Aspose.BarCode para la creación de códigos de barras**, manejando todas las opciones de codificación internamente.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Aspose常に先を行く");
```

### Paso 3: Establecer los parámetros del código de barras

Aquí configuramos los ajustes visuales y de codificación. `XDimension` define el tamaño de píxel por módulo, y `CodeTextEncoding` garantiza el manejo UTF‑8 para caracteres internacionales.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 4;
gen.Parameters.Barcode.Aztec.CodeTextEncoding = Encoding.UTF8;
```

### Paso 4: Guardar la imagen del código Aztec

Llamar a `Save` escribe el código de barras en el sistema de archivos. El formato puede ser PNG, JPEG, BMP o TIFF; en este ejemplo se usa PNG para calidad sin pérdidas.

```csharp
gen.Save($"{path}AztecCodeTextEncoding.png", BarCodeImageFormat.Png);
```

### Paso 5: Reconocer el código Aztec

`BarCodeReader` **es la clase que lee y decodifica códigos de barras** de imágenes o flujos. Valida que el código Aztec generado contenga el texto esperado.

```csharp
BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.Aztec);
foreach (BarCodeResult result in read.ReadBarCodes())
    Console.WriteLine("AztecCodeTextEncoding:" + result.GetCodeText(Encoding.UTF8));
```

## Problemas comunes y soluciones

- **Imagen no encontrada** – Verifique que la ruta del directorio termine con una barra invertida (`\`) y que la aplicación tenga permisos de escritura.
- **Texto incorrecto después de la lectura** – Asegúrese de que `CodeTextEncoding` coincida con la codificación usada durante la generación (se recomienda UTF‑8).
- **Símbolos Aztec grandes** – Aumente `XDimension` o ajuste `ErrorCorrectionLevel` para equilibrar el tamaño y la legibilidad.

## Preguntas frecuentes

**Q: ¿Cuál es la cantidad máxima de datos que puede contener un código de barras Aztec?**  
A: Hasta 3 832 caracteres en modo texto, o 2 880 bytes en modo binario, según el nivel de corrección de errores.

**Q: ¿Puedo generar códigos de barras Aztec en color?**  
A: Sí, establezca las propiedades `ForeColor` y `BackColor` en el `BarcodeGenerator` antes de guardar.

**Q: ¿Existe un límite en el tamaño de la imagen?**  
A: La biblioteca puede generar imágenes de hasta 10 000 × 10 000 píxeles; tamaños mayores pueden aumentar el uso de memoria.

**Q: ¿Aspose.BarCode soporta .NET 6?**  
A: Absolutamente: el paquete NuGet apunta a .NET Standard 2.0, lo que lo hace compatible con .NET 5, .NET 6 y versiones posteriores.

**Q: ¿Dónde puedo obtener una prueba gratuita?**  
A: Descargue la prueba desde [aquí](https://releases.aspose.com/). El soporte comunitario y las discusiones están disponibles en el foro de Aspose Barcode: [https://forum.aspose.com/c/barcode/13](https://forum.aspose.com/c/barcode/13).

---

**Última actualización:** 2026-05-19  
**Probado con:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose

## Tutoriales relacionados

- [Cómo generar código de barras Aztec con relación de aspecto personalizada usando Aspose.BarCode para .NET](/barcode/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Codificación de bytes Aztec usando generador de códigos de barras .net](/barcode/net/aztec-barcode-encoding/aztec-bytes-encoding/)
- [Dominar el modo de símbolo Aztec con Aspose.BarCode para .NET](/barcode/net/aztec-barcode-encoding/aztec-symbol-mode-example/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}