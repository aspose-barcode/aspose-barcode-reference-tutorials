---
date: 2026-05-24
description: Aprenda cómo crear códigos de barras Aztec .NET usando Aspose.BarCode
  para .NET, cubriendo los modos de símbolo Auto, FullRange, Compact y Rune con una
  guía paso a paso.
keywords:
- create aztec barcode .net
- aztec symbol mode
- aspose barcode .net
linktitle: Ejemplo de modo de símbolo Aztec
schemas:
- author: Aspose
  dateModified: '2026-05-24'
  description: Learn how to create aztec barcode .net using Aspose.BarCode for .NET,
    covering Auto, FullRange, Compact, and Rune symbol modes with step‑by‑step guidance.
  headline: Create Aztec Barcode .NET with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Aztec Symbol Mode determines how the library packs data into layers, affecting
      size, capacity, and readability.
    question: What is the purpose of Aztec Symbol Mode in barcode generation?
  - answer: Yes, simply assign a new string to the `CodeText` property before calling
      `Save`.
    question: Can I change the code text for Aztec barcodes in Aspose.BarCode for
      .NET?
  - answer: Yes, you can download a free trial version of Aspose.BarCode for .NET
      [here](https://releases.aspose.com/).
    question: Is there a free trial version of Aspose.BarCode for .NET available?
  - answer: You can refer to the complete documentation for Aspose.BarCode for .NET
      [here](https://reference.aspose.com/barcode/net/).
    question: Where can I find the full documentation for Aspose.BarCode for .NET?
  - answer: You can acquire a temporary license for Aspose.BarCode for .NET by visiting
      [this link](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Crear código de barras Aztec .NET con Aspose.BarCode
url: /es/net/aztec-barcode-encoding/aztec-symbol-mode-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dominar el modo de símbolo Aztec con Aspose.BarCode para .NET

Si buscas **create aztec barcode .net** de forma rápida y fiable, Aspose.BarCode para .NET te ofrece una API completa que funciona en .NET Framework, .NET Core y .NET 5/6+. En este tutorial exploraremos los cuatro modos de símbolo Aztec —Auto, FullRange, Compact y Rune— mostrándote exactamente cómo cambiar entre ellos y guardar el resultado como una imagen. Al final podrás incrustar códigos de barras Aztec en cualquier aplicación .NET con solo unas pocas líneas de código.

## Respuestas rápidas
- **¿Qué biblioteca genera códigos de barras Aztec en .NET?** Aspose.BarCode for .NET.  
- **¿Cuántos modos de símbolo admite Aztec?** Cuatro: Auto, FullRange, Compact y Rune.  
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita sirve para evaluación; se requiere una licencia comercial para producción.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ y .NET 6+.  
- **¿Puedo generar PNG, JPEG o SVG?** Sí, se admite cualquier formato de imagen estándar.

## ¿Qué es create aztec barcode .net?
`create aztec barcode .net` se refiere al proceso de generar un código de barras bidimensional Aztec usando la API Aspose.BarCode en un entorno .NET. La API maneja la codificación, la selección del modo de símbolo y el renderizado de la imagen automáticamente, permitiendo a los desarrolladores producir códigos de alta calidad sin ocuparse de detalles de bajo nivel como cálculos de corrección de errores o manipulación de píxeles.

## ¿Por qué usar Aspose.BarCode para códigos de barras Aztec?
Aspose.BarCode soporta **30+ simbologías de códigos de barras** y puede renderizar imágenes de hasta **10,000 × 10,000 px** sin cargar todo el archivo en memoria. Procesa un documento de 500 páginas en menos de **2 segundos** en un servidor típico, lo que lo hace ideal para escenarios empresariales de alto rendimiento.

## Requisitos previos

Antes de comenzar, asegúrate de contar con los siguientes requisitos:

- Un conocimiento práctico del desarrollo .NET.  
- Visual Studio instalado en su máquina.  
- Una copia de Aspose.BarCode para .NET. Puede descargarla [aquí](https://releases.aspose.com/barcode/net/). También puede explorar otros productos Aspose [aquí](https://releases.aspose.com/).

Ahora que todo está listo, sumérgete en los ejemplos de modo de símbolo Aztec.

## Importando espacios de nombres

Primero, necesitarás importar los espacios de nombres necesarios para trabajar con Aspose.BarCode para .NET. Abre tu proyecto en Visual Studio y agrega las siguientes sentencias using al inicio de tu archivo de código:

```csharp
using Aspose.BarCode.Generation;
```

Con los espacios de nombres en su lugar, ya puedes comenzar a usar Aspose.BarCode para .NET.

## ¿Cómo configuro el generador de códigos de barras para códigos Aztec?

La clase `BarcodeGenerator` es el componente central que crea imágenes de códigos de barras basándose en la simbología y las opciones de configuración seleccionadas. Proporciona una API sencilla para especificar el tipo de código de barras, los datos a codificar y varios parámetros de renderizado antes de guardar el resultado en un archivo de imagen.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecSymbolModeExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

En este paso, hemos configurado el generador y proporcionado el texto del código para la codificación.

## ¿Cómo establecer el modo de símbolo Aztec a Auto?

La enumeración `AztecSymbolMode` define los cuatro modos de símbolo posibles para los códigos Aztec, y la opción **Auto** permite que la biblioteca elija automáticamente el tamaño más compacto mientras preserva todos los requisitos de datos y corrección de errores. Este modo es ideal para la mayoría de los escenarios donde se desea el código de barras más pequeño posible sin ajustes manuales.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Auto;
gen.Save($"{path}AztecSymbolModeAuto.png", BarCodeImageFormat.Png);
```

Este paso asegura que el modo de símbolo Aztec se determine automáticamente y que la imagen resultante del código de barras se guarde.

## ¿Cómo forzar el modo de símbolo FullRange?

Cuando necesitas la máxima capacidad de datos, puedes seleccionar el valor **FullRange** de la enumeración `AztecSymbolMode`. Este modo desactiva la reducción automática de tamaño, permitiendo que el código de barras almacene todo el rango de caracteres y logre la mayor densidad de información posible, lo cual es útil para conjuntos de datos extensos.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
gen.Save($"{path}AztecSymbolModeFullRange.png", BarCodeImageFormat.Png);
```

Esto creará un código de barras con el modo de símbolo Aztec FullRange.

## ¿Cómo generar un código Aztec Compacto?

El valor **Compact** de la enumeración `AztecSymbolMode` produce un código de barras más pequeño al reducir el número de capas usadas en la matriz. Esto resulta en una imagen más eficiente en espacio, adecuada para aplicaciones con área de visualización limitada, como pantallas móviles o etiquetas pequeñas.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Compact;
gen.Save($"{path}AztecSymbolModeCompact.png", BarCodeImageFormat.Png);
```

Este paso configura el código de barras para que se genere con el modo de símbolo Aztec Compact.

## ¿Cómo crear un código Aztec Rune?

El modo **Rune** es una variante especializada de la simbología Aztec que codifica datos numéricos usando un conjunto de caracteres personalizado, ofreciendo un estilo visual distinto mientras mantiene la misma fuerza de corrección de errores que los demás modos. Es útil cuando se necesita un código de barras que enfatice la información numérica.

```csharp
gen.CodeText = "123"; // Change the code text if needed
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Rune;
gen.Save($"{path}AztecSymbolModeRune.png", BarCodeImageFormat.Png);
```

Este paso cambia el texto del código a "123" y genera un código de barras con el modo de símbolo Aztec Rune.

## Problemas comunes y soluciones

- **Imagen no se guarda** – Asegúrese de que la carpeta de salida exista y la aplicación tenga permisos de escritura.  
- **Tamaño de símbolo inesperado** – Verifique que no haya sobrescrito `EncodeMode` en otra parte de su código.  
- **Excepción de licencia** – La versión de prueba agrega una marca de agua; aplique una licencia válida para eliminarla.

## Preguntas frecuentes

**P: ¿Cuál es el propósito del modo de símbolo Aztec en la generación de códigos de barras?**  
R: El modo de símbolo Aztec determina cómo la biblioteca empaqueta los datos en capas, afectando el tamaño, la capacidad y la legibilidad.

**P: ¿Puedo cambiar el texto del código para los códigos Aztec en Aspose.BarCode para .NET?**  
R: Sí, simplemente asigna una nueva cadena a la propiedad `CodeText` antes de llamar a `Save`.

**P: ¿Existe una versión de prueba gratuita de Aspose.BarCode para .NET?**  
R: Sí, puedes descargar una versión de prueba gratuita de Aspose.BarCode para .NET [aquí](https://releases.aspose.com/).

**P: ¿Dónde puedo encontrar la documentación completa de Aspose.BarCode para .NET?**  
R: Puedes consultar la documentación completa de Aspose.BarCode para .NET [aquí](https://reference.aspose.com/barcode/net/).

**P: ¿Cómo puedo obtener una licencia temporal para Aspose.BarCode para .NET?**  
R: Puedes adquirir una licencia temporal para Aspose.BarCode para .NET visitando [este enlace](https://purchase.aspose.com/temporary-license/).

## Conclusión

En este tutorial exploramos cómo **create aztec barcode .net** usando Aspose.BarCode, cubriendo los modos de símbolo Auto, FullRange, Compact y Rune. Ahora tienes una base sólida para incrustar códigos de barras Aztec versátiles en cualquier aplicación .NET, ya sea que se ejecute en escritorio, servidor web o servicio en la nube.

Si tienes alguna pregunta o necesitas más ayuda, no dudes en contactar a la comunidad de Aspose.BarCode en su [foro de soporte](https://forum.aspose.com/c/barcode/13).

---

**Última actualización:** 2026-05-24  
**Probado con:** Aspose.BarCode 24.11 para .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Codificación de texto de código Aztec con Aspose.BarCode para .NET](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)
- [Codificación de bytes Aztec usando generador de códigos de barras .net](/barcode/net/aztec-barcode-encoding/aztec-bytes-encoding/)
- [Cómo crear un código Aztec con corrección de errores en .NET](/barcode/net/aztec-barcode-encoding/aztec-error-level-example/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}