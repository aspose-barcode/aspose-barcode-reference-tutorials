---
category: general
date: 2026-07-27
description: Come leggere rapidamente il codice a barre PDF417 in C#. Impara a leggere
  più codici a barre, decodificare immagini e ottenere i metadati Macro PDF417 in
  un esempio completo di codice a barre C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- c# barcode example
- read barcode image c#
language: it
lastmod: 2026-07-27
og_description: Come leggere il codice a barre PDF417 in C# con questa guida passo‑passo.
  Decodifica immagini, gestisci più codici a barre ed estrai i metadati Macro PDF417
  in un esempio pronto all'uso.
og_image_alt: Screenshot showing how to read PDF417 barcode using C# code
og_title: Come leggere PDF417 in C# – Esempio completo di codice a barre
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  headline: How to Read PDF417 in C# – Complete Barcode Example
  type: TechArticle
- description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  name: How to Read PDF417 in C# – Complete Barcode Example
  steps:
  - name: Loads a barcode image from disk.
    text: Loads a barcode image from disk.
  - name: Decodes **PDF417** (including Macro PDF417) barcodes.
    text: Decodes **PDF417** (including Macro PDF417) barcodes.
  - name: Prints basic information such as code type and text.
    text: Prints basic information such as code type and text.
  - name: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
    text: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image-processing
- Aspose
title: Come leggere PDF417 in C# – Esempio completo di codice a barre
url: /it/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come leggere PDF417 in C# – Esempio completo di barcode

Ti sei mai chiesto **come leggere un barcode PDF417** in un'applicazione C# senza impazzire? Non sei l'unico. Che tu stia costruendo uno scanner logistico, un validatore di biglietti, o semplicemente abbia bisogno di estrarre dati da un documento d'identità codificato in PDF417, il processo può sembrare un po' misterioso all'inizio.  

In questo tutorial vedremo un **esempio di barcode c#** che legge un'immagine PDF417, gestisce **la lettura di più barcode** se presenti, ed estrae tutti i pratici metadati Macro PDF417 di cui potresti aver bisogno.

## Cosa costruirai

Alla fine di questa guida avrai un piccolo programma console che:

1. Carica un'immagine di barcode dal disco.  
2. Decodifica i barcode **PDF417** (inclusi i Macro PDF417).  
3. Stampa informazioni di base come tipo di codice e testo.  
4. Restituisce l'intero set di campi Macro PDF417 (ID file, ID segmento, checksum, ecc.).  

Nessun servizio esterno, solo un singolo pacchetto NuGet e poche righe di C#.

## Prerequisiti – Cosa ti serve prima di iniziare

- **.NET 6.0** o versioni successive (il codice funziona anche su .NET Framework 4.6+).  
- Una versione recente della libreria **Aspose.BarCode for .NET** – installala tramite NuGet (`Install-Package Aspose.BarCode`).  
- Un file immagine che contiene un barcode PDF417 (la demo utilizza `ExtPDF417Meta.png`).  
- Una conoscenza di base delle app console C# (se hai scritto “Hello World”, sei a posto).

> **Consiglio professionale:** Se non hai a disposizione un campione PDF417, generane uno sul sito demo di Aspose o utilizza un'app per smartphone che può creare tag PDF417.

## Passo 1: Configura il progetto e installa la libreria

Per prima cosa, crea un nuovo progetto console:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
dotnet add package Aspose.BarCode
```

Questo aggiunge le dipendenze dell'**esempio di barcode c#** di cui abbiamo bisogno. Apri `Program.cs` e sostituisci il codice predefinito con lo scheletro qui sotto:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll fill this in in the next steps.
        }
    }
}
```

## Passo 2: Inizializza il Barcode Reader per PDF417

Il cuore della soluzione è la classe `BarCodeReader`. Le indichiamo quale file scansionare e quale tipo di barcode ci interessa — in questo caso `DecodeType.Pdf417` o la variante macro `DecodeType.MacroPdf417`. Usare il tipo macro garantisce di catturare i campi estesi.

```csharp
// Step 2: Create the reader, targeting Macro PDF417 barcodes
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(
           imagePath, DecodeType.MacroPdf417))
{
    // The rest of the logic lives inside this block.
}
```

