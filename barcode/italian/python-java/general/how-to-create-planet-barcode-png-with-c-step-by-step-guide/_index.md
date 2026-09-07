---
category: general
date: 2026-09-07
description: Crea barcode planet PNG in C# rapidamente. Scopri come generare immagini
  di barcode planet usando Aspose.BarCode con barre piene e vuote.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode png
- how to generate planet barcode
language: it
lastmod: 2026-09-07
og_description: Crea rapidamente un PNG di barcode planet in C#. Segui questa guida
  per imparare a generare immagini di barcode planet con barre piene e vuote usando
  Aspose.BarCode.
og_image_alt: Planet barcode PNG image showing filled bars and empty‑bars version
og_title: Crea barcode planet PNG in C# – tutorial completo di programmazione
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  headline: How to create planet barcode PNG with C# – step‑by‑step guide
  type: TechArticle
- description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  name: How to create planet barcode PNG with C# – step‑by‑step guide
  steps:
  - name: What if I need a different data format?
    text: 'Planet barcodes accept numeric strings up to 12 digits. If you pass a non‑numeric
      value, Aspose throws an `ArgumentException`. Validate the input before creating
      the generator:'
  - name: How do I change the image size without altering bar thickness?
    text: 'Use the `Resolution` property or scale the resulting bitmap after saving:'
  - name: Can I generate other image formats?
    text: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`, `Bmp`,
      or `Gif`. The API supports all common raster formats.
  - name: What about color customization?
    text: 'Set `BarColor` and `BackColor` on the `Barcode` parameters:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Come creare un PNG di barcode planet con C# – guida passo passo
url: /it/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare barcode planet PNG con C# – guida passo‑passo

Se hai bisogno di **creare file PNG di barcode planet** in C#, questa guida ti mostra i passaggi esatti. Che tu stia costruendo un'integrazione per il servizio postale o un cruscotto logistico, imparerai **come generare immagini di barcode planet** con barre sia riempite che vuote usando la libreria Aspose.BarCode.

In questo tutorial tu:

* Impostare la cartella di output per le tue immagini.  
* Configurare un `BarcodeGenerator` per la simbologia Planet.  
* Generare un PNG con lo stile predefinito a barre riempite.  
* Generare un PNG con barre vuote per contrasto visivo.  

Non sono richiesti servizi esterni—tutto viene eseguito localmente su .NET 6 o versioni successive.

## Prerequisiti

Prima di iniziare, assicurati di avere:

| Requisito | Perché è importante |
|-------------|----------------|
| .NET 6 SDK (or newer) | Fornisce l'ambiente di esecuzione per l'app console C#. |
| Visual Studio 2022 or VS Code | Qualsiasi IDE in grado di compilare progetti C#. |
| Aspose.BarCode for .NET (NuGet package `Aspose.BarCode`) | Fornisce la classe `BarcodeGenerator` usata per generare i barcode Planet. |
| Write permission to a folder on disk | I file PNG saranno salvati in questa posizione. |

Installa il pacchetto NuGet con il seguente comando:

```bash
dotnet add package Aspose.BarCode
```

## Passo 1: Creare un nuovo progetto console

Apri un terminale ed esegui:

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
```

Questo genera una minima applicazione console C# denominata **PlanetBarcodeDemo**.

## Passo 2: Definire la directory di output

