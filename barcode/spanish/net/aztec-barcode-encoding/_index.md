---
date: 2026-05-19
description: Aprenda cómo crear un código de barras Aztec usando Aspose.BarCode para
  .NET, personalice las relaciones de aspecto, codifique bytes o texto, y domine los
  modos de símbolo.
keywords:
- create aztec barcode
- aztec barcode encoding
- aspose barcode .net
linktitle: Codificación de código de barras Aztec
schemas:
- author: Aspose
  dateModified: '2026-05-19'
  description: Learn how to create Aztec barcode using Aspose.BarCode for .NET, customize
    aspect ratios, encode bytes or text, and master symbol modes.
  headline: How to create Aztec barcode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create Aztec barcode using Aspose.BarCode for .NET, customize
    aspect ratios, encode bytes or text, and master symbol modes.
  name: How to create Aztec barcode with Aspose.BarCode for .NET
  steps:
  - name: '**Create a `BarcodeGenerator` instance** with `EncodeTypes.Aztec`.'
    text: '**Create a `BarcodeGenerator` instance** with `EncodeTypes.Aztec`.'
  - name: '**Assign your data** (text, bytes, or numeric string).'
    text: '**Assign your data** (text, bytes, or numeric string).'
  - name: '**Set `AspectRatio`** – for example, `1.5` for a wider bar.'
    text: '**Set `AspectRatio`** – for example, `1.5` for a wider bar.'
  - name: '**Generate the image** using `Save` or `GetBarCodeImage`.'
    text: '**Generate the image** using `Save` or `GetBarCodeImage`.'
  - name: '**Prepare the byte array** (e.g., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).'
    text: '**Prepare the byte array** (e.g., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).'
  - name: '**Instantiate `BarcodeGenerator`** with `EncodeTypes.Aztec`.'
    text: '**Instantiate `BarcodeGenerator`** with `EncodeTypes.Aztec`.'
  - name: '**Call `EncodeBytes(data)`** to load the binary content.'
    text: '**Call `EncodeBytes(data)`** to load the binary content.'
  - name: '**Render the barcode** with `Save` or `GetBarCodeImage`.'
    text: '**Render the barcode** with `Save` or `GetBarCodeImage`.'
  - name: '**Create the generator** with `EncodeTypes.Aztec`.'
    text: '**Create the generator** with `EncodeTypes.Aztec`.'
  - name: '**Set `CodeText`** to the string you want to encode.'
    text: '**Set `CodeText`** to the string you want to encode.'
  type: HowTo
- questions:
  - answer: The library works with .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET
      6, and later.
    question: Which .NET versions are supported by Aspose.BarCode for Aztec encoding?
  - answer: Yes—set the `Resolution` property (e.g., 300 dpi) before saving the image
      to obtain print‑ready quality.
    question: Can I create a high‑resolution Aztec barcode for printing?
  - answer: Up to 3,000 numeric or 2,300 alphanumeric characters, or roughly 1,800
      bytes of raw data in Compact mode.
    question: How large a data payload can an Aztec barcode hold?
  - answer: Absolutely—Aspose.BarCode’s decoder automatically detects orientation
      and corrects it during the read operation.
    question: Is it possible to read an Aztec barcode that has been rotated?
  - answer: A free evaluation license is available for testing; a commercial license
      is required for production deployments.
    question: Do I need a license for development and testing?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Cómo crear un código de barras Aztec con Aspose.BarCode para .NET
url: /es/net/aztec-barcode-encoding/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Codificación de código de barras Aztec

¿Estás listo para sumergirte en el mundo de la codificación de códigos de barras Aztec y aprender a **create Aztec barcode** imágenes con Aspose.BarCode for .NET? Esta biblioteca te brinda control total sobre el tamaño, la corrección de errores y la representación de datos, lo que la hace ideal para todo, desde la emisión de boletos móviles hasta el seguimiento de inventario.

## Respuestas rápidas
- **¿Qué biblioteca admite códigos de barras Aztec?** Aspose.BarCode for .NET  
- **¿Puedo cambiar la relación de aspecto?** Yes, via the `AspectRatio` property  
- **¿Es posible la codificación a nivel de byte?** Absolutely – use the `EncodeBytes` method  
- **¿Qué niveles de corrección de errores están disponibles?** Levels 0 to 4 (higher = more redundancy)  
- **¿Necesito una licencia para producción?** Yes, a commercial license removes evaluation limits  

