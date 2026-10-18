---
category: general
date: 2026-10-18
description: Scopri come leggere i codici a barre da un'immagine in C# con Aspose.BarCode,
  includendo l'estrazione dei metadati Macro PDF417 e un codice di esempio completo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode from image
- C# barcode reader
- Macro PDF417 metadata
- BarCodeReader class
- DecodeType.MacroPdf417
- barcode metadata extraction
language: it
lastmod: 2026-10-18
og_description: Come leggere il codice a barre da un'immagine usando C# Aspose.BarCode.
  Segui questo tutorial passo passo per estrarre i metadati Macro PDF417 e gestire
  scenari comuni.
og_image_alt: Screenshot showing output of how to read barcode from image with C#
  Aspose.BarCode
og_title: Come leggere il codice a barre da un'immagine in C# – guida completa ad
  Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to read barcode from image in C# with Aspose.BarCode, covering
    Macro PDF417 metadata extraction and complete sample code.
  headline: How to read barcode from image in C# using Aspose.BarCode
  type: TechArticle
- description: Learn how to read barcode from image in C# with Aspose.BarCode, covering
    Macro PDF417 metadata extraction and complete sample code.
  name: How to read barcode from image in C# using Aspose.BarCode
  steps:
  - name: Expected console output
    text: '``` CodeType: MacroPdf417 CodeText: https://example.com/document.pdf MacroFileID:
      12345 MacroSegmentID: 1 MacroSegmentsCount: 3 MacroFileName: document.pdf MacroChecksum:
      0x1A2B3C4D MacroFileSize: 204800 MacroTimeStamp: 2023-07-15T10:23:45Z MacroAddressee:
      Acme Corp MacroSender: Warehouse 7 MacroTer'
  - name: Large images
    text: 'Reading very large images can consume significant memory. Use the `BarcodeReader`
      overload that accepts `ReaderParameters` to limit the maximum image size:'
  - name: Missing or corrupted metadata
    text: If any of the Macro fields are missing, the corresponding property returns
      `null` or `0`. Log these cases and decide whether to treat the barcode as incomplete.
  - name: Multiple barcode types in one image
    text: 'If an image may contain other barcode formats, you can pass an array of
      `DecodeType` values:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Come leggere il codice a barre da un'immagine in C# usando Aspose.BarCode
url: /it/net/one-dimensional-barcode-types/how-to-read-barcode-from-image-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come leggere un codice a barre da un'immagine in C# usando Aspose.BarCode

Se hai bisogno di **come leggere un codice a barre da un'immagine** in un'applicazione .NET, questa guida mostra i passaggi esatti con Aspose.BarCode. Che tu stia elaborando documenti scansionati, ricevute o etichette di inventario, vedrai come leggere il codice a barre, estrarre i metadati Macro PDF417 e gestire i casi limite più comuni.

Leggere un codice a barre da un'immagine è un compito di routine, ma estrarre i campi estesi Macro PDF417 aggiunge un livello di complessità. Questo tutorial copre l'intero flusso di lavoro, dalla configurazione del progetto a un esempio completamente eseguibile, così potrai copiare‑incollare il codice e vedere risultati immediati.

## Cosa imparerai

- Come configurare Aspose.BarCode per progetti C#.  
- Il modo corretto di istanziare il **lettore di codici a barre C#** per un'immagine Macro PDF417.  
- Come iterare su ogni codice a barre rilevato e visualizzare le informazioni di base.  
- Come accedere ai **metadati Macro PDF417** come file ID, segment ID e checksum.  
- Suggerimenti per gestire metadati mancanti, immagini di grandi dimensioni ed errori di decodifica comuni.  

**Prerequisiti**

- .NET 6.0 (o successivo) installato.  
- Familiarità di base con C# e Visual Studio (qualsiasi IDE va bene).  
- Un file immagine che contenga un codice a barre Macro PDF417 (ad es., `ExtPDF417Meta.png`).  

## Passo 1: Installa Aspose.BarCode

Apri un terminale nella cartella del tuo progetto ed esegui:

```bash
dotnet add package Aspose.BarCode
```

Il pacchetto include la **classe BarCodeReader**, che implementa la funzionalità del **lettore di codici a barre C#** necessaria per questo tutorial.

## Passo 2: Configura l'ambiente di sviluppo

