---
date: 2026-09-08
description: Aprenda cómo crear un código de barras code 128 y generar códigos de
  barras GS1 en C# con Aspose.BarCode para .NET. Guía paso a paso, requisitos previos
  y personalización sin código.
keywords:
- create code 128 barcode
- generate gs1 barcode
- how to generate barcode
- create barcode from data
- step by step barcode
lastmod: 2026-09-08
linktitle: Ejemplo de GS1 Code 128
og_description: Aprenda cómo crear un código de barras code 128 y generar códigos
  de barras GS1 en C# con Aspose.BarCode para .NET. Siga una guía paso a paso para
  generar y guardar imágenes de códigos de barras rápidamente.
og_image_alt: 'Developer guide: create code 128 barcode with Aspose.BarCode .NET'
og_title: Cómo crear un código de barras code 128 con GS1 usando Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-08'
  description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  headline: How to create code 128 barcode with GS1 using Aspose.BarCode
  type: TechArticle
- description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  name: How to create code 128 barcode with GS1 using Aspose.BarCode
  steps:
  - name: set your directory path
    text: Define the folder where the generated image will be stored. Keeping the
      path configurable makes the code reusable across environments. Replace `"Your
      Directory Path"` with an absolute or relative path that your application can
      write to, such as `@"C:\Barcodes"` or `Path.Combine(Environment.CurrentDi
  - name: create a GS1 Code 128 barcode
    text: Create the barcode generator, specify the symbology, and provide GS1‑formatted
      data. The data string must include Application Identifiers wrapped in parentheses.
      The example uses the GTIN `(01)12345678901231`, a serial number `(21)ASPOSE`,
      and an additional custom AI `(30)9876`. Aspose.BarCode autom
  - name: customize barcode parameters
    text: Adjust visual parameters such as `XDimension` (the width of the narrow bar)
      to control the barcode’s density. You can also modify height, colors, and margins.
      Setting `XDimension = 2` yields a barcode that is easily scannable by most handheld
      readers while keeping the image size modest.
  - name: save the barcode image
    text: Persist the generated barcode to disk. You may choose PNG for lossless quality,
      JPEG for smaller files, or TIFF for printing workflows. The `Save` method writes
      the image file in the format indicated by the file extension. Replace `GS1Code128Example.png`
      with any valid filename and extension that ma
  - name: verify the barcode (optional)
    text: After saving, you can load the image back into your application or use a
      barcode scanner to confirm that the encoded data matches the original string.
      This step is useful during development and automated testing.
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode works with .NET Core and .NET 5/6, so you can expose
      a lightweight REST endpoint that returns barcode images on demand.
    question: Can I generate barcodes in a web API without installing the full .NET
      Framework?
  - answer: Absolutely. Loop through a collection of data strings, instantiate a `BarcodeGenerator`
      for each, and call `Save` inside the loop. The library is thread‑safe for parallel
      processing.
    question: Does the library support batch generation of multiple barcodes?
  - answer: Use Aspose.PDF to create a PDF document, then call `PdfPage.AddImage`
      with the barcode image stream. This avoids writing intermediate files to disk.
    question: Is there a way to embed the barcode directly into a PDF?
  - answer: Set `BarcodeGenerator.Options.Barcode.XDimension` to at least 0.33 mm
      and enable `BarHeight` according to the label size. Aspose.BarCode validates
      the AI format and throws an exception for invalid data.
    question: How can I ensure the barcode meets ISO/GS1 quality standards?
  - answer: Aspose offers perpetual, subscription, and cloud‑based licensing models.
      A trial license works for evaluation, but a paid license removes the evaluation
      watermark and unlocks all features.
    question: What licensing options are available for production use?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- create code 128 barcode
- Aspose.BarCode
- .NET barcode generation
title: Cómo crear un código de barras code 128 con GS1 usando Aspose.BarCode
url: /es/net/gs1-barcode-encoding/gs1-code-128-example/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear código de barras code 128 con GS1 usando Aspose.BarCode

En este tutorial aprenderá a **crear un código de barras code 128** que cumpla con el estándar GS1 usando la biblioteca Aspose.BarCode para .NET. Ya sea que necesite un código de barras para inventario, envío o punto de venta, esta guía lo acompaña paso a paso—desde la configuración del entorno de desarrollo hasta el guardado de la imagen final—para que pueda comenzar a generar códigos de barras fiables en minutos.

## Respuestas rápidas
- **¿Cuál es la clase principal para generar un código de barras?** `BarcodeGenerator` crea y configura la imagen del código de barras.  
- **¿Qué simbología usa GS1 Code 128?** Utiliza el tipo `EncodeTypes.Code128` con formato de datos específico de GS1.  
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita funciona para evaluación; se requiere una licencia comercial para producción.  
- **¿Puedo cambiar el formato de imagen?** Sí—guarde como PNG, JPEG, BMP o TIFF cambiando la extensión del archivo.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ y .NET 6+.

## ¿Qué es crear código de barras code 128?
`create code 128 barcode` se refiere a generar un código de barras lineal que codifica datos alfanuméricos usando la simbología Code 128, ampliamente adoptada en logística porque soporta todo el conjunto ASCII y puede incorporar Identificadores de Aplicación (AI) de GS1. El código de barras puede almacenar identificadores de producto, números de serie y otros datos personalizados, lo que lo hace adecuado para una amplia gama de escenarios empresariales.

## ¿Por qué usar Aspose.BarCode para GS1 Code 128?
Aspose.BarCode soporta **más de 30 simbologías de códigos de barras** y puede renderizar imágenes de hasta **10 000 × 10 000 px** sin pérdida de calidad, lo que lo hace apto para impresión de etiquetas de alta resolución. La biblioteca también valida automáticamente las estructuras de datos GS1, reduciendo el riesgo de códigos de barras mal formados en líneas de producción. Además, ofrece amplias opciones de personalización de tamaño, color y diseño, lo que ayuda a cumplir con estrictos estándares de la industria.

## Requisitos previos
Antes de comenzar, asegúrese de contar con lo siguiente:

1. **Entorno de desarrollo .NET** – Visual Studio 2022, Rider o cualquier IDE que soporte .NET 6+.  
2. **Aspose.BarCode para .NET** – descárguelo desde la **página de descarga de Aspose.BarCode para .NET** en [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/) y añada el paquete NuGet `Aspose.BarCode` a su proyecto.  
3. **Conocimientos básicos de C#** – debe sentirse cómodo creando aplicaciones de consola o Windows.  
4. **Comprensión de GS1 Code 128** – opcional pero útil; GS1 usa Identificadores de Aplicación (AI) como `(01)` para GTIN y `(21)` para números de serie.

## Cómo crear código de barras code 128 paso a paso

Cargue la biblioteca, configure el tipo de código de barras, establezca los datos GS1, personalice las dimensiones y, finalmente, guarde la imagen. La respuesta directa a la pregunta “¿cómo crear código de barras code 128?” es: **instanciar `BarcodeGenerator` con `EncodeTypes.Code128` y datos formateados según GS1, ajustar `XDimension` si es necesario, y luego llamar a `Save` con el nombre y formato de archivo deseados**. Las siguientes secciones desglosan cada paso.

### Paso 1: establezca la ruta de su directorio
Defina la carpeta donde se almacenará la imagen generada. Mantener la ruta configurable hace que el código sea reutilizable en diferentes entornos.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Reemplace `"Your Directory Path"` por una ruta absoluta o relativa a la que su aplicación pueda escribir, como `@"C:\Barcodes"` o `Path.Combine(Environment.CurrentDirectory, "Output")`.

### Paso 2: cree un código de barras GS1 Code 128
Cree el generador de códigos de barras, especifique la simbología y proporcione datos formateados según GS1. La cadena de datos debe incluir Identificadores de Aplicación entre paréntesis.

```csharp
string path = "Your Directory Path";
```

El ejemplo utiliza el GTIN `(01)12345678901231`, un número de serie `(21)ASPOSE` y un AI personalizado adicional `(30)9876`. Aspose.BarCode inserta automáticamente el carácter FNC1 necesario para el cumplimiento de GS1.

### Paso 3: personalice los parámetros del código de barras
Ajuste parámetros visuales como `XDimension` (el ancho de la barra estrecha) para controlar la densidad del código de barras. También puede modificar la altura, colores y márgenes.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1Code128, "(01)12345678901231(21)ASPOSE(30)9876");
```

