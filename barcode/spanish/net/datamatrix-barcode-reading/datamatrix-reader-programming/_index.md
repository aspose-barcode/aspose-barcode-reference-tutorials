---
date: 2026-08-17
description: Explore la programación del lector DataMatrix con Aspose.BarCode para
  .NET. Aprenda cómo generar y leer códigos de barras DataMatrix en sus aplicaciones
  .NET con esta guía completa.
keywords:
- create barcode image .net
- barcode reader guide
- generate datamatrix c#
- c# barcode recognition library
- barcode image handling c#
lastmod: 2026-08-17
linktitle: Programación del lector DataMatrix
og_description: Crear imagen de código de barras .NET usando Aspose.BarCode para generar
  y leer códigos DataMatrix. Esta guía muestra la configuración paso a paso, fragmentos
  de código y mejores prácticas para el manejo de imágenes de códigos de barras en
  C#.
og_image_alt: Tutorial image showing DataMatrix barcode generated with Aspose.BarCode
  in a .NET application
og_title: Crear imagen de código de barras .NET con Aspose.BarCode DataMatrix
schemas:
- author: Aspose
  dateModified: '2026-08-17'
  description: Explore DataMatrix reader programming with Aspose.BarCode for .NET.
    Learn how to generate and read DataMatrix barcodes in your .NET applications with
    this comprehensive guide.
  headline: Create barcode image .NET with Aspose.BarCode for DataMatrix
  type: TechArticle
- description: Explore DataMatrix reader programming with Aspose.BarCode for .NET.
    Learn how to generate and read DataMatrix barcodes in your .NET applications with
    this comprehensive guide.
  name: Create barcode image .NET with Aspose.BarCode for DataMatrix
  steps:
  - name: '**Visual Studio** (any recent edition) with a supported .NET runtime installed.'
    text: '**Visual Studio** (any recent edition) with a supported .NET runtime installed.'
  - name: '**Aspose.BarCode for .NET** – download it from the [download page](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – download it from the [download page](https://releases.aspose.com/barcode/net/).'
  - name: '**Basic C# knowledge** – you should be comfortable creating a console or
      desktop project.'
    text: '**Basic C# knowledge** – you should be comfortable creating a console or
      desktop project.'
  type: HowTo
