---
category: general
date: 2026-07-18
description: Crea rapidamente il codice a barre Planet con C#. Scopri come generare
  barre piene e vuote, impostare la dimensione X e salvare immagini PNG – tutto in
  un unico tutorial.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode generator
- BarcodeGenerator parameters
- XDimension pixels
- filled bars vs empty bars
language: it
lastmod: 2026-07-18
og_description: Crea il codice a barre Planet istantaneamente. Questa guida ti mostra
  come impostare la dimensione X, passare da barre piene a vuote e esportare file
  PNG con Aspose.BarCode.
og_image_alt: Screenshot of a generated Planet barcode saved as PNG
og_title: Crea Planet Barcode in C# – Guida completa alla programmazione
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create Planet barcode quickly with C#. Learn how to generate filled
    and empty bars, set X‑dimension, and save PNG images – all in one tutorial.
  headline: Create Planet Barcode in C# – Full Step‑by‑Step Guide
  type: TechArticle
- description: Create Planet barcode quickly with C#. Learn how to generate filled
    and empty bars, set X‑dimension, and save PNG images – all in one tutorial.
  name: Create Planet Barcode in C# – Full Step‑by‑Step Guide
  steps:
  - name: “Can I change the image format?”
    text: Absolutely. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `Bmp`,
      `Gif`, etc. Just replace `BarCodeImageFormat.Png` with your desired format.
  - name: “What if I need a different barcode height?”
    text: 'Use `planetBarcode.Parameters.Barcode.BarHeight` (in points) to increase
      or decrease the vertical size. For example:'
  - name: “Is there a way to add a human‑readable caption?”
    text: 'Yes. Set the `CodeText` property on `planetBarcode.Parameters.Caption`:'
  - name: “Do I need to dispose the generator?”
    text: 'The `BarcodeGenerator` implements `IDisposable`. Wrap it in a `using` block
      if you’re creating many barcodes in a loop:'
  - name: “What about error handling?”
    text: 'Enclose the `Save` calls in a `try…catch` block to capture `IOException`
      (disk issues) or `ArgumentException` (invalid parameters). Example:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Crea il codice a barre Planet in C# – Guida completa passo passo
url: /it/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea il codice a barre Planet in C# – Guida completa passo‑passo

Hai mai dovuto **creare immagini di codice a barre planet** ma non sapevi quali proprietà modificare? Non sei solo. Molti sviluppatori si trovano in difficoltà quando le barre riempite di default non soddisfano le specifiche, o quando la larghezza della barra deve corrispondere alla DPI della stampante.  

In questo tutorial imparerai esattamente come **creare file di codice a barre planet** usando la libreria Aspose.BarCode, come controllare i **pixel XDimension**, e come passare da **barre riempite** a **barre vuote** senza riscrivere alcun codice. Alla fine avrai due file PNG—uno con barre solide e uno con barre cave—pronti per qualsiasi sistema postale che richieda la simbologia Planet.

## Prerequisiti

- .NET 6.0 o successivo (il codice funziona anche su .NET Framework 4.7 +)  
- Pacchetto NuGet Aspose.BarCode for .NET (`Install-Package Aspose.BarCode`)  
- Conoscenze di base di C# (vedrai più avanti perché usiamo le istruzioni `using`)  
- Una cartella scrivibile su disco dove salvare i PNG  

Se hai tutto questo, possiamo passare subito all'implementazione.

## Passo 1 – Configura il progetto e aggiungi la libreria

Per prima cosa, crea una nuova console app (o qualsiasi progetto C#) e aggiungi il riferimento alla **libreria generatore di codice a barre Planet**.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // The rest of the code lives here
        }
    }
}
```

> **Suggerimento:** In Visual Studio, fai clic destro sul progetto → *Manage NuGet Packages* → cerca **Aspose.BarCode** e premi *Install*. Questo ti dà accesso a `BarcodeGenerator` e a tutti i **parametri di BarcodeGenerator** di cui avrai bisogno.

## Passo 2 – Inizializza il generatore di codice a barre Planet

Ora creiamo effettivamente l'istanza del generatore **planet barcode** e gli forniamo i dati da codificare (`"123456"` in questo esempio). L'enumerazione `EncodeTypes.Planet` indica alla libreria quale simbologia utilizzare.

```csharp
// Step 2: Initialise the generator with Planet symbology and data
BarcodeGenerator planetBarcode = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

> **Perché è importante:** Il flag `EncodeTypes.Planet` applica automaticamente il checksum corretto e le regole di layout per il codice a barre postale Planet, così non devi calcolarli manualmente.

## Passo 3 – Configura X‑Dimension (larghezza barra)

La maggior parte delle stampanti si aspetta che ogni barra abbia un numero specifico di pixel. Qui impostiamo i **pixel XDimension** a `4`, valore comune per stampanti termiche a 203 dpi.

```csharp
// Step 3: Set the width of each bar (X‑dimension) to 4 pixels
planetBarcode.Parameters.Barcode.XDimension.Pixels = 4;
```

> **Caso limite:** Se la tua stampante è a 300 dpi, potresti aver bisogno di `3` o `5` pixel. Regola questo valore in base alla documentazione del tuo dispositivo.

## Passo 4 – Salva la versione a barre riempite

Per impostazione predefinita il generatore produce **barre riempite** (rettangoli neri solidi). Scriviamola su disco:

