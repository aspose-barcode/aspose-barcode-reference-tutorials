---
category: general
date: 2026-10-14
description: Crear un escáner de códigos de barras en consola en C# que lea códigos
  PDF417, maneje macro PDF417 y decodifique varios códigos de una sola imagen.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create console barcode scanner
- read barcodes from picture
- c# barcode reader example
lastmod: 2026-10-14
og_description: Crear un escáner de códigos de barras en consola en C# para leer rápidamente
  códigos PDF417 y macro PDF417 desde imágenes. Esta guía paso a paso muestra cómo
  decodificar varios códigos en una sola foto.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: Crear escáner de códigos de barras en consola en C# – guía completa
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  headline: Create console barcode scanner in C# – barcode reader example
  type: TechArticle
- description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  name: Create console barcode scanner in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
- console application
title: Crear escáner de códigos de barras en consola en C# – ejemplo de lectura de
  código PDF417
url: /es/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear escáner de códigos de barras de consola en C# – ejemplo de lectura de código de barras PDF417

`BarCodeReader` es la clase central de Aspose.BarCode que decodifica códigos de barras de imágenes y devuelve metadatos detallados. Si necesitas leer datos de códigos de barras PDF417 de una imagen, esta guía te muestra cómo hacerlo con la clase **BarCodeReader** en C#. Aprenderás un ejemplo de **crear escáner de códigos de barras de consola** que también maneja macro PDF417 y puede leer varios códigos de barras en una sola imagen.

Trabajar con códigos de barras a menudo implica manejar diferentes fuentes de imágenes, condiciones de iluminación variables y, a veces, datos compuestos como segmentos macro PDF417. Este tutorial cubre todo lo que necesitas para decodificar un código de barras PDF417, extraer sus campos extendidos y procesar varios códigos de barras de la misma foto. Al final tendrás un programa de consola ejecutable que lee códigos de barras de un archivo de imagen y muestra información detallada en la consola.

## Respuestas rápidas
- **¿Qué hace el ejemplo?** Crea un escáner de códigos de barras de consola que lee códigos de barras PDF417 y macro PDF417 de una imagen y muestra todos los campos decodificados.  
- **¿Qué biblioteca se requiere?** Aspose.BarCode para .NET (NuGet).  
- **¿Puede leer varios códigos de barras a la vez?** Sí – el lector itera sobre cada código de barras encontrado en la imagen.  
- **¿Necesito una conexión a internet?** No, la biblioteca funciona completamente sin conexión.  
- **¿Qué versión de .NET es compatible?** .NET 6.0 o posterior.

## Lo que necesitarás

Antes de comenzar, asegúrate de tener:

* .NET 6.0 SDK o posterior instalado  
* Una versión reciente del paquete NuGet **Aspose.BarCode for .NET** (o cualquier biblioteca compatible que proporcione `BarCodeReader` y `DecodeType.MacroPdf417`)  
* Un archivo de imagen que contenga un código de barras PDF417 o macro PDF417 (el ejemplo usa `ExtPDF417Meta.png`)  
* Un editor de código o IDE como Visual Studio 2022  

No se requieren servicios adicionales ni API externas.

## Configuración del proyecto para la lectura de códigos de barras

1. **Crear un nuevo proyecto de consola**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **Agregar la biblioteca de códigos de barras**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **Copiar la imagen del código de barras**  

   Coloca `ExtPDF417Meta.png` (o cualquier imagen que contenga un código de barras PDF417) en la carpeta del proyecto.  
   Para este tutorial asumimos que el archivo se encuentra en `YOUR_DIRECTORY/ExtPDF417Meta.png`.

El proyecto ya está listo para compilar y ejecutar el ejemplo del lector de códigos de barras.

## ¿Cómo crear un escáner de códigos de barras de consola en C#?

`BarCodeReader` es una clase proporcionada por Aspose.BarCode que lee códigos de barras de imágenes y devuelve sus datos decodificados.  
Carga la imagen con `BarCodeReader`, establece el tipo de decodificación a `MacroPdf417` y recorre los resultados: eso es todo lo que necesitas para crear un escáner de códigos de barras de consola. El lector libera automáticamente los recursos nativos gracias a la instrucción `using`, por lo que no tienes que gestionar la memoria manualmente. Este enfoque funciona con cualquier formato de imagen compatible con .NET, como PNG, JPEG o BMP.

### Guía paso a paso

