---
date: 2026-09-28
description: Aprenda cómo crear un código de matriz 2D con Aspose.BarCode for .NET
  – una guía paso a paso para generar códigos DotCode con texto de código extendido.
keywords:
- create 2d matrix barcode
- how to generate dotcode
- dotcode extended codetext
lastmod: 2026-09-28
linktitle: Configuración del Texto de Código Extendido de DotCode
og_description: Aprenda a crear un código de matriz 2D usando Aspose.BarCode for .NET.
  Esta guía muestra paso a paso cómo generar códigos DotCode con texto de código extendido.
og_image_alt: Guide showing how to create a 2d matrix DotCode barcode with extended
  codetext in .NET
og_title: Crear código de matriz 2D con Aspose.BarCode for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create 2d matrix barcode with Aspose.BarCode for .NET
    – a step‑by‑step guide for generating DotCode barcodes with extended code text.
  headline: How to create 2d matrix barcode via Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. The PNG image produced by the generator can be embedded in iOS, Android,
      or any cross‑platform mobile application.
    question: Can I use the generated barcode in a mobile app?
  - answer: Use the `AddECICodetext` method with the appropriate `ECIEncodings` (e.g.,
      `ECIEncodings.Base64`) to embed binary payloads.
    question: What if I need to encode binary data instead of text?
  - answer: Adjust the `XDimension.Pixels` property; higher values increase module
      size, while lower values make the barcode more compact.
    question: How do I change the barcode size without affecting readability?
  - answer: Yes. Set `gen.Parameters.Barcode.Margin` to define the desired quiet zone
      in pixels.
    question: Is there a way to add a quiet zone around the barcode?
  - answer: The latest Aspose.BarCode releases are compatible with .NET 8; just reference
      the appropriate NuGet package version.
    question: Does the library support .NET 8?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- dotcode
- Aspose.BarCode
- .NET barcode generation
- 2d matrix barcode
title: Cómo crear un código de matriz 2D mediante Aspose.BarCode for .NET
url: /es/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un código de barras matricial 2d mediante Aspose.BarCode para .NET

## Introducción

En el ámbito de la generación y gestión de códigos de barras, Aspose.BarCode para .NET se destaca como una solución versátil que admite **más de 50 formatos de entrada y salida** y puede procesar documentos de cientos de páginas sin cargar todo el archivo en memoria. Ya sea que necesite códigos de barras para el seguimiento de productos, control de inventario o aplicaciones con datos ricos, crear un **código de barras matricial 2d** como DotCode con codetext extendido le permite incrustar tanto carga útil textual como binaria en un símbolo cuadrado compacto. Este tutorial le guía paso a paso en la construcción de ese codetext extendido y en la renderización de la imagen final.

## Respuestas rápidas
- **¿Qué significa “crear codetext extendido de dotcode”?** Significa construir un código de barras DotCode que incluya FNC1, ECICodetext, texto plano y separadores de símbolo en una única carga útil extendida.  
- **¿Qué biblioteca se requiere?** Aspose.BarCode para .NET.  
- **¿Necesito una licencia?** Una licencia temporal funciona para evaluación; se requiere una licencia completa para producción.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10‑15 minutos para un ejemplo básico.

## Cómo crear codetext extendido de dotcode

Cargue su proyecto, establezca el directorio, construya el codetext extendido y genere la imagen, todo en menos de una docena de líneas de código. La siguiente respuesta directa resume todo el proceso:

Cargue el `BarcodeGenerator` con `EncodeTypes.DotCode`, construya el codetext extendido usando `DotCodeExtendedCodetextBuilder` (agregando FNC1, ECICodetext, texto plano y separadores FNC3), luego llame a `Save` para escribir un archivo PNG. Esta secuencia crea un código de barras matricial 2d totalmente conforme en una sola llamada.

## ¿Qué es el codetext extendido de dotcode?

El **codetext extendido de dotcode** es una cadena compuesta que combina varios segmentos de datos —como identificadores FNC1, ECICodetext, texto plano y separadores FNC3— en una única carga útil que DotCode puede decodificar. Permite codificar texto multilingüe, blobs binarios y datos estructurados dentro de un solo código de barras matricial 2d, lo que lo hace ideal para cadenas de suministro, atención sanitaria y escenarios IoT.

## ¿Por qué usar Aspose.BarCode para esta tarea?

Aspose.BarCode procesa **hasta 500 páginas por segundo** en hardware de servidor típico y admite **más de 30 simbologías de códigos de barras**, incluido DotCode. Su API `GetExtendedCodetext` garantiza la colocación correcta de los caracteres de control, eliminando errores de concatenación manual de cadenas y asegurando el cumplimiento de la norma ISO/IEC 24724. Además, ofrece corrección de errores incorporada y manejo automático de la zona silenciosa, reduciendo la necesidad de ajustes manuales.

## Requisitos previos

