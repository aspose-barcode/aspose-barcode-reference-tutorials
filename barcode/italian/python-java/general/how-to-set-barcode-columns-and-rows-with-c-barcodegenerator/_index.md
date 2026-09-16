---
category: general
date: 2026-09-16
description: Scopri come impostare le colonne del codice a barre in C# usando BarcodeGenerator
  e anche impostare le righe per i codici a barre DataBar Expanded Stacked.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- set barcode columns
- set barcode rows
- DataBar Expanded Stacked
- BarcodeGenerator C#
- barcode image format
- configure barcode dimensions
language: it
lastmod: 2026-09-16
og_description: Imposta rapidamente le colonne del codice a barre in C#. Questa guida
  ti mostra come configurare colonne, righe e formato immagine con BarcodeGenerator.
og_image_alt: DataBar Expanded Stacked barcode showing custom columns and rows
og_title: Imposta colonne e righe del codice a barre in C# – guida completa a BarcodeGenerator
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set barcode columns in C# using BarcodeGenerator and also
    set barcode rows for DataBar Expanded Stacked barcodes.
  headline: How to set barcode columns and rows with C# BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Come impostare colonne e righe del codice a barre con C# BarcodeGenerator
url: /it/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come impostare colonne e righe del codice a barre con C# BarcodeGenerator

Se devi impostare le colonne di un codice a barre in un'applicazione C#, questo tutorial mostra i passaggi esatti necessari. Vedrai come configurare sia le colonne sia le righe per un codice a barre DataBar Expanded Stacked, quindi salvare il risultato come immagine PNG.

Generare i codici a barre programmaticamente ti libera dal lavoro di design manuale e garantisce coerenza tra report, fatture ed etichette prodotto. L'esempio qui sotto copre l'intero flusso di lavoro, dall'installazione della libreria alla produzione di due immagini — una con un numero di colonne personalizzato e un'altra con un numero di righe personalizzato.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6.0 o versioni successive installate.
* Un riferimento al pacchetto NuGet **Aspose.BarCode for .NET**. Installalo con:

```bash
dotnet add package Aspose.BarCode
```

* Accesso in scrittura a una cartella dove verranno salvati i file PNG generati.

Questi requisiti garantiscono che il codice si compili ed esegua senza configurazioni aggiuntive.

## Come impostare le colonne del codice a barre in C#

Il primo passo importante è creare un'istanza di `BarcodeGenerator` per la simbologia **DataBar Expanded Stacked** e assegnare il numero di colonne desiderato.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize a DataBar Expanded Stacked barcode generator with the target text.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the number of columns. The DataBar object exposes a Columns property.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image using the PNG format.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**Perché funziona:**  
`EncodeTypes.DatabarExpandedStacked` indica alla libreria quale simbologia renderizzare. Impostare `Parameters.Barcode.DataBar.Columns` modifica il layout interno dei moduli, influenzando direttamente la larghezza visiva del codice a barre. Il metodo `Save` scrive l'immagine su disco nel formato `BarCodeImageFormat` richiesto.

### Risultato atteso
Apri `C:\Barcodes\DatabarCols4.png` con qualsiasi visualizzatore di immagini. Dovresti vedere un codice a barre DataBar Expanded Stacked più largo del valore predefinito perché utilizza quattro colonne.

## Come impostare le righe del codice a barre in C#

Dopo aver salvato l'immagine basata sulle colonne, potresti voler un codice a barre che vari in altezza regolando le righe. Il processo è analogo alla configurazione delle colonne ma utilizza la proprietà `Rows`.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 4️⃣ Re‑initialize the generator for a fresh configuration.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 5️⃣ Set the number of rows. This property controls the vertical module count.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6️⃣ Save the barcode image with the row configuration.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**Perché funziona:**  
Re‑inizializzare il generatore garantisce che l'impostazione delle colonne precedente non interferisca con la configurazione delle righe. Modificare `Parameters.Barcode.DataBar.Rows` altera l'altezza del codice a barre, producendo un'immagine più alta quando il conteggio delle righe supera il valore predefinito.

### Risultato atteso
Apri `C:\Barcodes\DatabarRows3.png`. Il codice a barre apparirà più alto, riflettendo la configurazione a tre righe.

## Esempio completo end‑to‑end

Di seguito trovi un unico programma che crea entrambe le immagini in un'unica esecuzione. Tenere il codice in un solo file dimostra come passare dalla configurazione delle colonne a quella delle righe senza riavviare l'applicazione.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Common text for both barcodes.
        const string barcodeText = "Databar Expanded Stacked long";

        // ---------- Column configuration ----------
        var colGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        colGenerator.Parameters.Barcode.DataBar.Columns = 4;
        colGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Row configuration ----------
        var rowGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;
        rowGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

L'esecuzione del programma produce due file PNG:

* **DatabarCols4.png** – codice a barre con quattro colonne.  
* **DatabarRows3.png** – codice a barre con tre righe.

Entrambi i file usano il **formato immagine del codice a barre** PNG, che preserva bordi nitidi e supporta la compressione senza perdita — ideale per stampa e visualizzazione digitale.

## Domande frequenti e consigli

| Domanda | Risposta |
|----------|--------|
| *Posso usare JPEG invece di PNG?* | Sì. Sostituisci `BarCodeImageFormat.Png` con `BarCodeImageFormat.Jpeg`. JPEG è più piccolo ma introduce artefatti di compressione, che possono influire sull'affidabilità dello scanner. |
| *Qual è il numero massimo di colonne o righe?* | La libreria valida i valori rispetto alla specifica DataBar. Valori al di fuori dell'intervallo consentito generano un'`ArgumentException`. Consulta la documentazione di Aspose.BarCode per i limiti esatti. |
| *Devo liberare le risorse del `BarcodeGenerator`?* | La classe implementa `IDisposable`. Avvolgi il generatore in un blocco `using` se crei molte istanze in un ciclo per liberare tempestivamente le risorse non gestite. |
| *Come modificare la dimensione del codice a barre senza alterare colonne/righe?* | Usa `barcodeGenerator.Parameters.Image.Width` e `Height` per scalare l'immagine di output mantenendo invariato il layout dei moduli. |

**Consiglio professionale:** Quando generi codici a barre per stampa ad alta risoluzione, aumenta le dimensioni dell'immagine di output (`Width`/`Height`) anziché il numero di colonne o righe. Questo approccio mantiene la dimensione standard del modulo definita dalla simbologia, fornendo un'immagine più nitida.

## Conclusione

Ora sai come impostare colonne e righe di un codice a barre in C# usando la classe **BarcodeGenerator**. La guida ha coperto l'inizializzazione del generatore, la configurazione dei conteggi di colonne e righe, il salvataggio del codice a barre in formato PNG e la gestione di variazioni comuni come il cambio del formato immagine e il rilascio delle risorse.

Successivamente, esplora argomenti correlati come **personalizzare i colori del codice a barre**, **aggiungere testo leggibile dall'uomo** e **incorporare i codici a barre in documenti PDF**. Tutte queste estensioni si basano sullo stesso schema di configurazione mostrato qui, permettendoti di creare soluzioni di codici a barre complete per qualsiasi applicazione .NET.

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [databar expanded stacked barcode guide – how to generate and size it in C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}