- questions:
  - answer: It embeds configuration data in a DataMatrix symbol so a scanner can automatically
      set parameters like illumination or decoding mode.
    question: What is DataMatrix reader programming?
  - answer: The library offers a unified API for over 50 barcode types, high‑performance
      encoding/decoding, and full .NET Core support.
    question: Why choose Aspose.BarCode for .NET?
  - answer: A trial version is available for evaluation; a commercial license is required
      for production deployments.
    question: Can I use Aspose.BarCode for free?
  - answer: You can request a short‑term license from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license?
  - answer: You can buy a full license from the [Aspose purchase page](https://purchase.aspose.com/buy).
    question: How can I purchase a full license?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- DataMatrix
- Aspose.BarCode
- barcode generation
- C# barcode
- create barcode image
title: Crear imagen de código de barras .NET con Aspose.BarCode para DataMatrix
url: /es/net/datamatrix-barcode-reading/datamatrix-reader-programming/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear imagen de código de barras .NET con Aspose.BarCode para DataMatrix

En este tutorial aprenderá cómo **crear imágenes de código de barras .NET** aplicaciones que generan y leen códigos DataMatrix usando Aspose.BarCode. Ya sea que necesite incrustar códigos de barras en etiquetas de fabricación o automatizar el seguimiento de inventario, esta guía lo lleva paso a paso—desde la configuración del proyecto hasta la lectura del código de barras—para que pueda implementar una solución confiable rápidamente.

## Respuestas rápidas
- **¿Qué significa “reader programming”?** Codifica símbolos DataMatrix para que un escáner pueda configurarse automáticamente.  
- **¿Qué versiones de .NET son compatibles?** Aspose.BarCode funciona con .NET Framework 4.0+, .NET Core 2.0+ y .NET 5/6+.  
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita es suficiente para pruebas; se requiere una licencia comercial para producción.  
- **¿Cuántos formatos de código de barras maneja Aspose.BarCode?** Más de 50 simbologías 1D y 2D, incluyendo DataMatrix, QR y PDF417.  
- **¿Puedo leer el código de barras sin guardar un archivo de imagen?** Sí—use un `MemoryStream` para procesar la imagen completamente en memoria.

## Qué es la programación de lector de códigos de barras DataMatrix
La programación de lector de códigos de barras DataMatrix es la técnica de incrustar datos de configuración especiales dentro de un símbolo DataMatrix para que un escáner pueda ajustar automáticamente su iluminación, modo de decodificación y otros parámetros operativos cuando se detecta el símbolo. Este enfoque reduce la necesidad de configuración manual del escáner y mejora el rendimiento en entornos de alto volumen, como líneas de fabricación o sistemas de clasificación en almacenes.

## Por qué usar Aspose.BarCode para .NET?
Aspose.BarCode para .NET ofrece una API unificada que soporta más de 50 simbologías de códigos de barras, puede manejar imágenes de varios megabytes sin cargar todo el archivo en memoria, y brinda codificación y decodificación en submilisegundos en hardware de servidor típico, lo que lo convierte en una opción de alto rendimiento tanto para aplicaciones de escritorio como basadas en la nube que requieren un procesamiento fiable de códigos de barras.

## Requisitos previos

1. **Visual Studio** (cualquier edición reciente) con un runtime .NET compatible instalado.  
2. **Aspose.BarCode for .NET** – descárguelo desde la [página de descarga](https://releases.aspose.com/barcode/net/).  
3. **Conocimientos básicos de C#** – debe sentirse cómodo creando un proyecto de consola o de escritorio.

## Importar espacios de nombres

`Aspose.BarCode` proporciona las clases principales para la generación y lectura de códigos de barras, mientras que `System.Drawing` maneja la manipulación de imágenes.

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

## Qué es la clase `BarcodeGenerator`?
La clase `BarcodeGenerator` es el objeto principal de Aspose.BarCode para crear imágenes de códigos de barras en memoria; encapsula todas las configuraciones necesarias para definir la simbología, apariencia visual, opciones de codificación y formato de salida, permitiendo a los desarrolladores generar códigos de barras de alta calidad con una única llamada a método.

## Cómo definir la ruta de su directorio

Defina una carpeta donde se guardará la imagen de código de barras generada.  

```csharp
string path = "Your Directory Path";
```

Reemplace `"Your Directory Path"` con la carpeta real en su máquina.

## Cómo inicializar el generador DataMatrix

Cree una instancia de `BarcodeGenerator`, establezca la simbología a DataMatrix y habilite la programación de lector.

```csharp
System.Console.WriteLine("DataMatrixReaderProgramming:");

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    // Set a flag that indicates data is encoded for reader programming
    generator.Parameters.Barcode.DataMatrix.IsReaderProgramming = true;
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

Configuraciones clave:

- `XDimension = 4` pixels controla el tamaño del módulo.  
- `IsReaderProgramming = true` indica al escáner que el símbolo lleva datos de configuración.

## Cómo generar la imagen del código de barras

Llame al método `Save` para escribir la imagen en la ruta seleccionada.

```csharp
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

La imagen se guarda en formato PNG por defecto, pero puede elegir JPEG, BMP o TIFF.

## Cómo leer el código de barras de nuevo

Utilice `BarCodeReader` para decodificar la imagen guardada y verificar la bandera de programación de lector. La clase `BarCodeReader` es el componente central para decodificar códigos de barras; lee una imagen, detecta las simbologías compatibles y expone propiedades como `IsReaderProgrammable` que indican si el símbolo DataMatrix contiene información de programación de lector.

```csharp
    using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
    {
        reader.ReadBarCodes();
        Console.WriteLine("Is reader programming: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.IsReaderProgramming);
    }
}
```

El lector devuelve `IsReaderProgrammable` = `true` cuando la bandera se codificó correctamente.

## Problemas comunes y solución de errores

- **Imagen no encontrada** – Verifique que la ruta del directorio termine con una barra invertida (`\`) o use `Path.Combine`.  
- **El lector devuelve false** – Asegúrese de que `IsReaderProgramming` esté configurado **antes** de llamar a `Save`.  
- **Formato de imagen no compatible** – Manténgase en PNG o JPEG; BMP y TIFF pueden requerir códecs adicionales en versiones antiguas de Windows.

## Preguntas frecuentes

**Q: ¿Qué es la programación de lector DataMatrix?**  
A: Incrusta datos de configuración en un símbolo DataMatrix para que un escáner pueda establecer automáticamente parámetros como iluminación o modo de decodificación.

**Q: ¿Por qué elegir Aspose.BarCode para .NET?**  
A: La biblioteca ofrece una API unificada para más de 50 tipos de códigos de barras, codificación/decodificación de alto rendimiento y soporte completo para .NET Core.

**Q: ¿Puedo usar Aspose.BarCode de forma gratuita?**  
A: Hay una versión de prueba disponible para evaluación; se requiere una licencia comercial para implementaciones en producción.

**Q: ¿Cómo obtengo una licencia temporal?**  
A: Puede solicitar una licencia a corto plazo en la [página de licencia temporal](https://purchase.aspose.com/temporary-license/).

**Q: ¿Cómo puedo comprar una licencia completa?**  
A: Puede adquirir una licencia completa en la [página de compra de Aspose](https://purchase.aspose.com/buy).

**Q: ¿La biblioteca es compatible con las últimas versiones de .NET?**  
A: Sí, es compatible con .NET Framework 4.0+, .NET Core 2.0+ y .NET 5/6+.

## Conclusión

Al seguir esta guía ahora sabe cómo **crear imágenes de código de barras .NET** soluciones que generan símbolos DataMatrix y los leen con Aspose.BarCode. Integre estos fragmentos en cualquier proyecto C#—de escritorio, servicio o web—para automatizar flujos de trabajo de códigos de barras en entornos de fabricación, logística o salud.

Para material de referencia más profundo, explore la [documentación oficial](https://reference.aspose.com/barcode/net/) o únase a la comunidad en el [foro de soporte de Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**Última actualización:** 2026-08-17  
**Probado con:** Aspose.BarCode 24.11 para .NET  
**Autor:** Aspose

## Tutoriales relacionados

- [Cómo leer códigos de barras DataMatrix con Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-reading/)
- [Cómo generar códigos de barras DataMatrix (ECC 200) con Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Crear PNG de código de barras – Relación de aspecto DataMatrix – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}