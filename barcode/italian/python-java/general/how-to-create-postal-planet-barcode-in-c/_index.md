---
category: general
date: 2026-11-23
description: Crea il codice a barre planet postale in C# con Aspose.BarCode. Scopri
  come generare il codice a barre planet, impostare la dimensione X e salvare le barre
  piene o vuote.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal planet barcode
- how to generate planet barcode
- Aspose.BarCode C#
- postal barcode example
- Planet barcode settings
language: it
lastmod: 2026-11-23
og_description: Crea un codice a barre planetario postale in C# e impara come generare
  il codice a barre planetario con Aspose.BarCode. Segui l'esempio completo per produrre
  barre piene e vuote.
og_image_alt: Example of a created postal planet barcode with filled bars
og_title: Come creare il codice a barre Postal Planet in C# – guida passo passo
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  headline: How to create postal planet barcode in C#
  type: TechArticle
- description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  name: How to create postal planet barcode in C#
  steps:
  - name: Changing the image format
    text: If your downstream system prefers JPEG, replace `BarCodeImageFormat.Png`
      with `BarCodeImageFormat.Jpeg`. JPEG introduces compression artifacts, so use
      it only when file size is a critical constraint.
  - name: Scaling the barcode
    text: 'You can enlarge the barcode while preserving the module width by adjusting
      the `Resolution` property:'
  - name: Using a custom background color
    text: 'The background can be set with:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Come creare il codice a barre Postal Planet in C#
url: /it/python-java/general/how-to-create-postal-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un codice a barre planetario postale in C#

Se hai bisogno di **creare un codice a barre planetario postale** in un'applicazione .NET, questa guida ti mostra esattamente **come generare un codice a barre planetario** usando la libreria Aspose.BarCode. Vedrai come configurare la dimensione X, passare da barre piene a barre vuote e salvare le immagini in formato PNG.

Generare un codice a barre Planet è comune per i servizi postali che richiedono simboli ad alta densità e leggibili da macchine. Alla fine di questo tutorial avrai due file PNG — uno con barre solide e uno con barre vuote — pronti per l'integrazione in qualsiasi flusso di lavoro di spedizione.

## Prerequisiti

