---
category: general
date: 2026-10-18
description: Scopri come creare un codice a barre PDF417 in C# con Aspose.BarCode.
  Questo tutorial copre la generazione di PDF417 base, compatto, macro e micro con
  codice completo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to create pdf417
language: it
lastmod: 2026-10-18
og_description: Crea un codice a barre PDF417 in C# con Aspose.BarCode. Segui questa
  guida per generare passo dopo passo codici a barre PDF417 base, compatti, macro
  e micro.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as an image file
og_title: Crea codice a barre PDF417 in C# – tutorial completo di Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to create PDF417 barcode in C# with Aspose.BarCode. This
    tutorial covers basic, compact, macro and micro PDF417 generation with full code.
  headline: Create PDF417 barcode in C# using Aspose.BarCode – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
- aspose
title: Crea il codice a barre PDF417 in C# usando Aspose.BarCode – guida passo passo
url: /it/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea codice a barre PDF417 in C# usando Aspose.BarCode – guida passo‑passo

Se hai bisogno di **creare un codice a barre PDF417** in un'applicazione .NET, questo tutorial ti guida attraverso l'intero processo. Vedrai come generare un codice a barre di base, abilitare la modalità compatta, aggiungere metadati macro e produrre una variante micro—tutto con spiegazioni chiare e codice eseguibile.

Generare codici a barre PDF417 è comune nella logistica, nella biglietteria e nella gestione dei documenti. Alla fine di questa guida sarai in grado di integrare la creazione di codici a barre in qualsiasi progetto C# senza strumenti esterni.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6.0 o successivo (il codice funziona anche con .NET Framework 4.7+)
* Visual Studio 2022 o qualsiasi IDE C#
* **Aspose.BarCode for .NET** pacchetto NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Permessi di scrittura su una cartella dove verranno salvati i file PNG generati

Non è necessaria alcuna configurazione aggiuntiva; la libreria gestisce tutti i dettagli di codifica a basso livello.

## Passo 1: Crea un codice a barre PDF417 di base

Il primo passo stabilisce un codice a barre PDF417 regolare con dimensione e numero di colonne personalizzati.

```csharp
using Aspose.BarCode.Generation;

// Initialize the generator for a standard PDF417 barcode
BarcodeGenerator basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

// Adjust the X‑dimension (module width) to 2 pixels for higher resolution
basicGen.Parameters.Barcode.XDimension.Pixels = 2;

// Set the number of columns – three columns keep the barcode compact yet readable
basicGen.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image
basicGen.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**Perché queste impostazioni sono importanti**

* `XDimension.Pixels` controlla la dimensione fisica di ogni elemento del codice a barre. Un valore di 2 produce un'immagine chiara sulla maggior parte degli schermi e delle stampanti.
* `Pdf417.Columns` determina quante colonne di dati contiene il codice a barre. Meno colonne riducono la larghezza; più colonne aumentano la capacità di dati.

L'esecuzione del codice crea `Pdf417Basic.png`, che appare come un tipico simbolo PDF417 con tre colonne di dati e una colonna completa di metadati sul lato destro.

## Passo 2: Abilita la modalità compatta (troncata)

La modalità compatta rimuove la colonna di metadati a destra, rendendo il codice a barre più stretto. È utile quando lo spazio è limitato ma i dati possono essere ricostruiti dalle righe rimanenti.

```csharp
// Turn on truncated mode to omit the metadata column
basicGen.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version
basicGen.Save(@"YOUR_DIRECTORY\CompactPdf417.png", BarCodeImageFormat.Png);
```

**Perché troncare?**  
Quando `Truncate` è `true`, il generatore omette la colonna opzionale a destra che memorizza la correzione d'errore e i metadati a livello di file. Il codice a barre risultante occupa meno colonne pur rimanendo leggibile dalla maggior parte dei lettori PDF417.

## Passo 3: Crea un codice a barre Macro PDF417 con metadati a livello di file

Macro PDF417 estende il formato standard con identificatori di segmento, consentendo a un documento grande di essere suddiviso in più codici a barre. È comodo per codificare stringhe lunghe o file multi‑pagina.

```csharp
// Initialize a generator for Macro PDF417
BarcodeGenerator macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");

// Set column count for better readability
macroGen.Parameters.Barcode.Pdf417.Columns = 5;

// Assign macro-specific identifiers
macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Unique file identifier
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;      // Current segment number
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total segments

