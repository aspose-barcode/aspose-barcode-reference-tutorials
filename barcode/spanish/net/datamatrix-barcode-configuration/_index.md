---
date: 2026-06-09
description: Aprenda cómo generar datamatrix barcode con Aspose.BarCode para .NET,
  personalice aspect ratios, modos ECC y la codificación datamatrix c40 para una creación
  de códigos de barras eficiente.
keywords:
- generate datamatrix barcode
- datamatrix c40 encoding
- aspose barcode .net
- datamatrix ecc modes
- barcode aspect ratio
linktitle: Configuración de DataMatrix Barcode
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  headline: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  name: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  steps:
  - name: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
    text: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
  - name: '**Adjust** `AspectRatio` to your desired value.'
    text: '**Adjust** `AspectRatio` to your desired value.'
  - name: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
    text: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
  type: HowTo
- questions:
  - answer: Choose ECC 000‑140 for small data sets with limited error correction,
      or ECC 200 for larger data and higher reliability. Macro mode adds an extra
      data layer for linking.
    question: How do I decide which ECC mode to use?
  - answer: Yes, set the `CodeText` property to your custom string, then select the
      appropriate encoding mode (ASCII, C40, etc.) to control size.
    question: Can I embed custom text in a DataMatrix barcode?
  - answer: Set `EncodeMode` to `Auto`; Aspose.BarCode evaluates the payload and picks
      the most space‑efficient mode automatically.
    question: Is there a way to automatically select the best encoding mode?
  - answer: Reuse a single `BarCodeGenerator` instance, enable multi‑threading, and
      generate PNG images for lossless quality or JPEG for smaller file size. Processing
      10 000 symbols typically completes in under 30 seconds on a standard 8‑core
      server.
    question: What are the performance considerations for large barcode batches?
  - answer: Absolutely – the library is fully compatible with .NET Framework, .NET
      Core, and the latest .NET releases, offering the same feature set across all
      platforms.
    question: Does Aspose.BarCode support .NET Core and .NET 5/6?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Generar DataMatrix Barcode – Guía profesional con Aspose.BarCode
url: /es/net/datamatrix-barcode-configuration/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generar código de barras DataMatrix – Guía profesional con Aspose.BarCode

Bienvenido a nuestra completa serie de tutoriales sobre **generate datamatrix barcode** usando Aspose.BarCode para .NET. Ya seas un desarrollador experimentado afinando la salida del código de barras o un recién llegado ansioso por comprender los fundamentos, esta guía lo lleva paso a paso—desde la configuración básica hasta técnicas avanzadas de codificación—para que pueda entregar códigos de barras fiables y listos para escanear en cualquier aplicación .NET.

## Respuestas rápidas
- **¿Cuál es el propósito principal?** Crear y personalizar códigos de barras DataMatrix de forma programática.  
- **¿Qué biblioteca se utiliza?** Aspose.BarCode for .NET.  
- **¿Necesito una licencia?** Disponible una prueba gratuita; se requiere una licencia comercial para producción.  
- **¿Versiones .NET compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **¿Puedo personalizar la relación de aspecto?** Sí – vea la sección “Cómo personalizar la relación de aspecto de DataMatrix”.

## ¿Qué es generate datamatrix barcode?
Un código de barras DataMatrix es una matriz bidimensional de celdas negras y blancas que puede almacenar hasta 2 300 caracteres alfanuméricos. Con Aspose.BarCode, puede **generate datamatrix barcode** imágenes, PDFs o SVGs directamente desde su código .NET, controlando el tamaño, el nivel de corrección de errores y el modo de codificación para cumplir con cualquier estándar de la industria.

