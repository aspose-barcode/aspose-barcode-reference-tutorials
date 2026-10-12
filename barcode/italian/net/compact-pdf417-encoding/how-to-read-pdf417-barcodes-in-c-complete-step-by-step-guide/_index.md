---
category: general
date: 2026-09-22
description: Impara a leggere i codici a barre PDF417 in C# con un esempio completo
  di lettore di codici a barre. Questo tutorial ti mostra come leggere rapidamente
  e in modo affidabile un'immagine di codice a barre in C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read barcode image c#
- c# barcode reader example
language: it
lastmod: 2026-09-22
og_description: Come leggere i codici a barre PDF417 in C# usando un esempio conciso
  di lettore di codici a barre. Segui la guida per decodificare le immagini Macro
  PDF417 ed estrarre i metadati.
og_image_alt: Screenshot of C# code that reads a PDF417 barcode and prints its metadata
og_title: Come leggere i codici a barre PDF417 in C# – esempio completo di lettore
  di codici a barre
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to read PDF417 barcodes in C# with a full barcode reader
    example. This tutorial shows you how to read barcode image C# quickly and reliably.
  headline: How to read PDF417 barcodes in C# – complete step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcodes in C# with a full barcode reader
    example. This tutorial shows you how to read barcode image C# quickly and reliably.
  name: How to read PDF417 barcodes in C# – complete step‑by‑step guide
  steps:
  - name: Why each step matters
    text: '1. **Creating the reader with `DecodeType.MacroPdf417`** – Macro PDF417
      is a special variant that can carry file‑level metadata. Specifying the decode
      type ensures the SDK parses those extra fields instead of treating the code
      as a plain PDF417. 2. **Iterating over `ReadBarCodes()`** – An image can '
  - name: Reading a non‑macro PDF417 barcode
    text: If your source images contain regular PDF417 codes (no macro metadata),
      replace `DecodeType.MacroPdf417` with `DecodeType.Pdf417`. The rest of the code
      stays identical, but the `Extended.Pdf417` block will be empty because those
      fields simply don’t exist.
  - name: Handling multi‑segment PDFs
    text: 'Macro PDF417 can split a large document across several barcode segments.
      To reassemble the original file you must:'
  - name: Dealing with corrupted images
    text: '- **Low contrast** – Increase image preprocessing (e.g., histogram equalization)
      before passing it to `BarCodeReader`. - **Rotation** – Use `barcodeReader.SetRotateAngle(90)`
      or enable auto‑rotate if the SDK supports it. - **Partial scans** – Ensure the
      image resolution is at least 300 dpi; otherwis'
  - name: Next steps
    text: '- Explore **read barcode image C#** techniques for other symbologies (QR,
      DataMatrix) using the same `BarCodeReader` API. - Integrate the barcode decoder
      into an ASP.NET Core service to process uploads on the fly. - Experiment with
      image preprocessing libraries (e.g., `OpenCvSharp`) to boost success'
  type: HowTo
tags:
- barcode
- pdf417
- c#
title: Come leggere i codici a barre PDF417 in C# – guida completa passo‑passo
url: /it/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come leggere i codici a barre PDF417 in C# – guida completa passo‑passo

Se hai bisogno di **come leggere pdf417** in un'applicazione .NET, questa guida ti mostra il codice esatto e il ragionamento di cui hai bisogno. Entro la fine delle prime due frasi saprai come leggere un'immagine di codice a barre in C# usando la popolare classe `BarCodeReader`, e avrai un esempio pronto all'uso che estrae ogni singolo metadato Macro PDF417.

La lettura dei codici a barre PDF417 è una necessità comune quando si elaborano etichette di spedizione, carte d'imbarco o documenti sicuri. Questo tutorial copre tutto, dalla configurazione del lettore alla gestione dei casi limite, così potrai integrare la scansione dei codici a barre con fiducia.

## Cosa otterrai

- Decodifica di un file immagine Macro PDF417.
- Stampa delle informazioni di base del codice a barre (tipo e testo).
- Accesso a tutti i campi estesi Macro PDF417 come ID file, conteggio segmenti e timestamp.
- Comprensione delle insidie comuni quando si lavora con codici PDF417 multi‑segmento.

**Prerequisiti**

- .NET 6.0 o successivo (il codice funziona anche con .NET Framework 4.7+).
- Un riferimento al SDK di barcode che fornisce `BarCodeReader`, `DecodeType` e `BarCodeResult` (ad es., Aspose.BarCode, Dynamsoft o qualsiasi libreria che espone la stessa API).
- Un file immagine (`ExtPDF417Meta.png`) che contiene un codice a barre Macro PDF417.

> **Consiglio professionale:** Posiziona l'immagine in una cartella relativa alla radice del tuo progetto e imposta la proprietà **Copy to Output Directory** su *Copy if newer* così il percorso funziona durante il debug.

