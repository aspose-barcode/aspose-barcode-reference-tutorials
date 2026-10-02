---
category: general
date: 2026-08-06
description: Crea rapidamente un codice a barre DataBar impilato in C#. Impara a impostare
  la dimensione X, regolare il rapporto d'aspetto e esportare file PNG utilizzando
  il generatore DataBar Stacked Omnidirectional.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode aspect ratio
- BarcodeGenerator C#
- BarCodeImageFormat PNG
language: it
lastmod: 2026-08-06
og_description: Crea un codice a barre databar impilato in C# con Aspose.BarCode.
  Questo tutorial mostra come configurare la dimensione X, modificare il rapporto
  d'aspetto e salvare immagini PNG.
og_image_alt: Screenshot of two PNG files generated from a DataBar Stacked Omnidirectional
  barcode with different aspect ratios
og_title: Crea codice a barre databar impilato in C# – guida completa di programmazione
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Create databar stacked barcode in C# quickly. Learn to set X dimension,
    adjust aspect ratio, and export PNG files using the DataBar Stacked Omnidirectional
    generator.
  headline: Create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Crea codice a barre Databar impilato in C# – guida passo passo
url: /it/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea databar stacked barcode in C# – guida passo‑passo

Se hai bisogno di **creare databar stacked barcode** immagini in C#, questa guida ti mostra esattamente come farlo usando la libreria Aspose.BarCode. Imparerai a impostare la dimensione X, modificare il rapporto d'aspetto del barcode e salvare il risultato come file PNG—tutto in pochi passaggi concisi.

Generare un DataBar Stacked barcode è comune quando devi codificare dati GS1‑128 per la scansione al dettaglio o il tracciamento logistico. Nelle sezioni successive copriamo tutto, dalla configurazione del progetto alla verifica dell'output, così potrai integrare la soluzione in qualsiasi applicazione .NET senza perdere alcun dettaglio.

## Prerequisiti

* **.NET 6.0** (o successivo) installato – il codice è destinato al moderno SDK.
* Una copia **licenziata** di **Aspose.BarCode for .NET**. La valutazione gratuita funziona per i test ma aggiunge una filigrana.
* Un IDE come **Visual Studio 2022** o **VS Code** con l'estensione C#.
* Familiarità di base con la sintassi **C#** e il concetto di Identificatori di Applicazione GS1.

> **Suggerimento professionale:** Se usi il gestore di pacchetti NuGet, il comando `dotnet add package Aspose.BarCode` risolve automaticamente tutte le dipendenze.

## Passo 1: Crea un nuovo progetto console

Apri un terminale o la Console di Gestione Pacchetti e esegui:

```bash
dotnet new console -n DatabarStackedDemo
cd DatabarStackedDemo
dotnet add package Aspose.BarCode
```

Il comando `dotnet new console` genera un file **Program.cs** minimale. Aggiungere il pacchetto **Aspose.BarCode** rende disponibile la classe `BarcodeGenerator`.

## Passo 2: Inizializza il generatore DataBar Stacked Omnidirectional

Apri **Program.cs** e sostituisci il contenuto predefinito con il codice seguente. La prima riga crea un **BarcodeGenerator** configurato per la simbologia **DataBar Stacked Omnidirectional** e fornisce un payload GS1‑128.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a DataBar Stacked Omnidirectional barcode
        // "(01)12345678901231" encodes a GTIN‑14 with Application Identifier (01)
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Continue with configuration...
```

**Perché è importante:** Il valore enum `EncodeTypes.DatabarStackedOmniDirectional` indica alla libreria di produrre un **databar stacked barcode**, che è la variante stacked della famiglia DataBar omnidirezionale. Questa simbologia può contenere fino a 14 caratteri numerici, rendendola ideale per i codici GTIN‑14.

## Passo 3: Imposta la dimensione X (larghezza del modulo)

La dimensione X controlla la larghezza della barra più piccola (il modulo). Un valore troppo piccolo può risultare poco leggibile su stampanti a bassa risoluzione, mentre un valore troppo grande può superare lo spazio disponibile sull'etichetta.

```csharp
        // Step 3: Define the module width – 2 pixels gives a crisp, printable barcode
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Suggerimento:** La proprietà `Pixels` è comoda per i test basati su schermo. Per scenari focalizzati sulla stampa, usa invece `generator.Parameters.Barcode.XDimension.Millimeters`.

## Passo 4: Regola il rapporto d'aspetto e salva la prima immagine