## ¿Por qué usar Aspose.BarCode para DataMatrix?
Aspose.BarCode renderiza símbolos DataMatrix a hasta **600 dpi** sin pixelación, garantizando escaneos nítidos en impresoras de alta resolución. Soporta **más de 50 modos ECC y macro**—incluidos ECC 000‑140, ECC 200 y Macro 05/06—para que pueda elegir el nivel de corrección de errores óptimo para el tamaño de sus datos. La API ofrece opciones de codificación **ASCII, C40, Text, X12 y Bytes**, permitiendo empaquetar datos de manera eficiente. La integración requiere solo un paquete NuGet y no necesita bibliotecas nativas externas.

## Cómo personalizar la relación de aspecto de DataMatrix
La propiedad `AspectRatio` de `BarCodeGenerator` controla la proporción ancho‑alto del símbolo DataMatrix generado. `BarCodeGenerator` es la clase principal en Aspose.BarCode utilizada para crear imágenes de códigos de barras.  

**Respuesta directa:** Establezca `generator.Parameters.Barcode.DataMatrix.AspectRatio = 1.2` (o cualquier valor entre 0.5 y 2.0) antes de llamar a `GenerateBarCodeImage()`. La biblioteca recalcula automáticamente el tamaño del módulo para mantener la fiabilidad del escaneo respetando la relación solicitada.

### Paso a paso
1. **Instanciar** `BarCodeGenerator` con `EncodeTypes.DataMatrix`.  
2. **Ajustar** `AspectRatio` al valor deseado.  
3. **Generar** la imagen y verificar con un escáner o el lector incorporado de Aspose.

## Cómo generar códigos de barras DataMatrix ECC 000‑140
ECC 000‑140 es ideal para cadenas de datos cortas donde se requiere un símbolo compacto, ofreciendo hasta 140 palabras de corrección de errores. `DataMatrixEccMode.Ecc000140` selecciona el esquema de corrección de errores ECC 000‑140 para DataMatrix.  

**Respuesta directa:** Use `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc000140` antes de renderizar. Esto cambia el codificador al algoritmo ECC 000‑140, produciendo la matriz más pequeña posible para los datos dados mientras sigue proporcionando una corrección de errores robusta.

### Consejo práctico
Al codificar datos numéricos de menos de 20 caracteres, ECC 000‑140 suele producir una matriz de 10 × 10, lo que ahorra espacio valioso en la etiqueta.

## Cómo generar códigos de barras DataMatrix ECC 200
ECC 200 es el modo DataMatrix más adoptado, soportando hasta 2 335 caracteres alfanuméricos y ofreciendo una corrección de errores superior. `DataMatrixEccMode.Ecc200` selecciona el esquema de corrección de errores ECC 200 para DataMatrix.  

**Respuesta directa:** Establezca `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc200` y proporcione su carga útil mediante `CodeText`. La biblioteca entonces selecciona automáticamente el tamaño de matriz óptimo.

### Cuándo preferir ECC 200
Utilice ECC 200 para cadenas más largas, datos de tipo mixto, o cuando necesite la mayor resistencia contra daños—hasta **30 %** del símbolo puede ser restaurado.

## Cómo dominar la codificación DataMatrix en ASCII
El modo ASCII codifica los caracteres usando un byte por carácter, lo que lo convierte en el más eficiente en espacio para texto plano. `DataMatrixEncodeMode.Ascii` indica al generador que use la codificación ASCII para el símbolo DataMatrix.  

**Respuesta directa:** Asigne `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Ascii` y establezca `CodeText` a su cadena ASCII. El motor empaqueta los datos sin sobrecarga adicional, produciendo la matriz más pequeña posible para contenido ASCII puro.

### Escenario de ejemplo
Un SKU de almacén compuesto por letras mayúsculas y dígitos (p. ej., “AB1234”) encaja perfectamente en modo ASCII, a menudo resultando en una matriz de 12 × 12.

## Cómo generar modo DataMatrix (Auto)
El modo Auto permite a Aspose.BarCode analizar la entrada y seleccionar automáticamente la codificación más eficiente (ASCII, C40, Text, X12 o Bytes). `DataMatrixEncodeMode.Auto` habilita esta función de selección automática.  

