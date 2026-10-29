---
category: general
date: 2026-10-28
description: Come decodificare rapidamente i codici a barre PDF417 in C#. Impara a
  leggere un'immagine di codice a barre in C# usando Aspose.BarCode con un esempio
  completo e eseguibile.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcode image c#
- PDF417 decoding C#
- barcode reader C#
- Aspose.BarCode example
language: it
lastmod: 2026-10-28
og_description: Come decodificare i codici a barre PDF417 in C# con Aspose.BarCode.
  Questa guida ti mostra come leggere un'immagine di codice a barre in C# passo passo,
  completa di codice.
og_image_alt: Screenshot of C# code that decodes a PDF417 barcode from an image
og_title: Come decodificare i codici a barre PDF417 in C# – tutorial C# per leggere
  l'immagine del codice a barre
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: How to decode PDF417 barcodes in C# quickly. Learn to read barcode
    image C# using Aspose.BarCode with a complete, runnable example.
  headline: How to decode PDF417 barcodes in C# and read barcode image C#
  type: TechArticle
- description: How to decode PDF417 barcodes in C# quickly. Learn to read barcode
    image C# using Aspose.BarCode with a complete, runnable example.
  name: How to decode PDF417 barcodes in C# and read barcode image C#
  steps:
  - name: What each line does
    text: '| Line | Explanation | |------|-------------| | `result.CodeTypeName` |
      Human‑readable name of the detected barcode type (e.g., “MacroPdf417”). | |
      `result.CodeText` | The raw data encoded in the barcode. | | `result.Extended.Pdf417.MacroPdf417FileID`
      | Identifier that ties all segments of a macro P'
  - name: Handling common edge cases
    text: '| Situation | Recommended handling | |-----------|----------------------|
      | **No barcode found** | Check `reader.ReadBarCodes().Any()` before the loop
      and display a friendly message. | | **Corrupted image** | Wrap the `BarCodeReader`
      creation in a `try/catch` block for `BarCodeException`. | | **Mult'
  - name: Next steps
    text: '* Explore other barcode formats by changing `DecodeType` (e.g., `DecodeType.QR`,
      `DecodeType.Code128`). * Combine multiple decoded segments to reconstruct the
      original document. * Use the `BarCodeGenerator` class to create test PDF417
      barcodes on the fly.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Come decodificare i codici a barre PDF417 in C# e leggere l'immagine del codice
  a barre in C#
url: /it/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-and-read-barcode-image-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come decodificare i codici a barre PDF417 in C# e leggere l'immagine del codice a barre C#

Se hai bisogno di **how to decode pdf417** in un'applicazione .NET, questa guida ti fornisce una soluzione pronta all'uso. Vedrai esattamente come **read barcode image c#** usando la libreria Aspose.BarCode, estrarre i campi macro‑PDF417 e visualizzarli nella console.

La decodifica dei codici a barre PDF417 appare spesso in sistemi di logistica, biglietteria e verifica dell'identità. Alla fine di questo tutorial sarai in grado di caricare qualsiasi immagine che contiene un codice a barre Macro PDF417, decodificarla e accedere ai valori file ID, segment ID e segment count, essenziali per assemblare documenti multi‑segmento.

## Prerequisiti

