---
category: general
date: 2026-09-26
description: La guida del generatore di codici a barre C# mostra come impostare le
  righe e le colonne quando si creano codici a barre Databar Expanded Stacked in C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- how to set rows
- how to set columns
- Databar Expanded Stacked barcode
- C# barcode library
language: it
lastmod: 2026-09-26
og_description: Il tutorial su C# per il generatore di codici a barre spiega come
  impostare righe e colonne per i codici a barre Databar Expanded Stacked, con codice
  completo e consigli.
og_image_alt: Barcode generator C# example showing rows and columns settings
og_title: Generatore di codici a barre C# – imposta righe e colonne passo dopo passo
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: barcode generator C# guide shows how to set rows and how to set columns
    when creating Databar Expanded Stacked barcodes in C#.
  headline: How to use barcode generator C# for rows and columns
  type: TechArticle
- description: barcode generator C# guide shows how to set rows and how to set columns
    when creating Databar Expanded Stacked barcodes in C#.
  name: How to use barcode generator C# for rows and columns
  steps:
  - name: Create a generator for a Databar Expanded Stacked barcode
    text: '```csharp // Create a generator for a Databar Expanded Stacked barcode
      with sample text BarcodeGenerator barcodeGenerator = new BarcodeGenerator( EncodeTypes.DatabarExpandedStacked,
      "Databar Expanded Stacked long"); ```'
  - name: How to set columns – configure the barcode to use 4 columns
    text: '```csharp // How to set columns: set the Columns property to 4 barcodeGenerator.Parameters.Barcode.DataBar.Columns
      = 4; ```'
  - name: Save the barcode image with the column setting
    text: '```csharp // Save the PNG image that reflects the column configuration
      barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
      ```'
  - name: Re‑initialize the generator for a different layout
    text: When you need a separate barcode with a different visual arrangement, create
      a new instance rather than re‑using the previous one. This guarantees that previous
      settings (like columns) do not bleed into the new configuration.
  - name: How to set rows – configure the barcode to use 3 rows
    text: '```csharp // How to set rows: assign the Rows property to 3 barcodeGenerator.Parameters.Barcode.DataBar.Rows
      = 3; ```'
  - name: Save the barcode image that includes the row setting
    text: '```csharp // Save the PNG image that reflects the row configuration barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  - name: Expected output
    text: 'Running the program produces two PNG files:'
  - name: Pro tip
    text: 'If you need to generate many barcodes with varying rows and columns, wrap
      the configuration logic in a helper method:'
  type: HowTo
tags:
- barcode
- C#
- code example
title: Come utilizzare il generatore di codici a barre C# per righe e colonne
url: /it/python-java/general/how-to-use-barcode-generator-c-for-rows-and-columns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come utilizzare il generatore di codici a barre C# per righe e colonne

Se hai bisogno di un **barcode generator C#** che ti consenta di controllare il layout visivo di un codice a barre Databar Expanded Stacked, questo tutorial ti fornisce una soluzione completa e eseguibile. Imparerai **come impostare le righe** e **come impostare le colonne** in modo che l'immagine generata corrisponda esattamente al design richiesto.

Generare codici a barre programmaticamente spesso sembra indovinare quale proprietà faccia cosa. Alla fine di questa guida comprenderai l'API, eviterai gli errori comuni e avrai un esempio di codice pronto‑all'uso che potrai copiare nel tuo progetto.

## Prerequisiti

* .NET 6.0 o versioni successive installate (il codice funziona anche con .NET Core e .NET Framework)
* Un riferimento alla libreria di generazione di codici a barre che fornisce `BarcodeGenerator` e `EncodeTypes` (ad esempio, Aspose.BarCode, Dynamsoft o qualsiasi SDK compatibile)
* Un IDE come Visual Studio o VS Code
* Permessi di scrittura su una cartella dove verranno salvati i file PNG

Non sono richiesti pacchetti NuGet aggiuntivi oltre al SDK del codice a barre stesso.

## Barcode generator C# – impostare righe e colonne

Le sezioni seguenti illustrano ogni passaggio di configurazione. Gli snippet di codice sono completi e possono essere incollati direttamente nel metodo `Main` di un'applicazione console.

### Passo 1: Creare un generatore per un codice a barre Databar Expanded Stacked

```csharp
// Create a generator for a Databar Expanded Stacked barcode with sample text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
```

*Perché è importante:* L'istanziazione di `BarcodeGenerator` è la prima azione che esegui in qualsiasi flusso di lavoro **barcode generator C#**. Il costruttore riceve il tipo di codifica e la stringa di dati da codificare.

### Passo 2: Come impostare le colonne – configurare il codice a barre per utilizzare 4 colonne

```csharp
// How to set columns: set the Columns property to 4
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

Impostare la proprietà `Columns` cambia il numero di moduli verticali che il DataBar utilizza. Un valore di `4` crea un codice a barre più denso e compatto, utile quando lo spazio orizzontale è limitato.

### Passo 3: Salvare l'immagine del codice a barre con l'impostazione delle colonne

```csharp
// Save the PNG image that reflects the column configuration
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

Il metodo `Save` scrive l'immagine generata su disco. Verifica il file di output per confermare che il layout a quattro colonne appaia come previsto.