Crea una nuova applicazione console se non ne hai già una:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Aggiungi le direttive `using` all'inizio di `Program.cs`:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;
```

Questi namespace espongono la **classe BarCodeReader** e l'enumerazione `DecodeType` richieste per la decodifica Macro PDF417.

## Passo 3: Inizializza il BarCodeReader per Macro PDF417

Il cuore di **come leggere un codice a barre da un'immagine** è creare un'istanza di `BarCodeReader` che punti al `DecodeType` specifico. Per Macro PDF417 devi passare `DecodeType.MacroPdf417`:

```csharp
// Step 3: Create a barcode reader for a Macro PDF417 image
using (BarCodeReader reader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png", DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image.
}
```

**Perché è importante:**  
Scegliere `DecodeType.MacroPdf417` indica alla libreria di cercare il formato esteso Macro PDF417, che contiene campi aggiuntivi oltre ai dati di base del codice a barre. Se utilizzi un generico `DecodeType.Pdf417`, quei campi extra verrebbero ignorati.

## Passo 4: Itera sui codici a barre rilevati

Un'immagine singola può contenere più codici a barre. Il metodo `ReadBarCodes()` restituisce una collezione enumerabile di oggetti `BarCodeResult`. Scorri la collezione per visualizzare le informazioni di base di ciascun codice a barre:

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    Console.WriteLine($"CodeType: {result.CodeTypeName}");
    Console.WriteLine($"CodeText: {result.CodeText}");
}
```

Il valore `CodeTypeName` indica la simbologia esatta del codice a barre (ad es., “MacroPdf417”), mentre `CodeText` contiene la stringa decodificata.

## Passo 5: Estrai e visualizza i metadati Macro PDF417

Quando il codice a barre è un Macro PDF417, la proprietà `Extended.Pdf417` fornisce un ricco insieme di campi di metadati. Accedili direttamente come mostrato di seguito:

```csharp
Console.WriteLine($"MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroTerminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
```

Questi campi ti danno tutto il necessario per ricostruire il file multi‑segmento originale, verificare l'integrità e associare il codice a barre a un documento o mittente specifico.

### Output console previsto

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
MacroFileID: 12345
MacroSegmentID: 1
MacroSegmentsCount: 3
MacroFileName: document.pdf
MacroChecksum: 0x1A2B3C4D
MacroFileSize: 204800
MacroTimeStamp: 2023-07-15T10:23:45Z
MacroAddressee: Acme Corp
MacroSender: Warehouse 7
MacroTerminator: END
```

Se l'immagine non contiene un codice a barre Macro PDF417, l'oggetto `Extended.Pdf417` sarà `null`. Gestisci questo caso per evitare `NullReferenceException`:

```csharp
if (result.Extended?.Pdf417 != null)
{
    // Safe to read metadata
}
else
{
    Console.WriteLine("No Macro PDF417 metadata found.");
}
```

## Passo 6: Gestione di errori comuni e casi limite

### Immagini di grandi dimensioni

Leggere immagini molto grandi può consumare molta memoria. Usa la sovraccarico di `BarcodeReader` che accetta `ReaderParameters` per limitare la dimensione massima dell'immagine:

```csharp
ReaderParameters parameters = new ReaderParameters
{
    MaxImageSize = 4096 // pixels
};

using (BarCodeReader reader = new BarCodeReader(
           "large_image.png", DecodeType.MacroPdf417, parameters))
{
    // Process as before
}
```

### Metadati mancanti o corrotti

Se uno dei campi Macro è mancante, la proprietà corrispondente restituisce `null` o `0`. Registra questi casi e decidi se trattare il codice a barre come incompleto.

### Più tipi di codice a barre in una sola immagine

Se un'immagine può contenere altri formati di codice a barre, puoi passare un array di valori `DecodeType`:

```csharp
DecodeType[] types = { DecodeType.MacroPdf417, DecodeType.QR, DecodeType.Code128 };
using (BarCodeReader reader = new BarCodeReader("mixed.png", types))
{
    // Iterate as before
}
```

Questo approccio mantiene la logica di **come leggere un codice a barre da un'immagine** flessibile senza sacrificare le prestazioni.

## Passo 7: Codice sorgente completo

Di seguito trovi il programma completo, pronto per l'esecuzione. Sostituisci `YOUR_DIRECTORY/ExtPDF417Meta.png` con il percorso della tua immagine.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image containing a Macro PDF417 barcode
            const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the C# barcode reader for Macro PDF417
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate over all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // Safely access Macro PDF417 metadata
                    if (result.Extended?.Pdf417 != null)
                    {
                        Console.WriteLine($"MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                        Console.WriteLine($"MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                        Console.WriteLine($"MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                        Console.WriteLine($"MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                        Console.WriteLine($"MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                        Console.WriteLine($"MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                        Console.WriteLine($"MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                        Console.WriteLine($"MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                        Console.WriteLine($"MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                        Console.WriteLine($"MacroTerminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro PDF417 metadata found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Barcode processing completed.");
        }
    }
}
```

Esegui il programma con:

```bash
dotnet run
```

Dovresti vedere il tipo di codice a barre, il testo decodificato e tutti i campi Macro PDF417 disponibili stampati nella console.

## Conclusione

In questo tutorial hai imparato **come leggere un codice a barre da un'immagine** usando Aspose.BarCode per C#. La guida ha coperto la configurazione del **lettore di codici a barre C#**,

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [How to read PDF417 barcode c# – complete step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}