## ¿Qué es un código de barras Aztec?
Un código de barras Aztec es un código matricial bidimensional que puede codificar hasta 3 000 caracteres numéricos o 2 300 alfanuméricos. Presenta un patrón central de localización, lo que permite un escaneo rápido incluso cuando el símbolo se imprime a baja resolución. Debido a que el patrón está ubicado en el centro, el código puede leerse desde cualquier dirección, lo que lo hace altamente fiable para aplicaciones móviles e industriales.

## ¿Cómo personalizar la relación de aspecto de un código de barras Aztec?
`BarcodeGenerator` es la clase principal utilizada para crear códigos de barras en Aspose.BarCode. Establece la propiedad `AspectRatio` en el objeto `BarcodeGenerator` al proporción ancho‑alto deseada, luego genera la imagen. Ajustar la relación de aspecto ayuda a encajar el código de barras en espacios UI limitados o diseños de etiquetas sin sacrificar la fiabilidad del escaneo, y también permite que coincida con las directrices de marca o requisitos específicos de la impresora.

### Pasos para personalizar la relación de aspecto
1. **Crea una instancia de `BarcodeGenerator`** con `EncodeTypes.Aztec`.  
2. **Asigna tus datos** (texto, bytes o cadena numérica).  
3. **Establece `AspectRatio`** – por ejemplo, `1.5` para una barra más ancha.  
4. **Genera la imagen** usando `Save` o `GetBarCodeImage`.  

## ¿Cómo codificar bytes sin procesar en un código de barras Aztec?
`EncodeBytes` es un método que acepta una matriz de bytes y la convierte en una matriz Aztec. Pasa una matriz de bytes al método `EncodeBytes` de `BarcodeGenerator`. La API convierte automáticamente los datos binarios en una matriz Aztec compacta, preservando cada bit. Esto es perfecto para incrustar cargas útiles cifradas, identificadores binarios o archivos comprimidos directamente en un código de barras.

### Pasos para codificar bytes
1. **Prepara la matriz de bytes** (p.ej., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).  
2. **Instancia `BarcodeGenerator`** con `EncodeTypes.Aztec`.  
3. **Llama a `EncodeBytes(data)`** para cargar el contenido binario.  
4. **Renderiza el código de barras** con `Save` o `GetBarCodeImage`.  

## ¿Cómo codificar texto en un código de barras Aztec?
`CodeText` es una propiedad que contiene los datos de texto plano a codificar. Usa la propiedad `CodeText` de `BarcodeGenerator` para proporcionar datos de texto plano. La biblioteca selecciona automáticamente el modo de codificación óptimo (numérico, alfanumérico o byte) y aplica el nivel de corrección de errores apropiado. Esto facilita incrustar URLs, IDs de producto o cualquier cadena legible.

### Pasos para codificar texto
1. **Crea el generador** con `EncodeTypes.Aztec`.  
2. **Establece `CodeText`** a la cadena que deseas codificar.  
3. **Opcionalmente ajusta `ErrorLevel`** para mayor resiliencia.  
4. **Genera la imagen** usando `Save` o `GetBarCodeImage`.  

## ¿Cómo generar códigos de barras Aztec con diferentes niveles de corrección de errores?
`ErrorLevel` es una propiedad que controla la cantidad de datos redundantes añadidos al código de barras. Ajusta la propiedad `ErrorLevel` (0‑4) antes de renderizar. Los niveles más altos aumentan la cantidad de datos redundantes, permitiendo que el código de barras se lea incluso cuando hasta el 30 % del símbolo está dañado. Esto es crucial para entornos duros como el etiquetado industrial o señalización exterior.

### Pasos para establecer la corrección de errores
1. **Instancia `BarcodeGenerator`** para Aztec.  
2. **Asigna tus datos** (texto o bytes).  
3. **Establece `ErrorLevel`** – p.ej., `generator.Parameters.Barcode.Aztec.ErrorLevel = 3`.  
4. **Renderiza el código de barras** con el formato de salida que prefieras.  

