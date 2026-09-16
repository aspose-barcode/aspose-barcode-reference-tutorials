---
date: 2026-05-24
description: Aprenda cómo crear un código de barras Codabar con caracteres de inicio
  y parada usando Aspose.BarCode para .NET. Tutorial paso a paso de generación de
  códigos de barras para desarrolladores.
keywords:
- create codabar barcode
- codabar start stop characters
- aspose barcode example
- barcode generation .net core
linktitle: Caracteres de inicio/parada de Codabar
schemas:
- author: Aspose
  dateModified: '2026-05-24'
  description: Learn how to create codabar barcode with start and stop characters
    using Aspose.BarCode for .NET. Step‑by‑step barcode generation tutorial for developers.
  headline: Create Codabar Barcode with Start/Stop Characters in Aspose.BarCode for
    .NET
  type: TechArticle
- description: Learn how to create codabar barcode with start and stop characters
    using Aspose.BarCode for .NET. Step‑by‑step barcode generation tutorial for developers.
  name: Create Codabar Barcode with Start/Stop Characters in Aspose.BarCode for .NET
  steps:
  - name: Initialize the Barcode Generator
    text: '`BarcodeGenerator` is the core class that creates barcode images. It takes
      the symbology type and the data string as constructor arguments. > **Pro tip:**
      The dash (`-`) is one of the valid start/stop symbols for Codabar. You can also
      use `A`, `B`, `C`, or `D` depending on your application’s require'
  - name: Set the X‑Dimension (barcode element width)
    text: '`XDimension` controls the width of the narrowest bar. Larger values improve
      readability on low‑resolution printers, while smaller values conserve space
      on high‑density labels. > **Why it matters:** Adjusting `XDimension` helps you
      meet scanner specifications that often require a minimum bar width of'
  - name: Define Start and Stop Characters
    text: Codabar supports four start/stop symbols (A, B, C, D). Below are examples
      for each option. Choose the one that matches the specification of the system
      you’re integrating with.
  - name: Save the Generated Barcode Images (PNG)
    text: '`Save` writes the barcode to a file. Using `BarCodeImageFormat.Png` produces
      lossless PNG images that are ideal for web and print use cases. Each file now
      contains a **codabar barcode example** with the corresponding start/stop symbols.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET
    question: What library do I need?
  - answer: PNG (`BarCodeImageFormat.Png`)
    question: Which format can I save the barcode in?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license for development?
  - answer: Yes – use `CodabarSymbol.A`, `B`, `C`, or `D`.
    question: Can I change the start/stop symbols?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Crear código de barras Codabar con caracteres de inicio/parada en Aspose.BarCode
  para .NET
url: /es/net/codabar-encoding-and-checksum/codabar-start-stop-characters/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear código de barras Codabar con caracteres de inicio/parada en Aspose.BarCode para .NET

## Introducción

En este tutorial **creará imágenes de códigos de barras Codabar** que incluyen caracteres de inicio/parada explícitos usando Aspose.BarCode para .NET. Ya sea que esté construyendo un sistema de inventario minorista, un rastreador de muestras de laboratorio o una solución de registros médicos, la simbología numérica de Codabar depende de esos símbolos de límite para garantizar un escaneo fiable. En los próximos minutos cubriremos todo, desde la configuración del entorno hasta guardar archivos PNG, para que pueda comenzar a generar códigos de barras Codabar de inmediato.

## Respuestas rápidas
- **¿Qué biblioteca necesito?** Aspose.BarCode for .NET  
- **¿En qué formato puedo guardar el código de barras?** PNG (`BarCodeImageFormat.Png`)  
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita funciona para pruebas; se requiere una licencia comercial para producción.  
- **¿Puedo cambiar los símbolos de inicio/parada?** Sí – use `CodabarSymbol.A`, `B`, `C`, o `D`.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Qué es Codabar y por qué los caracteres de inicio/parada son esenciales

Codabar es una simbología de código de barras numérico ampliamente utilizada en bibliotecas, atención médica y gestión de inventarios. Los caracteres de inicio y parada (A‑D o guion) definen los límites del código de barras, permitiendo a los escáneres detectar dónde comienzan y terminan los datos con una precisión de lectura del 99,9 %.

## ¿Por qué usar Aspose.BarCode para .NET?

Aspose.BarCode soporta **más de 30 simbologías de códigos de barras** y puede generar imágenes de hasta **10,000 × 10,000 px** sin cargar todo el documento en memoria. Funciona en Windows, Linux y macOS, y es compatible con .NET Framework, .NET Core y .NET 5+, lo que le brinda flexibilidad en todas las plataformas modernas.

## Requisitos previos

