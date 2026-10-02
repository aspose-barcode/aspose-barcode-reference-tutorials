---
category: general
date: 2026-08-15
description: Databar ha ampliato la generazione di codici a barre impilati in C#.
  Scopri come generare l'immagine del codice a barre, impostare colonne e righe per
  i layout DataBar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- generate barcode image
- how to generate barcode
- how to set columns
- how to set rows
language: it
lastmod: 2026-08-15
og_description: Databar ha ampliato la generazione di codici a barre impilati in C#.
  Segui questa guida passo passo per generare immagini di codici a barre, impostare
  le colonne e le righe in modo efficiente.
og_image_alt: Screenshot of a databar expanded stacked barcode generated with C#
og_title: Databar espanso impilato – genera immagine del codice a barre in C#
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Databar expanded stacked barcode generation in C#. Learn how to generate
    barcode image, set columns and rows for DataBar layouts.
  headline: 'Databar expanded stacked: generate barcode image in C#'
  type: TechArticle
- description: Databar expanded stacked barcode generation in C#. Learn how to generate
    barcode image, set columns and rows for DataBar layouts.
  name: 'Databar expanded stacked: generate barcode image in C#'
  steps:
  - name: 1. Install the Aspose.BarCode library
    text: 'The code uses the **Aspose.BarCode for .NET** library, which provides the
      `BarcodeGenerator` class. Install the NuGet package with the following command:'
  - name: 2. Create a barcode generator for **databar expanded stacked**
    text: The generator is the entry point for all barcode operations. You must specify
      the symbology (`EncodeTypes.DatabarExpandedStacked`) and the text to encode.
  - name: 3. How to set columns for DataBar
    text: The `Columns` property controls how many vertical modules appear in the
      stacked barcode. Valid values are 2, 3, or 4. Setting columns influences the
      barcode’s width and the amount of data it can store.
  - name: 4. Save the 4‑column barcode image
    text: Saving the image produces a file that you can embed in reports, invoices,
      or mobile apps. The `Save` method accepts a file path and an image format.
  - name: 5. How to set rows for DataBar
    text: Rows add a second dimension to the stacked layout, allowing more data to
      be encoded without widening the barcode. The `Rows` property defaults to 1;
      you can increase it up to 3 for the expanded stacked variant.
  - name: 6. Save the 3‑row barcode image
    text: '```csharp // Step 5: Save the 3‑row barcode image barcode.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  - name: 7. Complete C# example to generate barcode image
    text: 'Putting all steps together yields a self‑contained program you can copy
      into a console application:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: 'Databar expanded stacked: genera immagine del codice a barre in C#'
url: /it/python-java/general/databar-expanded-stacked-generate-barcode-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Databar expanded stacked: genera immagine barcode in C#

Se hai bisogno di generare un'immagine barcode **databar expanded stacked** in C#, questa guida ti mostra esattamente **come generare barcode** con layout personalizzati di colonne e righe. Vedrai come impostare le colonne, come impostare le righe e come salvare le immagini risultanti senza uscire dall'IDE.

Il tutorial copre:

* Creazione di un generatore di barcode per la simbologia **databar expanded stacked**.  
* Configurazione di un layout a 4 colonne e a 3 righe.  
* Salvataggio di ogni configurazione come file PNG.  
* Suggerimenti per gestire casi limite come conteggi di colonne non validi.

Nessuna documentazione esterna è necessaria; l'esempio completo e funzionante è incluso.

![Databar expanded stacked barcode example](YOUR_DIRECTORY/DatabarCols4.png){: .center alt="databar expanded stacked barcode generato con C#" }

## Passaggi per la generazione del barcode Databar expanded stacked

### 1. Installa la libreria Aspose.BarCode

Il codice utilizza la libreria **Aspose.BarCode for .NET**, che fornisce la classe `BarcodeGenerator`. Installa il pacchetto NuGet con il comando seguente:

```bash
dotnet add package Aspose.BarCode
```

Dopo l'installazione del pacchetto, aggiungi lo spazio dei nomi richiesto all'inizio del tuo file:

```csharp
using Aspose.BarCode.Generation;
```

### 2. Crea un generatore di barcode per **databar expanded stacked**

Il generatore è il punto di ingresso per tutte le operazioni sul barcode. Devi specificare la simbologia (`EncodeTypes.DatabarExpandedStacked`) e il testo da codificare.

