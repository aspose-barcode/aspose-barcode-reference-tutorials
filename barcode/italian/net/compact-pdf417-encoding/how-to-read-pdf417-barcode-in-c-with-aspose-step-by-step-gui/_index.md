---
category: general
date: 2026-10-24
description: Scopri come leggere i codici a barre PDF417 in C# usando Aspose.BarCode.
  Questo tutorial copre la lettura di un'immagine di codice a barre, l'estrazione
  dei campi Macro PDF417 e la gestione di scenari comuni.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode image c#
- read barcode with aspose
language: it
lastmod: 2026-10-24
og_description: Come leggere il codice a barre PDF417 in C# usando Aspose.BarCode.
  Segui questo tutorial completo per decodificare le immagini, recuperare i metadati
  Macro PDF417 e evitare le insidie più comuni.
og_image_alt: Screenshot showing how to read PDF417 barcode results in a C# console
  application
og_title: Come leggere il codice a barre PDF417 in C# con Aspose – guida completa
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  headline: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  name: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  steps:
  - name: Why use `DecodeType.MacroPdf417`?
    text: '* **Macro PDF417** stores additional fields (file ID, segment count, timestamps,
      etc.) that are not present in standard PDF417. * The `Extended` property of
      `BarCodeResult` is populated only when you request the macro type, saving you
      a separate parsing step.'
  - name: What each property means
    text: '| Property | Description | |----------|-------------| | **MacroPdf417FileID**
      | Unique identifier for the whole multi‑segment document. | | **MacroPdf417SegmentID**
      | Index of the current segment (starting at 0). | | **MacroPdf417SegmentsCount**
      | Total number of segments that belong to the file. | '
  - name: Missing macro fields
    text: 'Sometimes a PDF417 barcode is generated without the optional macro fields.
      Accessing a missing property returns `null` or `0`. Guard against this if you
      plan to store the values:'
  - name: Corrupted or low‑quality images
    text: 'If the image is blurry, you can improve detection by enabling the `BarCodeReader`
      quality options:'
  - name: Multiple barcode formats in one image
    text: 'If you suspect other barcode types might be present, use `DecodeType.AllSupported`
      and filter results:'
  type: HowTo
- questions:
  - answer: Yes. Change `DecodeType.MacroPdf417` to `DecodeType.Pdf417`. The `Extended`
      property will be empty, but `CodeText` and `CodeTypeName` remain available.
    question: Can I read a standard PDF417 (non‑macro) with the same code?
  - answer: Absolutely. Use the overload `new BarCodeReader(Stream, DecodeType)` and
      pass a `FileStream` or `MemoryStream`. This is useful when the image comes from
      a web API.
    question: Does Aspose.BarCode support reading from a stream instead of a file
      path?
  - answer: 'The `MacroPdf417Checksum` field contains the raw CRC‑16 value. You can
      recompute the checksum on the reconstructed file and compare it to ensure data
      integrity. ## Next steps and related topics * **Write PDF417 barcodes** – explore
      `BarCodeGenerator` to create macro barcodes for testing. * **Combine'
    question: How do I validate the checksum?
  type: FAQPage
tags:
- barcode
- Aspose.BarCode
- C#
title: Come leggere il codice a barre PDF417 in C# con Aspose – guida passo passo
url: /it/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-with-aspose-step-by-step-gui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come leggere il codice a barre PDF417 in C# con Aspose – guida passo‑passo

Se hai bisogno di **come leggere PDF417 barcode** in un'applicazione .NET, questa guida ti mostra esattamente come leggere il codice a barre PDF417 in C# usando la libreria Aspose.BarCode. Che tu stia elaborando documenti scansionati, acquisizioni da dispositivi mobili o immagini importate in batch, il codice qui sotto decodifica il codice a barre ed estrae ogni proprietà Macro PDF417 di cui potresti aver bisogno.

