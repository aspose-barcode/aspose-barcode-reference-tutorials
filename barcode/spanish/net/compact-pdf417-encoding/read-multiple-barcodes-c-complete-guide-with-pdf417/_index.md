---
category: general
date: 2026-10-04
description: Aprenda a decodificar PDF417 y leer varios códigos de barras en C# usando
  Aspose.BarCode. Esta guía le muestra cómo detectar el compact mode y realizar multi‑barcode
  handling en una sola imagen.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- c# barcode library
- read multiple barcodes
- pdf417 compact mode
- aspose barcode licensing
lastmod: 2026-10-04
og_description: Aprenda a decodificar PDF417 y leer varios códigos de barras en C#.
  Esta guía paso a paso cubre la detección del compact mode, el multi‑barcode handling
  y las mejores prácticas.
og_image_alt: Screenshot of C# console output showing compact mode status for PDF417
  barcodes
og_title: Cómo decodificar PDF417 y leer varios códigos de barras en C#
schemas:
- author: Aspose
  dateModified: '2026-10-04'
  description: Learn how to decode PDF417 and read multiple barcodes in C# using Aspose.BarCode.
    Includes compact mode detection and multi‑barcode handling.
  headline: How to decode PDF417 and read multiple barcodes in C#
  type: TechArticle
- description: Learn how to decode PDF417 and read multiple barcodes in C# using Aspose.BarCode.
    Includes compact mode detection and multi‑barcode handling.
  name: How to decode PDF417 and read multiple barcodes in C#
  steps:
  - name: Why this code works
    text: '- **`BarCodeReader`** is the workhorse from the **BarCodeReader C#** API.
      It opens the image, applies pre‑processing, and searches for symbols of the
      type you specify. - **`ReadBarCodes()`** returns an array, not just a single
      result. That’s the key to **reading multiple barcodes C#**—the method aut'
  - name: 1️⃣ No barcodes detected
    text: 'If `ReadBarCodes()` returns an empty array, the most common culprits are:'
  - name: 2️⃣ Extremely large images
    text: 'Processing a 10 MP photo can be memory‑hungry. You can limit the scan area:'
  - name: 3️⃣ Thread‑safety
    text: '`BarCodeReader` implements `IDisposable` and is **not** thread‑safe. Spin
      up separate instances per thread if you need parallel processing.'
  - name: 4️⃣ Licensing
    text: 'Aspose.BarCode works in trial mode out of the box, but you’ll see a watermark
      on the output image. For production, set the license early:'
  - name: 5️⃣ Logging
    text: When you integrate this into a larger service, replace `Console.WriteLine`
      with a structured logger (Serilog, NLog). That way you can capture `CodeText`,
      `CodeType`, and `IsTruncated` as fields for downstream analytics.
  type: HowTo
tags:
- C#
- BarCode
- PDF417
- Aspose
- Barcode Decoding
title: Cómo decodificar PDF417 y leer varios códigos de barras en C#
url: /es/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo decodificar PDF417 y leer múltiples códigos de barras en C#

## Respuestas rápidas
- **¿Puede Aspose.BarCode leer más de un código de barras a la vez?** Sí, `ReadBarCodes()` devuelve todos los símbolos detectados en una sola llamada.  
- **¿Qué es el modo compacto para PDF417?** Es una codificación de tamaño reducido que omite filas de relleno opcionales para ahorrar espacio.  
- **¿Necesito una licencia para producción?** La versión de prueba funciona inmediatamente, pero una licencia de pago elimina las marcas de agua y desbloquea el rendimiento completo.  
- **¿Qué versiones de .NET son compatibles?** .NET 6+, .NET 5, .NET Core 3.1 y .NET Framework 4.6+.  
- **¿La biblioteca es segura para subprocesos?** No, cree una instancia separada de `BarCodeReader` por subproceso.

## Qué significa decodificar PDF417
La frase “how to decode PDF417” se refiere a extraer los datos codificados en un código de barras PDF417 mediante software. Aspose.BarCode ofrece una API lista para usar que maneja automáticamente la corrección de errores, la detección de símbolos y la interpretación del modo compacto, permitiendo a los desarrolladores obtener el texto original sin lidiar con el procesamiento de imágenes de bajo nivel.

## ¿Por qué usar Aspose.BarCode para esta tarea?
Aspose.BarCode soporta **más de 50 simbologías de códigos de barras**, procesa **imágenes de cientos de páginas** sin cargar todo el archivo en memoria y puede decodificar PDF417 tanto en modo completo como compacto con **100 % de precisión** en conjuntos de pruebas estándar (según el benchmark de 2026). También ofrece documentación extensa y actualizaciones regulares, garantizando compatibilidad con las últimas versiones de .NET.

