---
category: general
date: 2026-09-13
description: Crea rapidamente un codice a barre databar impilato in C# usando Aspose.Barcode
  – impara a impostare colonne, righe e salvare le immagini.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- Databar Expanded Stacked
- barcode columns
- barcode rows
- Aspose.Barcode for .NET
- C# barcode generator
language: it
lastmod: 2026-09-13
og_description: Crea un codice a barre databar impilato in C# usando Aspose.Barcode.
  Questa guida mostra come configurare colonne, righe ed esportare immagini PNG.
og_image_alt: Screenshot of a generated Databar stacked barcode saved as PNG
og_title: Crea un codice a barre Databar impilato in C# – Guida completa passo passo
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Create databar stacked barcode in C# quickly using Aspose.Barcode –
    learn to set columns, rows, and save images.
  headline: How to create databar stacked barcode in C# with Aspose.Barcode
  type: TechArticle
- description: Create databar stacked barcode in C# quickly using Aspose.Barcode –
    learn to set columns, rows, and save images.
  name: How to create databar stacked barcode in C# with Aspose.Barcode
  steps:
  - name: 'Create a new Console App project:'
    text: 'Create a new Console App project:'
  - name: 'Add the Aspose.Barcode package:'
    text: 'Add the Aspose.Barcode package:'
  - name: 'Open **Program.cs** and add the required `using` statements:'
    text: 'Open **Program.cs** and add the required `using` statements:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- Databar
title: Come creare un codice a barre Databar impilato in C# con Aspose.Barcode
url: /it/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un codice a barre Databar stacked in C# con Aspose.Barcode

Se devi **creare un codice a barre databar stacked** in un'applicazione .NET, questa guida ti fornisce una soluzione completa, pronta all'uso. Vedrai esattamente come configurare il numero di colonne, regolare le righe e salvare il risultato come file PNG—tutto con la libreria Aspose.Barcode per .NET.

Generare un codice a barre **Databar Expanded Stacked** non è un mistero una volta compreso il flusso di lavoro a tre passaggi: istanziare il generatore, impostare le dimensioni desiderate e scrivere l'immagine su disco. Le sezioni seguenti ti accompagnano passo passo, spiegano perché le impostazioni sono importanti e mostrano il risultato finale che puoi verificare immediatamente.

## Prerequisiti

Prima di iniziare, assicurati di avere:

