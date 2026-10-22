---
category: general
date: 2026-10-21
description: Genera un'immagine di codice a barre Databar espanso impilato in C# usando
  BarcodeGenerator. Segui questa guida passo‑passo per creare immagini di codici a
  barre, personalizzare righe e colonne e esportare file PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- generate barcode image
- barcode generator c#
- how to generate databar
- create databar barcode
language: it
lastmod: 2026-10-21
og_description: Genera un codice a barre Databar espanso impilato in C# con questo
  tutorial. Scopri come utilizzare BarcodeGenerator, impostare righe e colonne e salvare
  immagini PNG.
og_image_alt: Sample databar expanded stacked barcode image generated with C#
og_title: Genera un codice a barre Databar Expanded Stacked in C# – guida completa
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  headline: How to generate a databar expanded stacked barcode in C#
  type: TechArticle
- description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  name: How to generate a databar expanded stacked barcode in C#
  steps:
  - name: Basic barcode generation
    text: The simplest way to generate a **databar expanded stacked** image is to
      instantiate `BarcodeGenerator` with the desired `EncodeTypes` value and a plain
      text payload.
  - name: Customizing columns – create databar barcode with 4 columns
    text: You can control the number of columns using the `Parameters.Barcode.DataBar.Columns`
      property. The following example creates a barcode with **4 columns** while keeping
      the default row count.
  - name: Customizing rows – create databar barcode with 3 rows
    text: Similarly, you can adjust the row count via `Parameters.Barcode.DataBar.Rows`.
      The code below generates a barcode with **3 rows** and the default column count
      (4).
  - name: Exporting to other formats
    text: 'If you need a different image type (e.g., JPEG, BMP, or SVG), replace `BarCodeImageFormat.Png`
      with the appropriate enum value:'
  - name: Saving to a memory stream
    text: 'Sometimes you want to embed the barcode directly into a web response or
      a PDF without touching the file system. Use a `MemoryStream`:'
  - name: Handling invalid input
    text: 'The `BarcodeGenerator` validates the payload against the chosen symbology.
      If the data contains prohibited characters, an `ArgumentException` is thrown.
      Wrap the generation code in a try‑catch block to provide a friendly error message:'
  - name: Scaling the barcode image
    text: 'You can change the image size without altering the encoded data by setting
      `Parameters.Image.Width` and `Parameters.Image.Height`:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Come generare un codice a barre Databar Expanded Stacked in C#
url: /it/python-java/general/how-to-generate-a-databar-expanded-stacked-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come generare un codice a barre databar expanded stacked in C#

Se hai bisogno di generare un **databar expanded stacked** barcode in C#, questa guida ti mostra come fare. La simbologia databar expanded stacked è ideale per codificare grandi quantità di dati in forma compatta, e puoi creare l'immagine con poche righe di codice. Imparerai anche come **generare immagini di codice a barre** in diversi formati e personalizzare righe o colonne per adattarle al tuo ambiente di scansione.

Questo tutorial copre tutto ciò di cui hai bisogno per iniziare a produrre codici a barre databar: installare la libreria necessaria, preparare la cartella di output, creare il codice a barre con righe o colonne personalizzate e salvare il risultato come file PNG. Alla fine, sarai in grado di **creare immagini di codice a barre databar** programmaticamente e adattare il codice ad altri formati immagine o scenari di runtime.

## Prerequisiti

* .NET 6.0 SDK o versioni successive (il codice funziona anche con .NET Core 3.1 e .NET Framework 4.7+)
* Un ambiente di sviluppo come Visual Studio 2022, Visual Studio Code o Rider
* Accesso a Internet per installare il pacchetto NuGet **Barcode Generator C#** (Aspose.BarCode per .NET)

> **Suggerimento professionale:** Se stai usando una pipeline CI/CD, aggiungi il riferimento al pacchetto NuGet nel file di progetto in modo che le build siano riproducibili.

## Installa la libreria Barcode Generator C# library

L'esempio utilizza la libreria Aspose.BarCode, che fornisce la classe `BarcodeGenerator` e l'enumerazione `EncodeTypes.DatabarExpandedStacked`.

```bash
dotnet add package Aspose.BarCode
```

Il comando aggiunge l'ultima versione stabile al tuo progetto. Dopo l'installazione, puoi importare lo spazio dei nomi nei tuoi file C#:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

## Prepara la cartella di output

Un percorso file affidabile previene errori di runtime quando la libreria tenta di scrivere l'immagine. Il codice seguente crea la directory se non esiste:

```csharp
using System;
using System.IO;

// Define the folder where barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);
```

> **Perché è importante:** Tentare di salvare in una directory inesistente genera un `IOException`. Creare la cartella in anticipo rende il codice robusto sia per lo sviluppo locale sia per gli ambienti di produzione.

## Generare un'immagine di codice a barre databar expanded stacked

### Generazione di base del codice a barre

Il modo più semplice per generare un'immagine **databar expanded stacked** è istanziare `BarcodeGenerator` con il valore `EncodeTypes` desiderato e un payload di testo semplice.

```csharp
// Create a barcode that encodes a long numeric string
var basicGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "01234567890123456789");

// Save the barcode as PNG
basicGenerator.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
    BarCodeImageFormat.Png);
```

