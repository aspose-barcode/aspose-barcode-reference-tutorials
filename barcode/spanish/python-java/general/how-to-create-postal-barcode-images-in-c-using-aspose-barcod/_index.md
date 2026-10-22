---
category: general
date: 2026-10-21
description: 'Aprende a crear imágenes de códigos de barras postales en C# con Aspose.BarCode:
  genera códigos de barras Planet y RM4SCC, controla las barras rellenas y guarda
  archivos PNG.'
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode
- generate planet barcode
- how to generate barcode c#
language: es
lastmod: 2026-10-21
og_description: Crea imágenes de códigos de barras postales en C# con Aspose.BarCode.
  Este tutorial muestra cómo generar códigos de barras Planet y RM4SCC, alternar barras
  rellenas y guardar archivos PNG.
og_image_alt: Screenshot of a generated Planet postal barcode with filled bars
og_title: Crear imágenes de códigos de barras postales en C# – guía paso a paso
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Learn how to create postal barcode images in C# with Aspose.BarCode
    – generate Planet and RM4SCC barcodes, control filled bars, and save PNG files.
  headline: How to create postal barcode images in C# using Aspose.BarCode
  type: TechArticle
- description: Learn how to create postal barcode images in C# with Aspose.BarCode
    – generate Planet and RM4SCC barcodes, control filled bars, and save PNG files.
  name: How to create postal barcode images in C# using Aspose.BarCode
  steps:
  - name: 1. Prepare the output folder
    text: The barcode images need a writable directory. The code creates the folder
      if it does not exist, preventing a runtime `DirectoryNotFoundException`.
  - name: 2. Generate a Planet barcode with filled bars
    text: Planet barcodes are used by many postal services for domestic mail. The
      default `FilledBars` setting renders solid bars, which is the most common visual
      style.
  - name: 3. Generate a Planet barcode with empty bars
    text: Some postal specifications require **empty** (hollow) bars. You can toggle
      this behavior via the `FilledBars` property.
  - name: 4. Generate an RM4SCC barcode with filled bars
    text: RM4SCC (Royal Mail 4‑State Customer Code) is the UK postal barcode. Like
      Planet, the default appearance uses solid bars.
  - name: Full source code in one block
    text: Copy the following snippet into a new C# console project. It compiles with
      .NET 6.0 and produces three PNG files in the `Barcodes` subfolder.
  - name: Next steps
    text: '* **Generate other postal barcodes** – try `EncodeTypes.Postnet` or `EncodeTypes.USPSIntelligentMail`.
      * **Customize appearance** – experiment with `BarHeight`, `ForeColor`, and `BackColor`
      to match your branding. * **Integrate into a web service** – expose the generation
      logic via ASP.NET Core endp'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Cómo crear imágenes de códigos de barras postales en C# usando Aspose.BarCode
url: /es/python-java/general/how-to-create-postal-barcode-images-in-c-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear imágenes de códigos de barras postales en C# usando Aspose.BarCode

Si necesita **crear códigos de barras postales** en un proyecto .NET, esta guía muestra una solución completa y lista‑para‑ejecutar. Verá cómo generar códigos de barras Planet y RM4SCC, alternar entre barras rellenas y vacías, y almacenar los resultados como archivos PNG, todo con unas pocas líneas de código C#.

Generar códigos de barras postales fiables es esencial para la automatización del correo, la impresión masiva de etiquetas y la integración con plataformas logísticas. Al final de este tutorial dispondrá de un fragmento de código reutilizable que podrá copiar en cualquier aplicación de consola o web en C#.

## Requisitos previos

* SDK .NET 6.0 o posterior instalado  
* Visual Studio 2022 (o cualquier IDE que admita .NET)  
* Un paquete NuGet activo de **Aspose.BarCode** (`Install-Package Aspose.BarCode`)  

Estas herramientas son suficientes para compilar y ejecutar el ejemplo sin dependencias adicionales.

## Guía paso a paso para **crear códigos de barras postales** imágenes

El proceso consta de cuatro pasos lógicos:

1. Preparar la carpeta de salida.  
2. Generar un código de barras Planet con barras rellenas (la apariencia predeterminada).  
3. Generar un código de barras Planet con barras vacías.  
4. Generar un código de barras RM4SCC con barras rellenas.  

Cada paso se explica a continuación, y el código fuente completo aparece después de las explicaciones.

### 1. Preparar la carpeta de salida

Las imágenes de códigos de barras necesitan un directorio con permisos de escritura. El código crea la carpeta si no existe, evitando una `DirectoryNotFoundException` en tiempo de ejecución.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // Define the output folder (adjust the path to your environment)
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

        // Ensure the folder exists
        Directory.CreateDirectory(outputFolder);
```

*Por qué es importante*: Un directorio ausente detiene el programa antes de que se genere cualquier código de barras. Usar `Directory.CreateDirectory` es seguro porque no hace nada si la carpeta ya existe.

### 2. Generar un código de barras Planet con barras rellenas

Los códigos de barras Planet son utilizados por muchos servicios postales para correo nacional. La configuración predeterminada `FilledBars` genera barras sólidas, que es el estilo visual más común.

```csharp
        // Step 2: Generate a Planet barcode with filled bars (default)
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        // XDimension controls the width of a single bar; 4 pixels works well for screen display
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
        planetFilled.Save(Path.Combine(outputFolder, "PostalPlanetFilledBars.png"),
                          BarCodeImageFormat.Png);