Leggere un'immagine di codice a barre in C# può sembrare arduo, soprattutto quando il codice contiene metadati estesi. Questo tutorial elimina le ipotesi fornendo un esempio completo e eseguibile, spiegando ogni riga e coprendo casi limite come segmenti macro mancanti o immagini corrotte. Alla fine, sarai in grado di integrare la decodifica PDF417 in qualsiasi progetto C# con sicurezza.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6.0 SDK o versioni successive installate  
* Visual Studio 2022 (o qualsiasi IDE che supporti .NET)  
* Una licenza o una valutazione gratuita di **Aspose.BarCode for .NET** – puoi ottenere una chiave temporanea dal sito web di Aspose  
* Un file immagine che contenga un codice a barre Macro PDF417 (ad es., `ExtPDF417Meta.png`)

> **Suggerimento:** Se vuoi solo sperimentare, Aspose offre una prova di 30 giorni che include tutte le funzionalità per la lettura dei codici a barre.

## Passo 1: Installa il pacchetto NuGet Aspose.BarCode

Apri la cartella del tuo progetto in un terminale ed esegui:

```bash
dotnet add package Aspose.BarCode
```

Il pacchetto aggiunge lo spazio dei nomi `Aspose.BarCode.ReadRecognition`, che contiene la classe `BarCodeReader` usata per decodificare le immagini.

## Passo 2: Crea un BarCodeReader per un'immagine PDF417

Il costruttore `BarCodeReader` accetta due argomenti: il percorso del file immagine e il `DecodeType` che desideri targettizzare. Specificare `DecodeType.MacroPdf417` indica ad Aspose di cercare simboli Macro PDF417 e di popolare automaticamente le proprietà estese.

```csharp
using Aspose.BarCode.ReadRecognition;

// Replace with the actual path to your barcode image
string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image
```

### Perché usare `DecodeType.MacroPdf417`?

* **Macro PDF417** memorizza campi aggiuntivi (ID file, conteggio segmenti, timestamp, ecc.) che non sono presenti nel PDF417 standard.  
* La proprietà `Extended` di `BarCodeResult` viene popolata solo quando richiedi il tipo macro, risparmiandoti un passaggio di parsing separato.

## Passo 3: Itera su tutti i codici a barre rilevati

Un'unica immagine può contenere più simboli PDF417 (ad esempio, quando un documento è suddiviso su più pagine). Il metodo `ReadBarCodes()` restituisce un `IEnumerable<BarCodeResult>` che puoi scorrere.

```csharp
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // Basic information
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

Se l'immagine non contiene alcun codice a barre, il ciclo non viene mai eseguito e il programma termina in modo pulito. Questo comportamento rende il codice sicuro per l'elaborazione in batch dove alcuni file potrebbero non contenere codici a barre.

## Passo 4: Visualizza le proprietà estese Macro PDF417

La proprietà `Extended.Pdf417` raggruppa tutti i campi specifici della macro. Ogni campo mappa direttamente alla specifica PDF417, così puoi archiviarli in un database, registrarli o usarli per ulteriori validazioni.

```csharp
        // Macro PDF417 extended properties
        Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
    }
}
```

### Cosa significa ciascuna proprietà

| Proprietà | Descrizione |
|----------|-------------|
| **MacroPdf417FileID** | Identificatore univoco per l'intero documento multi‑segmento. |
| **MacroPdf417SegmentID** | Indice del segmento corrente (a partire da 0). |
| **MacroPdf417SegmentsCount** | Numero totale di segmenti che appartengono al file. |
| **MacroPdf417FileName** | Nome file opzionale incorporato nel codice a barre. |
| **MacroPdf417Checksum** | Checksum CRC‑16 per il blocco dati macro. |
| **MacroPdf417FileSize** | Dimensione originale del file in byte. |
| **MacroPdf417TimeStamp** | Timestamp di generazione del codice a barre macro. |
| **MacroPdf417Addressee** | Destinatario previsto del documento. |
| **MacroPdf417Sender** | Mittente del documento. |
| **MacroPdf417Terminator** | Flag terminatore che indica la fine della sequenza macro. |

Questi campi sono particolarmente utili quando ricostruisci un PDF o un'immagine di grandi dimensioni che è stato suddiviso in diversi simboli PDF417 per la stampa su supporti a bassa risoluzione.

## Passo 5: Gestisci casi limite comuni

### Campi macro mancanti

A volte un codice a barre PDF417 viene generato senza i campi macro opzionali. L'accesso a una proprietà mancante restituisce `null` o `0`. Proteggi il tuo codice se prevedi di memorizzare i valori:

```csharp
string fileName = result.Extended.Pdf417.MacroPdf417FileName ?? "Unnamed";
long fileSize = result.Extended.Pdf417.MacroPdf417FileSize;
```

### Immagini corrotte o di bassa qualità

Se l'immagine è sfocata, puoi migliorare il rilevamento abilitando le opzioni di qualità del `BarCodeReader`:

```csharp
reader.BarcodeSettings.ImageQuality = 90; // value between 0‑100
reader.BarcodeSettings.PureBarcode = false; // allow detection in noisy backgrounds
```

Queste impostazioni sono opzionali ma possono aumentare notevolmente il tasso di successo per documenti scansionati.

### Formati di codice a barre multipli in una sola immagine

Se sospetti la presenza di altri tipi di codice a barre, usa `DecodeType.AllSupported` e filtra i risultati:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        if (result.CodeType == DecodeType.MacroPdf417)
        {
            // Process macro PDF417 as shown above
        }
    }
}
```

