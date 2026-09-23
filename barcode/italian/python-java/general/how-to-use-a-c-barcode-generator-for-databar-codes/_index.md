---
category: general
date: 2026-09-23
description: Il tutorial del generatore di codici a barre C# mostra come generare
  immagini di codici a barre con proporzioni personalizzate utilizzando la libreria
  Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- DataBar barcode C#
- barcode aspect ratio
- Aspose.BarCode C#
- barcode image export
language: it
lastmod: 2026-09-23
og_description: Guida al generatore di codici a barre C# che ti accompagna nella creazione
  di immagini di codici a barre, nella regolazione dei rapporti d'aspetto e nell'esportazione
  di file PNG utilizzando Aspose.BarCode.
og_image_alt: Screenshot of a barcode created with a C# barcode generator
og_title: Crea codici a barre di alta qualità con un generatore di codici a barre
  C#
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  headline: How to use a C# barcode generator for DataBar codes
  type: TechArticle
- description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  name: How to use a C# barcode generator for DataBar codes
  steps:
  - name: Switching to another barcode type
    text: 'If you need a QR code, Code 128, or PDF417, replace the enum value in the
      constructor:'
  - name: Handling unsupported characters
    text: 'The `BarcodeGenerator` validates the input string against the selected
      symbology. Supplying an illegal character throws an `ArgumentException`. Wrap
      the creation in a try‑catch block to provide a friendly error message:'
  - name: Exporting to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the second argument
      of `Save` accordingly:'
  - name: High‑resolution output for printing
    text: 'When printing on high‑DPI printers, increase the X‑dimension and optionally
      set the `Resolution` property:'
  type: HowTo
tags:
- barcode
- c#
- Aspose
title: Come usare un generatore di codici a barre C# per i codici DataBar
url: /it/python-java/general/how-to-use-a-c-barcode-generator-for-databar-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come utilizzare un generatore di codici a barre C# per i codici DataBar

Se hai bisogno di un **c# barcode generator** in grado di produrre simboli DataBar stacked Omni‑Directional, questa guida ti fornisce una soluzione completa, pronta all'uso. Vedrai come generare immagini di codici a barre, controllare la X‑dimension e modificare il rapporto d'aspetto senza uscire dall'IDE.

Generare codici a barre è una necessità comune per sistemi di inventario, etichette di spedizione e applicazioni point‑of‑sale. Alla fine di questo tutorial potrai creare file PNG con qualsiasi rapporto d'aspetto tu scelga e comprenderai come adattare il codice ad altri tipi di codici a barre.

## Prerequisiti