**Respuesta directa:** Establezca `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Auto`. La biblioteca evalúa la carga útil, selecciona el modo óptimo y renderiza el código de barras en un solo paso.

### Beneficios
El modo Auto reduce el esfuerzo de desarrollo y garantiza el símbolo más pequeño posible para datos de tipo mixto, mejorando la velocidad de escaneo.

## Cómo usar el modo de codificación DataMatrix (Bytes)
El modo Bytes está diseñado para datos binarios, como cargas cifradas o archivos comprimidos. `DataMatrixEncodeMode.Bytes` indica al generador que trate cada byte como datos sin procesar.  

**Respuesta directa:** Use `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Bytes` y proporcione una cadena codificada en Base64 como `CodeText`. El codificador trata cada byte como datos sin procesar, preservando la representación binaria exacta.

### Caso de uso
Incorporar un GUID de 128 bits o un pequeño token cifrado directamente en un símbolo DataMatrix.

## Cómo dominar el modo de codificación DataMatrix (C40)
El modo C40 comprime datos alfanuméricos en mayúsculas, logrando una reducción de tamaño de hasta **40 %** comparado con ASCII. `DataMatrixEncodeMode.C40` activa este algoritmo de compresión.  

**Respuesta directa:** Establezca `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.C40` y proporcione una cadena en mayúsculas (p. ej., “HELLO WORLD”). El motor empaqueta tres caracteres en dos palabras de código, reduciendo la matriz final.

### Consejo profesional
C40 funciona mejor cuando la carga útil consiste principalmente en letras mayúsculas, números y espacios. Para caso mixto, considere el modo Auto.

## Cómo configurar el texto del código DataMatrix
La propiedad `CodeText` define los datos exactos almacenados en el código de barras. Puede incluir texto plano, cadenas numéricas o incluso cargas XML. `CodeText` es la propiedad de cadena principal de `BarCodeGenerator` que contiene la carga del código de barras.  

**Respuesta directa:** Asigne `generator.Parameters.Barcode.CodeText = "YourDataHere"` antes de renderizar. La propiedad acepta cualquier cadena UTF‑8 hasta la longitud máxima soportada por el modo ECC seleccionado.

### Consejo avanzado
Combine `CodeText` con `ExtendedDataMatrix` para incrustar metadatos adicionales sin aumentar el tamaño visible de la matriz.

## Cómo dominar la configuración macro de DataMatrix
Los modos macro (Macro 05 y Macro 06) le permiten incrustar un símbolo DataMatrix secundario dentro del primario, útil para enlazar a fuentes de datos externas. `DataMatrixMacroMode.Macro05` y `DataMatrixMacroMode.Macro06` habilitan estas funciones macro.  

**Respuesta directa:** Habilite el modo macro con `generator.Parameters.Barcode.DataMatrix.MacroMode = DataMatrixMacroMode.Macro05` (o `Macro06`) y establezca las propiedades `MacroPdf417` para la carga secundaria. El generador crea un símbolo compuesto que los escáneres pueden interpretar como dos códigos vinculados.

### Ejemplo del mundo real
Incrustar una URL en la parte macro mientras se mantienen los identificadores de producto en la matriz primaria, habilitando una integración web‑a‑código de barras sin problemas.

*Listado de tutoriales de Aspose.BarCode para .NET*

