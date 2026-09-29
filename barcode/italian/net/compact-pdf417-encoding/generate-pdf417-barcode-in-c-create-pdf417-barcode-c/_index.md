---
category: general
date: 2026-07-24
description: Genera il codice a barre PDF417 in C# usando Aspose.BarCode. Scopri come
  creare un codice a barre PDF417 in C# con modalità compatta in pochi minuti.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- create pdf417 barcode c#
- c# barcode generator pdf417
- how to generate pdf417 barcode
language: it
lastmod: 2026-07-24
og_description: Genera rapidamente codici a barre PDF417 in C# con Aspose.BarCode.
  Questo tutorial ti mostra come creare un codice a barre PDF417 in C# in modalità
  compatta, coprendo configurazione, codice e verifica.
og_image_alt: Screenshot of generated compact PDF417 barcode saved as PNG using C#
  code
og_title: Genera codice a barre PDF417 in C# – Guida rapida
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Generate PDF417 barcode in C# using Aspose.BarCode. Learn how to create
    PDF417 barcode C# with compact mode in minutes.
  headline: Generate PDF417 Barcode in C# – Create PDF417 Barcode C#
  type: TechArticle
- description: Generate PDF417 barcode in C# using Aspose.BarCode. Learn how to create
    PDF417 barcode C# with compact mode in minutes.
  name: Generate PDF417 Barcode in C# – Create PDF417 Barcode C#
  steps:
  - name: '**Data definition** – PDF417 can store up to ~1850 characters, but we keep
      it short for the demo. Unicode support means those accented characters won’t
      break anything.'
    text: '**Data definition** – PDF417 can store up to ~1850 characters, but we keep
      it short for the demo. Unicode support means those accented characters won’t
      break anything.'
  - name: '**Generator construction** – The `EncodeTypes.Pdf417` enum value tells
      Aspose which symbology to use; swapping it for `EncodeTypes.QR` would give you
      a QR code instead.'
    text: '**Generator construction** – The `EncodeTypes.Pdf417` enum value tells
      Aspose which symbology to use; swapping it for `EncodeTypes.QR` would give you
      a QR code instead.'
  - name: '**X‑dimension** – This controls the width of each module (the tiny squares
      that make up the barcode). A value of `2` pixels yields a crisp image that’s
      still readable when printed at 300 dpi.'
    text: '**X‑dimension** – This controls the width of each module (the tiny squares
      that make up the barcode). A value of `2` pixels yields a crisp image that’s
      still readable when printed at 300 dpi.'
  - name: '**PDF417 options** – `Columns` influences the barcode’s aspect ratio; fewer
      columns make the image taller, which can be useful for receipts. `Truncate`
      (also called *Compact mode*) removes the start/stop pattern padding, reducing
      file size without sacrificing data integrity.'
    text: '**PDF417 options** – `Columns` influences the barcode’s aspect ratio; fewer
      columns make the image taller, which can be useful for receipts. `Truncate`
      (also called *Compact mode*) removes the start/stop pattern padding, reducing
      file size without sacrificing data integrity.'
  - name: '**Output path** – Using `Environment.CurrentDirectory` ensures the image
      lands next to the executable, making it easy to locate during development.'
    text: '**Output path** – Using `Environment.CurrentDirectory` ensures the image
      lands next to the executable, making it easy to locate during development.'
  - name: '**Saving** – `BarCodeImageFormat.Png` gives lossless quality, perfect for
      further processing or embedding in PDFs.'
    text: '**Saving** – `BarCodeImageFormat.Png` gives lossless quality, perfect for
      further processing or embedding in PDFs.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Genera codice a barre PDF417 in C# – Crea codice a barre PDF417 C#
url: /it/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Genera codice a barre PDF417 in C# – Guida completa di programmazione

Ti sei mai chiesto come **generare un codice a barre PDF417** in un'applicazione C# senza dover setacciare infinite discussioni nei forum? Non sei il solo. Che tu stia costruendo un sistema di biglietteria, una carta d'identità sicura, o semplicemente abbia bisogno di un modo rapido per incorporare dati in un formato stampabile, padroneggiare il formato PDF417 può farti risparmiare ore di tentativi ed errori.

In questa guida percorreremo un **esempio completo, pronto‑all'uso** che ti mostra esattamente come **creare un codice a barre PDF417 in C#** usando la popolare libreria Aspose.BarCode. Copriremo tutto, dall'installazione del pacchetto NuGet alla regolazione della modalità compatta, così potrai copiare‑incollare il codice e vedere i risultati immediatamente.

## Cosa imparerai

- Come configurare la libreria Aspose.BarCode in un progetto .NET.  
- Le istruzioni C# esatte necessarie per **generare un codice a barre PDF417** con testo personalizzato, dimensione del modulo e numero di colonne.  
- Perché attivare l'opzione *Compact* (Truncate) è importante per dati densi.  
- Come salvare il codice a barre come PNG e verificare l'output.  

Non è necessaria alcuna esperienza pregressa con i codici a barre; basta una comprensione di base di C# e Visual Studio (o di qualsiasi IDE preferisci). Alla fine avrai un metodo riutilizzabile da inserire in qualsiasi progetto che necessiti di un'immagine PDF417.

## Prerequisiti

