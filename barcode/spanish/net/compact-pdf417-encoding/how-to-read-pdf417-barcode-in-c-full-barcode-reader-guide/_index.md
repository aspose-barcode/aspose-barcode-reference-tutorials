---
category: general
date: 2026-10-21
description: Cómo leer códigos de barras PDF417 en C# usando un lector de códigos
  de barras a partir de una imagen. Sigue este ejemplo paso a paso de lector de códigos
  de barras en C# para una decodificación fiable.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode from image c#
- c# barcode reader example
- macro pdf417 decoding
- barcode extended fields c#
language: es
lastmod: 2026-10-21
og_description: Cómo leer códigos de barras PDF417 en C# con un ejemplo completo de
  lector de códigos de barras. Aprende a decodificar imágenes Macro PDF417 y acceder
  a todos los campos extendidos.
og_image_alt: Console output showing decoded PDF417 barcode fields in a C# application
og_title: Cómo leer códigos de barras PDF417 en C# – guía detallada
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: How to read PDF417 barcode in C# using a barcode reader from image.
    Follow this step‑by‑step C# barcode reader example for reliable decoding.
  headline: How to read PDF417 barcode in C# – full barcode reader guide
  type: TechArticle
- description: How to read PDF417 barcode in C# using a barcode reader from image.
    Follow this step‑by‑step C# barcode reader example for reliable decoding.
  name: How to read PDF417 barcode in C# – full barcode reader guide
  steps:
  - name: Initialise the `BarCodeReader` for the specific `DecodeType`.
    text: Initialise the `BarCodeReader` for the specific `DecodeType`.
  - name: Iterate through the returned `BarCodeResult` collection.
    text: Iterate through the returned `BarCodeResult` collection.
  - name: Access both basic and extended PDF417 fields.
    text: Access both basic and extended PDF417 fields.
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the Aspose.BarCode package** (as shown earlier).'
    text: '**Add the Aspose.BarCode package** (as shown earlier).'
  - name: '**Copy the image file** into the project folder or reference it with an
      absolute path.'
    text: '**Copy the image file** into the project folder or reference it with an
      absolute path.'
  - name: '**Build and run**'
    text: '**Build and run**'
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Cómo leer códigos de barras PDF417 en C# – guía completa del lector de códigos
  de barras
url: /es/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-full-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo leer códigos de barras PDF417 en C# – guía completa del lector de códigos de barras

Si necesitas **cómo leer códigos de barras PDF417** en una aplicación .NET, esta guía te muestra una solución lista para ejecutar. Verás cómo **leer códigos de barras desde una imagen C#** usando una biblioteca de códigos de barras popular y obtener cada atributo Macro PDF417 sin herramientas adicionales.

El tutorial cubre todo lo necesario para un **ejemplo de lector de códigos de barras C#**: configuración del proyecto, revisión del código y consejos para manejar casos límite. Al final podrás pegar el código en un proyecto de consola y comenzar a decodificar imágenes PDF417 al instante.

## Lo que necesitarás