Il **rapporto d'aspetto** influenza la relazione altezza‑larghezza del barcode stacked. Il tipo DataBar Stacked Omnidirectional supporta rapporti da 10 a 30. Genereremo due immagini per illustrare l'impatto visivo.

```csharp
        // Step 4a: Set aspect ratio to 15 (default is 15) and save as PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

La chiamata a `generator.Save` scrive un file **PNG** nella directory di lavoro corrente. L'enum `BarCodeImageFormat.Png` garantisce una compressione senza perdita, ideale per ulteriori elaborazioni o per l'incorporamento in PDF.

## Passo 5: Cambia il rapporto d'aspetto a 30 e salva la seconda immagine

Ora aumentiamo l'altezza delle barre stacked modificando il rapporto d'aspetto a **30**. Questo rende il barcode più alto senza alterare la dimensione X.

```csharp
        // Step 5a: Increase aspect ratio to 30 for a taller barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been generated:");
        Console.WriteLine(" • DatabarAspectRatio15.png");
        Console.WriteLine(" • DatabarAspectRatio30.png");
    }
}
```

Eseguendo il programma ora produce due file PNG:

* **DatabarAspectRatio15.png** – un barcode compatto adatto a etichette piccole.
* **DatabarAspectRatio30.png** – un barcode più alto che migliora l'affidabilità della scansione su superfici a basso contrasto.

Puoi aprire le immagini con qualsiasi visualizzatore per verificare che le barre siano correttamente impilate e che i dati codificati corrispondano alla stringa GS1 originale.

## Passo 6: Verifica il valore codificato (opzionale)

Se devi confermare che il barcode rappresenta effettivamente la stringa di input, puoi decodificarlo con la stessa libreria:

```csharp
        // Optional: Decode the generated PNG to ensure correctness
        var decoder = new BarCodeReader("DatabarAspectRatio15.png", DecodeType.DatabarStackedOmniDirectional);
        foreach (BarCodeResult result in decoder.ReadBarCodes())
        {
            Console.WriteLine($"Decoded text: {result.CodeText}");
        }
```

Il decodificatore dovrebbe restituire `(01)12345678901231`, dimostrando che il processo di **creare databar stacked barcode** ha preservato i dati.

## Problemi comuni e come evitarli

| Problema | Perché succede | Soluzione |
|----------|----------------|-----------|
| Il barcode appare sfocato | Dimensione X impostata troppo bassa per la risoluzione di output | Aumentare `XDimension.Pixels` o usare `Millimeters` per la stampa |
| Lo scanner segnala “simbolo non trovato” | Rapporto d'aspetto fuori dall'intervallo supportato 10‑30 | Mantenere il rapporto tra 10 e 30; 15 e 30 sono valori predefiniti sicuri |
| Il PNG contiene una filigrana | Uso della licenza di valutazione gratuita di Aspose.BarCode | Acquistare una licenza completa o usare la versione di prova solo per i test |
| Decodifica fallita nella seconda immagine | Il decodificatore era configurato per la simbologia errata | Usare `DecodeType.DatabarStackedOmniDirectional` quando si leggono barcode stacked |

## Prossimi passi

Ora che puoi **creare databar stacked barcode** immagini, potresti voler:

* **Incorpora i PNG in fatture PDF** usando una libreria PDF come **Aspose.PDF**.
* **Genera barcode al volo in una Web API** – restituisci i byte PNG direttamente da un controller ASP.NET Core.
* **Sperimenta con altre varianti DataBar** (ad es., `DatabarExpanded`, `DatabarLimited`) modificando l'enum `EncodeTypes`.
* **Regola i colori** impostando `generator.Parameters.Barcode.ForeColor` e `BackColor` per design specifici del brand.

Ognuno di questi argomenti si basa sugli stessi concetti fondamentali trattati qui: inizializzare `BarcodeGenerator`, configurare i parametri visivi e salvare il risultato con `BarCodeImageFormat`.

---

### Conclusione

Questo tutorial ha dimostrato come **creare databar stacked barcode** immagini in C# usando Aspose.BarCode. Hai imparato a impostare la **dimensione X**, modificare il **rapporto d'aspetto del barcode** e esportare il risultato come file **PNG** con `BarcodeGenerator`. Con il passaggio opzionale di decodifica, puoi anche verificare che i dati GS1 codificati siano accurati. Applica questi modelli alle tue applicazioni di inventario, spedizione o punto vendita, ed esplora le numerose opzioni di personalizzazione offerte dalla libreria. Buon coding!

## Cosa dovresti imparare dopo?

I tutorial seguenti coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Regolazione altezza Databar unidimensionale](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Genera immagine barcode – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}