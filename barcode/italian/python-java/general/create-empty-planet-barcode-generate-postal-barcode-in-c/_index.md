---
category: general
date: 2026-10-08
description: Crea un codice a barre Planet vuoto con C# e impara come generare un
  codice a barre postale usando Aspose.BarCode. Codice passo‑passo e consigli inclusi.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create empty planet barcode
- how to generate postal barcode
- Aspose.BarCode C#
- postal barcode example
- barcode XDimension setting
language: it
lastmod: 2026-10-08
og_description: Crea un codice a barre Planet vuoto con Aspose.BarCode in C# e scopri
  come generare immagini di codici a barre postali per le applicazioni di posta.
og_image_alt: Screenshot of generated empty Planet barcode and filled RM4SCC barcode
og_title: Crea un codice a barre Planet vuoto – Guida al codice a barre postale in
  C#
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Create empty planet barcode with C# and learn how to generate postal
    barcode using Aspose.BarCode. Step‑by‑step code and tips included.
  headline: Create empty planet barcode, generate postal barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- postal
title: Crea un codice a barre di pianeta vuoto, genera il codice a barre postale in
  C#
url: /it/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea un codice a barre planet vuoto, genera un codice a barre postale in C#

Se hai bisogno di **creare un codice a barre planet vuoto** per un sistema di spedizione, questa guida ti mostra esattamente come farlo con Aspose.BarCode per .NET. Imparerai anche **come generare immagini di codici a barre postali** come Planet e RM4SCC, personalizzare la larghezza delle barre e controllare l’opzione barre‑riempite.

La generazione di codici a barre postali non richiede una libreria grafica separata. L'SDK Aspose.BarCode fornisce un’unica API che gestisce la codifica, il rendering dell’immagine e la selezione del formato dell’immagine. Alla fine di questo tutorial avrai tre file PNG pronti all’uso:

* `PostalPlanetEmptyBars.png` – un codice a barre Planet con barre vuote  
* `PostalPlanetFilledBars.png` – il codice a barre Planet con barre riempite predefinite  
* `PostalRM4SCCFilledBars.png` – un codice a barre RM4SCC con barre riempite  

Puoi inserire questi file in qualsiasi modello di etichetta di spedizione, stamparli su buste o passarli a un servizio di terze parti.

## Prerequisiti

* .NET 6.0 o successivo (il codice funziona anche con .NET Framework 4.7+).  
* Visual Studio 2022 o qualsiasi IDE C#.  
* Aspose.BarCode for .NET – installa tramite NuGet:

```bash
dotnet add package Aspose.BarCode
```

Non sono richieste dipendenze aggiuntive.

## Crea un codice a barre planet vuoto con Aspose.BarCode

La simbologia Planet fa parte della famiglia di codici a barre del United States Postal Service (USPS). Per impostazione predefinita l'SDK disegna **barre riempite**. Per **creare un codice a barre planet vuoto**, disabiliti il flag `FilledBars`.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 1 – instantiate a Planet barcode generator with the data to encode.
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Step 2 – set the width of a single bar. XDimension defines the pixel size of one bar.
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Step 3 – disable the FilledBars option to get empty (hollow) bars.
planetEmpty.Parameters.Barcode.FilledBars = false;

// Step 4 – save the image. The PNG format is widely supported by printers and browsers.
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**Perché funziona:**  
`EncodeTypes.Planet` indica al generatore di utilizzare la simbologia Planet. `XDimension.Pixels` controlla la larghezza fisica di ogni barra, fondamentale per gli scanner postali che si aspettano una dimensione di modulo specifica. Impostare `FilledBars` a `false` dice al renderer di disegnare solo il contorno di ogni barra, producendo l’aspetto *vuoto* richiesto da alcuni standard di spedizione.

### Output previsto

Troverai `PostalPlanetEmptyBars.png` nella cartella di destinazione. L’immagine mostra un codice a barre Planet in cui ogni barra è un contorno anziché un rettangolo pieno.

![Empty Planet barcode example](empty-planet.png){: .align-center alt="Crea un codice a barre planet vuoto – esempio di un codice a barre Planet con barre vuote"}

## Come generare immagini di codici a barre postali (versione riempita)

La maggior parte dei flussi di lavoro postali utilizza la versione predefinita con barre riempite. La stessa API può generare un codice a barre Planet riempito e un codice a barre RM4SCC con poche righe di codice.

```csharp
// Filled Planet barcode (default behavior)
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// RM4SCC barcode – another USPS format that always uses filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
```

**Perché potresti aver bisogno di RM4SCC:**  
RM4SCC è il nuovo codice a barre USPS che codifica gli stessi dati di Planet ma con una densità maggiore. Alcuni corrieri richiedono RM4SCC per sconti su spedizioni di massa. Il codice sopra dimostra **come generare un codice a barre postale** per entrambi gli standard senza modificare il flusso di lavoro complessivo.

### Output previsto

* `PostalPlanetFilledBars.png` – un classico codice a barre Planet con barre riempite.  
* `PostalRM4SCCFilledBars.png` – un codice a barre RM4SCC con barre riempite, visivamente simile ma con spaziatura più stretta.

Entrambi i file possono essere aperti con qualsiasi visualizzatore di immagini per verificare i pattern delle barre.

## Regolare la larghezza delle barre per diverse risoluzioni di stampa

Gli scanner postali spesso specificano una larghezza minima del modulo (ad es., 0,013 pollici). Se la tua stampante lavora a 300 dpi, un modulo di 4 pixel corrisponde a 0,013 pollici. Regola il valore `XDimension.Pixels` per adattarlo al tuo hardware:

| Modulo desiderato (pollici) | DPI | Pixel necessari (`XDimension`) |
|-----------------------------|-----|---------------------------------|
| 0.013                       | 300 | 4                               |
| 0.013                       | 600 | 8                               |
| 0.015                       | 300 | 5                               |

**Consiglio professionale:** Testa sempre una


## Cosa dovresti imparare dopo?


I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare ulteriori funzionalità dell’API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [How to create planet barcode PNG with C# – step‑by‑step guide](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/)
- [Generate Postal Barcode in C# – Complete Guide with Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)
- [How to generate postal barcode in C# with Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}