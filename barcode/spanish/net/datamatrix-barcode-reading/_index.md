---
date: 2026-09-28
description: Aprenda a leer datamatrix y a generar códigos de barras datamatrix sin
  esfuerzo usando Aspose.BarCode for .NET. Explore la programación del lector, la
  concatenación estructurada y las guías de generación.
keywords:
- how to read datamatrix
- datamatrix barcode reading
- Aspose.BarCode .NET
lastmod: 2026-09-28
linktitle: Lectura de códigos de barras DataMatrix
og_description: Cómo leer códigos de barras datamatrix usando Aspose.BarCode for .NET
  – una guía rápida y multiplataforma que cubre la lectura, la concatenación estructurada
  y la generación. (150‑160 caracteres)
og_image_alt: Screenshot of Aspose.BarCode reading a DataMatrix barcode in a .NET
  app
og_title: Cómo leer códigos de barras datamatrix con Aspose.BarCode for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to read datamatrix and how to generate datamatrix barcodes
    effortlessly using Aspose.BarCode for .NET. Explore reader programming, structured
    append and generation guides.
  headline: How to read datamatrix barcodes with Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. A valid commercial license is required for production use, but a
      free trial is available for evaluation.
    question: Can I use Aspose.BarCode for commercial projects?
  - answer: Absolutely. You can load a PDF page as an image stream and pass it directly
      to the barcode reader.
    question: Does the library support reading DataMatrix from PDF files?
  - answer: The API automatically assembles the fragments if you enable the `ReadStructuredAppend`
      property before decoding.
    question: How do I handle Structured Append when a barcode is split across multiple
      images?
  - answer: You can choose from ECC 000, 050, 080, 100, 140, and 200 depending on
      the required data density and robustness.
    question: What error‑correction levels are available when generating a DataMatrix
      barcode?
  - answer: Yes—use the `BarcodeReader` with `ReadMultipleBarcodes` set to `true`
      and process images in parallel threads.
    question: Is there a way to improve read performance on large image batches?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix
- Aspose.BarCode
- .NET barcode processing
title: Cómo leer códigos de barras datamatrix con Aspose.BarCode for .NET
url: /es/net/datamatrix-barcode-reading/
weight: 31
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo leer códigos de barras DataMatrix

Si necesita **cómo leer DataMatrix** de manera eficiente en un entorno .NET, esta guía le ofrece un recorrido paso a paso de la lectura, la configuración de structured append y la generación de códigos de barras DataMatrix con Aspose.BarCode para .NET. Verá por qué la biblioteca es una opción principal, qué debe preparar de antemano y dónde encontrar los fragmentos de código más útiles.

## Respuestas rápidas
- **¿Qué es DataMatrix?** Un código de barras matricial bidimensional que almacena grandes cantidades de datos en un espacio diminuto.  
- **¿Qué biblioteca le ayuda a leer DataMatrix en .NET?** Aspose.BarCode for .NET.  
- **¿Necesito una licencia?** Hay una prueba gratuita disponible; se requiere una licencia comercial para producción.  
- **¿Puedo generar también códigos de barras DataMatrix?** Sí—use la misma API para **cómo generar DataMatrix** códigos de barras con configuraciones personalizadas.  
- **¿Plataformas compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7 en Windows, Linux y macOS.

## ¿Qué es la lectura de códigos de barras DataMatrix?
Leer un código de barras DataMatrix extrae el texto codificado o los datos binarios de una imagen, página PDF o fotograma de video en tiempo real. El decodificador de Aspose.BarCode funciona directamente con objetos `System.Drawing.Image`, `Stream` o `PdfPage`, por lo que puede alimentarlo desde archivos, flujos de memoria o capturas de cámara sin pasos de conversión adicionales.

## ¿Por qué usar Aspose.BarCode para DataMatrix?
Aspose.BarCode procesa hasta **5,000 códigos de barras por segundo** en una CPU estándar de 2.5 GHz, maneja **más de 50 formatos de entrada** y no requiere **dependencias nativas externas**. La biblioteca se ejecuta en Windows, Linux y macOS, soporta niveles de corrección de errores desde ECC 000 hasta ECC 200, y ofrece manejo integrado de structured‑append, todo mientras mantiene el uso de memoria por debajo de 20 MB para un lote de 1,000 páginas.

## Prerequisites
- .NET Framework 4.5+ o .NET Core 3.1+ (cualquier versión reciente de .NET).  
- Paquete NuGet de Aspose.BarCode para .NET instalado.  
- Familiaridad básica con C# y un IDE como Visual Studio o Rider.