* .NET 6.0 SDK o versioni successive installate  
* Visual Studio 2022 (o qualsiasi editor C# tu preferisca)  
* Un riferimento NuGet a **Aspose.BarCode** – la libreria che alimenta la classe `BarcodeGenerator`  

Non è necessaria una libreria grafica separata; Aspose.BarCode gestisce internamente la codifica delle immagini.

## Passo 1: Installare il pacchetto NuGet Aspose.BarCode

Apri un terminale nella cartella del tuo progetto ed esegui:

```bash
dotnet add package Aspose.BarCode
```

Il comando aggiunge l'ultima versione stabile della libreria al file del tuo progetto, rendendo disponibile la classe `BarcodeGenerator`.

## Passo 2: Definire la cartella di output

Scegli una cartella dove verranno salvati i file PNG generati. L'uso di un percorso assoluto o relativo funziona allo stesso modo, ma un percorso relativo mantiene il progetto portabile.

```csharp
// Define the output folder (relative to the project root)
string outputFolder = "GeneratedBarcodes/";
Directory.CreateDirectory(outputFolder); // Ensure the folder exists
```

Creare la directory programmaticamente evita errori di runtime se la cartella è assente.

## Passo 3: Istanziare il generatore di codici a barre C# con dati di esempio

Il costruttore `BarcodeGenerator` richiede due argomenti: il tipo di codice a barre e la stringa di dati. Per un simbolo DataBar stacked Omni‑Directional utilizzi `EncodeTypes.DatabarStackedOmniDirectional`.

```csharp
// Create a barcode generator for a DataBar stacked Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

La stringa di dati segue il formato GS1 Application Identifier. L'enumerazione `EncodeTypes` contiene oltre 150 standard di codici a barre; è possibile passare a un altro tipo modificando il valore dell'enum.

## Passo 4: Impostare la X‑dimension (dimensione in pixel) per il codice a barre

La X‑dimension controlla la larghezza della barra più stretta. Un valore di 2 pixel produce un'immagine nitida ad alta risoluzione adatta alla maggior parte degli schermi.

```csharp
// Set the X‑dimension to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Regolare la X‑dimension è opzionale, ma ti offre un controllo fine sulla densità visiva del codice a barre.

## Passo 5: Generare un codice a barre con un rapporto d'aspetto di 15 e salvarlo come PNG

La proprietà `AspectRatio` appartiene al sotto‑oggetto `DataBar`. Modificando questo valore si allunga o si comprime il codice a barre verticalmente mantenendo intatti i dati codificati.

```csharp
// Set aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Il metodo `Save` scrive il codice a barre nel percorso file specificato. L'enum `BarCodeImageFormat.Png` garantisce una compressione senza perdita.

![esempio di output del generatore di codici a barre c#](generated_barcode_example.png)

*Immagine: codice a barre generato con un rapporto d'aspetto di 15.*

## Passo 6: Modificare il rapporto d'aspetto a 30 e generare una seconda immagine

Riutilizzare la stessa istanza di `BarcodeGenerator` evita di allocare un nuovo oggetto. Basta aggiornare `AspectRatio` e chiamare nuovamente `Save`.

```csharp
// Update aspect ratio to 30 and save a second image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

Ora hai due file PNG che differiscono solo nella scala verticale. Questa tecnica è utile quando è necessario rendere gli stessi dati per etichette di dimensioni diverse.

## Varianti comuni e casi limite

### Passare a un altro tipo di codice a barre

Se ti serve un QR code, Code 128 o PDF417, sostituisci il valore dell'enum nel costruttore:

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(
    EncodeTypes.QR, "https://example.com");
```

Tutti gli altri passaggi di configurazione (X‑dimension, salvataggio) rimangono identici.

### Gestire caratteri non supportati

Il `BarcodeGenerator` valida la stringa di input rispetto alla simbologia selezionata. Fornire un carattere non consentito genera un `ArgumentException`. Avvolgi la creazione in un blocco try‑catch per fornire un messaggio di errore più amichevole:

```csharp
try
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid data for the selected barcode type: {ex.Message}");
}
```

### Esportare in altri formati immagine

Aspose.BarCode supporta BMP, JPEG, TIFF e SVG. Modifica il secondo argomento di `Save` di conseguenza:

```csharp
barcodeGenerator.Save($"{outputFolder}Databar.svg", BarCodeImageFormat.Svg);
```

### Output ad alta risoluzione per la stampa

Quando si stampa su stampanti ad alta DPI, aumenta la X‑dimension e, facoltativamente, imposta la proprietà `Resolution`:

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.ImageResolution.Dpi = 300;
```

Queste impostazioni producono file più grandi ma mantengono bordi nitidi sui supporti fisici.

## Output previsto

Eseguendo il programma completo vengono creati i seguenti file all'interno di `GeneratedBarcodes/`:

* `DatabarAspectRatio15.png` – un codice DataBar di altezza standard  
* `DatabarAspectRatio30.png` – una versione allungata verticalmente  

Entrambe le immagini contengono gli stessi dati GS1 codificati e puoi verificarle con qualsiasi app scanner di codici a barre.

## Codice sorgente completo

Copia il codice qui sotto in un nuovo progetto console (`dotnet new console`) ed eseguilo. Il programma stampa messaggi di stato sulla console e scrive i file PNG su disco.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Define the output folder
        string outputFolder = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputFolder);

        // Step 3: Create a C# barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Step 4: Set common barcode properties (pixel size of X‑dimension)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 5: Generate a barcode with aspect ratio 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        string file15 = Path.Combine(outputFolder, "DatabarAspectRatio15.png");
        barcodeGenerator.Save(file15, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

        // Step 6: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        string file30 = Path.Combine(outputFolder, "DatabarAspectRatio30.png");
        barcodeGenerator.Save(file30, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
    }
}
```

L'esecuzione del programma produce un output console simile a:

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

## Conclusione

Ora disponi di un **c# barcode generator** in grado di creare simboli DataBar stacked Omni‑Directional, regolare la X‑dimension e esportare file PNG con rapporti d'aspetto personalizzati. Lo stesso schema funziona per qualsiasi altra simbologia di codici a barre supportata da Aspose.BarCode, facilitando l'integrazione della generazione di codici a barre in soluzioni di inventario, spedizione o point‑of‑sale.

Se vuoi approfondire, prova:

* Generare codici QR o simboli PDF417 (`how to generate barcode` per app mobile)  
* Esportare in SVG per grafica web scalabile  
* Incorporare le immagini generate direttamente nelle fatture PDF usando Aspose.PDF  

Sperimenta con diversi valori di `AspectRatio`, dimensioni della X‑dimension e formati di output per corrispondere esattamente

## Cosa dovresti imparare dopo?

I tutorial seguenti coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}