Perché usare `MacroPdf417` invece di `Pdf417` semplice? Macro PDF417 contiene metadati aggiuntivi (ID file, conteggio segmenti, timestamp, ecc.) su cui molte applicazioni reali si basano — pensa ai manifesti di spedizione suddivisi su più pagine.

## Passo 3: Leggi tutti i barcode trovati nell'immagine

Un'unica immagine può contenere **più barcode** — magari un QR code accanto a un PDF417. Il metodo `ReadBarCodes()` restituisce un `IEnumerable<BarCodeResult>` che possiamo iterare.

```csharp
// Step 3: Iterate through every barcode detected
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Inside we’ll output both generic and macro‑specific data.
}
```

Se l'immagine contiene solo un PDF417, il ciclo verrà comunque eseguito una volta, mantenendo il codice flessibile per scenari futuri in cui potresti **leggere più barcode** dalla stessa scansione.

## Passo 4: Visualizza le informazioni di base del barcode

Prima di approfondire i campi macro, è utile mostrare il tipo di barcode e il testo decodificato. Questo ti aiuta a verificare che il lettore abbia effettivamente riconosciuto un PDF417 e non un'altra simbologia.

```csharp
Console.WriteLine($"CodeType : {result.CodeTypeName}");
Console.WriteLine($"CodeText : {result.CodeText}");
```

`CodeTypeName` restituirà *MacroPdf417* (o *Pdf417* se il flag macro non è impostato), mentre `CodeText` contiene i dati grezzi codificati nel barcode.

## Passo 5: Estrai i metadati Macro PDF417

La proprietà `Extended` ti offre un'analisi approfondita della struttura specifica del PDF417. Ogni campo che stampiamo di seguito corrisponde direttamente alla specifica macro del PDF417.

```csharp
// Step 5: Macro PDF417 metadata – all optional, but very handy
Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
```

Ogni riga estrae una diversa parte del payload macro:

- **FileID** – un identificatore unico per l'intero set di documenti.  
- **SegmentID** – quale parte del file multi‑segmento stai visualizzando.  
- **SegmentsCount** – numero totale di segmenti previsto.  
- **FileName, Checksum, FileSize** – utili per convalidare l'integrità del file trasferito.  
- **TimeStamp, Addressee, Sender** – campi opzionali che molti sistemi logistici incorporano.  

Se uno di questi campi è assente nel barcode di origine, la libreria restituisce `null` o `0`, che puoi gestire secondo necessità.

## Passo 6: Esegui l'esempio completo

Mettendo tutto insieme, ecco il programma completo, pronto per l'esecuzione:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the reader for Macro PDF417 (covers both standard and macro)
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Loop through every barcode detected – handles read multiple barcodes gracefully
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic info
                    Console.WriteLine($"CodeType : {result.CodeTypeName}");
                    Console.WriteLine($"CodeText : {result.CodeText}");

                    // Macro PDF417 specific metadata
                    Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding complete. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Output previsto

Quando esegui il programma su un valido `ExtPDF417Meta.png`, dovresti vedere qualcosa di simile a:

```
CodeType : MacroPdf417
CodeText : https://example.com/track?order=12345
Pdf417MacroFileID          : 101
Pdf417MacroSegmentID       : 1
Pdf417MacroSegmentsCount   : 3
Pdf417MacroFileName        : order_manifest.pdf
Pdf417MacroChecksum        : 0x1A2B3C4D
Pdf417MacroFileSize        : 45296
Pdf417MacroTimeStamp       : 2024-03-15T10:27:00Z
Pdf417MacroAddressee       : LogisticsDept
Pdf417MacroSender          : WarehouseA
MacroPdf417Terminator      : true
----------------------------------------
Decoding complete. Press any key to exit.
```

Se l'immagine contiene più di un barcode,

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come generare barcode PDF417 – Codifica PDF417 compatta](/barcode/english/net/compact-pdf417-encoding/)
- [Come creare barcode – PDF417 compatto con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Come leggere barcode DataMatrix con Aspose.BarCode per .NET](/barcode/english/net/datamatrix-barcode-reading/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}