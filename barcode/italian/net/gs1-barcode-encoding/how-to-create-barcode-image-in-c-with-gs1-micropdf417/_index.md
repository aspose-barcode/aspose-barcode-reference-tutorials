---
category: general
date: 2026-11-14
description: Scopri come creare un'immagine di codice a barre in C# usando Aspose.BarCode.
  Questa guida passo passo copre la configurazione del generatore di codici a barre
  in C#, la formattazione GS1 e l'esportazione in PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to generate barcode
- barcode generator c#
- create gs1 barcode
- barcode image from data
language: it
lastmod: 2026-11-14
og_description: Crea rapidamente un'immagine di codice a barre in C#. Segui questa
  guida per imparare a generare codici a barre, utilizzare il generatore di codici
  a barre in C# ed esportare un PNG GS1 MicroPDF417.
og_image_alt: Screenshot of a GS1 MicroPDF417 barcode generated in C#
og_title: Crea immagine di codice a barre in C# – guida completa per GS1 MicroPDF417
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to create barcode image in C# using Aspose.BarCode. This
    step‑by‑step guide covers barcode generator c# setup, GS1 formatting and PNG export.
  headline: How to create barcode image in C# with GS1 MicroPDF417
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Come creare un'immagine di codice a barre in C# con GS1 MicroPDF417
url: /it/net/gs1-barcode-encoding/how-to-create-barcode-image-in-c-with-gs1-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un'immagine di barcode in C# con GS1 MicroPDF417

Se hai bisogno di **creare un'immagine di barcode** in C#, questa guida ti mostra una soluzione completa, pronta‑all‑uso. Vedrai **come generare i dati del barcode** secondo lo standard GS1, configurare il generatore e esportare un file PNG di alta qualità.

Il tutorial copre tutto, dall'installazione della libreria necessaria alla gestione delle comuni insidie di formattazione dei dati. Alla fine sarai in grado di produrre una **immagine di barcode dai dati** con poche righe di codice, e comprenderai perché ogni impostazione è importante.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6.0 o successivo installato (il codice funziona anche con .NET Framework 4.7+).
* Un IDE come Visual Studio 2022 o Visual Studio Code.
* Il pacchetto NuGet **Aspose.BarCode for .NET**. Installalo con:

```bash
dotnet add package Aspose.BarCode
```

* Familiarità di base con la sintassi C# e il formato GS1 Application Identifier (AI).

> **Pro tip:** Mantieni la versione della libreria aggiornata; l'ultima release aggiunge supporto per nuove simbologie di barcode e miglioramenti di prestazioni.

## Creare un'immagine di barcode con BarcodeGenerator

Questa sezione contiene l'implementazione principale. Il codice crea un'istanza **barcode generator c#**, configura la dimensione X per la leggibilità e salva il risultato come file PNG.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialise the generator with the GS1 MicroPDF417 symbology
// The data string follows the GS1 syntax: (01)GTIN(21)SerialNumber
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,
    "(01)12345678901234(21)ABC123");

// Step 2: Adjust the module width (X‑dimension) to improve scan reliability
// A value of 2 pixels works well for most screen‑displayed barcodes.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Export the barcode as a PNG image
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "GS1MicroPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
```

### Perché ogni riga è importante

* **EncodeTypes.MicroPdf417** indica alla libreria di usare la simbologia GS1 MicroPDF417, compatta e ideale per la scansione mobile.
* La **stringa dei dati** deve iniziare con il GS1 AI `(01)` per il Global Trade Item Number (GTIN) seguito da `(21)` per il numero di serie. Se il formato è errato, il generatore genera un'eccezione.
* **XDimension.Pixels** controlla la larghezza della barra più piccola. Un valore più grande aumenta la leggibilità su display a bassa risoluzione, mentre un valore più piccolo riduce le dimensioni dell'immagine.
* **BarCodeImageFormat.Png** produce un'immagine lossless, preservando i bordi netti necessari per una scansione affidabile.

Eseguendo il programma viene creato `GS1MicroPdf417.png` sul desktop. Aprendo il file si vede un barcode denso, nero su bianco, che codifica il GTIN `12345678901234` e il seriale `ABC123`.

## Come generare un barcode usando GS1 MicroPDF417

Se sei nuovo al formato GS1, ecco le regole essenziali:

| GS1 AI | Significato                     | Esempio               |
|--------|---------------------------------|-----------------------|
| (01)   | Global Trade Item Number        | 12345678901234        |
| (21)   | Numero di serie (opzionale)     | ABC123                |

Quando concatenati gli AI con i loro valori, avvolgi ogni AI tra parentesi e posiziona i valori subito dopo. La stringa risultante può essere passata al **barcode generator c#** senza ulteriori codifiche.

### Insidie comuni

* **Parentisi mancanti** – Il generatore tratta la stringa come dati grezzi e non applica i controlli GS1.
* **Superamento dei limiti di lunghezza** – MicroPDF417 supporta fino a 155 caratteri. Rimuovi spazi inutili.
* **Caratteri non validi** – Sono consentiti solo caratteri numerici per il GTIN; il seriale può includere lettere maiuscole e cifre.

## Personalizzare l'immagine del barcode dai dati

Oltre alla dimensione X di base, Aspose.BarCode offre molte regolazioni visive. Di seguito alcuni aggiustamenti che potresti applicare a seconda dei requisiti del tuo progetto.

```csharp
// Set background to transparent (useful for overlaying on UI)
generator.Parameters.ImageBackgroundColor = Color.Transparent;

