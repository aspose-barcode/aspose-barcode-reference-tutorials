---
category: general
date: 2026-09-22
description: Scopri come creare un codice a barre PDF417 in C#, impostare le dimensioni
  del codice a barre e generare file immagine del codice a barre con chiari esempi
  di codice passo‑passo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to create PDF417
- set barcode size
- create barcode image c#
language: it
lastmod: 2026-09-22
og_description: Crea codici a barre PDF417 in C# rapidamente. Questo tutorial mostra
  come impostare le dimensioni del codice a barre, abilitare la modalità compatta
  e generare immagini PNG per qualsiasi progetto .NET.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Crea codice a barre PDF417 in C# – guida passo passo
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to create PDF417 barcode in C#, set barcode size, and generate
    barcode image files with clear step‑by‑step code examples.
  headline: How to create PDF417 barcode and set its size in C#
  type: TechArticle
tags:
- PDF417
- C#
- Barcode
- Imaging
title: Come creare un codice a barre PDF417 e impostarne le dimensioni in C#
url: /it/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un codice a barre PDF417 e impostarne le dimensioni in C#

Se hai bisogno di **creare un codice a barre PDF417** in C#, questa guida ti mostra come generare il codice a barre, controllarne le dimensioni e salvare il risultato come file immagine. Che tu stia costruendo un sistema di biglietteria, un'etichetta logistica o un documento sicuro, padroneggiare il formato PDF417 ti consente di codificare grandi quantità di dati in una forma visiva compatta.

In questo tutorial imparerai a:

* **Create PDF417 barcode** con la libreria Aspose.BarCode (o qualsiasi compatibile).  
* **Set barcode size** regolando la X‑dimension e il numero di colonne.  
* Genera un **barcode image in C#** per output PNG, JPEG o BMP.  

L'esempio utilizza l'edizione community gratuita di Aspose.BarCode per .NET, ma gli stessi concetti si applicano ad altre librerie che espongono proprietà simili.

## Prerequisiti

* .NET 6.0 SDK o versioni successive installato.  
* Un IDE C# (Visual Studio, Visual Studio Code, Rider, ecc.).  
* Il pacchetto NuGet `Aspose.BarCode` (`dotnet add package Aspose.BarCode`).  

Non è necessaria alcuna configurazione aggiuntiva; la libreria funziona su Windows, Linux e macOS.

## Passo 1: Creare un codice a barre PDF417 di base e impostarne le dimensioni

Il primo passo è istanziare un `BarcodeGenerator` con l'enumerazione `EncodeTypes.Pdf417` e fornire il testo da codificare. Quindi regola la **X‑dimension** (larghezza del modulo) e il numero di **colonne** per controllare le dimensioni complessive.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Define the text that the barcode will represent.
string data = "Sample text for PDF417 barcode";

// Create a basic PDF417 barcode generator.
var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Set the module width to 2 pixels (controls bar thickness).
basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Set the column count; 3 columns yields a compact visual but still readable.
basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image.
string basicPath = Path.Combine("YOUR_DIRECTORY", "Pdf417Basic.png");
basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
```

**Perché queste impostazioni sono importanti**

* `XDimension.Pixels` determina la larghezza della barra più stretta. Valori più piccoli producono un codice a barre più compatto, mentre valori più grandi aumentano la leggibilità su scanner a bassa risoluzione.  
* `Pdf417.Columns` influenza il rapporto d'aspetto del codice a barre. Meno colonne rendono il codice più alto; più colonne lo appiattiscono. Regolare le colonne è il modo principale per **set barcode size** senza modificare i dati codificati.

Dopo aver eseguito il codice, troverai `Pdf417Basic.png` nella cartella specificata. L'immagine è simile allo screenshot qui sotto:

<img src="images/pdf417-basic.png" alt="esempio di creazione di codice a barre PDF417 che mostra il layout di base del codice a barre">

## Passo 2: Creare un codice a barre PDF417 compatto (modalità truncate) con le stesse dimensioni

A volte è necessario un codice a barre più corto per spazi limitati. PDF417 offre una modalità *truncate* (compatta) che rimuove il pattern di stop e riduce l'altezza complessiva. La proprietà `Truncate` attiva/disattiva questo comportamento.

```csharp
// Reuse the same data string.
var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Keep the same module width and column count for a fair size comparison.
compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Enable compact (truncate) mode – this removes the stop pattern.
compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version.
string compactPath = Path.Combine("YOUR_DIRECTORY", "CompactPdf417.png");
compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
```

**Cosa cambia con `Truncate = true`?**

* Il codice a barre diventa circa il 15‑20 % più corto verticalmente, il che è utile per etichette piccole o schermi mobili.  
* I dati rimangono completamente recuperabili; la maggior parte degli scanner moderni comprende automaticamente la modalità truncate.

Il risultato `CompactPdf417.png` appare come una versione più sottile del codice a barre di base.

## Passo 3: Creare un codice a barre Micro PDF417, regolare le colonne e salvarlo

Micro PDF417 è una variante più recente ad alta densità progettata per spazi molto piccoli (ad es., carte d'identità). Supporta solo 1‑4 colonne, e la libreria espone la stessa proprietà `XDimension` per il controllo delle dimensioni.

```csharp
// Create a Micro PDF417 generator.
var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);

