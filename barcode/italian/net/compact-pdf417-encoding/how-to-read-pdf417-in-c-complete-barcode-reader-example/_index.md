---
category: general
date: 2026-07-21
description: Come leggere il codice a barre PDF417 in C# usando un esempio conciso
  di lettore di codici a barre. Impara rapidamente a leggere il codice a barre da
  un'immagine con codice passo‑passo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read barcode from image
- c# barcode reader example
language: it
lastmod: 2026-07-21
og_description: Come leggere il codice a barre PDF417 in C# con un esempio pratico.
  Scopri come leggere il codice a barre da un'immagine e integrare subito l'esempio
  di lettore di codici a barre in C#.
og_image_alt: Screenshot of a C# console app printing PDF417 barcode details
og_title: Come leggere PDF417 in C# – Guida completa al lettore di codici a barre
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: How to read PDF417 barcode in C# using a concise barcode reader example.
    Quickly learn how to read barcode from image with step‑by‑step code.
  headline: How to Read PDF417 in C# – Complete Barcode Reader Example
  type: TechArticle
- description: How to read PDF417 barcode in C# using a concise barcode reader example.
    Quickly learn how to read barcode from image with step‑by‑step code.
  name: How to Read PDF417 in C# – Complete Barcode Reader Example
  steps:
  - name: Why This Works
    text: '- **`DecodeType.MacroPdf417`** tells the reader to expect the extended
      Macro PDF417 format, which carries extra metadata (file ID, segment count, timestamps,
      etc.). - The **`Extended.Pdf417`** object is only populated for Macro PDF417
      barcodes, so accessing those properties is safe after the `ReadBa'
  - name: Multiple Barcodes in One Image
    text: Sometimes a single scan contains more than one PDF417 segment (think of
      a multi‑page document encoded across several symbols). The `foreach` loop already
      enumerates *all* detected barcodes, so you don’t need extra logic—just collect
      the segments and reassemble them later if required.
  - name: Missing Extended Data
    text: 'Not every PDF417 carries macro information. In that scenario `result.Extended.Pdf417`
      will be instantiated but its fields will be default values (zero, empty string,
      or `false`). You can guard against it like this:'
  - name: Performance Tips
    text: '- **Batch processing:** If you have a folder of images, wrap the `BarCodeReader`
      creation inside a loop that reuses the same instance with `barcodeReader.SetImage(imagePath)`.
      This reduces allocation overhead. - **Parallelism:** For large workloads, consider
      `Parallel.ForEach` on the file list, but '
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Come leggere PDF417 in C# – Esempio completo di lettore di codici a barre
url: /it/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come leggere PDF417 in C# – Esempio completo di lettura di codici a barre

Ti sei mai chiesto **come leggere PDF417** in un progetto .NET senza dover setacciare una miriade di documenti? Non sei l'unico. Che tu stia scansionando patenti di guida, carte d'imbarco o etichette di inventario personalizzate, estrarre quei dati in modo affidabile è una necessità reale.  

In questa guida percorreremo un **esempio di lettore di codici a barre c#** che estrae ogni singolo metadato Macro PDF417 da un unico file immagine. Alla fine avrai un'app console pronta all'uso che **legge il codice a barre dall'immagine** e stampa tutti i campi estesi di cui potresti aver bisogno.

## Cosa ti serve

- .NET 6.0 SDK o versioni successive (puoi anche puntare a .NET Framework 4.7+ – il codice funziona allo stesso modo)
- Visual Studio 2022, VS Code o qualsiasi editor C# a tua scelta
- Il pacchetto NuGet **Aspose.BarCode for .NET** (la classe `BarCodeReader` proviene da questa libreria)
- Un file immagine che contiene un codice a barre Macro PDF417 (per la demo useremo `ExtPDF417Meta.png`)

> **Suggerimento:** Se non hai a disposizione un esempio di PDF417, Aspose fornisce alcune immagini di test nel loro repository GitHub – basta scaricarne una e inserirla nella cartella del tuo progetto.

## Passo 1: Installa la libreria per i codici a barre

Apri un terminale nella cartella del tuo progetto ed esegui:

```bash
dotnet add package Aspose.BarCode
```

Il pacchetto aggiunge `BarCodeReader`, `DecodeType` e la proprietà `Extended` di cui avremo bisogno più avanti. Non è necessaria alcuna configurazione aggiuntiva; la libreria funziona subito per la maggior parte dei formati immagine (PNG, JPEG, BMP, ecc.).

## Passo 2: Crea un'app console minimale

Crea un nuovo progetto console se non lo hai già fatto:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Sostituisci il `Program.cs` generato con il codice qui sotto. Nota come ogni sezione sia commentata così puoi seguire la logica anche se sei nuovo nella gestione dei codici a barre.

```csharp
using System;
using Aspose.BarCode;               // Core barcode classes
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // 👉 1️⃣  Point the reader at the image that holds the Macro PDF417 barcode.
        //    Replace the path with your own image location if needed.
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // The BarCodeReader is disposable – using a using‑statement guarantees resources are freed.
        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // 👉 2️⃣  Iterate over every barcode that the reader finds.
            //    Macro PDF417 can embed multiple segments, so we handle them all.
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                // Basic barcode info – always handy for logging.
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // 👉 3️⃣  Pull out the extended Macro PDF417 fields.
                //    These properties live under result.Extended.Pdf417.
                var macro = result.Extended.Pdf417;

                Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40)); // visual separator
            }
        }

        // Keep the console window open when debugging.
        Console.WriteLine("Done. Press any key to exit...");
        Console.ReadKey();
    }
}
```

### Perché funziona

- **`DecodeType.MacroPdf417`** indica al lettore di attendersi il formato Macro PDF417 esteso, che contiene metadati aggiuntivi (ID file, conteggio segmenti, timestamp, ecc.).
- L'oggetto **`Extended.Pdf417`** viene popolato solo per i codici a barre Macro PDF417, quindi accedere a quelle proprietà è sicuro dopo la chiamata `ReadBarCodes()`.
- L'uso di un blocco **`using`** garantisce il rilascio dei handle dei file, evitando problemi di blocco dei file su Windows.

## Passo 3: Esegui l'applicazione

Compila ed esegui:

```bash
dotnet run
```

Se l'immagine contiene un codice a barre Macro PDF417 valido, dovresti vedere un output simile a:

```
CodeType: MacroPdf417
CodeText: 1234567890
Pdf417MacroFileID: 1
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: SampleDocument.pdf
Pdf417MacroChecksum: 0xABCD
Pdf417MacroFileSize: 102400
Pdf417MacroTimeStamp: 2024-03-15T10:23:45Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
Done. Press any key to exit...
```

Se non viene stampato nulla, verifica che il percorso dell'immagine sia corretto e che il codice a barre sia effettivamente una variante Macro PDF417. Un PDF417 normale (senza l'estensione macro) verrà comunque decodificato, ma le proprietà `Extended` saranno vuote.

## Gestione dei casi limite

### Più codici a barre in un'immagine

A volte una singola scansione contiene più di un segmento PDF417 (pensa a un documento multipagina codificato su più simboli). Il ciclo `foreach` elenca già *tutti* i codici a barre rilevati, quindi non è necessaria logica aggiuntiva—basta raccogliere i segmenti e riassemblarli in seguito se necessario.

### Dati estesi mancanti

Non tutti i PDF417 contengono informazioni macro. In questo caso `result.Extended.Pdf417` verrà istanziato ma i suoi campi avranno valori predefiniti (zero, stringa vuota o `false`). Puoi gestirlo così:

```csharp
if (macro.MacroPdf417FileID != 0)
{
    // Process macro data
}
else
{
    Console.WriteLine("No macro information present in this barcode.");
}
```

### Suggerimenti sulle prestazioni

- **Elaborazione batch:** Se hai una cartella di immagini, avvolgi la creazione di `BarCodeReader` all'interno di un ciclo che riutilizza la stessa istanza con `barcodeReader.SetImage(imagePath)`. Questo riduce l'overhead di allocazione.
- **Parallelismo:** Per carichi di lavoro elevati, considera `Parallel.ForEach` sulla lista dei file, ma ricorda che il lettore Aspose è thread‑safe solo quando ogni thread utilizza la propria istanza di `BarCodeReader`.

## Elenco completo del codice sorgente (pronto per copia‑incolla)

Di seguito trovi nuovamente l'intero programma, pronto da inserire in `Program.cs`. Non servono file aggiuntivi oltre all'immagine.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                var macro = result.Extended.Pdf417;

                Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }

        Console.WriteLine("Done. Press any key to exit...");
        Console.ReadKey();
    }
}
```