Establecer `XDimension = 2` produce un código de barras que es fácilmente escaneable por la mayoría de lectores portátiles mientras mantiene un tamaño de imagen razonable.

### Paso 4: guarde la imagen del código de barras
Persista el código de barras generado en disco. Puede elegir PNG para calidad sin pérdidas, JPEG para archivos más pequeños o TIFF para flujos de trabajo de impresión. El método `Save` escribe el archivo de imagen en el formato indicado por la extensión del archivo.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

Reemplace `GS1Code128Example.png` por cualquier nombre de archivo válido y extensión que coincida con el formato de salida deseado.

### Paso 5: verifique el código de barras (opcional)
Después de guardar, puede cargar la imagen nuevamente en su aplicación o usar un escáner de códigos de barras para confirmar que los datos codificados coinciden con la cadena original. Este paso es útil durante el desarrollo y pruebas automatizadas.

```csharp
gen.Save($"{path}GS1Code128Example.png", BarCodeImageFormat.Png);
```

## Problemas comunes y consejos de solución
- **FNC1 no detectado** – Asegúrese de que la cadena de datos comience con un paréntesis de apertura e incluya AI de GS1 válidos; la biblioteca inserta FNC1 automáticamente solo para patrones reconocidos.  
- **Imagen no guardada** – Verifique que el directorio de destino exista y que la aplicación tenga permisos de escritura. Use `Directory.CreateDirectory(path)` para crearlo al vuelo.  
- **Código de barras demasiado denso** – Disminuya `XDimension` o aumente la altura de la imagen para dar a los lectores más espacio para leer barras estrechas.  
- **Caracteres no soportados** – Code 128 solo puede codificar el conjunto ASCII completo; evite caracteres Unicode fuera de este rango.