```csharp
// Step 1: Create a barcode generator for Databar Expanded Stacked
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*Perché è importante:* L'enumerazione `EncodeTypes` indica alla libreria quale formato di barcode produrre. L'uso di **databar expanded stacked** garantisce che l'immagine risultante segua la specifica GS1 DataBar per layout impilati.

### 3. Come impostare le colonne per DataBar

La proprietà `Columns` controlla quante unità verticali compaiono nel barcode impilato. I valori validi sono 2, 3 o 4. Impostare le colonne influisce sulla larghezza del barcode e sulla quantità di dati che può contenere.

```csharp
// Step 2: Configure a 4‑column layout
barcode.Parameters.Barcode.DataBar.Columns = 4;
```

**Suggerimento:** Se tenti di assegnare un valore al di fuori dell'intervallo consentito, la libreria genera un'`ArgumentException`. Convalida sempre l'input quando esponi la selezione delle colonne agli utenti.

### 4. Salva l'immagine del barcode a 4 colonne

Il salvataggio dell'immagine produce un file che puoi incorporare in report, fatture o app mobili. Il metodo `Save` accetta un percorso file e un formato immagine.

```csharp
// Step 3: Save the 4‑column barcode image
barcode.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

Quando il file è scritto, puoi aprirlo con qualsiasi visualizzatore di immagini per confermare che il modello **databar expanded stacked** sia visualizzato correttamente.

### 5. Come impostare le righe per DataBar

Le righe aggiungono una seconda dimensione al layout impilato, consentendo di codificare più dati senza allargare il barcode. La proprietà `Rows` ha valore predefinito 1; puoi aumentarla fino a 3 per la variante expanded stacked.

```csharp
// Step 4: Switch to a 3‑row layout (columns remain unchanged)
barcode.Parameters.Barcode.DataBar.Rows = 3;
```

**Perché le righe sono importanti:** L'aumento delle righe riduce la larghezza complessiva mantenendo la capacità di dati, utile per etichette strette o spazi su schermi mobili.

### 6. Salva l'immagine del barcode a 3 righe

```csharp
// Step 5: Save the 3‑row barcode image
barcode.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

Ora disponi di due file PNG—uno con layout a 4 colonne e l'altro con layout a 3 righe—entrambi usando la simbologia **databar expanded stacked**.

### 7. Esempio completo in C# per generare l'immagine barcode

Unendo tutti i passaggi ottieni un programma autonomo che puoi copiare in un'applicazione console:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace DatabarExpandedStackedDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for Databar Expanded Stacked
            BarcodeGenerator barcode = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Configure a 4‑column layout and save
            barcode.Parameters.Barcode.DataBar.Columns = 4;
            barcode.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("4‑column barcode saved.");

            // Change to a 3‑row layout (columns stay at 4) and save
            barcode.Parameters.Barcode.DataBar.Rows = 3;
            barcode.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("3‑row barcode saved.");
        }
    }
}
```

**Output previsto**

L'esecuzione del programma stampa:

```
4‑column barcode saved.
3‑row barcode saved.
```

e crea due file PNG in `YOUR_DIRECTORY`. Apri i file per verificare che ciascuna immagine mostri un barcode **databar expanded stacked** valido.

## Problemi comuni e consigli pratici

* **Esistenza della directory** – `Save` non crea cartelle mancanti. Assicurati che `YOUR_DIRECTORY` esista o utilizza `Directory.CreateDirectory` prima di salvare.
* **Limiti delle colonne** – Valori diversi da 2, 3 o 4 generano un'eccezione. Proteggi l'input dell'utente con un semplice controllo di intervallo:

  ```csharp
  int columns = 4;
  if (columns < 2 || columns > 4) throw new ArgumentOutOfRangeException(nameof(columns));
  barcode.Parameters.Barcode.DataBar.Columns = columns;
  ```

* **Limiti delle righe** – La variante expanded stacked supporta fino a 3 righe. Impostare `Rows` a 0 o a un valore superiore a 3 solleva anch'essa un'eccezione.
* **Formato immagine** – `BarCodeImageFormat.Png` offre qualità lossless, ideale per la stampa. Usa `Jpeg` solo quando la dimensione del file è una priorità.

## Prossimi passi

Ora che sai **come generare barcode** con configurazioni personalizzate di colonne e righe, puoi:

* Integrare il generatore in una web API per servire immagini barcode su richiesta.  
* Combinare il barcode con librerie di generazione PDF per includerlo nelle fatture.  
* Sperimentare con altre varianti DataBar (`DatabarExpanded`, `DatabarLimited`) usando lo stesso oggetto `Parameters.Barcode.DataBar`.

Per una personalizzazione più approfondita—come cambiare il colore delle barre, aggiungere testo leggibile dall'uomo o applicare sovrapposizioni QR‑code—consulta la documentazione di Aspose.BarCode sulle proprietà di `BarcodeGenerator`.

---

Seguendo questa guida hai padroneggiato il flusso di lavoro **databar expanded stacked**, imparato **come impostare le colonne**, **come impostare le righe**, e prodotto due immagini barcode distinte pronte per l'uso in produzione. Buon coding!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi con spiegazioni passo‑passo per aiutarti a padroneggiare ulteriori funzionalità dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}