![Barcode generator C# example showing rows and columns settings](./images/barcode-rows-columns.png)

*L'immagine sopra illustra il risultato della configurazione delle colonne.*

### Passo 4: Re‑inizializzare il generatore per un layout diverso

Quando hai bisogno di un codice a barre separato con una disposizione visiva diversa, crea una nuova istanza invece di riutilizzare quella precedente. Questo garantisce che le impostazioni precedenti (come le colonne) non si trasferiscano nella nuova configurazione.

```csharp
// Re‑initialize to start a fresh configuration
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
```

### Passo 5: Come impostare le righe – configurare il codice a barre per utilizzare 3 righe

```csharp
// How to set rows: assign the Rows property to 3
barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

La proprietà `Rows` controlla l'impilamento verticale dei moduli DataBar. Un layout a tre righe è il valore predefinito per molti dispositivi di scansione, ma è possibile aumentarlo per una maggiore densità di dati.

### Passo 6: Salvare l'immagine del codice a barre che include l'impostazione delle righe

```csharp
// Save the PNG image that reflects the row configuration
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

Apri `DatabarRows3.png` per vedere la disposizione a tre righe. Se il codice a barre non viene letto, ricontrolla i valori di righe/colonne rispetto alle specifiche del tuo scanner.

## Codice sorgente completo – pronto da copiare

Di seguito trovi il programma completo che combina tutti i passaggi precedenti. Sostituisci `YOUR_DIRECTORY` con un percorso assoluto o relativo che esiste sulla tua macchina.

```csharp
using System;
using YourBarcodeSdkNamespace;   // Replace with the actual namespace of your SDK

class Program
{
    static void Main()
    {
        // ---------- Columns configuration ----------
        // 1. Create generator
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // 2. Set columns (how to set columns)
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3. Save image with column setting
        barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Rows configuration ----------
        // 4. Re‑initialize generator for a fresh instance
        barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // 5. Set rows (how to set rows)
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6. Save image with row setting
        barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

### Output previsto

L'esecuzione del programma produce due file PNG:

| Nome file            | Descrizione layout                         |
|----------------------|--------------------------------------------|
| `DatabarCols4.png`   | Databar Expanded Stacked con **4 colonne** |
| `DatabarRows3.png`   | Databar Expanded Stacked con **3 righe**    |

Entrambe le immagini dovrebbero essere leggibili da lettori di codici a barre standard che supportano la simbologia Databar Expanded Stacked.

## Errori comuni e consigli professionali

| Problema                              | Perché succede                               | Correzione / Consiglio |
|--------------------------------------|----------------------------------------------|------------------------|
| Utilizzare la stessa istanza di `BarcodeGenerator` per righe e colonne | L'SDK mantiene la configurazione precedente, quindi impostare le righe dopo le colonne può produrre una combinazione inaspettata | Re‑inizializzare il generatore (come mostrato nel Passo 4) prima di modificare l'altra dimensione |
| Dimenticare di impostare correttamente `EncodeTypes` | L'SDK utilizza per impostazione predefinita una simbologia diversa, generando un codice a barre non valido | Passare sempre `EncodeTypes.DatabarExpandedStacked` quando è necessario questo formato specifico |
| Salvare in una cartella inesistente      | `Save` genera un'eccezione se il percorso non è valido | Assicurarsi che `YOUR_DIRECTORY` esista o utilizzare `Directory.CreateDirectory` prima di chiamare `Save` |
| Utilizzare valori al di fuori dell'intervallo consentito (es. 0 colonne) | L'SDK valida l'intervallo e genera `ArgumentOutOfRangeException` | I valori validi per le colonne sono 1‑4; i valori validi per le righe sono 1‑3 per questa simbologia |

### Consiglio professionale

Se devi generare molti codici a barre con righe e colonne variabili, racchiudi la logica di configurazione in un metodo di supporto:

```csharp
static void GenerateDatabar(string text, int? rows, int? columns, string outputPath)
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, text);
    if (rows.HasValue)    generator.Parameters.Barcode.DataBar.Rows = rows.Value;
    if (columns.HasValue) generator.Parameters.Barcode.DataBar.Columns = columns.Value;
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Questo approccio riduce la duplicazione e rende il codice più facile da mantenere.

## Conclusione

Ora hai un esempio chiaro, completo, di utilizzo di un **barcode generator C#** per controllare sia il numero di righe sia il numero di colonne in un codice a barre Databar Expanded Stacked. Seguendo i passaggi sopra, potrai generare immagini di codici a barre precise che soddisfano i requisiti di layout esatti del tuo hardware di scansione.

Da qui potresti esplorare:

* Modificare altre proprietà `DataBar` come **AspectRatio** o **BarHeight**
* Generare altre simbologie (ad es., QR, Code128) con la stessa classe `BarcodeGenerator`
* Incorporare il PNG generato in PDF o stampare direttamente da C#

Sentiti libero di sperimentare diverse combinazioni di righe/colonne e condividi i tuoi risultati nei commenti. Buon coding!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come impostare le colonne per un codice a barre Databar Expanded Stacked – guida completa C#](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [Guida al codice a barre Databar Expanded Stacked – come generarlo e dimensionarlo in C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Esempio di Barcode Generator in C# – Imposta colonne, righe e esporta immagine](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}