| Requisito | Razón |
|--------------|--------|
| .NET 6.0 SDK or later | Proporciona el runtime para la aplicación de consola C# |
| Visual Studio 2022 (or any C# IDE) | Permite crear y depurar proyectos fácilmente |
| Aspose.BarCode for .NET (NuGet package) | Proporciona las clases `BarCodeReader` y `DecodeType` |
| A Macro PDF417 image file (e.g., `MacroPdf417.png`) | Sirve como entrada para la decodificación |

Puedes instalar la biblioteca con la CLI de dotnet:

```bash
dotnet add package Aspose.BarCode
```

## Cómo leer códigos de barras PDF417 desde una imagen en C#

El núcleo del flujo de trabajo de **leer códigos de barras desde una imagen C#** consta de tres acciones:

1. Inicializar el `BarCodeReader` para el `DecodeType` específico.
2. Iterar a través de la colección `BarCodeResult` devuelta.
3. Acceder a los campos PDF417 básicos y extendidos.

A continuación se muestra el código completo y ejecutable. Guárdalo como `Program.cs` dentro de un proyecto de consola.

```csharp
using System;
using Aspose.BarCode;               // Provides BarCodeReader, DecodeType, BarCodeResult
using Aspose.BarCode.BarCodeRecognition; // Contains extended PDF417 structures

class Program
{
    static void Main()
    {
        // Step 1: Initialise a BarCodeReader for a Macro PDF417 image
        // Replace the path with the location of your MacroPdf417.png file
        string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes present in the image
            foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
            {
                // Step 3: Display basic barcode information
                Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
                Console.WriteLine($"CodeText: {barcodeResult.CodeText}");

                // Step 4: Show Macro PDF417 specific extended fields
                Console.WriteLine($"File ID: {barcodeResult.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID: {barcodeResult.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count: {barcodeResult.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name: {barcodeResult.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum: {barcodeResult.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size: {barcodeResult.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"TimeStamp: {barcodeResult.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee: {barcodeResult.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender: {barcodeResult.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator: {barcodeResult.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

### Explicación de cada paso

* **Paso 1 – Inicializar el lector**  
  El constructor `BarCodeReader` recibe la ruta del archivo de imagen y un `DecodeType`. `DecodeType.MacroPdf417` indica a la biblioteca que busque símbolos Macro PDF417, que contienen metadatos adicionales más allá de los códigos de barras PDF417 ordinarios.

* **Paso 2 – ReadBarCodes()**  
  Este método devuelve un `IEnumerable<BarCodeResult>` que puede contener varios códigos de barras si la imagen contiene más de uno. El bucle `foreach` garantiza que cada símbolo detectado sea procesado.

* **Paso 3 – Información básica**  
  `CodeTypeName` identifica el formato del código de barras (p.ej., “MacroPDF417”). `CodeText` contiene la cadena de datos crudos codificada en el símbolo.

* **Paso 4 – Campos extendidos**  
  Macro PDF417 agrega un conjunto de propiedades extendidas bajo `barcodeResult.Extended.Pdf417`. Estos campos exponen datos a nivel de archivo como `FileID`, `SegmentID` y `FileName`. Acceder a ellos directamente te permite reconstruir documentos multi‑segmento o verificar la integridad.

#### Salida esperada en la consola

```
CodeType: MacroPDF417
CodeText: 1234567890
File ID: 5
Segment ID: 1
Segments Count: 3
File Name: invoice_2024.pdf
Checksum: 0A3F
File Size: 254321
TimeStamp: 2024-03-15T10:45:12Z
Addressee: Acme Corp.
Sender: Warehouse 12
Terminator: END
----------------------------------------
```

Los valores exactos reflejan el contenido codificado en tu `MacroPdf417.png`. Si la imagen contiene un solo segmento, `SegmentsCount` será 1 y `SegmentID` será 0.

## Configura el entorno del lector de códigos de barras C#

Un **ejemplo fiable de lector de códigos de barras C#** depende de una configuración de proyecto limpia:

1. **Crear un nuevo proyecto de consola**  
   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```
2. **Agregar el paquete Aspose.BarCode** (como se mostró antes).  
3. **Copiar el archivo de imagen** en la carpeta del proyecto o referenciarlo con una ruta absoluta.  
4. **Compilar y ejecutar**  
   ```bash
   dotnet run
   ```

Si la compilación falla con un error de referencia faltante, verifica que las sentencias `using Aspose.BarCode;` coincidan con la versión del paquete instalado. La API de la biblioteca es estable en .NET 6 y .NET 8, por lo que puedes actualizar el runtime sin cambios en el código.

## Decodificar el código de barras Macro PDF417

Cuando llamas a `ReadBarCodes()`, la biblioteca realiza lo siguiente internamente:

* **Preprocesamiento de imagen** – convierte el mapa de bits a una matriz binaria, corrigiendo rotación y ruido.  
* **Detección de patrones** – escanea los patrones de inicio/fin PDF417 y extrae el ancho del módulo.  
* **Corrección de errores** – aplica códigos Reed‑Solomon para recuperar palabras de código dañadas.  
* **Extracción de macro** – analiza el encabezado de segmento PDF417 extendido y rellena el objeto `Extended.Pdf417`.

Entender este flujo te ayuda a decidir cuándo ajustar las opciones del decodificador. Por ejemplo, si tus imágenes tienen bajo contraste, puedes habilitar la propiedad `ReadQuality` del `BarCodeReader` (disponible en versiones posteriores) para mejorar la tasa de detección.

## Interpretar los campos PDF417 extendidos

Los campos extendidos se mapean directamente a la especificación Macro PDF417:

| Campo | Significado |
|-------|-------------|
| `MacroPdf417FileID` | Identificador único para todo el archivo a través de todos los segmentos |
| `MacroPdf417SegmentID` | Índice basado en cero del segmento actual |
| `MacroPdf417SegmentsCount` | Número total de segmentos que componen el archivo |
| `MacroPdf417FileName` | Nombre original del archivo almacenado durante la codificación |
| `MacroPdf417Checksum` | Checksum de 16 bits para verificación de integridad |
| `MacroPdf417FileSize` | Tamaño del archivo original en bytes |
| `MacroPdf417TimeStamp` | Marca de tiempo UTC cuando se generó el código de barras |
| `MacroPdf417Addressee` | Destinatario previsto del documento |
| `MacroPdf417Sender` | Emisor del documento |
| `MacroPdf417Terminator` | Cadena literal “END” que marca el último segmento |

Puedes usar estos valores para reconstruir un PDF multi‑segmento, verificar que no falte ningún segmento, o registrar información de auditoría para propósitos de cumplimiento.

## Problemas comunes y solución de problemas

| Síntoma | Causa probable | Solución |
|---------|----------------|----------|
| No aparece salida | Ruta de la imagen incorrecta o formato no soportado | Usa una ruta absoluta y asegura que el archivo sea PNG/JPEG soportado por Aspose.BarCode |
| `CodeType` muestra “PDF417” en lugar de “MacroPDF417” | La imagen contiene un símbolo PDF417 regular, no una variante macro | Verifica que el código de barras de origen esté codificado con extensiones Macro PDF417 |
| Algunos campos están vacíos | El código de barras se generó sin esos campos macro | Codifica el código de barras con una carga macro completa, o maneja valores nulos en el código |
| El decodificador lanza `ArgumentException` | `DecodeType` especificado incorrecto | Cambia `DecodeType.MacroPdf417` a `DecodeType.Pdf417` si solo necesitas datos PDF417 estándar |

**Consejo profesional:** Envuelve el acceso a los campos en verificaciones de nulos si anticipas códigos de barras no macro. El objeto `Extended.Pdf417` devuelve valores predeterminados (p.ej., `0` para campos numéricos) cuando los datos están ausentes.

```csharp
int fileId = barcodeResult.Extended?.Pdf417?.MacroPdf417FileID ?? -1;
```

## Recapitulación del ejemplo completo funcional

Uniendo todo, el programa final consta de las directivas using, el método `Main` y el bucle de cuatro pasos mostrado anteriormente. No se requieren archivos de configuración adicionales. Compila y ejecuta el proyecto para ver la salida en la consola con todas las propiedades Macro PDF417.

## Conclusión

Ahora sabes **cómo leer códigos de barras PDF417** en C# usando un conciso **ejemplo de lector de códigos de barras C#**. La guía te llevó a través de la configuración del entorno, la implementación del código y la interpretación de cada campo Macro PDF417 extendido. Con esta base puedes integrar la lectura de códigos de barras en sistemas de inventario, flujos de trabajo de gestión documental o back‑ends móviles.

### Próximo

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarte a dominar características adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [Cómo leer PDF417 en C# – guía completa del lector de códigos de barras](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/)
- [Cómo decodificar PDF417 en C# con un ejemplo de lector de códigos de barras](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/)
- [Cómo crear una imagen de código de barras PDF417 en C# con opciones Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}