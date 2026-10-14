---
category: general
date: 2026-10-14
description: Aprenda cómo generar pdf417 con Aspose.BarCode, añada texto personalizado,
  metadatos macro y exporte el resultado como PNG en un tutorial paso a paso de C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- generate barcode aspose
- pdf417 macro metadata
- custom text barcode
- Aspose.BarCode C#
lastmod: 2026-10-14
og_description: Aprenda cómo generar pdf417 con Aspose.BarCode. Esta guía muestra
  paso a paso cómo añadir texto personalizado, metadatos macro y guardar el código
  de barras como una imagen PNG.
og_image_alt: Screenshot of a MacroPdf417 barcode generated with Aspose.BarCode in
  C#
og_title: Cómo generar pdf417 – guía completa de C#
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Learn how to generate pdf417 with Aspose.BarCode, add custom text,
    macro metadata, and export the result as a PNG.
  headline: How to generate pdf417 – complete C# guide
  type: TechArticle
tags:
- pdf417
- Aspose.BarCode
- C# barcode generation
- macro barcode
title: Cómo generar pdf417 – guía completa de C#
url: /es/net/compact-pdf417-encoding/generate-barcode-aspose-complete-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo generar pdf417 – guía completa en C#

Si necesitas **generar pdf417** para un símbolo MacroPdf417, este tutorial te guía a través de todo el proceso. Verás cómo configurar opciones específicas de macro, incrustar texto Unicode personalizado y guardar el código de barras como una imagen PNG. Al final de la guía tendrás un fragmento de C# listo para usar que puedes insertar en cualquier proyecto .NET, ya sea una aplicación de consola, un servicio de Windows o un micro‑servicio en la nube.

## Respuestas rápidas
- **¿Qué biblioteca necesito?** Aspose.BarCode para .NET (soporta más de 70 simbologías).  
- **¿Puedo añadir caracteres Unicode?** Sí – la API soporta completamente cadenas UTF‑8 como `"Åspóse.Barcóde©"`.  
- **¿Necesito una licencia para producción?** Se requiere una licencia válida de Aspose.BarCode para uso ilimitado; una evaluación gratuita sirve para pruebas.  
- **¿Qué versiones de .NET son compatibles?** .NET 6+, .NET 5, .NET Core 3.1 y .NET Framework 4.7+.  
- **¿Es PNG el mejor formato para imprimir?** PNG conserva calidad sin pérdidas y es ideal para impresión de códigos de barras de alta resolución.

## ¿Qué es pdf417?
`PDF417` es un código de barras lineal apilado que puede codificar hasta aproximadamente 1 700 caracteres por símbolo. Se usa ampliamente para boletos de transporte, tarjetas de identificación y seguimiento de inventario porque puede almacenar grandes cantidades de datos en un formato compacto y legible por máquinas.

## ¿Por qué usar Aspose.BarCode para generar pdf417?
Aspose.BarCode soporta **más de 70 simbologías de códigos de barras**, procesa archivos de hasta **2 GB** sin cargar todo el documento en memoria y garantiza **100 % de cumplimiento con ISO/IEC 15438**. En pruebas de referencia, la biblioteca crea un código de barras MacroPdf417 de tamaño completo en menos de **150 ms** en un portátil de desarrollo típico, lo que la hace lo suficientemente rápida para escenarios de servidor de alto rendimiento.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

* **.NET 6.0 o posterior** (el código también funciona en .NET Framework 4.7+).  
* Una **licencia válida de Aspose.BarCode para .NET** (la prueba gratuita sirve para desarrollo).  
* **Visual Studio 2022** o cualquier otro IDE de C# que prefieras.  
* Familiaridad básica con la sintaxis de C# y conceptos orientados a objetos.  

No se requieren paquetes NuGet adicionales más allá de **Aspose.BarCode**.

## ¿Cómo generar pdf417 con opciones de macro?

Carga el `BarcodeGenerator` con el enumerado `EncodeTypes.MacroPdf417`, establece el tamaño del módulo, configura los campos de macro y, finalmente, guarda la imagen. Los pasos siguientes muestran el orden exacto que debes seguir para evitar problemas comunes.

### Paso 1: instalar el paquete NuGet Aspose.BarCode

Abre tu proyecto en Visual Studio y ejecuta el siguiente comando en la Consola del Administrador de paquetes:

```powershell
Install-Package Aspose.BarCode
```

El paquete agrega el espacio de nombres `Aspose.BarCode`, que contiene la clase `BarcodeGenerator` utilizada a lo largo de este tutorial.

### Paso 2: crear un generador de códigos de barras para MacroPdf417