## Tutoriales de configuración de códigos de barras DataMatrix
### [Personalizando la relación de aspecto de DataMatrix](./datamatrix-aspect-ratio-customization/)
Aprenda cómo personalizar las relaciones de aspecto de códigos de barras DataMatrix usando Aspose.BarCode para .NET. Guía paso a paso para la generación de códigos de barras.
### [Generar códigos de barras DataMatrix ECC 000-140](./datamatrix-ecc-000-140-configuration/)
Cree códigos de barras DataMatrix ECC 000-140 con facilidad usando Aspose.BarCode para .NET. Mejore la eficiencia en la gestión de inventario y más.
### [Generar códigos de barras DataMatrix ECC 200](./datamatrix-ecc-200-configuration/)
Aprenda a generar códigos de barras DataMatrix ECC 200 en .NET usando Aspose.BarCode. Optimice operaciones con creación eficiente de códigos de barras.
### [Dominar la codificación DataMatrix en ASCII](./datamatrix-encoding-mode-ascii/)
Aprenda a crear códigos de barras DataMatrix en modo ASCII usando Aspose.BarCode para .NET. Guía paso a paso para desarrolladores.
### [Generar modo DataMatrix (Auto)](./datamatrix-encoding-mode-auto/)
Aprenda a generar el modo DataMatrix (Auto) con Aspose.BarCode para .NET. Esta guía paso a paso cubre todo, desde los requisitos previos hasta la lectura de códigos de barras.
### [Modo de codificación DataMatrix (Bytes)](./datamatrix-encoding-mode-bytes/)
Aprenda a codificar datos en formato DataMatrix usando el modo Bytes con Aspose.BarCode para .NET. Siga nuestra guía paso a paso para la generación y reconocimiento de códigos de barras.
### [Dominar el modo de codificación DataMatrix (C40)](./datamatrix-encoding-mode-c40/)
Aprenda el modo de codificación DataMatrix (C40) con Aspose.BarCode para .NET. Cree códigos de barras personalizados de manera eficiente. Explore la guía paso a paso.
### [Configurando el texto del código DataMatrix](./datamatrix-extended-code-text-configuration/)
Aprenda a configurar el texto extendido del código DataMatrix usando Aspose.BarCode para .NET. Genere, reconozca e integre códigos de barras en sus aplicaciones .NET.
### [Dominar la configuración macro de DataMatrix](./datamatrix-macro-configuration/)
Aprenda a configurar códigos de barras DataMatrix Macro con Aspose.BarCode para .NET. Genere, personalice y reconozca códigos de barras DataMatrix en sus aplicaciones .NET.

## Preguntas frecuentes

**Q:** ¿Cómo decido qué modo ECC usar?  
**A:** Elija ECC 000‑140 para conjuntos de datos pequeños con corrección de errores limitada, o ECC 200 para datos más grandes y mayor fiabilidad. El modo macro agrega una capa de datos adicional para enlazar.

**Q:** ¿Puedo incrustar texto personalizado en un código de barras DataMatrix?  
**A:** Sí, establezca la propiedad `CodeText` a su cadena personalizada, luego seleccione el modo de codificación apropiado (ASCII, C40, etc.) para controlar el tamaño.

**Q:** ¿Existe una forma de seleccionar automáticamente el mejor modo de codificación?  
**A:** Establezca `EncodeMode` a `Auto`; Aspose.BarCode evalúa la carga útil y elige automáticamente el modo más eficiente en espacio.

**Q:** ¿Cuáles son las consideraciones de rendimiento para lotes grandes de códigos de barras?  
**A:** Reutilice una única instancia de `BarCodeGenerator`, habilite la multihilo y genere imágenes PNG para calidad sin pérdida o JPEG para un tamaño de archivo menor. Procesar 10 000 símbolos típicamente se completa en menos de 30 segundos en un servidor estándar de 8 núcleos.

**Q:** ¿Aspose.BarCode soporta .NET Core y .NET 5/6?  
**A:** Absolutamente – la biblioteca es totalmente compatible con .NET Framework, .NET Core y las últimas versiones de .NET, ofreciendo el mismo conjunto de funciones en todas las plataformas.

**Última actualización:** 2026-06-09  
**Probado con:** Aspose.BarCode 24.12 for .NET  
**Autor:** Aspose

## Tutoriales relacionados

- [Cómo generar códigos de barras DataMatrix (ECC 200) con Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Dominar la codificación DataMatrix en ASCII con Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Crear PNG de código de barras – Relación de aspecto DataMatrix – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}