## Esempio completo eseguibile

Copia il programma seguente in un nuovo progetto console (`dotnet new console`) ed eseguilo. Sostituisci la variabile `imagePath` con il percorso della tua immagine Macro PDF417.

```csharp
using System;
using Aspose.BarCode.ReadRecognition;

class Program
{
    static void Main()
    {
        // Path to the barcode image
        string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Optional: improve detection on low‑quality scans
            reader.BarcodeSettings.ImageQuality = 90;
            reader.BarcodeSettings.PureBarcode = false;

            // Iterate through every barcode found in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Output extended Macro PDF417 fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender ?? \"N/A\"}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**Output previsto** (i valori varieranno in base alla tua immagine):

```
CodeType: MacroPdf417
CodeText: 1234567890ABCDEFGHIJ
Pdf417MacroFileID: 42
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: Invoice_2026_10.pdf
Pdf417MacroChecksum: 32768
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2026-10-24T14:32:10Z
Pdf417MacroAddressee: AccountingDept
Pdf417MacroSender: SalesTeam
MacroPdf417Terminator: True
----------------------------------------
```

Se l'immagine non contiene simboli Macro PDF417, il programma non scrive nulla e termina silenziosamente—perfetto per lavori batch che elaborano molti file.

## Domande frequenti

**D: Posso leggere un PDF417 standard (non‑macro) con lo stesso codice?**  
R: Sì. Cambia `DecodeType.MacroPdf417` in `DecodeType.Pdf417`. La proprietà `Extended` sarà vuota, ma `CodeText` e `CodeTypeName` rimarranno disponibili.

**D: Aspose.BarCode supporta la lettura da uno stream anziché da un percorso file?**  
R: Assolutamente. Usa il sovraccarico `new BarCodeReader(Stream, DecodeType)` e passa un `FileStream` o `MemoryStream`. Questo è utile quando l'immagine proviene da un'API web.

**D: Come valido il checksum?**  
R: Il campo `MacroPdf417Checksum` contiene il valore CRC‑16 grezzo. Puoi ricalcolare il checksum sul file ricostruito e confrontarlo per garantire l'integrità dei dati.

## Prossimi passi e argomenti correlati

* **Scrivere codici a barre PDF417** – esplora `BarCodeGenerator` per creare codici macro di test.  
* **Combinare più segmenti** – dopo aver letto tutti i segmenti, ordina per `MacroPdf417SegmentID` e concatena `CodeText` per ricostruire il payload originale.  
* **Ottimizzazione delle prestazioni** – per scenari ad alto volume, riutilizza una singola istanza di `BarCodeReader` su molte immagini e


## Cosa dovresti imparare dopo?


I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare ulteriori funzionalità dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come leggere PDF417 in C# – Esempio completo di codice a barre](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [Come creare un codice a barre macro PDF417 in C# usando Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Leggere il codice a barre da immagine C# – guida completa con Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}