---
date: 2026-06-09
description: Aprenda cómo crear un código de barras DataMatrix en modo ASCII usando
  Aspose.BarCode para .NET. Esta guía muestra cómo generar el código de barras en
  C# rápidamente.
keywords:
- create datamatrix barcode
- generate barcode c#
- how to encode barcode
- barcode generator example
linktitle: Modo de codificación DataMatrix (ASCII)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  headline: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  name: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  steps:
  - name: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
    text: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
  - name: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
  - name: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
    text: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
  - name: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
    text: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
  type: HowTo
- questions:
  - answer: Yes, a valid Aspose license is required for production use; a free trial
      is available for evaluation.
    question: Can I use this in a commercial application?
  - answer: Absolutely – Aspose.BarCode fully supports .NET Core 3.1+, .NET 5, .NET
      6, and later versions.
    question: Does the library work with .NET Core?
  - answer: Up to 2,335 alphanumeric characters fit in a single DataMatrix symbol
      when using ASCII encoding.
    question: How many characters can I encode in ASCII mode?
  - answer: Yes, adjust `generator.Parameters.Image.ForeColor` and `BackColor` to
      any `System.Drawing.Color` value.
    question: Can I change the barcode’s foreground or background color?
  - answer: The official documentation contains dozens of samples covering custom
      sizes, colors, and error‑correction levels.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Crear código de barras DataMatrix en modo ASCII con Aspose.BarCode para .NET
url: /es/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear código de barras DataMatrix en modo ASCII con Aspose.BarCode para .NET

## Introducción

¿Listo para **crear imágenes de códigos de barras DataMatrix** que utilicen la eficiente codificación ASCII? En este tutorial aprenderás a generar un código de barras DataMatrix en modo ASCII usando Aspose.BarCode para .NET. Repasaremos cada paso, desde la configuración del proyecto hasta guardar la imagen final, para que puedas añadir generación de códigos de barras a tus aplicaciones C# en minutos.

## Respuestas rápidas
- **¿Qué biblioteca es la mejor para DataMatrix en .NET?** Aspose.BarCode for .NET  
- **¿Cuántas líneas de código se necesitan?** Aproximadamente 5‑7 líneas para un código de barras ASCII básico  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia para producción  
- **¿Plataformas compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **¿Puedo cambiar el tamaño o los colores?** Sí, Aspose.BarCode expone propiedades para dimensiones y colores de primer plano/fondo  

## ¿Qué es el código de barras DataMatrix?
DataMatrix es un código de barras bidimensional que almacena texto y datos binarios en un patrón cuadrado compacto.  
Un código de barras DataMatrix codifica información en una cuadrícula de módulos negros y blancos, permitiendo hasta 2 335 caracteres alfanuméricos en un solo símbolo. Se utiliza ampliamente en la fabricación, la logística y la atención sanitaria porque puede imprimirse en tamaños muy pequeños manteniéndose altamente escaneable.

## Cómo crear un código de barras DataMatrix en modo ASCII
Carga el espacio de nombres Aspose.BarCode, instancia un `BarcodeGenerator`, establece el `EncodeMode` a **EncodeMode.ASCII**, asigna tu cadena de datos y llama a `Save` para escribir el archivo de imagen. Este enfoque produce un código de barras DataMatrix perfectamente conforme con codificación solo ASCII en tan solo unas pocas líneas de código C#.

## ¿Por qué usar codificación ASCII para DataMatrix?
El modo ASCII es la codificación predeterminada y más eficiente para datos de texto plano, ofreciendo el tamaño de símbolo más pequeño posible para cadenas alfanuméricas. Soporta los 128 caracteres ASCII, procesa los datos más rápido que los modos extendidos y garantiza la máxima compatibilidad con escáneres heredados que esperan símbolos ASCII estándar.

## Requisitos previos

