---
category: general
date: 2026-09-26
description: Impara come creare un'immagine di codice a barre postale in C#. Questa
  guida ti mostra come generare il codice a barre Planet e impostare l’altezza del
  codice a barre per un output personalizzato.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- barcode generator custom height
- how to set barcode height
language: it
lastmod: 2026-09-26
og_description: Crea rapidamente un'immagine di codice a barre postale in C#. Segui
  questo tutorial per generare il codice a barre planet, impostare l'altezza del codice
  a barre e produrre file PNG di alta qualità.
og_image_alt: Screenshot of a generated postal barcode image with custom bar height
og_title: Crea immagine di codice a barre postale con altezze personalizzate in C#
  – guida passo‑passo
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create postal barcode image in C#. This guide shows you
    how to generate planet barcode and set barcode height for custom output.
  headline: How to create postal barcode image with custom heights in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: Come creare un'immagine di codice a barre postale con altezze personalizzate
  in C#
url: /it/python-java/general/how-to-create-postal-barcode-image-with-custom-heights-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un'immagine di codice a barre postale con altezze personalizzate in C#

Se hai bisogno di **creare un'immagine di codice a barre postale** per le etichette di spedizione, questo tutorial ti mostra i passaggi esatti. Imparerai a generare un codice a barre Planet, regolare l'altezza della barra e salvare il risultato come file PNG — il tutto con la libreria Aspose.BarCode per .NET.

Creare un'immagine di codice a barre non richiede uno strumento di progettazione esterno. Alla fine di questa guida potrai produrre codici a barre sia con altezza predefinita sia con altezza personalizzata per gli standard Planet e RM4SCC, pronti per l'integrazione in qualsiasi flusso di lavoro di spedizione.

## Prerequisiti