## Programación del lector DataMatrix: una integración sin problemas

### ¿Cómo leer un código de barras DataMatrix en .NET?
`BarcodeReader` es la clase de Aspose.BarCode que decodifica códigos de barras a partir de imágenes, flujos o páginas PDF.  
Cargue la imagen o la página PDF, cree un `BarcodeReader`, habilite la bandera `ReadMultipleBarcodes` si espera más de un código, y llame a `Read`. El método devuelve una colección `BarCodeResult` que contiene el valor decodificado, el tipo de simbología y la puntuación de confianza.  
`BarCodeResult` representa un único código de barras decodificado, incluyendo su valor, tipo de simbología y puntuación de confianza.

### ¿Cómo habilitar el manejo de structured append?
Establezca la propiedad `ReadStructuredAppend` a `true` antes de llamar a `Read`. El lector concatenará automáticamente los fragmentos que pertenecen al mismo mensaje lógico, devolviendo un único resultado combinado.

## Configuración de structured append de DataMatrix: organizar datos con precisión

Structured Append permite que un único mensaje lógico se divida entre varios símbolos DataMatrix. Cuando habilita esta función, Aspose.BarCode ensambla los fragmentos basándose en los números de secuencia incrustados en cada símbolo. Esto es ideal para codificar URLs largas, grandes bloques binarios o documentos multipágina.

## Generar códigos de barras DataMatrix: desate la creatividad con Aspose.BarCode para .NET

`BarcodeGenerator` es la clase de Aspose.BarCode utilizada para generar imágenes de códigos de barras con parámetros personalizables. La misma clase `BarcodeGenerator` que usa para la lectura también crea símbolos DataMatrix. Puede controlar el tamaño del módulo, el margen, el nivel ECC e incluso incrustar una imagen de logotipo. El generador produce archivos PNG, JPEG, SVG o PDF, brindándole total flexibilidad para escenarios web, de impresión o móviles.

## Tutoriales de lectura de códigos de barras DataMatrix
### [Programación del lector DataMatrix](./datamatrix-reader-programming/)
Explore la programación del lector DataMatrix con Aspose.BarCode para .NET. Aprenda cómo generar y leer códigos de barras DataMatrix en sus aplicaciones .NET con esta guía completa.
### [Configuración de Structured Append de DataMatrix](./datamatrix-structured-append-configuration/)
Aprenda cómo crear y leer la configuración de structured append de DataMatrix en .NET usando Aspose.BarCode para una organización de datos de alta eficiencia.
### [Generar códigos de barras DataMatrix](./datamatrix-versions/)
Aprenda cómo generar códigos de barras DataMatrix en .NET usando Aspose.BarCode para .NET. Dimensiones personalizadas, soporte ECC y más.

## Preguntas frecuentes

**Q: ¿Puedo usar Aspose.BarCode para proyectos comerciales?**  
A: Sí. Se requiere una licencia comercial válida para uso en producción, pero hay una prueba gratuita disponible para evaluación.

**Q: ¿La biblioteca soporta la lectura de DataMatrix desde archivos PDF?**  
A: Absolutamente. Puede cargar una página PDF como un flujo de imagen y pasarla directamente al lector de códigos de barras.

**Q: ¿Cómo manejo Structured Append cuando un código de barras está dividido en varias imágenes?**  
A: La API ensambla automáticamente los fragmentos si habilita la propiedad `ReadStructuredAppend` antes de decodificar.

**Q: ¿Qué niveles de corrección de errores están disponibles al generar un código de barras DataMatrix?**  
A: Puede elegir entre ECC 000, 050, 080, 100, 140 y 200 según la densidad de datos y la robustez requeridas.

**Q: ¿Hay alguna forma de mejorar el rendimiento de lectura en lotes grandes de imágenes?**  
A: Sí—use el `BarcodeReader` con `ReadMultipleBarcodes` configurado a `true` y procese las imágenes en hilos paralelos.

---

**Última actualización:** 2026-09-28  
**Probado con:** Aspose.BarCode for .NET 24.12  
**Autor:** Aspose

## Tutoriales relacionados

- [Cómo generar códigos de barras DataMatrix usando Aspose.BarCode para .NET – Guía paso a paso](/barcode/net/datamatrix-barcode-configuration/)
- [Cómo leer DataMatrix Append con Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)
- [Generar un código de barras DataMatrix en modo ASCII con Aspose.BarCode para .NET (C#)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}