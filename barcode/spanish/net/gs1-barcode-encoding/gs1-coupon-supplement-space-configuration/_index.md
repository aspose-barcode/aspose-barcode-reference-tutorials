---
date: 2026-09-28
description: Aprenda cómo crear un espacio personalizado de código de barras para
  cupones GS1 con Aspose.BarCode para .NET y mejore la legibilidad del código de barras.
  Siga nuestra guía paso a paso.
keywords:
- create barcode custom space
- GS1 coupon supplement
- Aspose.BarCode .NET
- increase barcode readability
lastmod: 2026-09-28
linktitle: Configuración del espacio del suplemento de cupones GS1
og_description: Aprenda cómo crear un espacio personalizado de código de barras para
  cupones GS1 con Aspose.BarCode para .NET y mejore la legibilidad del código de barras.
  Código paso a paso y consejos incluidos.
og_image_alt: Screenshot of a GS1 coupon barcode generated with custom supplement
  space using Aspose.BarCode for .NET
og_title: Crear espacio personalizado de código de barras para el suplemento de cupones
  GS1 – Aspose.BarCode .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  headline: How to create barcode custom space for GS1 coupon supplement
  type: TechArticle
- description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  name: How to create barcode custom space for GS1 coupon supplement
  steps:
  - name: '**Visual Studio** – The primary IDE for .NET development.'
    text: '**Visual Studio** – The primary IDE for .NET development.'
  - name: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
  - name: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
    text: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
  - name: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
    text: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
  - name: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
    text: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
  - name: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
    text: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
  type: HowTo
