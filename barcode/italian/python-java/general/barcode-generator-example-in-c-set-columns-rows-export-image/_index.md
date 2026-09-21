---
category: general
date: 2026-07-15
description: Esempio di generatore di codici a barre in C# che mostra come impostare
  le colonne, come impostare le righe e come esportare rapidamente l'immagine del
  codice a barre. Segui questa guida passo‑passo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to set columns
- how to set rows
- export barcode image
- create barcode image c#
language: it
lastmod: 2026-07-15
og_description: L'esempio di generatore di codici a barre in C# dimostra come impostare
  le colonne, come impostare le righe e esportare l'immagine del codice a barre. Scopri
  l'intero flusso di lavoro in pochi minuti.
og_image_alt: Screenshot of a barcode generator example showing column and row settings
  in C#
og_title: Esempio di generatore di codici a barre in C# – Colonne, righe e esportazione
  immagine
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Barcode generator example in C# showing how to set columns, how to
    set rows, and export barcode image quickly. Follow this step‑by‑step guide.
  headline: Barcode Generator Example in C# – Set Columns, Rows & Export Image
  type: TechArticle
- description: Barcode generator example in C# showing how to set columns, how to
    set rows, and export barcode image quickly. Follow this step‑by‑step guide.
  name: Barcode Generator Example in C# – Set Columns, Rows & Export Image
  steps:
  - name: '**Add colors** – Set `generator.Parameters.Barcode.ForegroundColor` to
      `Color.Blue`.'
    text: '**Add colors** – Set `generator.Parameters.Barcode.ForegroundColor` to
      `Color.Blue`.'
  - name: '**Encode different data** – Pass a variable string instead of the hard‑coded
      `"Databar Expanded Stacked long"`.'
    text: '**Encode different data** – Pass a variable string instead of the hard‑coded
      `"Databar Expanded Stacked long"`.'
  - name: '**Batch processing** – Loop over a CSV file of product codes, generating
      a PNG for each.'
    text: '**Batch processing** – Loop over a CSV file of product codes, generating
      a PNG for each.'
  - name: '**Integrate with a web API** – Expose an endpoint that returns the barcode
      as a base64‑encoded string.'
    text: '**Integrate with a web API** – Expose an endpoint that returns the barcode
      as a base64‑encoded string.'
  type: HowTo
tags:
- barcode
- C#
- image export
title: Esempio di generatore di codici a barre in C# – Imposta colonne, righe e esporta
  immagine
url: /it/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Esempio di Generatore di Codici a Barre in C# – Guida Completa

Ti sei mai chiesto come creare un **esempio di generatore di codici a barre** in C# che ti permetta di modificare colonne, righe e poi esportare il risultato come immagine? Non sei solo. Molti sviluppatori si trovano in difficoltà quando hanno bisogno di un modo rapido per generare codici DataBar Expanded Stacked con opzioni di layout personalizzate. In questo tutorial risolveremo il problema passo‑passo, mostrandoti **come impostare le colonne**, **come impostare le righe** e infine **esportare le immagini del codice a barre**—tutto con codice pulito, pronto per la produzione.

Alla fine di questa guida avrai un programma completo e eseguibile che crea un'immagine di codice a barre, ne regola il layout e salva due file PNG su disco. Nessuna libreria misteriosa, nessuna configurazione nascosta—solo puro C# e un SDK di codici a barre affidabile.

---

## Prerequisiti

Prima di immergerci, assicurati di avere quanto segue:

- **.NET 6.0** (o qualsiasi versione successiva di .NET). Il codice compila anche con .NET Framework, ma .NET 6+ offre i più recenti miglioramenti di runtime.
- Una **libreria di generazione di codici a barre** che supporti DataBar Expanded Stacked. Negli esempi useremo **Aspose.BarCode for .NET**, gratuita per la prova e con un'API semplice.
- Un ambiente di sviluppo—Visual Studio 2022, Rider o VS Code vanno tutti bene.
- Permessi di scrittura su una cartella dove verranno salvati i file PNG.

Se non hai ancora la libreria, scaricala da NuGet:

```bash
dotnet add package Aspose.BarCode
```