Il primo blocco di codice determina dove verranno salvati i file PNG generati. Funziona sia con un percorso assoluto che relativo; assicurati solo che la cartella esista o lascia che il programma la crei.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Define the output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputDir); // Guarantees the folder exists
```

*Perché questo passaggio?* Separare l'output dal codice sorgente mantiene il progetto ordinato ed evita sovrascritture accidentali.

## Passo 3: Generare un barcode Planet a barre riempite

Un barcode Planet è composto da cerchi concentrici (riempiti per impostazione predefinita). Configuriamo la dimensione X (larghezza in pixel di ogni barra) e poi salviamo l'immagine come PNG.

```csharp
        // Step 3: Create a Planet barcode with the default (filled) bars
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4; // Controls bar thickness

        // Save the filled‑bars barcode as PNG
        string filledPath = Path.Combine(outputDir, "PostalPlanetFilledBars.png");
        planetFilled.Save(filledPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Filled‑bars barcode saved to: {filledPath}");
```

**Spiegazione**

* `EncodeTypes.Planet` indica ad Aspose di usare la simbologia Planet, comune per i servizi postali.  
* `XDimension.Pixels = 4` produce una dimensione chiara e stampabile senza scalatura manuale.  
* Il metodo `Save` scrive un file PNG; è possibile scegliere anche JPEG o BMP modificando `BarCodeImageFormat`.

## Passo 4: Generare un barcode Planet a barre vuote

Talvolta è necessario un visual con barre vuote (trasparenti)—ad esempio quando il barcode è sovrapposto a uno sfondo colorato. Impostare `FilledBars` a `false` produce questo stile.

```csharp
        // Step 4: Create a Planet barcode with empty bars
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        planetEmpty.Parameters.Barcode.FilledBars = false; // Switch to empty‑bars mode

        // Save the empty‑bars barcode as PNG
        string emptyPath = Path.Combine(outputDir, "PostalPlanetEmptyBars.png");
        planetEmpty.Save(emptyPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Empty‑bars barcode saved to: {emptyPath}");
```

**Spiegazione**

* `FilledBars = false` disabilita i cerchi solidi, lasciando solo i contorni.  
* Tutte le altre impostazioni (dimensione X, stringa dati) rimangono identiche, garantendo che entrambe le immagini rappresentino gli stessi dati.

## Passo 5: Eseguire il programma e verificare l'output

Compila ed esegui:

```bash
dotnet run
```

Dovresti vedere messaggi nella console che confermano i file salvati, e la cartella `Barcodes` conterrà:

* `PostalPlanetFilledBars.png` – un classico barcode Planet a barre riempite.  
* `PostalPlanetEmptyBars.png` – gli stessi dati renderizzati con barre vuote.

Apri i PNG in qualsiasi visualizzatore di immagini. Entrambe le immagini codificano la stringa numerica **123456** e possono essere lette da lettori di barcode postali standard.

## Domande comuni e gestione dei casi limite

### E se ho bisogno di un formato dati diverso?

I barcode Planet accettano stringhe numeriche fino a 12 cifre. Se passi un valore non numerico, Aspose lancia un `ArgumentException`. Convalida l'input prima di creare il generatore:

```csharp
if (!Regex.IsMatch(data, @"^\d{1,12}$"))
    throw new ArgumentException("Planet barcode data must be numeric and up to 12 digits.");
```

### Come modificare la dimensione dell'immagine senza alterare lo spessore delle barre?

Usa la proprietà `Resolution` o scala il bitmap risultante dopo il salvataggio:

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI for high‑resolution print
```

### Posso generare altri formati immagine?

Sì. Sostituisci `BarCodeImageFormat.Png` con `BarCodeImageFormat.Jpeg`, `Bmp` o `Gif`. L'API supporta tutti i formati raster comuni.

### E per la personalizzazione dei colori?

Imposta `BarColor` e `BackColor` sui parametri `Barcode`:

```csharp
planetFilled.Parameters.Barcode.BarColor = Color.DarkBlue;
planetFilled.Parameters.Barcode.BackColor = Color.LightYellow;
```

Queste opzioni funzionano sia per le versioni a barre riempite che vuota.

## Consigli professionali per l'uso in produzione

* **Cache il generatore** quando devi renderizzare molti barcode con le stesse impostazioni—l'inizializzazione ripetuta dell'oggetto aggiunge overhead.  
* **Dispose** degli oggetti `BarcodeGenerator` se ne crei molti in un ciclo (implementano `IDisposable`).  
* **Convalida la cartella di output** in anticipo per evitare eccezioni a runtime su directory protette in scrittura.  

## Conclusione

Ora sai come **creare file PNG di barcode planet** in C# e comprendi **come generare immagini di barcode planet** con entrambi gli stili a barre riempite e vuote. L'esempio completo e eseguibile dimostra come impostare la directory di output, configurare il `BarcodeGenerator` e salvare i risultati come file PNG.

Successivamente, potresti esplorare:

* Aggiungere **testo leggibile dall'uomo** sotto il barcode (`planetFilled.Parameters.Caption.Visible = true`).  
* Integrare i PNG generati in una **fattura PDF** usando Aspose.PDF.  
* Passare ad altre simbologie postali come **IMB** o **ITF** (`EncodeTypes.IMB`, `EncodeTypes.ITF`).  

Sentiti libero di sperimentare con lo spessore delle barre, i colori e le risoluzioni delle immagini per soddisfare i requisiti specifici della tua applicazione. Buon coding!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Crea immagine barcode Planet in C# – Come generare barcode postale](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Crea barcode Planet in C# – Guida completa passo‑passo](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Genera barcode PNG con Aspose.BarCode per .NET: Barre unidimensionali riempite](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-filled-bars-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}