* .NET 6.0 o versioni successive installate  
* Visual Studio 2022 (o qualsiasi IDE C#)  
* Aspose.BarCode per .NET aggiunto tramite NuGet (`Install-Package Aspose.BarCode`)  

Non è necessaria alcuna configurazione aggiuntiva; la libreria gestisce il rendering dell'immagine internamente.

## Passo 1: Configura il progetto e importa i namespace

Crea una nuova applicazione console e aggiungi le dichiarazioni `using` richieste.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Questi namespace espongono la classe `BarcodeGenerator` e l'enumerazione `EncodeTypes` che utilizzerai per **generare il codice a barre planet** e altri formati postali.

## Passo 2: Crea un codice a barre Planet con l'altezza della barra predefinita

Il primo esempio crea un codice a barre Planet utilizzando l'altezza della barra predefinita della libreria. Questo dimostra l'output di base prima di applicare qualsiasi dimensionamento personalizzato.

```csharp
// Initialize the generator for a Planet barcode
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the X‑dimension (module width) to 4 pixels for better readability
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the barcode image; the default bar height is applied automatically
planetGenerator.Save("PostalPlanetBarHeightDefault.png", BarCodeImageFormat.Png);
```

**Perché è importante:** L'altezza predefinita è adatta alla maggior parte delle stampanti di etichette, ma alcuni flussi di lavoro richiedono barre più alte per una maggiore affidabilità della scansione. Il codice sopra ti fornisce un'immagine di riferimento da confrontare con la versione a altezza personalizzata.

## Passo 3: Applica un'altezza della barra personalizzata al codice a barre Planet

Per **impostare manualmente l'altezza del codice a barre**, assegna un valore in pixel a `BarHeight.Pixels`. Il frammento seguente crea un codice a barre Planet alto 100 pixel.

```csharp
// Initialize a second generator for the same data
BarcodeGenerator planetHeightGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Define X‑dimension and a custom bar height of 100 pixels
planetHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
planetHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the custom‑height image
planetHeightGenerator.Save("PostalPlanetBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

**Consiglio professionale:** Scegli un'altezza della barra che corrisponda al DPI della tua stampante. Per una stampante da 300 dpi, una barra di 100 pixel corrisponde a circa 0,33 pollici, valore spesso consigliato per gli scanner postali.

## Passo 4: Genera un codice a barre RM4SCC con altezza predefinita

RM4SCC è un'altra simbologia postale comune. Il processo rispecchia l'esempio Planet ma utilizza `EncodeTypes.RM4SCC`.

```csharp
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Set X‑dimension; the library applies the default bar height automatically
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccGenerator.Save("PostalRM4SCCBarHeightDefault.png", BarCodeImageFormat.Png);
```

Questo passo conferma che la stessa logica di **altezza personalizzata del generatore di codici a barre** funziona su diversi formati postali.

## Passo 5: Applica un'altezza personalizzata al codice a barre RM4SCC

Infine, regola l'altezza della barra per il codice a barre RM4SCC nello stesso modo in cui hai fatto per il codice a barre Planet.

```csharp
BarcodeGenerator rm4sccHeightGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Define both X‑dimension and a 100‑pixel bar height
rm4sccHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the custom‑height image
rm4sccHeightGenerator.Save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

## Output previsto

Eseguendo il programma completo vengono generati quattro file PNG nella directory di output del progetto:

| Nome file                               | Altezza barra | Simbolia |
|----------------------------------------|---------------|----------|
| `PostalPlanetBarHeightDefault.png`     | default       | Planet   |
| `PostalPlanetBarHeight100Pixels.png`   | 100 px        | Planet   |
| `PostalRM4SCCBarHeightDefault.png`     | default       | RM4SCC   |
| `PostalRM4SCCBarHeight100Pixels.png`   | 100 px        | RM4SCC   |

Ogni immagine mostra un codice a barre chiaro e ad alto contrasto, pronto per la stampa su etichette di spedizione. Puoi aprire i file PNG in qualsiasi visualizzatore di immagini per verificare le dimensioni delle barre.

## Domande comuni e casi particolari

**E se avessi bisogno di un'altezza della barra in millimetri invece che in pixel?**  
La libreria funziona in pixel perché mappa direttamente alla risoluzione del bitmap. Converti i millimetri in pixel usando il DPI della stampante:  
`pixels = (mm / 25.4) * DPI`. Imposta `BarHeight.Pixels` con il valore calcolato.

**Posso modificare l'altezza della barra dopo aver chiamato `Save`?**  
No. L'immagine del codice a barre viene renderizzata nel momento in cui viene invocato `Save`. Regola tutti i parametri prima di chiamare `Save`.

**È necessaria una X‑dimensione più grande per barre più alte?**  
Aumentare `XDimension` rende ogni modulo più largo, il che può migliorare la leggibilità su stampanti a bassa risoluzione. Tuttavia, aumenta anche la larghezza complessiva del codice a barre. Prova entrambi i valori per trovare il bilanciamento ottimale per la dimensione della tua etichetta.

**Il medesimo codice funzionerà su .NET Framework 4.8?**  
Sì. Aspose.BarCode supporta .NET Framework 4.6.2 e versioni successive, quindi puoi puntare a runtime più vecchi senza modifiche.

## Codice sorgente completo per copia‑incolla veloce

Di seguito trovi il programma completo e eseguibile che incorpora tutti i passaggi descritti sopra.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // ---------- Planet barcode (default height) ----------
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        planetGenerator.Save("PostalPlanetBarHeightDefault.png", BarCodeImageFormat.Png);

        // ---------- Planet barcode (custom 100‑pixel height) ----------
        BarcodeGenerator planetHeightGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        planetHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        planetHeightGenerator.Save("PostalPlanetBarHeight100Pixels.png", BarCodeImageFormat.Png);

        // ---------- RM4SCC barcode (default height) ----------
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccGenerator.Save("PostalRM4SCCBarHeightDefault.png", BarCodeImageFormat.Png);

        // ---------- RM4SCC barcode (custom 100‑pixel height) ----------
        BarcodeGenerator rm4sccHeightGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4sccHeightGenerator.Save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);

        Console.WriteLine("All barcode images have been generated successfully.");
    }
}
```

Esegui il programma e la console confermerà che ogni immagine è stata salvata. Ora puoi incorporare questi file PNG nei tuoi modelli di etichette di spedizione, stamparli o inviarli a un'API di logistica di terze parti.

## Conclusione

Ora sai come **creare file di codice a barre postale** in C# usando Aspose.BarCode. La guida ha coperto la generazione di un codice a barre Planet, la regolazione dell'altezza della barra e l'applicazione della stessa tecnica ai codici a barre RM4SCC. Controllando `XDimension` e `BarHeight.Pixels`, ottieni risultati visivi precisi che soddisfano i requisiti dei servizi postali.

Successivamente, esplora argomenti correlati come **generare codici QR per il tracciamento**, **incorporare codici a barre in fatture PDF**, o **elaborare in batch più immagini di codici a barre**. Regolare l'altezza della barra è solo una leva; puoi anche personalizzare i colori, aggiungere testo leggibile dall'uomo o esportare in SVG per l'uso web.

Buona programmazione e che le tue spedizioni vengano scansionate senza problemi!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Crea immagine di codice a barre postale in C# – guida passo‑passo](/barcode/english/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/)
- [Crea immagini di codici a barre postali – modifica facilmente l'altezza del codice a barre](/barcode/english/python-java/general/create-postal-barcode-images-change-barcode-height-easily/)
- [Come generare un codice a barre postale in C# con dimensioni personalizzate](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}