---
date: 2026-05-30
description: Aprenda cómo crear un PNG de código de barras con una relación de aspecto
  DataMatrix personalizada usando Aspose.BarCode para .NET. Guía paso a paso para
  la generación de códigos de barras y la personalización del tamaño.
keywords:
- create barcode png
- generate datamatrix barcode
- asp.net barcode generation
- barcode generation visual studio
linktitle: Personalización de la relación de aspecto DataMatrix
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  headline: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  name: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  steps:
  - name: Set Up Your Project
    text: Create a new console or Windows Forms project in Visual Studio and add a
      reference to the Aspose.BarCode DLL.
  - name: Initialize a Barcode Generator
    text: 'Instantiate it with the DataMatrix symbology and the data you want to encode:
      `BarcodeGenerator` creates a barcode image from the specified symbology and
      data. > This line creates a generator ready to produce a DataMatrix barcode
      that contains the sample text.'
  - name: Customize Aspect Ratio and Save PNG Files
    text: 'Now you can change the **aspect ratio** and save each version as a PNG
      image: `AspectRatio` sets the width‑to‑height proportion of the DataMatrix modules.
      `Save` writes the generated barcode image to a file in the chosen format. -
      The first call creates a square‑proportioned barcode (`AspectRatio = '
  type: HowTo
- questions:
  - answer: Yes, many 2‑D barcodes (e.g., QR, PDF417) support aspect‑ratio adjustments
      through their specific parameter objects.
    question: Can I customize the aspect ratio of other barcode types using Aspose.BarCode
      for .NET?
  - answer: Yes, you can access a free trial of Aspose.BarCode for .NET [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: You can purchase a license on the Aspose website [here](https://purchase.aspose.com/buy).
    question: Where can I purchase a license for Aspose.BarCode for .NET?
  - answer: Yes, it works with .NET Framework 4.x, .NET Core 3.1+, and the latest
      .NET releases.
    question: Is Aspose.BarCode for .NET compatible with different .NET Framework
      versions?
  - answer: Absolutely – PNG, JPEG, BMP, GIF, TIFF, SVG, and PDF are all supported
      out of the box.
    question: Can I generate barcodes in different formats with Aspose.BarCode for
      .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Crear PNG de código de barras – Relación de aspecto DataMatrix – Aspose.BarCode
url: /es/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear PNG de código de barras – Relación de aspecto DataMatrix – Aspose.BarCode

Generar un **barcode PNG** con una relación de aspecto DataMatrix personalizada es un requisito común cuando necesitas **crear archivos barcode PNG** que se ajusten a restricciones de diseño específicas. En este tutorial recorreremos los pasos exactos para **crear archivos barcode PNG** usando Aspose.BarCode para .NET, explicaremos por qué podrías querer ajustar la relación de aspecto y te mostraremos cómo afinar la salida para tu aplicación.

## Respuestas rápidas
- **¿Qué controla la “relación de aspecto”?** Define la proporción ancho‑alto de los módulos DataMatrix.  
- **¿Puedo generar PNG, JPEG o SVG?** Sí – el método `Save` admite PNG, JPEG, BMP, GIF, TIFF, SVG y PDF.  
- **¿Necesito una licencia para esta función?** Una prueba gratuita funciona para desarrollo; se requiere una licencia completa para producción.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.x, .NET Core 3.1+, .NET 5/6/7.  
- **¿Cuántos valores de relación de aspecto son válidos?** Cualquier número flotante positivo; los valores típicos son 0.5 – 2.0.

## Qué es un código de barras DataMatrix y por qué ajustar su relación de aspecto?
Un código de barras DataMatrix es un código matricial bidimensional que almacena grandes cantidades de datos en un cuadrado compacto. Ajustar la **relación de aspecto** te permite estirar o comprimir los módulos horizontalmente, lo que es útil cuando necesitas encajar el código de barras en columnas estrechas o etiquetas anchas sin sacrificar la fiabilidad del escaneo.

## Por qué usar Aspose.BarCode para crear barcode PNG?
Aspose.BarCode admite **7 formatos de imagen** — PNG, JPEG, BMP, GIF, TIFF, SVG y PDF — y puede procesar **más de 50 formatos de entrada y salida** en memoria, manejando documentos de cientos de páginas sin cargar el archivo completo. La biblioteca ofrece una API fluida que te permite generar un código de barras DataMatrix en una sola línea de código, garantizando una renderización pixel‑perfecta y plena compatibilidad con .NET.

## Requisitos previos

Antes de comenzar a personalizar las relaciones de aspecto DataMatrix, asegúrate de tener los siguientes requisitos preparados:

1. **Visual Studio** – cualquier versión reciente servirá.  
2. **Aspose.BarCode for .NET** – descárgalo [aquí](https://releases.aspose.com/barcode/net/).  
3. También puedes explorar otras versiones de productos Aspose [aquí](https://releases.aspose.com/).  
4. **.NET Framework / .NET Core** – tu proyecto debe dirigirse a una versión compatible.

## Importar espacios de nombres

Primero, necesitas importar el espacio de nombres necesario en tu proyecto C#:

`using Aspose.BarCode.Generation;` importa el espacio de nombres que contiene las clases de generación de códigos de barras.  

```csharp
using Aspose.BarCode.Generation;
```

> **Consejo profesional:** Mantén esta declaración `using` al inicio de tu archivo para que la clase `BarcodeGenerator` esté siempre disponible.

## Cómo crear barcode PNG con relación de aspecto personalizada?

Carga el `BarcodeGenerator`, establece el tipo DataMatrix, ajusta la propiedad `AspectRatio` y llama a `Save`. Este patrón de una sola línea crea un barcode PNG que respeta la relación que especificas, y la biblioteca maneja automáticamente el escalado de módulos y las zonas silenciosas.

`BarcodeGenerator` crea una imagen de código de barras a partir de la simbología y los datos especificados.  

### Paso 1: Configura tu proyecto
Crea un nuevo proyecto de consola o Windows Forms en Visual Studio y agrega una referencia al DLL de Aspose.BarCode.

### Paso 2: Inicializar un generador de códigos de barras
Instáncialo con la simbología DataMatrix y los datos que deseas codificar:

`BarcodeGenerator` crea una imagen de código de barras a partir de la simbología y los datos especificados.  

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> Esta línea crea un generador listo para producir un código de barras DataMatrix que contiene el texto de ejemplo.

### Paso 3: Personalizar la relación de aspecto y guardar archivos PNG
Ahora puedes cambiar la **relación de aspecto** y guardar cada versión como una imagen PNG:

`AspectRatio` establece la proporción ancho‑alto de los módulos DataMatrix.  
`Save` escribe la imagen de código de barras generada en un archivo en el formato elegido.  

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- La primera llamada crea un código de barras con proporción cuadrada (`AspectRatio = 1`).  
- La segunda llamada comprime el código de barras horizontalmente (`AspectRatio = 0.5`), produciendo una apariencia más ancha.

Ahora tienes dos archivos **barcode PNG** con diferentes relaciones de aspecto listos para usar en informes, etiquetas o elementos de UI.

## Problemas comunes y soluciones
| Problema | Solución |
|----------|----------|
| **La imagen generada está borrosa** | Aumenta el parámetro `Resolution` antes de guardar (`gen.Parameters.ImageResolution = 300`). |
| **El código de barras no se escanea** | Asegúrate de que la relación de aspecto se mantenga entre 0.5 – 2.0 y conserva una zona silenciosa suficiente (`gen.Parameters.Barcode.CodeTextParameters.Margin`). |
| **Errores de ruta de archivo** | Utiliza `Path.Combine` para construir la ruta de salida y verifica que la carpeta exista. |

## Preguntas frecuentes

**Q:** ¿Puedo personalizar la relación de aspecto de otros tipos de códigos de barras usando Aspose.BarCode para .NET?  
**A:** Sí, muchos códigos de barras 2‑D (p. ej., QR, PDF417) admiten ajustes de relación de aspecto a través de sus objetos de parámetros específicos.

**Q:** ¿Hay una prueba gratuita disponible para Aspose.BarCode para .NET?  
**A:** Sí, puedes acceder a una prueba gratuita de Aspose.BarCode para .NET [aquí](https://releases.aspose.com/).

**Q:** ¿Dónde puedo comprar una licencia para Aspose.BarCode para .NET?  
**A:** Puedes comprar una licencia en el sitio web de Aspose [aquí](https://purchase.aspose.com/buy).

**Q:** ¿Es Aspose.BarCode para .NET compatible con diferentes versiones de .NET Framework?  
**A:** Sí, funciona con .NET Framework 4.x, .NET Core 3.1+ y las últimas versiones de .NET.

**Q:** ¿Puedo generar códigos de barras en diferentes formatos con Aspose.BarCode para .NET?  
**A:** Absolutamente – PNG, JPEG, BMP, GIF, TIFF, SVG y PDF son compatibles de forma nativa.

## Conclusión

Personalizar la **relación de aspecto** de un código de barras DataMatrix y **crear archivos barcode PNG** es sencillo con Aspose.BarCode para .NET. Siguiendo los pasos anteriores, puedes generar códigos de barras de tamaño perfecto que cumplan con los requisitos exactos de diseño de tu proyecto. Explora parámetros adicionales como `Resolution`, `Margin` y `Color` para ajustar aún más la salida, y considera las capacidades de `generate datamatrix barcode` al crear aplicaciones amigables con el escaneo en Visual Studio.

Para una exploración más profunda, consulta la [documentación](https://reference.aspose.com/barcode/net/) oficial o únete a la comunidad en el [foro de Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**Última actualización:** 2026-05-30  
**Probado con:** Aspose.BarCode 24.12 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Generar código de barras DataMatrix – Guía Pro con Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/)
- [Cómo generar códigos de barras DataMatrix (ECC 200) con Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Dominar la codificación DataMatrix en ASCII con Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}