```csharp
// Step 4: Save the barcode with default (filled) bars
planetBarcode.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

Sostituisci `YOUR_DIRECTORY` con un percorso assoluto o relativo a cui la tua app può scrivere. Dopo l'esecuzione di questa riga troverai un file PNG che assomiglia a un classico codice a barre Planet—perfetto per testarlo con uno scanner postale.

## Passo 5 – Passa a barre vuote

A volte i servizi postali richiedono lo stile “barre vuote”, dove le barre sono intagliate su uno sfondo bianco invece di essere dipinte di nero. La libreria espone un semplice interruttore:

```csharp
// Step 5: Re‑configure the generator to produce empty bars
planetBarcode.Parameters.Barcode.FilledBars = false;
```

Impostare `FilledBars` a `false` dice al renderer di invertire la logica di riempimento delle barre. Non è necessario creare una nuova istanza di `BarcodeGenerator`; basta modificare i **parametri di BarcodeGenerator** esistenti.

## Passo 6 – Salva la versione a barre vuote

Infine, esporta la seconda immagine:

```csharp
// Step 6: Save the barcode with empty bars
planetBarcode.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

Ora disponi di due file PNG distinti, ciascuno conforme a un requisito visivo diverso.

## Esempio completo funzionante

Mettendo insieme tutti i pezzi, ecco il programma completo, pronto per il copia‑incolla:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Initialise the Planet barcode generator with data
            BarcodeGenerator planetBarcode = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // Configure bar width (X‑dimension) – 4 pixels works for most 203 dpi printers
            planetBarcode.Parameters.Barcode.XDimension.Pixels = 4;

            // Save the default filled‑bars version
            planetBarcode.Save(@"C:\Barcodes\PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

            // Switch to empty‑bars style
            planetBarcode.Parameters.Barcode.FilledBars = false;

            // Save the empty‑bars version
            planetBarcode.Save(@"C:\Barcodes\PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

            Console.WriteLine("Both Planet barcode images have been generated successfully.");
        }
    }
}
```

**Output previsto** (sulla console):

```
Both Planet barcode images have been generated successfully.
```

E in `C:\Barcodes\` vedrai:

- `PostalPlanetFilledBars.png` – barre nere solide  
- `PostalPlanetEmptyBars.png` – barre bianche con contorni neri  

Aprili con qualsiasi visualizzatore di immagini; dovrebbero entrambi rispettare la specifica Planet.

## Domande comuni e consigli

### “Posso cambiare il formato dell’immagine?”

Assolutamente. Il metodo `Save` accetta `BarCodeImageFormat.Jpeg`, `Bmp`, `Gif`, ecc. Basta sostituire `BarCodeImageFormat.Png` con il formato desiderato.

### “E se ho bisogno di un’altezza diversa per il codice a barre?”

Usa `planetBarcode.Parameters.Barcode.BarHeight` (in punti) per aumentare o diminuire la dimensione verticale. Per esempio:

```csharp
planetBarcode.Parameters.Barcode.BarHeight = 30; // 30 points tall
```

### “C’è un modo per aggiungere una didascalia leggibile dall’uomo?”

Sì. Imposta la proprietà `CodeText` su `planetBarcode.Parameters.Caption`:

```csharp
planetBarcode.Parameters.Caption.Visible = true;
planetBarcode.Parameters.Caption.TopMargin = 5; // space between barcode and text
planetBarcode.Parameters.Caption.Text = "123456";
```

### “Devo rilasciare il generatore?”

Il `BarcodeGenerator` implementa `IDisposable`. Avvolgilo in un blocco `using` se crei molti codici a barre in un ciclo:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(...))
{
    // configure and save
}
```

### “E per la gestione degli errori?”

Racchiudi le chiamate a `Save` in un blocco `try…catch` per catturare `IOException` (problemi di disco) o `ArgumentException` (parametri non validi). Esempio:

```csharp
try
{
    planetBarcode.Save(path, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to save barcode: {ex.Message}");
}
```

## Riepilogo

Abbiamo coperto tutto ciò che serve per **creare immagini di codice a barre planet** in C#:

1. Inizializza il **generatore di codice a barre Planet** con i tuoi dati.  
2. Regola i **pixel XDimension** per corrispondere alle specifiche della stampante.  
3. Salva un PNG con **barre riempite**.  
4. Attiva `FilledBars` per produrre **barre vuote**.  
5. Salva il secondo PNG.  

Da qui puoi esplorare altri **parametri di BarcodeGenerator**, sperimentare con altre simbologie (`EncodeTypes.Postnet`, `EncodeTypes.Code128`, ecc.), o integrare le immagini in un flusso di lavoro di spedizione.

---

**Pronto per il passo successivo?** Prova ad aggiungere un QR code allo stesso documento, o genera un batch di codici a barre Planet da un elenco CSV usando un ciclo `foreach`. L’API Aspose.BarCode è sufficientemente flessibile da gestire operazioni in blocco, colori personalizzati e persino output vettoriale SVG.

Se incontri difficoltà, lascia un commento qui sotto o consulta la documentazione ufficiale di Aspose.BarCode per approfondimenti sulle funzionalità avanzate. Buona programmazione!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi con spiegazioni passo‑passo per aiutarti a padroneggiare ulteriori funzionalità dell’API e a esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Crea codice a barre con Aspose - Imposta le dimensioni X & Y in Java](/barcode/english/java/barcode-configuration/managing-x-y-dimension-barcode/)
- [Come creare immagini di codice a barre code128 in Java con Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)
- [Come creare codice a barre code128 in Java e impostare l’altezza della barra](/barcode/english/java/barcode-configuration/setting-bars-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}