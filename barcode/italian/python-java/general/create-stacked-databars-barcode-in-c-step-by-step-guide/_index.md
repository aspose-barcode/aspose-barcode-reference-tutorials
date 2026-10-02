---
category: general
date: 2026-10-02
description: Crea rapidamente un codice a barre stacked databars in C#. Impara a impostare
  XDimension, regolare il rapporto d'aspetto e esportare immagini PNG con un generatore
  di codici a barre.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create stacked databars barcode
- C# barcode generator
- DataBar stacked omnidirectional
- barcode aspect ratio
- XDimension pixel size
- BarCodeImageFormat PNG
language: it
lastmod: 2026-10-02
og_description: Crea un codice a barre stacked databars in C# con un esempio di codice
  completo. Regola XDimension, modifica il rapporto d'aspetto e salva i file PNG in
  poche righe.
og_image_alt: Screenshot showing a create stacked databars barcode example generated
  with C#
og_title: Crea un codice a barre DataBar impilato in C# – tutorial rapido
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create stacked databars barcode in C# quickly. Learn to set XDimension,
    adjust aspect ratio, and export PNG images with a barcode generator.
  headline: Create stacked databars barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- Aspose
- image generation
title: Crea un codice a barre a barre dati impilate in C# – guida passo passo
url: /it/python-java/general/create-stacked-databars-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea barcode stacked databars in C# – guida passo‑passo

Se hai bisogno di **creare barcode stacked databars** in un progetto .NET, questo tutorial ti mostra esattamente come fare. Vedrai come configurare la X‑dimension, cambiare i rapporti d'aspetto e salvare il risultato come file PNG—tutto con la libreria Aspose.BarCode.

Generare un barcode DataBar stacked non richiede una pipeline grafica complessa. Alla fine di questa guida avrai due immagini PNG pronte all'uso che illustrano diversi rapporti d'aspetto, e comprenderai perché quei parametri sono importanti per l'affidabilità della scansione.

## Cosa ti servirà

- .NET 6.0 o successivo (il codice funziona anche con .NET Framework 4.6+)
- Visual Studio 2022 o qualsiasi IDE C#
- **Aspose.BarCode for .NET** pacchetto NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Permesso di scrittura su una cartella dove verranno salvati i file PNG

## Passo 1: Configura il progetto e importa i namespace

Crea una nuova applicazione console (o aggiungi il codice a un progetto esistente) e importa i namespace richiesti:

```csharp
using System;
using Aspose.BarCode.Generation;   // BarcodeGenerator lives here
using Aspose.BarCode;               // BarCodeImageFormat enum
```

> **Perché è importante:** `Aspose.BarCode.Generation` fornisce la classe `BarcodeGenerator`, mentre `Aspose.BarCode` contiene l'enumerazione `BarCodeImageFormat` usata per salvare le immagini.

## Passo 2: Inizializza il generatore per un DataBar stacked omnidirezionale

Il valore `EncodeTypes.DatabarStackedOmniDirectional` seleziona la simbologia DataBar stacked. La stringa di dati deve seguire il formato GS1 Application Identifier (AI); qui utilizziamo un valore GTIN‑14 fittizio.

```csharp
// Initialise a generator for a stacked omnidirectional DataBar barcode
var barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

> **Perché è importante:** Il tipo di codifica scelto indica alla libreria di generare un barcode *stacked*, essenziale per etichette ad alta densità dove lo spazio verticale è limitato.

## Passo 3: Definisci la dimensione del modulo (X‑dimension) in pixel

La X‑dimension controlla la larghezza della barra più piccola (il “modulo”). Un valore di 2 pixel funziona bene per la maggior parte delle uscite a risoluzione schermo.

```csharp
// Set the X‑dimension to 2 pixels (module width)
barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Perché è importante:** Gli scanner interpretano la larghezza del modulo come unità di misura di base. Un valore troppo piccolo può causare stampe sfocate; uno troppo grande spreca spazio.

## Passo 4: Salva la prima immagine con un rapporto d'aspetto di 15

La proprietà `AspectRatio` influenza la relazione altezza‑larghezza di ciascun segmento stacked. Un rapporto d'aspetto di 15 è un valore predefinito comune per le applicazioni retail.

