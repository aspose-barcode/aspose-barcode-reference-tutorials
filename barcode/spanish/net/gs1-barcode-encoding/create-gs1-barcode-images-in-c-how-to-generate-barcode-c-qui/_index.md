---
category: general
date: 2026-07-18
description: Crea imágenes de códigos de barras GS1 en C# con esta guía paso a paso
  sobre cómo generar códigos de barras en C# usando Aspose.BarCode – sin rodeos, solo
  código funcional.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create gs1 barcode images
- how to generate barcode c#
language: es
lastmod: 2026-07-18
og_description: Crea imágenes de códigos de barras GS1 en C# con este tutorial conciso.
  Aprende a generar códigos de barras en C# usando Aspose.BarCode y a guardar archivos
  PNG en segundos.
og_image_alt: Screenshot of a generated GS1‑MicroPDF417 barcode saved as a PNG file
og_title: Crear imágenes de códigos de barras GS1 en C# – Guía completa paso a paso
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create GS1 barcode images in C# with this step‑by‑step guide on how
    to generate barcode C# using Aspose.BarCode – no fluff, just working code.
  headline: Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly
  type: TechArticle
tags:
- barcode
- csharp
- gs1
- aspose
title: Crear imágenes de códigos de barras GS1 en C# – Cómo generar códigos de barras
  en C# rápidamente
url: /es/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear imágenes de códigos de barras GS1 en C# – Cómo generar código de barras C#

¿Alguna vez necesitaste **crear imágenes de códigos de barras gs1** para una etiqueta de embalaje pero no sabías por dónde empezar? No estás solo. En este tutorial verás exactamente **cómo generar código de barras c#** que produce imágenes GS1‑MicroPDF417 en cuestión de minutos.

Recorreremos todo el proceso: instalar la biblioteca, configurar el generador, intercambiar datos AI (Identificador de Aplicación) y, finalmente, guardar un conjunto de archivos PNG. Al final tendrás una aplicación de consola lista para ejecutar que genera varias imágenes de códigos de barras GS1, cada una con una combinación diferente de AI.

---

## Lo que necesitarás

- **.NET 6+** (o .NET Framework 4.6+). La última versión del runtime funciona mejor con Aspose.BarCode.
- **Aspose.BarCode for .NET** – instalar vía NuGet (`Install-Package Aspose.BarCode`).
- Una carpeta en disco donde se escribirán los archivos PNG (la llamaremos `YOUR_DIRECTORY`).
- Un conocimiento básico de la sintaxis de C#—no se requiere nada avanzado.

Si ya tienes todo eso, genial. Si no, primero obtén el paquete NuGet; es una sola línea en la consola del Administrador de paquetes y se encarga de todas las dependencias.

---

## Paso 1: Configurar un proyecto de consola mínimo

Abre tu IDE favorito (Visual Studio, Rider o VS Code) y crea un nuevo proyecto de consola:

```bash
dotnet new console -n Gs1BarcodeDemo
cd Gs1BarcodeDemo
dotnet add package Aspose.BarCode
```

Reemplaza el `Program.cs` generado automáticamente con el código que se muestra en los siguientes pasos. Este esqueleto nos brinda una hoja en blanco para **crear imágenes de códigos de barras gs1** sin desorden adicional.

---

## Paso 2: Cómo crear imágenes de códigos de barras gs1 – Inicializar el generador

El corazón de la operación es `BarcodeGenerator`. Lo iniciaremos con un valor GS1‑MicroPDF417 inicial, por ejemplo `(17)991231(10)ABCD`. Esa cadena codifica dos AI: fecha de caducidad (17) y lote (10).

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with a GS1‑MicroPDF417 barcode type
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.GS1MicroPdf417,
            "(17)991231(10)ABCD");
```

**Por qué es importante:** `EncodeTypes.GS1MicroPdf417` indica a Aspose que estamos trabajando con un formato GS1 compacto y de alta densidad. Comenzar con una cadena AI válida garantiza que el primer PNG que guardemos ya cumpla con los estándares GS1.

---

## Paso 3: Ajustar parámetros visuales – Afinar tamaño y diseño

Un código de barras demasiado pequeño o con forma extraña no se escaneará. Aquí establecemos la dimensión X (ancho del módulo) a 2 píxeles, limitamos el número de columnas para mantener la imagen estrecha y habilitamos el enlace para que varios códigos de barras puedan concatenarse más tarde si es necesario.

```csharp
        // Set visual parameters for a crisp, scannable image
        barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;      // module width
        barcodeGen.Parameters.Barcode.Pdf417.Columns = 2;        // column count
        barcodeGen.Parameters.Barcode.Pdf417.IsLinked = true;   // enable linking
```

**Consejo:** Si necesitas un código de barras más alto, aumenta `Rows` en lugar de columnas. Juega con `XDimension` para cumplir el tamaño mínimo de módulo de 0,33 mm requerido por la mayoría de los escáneres.

---

## Paso 4: Guardar el primer código de barras – AI 17 + AI 10

Ahora realmente escribimos la imagen en disco. El nombre del archivo refleja los AI utilizados, lo que facilita su localización más adelante.

```csharp
        // Save the first image (AI 17 + AI 10)
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_17_10.png",
                        BarCodeImageFormat.Png);