* SDK .NET 6.0 o successivo installato  
* Visual Studio 2022 (o qualsiasi IDE C#)  
* Un pacchetto NuGet Aspose.BarCode per .NET (`Aspose.BarCode`)  
* Un file immagine che contiene un codice a barre Macro PDF417 (l'esempio utilizza `ExtPDF417Meta.png`)

Puoi aggiungere il pacchetto NuGet con il seguente comando:

```bash
dotnet add package Aspose.BarCode
```

## Passo 1: Configurare il progetto e importare i namespace

Crea un nuovo progetto console e importa i namespace richiesti. Le direttive `using` ti danno accesso a `BarCodeReader`, `DecodeType` e agli oggetti di estensione del risultato.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;
```

> **Perché questo passo è importante** – Importare i namespace corretti previene errori di compilazione e rende disponibile l'API per la logica di decodifica successiva.

## Passo 2: Specificare il percorso dell'immagine

Definisci il percorso assoluto o relativo dell'immagine del codice a barre. Mantenere il percorso in una variabile rende il codice riutilizzabile per immagini diverse.

```csharp
// Step 2: Specify the path to the image that contains a Macro PDF417 barcode
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
```

> **Suggerimento:** Usa `Path.Combine` se costruisci il percorso da più parti; gestisce i separatori di directory tra i diversi sistemi operativi.

## Passo 3: Creare un `BarCodeReader` configurato per la decodifica Macro PDF417

Istanzia `BarCodeReader` con il percorso dell'immagine e il flag `DecodeType.MacroPdf417`. Questo indica alla libreria di cercare specificamente i simboli Macro PDF417.

```csharp
// Step 3: Create a BarCodeReader configured for MacroPdf417 decoding
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image.
```

> **Perché questo passo è importante** – Selezionare il `DecodeType` corretto migliora le prestazioni perché il motore ignora i formati di codice a barre non correlati.

## Passo 4: Leggere tutti i codici a barre e visualizzare le informazioni macro

Itera su ogni `BarCodeResult` restituito da `reader.ReadBarCodes()`. L'oggetto risultato contiene sia campi generici (`CodeTypeName`, `CodeText`) sia estensioni specifiche di Macro PDF417 (`MacroPdf417FileID`, `MacroPdf417SegmentID`, `MacroPdf417SegmentsCount`).

```csharp
    // Step 4: Read all barcodes in the image and display the most relevant macro information
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Code Type : {result.CodeTypeName}");
        Console.WriteLine($"Code Text : {result.CodeText}");

        // Macro PDF417 specific fields
        Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Segment ID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Segments  : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
    }
}
```

### Cosa fa ogni riga

| Riga | Spiegazione |
|------|-------------|
| `result.CodeTypeName` | Nome leggibile dall'uomo del tipo di codice a barre rilevato (es., “MacroPdf417”). |
| `result.CodeText` | I dati grezzi codificati nel codice a barre. |
| `result.Extended.Pdf417.MacroPdf417FileID` | Identificatore che collega tutti i segmenti di un documento macro PDF417. |
| `result.Extended.Pdf417.MacroPdf417SegmentID` | Indice del segmento corrente all'interno dell'intero documento. |
| `result.Extended.Pdf417.MacroPdf417SegmentsCount` | Numero totale di segmenti previsto per il documento. |

> **Consiglio professionale:** Memorizza i campi macro in un database se devi ricostruire il documento completo in seguito. Il `File ID` ti consente di raggruppare i segmenti appartenenti alla stessa origine.

## Passo 5: Eseguire il programma e verificare l'output

Compila ed esegui l'applicazione console:

```bash
dotnet run
```

L'output tipico della console appare così:

```
Code Type : MacroPdf417
Code Text : 0123456789ABCD
File ID   : 101
Segment ID: 1
Segments  : 3
```

Se l'immagine contiene più simboli Macro PDF417, il ciclo stampa ciascuno in sequenza.

### Gestione dei casi limite comuni

| Situazione | Gestione consigliata |
|------------|----------------------|
| **Nessun codice a barre trovato** | Verifica `reader.ReadBarCodes().Any()` prima del ciclo e visualizza un messaggio amichevole. |
| **Immagine corrotta** | Avvolgi la creazione di `BarCodeReader` in un blocco `try/catch` per `BarCodeException`. |
| **Formati di codice a barre multipli** | Usa `DecodeType.AllSupported` e filtra i risultati con `result.CodeTypeName == "MacroPdf417"`. |
| **Immagini di grandi dimensioni** | Ridimensiona l'immagine prima della decodifica per migliorare le prestazioni; la libreria accetta un oggetto `Bitmap`. |

## Codice sorgente completo

Di seguito trovi il programma completo e autonomo. Copialo in `Program.cs` di un nuovo progetto console e sostituisci `YOUR_DIRECTORY/ExtPDF417Meta.png` con il percorso reale della tua immagine.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417Decoder
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Specify the path to the image that contains a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Step 3: Create a BarCodeReader configured for MacroPdf417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Step 4: Read all barcodes in the image and display the most relevant macro information
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // Macro PDF417 specific fields
                    Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Segment ID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Segments  : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                }
            }
        }
    }
}
```

## Conclusione

Ora sai **how to decode pdf417** i codici a barre in C# e come **read barcode image c#** usando Aspose.BarCode. Il tutorial ti ha guidato attraverso la configurazione del progetto, il caricamento dell'immagine, la configurazione del lettore, l'estrazione dei risultati e la gestione dei casi limite. Con questa base puoi integrare la decodifica PDF417 in sistemi di inventario, validatori di biglietti o qualsiasi flusso di lavoro che si basa su dati macro‑codificati.

### Prossimi passi

* Esplora altri formati di codice a barre cambiando `DecodeType` (es., `DecodeType.QR`, `DecodeType.Code128`).  
* Combina più segmenti decodificati per ricostruire il documento originale.  
* Usa la classe `BarCodeGenerator` per creare codici a barre PDF417 di test al volo.  

Sentiti libero di sperimentare con diverse sorgenti di immagini, regolare l'output della console o incorporare la logica di decodifica in una web API per l'elaborazione in tempo reale. Buon coding!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come decodificare PDF417 in C# con un esempio di lettore di codici a barre](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/)
- [Come generare codici a barre PDF417 in C# con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/)
- [Come leggere un codice a barre da un'immagine c# usando Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}