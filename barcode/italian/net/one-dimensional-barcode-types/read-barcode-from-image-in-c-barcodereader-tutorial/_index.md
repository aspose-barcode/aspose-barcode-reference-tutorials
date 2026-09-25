---
category: general
date: 2026-08-15
description: Leggi il codice a barre da un'immagine in C# usando BarCodeReader. Scopri
  come leggere più codici a barre in C#, leggere il codice a barre PDF417 e vedere
  un esempio completo di BarCodeReader in C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image
- read multiple barcodes c#
- how to read pdf417 barcode
- c# barcodereader example
language: it
lastmod: 2026-08-15
og_description: Leggi il codice a barre da un'immagine in C# con una guida passo passo.
  Scopri come leggere più codici a barre in C#, decodificare i simboli PDF417 e eseguire
  un esempio completo di BarCodeReader in C#.
og_image_alt: Screenshot of C# code that reads barcode from image using BarCodeReader
og_title: Leggi il codice a barre da un'immagine in C# – tutorial BarCodeReader
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Read barcode from image in C# using BarCodeReader. Learn how to read
    multiple barcodes C#, read PDF417 barcode, and see a full C# BarCodeReader example.
  headline: Read barcode from image in C# – BarCodeReader tutorial
  type: TechArticle
tags:
- barcode
- C#
- .NET
- image processing
title: Leggi il codice a barre da un'immagine in C# – tutorial BarCodeReader
url: /it/net/one-dimensional-barcode-types/read-barcode-from-image-in-c-barcodereader-tutorial/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Leggi il codice a barre da un'immagine in C# – tutorial BarCodeReader

Se devi **leggere un codice a barre da un'immagine** in un'applicazione .NET, questa guida ti mostra esattamente come farlo con la classe `BarCodeReader`. Vedrai anche come **leggere più codici a barre C#**, decodificare un simbolo PDF417 e ottenere un **esempio completo di C# BarCodeReader** da copiare nel tuo progetto.

Il tutorial copre ogni passaggio—dall'aggiunta del pacchetto NuGet necessario alla stampa dei campi PDF417 estesi—così terminerai con un programma console eseguibile. Non è necessaria alcuna documentazione esterna; tutto il codice e le spiegazioni sono inclusi.

## Cosa ti servirà

Prima di iniziare, assicurati di avere:

* .NET 6.0 SDK o successivo (il codice funziona con .NET Core e .NET Framework)
* Visual Studio 2022 o qualsiasi editor compatibile con C#
* Il pacchetto NuGet `Aspose.BarCode` (o la libreria equivalente che fornisce `BarCodeReader`)
* Un file immagine che contenga un codice a barre Macro PDF417 (ad es., `ExtPDF417Meta.png`)

Avere questi prerequisiti garantisce che il campione si compili senza configurazioni aggiuntive.

## Leggi il codice a barre da un'immagine con BarCodeReader

Il primo passo è creare un'istanza di `BarCodeReader` che punti al file immagine e indichi alla libreria quale tipo di codice a barre cercare.

```csharp
using System;
using Aspose.BarCode;               // Namespace for BarCodeReader
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // Path to the image that holds the Macro PDF417 barcode
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417 barcodes only
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Read all barcodes present in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Basic barcode information
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");

                // Extended Macro PDF417 fields (available only for this type)
                Console.WriteLine($"File ID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name        : {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum         : {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Time Stamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee        : {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender           : {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator Flag  : {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**Perché funziona:**  
`BarCodeReader` apre l'immagine, esegue la scansione per il `DecodeType` specificato e restituisce una collezione di oggetti `BarCodeResult`. Ogni risultato contiene i dati generici del codice a barre (`CodeTypeName`, `CodeText`) e, per Macro PDF417, un oggetto `Extended.Pdf417` che espone tutti i campi aggiuntivi definiti dallo standard.

## Leggi più codici a barre C# in una singola immagine

A volte un'immagine contiene più di un codice a barre (ad es., un QR code accanto a un PDF417). Per gestire questo scenario, basta omettere il `DecodeType` esplicito o passare `DecodeType.AllSupported` e iterare sui risultati.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Found {result.CodeTypeName}: {result.CodeText}");
    }
}
```