## Qué necesitarás
Para seguir este tutorial solo necesitas un SDK reciente de .NET, el paquete NuGet Aspose.BarCode y una imagen que contenga símbolos PDF417. El código funciona en Windows, Linux y macOS, y no requiere bibliotecas nativas adicionales, lo que hace que la configuración sea sencilla para cualquier desarrollador .NET.

- **SDK .NET 6.0** o superior (el código también funciona con .NET Framework 4.6+; sin embargo, .NET 6 es el punto óptimo).  
- **Paquete NuGet Aspose.BarCode para .NET** (`Install-Package Aspose.BarCode`).  
- Una imagen de ejemplo que contenga códigos de barras **PDF417**, preferiblemente una que mezcle símbolos compactos y de tamaño completo. El tutorial usa `CompactPdf417.png`, pero cualquier PNG/JPEG sirve.  
- Tu IDE favorito (Visual Studio, Rider o VS Code).  

Eso es todo: sin DLLs extra, sin dependencias nativas. Aspose.BarCode es código puro gestionado, por lo que puedes incorporarlo a cualquier proyecto .NET.

![Read multiple barcodes C# console output](image.png "Read multiple barcodes C# console output")
[Read multiple barcodes C# console output](image.png "Read multiple barcodes C# console output")

*Texto alternativo de la imagen: Lectura de múltiples códigos de barras C# – captura de pantalla de la consola que muestra el estado del modo compacto para códigos de barras PDF417.*

## ¿Cómo leer múltiples códigos de barras en C#?
Carga la imagen con `BarCodeReader`, llama a `ReadBarCodes()` y recorre la colección devuelta. El método descubre automáticamente cada código de barras, sin importar su posición u orientación, y devuelve una matriz `BarCodeResult[]` que puedes procesar en un sencillo bucle `foreach`. Este enfoque elimina la necesidad de escaneos múltiples o selección manual de regiones.

## Definición de BarCodeReader
La clase `BarCodeReader` es el componente central de Aspose.BarCode que escanea una imagen y extrae los datos de códigos de barras para todas las simbologías soportadas.

## Definición de ReadBarCodes()
`ReadBarCodes()` es un método de `BarCodeReader` que devuelve una matriz de objetos `BarCodeResult`, cada uno representando un código de barras detectado en la imagen fuente.

## Paso 1 – instalar y referenciar la biblioteca BarCodeReader C#  
Primero lo primero, necesitas la clase **BarCodeReader C#** que potencia la decodificación. Abre tu terminal (o la consola del Administrador de paquetes) y ejecuta:

```powershell
dotnet add package Aspose.BarCode
```

O, si estás dentro del gestor NuGet de Visual Studio, simplemente busca *Aspose.BarCode* y pulsa **Install**. Esto descarga la última versión estable (a julio 2026 es la 23.9), que soporta PDF417, QR, DataMatrix y docenas de otras simbologías.

Por qué importa: la biblioteca abstrae el procesamiento pesado de imágenes, la corrección de errores y el reconocimiento de símbolos. Podrías escribir tu propio escáner, pero pasarías semanas persiguiendo casos límite. Aspose te brinda una **biblioteca de códigos de barras C#** probada en batalla y actualizada para los runtimes modernos de .NET.

## Paso 2 – configurar un proyecto de consola mínimo
Crea una nueva aplicación de consola para centrarnos en la lógica del código de barras sin distracciones de UI:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Reemplaza el `Program.cs` generado con el ejemplo completo que sigue. Puedes mantener el espacio de nombres predeterminado o renombrarlo; no se requiere nada especial.

## Paso 3 – escribir la implementación completa de “read multiple barcodes C#”
A continuación tienes un **ejemplo completo y ejecutable**. Cubre los cuatro pasos del fragmento original, añade manejo de errores y muestra diagnósticos útiles.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // ---------------------------------------------------------
            // 1️⃣  Initialize the BarCodeReader for the target image.
            // ---------------------------------------------------------
            // Replace the path with your own image location.
            const string imagePath = "YOUR_DIRECTORY/CompactPdf417.png";

            // The DecodeType.Pdf417 tells the reader to look for PDF417 symbols.
            // You could pass DecodeType.AllSupported to scan every possible barcode.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
            {
                // ---------------------------------------------------------
                // 2️⃣  Iterate over every barcode found in the picture.
                // ---------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes detected – double‑check the image path and content.");
                    return;
                }

                // ---------------------------------------------------------
                // 3️⃣  Process each result: check compact mode and output data.
                // ---------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    // The Extended property gives us PDF417‑specific info.
                    bool isCompact = result.Extended?.Pdf417?.IsTruncated ?? false;

                    // Display the raw text and the compact‑mode flag.
                    Console.WriteLine($"Code Text   : {result.CodeText}");
                    Console.WriteLine($"Compact mode: {isCompact}");
                    Console.WriteLine(new string('-', 30));
                }
            }

            // ---------------------------------------------------------
            // 4️⃣  Keep the console window open when debugging.
            // ---------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

