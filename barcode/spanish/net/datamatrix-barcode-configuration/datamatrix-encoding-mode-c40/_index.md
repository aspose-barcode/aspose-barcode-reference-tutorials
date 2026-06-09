---
date: 2026-06-09
description: Aprenda cómo generar códigos de barras DataMatrix y guardar PNG usando
  la codificación C40 con Aspose.BarCode – guía completa para la generación de códigos
  de barras en .NET Core.
keywords:
- how to generate datamatrix
- barcode generation .net core
- datamatrix c40 png
linktitle: Modo de codificación DataMatrix (C40)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  headline: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  type: TechArticle
- description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  name: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  steps:
  - name: Define the Directory Path
    text: Set the folder where the PNG image will be stored. Replace the placeholder
      with an actual path on your machine.
  - name: Set Up Barcode Generation
    text: Create a `BarcodeGenerator` instance, specify `EncodeTypes.DataMatrix`,
      and provide the data you want to encode.
  - name: Customize Barcode
    text: Configure the X‑dimension (pixel width of the modules) and switch the encoding
      mode to C40.
  - name: Save the Barcode Image
    text: Finally, save the generated barcode as a PNG file. This is the concrete
      answer to **how to save png** with Aspose.BarCode. When you run the program,
      you’ll find `DataMatrixEncodeModeC40.png` in the folder you specified, ready
      to be used in reports, labels, or web pages.
  type: HowTo