// Save the macro barcode
macroGen.Save(@"YOUR_DIRECTORY\MacroPdf417.png", BarCodeImageFormat.Png);
```

**Spiegazione dei campi macro**

| Proprietà | Scopo |
|-----------|-------|
| `MacroPdf417FileID` | Identificatore unico per l'intero file; tutti i segmenti condividono questo valore. |
| `MacroPdf417SegmentID` | Indice del segmento corrente (parte da 1). |
| `MacroPdf417SegmentsCount` | Numero totale di segmenti che compongono l'insieme completo di dati. |

Uno scanner che comprende Macro PDF417 può ricomporre i dati originali leggendo tutti i segmenti e utilizzando questi identificatori.

## Passo 4: Crea un codice a barre Micro PDF417 per dati brevi

Micro PDF417 è una versione compatta progettata per piccoli payload (fino a 90 caratteri). Limita l'intervallo di colonne a 1‑4, rendendo il codice a barre adatto a etichette minuscole o dispositivi con area di visualizzazione limitata.

```csharp
// Initialize a generator for Micro PDF417
BarcodeGenerator microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");

// Set a fine X‑dimension for crisp rendering
microGen.Parameters.Barcode.XDimension.Pixels = 2;

// Choose a column count within the allowed range (1‑4)
microGen.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode
microGen.Save(@"YOUR_DIRECTORY\MicroPdf417.png", BarCodeImageFormat.Png);
```

**Quando usare Micro PDF417**  
Utilizza questa variante quando il payload di dati è breve e hai bisogno del codice a barre più piccolo possibile. È ideale per etichette di inventario, carte di accesso o qualsiasi scenario in cui lo spazio sullo schermo è prezioso.

## Esempio completo funzionante

Di seguito trovi un'applicazione console autonoma che genera tutti e quattro i tipi di codice a barre in un'unica esecuzione. Copia il codice in un nuovo progetto C#, sostituisci `YOUR_DIRECTORY` con un percorso di cartella esistente e avvialo.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Adjust this path to a writable folder on your machine
            string outputPath = @"C:\Barcodes";

            // ---------- Basic PDF417 ----------
            var basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            basicGen.Parameters.Barcode.XDimension.Pixels = 2;
            basicGen.Parameters.Barcode.Pdf417.Columns = 3;
            basicGen.Save($"{outputPath}\\Pdf417Basic.png", BarCodeImageFormat.Png);

            // ---------- Compact PDF417 ----------
            basicGen.Parameters.Barcode.Pdf417.Truncate = true;
            basicGen.Save($"{outputPath}\\CompactPdf417.png", BarCodeImageFormat.Png);

            // ---------- Macro PDF417 ----------
            var macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");
            macroGen.Parameters.Barcode.Pdf417.Columns = 5;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
            macroGen.Save($"{outputPath}\\MacroPdf417.png", BarCodeImageFormat.Png);

            // ---------- Micro PDF417 ----------
            var microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");
            microGen.Parameters.Barcode.XDimension.Pixels = 2;
            microGen.Parameters.Barcode.Pdf417.Columns = 4; // valid range: 1‑4
            microGen.Save($"{outputPath}\\MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("All PDF417 barcodes have been generated successfully.");
        }
    }
}
```

**Output previsto**

L'esecuzione del programma crea quattro file PNG nella cartella specificata:

* `Pdf417Basic.png` – codice a barre standard con tre colonne
* `CompactPdf417.png` – stessi dati, colonna destra troncata
* `MacroPdf417.png` – codice a barre macro contenente i metadati di segmento
* `MicroPdf417.png` – codice a barre micro compatto per stringhe brevi

Apri qualsiasi immagine con un visualizzatore; vedrai i distinti pattern PDF417. Scansionandoli con un lettore di codici a barre mobile (ad es., ZXing, Scandit) otterrai le stringhe di testo originali.

## Domande frequenti e consigli

* **E se il codice a barre appare sfocato?**  
  Aumenta `XDimension.Pixels` a 3 o 4. Dimensioni di modulo più grandi producono immagini ad alta risoluzione, a costo di un file più grande.

* **Posso generare SVG invece di PNG?**  
  Sì. Sostituisci `BarCodeImageFormat.Png` con `BarCodeImageFormat.Svg` nelle chiamate `Save`.

* **Devo impostare manualmente il livello di correzione d'errore?**  
  Aspose.BarCode sceglie automaticamente un livello ottimale. Per casi d'uso specializzati puoi regolare `Pdf417.ErrorCorrectionLevel`.

* **Come incorporare il codice a barre in un documento PDF?**  
  Usa `Aspose.Pdf` per aggiungere il PNG o l'SVG generato come elemento immagine su una pagina PDF.

* **La libreria è thread‑safe?**  
  Ogni istanza di `BarcodeGenerator` è indipendente; puoi creare generatori su più thread senza stato condiviso.

## Conclusione

Ora sai come **creare un codice a barre PDF417** in C# usando Aspose.BarCode, coprendo le varianti base, compatta, macro e micro.

## Cosa dovresti imparare dopo?

I seguenti tutorial trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come creare un codice a barre pdf417 in C# – guida passo‑passo](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [Come creare un codice a barre PDF417 in C# con modalità compatta](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [Come creare un codice a barre macro PDF417 in C# usando Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}