---
category: general
date: 2026-09-07
description: Scopri come decodificare i codici a barre PDF417 in C# usando BarCodeReader.
  Questa guida passo passo spiega anche come leggere i dati PDF417 in modo efficiente.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- how to read pdf417
- PDF417 barcode decoding C#
- MacroPdf417 extraction C#
- barcode reader BarCodeReader
- GroupDocs.Barcode tutorial
language: it
lastmod: 2026-09-07
og_description: Come decodificare i codici a barre PDF417 in C# usando BarCodeReader.
  Segui questo tutorial per imparare a leggere i dati PDF417 ed estrarre i campi MacroPdf417.
og_image_alt: Screenshot of C# code reading PDF417 barcode fields in the console
og_title: Come decodificare i codici a barre PDF417 in C# – guida completa
schemas:
- author: GroupDocs
  dateModified: '2026-09-07'
  description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  headline: How to decode PDF417 barcodes in C# with BarCodeReader
  type: TechArticle
- description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  name: How to decode PDF417 barcodes in C# with BarCodeReader
  steps:
  - name: Prepare the project and import namespaces
    text: '```csharp using System; using GroupDocs.Barcode; using GroupDocs.Barcode.Common;
      ```'
  - name: Define the image path
    text: '```csharp // Replace with the absolute or relative path to your barcode
      image string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png"; ```'
  - name: Initialize the barcode reader for MacroPdf417 decoding
    text: '```csharp using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
      { // Step 4 runs inside this block } ```'
  - name: Read every barcode found in the image
    text: '```csharp foreach (BarCodeResult result in reader.ReadBarCodes()) { //
      Step 5 extracts the MacroPdf417 fields } ```'
  - name: Retrieve and display Macro PDF417 specific data
    text: '```csharp Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
      Console.WriteLine'
  - name: Full runnable example
    text: 'Combine the snippets above into a single `Program.cs` file:'
  type: HowTo
tags:
- PDF417
- C#
- barcode decoding
title: Come decodificare i codici a barre PDF417 in C# con BarCodeReader
url: /it/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-with-barcodereader/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come decodificare i codici a barre PDF417 in C# con BarCodeReader

Se hai bisogno di **come decodificare i codici a barre PDF417** in un'applicazione .NET, questa guida ti accompagna passo passo nell'intero processo. Scoprirai anche **come leggere i dati PDF417** come il file MacroPdf417 e gli identificatori di segmento, il tutto con poche righe di C#.

La decodifica di PDF417 è comune quando si lavora con biglietti di trasporto, patenti di guida o etichette di spedizione. Alla fine di questo tutorial avrai un programma console eseguibile che stampa ogni campo MacroPdf417 esposto dal SDK GroupDocs.Barcode.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6.0 SDK o successivo (il codice compila con .NET Core e .NET Framework)
* Visual Studio 2022 o qualsiasi IDE che supporti C#
* Il pacchetto NuGet **GroupDocs.Barcode** (`GroupDocs.Barcode` ≥ 23.3)
* Un file immagine che contenga un codice a barre Macro PDF417 (ad es., `ExtPDF417Meta.png`)

> **Suggerimento:** Installa il pacchetto tramite CLI:  
> `dotnet add package GroupDocs.Barcode --version 23.3`

## Come decodificare i codici a barre PDF417 in C#

Le sezioni seguenti suddividono la soluzione in passaggi logici. Ogni passaggio include il codice esatto di cui hai bisogno e una breve spiegazione del perché è importante.

### Passo 1: Preparare il progetto e importare gli spazi dei nomi

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;
```

*Perché?*  
`GroupDocs.Barcode` fornisce la classe `BarCodeReader`, mentre `GroupDocs.Barcode.Common` contiene l'enumerazione `DecodeType` necessaria per la decodifica PDF417.

### Passo 2: Definire il percorso dell'immagine

```csharp
// Replace with the absolute or relative path to your barcode image
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
```

*Perché?*  
Il lettore funziona con qualsiasi formato immagine supportato da .NET (`.png`, `.jpg`, `.bmp`). Fornire il percorso corretto garantisce che l'SDK possa trovare il file.

### Passo 3: Inizializzare il lettore di codici a barre per la decodifica MacroPdf417

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Step 4 runs inside this block
}
```