| Requisito | Perché è importante |
|-----------|----------------------|
| .NET 6.0 or later (or .NET Framework 4.7+) | Aspose.BarCode supporta entrambi; i runtime più recenti offrono migliori prestazioni. |
| Visual Studio 2022 (or VS Code with C# extensions) | Fornisce IntelliSense e debug semplificato. |
| Internet connection (for the first NuGet restore) | La libreria viene scaricata da NuGet.org. |
| Basic C# knowledge | Necessario per comprendere le strutture di classe e le chiamate ai metodi. |

Se li hai già, ottimo—tuffiamoci.

## Installa il pacchetto NuGet Aspose.BarCode

Open your project folder in a terminal and run:

```bash
dotnet add package Aspose.BarCode
```

Oppure, all'interno di Visual Studio, fai clic destro su **Dependencies → Manage NuGet Packages**, cerca *Aspose.BarCode* e fai clic su **Install**. Questa singola riga aggiunge tutti i tipi che utilizzeremo, inclusi `BarcodeGenerator`, `EncodeTypes` e `BarCodeImageFormat`.

> **Consiglio professionale:** Dopo l'installazione, pulisci e ricostruisci la soluzione per assicurarti che l'assembly sia referenziato correttamente.

## Genera codice a barre PDF417 – Configurazione e dipendenze

First things first: we need a `using` block that pulls the relevant namespaces into scope.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

These namespaces give us access to the generator class and the enumeration of barcode types. Nothing fancy—just three lines, and we’re ready to start creating the barcode.

## Crea codice a barre PDF417 in C# – Implementazione passo‑a‑passo

Di seguito trovi un **programma console autonomo** che crea un codice a barre PDF417 compatto dalla stringa `"Åspóse.Barcóde©"` e lo salva come `CompactPdf417.png`. Sentiti libero di sostituire il testo con qualsiasi cosa ti serva; il generatore gestirà i caratteri Unicode senza ulteriori configurazioni.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Define the data you want to encode.
            string data = "Åspóse.Barcóde©";

            // 2️⃣ Initialise the generator for PDF417.
            //    EncodeTypes.Pdf417 tells Aspose we want a PDF417 barcode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // 3️⃣ Adjust the module (X‑dimension) size.
            //    Smaller values give a tighter image; 2 pixels works well for most screens.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Configure PDF417‑specific options.
            //    • Columns = 3 → fewer columns, taller barcode.
            //    • Truncate = true → enables Compact mode, which removes unnecessary padding.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Choose the output folder – adjust as needed.
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "CompactPdf417.png");

            // 6️⃣ Save the image as PNG.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ PDF417 barcode saved to: {outputPath}");
        }
    }
}
```

### Perché ogni passaggio è importante

1. **Definizione dei dati** – PDF417 può memorizzare fino a ~1850 caratteri, ma lo manteniamo breve per la demo. Il supporto Unicode significa che quei caratteri accentati non romperanno nulla.  
2. **Costruzione del generatore** – Il valore enum `EncodeTypes.Pdf417` indica ad Aspose quale simbologia utilizzare; sostituendolo con `EncodeTypes.QR` otterresti un codice QR invece.  
3. **X‑dimension** – Controlla la larghezza di ogni modulo (i piccoli quadrati che compongono il codice a barre). Un valore di `2` pixel produce un'immagine nitida che rimane leggibile quando stampata a 300 dpi.  
4. **Opzioni PDF417** – `Columns` influenza il rapporto d'aspetto del codice a barre; meno colonne rendono l'immagine più alta, il che può essere utile per ricevute. `Truncate` (chiamato anche *modalità compatta*) rimuove il padding del pattern di inizio/fine, riducendo la dimensione del file senza sacrificare l'integrità dei dati.  
5. **Percorso di output** – Usare `Environment.CurrentDirectory` garantisce che l'immagine venga salvata accanto all'eseguibile, facilitandone la localizzazione durante lo sviluppo.  
6. **Salvataggio** – `BarCodeImageFormat.Png` offre qualità lossless, perfetta per ulteriori elaborazioni o per l'incorporamento in PDF.  

Esegui il programma (`dotnet run` o premi **F5** in Visual Studio). Dopo pochi secondi dovresti vedere un messaggio nella console che conferma la posizione del file, e il PNG apparirà nella cartella del progetto.

![Esempio di generazione codice a barre PDF417](generated-pdf417.png)

*Testo alternativo dell'immagine: esempio di generazione codice a barre pdf417 – immagine PNG di un codice a barre PDF417 compatto creato con C#.*

## Configura la modalità compatta – Opzioni del generatore di codici a barre PDF417 in C#

Se ti serve un codice a barre più grande (forse per la scansione da una distanza), modifica le proprietà `Columns` e `Rows`. Ecco un breve snippet che dimostra configurazioni alternative:

```csharp
// Increase columns for a wider, shorter barcode.
generator.Parameters.Barcode.Pdf417.Columns = 6;

// Disable Compact mode if the scanning hardware struggles with it.
generator.Parameters.Barcode.Pdf417.Truncate = false;

// Optionally set error correction level (0–8). Higher values increase redundancy.
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;
```

> **Domanda comune:** *Disabilitare Truncate romperà gli scanner esistenti?*  
> Di solito no. La maggior parte degli scanner moderni comprende sia il PDF417 a dimensione piena sia quello compatto. Tuttavia, se ti rivolgi a hardware legacy, lascia `Truncate` impostato su `false`.

## Salva e verifica – come generare l'output del codice a barre pdf417

Dopo il salvataggio, puoi aprire il PNG con qualsiasi visualizzatore di immagini. Per verificare che il codice a barre codifichi i dati desiderati, usa il `BarCodeReader` di Aspose:



## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑a‑passo per aiutarti a padroneggiare ulteriori funzionalità dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come creare un codice a barre – PDF417 compatto con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Come generare un codice a barre Aztec con rapporto d'aspetto personalizzato usando Aspose.BarCode per .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Libreria barcode Java – Aggiungere un codice a barre a PDF usando Aspose](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}