- **Aspose.BarCode para .NET** – descárguelo de la [documentación de Aspose.BarCode para .NET](https://reference.aspose.com/barcode/net/).  
- Un entorno de desarrollo .NET (se recomienda Visual Studio 2022 o posterior).  
- Opcional: un archivo de licencia temporal para evaluación.

## Importar espacios de nombres

`using Aspose.BarCode.Generation;`  
`using Aspose.BarCode.ComplexBarcodes;`  

Estos espacios de nombres exponen la clase `BarcodeGenerator` y el asistente `DotCodeExtendedCodetextBuilder` necesarios para el ejemplo.

```csharp
using Aspose.BarCode.Generation;
```

Ahora que hemos cubierto los requisitos previos, desglosaremos el proceso de generación del DotCode Extended Code Text en una guía paso a paso.

## Paso 1: definir la ruta del directorio

Especifique dónde se guardará el PNG generado. Use una ruta absoluta o relativa a la que su aplicación pueda escribir.

```csharp
string path = "Your Directory Path";
```

Reemplace `"Your Directory Path"` con la ruta real en su sistema.

## Paso 2: crear codetext extendido de dotcode

La clase `DotCodeExtendedCodetextBuilder` ensambla los diversos segmentos en una única cadena de codetext extendido.

Para crear el DotCode Extended Code Text, siga estos sub‑pasos:

### 2.1 agregar identificador de formato fnc1

El identificador de formato FNC1 marca el inicio de un nuevo campo de datos. Es necesario para símbolos DotCode compatibles con GS1.

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 agregar ecicodetext

El ECICodetext codifica caracteres especiales y texto internacional. En este ejemplo codificamos `"犬Right狗"` usando UTF‑8.

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 agregar codetext plano

También puede agregar texto plano al DotCode Extended Code Text. Aquí, añadimos `"Plain text"`.

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 agregar separador de símbolo fnc3

El separador de símbolo FNC3 separa diferentes secciones del código, mejorando la legibilidad para los escáneres.

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 agregar inicialización del lector fnc3

Este paso agrega la información de Inicialización del Lector FNC3, que indica al escáner cómo interpretar los datos siguientes.

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 generar codetext

Ahora genere el DotCode Extended Codetext llamando al método `GetExtendedCodetext` del objeto `textBuilder`.

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## Paso 3: generar imagen dotcode

Renderice la imagen del código de barras a partir del codetext extendido.

#### 3.1 inicializar generador de código de barras

La clase `BarcodeGenerator` es el objeto central de Aspose.BarCode para crear cualquier código de barras. Se instancia con la simbología deseada (`EncodeTypes.DotCode`) y el codetext extendido que acaba de construir.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    // Set the X-dimension for the barcode (adjust as needed).
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    // Set the DotCode encoding mode to ExtendedCodetext.
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    // Save the generated barcode image.
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Finalmente, llame a `Save` para escribir el archivo PNG en disco. La imagen está lista para incrustarse en informes, aplicaciones móviles o etiquetas impresas.

## Problemas comunes y soluciones

- **Codificación incorrecta** – Asegúrese de usar `ECIEncodings.UTF8` al agregar texto multilingüe; de lo contrario, los caracteres pueden aparecer distorsionados.  
- **Errores de acceso a archivos** – Verifique que la aplicación tenga permisos de escritura en el directorio de destino.  
- **Zona silenciosa ausente** – Configure `gen.Parameters.Barcode.Margin` si los escáneres requieren espacio blanco adicional alrededor del símbolo.

## Preguntas frecuentes

**P: ¿Puedo usar el código de barras generado en una aplicación móvil?**  
R: Sí. La imagen PNG producida por el generador puede incrustarse en iOS, Android o cualquier aplicación móvil multiplataforma.

**P: ¿Qué pasa si necesito codificar datos binarios en lugar de texto?**  
R: Use el método `AddECICodetext` con el `ECIEncodings` apropiado (por ejemplo, `ECIEncodings.Base64`) para incrustar cargas binarias.

**P: ¿Cómo cambio el tamaño del código de barras sin afectar la legibilidad?**  
R: Ajuste la propiedad `XDimension.Pixels`; valores mayores aumentan el tamaño del módulo, mientras que valores menores hacen el código más compacto.

**P: ¿Hay una forma de agregar una zona silenciosa alrededor del código de barras?**  
R: Sí. Establezca `gen.Parameters.Barcode.Margin` para definir la zona silenciosa deseada en píxeles.

**P: ¿La biblioteca es compatible con .NET 8?**  
R: Las versiones más recientes de Aspose.BarCode son compatibles con .NET 8; solo hay que referenciar la versión adecuada del paquete NuGet.

Si necesita más orientación o tiene preguntas, no dude en visitar la [documentación de Aspose.BarCode para .NET](https://reference.aspose.com/barcode/net/) o participar en la comunidad del [foro de soporte de Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**Last Updated:** 2026-09-28  
**Tested With:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose

## Tutoriales relacionados

- [Crear código de barras DotCode .NET (Modo automático) con Aspose.BarCode](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)
- [Cómo generar códigos de barras DataMatrix usando Aspose.BarCode para .NET – Guía paso a paso](/barcode/net/datamatrix-barcode-configuration/)
- [Cómo crear código de barras Aztec con Aspose.BarCode para .NET](/barcode/net/aztec-barcode-encoding/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}