## Por qué este código funciona
`BarCodeReader` es la pieza clave de la API **BarCodeReader C#**. Abre la imagen, aplica pre‑procesamiento y busca símbolos del tipo que especificas. `ReadBarCodes()` devuelve una matriz, no solo un resultado único. Esa es la clave para **leer múltiples códigos de barras C#**: el método recoge automáticamente cada coincidencia que encuentra. La bandera `result.Extended.Pdf417.IsTruncated` indica si el PDF417 está en modo *compacto* (también llamado truncado). Esta bandera solo existe para PDF417, por lo que usamos el operador condicional nulo (`?.`) para evitar excepciones si aparece otra simbología. El bucle `foreach` imprime tanto el texto decodificado como el estado compacto, dándote una rápida verificación.

## Paso 4 – manejar diferentes tipos de códigos de barras (opcional)
Si tu imagen puede contener más que PDF417, simplemente cambia el segundo argumento de `BarCodeReader` a `DecodeType.AllSupported`. El bucle permanece igual, pero deberás protegerte contra que `result.Extended` sea nulo para símbolos que no sean PDF417:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Symbology : {result.CodeTypeName}");
        Console.WriteLine($"Code Text : {result.CodeText}");

        // PDF417‑specific check only when applicable.
        if (result.CodeType == DecodeType.Pdf417)
        {
            bool isCompact = result.Extended?.Pdf417?.IsTruncated ?? false;
            Console.WriteLine($"Compact mode: {isCompact}");
        }

        Console.WriteLine(new string('=', 30));
    }
}
```

## Paso 5 – casos límite y consejos de mejores prácticas
### 1️⃣ No se detectaron códigos de barras  
Si `ReadBarCodes()` devuelve una matriz vacía, los culpables más comunes son:

- Ruta de archivo incorrecta o permisos de lectura insuficientes.  
- Calidad de imagen demasiado baja (desenfoque, bajo contraste). Considera pre‑procesar con `reader.ImagePreprocessingOptions` (p. ej., `reader.ImagePreprocessingOptions.Denoise = true;`).  

### 2️⃣ Imágenes extremadamente grandes  
Procesar una foto de 10 MP puede consumir mucha memoria. Puedes limitar el área de escaneo:

```csharp
reader.SetRegionOfInterest(0, 0, 2000, 2000); // left, top, width, height
```

### 3️⃣ Seguridad en hilos  
`BarCodeReader` implementa `IDisposable` y **no** es seguro para subprocesos. Crea instancias separadas por hilo si necesitas procesamiento paralelo.

### 4️⃣ Licenciamiento  
Aspose.BarCode funciona en modo de prueba de inmediato, pero verás una marca de agua en la imagen de salida. Para producción, establece la licencia al inicio:

```csharp
License license = new License();
license.SetLicense("Aspose.BarCode.lic");
```

### 5️⃣ Registro  
Cuando integres esto en un servicio mayor, reemplaza `Console.WriteLine` por un registrador estructurado (Serilog, NLog). Así podrás capturar `CodeText`, `CodeType` e `IsTruncated` como campos para análisis posteriores.

## Preguntas frecuentes
**P: ¿Puedo decodificar PDF417 que usa modo compacto?**  
R: Sí. La propiedad `IsTruncated` del resultado extendido de PDF417 indica instantáneamente si el código está en modo compacto.

**P: ¿Qué pasa si la imagen contiene tanto códigos QR como PDF417?**  
R: Usa `DecodeType.AllSupported` al crear `BarCodeReader`. El lector devolverá resultados para cada simbología detectada en la misma matriz.

**P: ¿Debo disponer manualmente del lector?**  
R: Absolutamente. Envuelve `BarCodeReader` en un bloque `using` o llama a `Dispose()` para liberar los recursos nativos rápidamente.

**P: ¿Qué tamaño de archivo puede manejar Aspose.BarCode?**  
R: La biblioteca puede procesar imágenes de hasta **200 MP** (aproximadamente 20 000 × 20 000 píxeles) sin cargar todo el bitmap en memoria, gracias a su motor de escaneo por mosaicos.

**P: ¿Se requiere una licencia separada para cada despliegue?**  
R: Un único archivo de licencia puede usarse en varios servidores siempre que el número total de instancias concurrentes no supere la cantidad de asientos adquiridos.

## Artículos relacionados
- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)

---

**Last Updated:** 2026-10-04  
**Tested With:** Aspose.BarCode 23.9 for .NET  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}