```

*Explicación*:  
* `EncodeTypes.Planet` indica a Aspose.BarCode que use el estándar Planet.  
* La cadena de datos `"123456"` es una carga útil Planet válida (6 caracteres numéricos).  
* `XDimension.Pixels = 4` produce un ancho de barra de 4 px, lo que equilibra legibilidad y tamaño de archivo.  
* `Save` escribe la imagen como PNG, un formato sin pérdida adecuado para procesamiento posterior.

### 3. Generar un código de barras Planet con barras vacías

Algunas especificaciones postales requieren barras **vacías** (huecas). Puede alternar este comportamiento mediante la propiedad `FilledBars`.

```csharp
        // Step 3: Generate a Planet barcode with empty bars
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        // Setting FilledBars to false creates hollow bars
        planetEmpty.Parameters.Barcode.FilledBars = false;
        planetEmpty.Save(Path.Combine(outputFolder, "PostalPlanetEmptyBars.png"),
                         BarCodeImageFormat.Png);
```

*Consejo*: Al cambiar entre barras rellenas y vacías, mantenga el valor de `XDimension` sin cambios para conservar un tamaño consistente entre las imágenes.

### 4. Generar un código de barras RM4SCC con barras rellenas

RM4SCC (Royal Mail 4‑State Customer Code) es el código de barras postal del Reino Unido. Al igual que Planet, la apariencia predeterminada utiliza barras sólidas.

```csharp
        // Step 4: Generate an RM4SCC barcode with filled bars (default)
        BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFilled.Save(Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png"),
                          BarCodeImageFormat.Png);
    }
}
```

*Por qué RM4SCC*: El formato RM4SCC codifica una cadena numérica de 6 dígitos más un dígito de control, lo que lo hace ideal para los servicios de correo del Reino Unido.

### Código fuente completo en un solo bloque

Copie el siguiente fragmento en un nuevo proyecto de consola C#. Compila con .NET 6.0 y genera tres archivos PNG en la subcarpeta `Barcodes`.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // -------------------------------------------------
        // 1. Prepare the output folder
        // -------------------------------------------------
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // -------------------------------------------------
        // 2. Planet barcode – filled bars (default)
        // -------------------------------------------------
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
        planetFilled.Save(Path.Combine(outputFolder, "PostalPlanetFilledBars.png"),
                          BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 3. Planet barcode – empty bars
        // -------------------------------------------------
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        planetEmpty.Parameters.Barcode.FilledBars = false;
        planetEmpty.Save(Path.Combine(outputFolder, "PostalPlanetEmptyBars.png"),
                         BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 4. RM4SCC barcode – filled bars (default)
        // -------------------------------------------------
        BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFilled.Save(Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png"),
                          BarCodeImageFormat.Png);

        Console.WriteLine("All barcode images have been saved to: " + outputFolder);
    }
}
```

#### Salida esperada

Ejecutar el programa muestra una línea de confirmación y crea tres archivos:

* `PostalPlanetFilledBars.png` – código de barras Planet con barras sólidas  
* `PostalPlanetEmptyBars.png` – código de barras Planet con barras huecas  
* `PostalRM4SCCFilledBars.png` – código de barras RM4SCC con barras sólidas  

Cada imagen tiene un ancho de 4 px por barra, adecuado para vista previa en pantalla o incrustación en PDF listo para imprimir.

## Preguntas frecuentes y manejo de casos límite

| Pregunta | Respuesta |
|----------|-----------|
| **¿Qué pasa si la cadena de datos es inválida?** | Aspose.BarCode lanza `ArgumentException`. Valide la longitud de la entrada (Planet = 6 numéricos, RM4SCC = 6 numéricos) antes de crear el generador. |
| **¿Puedo cambiar el formato de imagen?** | Sí. Reemplace `BarCodeImageFormat.Png` por `Jpeg`, `Gif`, `Bmp` o `Tiff` según sea necesario. |
| **¿Cómo ajusto la altura de la barra?** | Utilice `planetFilled.Parameters.Barcode.BarHeight` (el valor predeterminado es 50 px). |
| **¿Es seguro usar este código en una API web?** | Absolutamente. El generador es seguro para hilos en operaciones de solo lectura, pero cree una nueva instancia de `BarcodeGenerator` por solicitud para evitar estado compartido. |
| **¿Qué hay de otros estándares postales?** | Aspose.BarCode también admite `EncodeTypes.Postnet`, `EncodeTypes.USPSIntelligentMail`, etc. El mismo patrón se aplica—simplemente cambie el valor de `EncodeTypes`. |

## Conclusión

Ahora sabe cómo **crear imágenes de códigos de barras postales** en C# con Aspose.BarCode, cubriendo los formatos Planet y RM4SCC y demostrando cómo alternar entre barras rellenas y vacías. El ejemplo completo y ejecutable puede insertarse en cualquier proyecto .NET, proporcionando una salida visual inmediata.

### Próximos pasos

* **Generar otros códigos de barras postales** – pruebe `EncodeTypes.Postnet` o `EncodeTypes.USPSIntelligentMail`.  
* **Personalizar la apariencia** – experimente con `BarHeight`, `ForeColor` y `BackColor` para que coincidan con su marca.  
* **Integrar en un servicio web** – exponga la lógica de generación mediante endpoints de ASP.NET Core para crear códigos de barras bajo demanda.  

Al dominar estas técnicas podrá **generar imágenes de códigos de barras planet** y responder consultas como “**cómo generar código de barras C#**” con confianza, ya sea que esté construyendo una herramienta de correo de escritorio o una API de envío basada en la nube. ¡Feliz codificación!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que se basan en las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y funcionales con explicaciones paso a paso para ayudarle a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en sus propios proyectos.

- [Cómo crear código de barras planet con barras rellenas y vacías](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [Cómo crear código de barras RM4SCC y generar código de barras planet en C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-generate-planet-barcode-in/)
- [Generar código de barras postal en C# – Guía completa con código de barras planet](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}