`BarcodeGenerator` es la clase central utilizada para generar códigos de barras en Aspose.BarCode.  
La primera línea crea una instancia de `BarcodeGenerator` que apunta a la simbología **MacroPdf417** e incrusta el texto personalizado que deseas codificar.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

// Step 2: Initialize the generator with custom text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The rest of the configuration goes here
}
```

`BarcodeGenerator` es la clase principal de Aspose.BarCode para crear cualquier código de barras; contiene todas las opciones de codificación y configuración de renderizado.

### Paso 3: definir el tamaño básico del módulo

`XDimension` establece el ancho de un solo módulo (píxel) en el código de barras.  
El tamaño del módulo controla la densidad visual del código. Un valor de píxel de `2` produce una imagen nítida que se imprime bien en impresoras de etiquetas estándar.

```csharp
    // Step 3: Set the X‑dimension (module width) in pixels
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Aumentar el valor hace que el código de barras sea más grande, mientras que reducirlo puede causar problemas de escaneo en dispositivos de baja resolución.

### Paso 4: configurar opciones de diseño específicas de macro‑PDF417

`Columns` determina el número de columnas de datos en el código de barras PDF417.  
MacroPdf417 requiere varios parámetros adicionales. Estas configuraciones te permiten dividir los datos en varios archivos, identificar cada segmento y verificar la integridad.

```csharp
    // Step 4: Macro‑specific layout
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

La propiedad `Columns` influye en el ancho del código de barras, mientras que los campos de macro (`FileID`, `SegmentID`, `SegmentsCount`, `FileName`) permiten a los sistemas posteriores volver a ensamblar los datos originales correctamente.

### Paso 5: añadir metadatos macro adicionales

`MacroPdf417Terminator` indica si el segmento actual es el último de una serie macro.  
Aspose.BarCode te permite incrustar campos macro opcionales como checksum, tamaño de archivo, marca de tiempo e información del remitente/receptor. Estos campos son útiles para auditorías y detección de errores.

```csharp
    // Step 5: Optional macro metadata
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                 // CCITT‑16 example
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // Approximate size in bytes
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                       // Creation date
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                       // Marks the last segment
```

El checksum protege contra errores de transmisión, mientras que la marca de tiempo y los campos de remitente proporcionan contexto para el procesamiento posterior. Establecer `MacroPdf417Terminator` a `Set` indica que este es el segmento final de la serie macro.

### Paso 6: guardar el código de barras como imagen PNG

`Save` escribe la imagen del código de barras generado en un archivo con el formato especificado.  
Finalmente, escribe el código de barras generado en disco. PNG conserva calidad sin pérdidas, lo que es ideal para escaneo.

```csharp
    // Step 6: Export the barcode
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Cuando el código finaliza, el archivo `ExtPDF417Meta.png` contiene un código de barras MacroPdf417 de alta resolución que codifica el texto personalizado y todos los metadatos macro.

#### Resultado esperado

Abrir `ExtPDF417Meta.png` muestra un código de barras orientado verticalmente con filas y columnas claramente definidas. Escanear la imagen con cualquier lector PDF417 devuelve la cadena original **Åspóse.Barcóde©** y los campos macro que configuraste (ID de archivo, ID de segmento, checksum, etc.).

## ¿Cómo generar pdf417 sin opciones de macro?