Eseguendo lo snippet si genera `DatabarBasic.png` nella cartella *Barcodes*. L'immagine contiene un simbolo standard databar expanded stacked con il layout predefinito (4 colonne × 4 righe).

### Personalizzazione delle colonne – creare un codice a barre databar con 4 colonne

Puoi controllare il numero di colonne usando la proprietà `Parameters.Barcode.DataBar.Columns`. L'esempio seguente crea un codice a barre con **4 colonne** mantenendo il conteggio delle righe predefinito.

```csharp
// Step 1: Define a generator with custom column count
var columnGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the column count to 4 (default rows = 4)
columnGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the image
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
    BarCodeImageFormat.Png);
```

Il file risultante, **DatabarCols4.png**, appare così:

![Codice a barre databar expanded stacked con 4 colonne](databar_cols4.png "Codice a barre databar expanded stacked con 4 colonne – generato con C#")

*Testo alternativo dell'immagine (og_image_alt):* **Esempio di immagine di codice a barre databar expanded stacked generata con C#** – questo soddisfa il requisito SEO per il testo alternativo dell'immagine.

### Personalizzazione delle righe – creare un codice a barre databar con 3 righe

Allo stesso modo, puoi regolare il conteggio delle righe tramite `Parameters.Barcode.DataBar.Rows`. Il codice qui sotto genera un codice a barre con **3 righe** e il conteggio delle colonne predefinito (4).

```csharp
// Step 2: Define a generator with custom row count
var rowGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the row count to 3 (default columns = 4)
rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

// Save the image
rowGenerator.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
    BarCodeImageFormat.Png);
```

Il file **DatabarRows3.png** contiene un simbolo databar expanded stacked leggermente più corto in verticale, il che può essere utile per etichette con spazio limitato.

### Esportazione in altri formati

Se hai bisogno di un tipo di immagine diverso (ad esempio JPEG, BMP o SVG), sostituisci `BarCodeImageFormat.Png` con il valore enum appropriato:

```csharp
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
    BarCodeImageFormat.Jpeg);
```

La libreria supporta anche formati vettoriali come SVG, ideali per la stampa ad alta risoluzione.

## Scenari avanzati

### Salvataggio in uno stream di memoria

A volte vuoi incorporare il codice a barre direttamente in una risposta web o in un PDF senza toccare il file system. Usa un `MemoryStream`:

```csharp
using System.IO;

// Generate barcode into a memory stream
using var ms = new MemoryStream();
columnGenerator.Save(ms, BarCodeImageFormat.Png);

// Reset stream position before reading
ms.Position = 0;

// Example: return the stream as a file download in ASP.NET Core
// return File(ms.ToArray(), "image/png", "databar.png");
```

### Gestione di input non valido

`BarcodeGenerator` valida il payload rispetto alla simbologia scelta. Se i dati contengono caratteri proibiti, viene generata un'`ArgumentException`. Avvolgi il codice di generazione in un blocco try‑catch per fornire un messaggio di errore amichevole:

```csharp
try
{
    var gen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "INVALID*DATA");
    gen.Save(Path.Combine(outputFolder, "Invalid.png"), BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

### Ridimensionamento dell'immagine del codice a barre

Puoi modificare le dimensioni dell'immagine senza alterare i dati codificati impostando `Parameters.Image.Width` e `Parameters.Image.Height`:

```csharp
columnGenerator.Parameters.Image.Width = 300;   // pixels
columnGenerator.Parameters.Image.Height = 150; // pixels
columnGenerator.Save(Path.Combine(outputFolder, "DatabarLarge.png"),
    BarCodeImageFormat.Png);
```

Il ridimensionamento è utile quando il codice a barre deve soddisfare un requisito DPI specifico per gli scanner.

## Esempio completo funzionante

Di seguito trovi un'applicazione console completa, pronta per l'esecuzione, che dimostra tutti i passaggi descritti:

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace DatabarExpandedStackedDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Prepare output folder
            string outputFolder = Path.Combine(
                Environment.CurrentDirectory, "Barcodes");
            Directory.CreateDirectory(outputFolder);

            // 2️⃣ Generate basic barcode
            var basic = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "01234567890123456789");
            basic.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
                BarCodeImageFormat.Png);

            // 3️⃣ Generate barcode with 4 columns
            var colGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            colGen.Parameters.Barcode.DataBar.Columns = 4;
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
                BarCodeImageFormat.Png);

            // 4️⃣ Generate barcode with 3 rows
            var rowGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            rowGen.Parameters.Barcode.DataBar.Rows = 3;
            rowGen.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
                BarCodeImageFormat.Png);

            // 5️⃣ Export to JPEG as an extra format
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
                BarCodeImageFormat.Jpeg);

            Console.WriteLine("All barcode images have been generated in:");
            Console.WriteLine(outputFolder);
        }
    }
}
```

**Output previsto**


## Cosa dovresti imparare dopo?

I tutorial seguenti coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come impostare le colonne per un codice a barre Databar Expanded Stacked – guida completa C#](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [Come creare un esempio di generatore di codice a barre in C# con DataBar Expanded Stacked](/barcode/english/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/)
- [Guida al codice a barre databar expanded stacked – come generarlo e dimensionarlo in C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}