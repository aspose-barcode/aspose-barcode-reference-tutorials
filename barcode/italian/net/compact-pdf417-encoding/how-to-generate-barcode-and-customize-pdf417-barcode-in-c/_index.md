---
category: general
date: 2026-09-19
description: Come generare un codice a barre in C# con una guida passo passo. Impara
  a personalizzare le impostazioni del codice a barre PDF417 e a creare un'immagine
  di codice a barre che gli sviluppatori C# possono utilizzare subito.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- customize pdf417 barcode
- create barcode image c#
language: it
lastmod: 2026-09-19
og_description: Come generare un codice a barre in C# con istruzioni dettagliate.
  Personalizza i parametri del codice a barre PDF417 e crea un'immagine di codice
  a barre che i progetti C# possono utilizzare oggi.
og_image_alt: Screenshot of a generated MicroPDF417 barcode image created with C#
  code
og_title: Come generare un codice a barre e personalizzare il codice a barre PDF417
  in C#
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  headline: How to generate barcode and customize PDF417 barcode in C#
  type: TechArticle
- description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  name: How to generate barcode and customize PDF417 barcode in C#
  steps:
  - name: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
    text: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
  - name: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
    text: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
  - name: Increase `ErrorLevel` to improve tolerance.
    text: Increase `ErrorLevel` to improve tolerance.
  type: HowTo
tags:
- barcode
- C#
- pdf417
title: Come generare un codice a barre e personalizzare il codice a barre PDF417 in
  C#
url: /it/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come generare un codice a barre e personalizzare il codice a barre PDF417 in C#

Se hai bisogno di **come generare un codice a barre** in un'applicazione .NET, questo tutorial ti mostra una soluzione completa, pronta all'uso. Imparerai a personalizzare le dimensioni del codice a barre PDF417, scegliere il numero di colonne e, infine, **creare un'immagine di codice a barre C#** che i progetti possono incorporare direttamente.

Generare un codice a barre non richiede una pipeline di build complessa. Alla fine di questa guida avrai un file PNG contenente un codice a barre MicroPDF417 che corrisponde esattamente alle dimensioni e alla risoluzione di cui hai bisogno.

## Prerequisiti

Dovresti avere installato quanto segue prima di iniziare:

