---
category: general
date: 2026-08-19
description: Il tutorial del generatore di codici a barre C# mostra come generare
  codici a barre DataBar Expanded Stacked, personalizzare le dimensioni del codice
  a barre e configurare righe e colonne.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- create databar barcode
- customize barcode size
- configure databar parameters
language: it
lastmod: 2026-08-19
og_description: Il tutorial sul generatore di codici a barre in C# ti insegna come
  generare codici a barre DataBar, personalizzare le dimensioni e configurare righe
  e colonne per un output preciso.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: Generatore di codici a barre C# – guida passo passo per codici DataBar personalizzati
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: C# barcode generator tutorial shows how to generate DataBar Expanded
    Stacked barcodes, customize barcode size, and configure rows and columns.
  headline: 'C# barcode generator: create custom DataBar barcodes'
  type: TechArticle
- description: C# barcode generator tutorial shows how to generate DataBar Expanded
    Stacked barcodes, customize barcode size, and configure rows and columns.
  name: 'C# barcode generator: create custom DataBar barcodes'
  steps:
  - name: Initialise the barcode generator with sample text
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: Set the number of columns (default rows are used)
    text: '```csharp // Configure the DataBar to use four columns. barcodeGenerator.Parameters.Barcode.DataBar.Columns
      = 4; ```'
  - name: Save the barcode image that uses four columns
    text: '```csharp // Save the barcode as a PNG file. barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png",
      BarCodeImageFormat.Png); ```'
  - name: Re‑initialise the generator for a new configuration
    text: '```csharp // Create a new generator instance for the same symbology and
      text. barcodeGenerator = new BarcodeGenerator( EncodeTypes.DatabarExpandedStacked,
      "Databar Expanded Stacked long"); ```'
  - name: Set the number of rows (default columns are used)
    text: '```csharp // Configure the DataBar to use three rows. barcodeGenerator.Parameters.Barcode.DataBar.Rows
      = 3; ```'
  - name: Save the barcode image that uses three rows
    text: '```csharp // Save the barcode with three rows. barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  type: HowTo
tags:
- barcode
- csharp
- databar
title: 'Generatore di codici a barre C#: crea codici DataBar personalizzati'
url: /it/python-java/general/c-barcode-generator-create-custom-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generatore di codici a barre C#: crea codici DataBar personalizzati

Se hai bisogno di un **c# barcode generator** in grado di produrre simboli DataBar Expanded Stacked, questa guida ti mostra esattamente come generare immagini di codici a barre con righe e colonne personalizzate. Imparerai a configurare i parametri databar, regolare le dimensioni del codice a barre e salvare il risultato come file PNG.

Generare codici a barre programmaticamente elimina le fasi di progettazione manuale e garantisce un output coerente su tutte le piattaforme. In questo tutorial tu:

* Installa e riferisci la libreria Aspose.BarCode per .NET (o qualsiasi pacchetto compatibile).
* Crea un generatore di codici a barre per la simbologia DataBar Expanded Stacked.
* **How to generate barcode** immagini con impostazioni specifiche di colonna e riga.
* **Customize barcode size** controllando le righe e le colonne DataBar.
* **Configure databar parameters** come testo, formato e qualità dell'immagine.

## Prerequisiti

* .NET 6.0 SDK o successivo installato.
* Un ambiente di sviluppo C# (Visual Studio, VS Code, Rider, ecc.).
* Pacchetto NuGet `Aspose.BarCode` (o una libreria equivalente che fornisce `BarcodeGenerator`, `EncodeTypes` e `BarCodeImageFormat`).

Add the package with the .NET CLI:

```bash
dotnet add package Aspose.BarCode
```

## Utilizzare il generatore di codici a barre C# per creare codici DataBar

Le sezioni seguenti ti guidano passo passo. L'attenzione principale è sull'API **c# barcode generator**, ma lo stesso schema si applica ad altre librerie di codici a barre che espongono proprietà simili.

### Passo 1: Inizializza il generatore di codici a barre con testo di esempio

```csharp
using Aspose.BarCode.Generation;

// Create a generator for DataBar Expanded Stacked with sample text.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*Perché questo passo?*  
`BarcodeGenerator` è il punto di ingresso per tutte le attività di creazione di codici a barre. Fornire l'enumerazione `EncodeTypes.DatabarExpandedStacked` indica alla libreria quale simbologia utilizzare, mentre l'argomento di testo diventa il valore leggibile dall'uomo codificato nel simbolo.

### Passo 2: Imposta il numero di colonne (vengono usate le righe predefinite)

```csharp
// Configure the DataBar to use four columns.
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

*Perché questo passo?*  
I simboli DataBar Expanded Stacked consistono di elementi lineari impilati. Modificare la proprietà `Columns` cambia la densità orizzontale, consentendo di inserire stringhe di dati più lunghe senza aumentare l'altezza complessiva. Questo personalizza direttamente **customizes barcode size**.

### Passo 3: Salva l'immagine del codice a barre che utilizza quattro colonne

```csharp
// Save the barcode as a PNG file.
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

*Cosa vedi:*  
L'immagine salvata `DatabarCols4.png` mostra un codice DataBar più largo del predefinito perché contiene quattro colonne. Puoi aprire il file in qualsiasi visualizzatore di immagini per verificare l'output.

### Passo 4: Re‑inizializza il generatore per una nuova configurazione

```csharp
// Create a new generator instance for the same symbology and text.
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*Perché re‑inizializzare?*  
Modificare la proprietà `Rows` mantenendo l'impostazione della colonna precedente potrebbe produrre una combinazione inattesa. Iniziare con una nuova istanza garantisce che solo il parametro previsto (`Rows`) influenzi l'immagine successiva.