- questions:
  - answer: C40 is a compact alphanumeric encoding scheme for DataMatrix symbols,
      ideal for text that includes letters, numbers, and a limited set of special
      characters.
    question: What is DataMatrix Encoding Mode (C40)?
  - answer: You can find the documentation [here](https://reference.aspose.com/barcode/net/).
      It provides detailed guidance on all barcode types and encoding options.
    question: Where can I find the Aspose.BarCode for .NET documentation?
  - answer: Yes, the library supports a wide range of .NET versions, from .NET Framework
      4.5+ to .NET 6 and later.
    question: Is Aspose.BarCode for .NET compatible with all .NET versions?
  - answer: Yes, you can explore a free trial of Aspose.BarCode for .NET by visiting
      [this link](https://releases.aspose.com/). It allows you to test the library’s
      features and capabilities.
    question: Can I try Aspose.BarCode for .NET before purchasing?
  - answer: You can find a supportive community and access support for Aspose.BarCode
      for .NET on the [Aspose forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Cómo generar PNG de DataMatrix con C40 usando Aspose.BarCode
url: /es/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Modo de codificación Master DataMatrix (C40) con Aspose.BarCode para .NET

## Introducción

En este tutorial aprenderás **cómo generar datamatrix** códigos de barras y guardarlos como archivos PNG usando el modo de codificación C40 con Aspose.BarCode para .NET. Ya sea que estés construyendo un sistema de inventario, un generador de etiquetas de envío o cualquier solución que requiera símbolos compactos y de alta densidad, dominar C40 te brinda símbolos más pequeños sin sacrificar la legibilidad. Recorreremos cada paso—desde configurar el entorno hasta producir el PNG final—para que puedas integrar el código instantáneamente en tu proyecto.

## Respuestas rápidas
- **¿A qué se refiere “how to generate datamatrix”?** Creación programática de una imagen de código de barras DataMatrix.  
- **¿Qué modo de codificación se cubre?** DataMatrix C40, un esquema alfanumérico eficiente.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para pruebas; se requiere una licencia comercial para producción.  
- **¿Puedo ejecutar esto en .NET Core?** Sí, Aspose.BarCode soporta completamente .NET Core, .NET 5, .NET 6 y versiones posteriores.  
- **¿Qué formato de archivo se produce?** PNG – un formato de imagen sin pérdida y amigable para la web.

## Cómo generar DataMatrix con codificación C40

Carga tus datos, configura el generador y llama a `Save`; ese es el flujo completo en tres pasos concisos. La clase `BarcodeGenerator` maneja la creación del símbolo, mientras que el enumerado `BarCodeImageFormat.Png` indica a Aspose.BarCode que escriba el resultado como un archivo PNG. `Save` escribe la imagen del código de barras generado en la ruta de archivo especificada en el formato elegido. Este párrafo de respuesta directa te brinda la solución de extremo a extremo antes de profundizar en cada línea de código.

## ¿Qué es el modo de codificación DataMatrix (C40)?

`DataMatrixEncodeMode` es una enumeración que especifica qué esquema de codificación debe usar Aspose.BarCode para los símbolos DataMatrix. La opción `DataMatrixEncodeMode.C40` selecciona la codificación alfanumérica C40, que empaqueta letras, dígitos y un conjunto limitado de puntuación en menos módulos, reduciendo el tamaño total del símbolo mientras mantiene la legibilidad para textos típicos de inventario. Este esquema eficiente es ideal cuando necesitas codificar datos alfanuméricos de forma compacta.

## ¿Por qué usar Aspose.BarCode para .NET?

Aspose.BarCode ofrece **más de 30 parámetros configurables** para dimensiones, niveles de corrección de errores y modos de codificación, y soporta **más de 50 formatos de imagen y código de barras**. La biblioteca funciona en **.NET Framework 4.5+, .NET Core 2.0+, .NET 5/6+**, proporcionando generación sin dependencias que opera en servidores, escritorios y dispositivos móviles por igual.

## Requisitos previos

Antes de sumergirnos en el código, asegúrate de contar con lo siguiente:

1. **Entorno de desarrollo .NET** – Visual Studio, Rider o cualquier IDE que soporte C#.  
2. **Aspose.BarCode para .NET** – instalado vía NuGet o el instalador oficial. Consulta la [documentación](https://reference.aspose.com/barcode/net/) para más detalles.  
3. **Conocimientos básicos de C#** – deberías estar cómodo con namespaces, clases y sentencias using.  
4. **Carpeta con permiso de escritura** – un directorio en tu máquina donde se guardará el PNG.

## Importando los espacios de nombres necesarios

La clase `BarcodeGenerator` es el punto de entrada para crear cualquier código de barras. Añade el espacio de nombres requerido al inicio de tu archivo fuente C# para poder acceder a la API de generación:

```csharp
using Aspose.BarCode.Generation;
```

## Generación de códigos de barras paso a paso

A continuación se muestra una guía **paso a paso** del código de barras. Cada paso se explica en lenguaje sencillo, y los marcadores originales se mantienen sin cambios para facilitar la copia y pegado.

### Paso 1: Definir la ruta del directorio
Establece la carpeta donde se almacenará la imagen PNG. Reemplaza el marcador de posición con una ruta real en tu máquina.

```csharp
string path = "Your Directory Path";
```

### Paso 2: Configurar la generación del código de barras
Crea una instancia de `BarcodeGenerator`, especifica `EncodeTypes.DataMatrix` y proporciona los datos que deseas codificar.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE.BARCODE"))
{
    // Additional steps go here
}
```

### Paso 3: Personalizar el código de barras
Configura la X‑dimension (ancho en píxeles de los módulos) y cambia el modo de codificación a C40.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 6;
gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.C40;
```

### Paso 4: Guardar la imagen del código de barras
Finalmente, guarda el código de barras generado como un archivo PNG. Esta es la respuesta concreta a **cómo guardar png** con Aspose.BarCode.

```csharp
gen.Save($"{path}DataMatrixEncodeModeC40.png", BarCodeImageFormat.Png);
```

Al ejecutar el programa, encontrarás `DataMatrixEncodeModeC40.png` en la carpeta que especificaste, listo para usarse en informes, etiquetas o páginas web.

## Problemas comunes y consejos

- **Ruta inválida** – Asegúrese de que el directorio exista y tenga permisos de escritura; de lo contrario `gen.Save` lanzará una excepción.  
- **Modo de codificación incorrecto** – Si necesita codificar caracteres fuera del conjunto C40, cambie a `DataMatrixEncodeMode.Auto` u otro modo apropiado.  
- **Tamaño de la imagen** – Ajuste `XDimension.Pixels` para aumentar o disminuir el tamaño total del código de barras sin afectar la legibilidad.

## Preguntas frecuentes

**P: ¿Qué es el modo de codificación DataMatrix (C40)?**  
R: C40 es un esquema de codificación alfanumérico compacto para símbolos DataMatrix, ideal para texto que incluye letras, números y un conjunto limitado de caracteres especiales.

**P: ¿Dónde puedo encontrar la documentación de Aspose.BarCode para .NET?**  
R: Puede encontrar la documentación [aquí](https://reference.aspose.com/barcode/net/). Proporciona una guía detallada sobre todos los tipos de códigos de barras y opciones de codificación.

**P: ¿Es Aspose.BarCode para .NET compatible con todas las versiones de .NET?**  
R: Sí, la biblioteca soporta una amplia gama de versiones de .NET, desde .NET Framework 4.5+ hasta .NET 6 y posteriores.

**P: ¿Puedo probar Aspose.BarCode para .NET antes de comprar?**  
R: Sí, puede explorar una prueba gratuita de Aspose.BarCode para .NET visitando [este enlace](https://releases.aspose.com/). Le permite probar las funciones y capacidades de la biblioteca.

**P: ¿Dónde puedo obtener soporte para Aspose.BarCode para .NET?**  
R: Puede encontrar una comunidad de apoyo y acceder al soporte de Aspose.BarCode para .NET en el [foro de Aspose](https://forum.aspose.com/c/barcode/13).

## Conclusión

Siguiendo esta guía **paso a paso**, ahora sabes exactamente **cómo generar datamatrix** códigos de barras y guardarlos como archivos PNG usando el modo de codificación C40 con Aspose.BarCode para .NET. Este enfoque te brinda control total sobre la apariencia, el tamaño y la representación de datos del código de barras, facilitando la inserción de códigos de alta calidad en cualquier aplicación .NET.

---

**Última actualización:** 2026-06-09  
**Probado con:** Aspose.BarCode 24.11 para .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Codificación DataMatrix en bytes con Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [Codificación Master DataMatrix en ASCII con Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Cómo generar códigos de barras DataMatrix (ECC 200) con Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}