* .NET 6.0 SDK o versioni successive (il codice funziona anche con .NET Framework 4.6+)
* Visual Studio 2022 (o qualsiasi editor C# tu preferisca)
* Pacchetto NuGet Aspose.BarCode for .NET – installa con  
  `dotnet add package Aspose.BarCode`

Non sono richiesti strumenti esterni aggiuntivi.

## Passo 1: Configurare il progetto e importare i namespace

Crea un nuovo progetto console e aggiungi il riferimento a Aspose.BarCode.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Apri `Program.cs` e aggiungi le direttive `using` necessarie:

```csharp
using System;
using Aspose.BarCode.Generation;   // Provides BarcodeGenerator and EncodeTypes
using Aspose.BarCode;               // Contains BarCodeImageFormat enum
```

Questi namespace espongono le classi che ti permettono di **come generare un codice a barre** e controllare le opzioni specifiche di PDF417.

## Passo 2: Inizializzare il generatore MicroPDF417 con il testo desiderato

La prima riga crea un'istanza di `BarcodeGenerator` configurata per la simbologia MicroPDF417. Il costruttore accetta il tipo di codifica e la stringa di dati che vuoi codificare.

```csharp
// Step 2: Create a MicroPDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");
```

**Perché è importante:** MicroPDF417 è una variante compatta dello standard PDF417 completo, ideale per etichette piccole o schermi mobili. Inizializzare il generatore con il corretto `EncodeTypes` garantisce che la libreria utilizzi l'algoritmo di codifica giusto.

## Passo 3: Personalizzare la X‑dimension (larghezza del modulo) per una risoluzione più fine

La X‑dimension controlla la larghezza di un singolo modulo del codice a barre (la barra nera o bianca più piccola). Impostarla a un valore di pixel basso produce un'immagine a risoluzione più alta.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Perché è importante:** Una X‑dimension più grande rende il codice a barre più facile da leggere per scanner a bassa risoluzione, mentre un valore più piccolo consente di inserire più dati in uno spazio limitato. Regola questo valore in base all'ambiente di scansione.

## Passo 4: Definire il numero di colonne per controllare le dimensioni del codice a barre

MicroPDF417 consente da 1 a 4 colonne. Più colonne producono un codice a barre più corto e più largo; meno colonne creano uno più alto e più stretto.

```csharp
// Step 4: Define the number of columns (1‑4 are allowed) to control barcode size
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Perché è importante:** Scegliere il giusto numero di colonne ti permette di adattare il codice a barre a un elemento UI specifico o a un'etichetta stampata senza dover scalare manualmente.

## Passo 5: Salvare il codice a barre come immagine PNG

Infine, scrivi il codice a barre generato su disco. PNG conserva la qualità lossless, importante per una scansione nitida.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\MicroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Se la directory di destinazione non esiste, il metodo `Save` genera un'`ArgumentException`. Puoi prevenirlo con un semplice controllo:

```csharp
if (!System.IO.Directory.Exists(@"C:\Barcodes"))
{
    System.IO.Directory.CreateDirectory(@"C:\Barcodes");
}
```

### Codice sorgente completo

Unendo tutti i pezzi, ecco il programma completo e eseguibile:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");

            // 2️⃣ Set the X‑dimension (module width) in pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Define the number of columns (1‑4 are allowed) to control barcode size
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Ensure the output folder exists
            string folder = @"C:\Barcodes";
            if (!System.IO.Directory.Exists(folder))
                System.IO.Directory.CreateDirectory(folder);

            // 4️⃣ Save the generated barcode as a PNG image
            string outputPath = System.IO.Path.Combine(folder, "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Eseguendo questo programma otterrai un file chiamato **MicroPdf417.png** che appare come nello screenshot qui sotto (immagine omessa per brevità). Il codice a barre codifica il testo *Sample* e rispetta le impostazioni di X‑dimension e colonne che hai definito.

## Personalizzare altre opzioni PDF417

Sebbene questa guida si concentri su **personalizzare pdf417 barcode** parametri che influenzano le dimensioni, Aspose.BarCode offre molte altre impostazioni che potresti necessitare:

| Property | Scopo | Valori tipici |
|----------|-------|---------------|
| `generator.Parameters.Barcode.Pdf417.Rows` | Controlla il numero di righe (altezza) | 3‑30 |
| `generator.Parameters.Barcode.Pdf417.ErrorLevel` | Imposta il livello di correzione errori (più alto = più tollerante) | 0‑8 |
| `generator.Parameters.Barcode.Pdf417.Truncated` | Genera un codice a barre troncato (senza pattern di stop) | `true`/`false` |
| `generator.Parameters.Barcode.Pdf417.CompactionMode` | Sceglie la compattazione numerica, testuale o byte | `CompactionModes.Numeric`, ecc. |

**Consiglio professionale:** Quando hai bisogno di un codice a barre che si adatti a una larghezza fissa, inizia aumentando `Columns` e diminuendo `XDimension`. Se lo scanner segnala simboli mancanti, alza `ErrorLevel` per migliorare la ridondanza.

## Gestire i casi limite

* **Testo troppo lungo per MicroPDF417:** La variante Micro supporta fino a 1 KB di dati. Se la tua stringa supera questo limite, passa alla simbologia completa `Pdf417` cambiando `EncodeTypes.MicroPdf417` in `EncodeTypes.Pdf417`.
* **Formato immagine non supportato:** `BarCodeImageFormat` supporta anche `Jpeg`, `Bmp` e `Gif`. Scegli un formato che corrisponda al tuo flusso di lavoro downstream.
* **Percorsi cross‑platform:** Usa `Path.Combine` invece di backslash hard‑coded quando miri a Linux o macOS.

## Verificare il codice a barre

Puoi verificare l'immagine generata con qualsiasi app scanner di codici a barre standard (mobile o desktop). Lo scanner dovrebbe restituire il testo originale **Sample**. Se fallisce:

1. Controlla che la X‑dimension non sia impostata sotto 1 pixel (alcuni scanner non riescono a risolvere moduli sub‑pixel).
2. Assicurati che il file di output non sia corrotto—riavvia il programma e confronta le dimensioni dei file.
3. Aumenta `ErrorLevel` per migliorare la tolleranza.

## Conclusione

Ora sai **come generare un codice a barre** in C# usando Aspose.BarCode, come **personalizzare pdf417 barcode** dimensioni e numero di colonne, e come **creare un'immagine di codice a barre C#** che i progetti possono incorporare direttamente. L'esempio completo dimostra un flusso di lavoro pratico dalla configurazione del progetto all'output PNG finale.

Successivamente, esplora altre simbologie come QR, Code128 o DataMatrix cambiando il valore dell'enum `EncodeTypes`. Regolare parametri aggiuntivi come `Resolution` o `Margin` ti permette di perfezionare ogni codice a barre per la tua applicazione specifica.

Buona programmazione, e lascia che i tuoi codici a barre potenzino il tuo prossimo progetto di automazione!

## Cosa dovresti imparare dopo?

I tutorial seguenti coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}