## ¿Cuáles son los diferentes modos de símbolo Aztec y cómo utilizarlos?
`SymbolMode` es una configuración que determina el tamaño de la matriz y la capacidad de datos del código Aztec generado. El modo de símbolo Aztec determina el tamaño de la matriz y la capacidad de datos. La biblioteca ofrece cuatro modos: **Auto**, **FullRange**, **Compact** y **Rune**.  

- **Auto** – el generador selecciona el tamaño más pequeño posible.  
- **FullRange** – permite el tamaño máximo de matriz para conjuntos de datos muy grandes.  
- **Compact** – crea un símbolo más pequeño y denso, ideal para espacios limitados.  
- **Rune** – un modo especializado para codificar runas Unicode.  

Selecciona el modo a través de `Generator.Parameters.Barcode.Aztec.SymbolMode`. Cada modo equilibra tamaño, legibilidad y capacidad de datos, permitiéndote adaptar el código de barras a las limitaciones de tu aplicación.

## Tutoriales de codificación de códigos de barras Aztec
A continuación se presentan las guías paso a paso dedicadas que profundizan en cada uno de los temas cubiertos arriba. Haz clic en cualquier enlace para explorar ejemplos de código completos, requisitos previos y consejos de mejores prácticas.

### [Personalizar la relación de aspecto del código de barras Aztec](./aztec-aspect-ratio-customization/)
Aprende cómo personalizar las relaciones de aspecto de los códigos de barras Aztec usando Aspose.BarCode for .NET. Crea códigos de barras únicos y flexibles para tus aplicaciones .NET.

### [Aztec Bytes Encoding](./aztec-bytes-encoding/)
Aprende cómo realizar la codificación de bytes Aztec con Aspose.BarCode for .NET. Guía paso a paso, requisitos previos y ejemplos de código incluidos.

### [Aztec Code Text Encoding](./aztec-code-text-encoding/)
Descubre el poder de la codificación de texto de códigos Aztec con Aspose.BarCode for .NET. Aprende cómo crear y reconocer códigos Aztec en tus aplicaciones .NET.

### [Generating Aztec Error Barcodes](./aztec-error-level-example/)
Aprende cómo generar códigos de barras Aztec con diferentes niveles de error usando Aspose.BarCode for .NET. Guía completa para la creación de códigos de barras.

### [Mastering Aztec Symbol Mode](./aztec-symbol-mode-example/)
Explora el modo de símbolo Aztec en Aspose.BarCode for .NET y aprende a generar códigos de barras versátiles con facilidad. Practica con los modos Auto, FullRange, Compact y Rune en este tutorial completo.

## Preguntas frecuentes

**Q: ¿Qué versiones de .NET son compatibles con Aspose.BarCode para la codificación Aztec?**  
A: La biblioteca funciona con .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6 y posteriores.

**Q: ¿Puedo crear un código de barras Aztec de alta resolución para impresión?**  
A: Sí—establece la propiedad `Resolution` (p.ej., 300 dpi) antes de guardar la imagen para obtener calidad lista para imprimir.

**Q: ¿Qué tamaño de carga de datos puede contener un código de barras Aztec?**  
A: Hasta 3 000 caracteres numéricos o 2 300 alfanuméricos, o aproximadamente 1 800 bytes de datos sin procesar en modo Compact.

**Q: ¿Es posible leer un código de barras Aztec que ha sido rotado?**  
A: Absolutamente—el decodificador de Aspose.BarCode detecta automáticamente la orientación y la corrige durante la operación de lectura.

**Q: ¿Necesito una licencia para desarrollo y pruebas?**  
A: Hay una licencia de evaluación gratuita disponible para pruebas; se requiere una licencia comercial para implementaciones en producción.

---

**Última actualización:** 2026-05-19  
**Probado con:** Aspose.BarCode 24.12 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Cómo generar código de barras Aztec con relación de aspecto personalizada usando Aspose.BarCode for .NET](/barcode/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Codificación de bytes Aztec usando generador de códigos de barras .net](/barcode/net/aztec-barcode-encoding/aztec-bytes-encoding/)
- [Cómo crear código de barras Aztec con corrección de errores en .NET](/barcode/net/aztec-barcode-encoding/aztec-error-level-example/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}