*Perché?*  
`DecodeType.MacroPdf417` indica all'SDK di cercare il formato esteso Macro PDF417, che trasporta metadati aggiuntivi come gli ID di file e di segmento. L'uso dell'istruzione `using` garantisce che le risorse non gestite vengano rilasciate tempestivamente.

### Passo 4: Leggere tutti i codici a barre trovati nell'immagine

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Step 5 extracts the MacroPdf417 fields
}
```

*Perché?*  
Un'immagine può contenere più codici a barre. Il metodo `ReadBarCodes()` restituisce una collezione, permettendoti di elaborare ciascuno individualmente.

### Passo 5: Recuperare e visualizzare i dati specifici di Macro PDF417

```csharp
Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
```

*Perché?*  
L'oggetto `Extended.Pdf417` espone tutti i campi Macro PDF417 definiti dalla specifica. Stamparli ti consente di verificare che l'operazione di decodifica sia riuscita e ti fornisce i dati necessari per l'elaborazione successiva.

### Esempio completo eseguibile

Unisci gli snippet sopra in un unico file `Program.cs`:

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // 1️⃣ Path to the image that contains the Macro PDF417 barcode
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 2️⃣ Create a reader configured for MacroPdf417 decoding
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // 3️⃣ Iterate over all detected barcodes
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // 4️⃣ Output Macro PDF417 metadata
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
                Console.WriteLine(); // Blank line for readability
            }
        }
    }
}
```

**Output console previsto** (i valori varieranno in base al contenuto del codice a barre):

```
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentCount: 3
Pdf417MacroFileName: shipment_data
Pdf417MacroTimestamp: 2024-07-15T10:23:45Z
```

Se l'immagine non contiene un codice a barre Macro PDF417, la collezione `ReadBarCodes()` sarà vuota e non verrà stampato nulla.

## Varianti comuni e casi limite

| Situazione | Come adattare il codice |
|------------|--------------------------|
| **PDF417 standard (non macro)** | Cambia `DecodeType.MacroPdf417` in `DecodeType.Pdf417`. L'oggetto `Extended.Pdf417` sarà `null`, quindi gestisci i riferimenti null. |
| **Immagini multiple** | Avvolgi l'inizializzazione del lettore in un ciclo `foreach (var path in imagePaths)`. |
| **Immagini di grandi dimensioni** | Imposta `reader.Options.ImageProcessingOptions.MaxImageDimension = 2000;` per limitare l'uso di memoria. |
| **Batch ad alte prestazioni** | Riutilizza una singola istanza di `BarCodeReader` con `reader.SetImage(path)` invece di creare un nuovo oggetto per ogni file. |

## Checklist di risoluzione problemi

* **Nessun output:** Verifica che `imagePath` punti a un file valido e che l'immagine contenga effettivamente un codice a barre PDF417. |
* **`Extended.Pdf417` nullo:** Probabilmente hai usato `DecodeType.Pdf417` invece di `MacroPdf417`. |
* **Eccezione `FileNotFoundException`:** Assicurati che la directory di lavoro corrisponda al percorso o utilizza un percorso assoluto. |
* **Punteggio di confidenza basso:** Aumenta la qualità dell'immagine o regola le impostazioni `reader.Options.Quality`. |

## Conclusione

Ora sai **come decodificare i codici a barre PDF417** in C# e **come leggere i metadati PDF417** come gli ID di file Macro, gli ID di segmento e i timestamp. L'esempio completo dimostra come inizializzare `BarCodeReader`, selezionare il tipo di decodifica corretto, iterare sui risultati e estrarre ogni campo MacroPdf417 disponibile.

Da qui puoi:

* Integrare i dati estratti in un sistema di logistica o di validazione dei biglietti.
* Estendere l'app console per scrivere i risultati in un database o in un file JSON.
* Esplorare altri formati di codice a barre supportati da GroupDocs.Barcode (QR, DataMatrix, Code128, ecc.) cambiando l'enumerazione `DecodeType`.

Buona programmazione, e sentiti libero di sperimentare con immagini e impostazioni diverse per padroneggiare la decodifica PDF417 nei tuoi progetti .NET!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare ulteriori funzionalità dell'API e a esplorare approcci di implementazione alternativi nei tuoi progetti.

- [How to Read PDF417 in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [How to Read PDF417 in C# – Complete Barcode Reader Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [How to Generate PDF417 Barcode – Complete Programming Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}