1. **Entorno de desarrollo** – Visual Studio, Rider o cualquier IDE compatible con C#.  
2. **Aspose.BarCode para .NET** – Descarga el paquete más reciente desde [aquí](https://releases.aspose.com/barcode/net/).  
   - Documentación: [documentación de Aspose.BarCode para .NET](https://reference.aspose.com/barcode/net/)  
   - Ayuda de la comunidad: [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)  
3. **Conocimientos básicos de C#** – Familiaridad con la estructura de proyectos .NET te ayudará a seguir los pasos rápidamente.  
4. **Otros productos Aspose** pueden encontrarse [aquí](https://releases.aspose.com/).

## Importar espacios de nombres

Para comenzar, agrega las directivas `using` requeridas al inicio de tu archivo C#:

```csharp
using Aspose.BarCode.Generation;
using System.Drawing;
```

Estos espacios de nombres te dan acceso a la clase `BarcodeGenerator` y a los tipos relacionados con imágenes necesarios para guardar la salida.

## Paso 1: Crear un directorio

Elige una carpeta donde se almacenarán las imágenes de códigos de barras generadas. Reemplaza `"Your Directory Path"` con una ruta absoluta o relativa que **exista** en tu máquina.

```csharp
string outputDir = @"C:\Barcodes";
if (!System.IO.Directory.Exists(outputDir))
{
    System.IO.Directory.CreateDirectory(outputDir);
}
```

El código garantiza que el directorio exista antes de intentar escribir cualquier archivo, evitando errores en tiempo de ejecución.

## Paso 2: Codificar datos en modo ASCII

La clase `BarcodeGenerator` crea y configura imágenes de códigos de barras. La enumeración `DataMatrixEncodeMode` selecciona el algoritmo de codificación para los símbolos DataMatrix.

```csharp
// Initialise the generator with the data you want to encode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "1234567890");

// Set the encoding mode to ASCII for optimal size
generator.Parameters.Barcode.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;

// Optional: adjust image dimensions or colors here
generator.Parameters.Image.Width = 200;
generator.Parameters.Image.Height = 200;

// Save the barcode as a PNG file
string filePath = System.IO.Path.Combine(outputDir, "datamatrix_ascii.png");
generator.Save(filePath, BarCodeImageFormat.Png);
```

Después de ejecutar el código, encontrarás `datamatrix_ascii.png` en la carpeta que especificaste. La imagen contiene un código de barras DataMatrix que codifica la cadena `"1234567890"` usando el modo ASCII compacto.

## Problemas comunes y soluciones

- **Errores de acceso a archivos** – Asegúrate de que la aplicación tenga permisos de escritura en la carpeta de destino. Ejecutar Visual Studio como Administrador puede resolver problemas de permisos en Windows.  
- **Tamaño de símbolo incorrecto** – Si el código de barras aparece demasiado grande o pequeño, ajusta `generator.Parameters.Image.Width` y `Height` o permite que Aspose calcule automáticamente el tamaño óptimo omitiendo esas propiedades.  
- **Caracteres no compatibles** – El modo ASCII solo acepta caracteres en el rango 0‑127. Para datos Unicode, cambia a `DataMatrixEncodeMode.Base256` u otro modo adecuado.

## Preguntas frecuentes

**P: ¿Puedo usar esto en una aplicación comercial?**  
R: Sí, se requiere una licencia válida de Aspose para uso en producción; una prueba gratuita está disponible para evaluación.

**P: ¿La biblioteca funciona con .NET Core?**  
R: Absolutamente – Aspose.BarCode soporta completamente .NET Core 3.1+, .NET 5, .NET 6 y versiones posteriores.

**P: ¿Cuántos caracteres puedo codificar en modo ASCII?**  
R: Hasta 2 335 caracteres alfanuméricos caben en un solo símbolo DataMatrix al usar codificación ASCII.

**P: ¿Puedo cambiar el color de primer plano o de fondo del código de barras?**  
R: Sí, ajusta `generator.Parameters.Image.ForeColor` y `BackColor` a cualquier valor de `System.Drawing.Color`.

**P: ¿Dónde puedo encontrar ejemplos más avanzados?**  
R: La documentación oficial contiene docenas de ejemplos que cubren tamaños personalizados, colores y niveles de corrección de errores.

## Preguntas frecuentes

### P1: ¿Puedo usar Aspose.BarCode para .NET con otros lenguajes de programación además de C#?
R1: Aspose.BarCode soporta varios lenguajes de programación, pero este tutorial se centra en C#.

### P2: ¿Cuáles son los diferentes modos de codificación disponibles en los códigos de barras DataMatrix?
R2: Los códigos de barras DataMatrix soportan varios modos de codificación, incluidos ASCII, C40, Text y Base256. Cada modo es adecuado para diferentes tipos de datos.

### P3: ¿Puedo personalizar la apariencia del código de barras generado, como su tamaño y color?
R3: Sí, Aspose.BarCode ofrece una amplia gama de parámetros para personalizar la apariencia del código de barras, incluyendo tamaño, color y más.

### P4: ¿Existe una versión de prueba gratuita de Aspose.BarCode para .NET?
R4: Sí, puedes explorar Aspose.BarCode para .NET con una prueba gratuita desde [aquí](https://releases.aspose.com/).

### P5: ¿Dónde puedo comprar una licencia para Aspose.BarCode para .NET?
R5: Puedes comprar una licencia en el sitio web de Aspose [aquí](https://purchase.aspose.com/buy).

---

**Última actualización:** 2026-06-09  
**Probado con:** Aspose.BarCode 24.11 para .NET  
**Autor:** Aspose

## Tutoriales relacionados

- [Codificación DataMatrix en bytes con Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [Leer código de barras DataMatrix C# – Generar modo DataMatrix (Auto)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Cómo generar códigos de barras DataMatrix (ECC 200) con Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.BarCode.Generation;
```

```csharp
string path = "Your Directory Path";
```

```csharp
System.Console.WriteLine("DataMatrixEncodeModeASCII:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    // Set the X-dimension (size) of the barcode in pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set the encoding mode to ASCII
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;
    
    // Save the barcode as a PNG image
    gen.Save($"{path}DataMatrixEncodeModeASCII.png", BarCodeImageFormat.Png);
}
```

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}