Para crear un código de barras PDF417 estándar, solo necesitas establecer la simbología a `EncodeTypes.Pdf417`, proporcionar el texto a codificar, opcionalmente ajustar parámetros como `XDimension` y `Columns`, y luego llamar a `Save`. Este enfoque omite todas las propiedades específicas de macro, produciendo un código de barras de segmento único adecuado para la mayoría de las aplicaciones.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(
           EncodeTypes.Pdf417, "Standard PDF417 data"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 3;
    generator.Parameters.Barcode.Pdf417.Columns = 6;
    generator.Save("StandardPdf417.png", BarCodeImageFormat.Png);
}
```

Este fragmento muestra **cómo generar pdf417** rápidamente cuando no se requiere funcionalidad macro. La respuesta directa: crea un `BarcodeGenerator` con `EncodeTypes.Pdf417`, establece `CodeText`, opcionalmente ajusta `XDimension` y `Columns`, y luego llama a `Save` con el formato de imagen deseado.

## Problemas comunes y consejos profesionales

| Problema | Por qué ocurre | Solución |
|----------|----------------|----------|
| El código de barras es demasiado pequeño para escanear | X‑dimension establecida en 1 píxel o columnas demasiado altas | Usa al menos `2` píxeles para `XDimension` y mantén las columnas entre `3` y `9` para tamaños de etiqueta típicos |
| Los caracteres Unicode aparecen como � | Incompatibilidad de codificación en el archivo del proyecto | Asegúrate de que el archivo del proyecto esté guardado como UTF‑8 y que el archivo fuente contenga el BOM correcto |
| Los campos macro son ignorados por el escáner | `MacroPdf417Terminator` no está configurado para el último segmento | Establece `MacroPdf417Terminator = Pdf417MacroTerminator.Set` en el segmento final |
| El archivo de imagen está corrupto | El flujo de salida no se cierra correctamente | Usa la instrucción `using` (como se muestra) para garantizar la eliminación del generador |

## Ejemplo completo y ejecutable

`BarcodeGenerator` es la clase que crea la imagen del código de barras.  
Copia el siguiente código en una nueva aplicación de consola y ejecútalo. El programa crea el código de barras, lo guarda y muestra la ruta de salida en la consola.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace AsposeBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with custom Unicode text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Basic size
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // Macro layout
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Optional macro metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputFile = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
                barcodeGenerator.Save(outputFile, BarCodeImageFormat.Png);

                Console.WriteLine($"Barcode saved to: {outputFile}");
            }
        }
    }
}
```

Al ejecutar el programa se imprimirá una línea similar a:

```
Barcode saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

Abre el archivo para verificar la salida visual.

## Preguntas frecuentes

**Q: ¿Puedo usar este código en una API web ASP.NET Core?**  
**A:** Sí. La misma clase `BarcodeGenerator` funciona en cualquier tiempo de ejecución .NET, incluido ASP.NET Core, siempre que se haga referencia al ensamblado `Aspose.BarCode`.

**Q: ¿Aspose.BarCode soporta otros formatos de imagen?**  
**A:** Por supuesto. Puedes guardar en PNG, JPEG, BMP, TIFF e incluso SVG pasando el valor correspondiente del enumerado `BarCodeImageFormat` al método `Save`.

**Q: ¿Qué tan grande puede ser los datos codificados?**  
**A:** Un solo símbolo PDF417 puede contener hasta 1 700 caracteres; con MacroPdf417 puedes dividir los datos en varios segmentos, soportando efectivamente longitud ilimitada.

**Q: ¿Hay forma de añadir color al código de barras?**  
**A:** Sí. Establece las propiedades `ForeColor` y `BackColor` del `BarcodeGenerator` antes de llamar a `Save` para producir códigos de barras coloreados.

**Q: ¿Qué pasa si necesito incrustar el código de barras directamente en un PDF?**  
**A:** Usa Aspose.PDF para insertar la imagen PNG o SVG generada en una página PDF, o utiliza la función de exportación a PDF incorporada en Aspose.BarCode.

## Conclusión

Ahora sabes **cómo generar pdf417** para la simbología MacroPdf417, incrustar texto Unicode personalizado, configurar metadatos macro y exportar el resultado como una imagen PNG. El mismo patrón te permite generar un código de barras PDF417 simple cuando no se requieren opciones macro, y puedes adaptar el código a otros formatos de códigos de barras soportados por Aspose.BarCode. Experimenta con diferentes valores de `XDimension`, recuentos de columnas y combinaciones de campos macro para afinar el código de barras según tu impresora o escáner específico.

A continuación, explora temas relacionados como **crear texto de código de barras personalizado** para códigos QR, añadir filtros de color con parámetros `Color`, o incrustar códigos de barras directamente en documentos PDF usando Aspose.PDF. La flexibilidad de Aspose.BarCode te permite manejar desde códigos de barras simples de una línea hasta complejos códigos de barras macro de varios segmentos con solo unas pocas líneas de C#.

¡Feliz codificación y disfruta de la fiabilidad que Aspose.BarCode aporta a tus soluciones de códigos de barras .NET!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo crear código de barras – PDF417 compacto con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cómo generar código de barras DataMatrix con Aspose.BarCode para .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [Generar código de barras Java - Establecer texto del código usando Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)

---

**Última actualización:** 2026-10-14  
**Probado con:** Aspose.BarCode 24.11 para .NET  
**Autor:** Aspose

## Tutoriales relacionados

- [Crear Macro Pdf417 Barcode con Aspose Barcode C](/barcode/net/compact-pdf417-encoding/create-macro-pdf417-barcode-with-aspose-barcode-c/)
- [Ajustar tamaño de código de barras Guía C para generar códigos Pdf417](/barcode/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Leer código de barras desde imagen C Guía completa con Macro Pdf417](/barcode/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}