```csharp
// Apply aspect ratio 15 and save the first PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

> **Perché è importante:** Un rapporto d'aspetto più basso produce un barcode più piatto, che può essere più facile da scansionare su certi materiali di etichetta. Il formato PNG preserva la qualità lossless per i test.

## Passo 5: Cambia il rapporto d'aspetto a 30 e salva la seconda immagine

Aumentare il rapporto d'aspetto rende ogni segmento stacked più alto, il che può migliorare l'affidabilità della scansione su sfondi a basso contrasto.

```csharp
// Apply aspect ratio 30 and save the second PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

> **Perché è importante:** Diversi rivenditori o partner logistici possono richiedere dimensioni specifiche del barcode. Fornire entrambe le versioni ti permette di confrontare rapidamente le prestazioni di scansione.

## Esempio completo, eseguibile

Di seguito trovi il programma completo che puoi copiare‑incollare in `Program.cs`. Si compila ed esegue senza modifiche dopo aver installato il pacchetto NuGet Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace StackedDataBarDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for stacked omnidirectional DataBar
            var barcodeGen = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Define the module (X‑dimension) size in pixels
            barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Save first image with aspect ratio 15
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio15.png");

            // 4️⃣ Save second image with aspect ratio 30
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio30.png");
        }
    }
}
```

### Output previsto

L'esecuzione del programma crea due file nella cartella di esecuzione:

| Nome file                     | Rapporto d'aspetto | Descrizione visiva |
|-------------------------------|--------------------|--------------------|
| `DatabarAspectRatio15.png`    | 15                 | Barcode stacked più corto e più piatto |
| `DatabarAspectRatio30.png`    | 30                 | Barcode stacked più alto e più allungato |

Puoi aprire i file PNG con qualsiasi visualizzatore di immagini per verificare che il barcode venga renderizzato correttamente.

![Create stacked databars barcode example](placeholder-image.png){alt="Esempio di creazione di barcode stacked databars"}

## Domande frequenti e casi particolari

| Domanda | Risposta |
|----------|--------|
| **Posso usare una X‑dimension diversa?** | Sì. I valori tipici variano da 1 a 4 pixel. Valori più grandi aumentano le dimensioni del barcode ma possono migliorare la leggibilità su stampanti a bassa risoluzione. |
| **E se ho bisogno di una simbologia diversa?** | Sostituisci `EncodeTypes.DatabarStackedOmniDirectional` con un altro valore di `EncodeTypes`, ad esempio `DatabarStacked` (non omnidirezionale) o `DatabarLimited`. |
| **Come cambio il formato di output?** | Usa `BarCodeImageFormat.Jpeg`, `Gif` o `Bmp` nella chiamata `Save`. |
| **Il formato GTIN‑14 è obbligatorio?** | La simbologia DataBar si aspetta una stringa numerica prefissata con un AI appropriato (es. `(01)` per GTIN‑14). Adatta i dati al tuo caso d'uso. |
| **Cosa riguarda le impostazioni DPI?** | Il generatore rispetta la proprietà `Resolution`. Per stampe ad alta risoluzione, imposta `barcodeGen.Parameters.ImageResolution.DpiX` e `DpiY` di conseguenza. |

## Consigli professionali

- **Generazione batch:** Inserisci la logica di salvataggio in un ciclo e fornisci un elenco di GTIN per produrre migliaia di barcode automaticamente.
- **Validazione:** Usa `barcodeGen.Validate()` prima di salvare per intercettare dati malformati in anticipo.
- **Prestazioni:** Riutilizzare la stessa istanza di `BarcodeGenerator` (modificando solo i parametri) è più veloce che creare un nuovo oggetto per ogni immagine.

## Prossimi passi

Ora che sai **creare barcode stacked databars** con rapporti d'aspetto personalizzati, considera di approfondire:

- Aggiungere testo leggibile dall'uomo sotto il barcode (`barcodeGen.Parameters.Barcode.CodeText`).
- Esportare in **PDF** per fogli di etichette stampabili (`BarCodeImageFormat.Pdf`).
- Integrare il generatore in una web API per fornire barcode su richiesta.
- Sperimentare con altre **parole chiave secondarie** come *C# barcode generator* e *barcode aspect ratio* per ottimizzare l'implementazione su hardware specifico.

Buona programmazione e goditi la flessibilità che Aspose.BarCode porta ai tuoi progetti di barcode C#!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API e a esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Crea barcode databar stacked in C# – guida passo‑passo](/barcode/english/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/)
- [Barcode databar stacked omnidirezionale in C# – Guida completa](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [Come creare immagini PNG databar con C# e Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}