// Set module width – 2 pixels works well for most printers.
microPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Micro PDF417 allows only 1 to 4 columns; choose 4 for a more square shape.
microPdf417.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode.
string microPath = Path.Combine("YOUR_DIRECTORY", "MicroPdf417.png");
microPdf417.Save(microPath, BarCodeImageFormat.Png);
```

**Punti chiave per Micro PDF417**

* L'enumerazione `EncodeTypes.MicroPdf417` seleziona automaticamente la variante micro.  
* Poiché il simbolo è più denso, potresti aver bisogno di una stampante a DPI più elevato (300 dpi o più) per mantenere il codice leggibile.  
* Regolare il conteggio delle colonne è l'unico controllo di dimensione disponibile; la libreria rispetta comunque `XDimension`.

## Come impostare le dimensioni del codice a barre per diversi formati di output

Gli esempi sopra usano PNG, ma lo stesso metodo `Save` funziona con JPEG, BMP o TIFF. Se ti serve una dimensione immagine specifica (ad es., 300 × 150 px), combina `XDimension` con `ResolutionX`/`ResolutionY`:

```csharp
basicPdf417.Parameters.ImageResolution = 300; // DPI
basicPdf417.Parameters.Barcode.XDimension.Pixels = 3; // larger modules for higher DPI
basicPdf417.Save("Pdf417HighRes.jpg", BarCodeImageFormat.Jpeg);
```

Aumentare `ImageResolution` mentre si scala `XDimension` preserva la qualità visiva su stampe ad alta risoluzione.

## Problemi comuni e consigli professionali

| Problema | Perché succede | Soluzione |
|----------|----------------|-----------|
| Il codice a barre appare sfocato sullo schermo | Bassa DPI combinata con `XDimension` piccola | Aumenta `ImageResolution` e/o `XDimension.Pixels` |
| Lo scanner non riesce a leggere la modalità truncate | Il firmware dello scanner più vecchio non supporta la modalità | Usa la modalità completa (non troncata) per hardware legacy |
| Micro PDF417 non è leggibile | Stampato a < 300 dpi o con contrasto insufficiente | Stampa su carta opaca a 300 dpi o più, assicurando uno sfondo scuro |
| Il file di output è corrotto | Mancano i permessi di scrittura nella cartella di destinazione | Verifica che `YOUR_DIRECTORY` esista e sia scrivibile |

**Consiglio professionale:** Genera sempre il codice a barre come PNG quando hai bisogno di qualità lossless per ulteriori elaborazioni (ad es., incorporamento in PDF). PNG conserva i valori dei pixel esatti, mentre JPEG introduce artefatti di compressione che possono influire sulla leggibilità del codice a barre.

## Esempio completo, eseguibile

Di seguito è riportata un'applicazione console completa che dimostra tutti e tre i tipi di codice a barre in un'unica esecuzione. Copia il codice in un nuovo progetto console .NET ed eseguilo.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // The text to encode – change this to whatever data you need.
        const string data = "Sample text for PDF417 barcode";

        // Directory where images will be saved.
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // ---------- Basic PDF417 ----------
        var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        string basicPath = Path.Combine(outputDir, "Pdf417Basic.png");
        basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Basic PDF417 saved to {basicPath}");

        // ---------- Compact (Truncate) PDF417 ----------
        var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;
        string compactPath = Path.Combine(outputDir, "CompactPdf417.png");
        compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Compact PDF417 saved to {compactPath}");

        // ---------- Micro PDF417 ----------
        var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);
        microPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        microPdf417.Parameters.Barcode.Pdf417.Columns = 4; // 1‑4 allowed
        string microPath = Path.Combine(outputDir, "MicroPdf417.png");
        microPdf417.Save(microPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Micro PDF417 saved to {microPath}");
    }
}
```

**Output previsto**

Eseguendo il programma vengono creati tre file PNG all'interno della cartella `Barcodes`:

* `Pdf417Basic.png` – un codice a barre PDF417 standard con tre colonne.  
* `CompactPdf417.png` – gli stessi dati in modalità truncate (compatta), leggermente più corto.  
* `MicroPdf417.png` – una variante Micro PDF417 ad alta densità con quattro colonne.

Apri qualsiasi immagine con un visualizzatore; dovresti vedere il caratteristico layout impilato

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come creare un codice a barre – PDF417 compatto con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Come impostare il livello di errore nel codice a barre PDF417 – Guida completa](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Creare metadati del codice a barre PDF417 in C# – Guida completa passo‑passo](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}