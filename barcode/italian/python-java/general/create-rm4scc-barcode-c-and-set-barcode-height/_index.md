---
category: general
date: 2026-08-25
description: Crea un codice a barre RM4SCC in C# con codice passo passo e scopri come
  impostare l'altezza del codice a barre per una dimensione precisa.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create rm4scc barcode c#
- how to set barcode height
language: it
lastmod: 2026-08-25
og_description: Crea un codice a barre RM4SCC in C# con Aspose.BarCode e scopri come
  impostare l'altezza del codice a barre per un controllo preciso nelle tue applicazioni
  .NET.
og_image_alt: Screenshot of an RM4SCC barcode generated with C#
og_title: Crea codice a barre RM4SCC in C# – guida per impostare l’altezza del codice
  a barre
schemas:
- author: Aspose
  dateModified: '2026-08-25'
  description: Create RM4SCC barcode C# with step‑by‑step code and learn how to set
    barcode height for precise sizing.
  headline: Create RM4SCC barcode C# and set barcode height
  type: TechArticle
tags:
- barcode
- C#
- RM4SCC
- Aspose.BarCode
title: Crea codice a barre RM4SCC in C# e imposta l’altezza del codice a barre
url: /it/python-java/general/create-rm4scc-barcode-c-and-set-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea codice a barre RM4SCC C# e imposta l'altezza del codice a barre

Crea rapidamente un codice a barre RM4SCC C# utilizzando la libreria Aspose.BarCode. Questo tutorial mostra **come impostare l'altezza del codice a barre** e personalizzare altre proprietà visive affinché il codice a barre si adatti esattamente al tuo layout.

Vedrai un programma console completo, pronto‑all'uso, che genera tre file PNG:

* un codice a barre Planet con altezza predefinita (per confronto)  
* un codice a barre RM4SCC con altezza manuale di 100 px  
* un codice a barre Planet con barre vuote (non riempite)  

L'esempio presuppone che tu abbia Visual Studio 2022 (o qualsiasi IDE .NET 6+) e una licenza valida di Aspose.BarCode per .NET o una copia di valutazione.

## Prerequisiti

| Requisito | Motivo |
|-------------|--------|
| .NET 6 SDK (or later) | Fornisce l'ambiente di esecuzione per l'app console |
| Aspose.BarCode for .NET NuGet package | Fornisce `BarcodeGenerator`, `EncodeTypes` e le API di esportazione immagine |
| Basic C# knowledge | Necessario per comprendere il flusso del codice |

Installa il pacchetto NuGet con:

```bash
dotnet add package Aspose.BarCode
```

> **Suggerimento:** Se esegui il codice senza licenza, le immagini generate conterranno una piccola filigrana Aspose.

## Passo 1: Configura la struttura del progetto

Crea un nuovo progetto console e aggiungi le direttive `using` necessarie:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat; // optional, you can use the enum directly
```

Le istruzioni `using` ti danno accesso alle classi del generatore di codici a barre e all'enumerazione del formato PNG.

## Passo 2: Definisci la cartella di output

Scegli una cartella dove verranno salvati i file PNG. La cartella deve esistere prima di chiamare `Save`.

```csharp
// Step 1: Define the output folder
string outputFolder = "GeneratedBarcodes/";

// Ensure the directory exists
System.IO.Directory.CreateDirectory(outputFolder);
```

Creare la directory programmaticamente evita una *FileNotFoundException* quando il codice viene eseguito su una macchina nuova.

## Passo 3: Genera un codice a barre Planet con l'altezza predefinita (baseline)

Il codice a barre Planet non è l'oggetto principale di questa guida, ma fornisce una baseline visiva per confrontarlo con il codice a barre RM4SCC di dimensioni manuali.

```csharp
// Step 2: Generate a Planet barcode with the default (auto) height
BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // controls bar width
planetAuto.Save($"{outputFolder}PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

*Perché è importante:* `XDimension` determina la larghezza di una singola barra. Mantenerla costante mentre si modifica `BarHeight` isola l'effetto dell'altezza.

## Passo 4: **Crea codice a barre RM4SCC C#** – imposta un'altezza manuale

Ora affrontiamo il compito principale: **creare codice a barre RM4SCC C#** e controllare esplicitamente la sua altezza.

```csharp
// Step 3: Generate an RM4SCC barcode with a manual height of 100 px
BarcodeGenerator rm4sccManual = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccManual.Parameters.Barcode.XDimension.Pixels = 4;           // same bar width as Planet example
rm4sccManual.Parameters.Barcode.BarHeight.Pixels = 100;          // <-- how to set barcode height
rm4sccManual.Save($"{outputFolder}PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

### Come impostare l'altezza del codice a barre

La proprietà `BarHeight` si trova sotto `Parameters.Barcode`. Accetta un valore `float` espresso in **pixel**, **punti** o **millimetri** a seconda dell'`Unit` che scegli (`Pixels`, `Points`, `Millimeters`). Nell'esempio utilizziamo `Pixels` perché il formato di output è PNG.

Se hai bisogno di un'altezza in millimetri, cambia prima l'unità:

```csharp
rm4sccManual.Parameters.Barcode.BarHeight.Unit = BarHeightUnit.Millimeters;
rm4sccManual.Parameters.Barcode.BarHeight.Value = 25; // 25 mm tall
```

## Passo 5: Genera un codice a barre Planet con barre vuote (non riempite)

Questo passo dimostra un'altra proprietà utile—`FilledBars`. Impostandola su `false` si crea un codice a barre “vuoto”, utile per scopi di design.

```csharp
// Step 4: Generate a Planet barcode with empty (unfilled) bars
BarcodeGenerator planetEmptyBars = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetEmptyBars.Parameters.Barcode.XDimension.Pixels = 4;
planetEmptyBars.Parameters.Barcode.FilledBars = false; // makes bars transparent
planetEmptyBars.Save($"{outputFolder}PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

## Programma completo, eseguibile

Copia il codice seguente in `Program.cs`. Compila ed esegui il progetto; tre file PNG appariranno nella cartella `GeneratedBarcodes`.



## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come creare un codice a barre code128 Java e impostare l'altezza delle barre](/barcode/english/java/barcode-configuration/setting-bars-height/)
- [Come creare una zona silenziosa per il codice a barre .NET per Code 16K usando Aspose.BarCode](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Come creare un codice a barre Aztec con Aspose.BarCode per .NET](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}