## Riepilogo: Come leggere PDF417 in C# rapidamente

- Installa **Aspose.BarCode** tramite NuGet.
- Indirizza un `BarCodeReader` verso la tua immagine con `DecodeType.MacroPdf417`.
- Itera su `ReadBarCodes()` e recupera sia i campi base che quelli estesi.
- Gestisci i dati macro mancanti in modo elegante e considera ottimizzazioni di prestazioni per scansioni di massa.

## Prossimi passi e argomenti correlati

- **Leggi il codice a barre dall'immagine** usando altri formati (QR, DataMatrix) – basta cambiare l'enum `DecodeType`.
- **Codifica PDF417** con `BarCodeGenerator` se hai bisogno di creare codici a barre programmaticamente.
- Esplora i **livelli di correzione degli errori** e come influenzano l'affidabilità della scansione.
- Integra questa logica in un'API ASP.NET Core per esporre la lettura dei codici a barre come servizio web.

Sentiti libero di sperimentare: cambia l'immagine, gioca con il flag `DecodeType`, o inserisci i dati macro in un database. Il modello di base rimane lo stesso, e ora hai un solido **esempio di lettore di codici a barre c#** nella tua cassetta degli attrezzi.

Buona programmazione, e che le tue scansioni siano sempre pulite!

## Cosa dovresti imparare dopo?

I tutorial seguenti coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API ed esplorare approcci alternativi di implementazione nei tuoi progetti.

- [Come leggere i codici DataMatrix con Aspose.BarCode per .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Come creare un codice a barre – PDF417 compatto con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Come creare la zona silenziosa del codice a barre per Code 16K usando Aspose.BarCode per .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}