![Come leggere il codice a barre PDF417 usando C#](https://example.com/placeholder-image.png)

## Come leggere il codice a barre PDF417 in C# – il codice completo

Di seguito trovi un programma autonomo che puoi incollare in un'applicazione console. Crea un lettore di codici a barre, itera su ogni risultato decodificato e stampa sia i campi standard sia quelli estesi Macro PDF417.

```csharp
using System;
using Aspose.BarCode;          // Replace with the namespace of your barcode SDK
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode reader for a Macro PDF417 image
        // The second argument tells the SDK to look specifically for Macro PDF417 codes.
        using var barcodeReader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417);

        // Step 2: Decode all barcodes present in the image
        foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
        {
            // Step 3: Display the basic barcode information
            Console.WriteLine($"CodeType: {result.CodeTypeName}");
            Console.WriteLine($"CodeText: {result.CodeText}");

            // Step 4: Output Macro PDF417 specific metadata
            // All properties are available through the Extended.Pdf417 object.
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
            Console.WriteLine(new string('-', 40));
        }
    }
}
```

### Perché ogni passaggio è importante

1. **Creare il lettore con `DecodeType.MacroPdf417`** – Macro PDF417 è una variante speciale che può trasportare metadati a livello di file. Specificare il tipo di decodifica assicura che l'SDK analizzi quei campi extra invece di trattare il codice come un semplice PDF417.
2. **Iterare su `ReadBarCodes()`** – Un'immagine può contenere più di un codice a barre (ad es., un QR code accanto a un PDF417). Il ciclo garantisce che vengano catturati tutti i risultati.
3. **Stampare `CodeTypeName` e `CodeText`** – Queste sono le proprietà più usate; forniscono il nome della simbologia e il payload leggibile dall'uomo.
4. **Accedere a `Extended.Pdf417`** – L'oggetto `Extended` appare solo per i tipi di decodifica correlati a PDF417. Ogni proprietà mappa direttamente alla specifica Macro PDF417, permettendoti di ricostruire il file originale o convalidare l'ordine dei segmenti.

## Varianti comuni e casi limite

### Lettura di un codice a barre PDF417 non macro

Se le tue immagini di origine contengono codici PDF417 regolari (senza metadati macro), sostituisci `DecodeType.MacroPdf417` con `DecodeType.Pdf417`. Il resto del codice rimane identico, ma il blocco `Extended.Pdf417` sarà vuoto perché quei campi semplicemente non esistono.

### Gestione di PDF multi‑segmento

Macro PDF417 può suddividere un documento grande in diversi segmenti di codice a barre. Per ricomporre il file originale devi:

1. Raccogliere l'`Pdf417MacroSegmentID` di ogni segmento.
2. Ordinare i segmenti per ID.
3. Verificare che `Pdf417MacroSegmentsCount` corrisponda al numero di segmenti ricevuti.
4. Concatenare il `CodeText` di ciascun segmento nell'ordine corretto.
5. Facoltativamente convalidare `Pdf417MacroChecksum`.

Di seguito trovi uno snippet conciso che dimostra la logica di ricomposizione:

```csharp
var segments = new SortedDictionary<int, string>();
int expectedCount = 0;

foreach (var result in barcodeReader.ReadBarCodes())
{
    int segId = result.Extended.Pdf417.MacroPdf417SegmentID;
    int segCount = result.Extended.Pdf417.MacroPdf417SegmentsCount;
    expectedCount = segCount;               // will be the same for every segment
    segments[segId] = result.CodeText;       // store payload by segment ID
}

// Verify we have all parts
if (segments.Count == expectedCount)
{
    string fullPayload = string.Concat(segments.Values);
    Console.WriteLine("Reassembled payload:");
    Console.WriteLine(fullPayload);
}
else
{
    Console.WriteLine($"Missing segments: expected {expectedCount}, received {segments.Count}");
}
```

### Gestione di immagini corrotte

- **Basso contrasto** – Aumenta la pre‑elaborazione dell'immagine (ad es., equalizzazione dell'istogramma) prima di passarla a `BarCodeReader`.
- **Rotazione** – Usa `barcodeReader.SetRotateAngle(90)` o abilita l'auto‑rotazione se l'SDK lo supporta.
- **Scansioni parziali** – Assicurati che la risoluzione dell'immagine sia almeno 300 dpi; altrimenti l'SDK potrebbe non rilevare i piccoli segmenti.

## Esempio di lettore di barcode c# – migliori pratiche

| Pratica | Motivo |
|----------|--------|
| **Disporre il lettore con `using`** | Garantisce il rilascio tempestivo delle risorse native, prevenendo perdite di memoria. |
| **Validare che `result.Extended` non sia null** | Alcuni SDK restituiscono `null` per codici non macro; il controllo evita un `NullReferenceException`. |
| **Registrare il `Pdf417MacroFileID`** | Questo identificatore è unico per file ed è utile per le tracce di audit. |
| **Racchiudere la decodifica in try/catch** | Errori I/O (file mancante) o formati non supportati generano eccezioni che devono essere gestite in modo elegante. |

```csharp
try
{
    // decoding logic here
}
catch (FileNotFoundException ex)
{
    Console.Error.WriteLine($"Image not found: {ex.FileName}");
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## Output previsto

Eseguendo il programma completo su un `ExtPDF417Meta.png` formattato correttamente otterrai un output simile a:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-08-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

Se l'immagine contiene più segmenti, il ciclo stamperà i metadati di ciascun segmento in sequenza.

## Conclusione

Ora sai **come leggere pdf417** in C# e disponi di un **esempio di lettore di barcode c#** che estrae ogni campo Macro PDF417. La soluzione copre la decodifica di base, l'estrazione dei metadati, la ricomposizione multi‑segmento e la gestione degli errori, fornendoti una base pronta per la produzione per qualsiasi flusso di lavoro di elaborazione documenti.

### Prossimi passi

- Esplora le tecniche **read barcode image C#** per altre simbologie (QR, DataMatrix) usando la stessa API `BarCodeReader`.
- Integra il decoder di barcode in un servizio ASP.NET Core per elaborare upload al volo.
- Sperimenta con librerie di pre‑elaborazione immagini (ad es., `OpenCvSharp`) per aumentare il tasso di successo su scansioni di bassa qualità.

Buon coding, e sentiti libero di adattare l'esempio alle tue esigenze specifiche!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive e a esplorare approcci di implementazione alternativi nei tuoi progetti.

- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [How to Read PDF417 in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}