```

Después de ejecutar el programa, deberías ver un PNG nítido en `YOUR_DIRECTORY`. Ábrelo—verás las barras diminutas y el texto legible para humanos debajo. Esa es la primera de muchas **imágenes de códigos de barras gs1** que generaremos.

---

## Paso 5: Cambiar los datos codificados – Reutilizar el mismo generador

En lugar de crear un nuevo `BarcodeGenerator` para cada par de AI, simplemente cambiamos la propiedad `CodeText` y llamamos a `Save` nuevamente. Este enfoque es la forma más eficiente de **crear imágenes de códigos de barras gs1** en lote.

```csharp
        // AI 15 (best before) + AI 10 (batch)
        barcodeGen.CodeText = "(15)991231(10)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_15_10.png",
                        BarCodeImageFormat.Png);

        // AI 13 (production date) + AI 21 (serial)
        barcodeGen.CodeText = "(13)991231(21)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_13_21.png",
                        BarCodeImageFormat.Png);

        // AI 11 (manufacture date) + AI 21 (serial)
        barcodeGen.CodeText = "(11)991231(21)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_11_21.png",
                        BarCodeImageFormat.Png);

        // Only AI 17 (expiration) – no batch number
        barcodeGen.CodeText = "(17)991231";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_17.png",
                        BarCodeImageFormat.Png);
```

**¿Por qué reutilizar?** Cambiar `CodeText` evita la sobrecarga de volver a instanciar el generador y garantiza configuraciones visuales consistentes en todas las imágenes.

---

## Paso 6: Ejecutar, verificar y ajustar

Compila y ejecuta:

```bash
dotnet run
```

Ahora deberías tener cinco archivos PNG, cada uno nombrado según el par de AI que contiene. Abre cualquiera con un visor de imágenes; verás el código de barras y el texto codificado debajo. Para confirmar que los datos son correctos, usa una aplicación gratuita de escáner GS1 en tu teléfono—apúntala al PNG en tu pantalla y observa cómo aparecen los valores de AI.

**Problemas comunes y cómo evitarlos**

| Problema | Causa | Solución |
|----------|-------|----------|
| Código de barras ilegible | `XDimension` demasiado bajo (p. ej., 1 píxel) | Aumentar a 2 o 3 píxeles |
| Faltan corchetes AI | Formato incorrecto de `CodeText` | Siempre encerrar cada AI entre paréntesis |
| Imagen demasiado grande | Demasiadas columnas/filas | Reducir `Columns` o dejar que Aspose ajuste automáticamente |
| Error en tiempo de ejecución `EncodeTypes` no encontrado | Falta `using Aspose.BarCode.Generation` | Añadir la directiva `using` que falta |

---

## Paso 7: Extender el ejemplo – Generar más combinaciones de AI

Si necesitas **crear imágenes de códigos de barras gs1** para docenas de variantes de producto, considera cargar los pares de AI desde un archivo CSV:

```csharp
using System.IO;

string[] lines = File.ReadAllLines(@"ai_pairs.csv"); // format: "(17)991231,(10)ABCD"
foreach (var line in lines)
{
    barcodeGen.CodeText = line.Replace(',', ' ');
    string fileName = $"GS1MicroPdf417_{line.Replace("(", "").Replace(")", "").Replace(",", "_")}.png";
    barcodeGen.Save(Path.Combine(@"YOUR_DIRECTORY", fileName), BarCodeImageFormat.Png);
}
```

Este pequeño bucle lee cada línea, intercambia los datos y guarda un PNG con un nombre descriptivo—perfecto para pipelines de impresión de etiquetas a gran escala.

---

## Conclusión

Ahora tienes un programa C# completo y listo para ejecutar que **crea imágenes de códigos de barras gs1** para múltiples escenarios de AI, demostrando la forma más directa de **cómo generar código de barras c#** usando Aspose.BarCode. Reutilizando una única instancia de `BarcodeGenerator`, ajustando parámetros visuales y cambiando `CodeText`, puedes producir tantos PNG compatibles con GS1‑MicroPDF417 como requiera tu proyecto.

¿Qué sigue? Prueba añadir colores (`barcodeGen.Parameters.Barcode.ForeColor`), incrustar el código de barras en un PDF, o cambiar a otra simbología GS1 como DataMatrix. El mismo patrón se aplica: inicializar, configurar, establecer `CodeText` y guardar.

No dudes en dejar un comentario si encuentras algún obstáculo, o compartir tus propias variaciones. ¡Feliz codificación y que tus escaneos siempre sean limpios!

## ¿Qué deberías aprender a continuación?

Los siguientes tutoriales cubren temas estrechamente relacionados que amplían las técnicas demostradas en esta guía. Cada recurso incluye ejemplos de código completos y explicaciones paso a paso para ayudarte a dominar funciones adicionales de la API y explorar enfoques de implementación alternativos en tus propios proyectos.

- [How to create barcode quiet zone for Code 16K using Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}