Quella singola riga importa tutto il necessario, inclusa la classe `BarcodeGenerator` e l'enumerazione `BarCodeImageFormat` usata più avanti.

---

## Passo 1: Configurare lo Scheletro del Progetto

Crea una nuova applicazione console e aggiungi le direttive `using` necessarie:

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum
```

Ecco lo **scheletro completo** del file `Program.cs`:

```csharp
namespace BarcodeDemo
{
    internal class Program
    {
        static void Main(string[] args)
        {
            // We'll fill this in in the next steps.
        }
    }
}
```

> **Consiglio professionale:** Mantieni il metodo `Main` ordinato; delegheremo il lavoro più pesante a metodi di supporto più tardi. Questo rende il codice più facile da testare e riutilizzare.

---

## Passo 2: Creare l'Esempio di Generatore di Codici a Barre

Ora costruiremo il **esempio di generatore di codici a barre** che crea un codice DataBar Expanded Stacked. Questo è il cuore del tutorial.

```csharp
static BarcodeGenerator CreateGenerator()
{
    // Step 1: Instantiate the generator for DataBar Expanded Stacked.
    // The second argument is the text you want encoded.
    var generator = new BarcodeGenerator(
        EncodeTypes.DatabarExpandedStacked,
        "Databar Expanded Stacked long");

    // Optional: fine‑tune image size or resolution if needed.
    generator.Parameters.Image.Width = 300;
    generator.Parameters.Image.Height = 150;

    return generator;
}
```

Perché lo separiamo in un proprio metodo? Isola la logica dell'**esempio di generatore di codici a barre**, rendendola riutilizzabile se in seguito dovrai generare più codici con dati diversi.

---

## Passo 3: Come Impostare le Colonne

Il formato DataBar Expanded Stacked può essere renderizzato in un layout orientato alle colonne. Per impostazione predefinita l'SDK sceglie un valore sensato, ma spesso è necessario adeguarsi a una dimensione di etichetta specifica. Ecco **come impostare le colonne** a quattro:

```csharp
static void SetColumns(BarcodeGenerator generator, int columns)
{
    // Step 2: Adjust the column count.
    generator.Parameters.Barcode.DataBar.Columns = columns;
}
```

> **Perché le colonne sono importanti:** Ogni colonna aggiunge spazio verticale, il che può essere cruciale quando si stampa su etichette strette. Impostandola a `4` ottieni un codice a barre equilibrato e leggibile senza sacrificare l'affidabilità della scansione.

Nel flusso principale chiameremo questo metodo:

```csharp
var generator = CreateGenerator();
SetColumns(generator, 4);
```

---

## Passo 4: Come Impostare le Righe

A volte serve un layout più compatto, soprattutto se stampi su un'etichetta corta e larga. È qui che entra in gioco **come impostare le righe**. Passare da un layout basato su colonne a uno basato su righe può ridurre l'ingombro del codice a barre.

```csharp
static void SetRows(BarcodeGenerator generator, int rows)
{
    // Step 4: Change the layout to use rows instead of columns.
    generator.Parameters.Barcode.DataBar.Rows = rows;
}
```

La chiamata è così:

```csharp
SetRows(generator, 3);
```

> **Nota su casi limite:** Non è possibile impostare contemporaneamente colonne *e* righe—l'SDK darà priorità alle righe se assegni un valore diverso da zero a `Rows`. Quindi assicurati di azzerare l'altra proprietà quando cambi layout:

```csharp
generator.Parameters.Barcode.DataBar.Columns = 0; // Disable columns when using rows
```

---

## Passo 5: Esportare l'Immagine del Codice a Barre

Con il layout configurato, l'ultimo passo è **esportare le immagini del codice a barre**. L'SDK supporta PNG, JPEG, BMP e altro. PNG è lossless e funziona bene per la maggior parte delle stampanti di etichette.

```csharp
static void SaveBarcode(BarcodeGenerator generator, string filePath)
{
    // Step 5: Save the image using the PNG format.
    generator.Save(filePath, BarCodeImageFormat.Png);
}
```

Mettere tutto insieme in `Main`:

```csharp
static void Main(string[] args)
{
    // 1️⃣ Create the generator (barcode generator example)
    var generator = CreateGenerator();

    // 2️⃣ Set columns and save the first image
    SetColumns(generator, 4);
    string colsPath = @"YOUR_DIRECTORY\DatabarCols4.png";
    SaveBarcode(generator, colsPath);
    Console.WriteLine($"Barcode with 4 columns saved to {colsPath}");

    // 3️⃣ Switch to rows and save the second image
    SetRows(generator, 3);
    // Clear columns to avoid conflict
    generator.Parameters.Barcode.DataBar.Columns = 0;
    string rowsPath = @"YOUR_DIRECTORY\DatabarRows3.png";
    SaveBarcode(generator, rowsPath);
    Console.WriteLine($"Barcode with 3 rows saved to {rowsPath}");
}
```

### Output Atteso

Quando esegui il programma, dovresti vedere due file PNG in `YOUR_DIRECTORY`:

- **DatabarCols4.png** – un codice a barre renderizzato con quattro colonne verticali.
- **DatabarRows3.png** – gli stessi dati, ma disposti in tre righe orizzontali.

Entrambe le immagini saranno 300 × 150 px (come impostato in `CreateGenerator`) e pronte per la stampa o per l'inserimento in un PDF.

---

## Problemi Comuni & Consigli

| Problema | Perché accade | Soluzione |
|----------|----------------|-----------|
| **Errori di percorso file** | Usare un percorso relativo senza la directory corretta può generare `DirectoryNotFoundException`. | Usa `Path.Combine(Environment.CurrentDirectory, "output", "file.png")` o assicurati che la cartella esista con `Directory.CreateDirectory`. |
| **Conflitto Righe vs. Colonne** | Impostare entrambe le proprietà fa sì che l'SDK ignori le colonne. | Imposta esplicitamente la proprietà opposta a `0` quando cambi layout. |
| **Tipo di codice a barre non supportato** | Non tutte le librerie supportano DataBar Expanded Stacked. | Verifica che la tua versione della libreria includa `EncodeTypes.DatabarExpandedStacked`. |
| **Qualità immagine troppo bassa** | La DPI predefinita può essere insufficiente per stampanti ad alta risoluzione. | Regola `generator.Parameters.Image.ResolutionX/Y` a `300` o più. |

---

## Estendere l'Esempio di Generatore di Codici a Barre

Ora che hai un **esempio di generatore di codici a barre** solido, potresti chiederti cos'altro è possibile fare.

1. **Aggiungere colori** – Imposta `generator.Parameters.Barcode.ForegroundColor` a `Color.Blue`.
2. **Codificare dati diversi** – Passa una stringa variabile invece della costante `"Databar Expanded Stacked long"`.
3. **Elaborazione batch** – Scorri un file CSV di codici prodotto, generando un PNG per ciascuno.
4. **Integrare con un'API web** – Esporre un endpoint che restituisce il codice a barre come stringa codificata in base64.

Ognuna di queste estensioni segue lo stesso schema: configura l'istanza `BarcodeGenerator`, poi chiama `Save` o `Export` secondo necessità.

---

## Conclusione

Abbiamo percorso insieme un **esempio completo di generatore di codici a barre** in C# che mostra **come impostare le colonne**, **come impostare le righe** e come **esportare le immagini del codice a barre**. Il codice è autonomo, funziona subito con Aspose.BarCode e dimostra le migliori pratiche per leggibilità e manutenibilità.

Sentiti libero di sperimentare—cambia la stringa dei dati, modifica le dimensioni dell'immagine o passa a una simbologia di codice a barre diversa. I concetti appresi qui—inizializzare il generatore, configurare i parametri di layout ed esportare—si applicano praticamente a qualsiasi tipo di codice a barre supportato dall'SDK.

Hai domande su come creare programmi C# per immagini di codici a barre, o ti serve aiuto con una stampante di etichette specifica? Lascia un commento qui sotto, e buona programmazione!

---


## Cosa Dovresti Imparare Dopo?

I tutorial seguenti trattano argomenti strettamente correlati che approfondiscono le tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive e a esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Create barcode image c# – Configure Codablock F Rows & Columns](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}