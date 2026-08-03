---
category: general
date: 2026-08-03
description: Crea rapidamente un'immagine di codice a barre postale in C#. Scopri
  come generare un codice a barre postale, impostare le dimensioni del codice a barre
  e generare un codice a barre Planet.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- how to generate postal barcode
- generate planet barcode
- how to set barcode dimensions
language: it
lastmod: 2026-08-03
og_description: Crea un'immagine di codice a barre postale in C# con questo tutorial
  completo; impara a impostare le dimensioni del codice a barre, generare un codice
  a barre Planet e produrre codici a barre RM4SCC.
og_image_alt: Generated postal barcode image saved as PNG using C# BarcodeGenerator
og_title: Crea immagine di codice a barre postale in C# – guida completa di programmazione
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create postal barcode image in C# quickly. Learn how to generate postal
    barcode, set barcode dimensions, and generate a Planet barcode.
  headline: Create postal barcode image in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- postal barcode
title: Crea immagine di codice a barre postale in C# – guida passo passo
url: /it/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea un'immagine di codice a barre postale in C# – guida passo‑paso

Se hai bisogno di **creare un'immagine di codice a barre postale** in C#, questa guida ti mostra esattamente come fare. Copriremo **come generare un codice a barre postale**, **come impostare le dimensioni del codice a barre** e come **generare il codice a barre Planet** per gli standard postali più comuni.

Terminerai con due file PNG pronti all'uso — un codice a barre Planet e un codice a barre RM4SCC — entrambi alti 100 px. Non sono necessari strumenti aggiuntivi oltre alla libreria Aspose.BarCode per .NET.

## Prerequisiti

* .NET 6 SDK o versioni successive (il codice funziona anche con .NET Framework 4.7+)
* Visual Studio 2022 o qualsiasi IDE C#
* Pacchetto NuGet **Aspose.BarCode** (la libreria che fornisce `BarcodeGenerator`)

## Passo 1: Installa la libreria per i codici a barre

Apri un terminale nella cartella del tuo progetto ed esegui:

```bash
dotnet add package Aspose.BarCode
```

Il pacchetto aggiunge lo spazio dei nomi `Aspose.BarCode`, che contiene `BarcodeGenerator` e l'enumerazione `EncodeTypes` necessaria per i codici a barre postali.

## Passo 2: Definisci la cartella di output

Creare un percorso di output affidabile evita errori di runtime quando la cartella non esiste.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // Ensure the directory exists
        string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputFolder);
```

*Perché è importante*: `Directory.CreateDirectory` è idempotente — crea la cartella solo se non è già presente, evitando eccezioni nelle esecuzioni successive.

## Passo 3: Configura le dimensioni comuni del codice a barre

Impostare la X‑dimension (larghezza di una singola barra) e l'altezza complessiva della barra ti consente di controllare la dimensione visiva dell'immagine generata.

```csharp
        // Common dimension settings
        const int xDimensionPixels = 4;   // Width of a single bar
        const int barHeightPixels = 100; // Desired barcode height
```

**Come impostare le dimensioni del codice a barre**: la proprietà `Parameters.Barcode.XDimension.Pixels` definisce la larghezza della barra stretta, mentre `Parameters.Barcode.BarHeight.Pixels` definisce l'altezza totale. Regola questi valori per soddisfare le specifiche del tuo servizio postale.

## Passo 4: Genera un codice a barre Planet

Planet è un codice a barre postale ampiamente usato nel Regno Unito. Il codice seguente crea un codice a barre Planet alto 100 px e lo salva come PNG.

```csharp
        // Step 4: Generate Planet barcode
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        planetGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;

        string planetPath = Path.Combine(outputFolder, "PostalPlanetBarHeight100Pixels.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);
```

**Perché funziona**: `EncodeTypes.Planet` indica al generatore di utilizzare la simbologia Planet. Il metodo `Save` scrive un file PNG nel percorso specificato, preservando le dimensioni impostate in precedenza.

## Passo 5: Genera un codice a barre RM4SCC

RM4SCC è lo standard di codice a barre postale olandese. Il codice qui sotto rispecchia l'esempio Planet, dimostrando **come generare un codice a barre postale** di tipo diverso con le stesse dimensioni.

```csharp
        // Step 5: Generate RM4SCC barcode
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;

        string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCBarHeight100Pixels.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);
```

Entrambi i file PNG ora risiedono nella cartella `Barcodes`. Aprirli mostrerà codici a barre puliti, alti 100 px, pronti per la stampa o per l'inserimento in documenti.

## Codice sorgente completo

Di seguito trovi il programma completo, eseguibile, che **crea file immagine di codice a barre postale** per gli standard Planet e RM4SCC.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // Ensure output directory exists
        string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // Dimension settings – reusable for all barcodes
        const int xDimensionPixels = 4;   // Width of a single bar
        const int barHeightPixels = 100; // Height of the barcode

        // ---- Generate Planet barcode ----
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        planetGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;
        string planetPath = Path.Combine(outputFolder, "PostalPlanetBarHeight100Pixels.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);

        // ---- Generate RM4SCC barcode ----
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;
        string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCBarHeight100Pixels.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);

        Console.WriteLine("Barcodes generated:");
        Console.WriteLine($"• {planetPath}");
        Console.WriteLine($"• {rm4sccPath}");
    }
}
```

### Output previsto

L'esecuzione del programma stampa i percorsi dei file e crea due file PNG:

```
Barcodes/
 ├─ PostalPlanetBarHeight100Pixels.png
 └─ PostalRM4SCCBarHeight100Pixels.png
```

Ogni immagine è alta 100 px, con una larghezza di barra stretta di 4 pixel, corrispondente alle dimensioni impostate.

## Consigli pratici e problemi comuni

* **Permessi della cartella** – Se il programma viene eseguito con un account con restrizioni, assicurati che la cartella di destinazione sia scrivibile.
* **Dimensioni diverse** – Per creare un codice a barre più alto, aumenta `barHeightPixels`. Per una risoluzione più fine, diminuisci `xDimensionPixels`, ma mantienila ≥ 2 per evitare artefatti di rendering.
* **Altre simbologie postali** – Aspose.BarCode supporta anche `EncodeTypes.Postnet` e `EncodeTypes.AustralianPost`. Sostituisci il valore di `EncodeTypes` mantenendo la stessa logica delle dimensioni.
* **Formato immagine** – Usa `BarCodeImageFormat.Jpeg` per ridurre le dimensioni del file quando la qualità senza perdita non è necessaria.

## Conclusione

Ora sai come **creare file immagine di codice a barre postale** in C# configurando le dimensioni, selezionando la simbologia corretta e salvando il risultato come PNG. Il tutorial ha coperto **come generare un codice a barre postale**, ha mostrato **come generare un codice a barre Planet** e ha spiegato **come impostare le dimensioni del codice a barre** per ottenere un output coerente.

Successivamente, esplora **la personalizzazione dei colori del codice a barre**, l'aggiunta di **testo leggibile dall'uomo**, o l'integrazione delle immagini in fatture PDF. Lo stesso schema si applica a qualsiasi altro tipo di codice a barre supportato da Aspose.BarCode, permettendoti di estendere questa soluzione a un flusso di lavoro completo di automazione postale.


## Cosa dovresti imparare dopo?


I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API e a esplorare approcci di implementazione alternativi nei tuoi progetti.

- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to generate barcode java – Australia Post Barcode with Aspose](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}