### Passo 5: Imposta il numero di righe (vengono usate le colonne predefinite)

```csharp
// Configure the DataBar to use three rows.
barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

*Perché questo passo?*  
La proprietà `Rows` controlla l'impilamento verticale. Aumentare le righe rende il codice a barre più alto, il che può essere utile quando lo spazio è limitato orizzontalmente ma abbondante verticalmente. Questo è un altro modo per **customize barcode size**.

### Passo 6: Salva l'immagine del codice a barre che utilizza tre righe

```csharp
// Save the barcode with three rows.
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

*Risultato:*  
`DatabarRows3.png` mostra un codice a barre più alto con tre righe impilate, dimostrando come **configure databar parameters** influisce sull'aspetto visivo.

## Esempio completo eseguibile

Di seguito è riportato un programma completo che puoi copiare, incollare ed eseguire. Include tutti gli import, la gestione degli errori e i commenti per chiarezza.

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder (adjust as needed).
        string outputFolder = @"C:\Barcodes";

        // -----------------------------------------------------------------
        // Create barcode with custom column count.
        // -----------------------------------------------------------------
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 4 columns – this widens the symbol.
        generator.Parameters.Barcode.DataBar.Columns = 4;

        // Save the first image.
        string colsPath = System.IO.Path.Combine(outputFolder, "DatabarCols4.png");
        generator.Save(colsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with 4 columns to: {colsPath}");

        // -----------------------------------------------------------------
        // Create barcode with custom row count.
        // -----------------------------------------------------------------
        generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 3 rows – this makes the symbol taller.
        generator.Parameters.Barcode.DataBar.Rows = 3;

        // Save the second image.
        string rowsPath = System.IO.Path.Combine(outputFolder, "DatabarRows3.png");
        generator.Save(rowsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with 3 rows to: {rowsPath}");
    }
}
```

**Output previsto**

L'esecuzione del programma produce due file PNG:

* `DatabarCols4.png` – un codice DataBar largo con quattro colonne.
* `DatabarRows3.png` – un codice DataBar alto con tre righe.

Apri le immagini per confermare che le dimensioni del codice a barre corrispondano ai parametri configurati.

## Domande comuni e gestione dei casi limite

| Question | Answer |
|----------|--------|
| *E se avessi bisogno sia di righe personalizzate **e** colonne?* | Imposta `Rows` **e** `Columns` sulla stessa istanza di `BarcodeGenerator` prima di chiamare `Save`. La libreria combina entrambi i valori per produrre una griglia della dimensione richiesta. |
| *Posso cambiare il formato dell'immagine?* | Sì. Sostituisci `BarCodeImageFormat.Png` con `Jpeg`, `Bmp` o `Gif` per adattarlo al tuo flusso di lavoro. |
| *Cosa succede quando il testo è più lungo di quanto il simbolo possa contenere?* | Il generatore genera un'`ArgumentException`. Accorcia il testo o aumenta `Columns`/`Rows` per fornire più capacità. |
| *È possibile impostare DPI o risoluzione dell'immagine?* | Usa `generator.Parameters.ImageResolution` per specificare il DPI desiderato prima di salvare. Questo personalizza ulteriormente **customizes barcode size** per la stampa ad alta risoluzione. |
| *La libreria supporta altre varianti DataBar?* | Sì. Sostituisci `EncodeTypes.DatabarExpandedStacked` con `DatabarExpanded`, `DatabarLimited`, ecc., mantenendo la stessa struttura dei parametri. |

## Suggerimenti per una generazione affidabile di codici a barre

* **Pro tip:** Verifica sempre l'immagine generata con uno scanner o un'app mobile prima di distribuirla in produzione.  
* **Watch out for:** Directory di output nulle o vuote—`Save` genererà un'eccezione se il percorso non esiste. Crea la cartella programmaticamente se necessario.  
* **Performance note:** Riutilizzare una singola istanza di `BarcodeGenerator` e modificare solo `Rows` o `Columns` può ridurre l'overhead di creazione degli oggetti quando si generano molti codici a barre in un ciclo.

## Conclusione

Ora sai come utilizzare un **c# barcode generator** per **creare immagini di codici databar**, **customize barcode size**, e **configure databar parameters** come righe e colonne. Regolando queste impostazioni puoi adattare i codici a barre a qualsiasi requisito di layout mantenendo l'affidabilità della scansione.

Successivamente, esplora argomenti correlati come **how to generate barcode** PDF, l'inserimento di codici a barre nei report o il passaggio ad altre simbologie (QR, Code‑128, ecc.). Sperimenta con diversi `Rows`, `Columns` e risoluzioni immagine per trovare la configurazione ottimale per il tuo caso d'uso specifico.

---


## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo passo per aiutarti a padroneggiare ulteriori funzionalità dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come generare e regolare l'altezza del codice a barre per Databar unidimensionale usando Aspose.BarCode per .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generare codici a barre Databar 2D unidimensionali usando l'API Aspose.BarCode per .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)
- [Generare codici a barre Aspose.BarCode Databar usando l'API .NET – Configurazione di righe e colonne](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}