## Preguntas frecuentes

**P: ¿Puedo generar códigos de barras en una API web sin instalar todo el .NET Framework?**  
R: Sí, Aspose.BarCode funciona con .NET Core y .NET 5/6, por lo que puede exponer un endpoint REST ligero que devuelva imágenes de códigos de barras bajo demanda.

**P: ¿La biblioteca soporta generación por lotes de múltiples códigos de barras?**  
R: Absolutamente. Recorra una colección de cadenas de datos, instancie un `BarcodeGenerator` para cada una y llame a `Save` dentro del bucle. La biblioteca es segura para subprocesos y permite procesamiento paralelo.

**P: ¿Existe una forma de incrustar el código de barras directamente en un PDF?**  
R: Use Aspose.PDF para crear un documento PDF y luego llame a `PdfPage.AddImage` con el flujo de la imagen del código de barras. Así evita escribir archivos intermedios en disco.

**P: ¿Cómo puedo asegurar que el código de barras cumpla con los estándares de calidad ISO/GS1?**  
R: Establezca `BarcodeGenerator.Options.Barcode.XDimension` en al menos 0.33 mm y habilite `BarHeight` según el tamaño de la etiqueta. Aspose.BarCode valida el formato de AI y lanza una excepción si los datos son inválidos.

**P: ¿Qué opciones de licencia están disponibles para uso en producción?**  
R: Aspose ofrece licencias perpetuas, por suscripción y basadas en la nube. Una licencia de prueba funciona para evaluación, pero una licencia paga elimina la marca de agua de evaluación y desbloquea todas las funciones.

## Recursos adicionales

- **Documentación** – Acceda a la referencia completa de la API en [https://reference.aspose.com/barcode/net/](https://reference.aspose.com/barcode/net/).  
- **Descarga** – Obtenga la última versión de la biblioteca en [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/).  
- **Prueba gratuita** – Inicie una prueba de 30 días en [https://releases.aspose.com/](https://releases.aspose.com/).  
- **Compra** – Adquiera una licencia comercial en [https://purchase.aspose.com/buy](https://purchase.aspose.com/buy).  
- **Soporte** – Únase al foro de la comunidad en [https://forum.aspose.com/c/barcode/13](https://forum.aspose.com/c/barcode/13) para obtener ayuda de solución de problemas.

---

**Última actualización:** 2026-09-08  
**Probado con:** Aspose.BarCode 24.11 para .NET  
**Autor:** Aspose

## Tutoriales relacionados

- [How to Create ITF-14 Barcode .NET – Comprehensive Aspose.BarCode Tutorials](/barcode/net/)
- [Generate One-Dimensional Databar 2D Barcodes Using Aspose.BarCode .NET API](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}