---
category: general
date: 2026-08-22
description: Come leggere i codici a barre PDF417 in C# con una guida passo passo,
  che copre come leggere più codici a barre da un'immagine ed estrarre i dettagli
  MacroPdf417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcodes image c#
language: it
lastmod: 2026-08-22
og_description: Come leggere rapidamente i codici a barre PDF417 in C#. Questo tutorial
  ti mostra come leggere più codici a barre da un'immagine e recuperare le informazioni
  estese MacroPdf417.
og_image_alt: Developer console displaying MacroPdf417 barcode details extracted by
  C# code
og_title: Come leggere i codici a barre PDF417 in C# – guida completa alla programmazione
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to read PDF417 barcodes in C# with a step‑by‑step guide, covering
    how to read multiple barcodes from an image and extract MacroPdf417 details.
  headline: How to read PDF417 barcodes in C# – complete guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Come leggere i codici a barre PDF417 in C# – guida completa
url: /it/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come leggere i codici a barre PDF417 in C# – guida completa

Se hai bisogno di **come leggere PDF417** in un'applicazione .NET, questo tutorial ti fornisce una soluzione pronta all'uso. Imparerai a leggere più codici a barre da una singola immagine, estrarre l'intero set di dati MacroPdf417 e visualizzarlo nella console. L'approccio funziona con la libreria Aspose.BarCode per .NET e richiede solo poche righe di codice.

La lettura di codici a barre da un'immagine è un'operazione comune nei sistemi di inventario, nella validazione dei biglietti e nella gestione dei documenti. Alla fine di questa guida sarai in grado di decodificare qualsiasi codice a barre PDF417 o MacroPdf417, gestire più codici in un'unica immagine e comprendere i campi estesi forniti da MacroPdf417.

## Prerequisiti

- .NET 6.0 SDK o successivo (il codice si compila anche con .NET Framework 4.7+)
- Visual Studio 2022 o qualsiasi editor C# tu preferisca
- Pacchetto NuGet Aspose.BarCode per .NET (`Install-Package Aspose.BarCode`)
- Un'immagine di esempio che contenga un codice a barre MacroPdf417 (ad es., `MacroPdf417.png`)

Non è necessaria alcuna configurazione aggiuntiva; la libreria gestisce internamente il caricamento e la decodifica dell'immagine.

## Come leggere i codici a barre PDF417 da un'immagine in C#

Il cuore della soluzione è la classe `BarCodeReader`. Essa apre l'immagine, rileva tutti i codici a barre del tipo specificato e restituisce una collezione di oggetti `BarCodeResult`. Il codice seguente mostra un programma console completo.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            // Path to the image that contains one or more MacroPdf417 barcodes
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            // 1️⃣ Initialize the reader for MacroPdf417 barcodes.
            // DecodeType.MacroPdf417 tells the engine to look for the extended PDF417 format.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // 2️⃣ Iterate over every barcode found in the image.
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // 3️⃣ Print basic information.
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // 4️⃣ Access MacroPdf417 extended fields.
                    // The Extended property contains format‑specific data; for PDF417 it is .Pdf417.
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

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Perché ogni riga è importante

| Passo | Scopo |
|------|---------|
| **1️⃣ Initialize** | Crea un `BarCodeReader` associato al file immagine e limita il rilevamento alla simbologia MacroPdf417, velocizzando l'elaborazione. |
| **2️⃣ Iterate** | `ReadBarCodes()` restituisce **tutti** i codici a barre che corrispondono al tipo richiesto, consentendoti di **leggere più codici a barre** senza cicli aggiuntivi. |
| **3️⃣ Basic output** | Mostra il generico `CodeTypeName` e il `CodeText` leggibile dall’uomo. Questo è utile per il logging o per una rapida validazione. |
| **4️⃣ Extended data** | MacroPdf417 trasporta metadati aggiuntivi (ID file, conteggio segmenti, timestamp, ecc.). L'oggetto `Extended.Pdf417` espone direttamente ogni campo, così puoi memorizzare o verificare l'intero pacchetto di dati. |

Eseguire il programma su un'immagine MacroPdf417 valida produce un output in console simile al seguente:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345678
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x9A3F
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2024-07-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