// Change foreground color to dark blue for branding
generator.Parameters.Barcode.BarColor = Color.FromArgb(0, 0, 139);

// Increase image resolution to 300 dpi for print‑ready output
generator.Parameters.ImageResolution = 300;
```

Ogni impostazione è opzionale; i valori predefiniti producono già un **barcode image** pulito e leggibile. Sperimenta con colori e risoluzioni solo dopo aver verificato che gli scanner riescano ancora a leggere il codice.

## Salvare il barcode in altri formati

Sebbene PNG sia il formato più comune per web e mobile, potresti aver bisogno di JPEG, BMP o SVG. Il metodo `Save` accetta qualsiasi valore di `BarCodeImageFormat`.

```csharp
generator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
generator.Save("barcode.svg", BarCodeImageFormat.Svg);
```

* JPEG riduce le dimensioni del file ma introduce artefatti di compressione che possono influire sulla leggibilità.
* SVG conserva la qualità vettoriale ed è ideale per design web responsivi.

## Verificare il barcode generato

Un modo rapido per confermare che il passaggio **create barcode image** sia riuscito è usare un'app scanner mobile che supporti GS1 MicroPDF417. Scansiona il PNG salvato; l'app dovrebbe mostrare:

```
GTIN: 12345678901234
Serial: ABC123
```

Se lo scanner segnala un errore, ricontrolla la formattazione degli AI e il valore della dimensione X.

## Esempio completo – programma console autonomo

Di seguito trovi un programma completo che puoi copiare, incollare e eseguire senza modifiche (eccetto il passaggio di installazione del NuGet).

```csharp
using System;
using System.IO;
using System.Drawing;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with GS1 MicroPDF417 and sample data
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "(01)12345678901234(21)ABC123");

            // Improve readability by setting module width
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Optional visual customisation
            generator.Parameters.ImageBackgroundColor = Color.Transparent;
            generator.Parameters.Barcode.BarColor = Color.FromArgb(0, 0, 139);
            generator.Parameters.ImageResolution = 300;

            // Define output path (Desktop folder)
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "GS1MicroPdf417.png");

            // Save the barcode as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to: {outputPath}");
        }
    }
}
```

Quando esegui il programma, la console stampa il percorso completo del file e il PNG appare sul desktop. Questo esempio dimostra **come generare barcode** dai dati, personalizzare l'aspetto e esportare una **barcode image from data** in un unico flusso di lavoro coeso.

## Domande frequenti

| Domanda | Risposta |
|----------|----------|
| *Posso generare altre simbologie GS1?* | Sì. Sostituisci `EncodeTypes.MicroPdf417` con `EncodeTypes.Pdf417`, `EncodeTypes.DataMatrix`, ecc., e adatta di conseguenza la stringa dei dati. |
| *Cosa succede se i miei dati superano la capacità del MicroPDF417?* | Passa alla simbologia PDF417 regolare, che supporta payload più lunghi. |
| *Ho bisogno di una licenza per Aspose.BarCode?* | Una licenza di valutazione gratuita funziona per lo sviluppo. Per la produzione, acquista una licenza per rimuovere il watermark di valutazione. |
| *Il PNG è adatto per la stampa su etichette?* | Aumenta `ImageResolution` a 300 dpi o più, e considera di salvare come TIFF per stampanti industriali. |

## Conclusione

Ora sai come **creare un'immagine di barcode** in C# usando l'approccio **barcode generator c#**, formattare i dati per uno scenario **create gs1 barcode** e esportare il risultato come PNG o altro tipo di immagine. L'esempio completo dimostra ogni passaggio—from preparazione dei dati alla personalizzazione visiva—così da poter integrare la creazione di barcode in qualsiasi applicazione .NET.

Successivamente, esplora argomenti correlati come **barcode image from data** per i QR code, aggiungere più barcode a un unico PDF, o automatizzare la generazione batch per sistemi di inventario. Sperimenta con diversi valori di dimensione X e formati immagine per trovare il punto ottimale per il tuo ambiente di scansione.

Buona programmazione, e lascia che le tue applicazioni inizino **a creare immagini di barcode** affidabili nel mondo reale!

## Cosa dovresti imparare dopo?

I tutorial seguenti coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [How to create barcode image with Aspose.Barcode in C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [How to create postal barcode image in C# using Aspose.BarCode](/barcode/english/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/)
- [How to create PDF417 barcode image in C# – complete guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}