* .NET 6.0 SDK o versioni successive installato.
* Visual Studio 2022 (o qualsiasi editor C#) configurato per lo sviluppo .NET.
* Una licenza NuGet attiva per **Aspose.BarCode for .NET**. Installa il pacchetto con:

```bash
dotnet add package Aspose.BarCode
```

Non sono richiesti servizi esterni aggiuntivi; la libreria esegue tutta la codifica localmente.

## Passo 1 – creare un codice a barre planetario postale

La prima operazione è istanziare un `BarcodeGenerator` per la simbologia **Planet** e fornire i dati da codificare. La stringa di dati deve essere numerica e fino a 12 cifre secondo la specifica postale.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

La creazione del generatore alloca tutte le strutture interne necessarie per il rendering. Il valore enum `EncodeTypes.Planet` seleziona l'algoritmo di codifica corretto per il formato postale.

## Passo 2 – impostare la dimensione X per una migliore visibilità

La dimensione X definisce la larghezza di un singolo modulo (l'elemento di barra più piccolo). Un valore di 4 pixel fornisce una rappresentazione visiva chiara senza ingrandire l'immagine complessiva.

```csharp
// Step 2: Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
```

Regolare la dimensione X è essenziale quando il codice a barre verrà stampato su supporti a bassa risoluzione. La stessa impostazione verrà riutilizzata per la versione a barre vuote per mantenere entrambe le immagini coerenti.

## Passo 3 – salvare il codice a barre con barre piene

Per impostazione predefinita il generatore rende **barra piene** (moduli neri solidi). Salvare l'immagine è una singola chiamata di metodo che scrive il file PNG su disco.

```csharp
// Step 3: Save the barcode with the default setting (filled bars)
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

Sostituisci `YOUR_DIRECTORY` con il percorso reale dove desideri i file di output. L'enumerazione `BarCodeImageFormat.Png` garantisce una compressione senza perdita, ideale per l'elaborazione successiva.

## Passo 4 – creare un altro generatore di codice a barre Planet per barre vuote

Per produrre una versione che utilizza **barra vuote** (moduli bianchi su sfondo nero), è necessaria una seconda istanza di `BarcodeGenerator`. Riutilizzare la stessa stringa di dati garantisce che entrambe le immagini rappresentino lo stesso codice postale.

```csharp
// Step 4: Create another Planet barcode generator for the same data
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

Creare un generatore separato isola la proprietà `FilledBars`, consentendoti di alternare lo stile visivo senza influenzare la prima immagine.

## Passo 5 – configurare il generatore per rendere barre vuote

Il flag `FilledBars` inverte la modalità di rendering. Impostandolo su `false` la libreria disegna le barre come vuote (trasparenti) mantenendo lo sfondo solido.

```csharp
// Step 5: Apply the same X‑dimension and configure empty bars
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
planetEmpty.Parameters.Barcode.FilledBars = false;
```

Mantenere la dimensione X identica alla versione con barre piene garantisce che entrambi i file PNG abbiano le stesse dimensioni, semplificando i calcoli di layout nei modelli di stampa.

## Passo 6 – salvare il codice a barre che rende barre vuote

Infine, scrivi l'immagine a barre vuote su disco. Viene utilizzato lo stesso formato PNG, ma è possibile passare a JPEG o BMP modificando il valore `BarCodeImageFormat`.

```csharp
// Step 6: Save the barcode that renders empty bars
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

A questo punto hai due file:

* `PostalPlanetFilledBars.png` – barre nere solide.
* `PostalPlanetEmptyBars.png` – barre vuote su sfondo nero.

Entrambi soddisfano la specifica postale per la simbologia Planet.

## Codice sorgente completo

Unendo tutti i passaggi si ottiene un'applicazione console compatta che puoi eseguire direttamente.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a Planet barcode with filled bars
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
            planetFilled.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

            // Create a Planet barcode with empty bars
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
            planetEmpty.Parameters.Barcode.FilledBars = false;
            planetEmpty.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcodes generated successfully.");
        }
    }
}
```

Compila ed esegui il programma:

```bash
dotnet run
```

La console stampa *Barcodes generated successfully.* e i due file PNG appaiono nella cartella del progetto.

## Output previsto

Di seguito è riportata una rappresentazione visiva dell'immagine con barre piene. La controparte con barre vuote appare identica, tranne per il fatto che le barre sono trasparenti.

![Esempio di un codice a barre planetario postale creato con barre piene](postal-planet-filled.png)

*Testo alternativo dell'immagine:* **Esempio di un codice a barre planetario postale creato con barre piene** (contiene la parola chiave principale).

Entrambe le immagini sono 150 × 150 pixel per impostazione predefinita, ma è possibile controllare le dimensioni complessive con i parametri `ImageWidth` e `ImageHeight` se è necessaria una risoluzione diversa.

## Variazioni opzionali

### Cambiare il formato immagine

Se il tuo sistema a valle preferisce JPEG, sostituisci `BarCodeImageFormat.Png` con `BarCodeImageFormat.Jpeg`. JPEG introduce artefatti di compressione, quindi usalo solo quando la dimensione del file è un vincolo critico.

### Ridimensionare il codice a barre

Puoi ingrandire il codice a barre mantenendo la larghezza del modulo regolando la proprietà `Resolution`:

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI
```

Valori DPI più alti migliorano la qualità di stampa su stampanti laser.

### Utilizzare un colore di sfondo personalizzato

Lo sfondo può essere impostato con:

```csharp
planetEmpty.Parameters.Barcode.BackColor = System.Drawing.Color.LightGray;
```

Questo è utile per test visivi ma dovrebbe essere evitato nelle etichette postali di produzione, che richiedono uno sfondo bianco.

## Domande frequenti

**Funziona con .NET Core?**  
Sì. La libreria Aspose.BarCode è destinata a .NET Standard 2.0, che è compatibile con .NET 5, .NET 6 e .NET Core 3.1.

**Cosa succede se la stringa di dati contiene caratteri non numerici?**  
I codici a barre Planet accettano solo input numerico. Fornire lettere o simboli genera una `BarcodeException`. Convalida l'input prima di creare il generatore.

**Posso generare un codice a barre in memoria senza scriverlo su disco?**  
Usa il metodo `GenerateBarCodeImage` per ottenere un oggetto `System.Drawing.Image`, quindi trasmettilo direttamente a una risposta o a un database.

## Conclusione

Ora sai come **creare un codice a barre planetario postale** in C# e comprendi **come generare un codice a barre planetario** con entrambi gli stili di barre piene e vuote. Il tutorial ha coperto l'intero flusso di lavoro — dall'inizializzazione del generatore, configurazione della dimensione X, attivazione del flag `FilledBars`, al salvataggio dei file PNG. Sperimenta con i formati immagine, le impostazioni DPI e i colori di sfondo per adattare il codice a barre al tuo specifico sistema di spedizione.

Per il passo successivo, esplora altre simbologie postali come **POSTNET** o **Intelligent Mail** usando la stessa API Aspose.BarCode. Regolare parametri come `EncodeTypes.Postnet` segue lo stesso schema mostrato qui, permettendoti di costruire una suite completa di generazione di codici a barre in un unico codice.

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Crea codice a barre planetario vuoto, genera codice a barre postale in C#](/barcode/english/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/)
- [Come impostare la larghezza e generare un codice a barre Planet in C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Genera codice a barre postale in C# – Guida completa con codice a barre Planet](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}