L'output conferma che la libreria ha letto correttamente il codice a barre, estratto il testo e fornito tutti i campi MacroPdf417.

## Lettura di più codici a barre da un'unica immagine

Molti scenari reali posizionano diversi simboli PDF417 su un'unica etichetta—pensa a un manifesto di spedizione che contiene un codice vettore, un numero di tracciamento e una dichiarazione doganale. Il blocco di codice mostrato sopra legge già **più codici a barre** perché `ReadBarCodes()` restituisce un enumerabile di tutti i risultati. Non è necessaria alcuna configurazione aggiuntiva; basta iterare sui risultati, come dimostrato.

Se desideri limitare il lettore al PDF417 standard (non macro) mantenendo la capacità di gestire più codici, sostituisci `DecodeType.MacroPdf417` con `DecodeType.Pdf417`. Il resto della logica rimane invariato.

## Comprendere i dati estesi MacroPdf417

MacroPdf417 è un’estensione della specifica PDF417 normale. Divide grandi payload in più segmenti e aggiunge un piccolo header che descrive l’intero file. I campi più rilevanti sono:

- **MacroPdf417FileID** – un identificatore unico condiviso da tutti i segmenti dello stesso file.
- **MacroPdf417SegmentID** – il numero di sequenza del segmento corrente.
- **MacroPdf417SegmentsCount** – numero totale di segmenti attesi.
- **MacroPdf417FileName** – nome file opzionale trasmesso con il codice a barre.
- **MacroPdf417Checksum** – valore di controllo per l’intero file.
- **MacroPdf417FileSize** – dimensione del payload binario originale.
- **MacroPdf417TimeStamp** – timestamp ISO‑8601 al momento della generazione del codice a barre.
- **MacroPdf417Addressee / Sender** – campi testuali opzionali per l’instradamento.
- **MacroPdf417Terminator** – indica se questo segmento è quello finale.

Quando ricevi tutti i segmenti, puoi ricostruire il file originale ordinandoli per `MacroPdf417SegmentID` e concatenando i valori di `CodeText`. Questa logica è semplice da implementare una volta che i campi sono disponibili.

## Problemi comuni e consigli professionali

- **La qualità dell’immagine è fondamentale** – file PNG/JPEG a bassa risoluzione o fortemente compressi possono causare mancati rilevamenti. Usa almeno 300 dpi per i codici a barre stampati.
- **Simboli misti** – se l’immagine contiene sia MacroPdf417 sia PDF417 normale, istanzia due lettori (uno per ciascun `DecodeType`) oppure usa `DecodeType.AllSupported` e filtra i risultati in base a `result.CodeTypeName`.
- **Uso della memoria** – l’istruzione `using` elimina prontamente il `BarCodeReader`, evitando che grandi buffer di immagine rimangano in memoria.
- **Sicurezza dei thread** – `BarCodeReader` non è thread‑safe. Crea un’istanza separata per ogni thread se decodifichi immagini in parallelo.
- **Gestione degli errori** – avvolgi la chiamata a `ReadBarCodes()` in un blocco try/catch per catturare `BarCodeException` in caso di immagini corrotte.

## Riepilogo dell’esempio completo funzionante

Di seguito trovi il programma completo che puoi copiare in un nuovo progetto console. Include tutte le direttive `using`, una costante per il percorso dell’immagine e lo schema di disposal.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
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

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

Compila con `dotnet build` ed esegui con `dotnet run`. La console stampa i dati di base di ogni codice a barre e l’intero payload MacroPdf417.

## Prossimi passi

- **Ricostruire file multipart** – raccogli tutti i segmenti, ordina per `MacroPdf417SegmentID` e concatena `CodeText` per

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi con spiegazioni passo‑passo per aiutarti a padroneggiare ulteriori funzionalità dell’API e a esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come generare il codice a barre PDF417 – Codifica PDF417 compatta](/barcode/english/net/compact-pdf417-encoding/)
- [Come leggere i codici a barre PDF417 con caratteri turchi in Java](/barcode/english/java/multilingual-support/recognizing-pdf417-turkish-characters/)
- [Come usare Aspose per il codice a barre PDF417 (cinese) in Java](/barcode/english/java/multilingual-support/recognizing-pdf417-chinese-characters/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}