1. **Configuración del entorno** – Asegúrese de tener un entorno de desarrollo .NET funcional. Si necesita orientación, consulte la [documentación](https://reference.aspose.com/barcode/net/).  
2. **Biblioteca Aspose.BarCode para .NET** – Descargue e instale la biblioteca desde el [origen](https://releases.aspose.com/barcode/net/).  
3. **Conocimientos básicos de .NET** – Familiaridad con C# y un IDE como Visual Studio, Rider o VS Code.  
4. **IDE** – Visual Studio, Rider o Visual Studio Code son todos adecuados.

Ahora que hemos cubierto los requisitos previos, sumerjámonos en el código real.

## ¿Cómo generar un código de barras Codabar con caracteres de inicio/parada?

Cargue el `BarcodeGenerator`, establezca el tipo de codificación a **Codabar**, y pase una cadena de datos que ya contenga los símbolos de inicio/parada requeridos (por ejemplo, “-12345-”). Luego configure la X‑Dimension, opcionalmente elija un símbolo de inicio/parada diferente, y finalmente guarde la imagen como PNG. Este flujo de extremo a extremo crea un código de barras listo para usar en solo unas pocas líneas de C#.

### Importar espacios de nombres

El `BarcodeGenerator` y los tipos relacionados se encuentran en el espacio de nombres `Aspose.BarCode.Generation`.

```csharp
using Aspose.BarCode.Generation;
```

### Paso 1: Inicializar el generador de códigos de barras

`BarcodeGenerator` es la clase central que crea imágenes de códigos de barras. Toma el tipo de simbología y la cadena de datos como argumentos del constructor.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarStartStop:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

> **Consejo profesional:** El guion (`-`) es uno de los símbolos de inicio/parada válidos para Codabar. También puede usar `A`, `B`, `C` o `D` según los requisitos de su aplicación.

### Paso 2: Establecer la X‑Dimension (ancho del elemento del código de barras)

`XDimension` controla el ancho de la barra más estrecha. Valores mayores mejoran la legibilidad en impresoras de baja resolución, mientras que valores menores conservan espacio en etiquetas de alta densidad.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Por qué es importante:** Ajustar `XDimension` le ayuda a cumplir con las especificaciones del escáner que a menudo requieren un ancho mínimo de barra de 0,25 mm.

### Paso 3: Definir los caracteres de inicio y parada

Codabar soporta cuatro símbolos de inicio/parada (A, B, C, D). A continuación se muestran ejemplos para cada opción. Elija el que coincida con la especificación del sistema con el que está integrando.

#### Configurar Inicio A y Parada A

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.A;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.A;
```

#### Configurar Inicio B y Parada B

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.B;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.B;
```

#### Configurar Inicio C y Parada C

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.C;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.C;
```

#### Configurar Inicio D y Parada D

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.D;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.D;
```

Puede repetir la configuración para cada símbolo que necesite generar; el ejemplo a continuación guarda cuatro imágenes separadas, una para cada par de inicio/parada.

### Paso 4: Guardar las imágenes de códigos de barras generadas (PNG)

`Save` escribe el código de barras en un archivo. Usar `BarCodeImageFormat.Png` produce imágenes PNG sin pérdida que son ideales para casos de uso web e impresión.

```csharp
gen.Save($"{path}CodabarStartAStopA.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartBStopB.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartCStopC.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartDStopD.png", BarCodeImageFormat.Png);
```

Cada archivo ahora contiene un **ejemplo de código de barras codabar** con los símbolos de inicio/parada correspondientes.

## Problemas comunes y solución de problemas

| Síntoma | Causa probable | Solución |
|---------|----------------|----------|
| El código de barras aparece distorsionado | X‑Dimension demasiado bajo para la resolución de la impresora elegida | Aumente `XDimension.Pixels` (p.ej., a 3 o 4) |
| El escáner no puede leer el inicio/parada | Símbolo de inicio/parada incorrecto para el sistema objetivo | Verifique el símbolo requerido (A‑D) y configúrelo en consecuencia |
| El archivo PNG está vacío o corrupto | Ruta de salida inválida o permisos de escritura insuficientes | Asegúrese de que `path` apunte a una carpeta existente y que su aplicación tenga acceso de escritura |

## Preguntas frecuentes

**Q1: ¿Qué es Codabar y por qué son importantes los caracteres de inicio y parada?**  
A: Codabar es una simbología de código de barras numérico utilizada en inventario, bibliotecas y atención médica. Los caracteres de inicio/parada definen los límites del código de barras, asegurando que los escáneres sepan dónde comienza y termina la información.

**Q2: ¿Puedo personalizar la apariencia de los códigos de barras Codabar con Aspose.BarCode para .NET?**  
A: Sí. Además de X‑Dimension, puede cambiar colores, agregar márgenes y exportar a PDF o SVG usando la misma API.

**Q3: ¿Existen limitaciones en los códigos de barras Codabar respecto a la codificación de datos?**  
A: Codabar soporta principalmente datos numéricos (0‑9) más un conjunto limitado de caracteres especiales. No es adecuado para cadenas alfanuméricas completas.

**Q4: ¿Es Aspose.BarCode para .NET adecuado para uso comercial y cómo puedo obtener una licencia?**  
A: Sí, está listo para producción. Compre una licencia en la [página de compra de Aspose](https://purchase.aspose.com/buy).

**Q5: ¿Dónde puedo buscar ayuda o discutir problemas relacionados con Aspose.BarCode para .NET?**  
A: Únase a la comunidad en el [foro de soporte de Aspose.BarCode para .NET](https://forum.aspose.com/c/barcode/13) para obtener asistencia tanto de ingenieros de Aspose como de otros desarrolladores.

**Last Updated:** 2026-05-24  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose

## Tutoriales relacionados

- [Codabar caracteres de inicio/parada y checksum](/barcode/net/codabar-encoding-and-checksum/)
- [Cómo agregar checksum a códigos de barras Codabar usando Aspose.BarCode para .NET](/barcode/net/codabar-encoding-and-checksum/codabar-checksum-calculation/)
- [Tutoriales y ejemplos completos de Aspose.BarCode para .NET](/barcode/net/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}