**Perché ti serve:**  
Specificare `AllSupported` indica al motore di provare tutti i formati di codice a barre noti, garantendo che tu catturi ogni simbolo presente nell'immagine. Questo è l'approccio consigliato quando non è possibile prevedere in anticipo i tipi di codice a barre.

## Come leggere un codice a barre PDF417 usando C#

Se ti interessa solo il formato PDF417 classico (non macro), cambia il `DecodeType` in `Pdf417`. Il resto del codice rimane identico, tranne per il fatto che i campi estesi non sono disponibili.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"PDF417 text: {result.CodeText}");
    }
}
```

**Perché è importante:**  
Il PDF417 classico non espone le proprietà specifiche del macro, quindi il blocco `Extended.Pdf417` è superfluo. Utilizzare il `DecodeType` preciso velocizza anche la scansione perché la libreria salta gli algoritmi non supportati.

## Esempio completo di C# BarCodeReader che puoi copiare

Di seguito trovi il programma completo che combina i tre scenari in una singola applicazione console facile da eseguire. Sostituisci `YOUR_DIRECTORY/ExtPDF417Meta.png` con il percorso reale della tua immagine.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 1️⃣ Read Macro PDF417 and show extended fields
        Console.WriteLine("=== Macro PDF417 ===");
        ReadMacroPdf417(imagePath);

        // 2️⃣ Read any barcode type present (multiple barcodes)
        Console.WriteLine("\n=== All supported barcodes ===");
        ReadAllBarcodes(imagePath);

        // 3️⃣ Read classic PDF417 only
        Console.WriteLine("\n=== Classic PDF417 ===");
        ReadClassicPdf417(imagePath);
    }

    static void ReadMacroPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");
                Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                // ... other extended fields omitted for brevity
                Console.WriteLine(new string('-', 30));
            }
        }
    }

    static void ReadAllBarcodes(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.AllSupported))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"{result.CodeTypeName}: {result.CodeText}");
            }
        }
    }

    static void ReadClassicPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.Pdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"PDF417 text: {result.CodeText}");
            }
        }
    }
}
```

### Output previsto

Quando l'immagine di esempio contiene un codice a barre Macro PDF417, la console stampa qualcosa di simile a:

```
=== Macro PDF417 ===
Code Type : MacroPdf417
Code Text : 1234567890
File ID   : 5
Segment ID       : 2
Segments Count   : 3
File Name        : report.pdf
Checksum         : 0x1A2B
File Size        : 84212
Time Stamp       : 2024-03-15T10:22:31Z
Addressee        : John Doe
Sender           : Acme Corp
Terminator Flag  : True
------------------------------

=== All supported barcodes ===
MacroPdf417: 1234567890
QrCode: https://example.com

=== Classic PDF417 ===
PDF417 text: 0987654321
```

Se l'immagine contiene solo un PDF417 normale, la sezione “Macro PDF417” sarà vuota e la sezione “Classic PDF417” mostrerà il testo decodificato.

## Conclusione

Ora sai come **leggere un codice a barre da un'immagine** in C# usando `BarCodeReader`, come **leggere più codici a barre C#** in un unico file, e i passaggi esatti per **leggere un codice a barre PDF417**—sia nella variante macro che classica. L'intero **esempio C# BarCodeReader** è pronto per essere incollato in qualsiasi progetto .NET, e puoi estenderlo per gestire altri formati o integrarlo in una pipeline di elaborazione immagini più ampia.

**Passi successivi**

* Esplora i pattern di gestione degli errori come `try / catch` attorno al blocco reader.  
* Sperimenta con l'oggetto `ReaderParameters` per ottimizzare velocità e precisione di rilevamento.  
* Combina la lettura dei codici a barre con librerie di pre‑elaborazione immagini (

## Cosa dovresti imparare dopo?


I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API e a esplorare approcci di implementazione alternativi nei tuoi progetti.

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Read DataMatrix barcode C# – Generate DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Read Barcode from Image – Mastering Barcode Region Extraction in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}