El núcleo de la solución es un bloque `using` que crea una instancia de `BarCodeReader`, especifica `DecodeType.MacroPdf417` y recorre cada código de barras detectado. El siguiente código es un programa completo y autónomo que puedes pegar en `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**Por qué funciona**:  

* `DecodeType.MacroPdf417` indica al lector que busque la extensión macro de PDF417, que lleva metadatos adicionales como ID de archivo, recuento de segmentos y marcas de tiempo.  
* La instrucción `using` garantiza que los recursos no administrados (manejadores de archivo, búferes nativos de decodificación) se liberen rápidamente.  
* El bucle `foreach` procesa automáticamente **todos** los códigos de barras que contiene la imagen, cumpliendo con el requisito de *leer varios códigos de barras*.  

Al ejecutar el programa (`dotnet run`), deberías ver una salida similar a la siguiente:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

Si la imagen contiene más de un código de barras PDF417, el bucle imprime un bloque separado para cada código, demostrando así cómo **leer varios códigos de barras** de una sola foto.

## ¿Cómo puedo leer varios códigos de barras de una imagen?

Utiliza una única instancia de `BarCodeReader` y establece la bandera `DecodeType` para incluir todos los formatos que deseas detectar. Combinando banderas con el operador OR bit a bit, puedes indicar a la biblioteca que busque PDF417, QR, Code‑128 y muchas otras simbologías en una sola pasada. Esto elimina la necesidad de lectores separados y reduce el tiempo de procesamiento.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* es una máscara de bits, por lo que puedes combinar cualquier número de formatos compatibles. Aspose.BarCode admite **más de 30 simbologías de códigos de barras**, incluyendo QR, DataMatrix, Code‑128 y UPC‑A, lo que permite a un solo escáner manejar casos de uso diversos como etiquetado de productos, validación de tickets y verificación de identidad.

## ¿Qué es macro PDF417 y cómo acceder a sus campos de forma segura?

Macro PDF417 es una extensión de la simbología PDF417 que permite dividir un conjunto de datos grande en varios símbolos de código de barras.  
Macro PDF417 agrega un conjunto rico de propiedades extendidas. Sin embargo, no todos los códigos de barras incluyen todos los campos. Acceder a una propiedad que falta puede lanzar una `NullReferenceException`. El enfoque más seguro es verificar cada propiedad antes de imprimirla, garantizando que tu aplicación permanezca estable incluso cuando los datos macro estén ausentes.

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*Por qué importa*: En implementaciones del mundo real puedes recibir códigos de barras PDF417 simples que carecen de datos macro. La verificación defensiva asegura que tu aplicación continúe ejecutándose sin bloquearse.

## Errores comunes y buenas prácticas

| Problema | Por qué ocurre | Corrección recomendada |
|----------|----------------|------------------------|
| La ruta de la imagen es incorrecta | `BarCodeReader` lanza una excepción de archivo no encontrado antes de que ocurra cualquier decodificación | Utiliza `Path.Combine` y valida que el archivo exista con `File.Exists` |
| Imagen de baja resolución | El decodificador no puede localizar los bordes del código de barras, lo que resulta en cero detecciones | Proporciona una resolución mínima de 300 dpi para resultados fiables |
| Código de barras rotado > 45° | Muchas bibliotecas asumen orientación vertical | Habilita `reader.RecognitionOptions.RotateImage = true` si la imagen puede estar rotada |
| Faltan campos macro | Intentar leer una propiedad nula provoca un bloqueo | Siempre verifica `null` antes de acceder a propiedades macro |
| Procesamiento por lotes grande | Recrear el lector para cada archivo añade sobrecarga | Reutiliza una única instancia de `BarCodeReader` con diferentes streams al procesar muchas imágenes |

## ¿Por qué usar Aspose.BarCode para un escáner de códigos de barras de consola?

Aspose.BarCode puede decodificar **más de 30 tipos de códigos de barras** y procesa imágenes de hasta **200 MP** sin cargar todo el archivo en memoria, alcanzando un rendimiento de **150 fotogramas por segundo** en una CPU típica de 3.2 GHz. Estas capacidades cuantificadas lo convierten en una opción fiable para soluciones de escaneo de alto volumen y locales donde la latencia y la precisión son críticas.

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos con explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo leer códigos de barras DataMatrix con Aspose.BarCode para .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Leer código de barras DataMatrix C# – Generar modo DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Leer código de barras de una imagen – Dominando la extracción de regiones de códigos de barras en Java con Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

## Preguntas frecuentes

**P: ¿Puedo usar este escáner en un entorno de producción?**  
**R: Sí. Compra una licencia comercial de Aspose.BarCode para eliminar la marca de agua de evaluación y obtener soporte completo.**

**P: ¿La biblioteca funciona en Linux y macOS?**  
**R: Absolutamente. Aspose.BarCode para .NET es multiplataforma y se ejecuta en .NET 6+ en Windows, Linux y macOS.**

**P: ¿Cómo manejo imágenes muy grandes sin agotar la memoria?**  
**R: Usa el constructor `LoadOptions` para habilitar el modo de transmisión, que procesa la imagen en fragmentos en lugar de cargarla completamente en RAM.**

**P: ¿Es posible decodificar imágenes cifradas o protegidas con contraseña?**  
**R: El lector puede manejar imágenes cifradas con los esquemas de contraseña estándar PNG/JPEG; simplemente proporciona la contraseña mediante `reader.ImagePassword`.**

**P: ¿Qué pasa si mi código de barras está parcialmente dañado?**  
**R: Habilita opciones de corrección de errores como `reader.RecognitionOptions.CorrectErrors = true` para mejorar la resistencia contra daños o ruido.**

---

**Última actualización:** 2026-10-14  
**Probado con:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose

## Tutoriales relacionados

- [Cómo leer Pdf417 en C Ejemplo completo de lector de códigos de barras](/barcode/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Leer varios códigos de barras C Guía completa con Pdf417](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)
- [Decodificar código de barras de una imagen con un ejemplo de lector de códigos de barras C](/barcode/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}