- questions:
  - answer: It adds a mandatory blank margin around the supplemental data, improving
      scanner reliability and meeting retailer‑specified minimum widths.
    question: What is the purpose of the GS1 Coupon Supplement Space in barcodes?
  - answer: Yes, set `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` to any
      integer value; the library instantly applies the change to the generated image.
    question: Can I customize the width of the GS1 Coupon Supplement Space with Aspose.BarCode
      for .NET?
  - answer: Refer to the [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)
      and visit the [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)
      for community assistance.
    question: Where can I find additional documentation and support for Aspose.BarCode
      for .NET?
  - answer: Absolutely. The API offers straightforward methods for quick tasks and
      advanced options for fine‑tuned barcode generation.
    question: Is Aspose.BarCode for .NET suitable for both beginners and experienced
      developers?
  - answer: Yes, request a trial license from the [Aspose temporary license website](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for Aspose.BarCode for .NET to evaluate
      its features?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- barcode configuration
- GS1 standards
- Aspose.BarCode
- .NET barcode generation
title: Cómo crear un espacio personalizado de código de barras para el suplemento
  de cupones GS1
url: /es/net/gs1-barcode-encoding/gs1-coupon-supplement-space-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configuración del espacio suplementario del cupón GS1

En este tutorial **creará espacio personalizado de código de barras** para el Espacio Suplementario del Cupón GS1 usando Aspose.BarCode para .NET. Ajustar el espacio suplementario es esencial cuando necesita **aumentar la legibilidad del código de barras** en escáneres de baja resolución o cumplir con los márgenes exigidos por los minoristas. Al final de esta guía comprenderá por qué el espacio suplementario es importante, cómo configurarlo programáticamente y cómo generar imágenes con diferentes valores de píxeles.

## Respuestas rápidas
- **¿Qué controla el espacio suplementario?** Define el área en blanco (en píxeles) entre los datos del cupón y el resto del código de barras.  
- **¿Qué tipo de código de barras se utiliza?** `EncodeTypes.UpcaGs1DatabarCoupon`.  
- **¿Puedo cambiar el tamaño del espacio?** Sí – establezca `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` a cualquier valor entero.  
- **¿Necesito una licencia para esta función?** Una licencia temporal funciona para evaluación; se requiere una licencia completa para producción.  
- **¿Qué formatos de salida son compatibles?** PNG, JPEG, BMP, GIF, TIFF y más a través de `BarCodeImageFormat`.

## Qué es el espacio suplementario del cupón GS1
El Espacio Suplementario del Cupón GS1 es una región en blanco definida que aparece en los códigos de barras de cupones GS1‑Databar. Los sistemas minoristas utilizan este espacio para mejorar la fiabilidad del escaneo y cumplir con las especificaciones de la industria que requieren un margen mínimo alrededor de los datos suplementarios.

## Por qué configurar el espacio suplementario
El espacio suplementario **aumenta directamente la legibilidad del código de barras** y le ayuda a cumplir con las estrictas directrices de los minoristas. Al añadir píxeles adicionales reduce la probabilidad de lecturas erróneas en escáneres de baja resolución, asegura un escaneo consistente en diversos tamaños de etiquetas y le brinda flexibilidad visual para equilibrar el código de barras dentro de un diseño impreso.

## Requisitos previos

Antes de sumergirnos en la configuración del Espacio Suplementario del Cupón GS1 con Aspose.BarCode para .NET, asegúrese de contar con lo siguiente:

1. **Visual Studio** – El IDE principal para el desarrollo .NET.  
2. **Aspose.BarCode for .NET** – Descargue la biblioteca desde la [documentación de Aspose.BarCode for .NET](https://reference.aspose.com/barcode/net/).  
3. **.NET Framework o .NET 5+** – Se requiere familiaridad con C# y el tiempo de ejecución .NET.

Ahora que el entorno está listo, pasemos a la implementación.

## Importar espacios de nombres

El espacio de nombres `Aspose.BarCode.Generation` contiene la clase `BarcodeGenerator` y configuraciones relacionadas.

```csharp
using Aspose.BarCode;
```

## Paso 1: definir la ruta

Elija una carpeta donde se guardarán las imágenes generadas. La ruta debe terminar con el separador de directorios apropiado para su sistema operativo.

```csharp
string path = "Your Directory Path";
```

## Paso 2: generar la configuración del espacio suplementario del cupón GS1

El siguiente fragmento crea un código de barras, establece la dimensión X y ajusta el espacio suplementario.

```csharp
System.Console.WriteLine("Gs1CouponSupplementSpace:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.UpcaGs1DatabarCoupon, "123456789012(8110)ASPOSE");
gen.Parameters.Barcode.XDimension.Pixels = 2;

// Set coupon supplement space to 30 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 30;
gen.Save($"{path}Gs1CouponSpace30Pixels.png", BarCodeImageFormat.Png);

// Set coupon supplement space to 50 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 50;
gen.Save($"{path}Gs1CouponSpace50Pixels.png", BarCodeImageFormat.Png);
```

En este ejemplo nosotros:

1. **Crear** una instancia de `BarcodeGenerator` para el tipo `UpcaGs1DatabarCoupon`.  
2. **Establecer** la dimensión X a 2 píxeles, lo que determina el ancho de barra más estrecho.  
3. **Ajustar** la propiedad `SupplementSpace.Pixels` a 30 px, generar una imagen y luego repetir con 50 px.  

Sienta libre de experimentar con otros valores de píxeles para adaptarlos a su flujo de trabajo de impresión.

## Problemas comunes y consejos
- **Ruta inválida** – Asegúrese de que la variable `path` termine con una barra invertida (`\`) o barra diagonal (`/`) adecuada para su SO.  
- **Permisos insuficientes** – Ejecute Visual Studio como Administrador o elija una carpeta donde la aplicación tenga acceso de escritura.  
- **Formato de datos incorrecto** – La cadena de datos debe seguir la sintaxis GS1 (`(8110)` denota el identificador del suplemento).

## Por qué esto es importante para su negocio

Aspose.BarCode soporta **más de 60 simbologías de códigos de barras** y puede renderizar imágenes de hasta **10,000 × 10,000 píxeles** sin agotar la memoria. Para implementaciones minoristas a gran escala, esto significa que puede generar cupones GS1 de alta resolución en modo por lotes mientras mantiene el tiempo de procesamiento bajo un segundo por imagen en hardware de servidor típico.

## Preguntas frecuentes

**Q: ¿Cuál es el propósito del Espacio Suplementario del Cupón GS1 en los códigos de barras?**  
A: Añade un margen en blanco obligatorio alrededor de los datos suplementarios, mejorando la fiabilidad del escáner y cumpliendo con los anchos mínimos especificados por los minoristas.

**Q: ¿Puedo personalizar el ancho del Espacio Suplementario del Cupón GS1 con Aspose.BarCode para .NET?**  
A: Sí, establezca `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` a cualquier valor entero; la biblioteca aplica instantáneamente el cambio a la imagen generada.

**Q: ¿Dónde puedo encontrar documentación adicional y soporte para Aspose.BarCode para .NET?**  
A: Consulte la [documentación de Aspose.BarCode for .NET](https://reference.aspose.com/barcode/net/) y visite el [foro de Aspose.BarCode](https://forum.aspose.com/c/barcode/13) para obtener asistencia de la comunidad.

**Q: ¿Aspose.BarCode para .NET es adecuado tanto para principiantes como para desarrolladores experimentados?**  
A: Absolutamente. La API ofrece métodos sencillos para tareas rápidas y opciones avanzadas para una generación de códigos de barras afinada.

**Q: ¿Puedo obtener una licencia temporal para Aspose.BarCode para .NET y evaluar sus funciones?**  
A: Sí, solicite una licencia de prueba en el [sitio web de licencias temporales de Aspose](https://purchase.aspose.com/temporary-license/).

## Conclusión

Al seguir los pasos anteriores ahora sabe cómo **crear espacio personalizado de código de barras** para el Espacio Suplementario del Cupón GS1, una técnica clave para **aumentar la legibilidad del código de barras** y cumplir con los estándares minoristas. Incorpore el código en sus soluciones de escaneo existentes, experimente con diferentes valores de píxeles y explore otros tipos de códigos de barras ofrecidos por Aspose.BarCode para .NET.

---

**Última actualización:** 2026-09-28  
**Probado con:** Aspose.BarCode 24.12 for .NET  
**Autor:** Aspose

## Tutoriales relacionados

- [Generar código de barras Databar de Aspose.BarCode usando la API .NET – Configuración de filas y columnas](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)
- [Cómo generar códigos de barras DataMatrix usando Aspose.BarCode para .NET – Guía paso a paso](/barcode/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}