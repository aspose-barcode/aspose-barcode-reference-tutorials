---
date: 2026-08-02
description: Guía paso a paso sobre cómo leer código de barras DataMatrix C# y generar
  una imagen de código de barras C# usando Aspose.BarCode for .NET con codificación
  automática.
keywords:
- how to read datamatrix
- read barcode from file
- how to generate datamatrix
- datamatrix encoding auto
lastmod: 2026-08-02
linktitle: Modo de codificación DataMatrix (Automático)
og_description: Aprende a leer código de barras DataMatrix C# y generarlo en modo
  automático usando Aspose.BarCode for .NET. Este tutorial cubre la configuración,
  el código y la solución de problemas.
og_image_alt: 'Guide: Read and generate DataMatrix barcode in C# with Aspose.BarCode'
og_title: Cómo leer código de barras DataMatrix C# – Modo automático
schemas:
- author: Aspose
  dateModified: '2026-08-02'
  description: Step‑by‑step guide on how to read DataMatrix barcode C# and generate
    barcode image C# using Aspose.BarCode for .NET with auto encoding.
  headline: How to read DataMatrix barcode C# – Auto mode
  type: TechArticle
- questions:
  - answer: It allows Aspose.BarCode to automatically select the optimal encoding
      method for the provided data, simplifying the **how to generate datamatrix**
      process.
    question: What is DataMatrix encoding mode "Auto"?
  - answer: Yes – adjust `generator.Parameters.Barcode.XDimension.Pixels` to change
      module size.
    question: Can I customize the dimensions of the generated barcode?
  - answer: Absolutely. Purchase a license from the [website](https://purchase.aspose.com/buy).
    question: Is Aspose.BarCode for .NET suitable for commercial use?
  - answer: Yes, you can explore Aspose.BarCode with a free trial from [this link](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Aspose.BarCode supports UTF‑8, ASCII, and other ECI encodings; set the
      desired value via `ECIEncoding`.
    question: What encoding options are available for DataMatrix barcodes?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- C# barcode generation
title: Cómo leer código de barras DataMatrix C# – Modo automático
url: /es/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo leer DataMatrix barcode C# – Modo Auto

En el mundo digital de hoy, que avanza rápidamente, **cómo leer datamatrix** de forma rápida y fiable es esencial para el seguimiento de inventario, la gestión segura de documentos y muchos otros escenarios empresariales. Este tutorial le guía a través de la generación de un código de barras DataMatrix en modo *Auto* con Aspose.BarCode para .NET y luego muestra cómo leer ese código de barras nuevamente en C#. Ya sea que esté siguiendo una guía de tutorial de códigos de barras o necesite un ejemplo de código listo para usar, terminará con una solución lista para producción que puede incorporar en cualquier proyecto .NET.

## Respuestas rápidas
- **¿Qué hace el modo “Auto”?** Permite que Aspose.BarCode seleccione automáticamente el mejor esquema de codificación para sus datos.  
- **¿Qué biblioteca se requiere?** Aspose.BarCode para .NET (prueba gratuita disponible).  
- **¿Puedo leer el código de barras en la misma aplicación?** Sí – use `BarCodeReader` con `DecodeType.DataMatrix`.  
- **¿Necesito una licencia para producción?** Se requiere una licencia comercial para uso en producción.  
- **¿Versiones .NET compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  

`BarCodeReader` es la clase de Aspose.BarCode para escanear imágenes y obtener información del código de barras.

## ¿Qué es leer un código de barras DataMatrix en C#?
Leer un código de barras DataMatrix en C# significa decodificar la matriz bidimensional de módulos negros y blancos de nuevo al texto o datos originales. Aspose.BarCode abstrae el procesamiento de imágenes de bajo nivel, por lo que puede centrarse en la lógica de negocio mientras la biblioteca maneja la corrección de errores, la selección del tamaño del símbolo y el soporte Unicode automáticamente.

## ¿Por qué usar Aspose.BarCode para generar una imagen de código de barras C#?
Aspose.BarCode selecciona automáticamente la codificación óptima, admite **más de 30 simbologías de códigos de barras**, y puede generar símbolos DataMatrix de hasta **1558 × 1558 módulos**, mucho más grande que la mayoría de los competidores. Funciona en Windows, Linux y macOS sin dependencias nativas, ofreciéndole una única API multiplataforma tanto para la generación como para la lectura.

## Requisitos previos

1. **Entorno .NET** – Instale la última versión del runtime .NET desde el [.NET website](https://dotnet.microsoft.com/download/dotnet).  
2. **Aspose.BarCode para .NET** – Descargue la biblioteca desde el [website](https://releases.aspose.com/barcode/net/).  

## Importando espacios de nombres
El espacio de nombres `Aspose.BarCode` contiene todas las clases que necesita para la creación y lectura de códigos de barras. Impórtelo al inicio de su archivo antes de cualquier otro código.

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

Ahora que los espacios de nombres están en su lugar, recorramos el código paso a paso.

## Paso 1: Establecer la ruta del directorio
Elija una carpeta donde se guardará el PNG generado (o cualquier formato compatible). Esta ruta puede ser absoluta o relativa a su proyecto.

```csharp
string path = "Your Directory Path";
```

Reemplace `"Your Directory Path"` por la carpeta que prefiera. Mantener la carpeta de salida configurable hace que el tutorial sea reutilizable en diferentes entornos.

## Paso 2: Crear un código de barras DataMatrix en modo Auto
`DataMatrixEncodeMode.Auto` indica al generador que seleccione automáticamente el esquema de codificación óptimo para los datos suministrados.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose常に先を行く"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Auto;
    generator.Parameters.Barcode.DataMatrix.ECIEncoding = ECIEncodings.UTF8;
    Bitmap bitmap = generator.GenerateBarCodeImage();
}
```

Siéntase libre de reemplazar el texto de ejemplo con cualquier cadena que necesite **para generar datamatrix**. El modo auto cambiará automáticamente entre Base‑256, ASCII u otros esquemas para lograr el símbolo más pequeño posible.

## Paso 3: Leer el código de barras (leer código de barras DataMatrix C#)
`BarCodeReader` es la clase de Aspose.BarCode para escanear imágenes y obtener información del código de barras. Soporta la lectura desde streams, archivos y objetos bitmap, lo que lo hace ideal para escenarios de **leer código de barras desde archivo**.

```csharp
using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
{
    reader.ReadBarCodes();
    Console.WriteLine(reader.FoundBarCodes[0].CodeText);
}
```

Este fragmento decodifica la imagen que acabamos de generar e imprime el texto original en la consola, demostrando un ciclo completo desde la generación hasta la lectura.

## Problemas comunes y soluciones

| Problema | Causa | Solución |
|----------|-------|----------|
| **No se detectó el código de barras** | Resolución de la imagen demasiado baja | Aumente `XDimension.Pixels` (p.ej., a 6) |
| **Caracteres basura** | Codificación ECI incorrecta | Establezca `ECIEncoding` para que coincida con sus datos (UTF‑8, ASCII, etc.) |
| **Excepción en `ReadBarCodes`** | Bitmap eliminado antes de la lectura | Mantenga la instancia `Bitmap` viva hasta después de la lectura |

## Preguntas frecuentes

**P: ¿Qué es el modo de codificación DataMatrix "Auto"?**  
R: Permite que Aspose.BarCode seleccione automáticamente el método de codificación óptimo para los datos proporcionados, simplificando el proceso de **cómo generar datamatrix**.

**P: ¿Puedo personalizar las dimensiones del código de barras generado?**  
R: Sí – ajuste `generator.Parameters.Barcode.XDimension.Pixels` para cambiar el tamaño del módulo.

**P: ¿Es Aspose.BarCode para .NET adecuado para uso comercial?**  
R: Absolutamente. Adquiera una licencia desde el [website](https://purchase.aspose.com/buy).

**P: ¿Hay una prueba gratuita disponible?**  
R: Sí, puede explorar Aspose.BarCode con una prueba gratuita desde [este enlace](https://releases.aspose.com/).

**P: ¿Qué opciones de codificación están disponibles para los códigos de barras DataMatrix?**  
R: Aspose.BarCode admite UTF‑8, ASCII y otras codificaciones ECI; establezca el valor deseado mediante `ECIEncoding`.

## Conclusión

Ahora tiene un ejemplo completo y listo para producción que **lee códigos de barras DataMatrix C#**, genera el código de barras en modo Auto y verifica el resultado, todo usando Aspose.BarCode para .NET. Experimente con diferentes textos, tamaños y configuraciones ECI para adaptarse a su escenario específico, y consulte la [documentación](https://reference.aspose.com/barcode/net/) oficial para una personalización más profunda.

---

**Última actualización:** 2026-08-02  
**Probado con:** Aspose.BarCode 24.12 para .NET  
**Autor:** Aspose

## Tutoriales relacionados

- [Cómo leer códigos de barras DataMatrix con Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-reading/)
- [Configuración de Structured Append de DataMatrix con Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)
- [Programación del lector DataMatrix con Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-reader-programming/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}