- **Visual Studio 2022** (o qualsiasi IDE C#) con .NET 6+ installato.  
- Pacchetto NuGet **Aspose.Barcode for .NET** (`Install-Package Aspose.Barcode`).  
- Permessi di scrittura su una cartella dove verranno salvati i file PNG.

Non sono richieste dipendenze aggiuntive.

## Passo 1: Configurare il progetto e aggiungere Aspose.Barcode

1. Crea un nuovo progetto Console App:

   ```bash
   dotnet new console -n DatabarStackedDemo
   cd DatabarStackedDemo
   ```

2. Aggiungi il pacchetto Aspose.Barcode:

   ```bash
   dotnet add package Aspose.Barcode
   ```

3. Apri **Program.cs** e aggiungi le dichiarazioni `using` necessarie:

   ```csharp
   using Aspose.BarCode;
   using Aspose.BarCode.Generation;
   using System;
   ```

Questi passaggi garantiscono che le classi **C# barcode generator** siano disponibili nel tuo codice.

## Passo 2: Creare un generatore per un codice a barre Databar stacked

Il primo oggetto di cui hai bisogno è un `BarcodeGenerator` configurato per la simbologia **Databar Expanded Stacked**. Questo oggetto è il punto di ingresso per tutte le operazioni relative ai codici a barre.

```csharp
// Step 2: Initialize a generator for Databar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, // Symbology
    "Databar Expanded Stacked long");   // Human‑readable text (optional)
```

**Perché è importante:**  
`EncodeTypes.DatabarExpandedStacked` indica ad Aspose.Barcode di utilizzare la versione stacked della famiglia DataBar, ideale per spazi con altezza limitata come le ricevute. Il secondo argomento fornisce i dati codificati nel codice a barre; puoi sostituirlo con qualsiasi stringa numerica o alfanumerica conforme allo standard DataBar.

## Passo 3: Configurare le colonne del codice a barre e salvare l'immagine

Un DataBar stacked può essere visualizzato usando un numero configurabile di **colonne**. Il valore predefinito è tre, ma potresti aver bisogno di quattro colonne per stringhe di dati più lunghe. Regola la proprietà `Columns` prima di salvare.

```csharp
// Step 3: Set the barcode to use 4 columns (default rows) and save the image
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Choose an output folder that exists on your machine
string outputPathCols = @"YOUR_DIRECTORY\DatabarCols4.png";
barcodeGenerator.Save(outputPathCols, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 4 columns saved to {outputPathCols}");
```

**Spiegazione:**  
- `Parameters.Barcode.DataBar.Columns` influenza direttamente la segmentazione orizzontale del codice a barre. Più colonne creano un'immagine più larga ma mantengono la stessa altezza.  
- `Save` scrive il codice a barre in un file PNG. Sono supportati anche altri formati (JPEG, BMP, SVG) passando un valore diverso di `BarCodeImageFormat`.

## Passo 4: Creare un altro generatore e configurare le righe del codice a barre

A volte l'ambiente di scansione richiede un codice a barre più alto, cosa che ottieni aumentando il numero di **righe**. Il frammento seguente crea una seconda istanza del generatore, imposta tre righe e salva il risultato.

```csharp
// Step 4: Create a new generator for the same data but with 3 rows
BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the barcode to use 3 rows (default columns)
barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

// Save the image with rows configured
string outputPathRows = @"YOUR_DIRECTORY\DatabarRows3.png";
barcodeGeneratorRows.Save(outputPathRows, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 3 rows saved to {outputPathRows}");
```

**Perché un'istanza separata?**  
Modificare `Rows` sullo stesso `BarcodeGenerator` dopo una chiamata a `Save` funzionerebbe comunque, ma creare una nuova istanza mantiene ogni configurazione isolata e rende il codice più leggibile—soprattutto quando in seguito espanderai il tutorial per coprire altre varianti (ad es., diverse stringhe di dati o livelli di correzione degli errori).

## Passo 5: Verificare i codici a barre generati

Apri i due file PNG appena creati. Dovresti vedere:

- **DatabarCols4.png** – un codice a barre più largo composto da quattro colonne verticali.  
- **DatabarRows3.png** – un codice a barre più alto composto da tre righe orizzontali.

Entrambe le immagini codificano lo stesso testo (`"Databar Expanded Stacked long"`), ma le loro strutture visive differiscono. Scansionali con qualsiasi lettore DataBar standard o con un'app mobile che supporti DataBar per confermare che vengano decodificate correttamente.

## Problemi comuni e consigli professionali

| Problema | Perché accade | Come evitarlo |
|----------|----------------|----------------|
| **Percorso cartella errato** | `Save` genera `DirectoryNotFoundException` se la directory non esiste. | Usa `Directory.CreateDirectory(Path.GetDirectoryName(outputPath))` prima di chiamare `Save`. |
| **Troppo molte colonne/righe** | Le specifiche DataBar limitano le colonne a 4 e le righe a 3. | Rispettare l'intervallo consentito; Aspose.Barcode lancerà `ArgumentOutOfRangeException` altrimenti. |
| **Codice a barre illeggibile** | Una risoluzione immagine bassa può rendere il codice sfocato. | Aumenta DPI tramite `barcodeGenerator.Parameters.ImageResolution` se ti serve maggiore qualità (es., 300 dpi). |
| **Formato dati errato** | DataBar accetta solo stringhe numeriche fino a 13 cifre per alcune modalità. | Convalida la stringa di input prima di passarla al generatore. |

## Estendere l'esempio

Ora che sai **creare un codice a barre databar stacked** con colonne e righe personalizzate, potresti voler esplorare:

- **Modificare i colori di primo piano/sfondo** (`barcodeGenerator.Parameters.Barcode.Color = Color.Blue;`).  
- **Aggiungere una zona silenziosa** (`barcodeGenerator.Parameters.Barcode.Qz = 2;`).  
- **Esportare in SVG** per rendering indipendente dalla risoluzione (`BarCodeImageFormat.Svg`).

Tutte queste opzioni sono documentate nella [riferimento API di Aspose.Barcode per .NET](https://docs.aspose.com/barcode/net/).

## Codice sorgente completo

Di seguito trovi il programma completo, pronto per l'esecuzione, che incorpora tutti i passaggi descritti sopra. Copialo in `Program.cs`, sostituisci `YOUR_DIRECTORY` con un percorso reale e avvia `dotnet run`.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;
using System.IO;

class Program
{
    static void Main()
    {
        // Ensure the output directory exists
        string outputDir = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputDir);

        // -------------------------------------------------
        // Step 1: Generator for 4‑column stacked barcode
        // -------------------------------------------------
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 4 columns (default rows = 2)
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        string colsPath = Path.Combine(outputDir, "DatabarCols4.png");
        barcodeGenerator.Save(colsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved 4‑column barcode to {colsPath}");

        // -------------------------------------------------
        // Step 2: Generator for 3‑row stacked barcode
        // -------------------------------------------------
        BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 3 rows (default columns = 2)
        barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

        string rowsPath = Path.Combine(outputDir, "DatabarRows3.png");
        barcodeGeneratorRows.Save(rowsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved 3‑row barcode to {rowsPath}");
    }
}
```

L'esecuzione del programma produce due file PNG che dimostrano come **le colonne del codice a barre** e **le righe del codice a barre** influenzino il layout visivo di un simbolo **Databar Expanded Stacked**.

## Conclusione

Ora sai come **creare un codice a barre databar stacked** in C# usando Aspose.Barcode per .NET. Regolando le proprietà `Columns` e `Rows` puoi generare codici a barre che si adattano a una vasta gamma di vincoli di spazio mantenendo intatta l'integrità dei dati. L'esempio copre tutto, dall'impostazione del progetto al troubleshooting, fornendoti una solida base per scenari di codici a barre più avanzati.

**Passi successivi:**  
- Sperimenta con diverse stringhe di dati e osserva come i limiti di colonne/righe influenzino la leggibilità.  
- Combina questo codice con un'API web per generare codici a barre su richiesta.  
- Esplora altre simbologie (es., QR, Code128) usando lo stesso modello `BarcodeGenerator`.

Buona programmazione, e che le tue scansioni siano sempre riuscite!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Barcode Generator C# – Create DataBar Expanded Stacked Images](/barcode/english/python-java/general/barcode-generator-c-create-databar-expanded-stacked-images/)
- [databar expanded stacked barcode guide – how to generate and size it in C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Generate Aspose.BarCode Databar barcode using .NET API – Row & Column Configuration](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}