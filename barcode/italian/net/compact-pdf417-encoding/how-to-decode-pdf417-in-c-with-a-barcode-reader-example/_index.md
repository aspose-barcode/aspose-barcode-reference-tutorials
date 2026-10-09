---
category: general
date: 2026-09-19
description: Come decodificare PDF417 in C# – impara a leggere i codici a barre da
  un'immagine usando un esempio conciso di lettore di codici a barre che estrae i
  dati completi di Macro PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcodes from image
- decode pdf417 barcode
- c# barcode reader example
language: it
lastmod: 2026-09-19
og_description: Come decodificare PDF417 in C# con un esempio di lettore di codici
  a barre passo‑passo. Estrai ogni campo Macro PDF417 da un'immagine in pochi secondi.
og_image_alt: Screenshot showing how to decode PDF417 in C# using a barcode reader
og_title: Come decodificare PDF417 in C# – guida completa al lettore di codici a barre
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to decode PDF417 in C# – learn to read barcodes from image using
    a concise barcode reader example that extracts full Macro PDF417 data.
  headline: How to decode PDF417 in C# with a barcode reader example
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Come decodificare PDF417 in C# con un esempio di lettore di codici a barre
url: /it/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come decodificare PDF417 in C# con un esempio di lettore di codici a barre

Se hai bisogno di decodificare PDF417 in C#, questa guida ti mostra esattamente come decodificare PDF417 da un file immagine. Imparerai a leggere i codici a barre dall’immagine, accedere ai campi Macro PDF417 estesi e integrare la soluzione in qualsiasi progetto .NET.

La decodifica dei codici a barre PDF417 è comune nella logistica, nei biglietti e nella verifica dell’identità. Questo tutorial copre tutto il necessario per un’implementazione pronta per la produzione, incluse le librerie prerequisito, il codice sorgente completo e consigli per gestire i casi limite.

## Prerequisiti

Prima di iniziare, assicurati di avere:

- .NET 6.0 o successivo installato  
- Visual Studio 2022 (o qualsiasi IDE che supporti C#)  
- Il pacchetto NuGet **Aspose.BarCode for .NET** (versione 23.11 o più recente)  

Puoi aggiungere il pacchetto con il seguente comando:

```bash
dotnet add package Aspose.BarCode
```

La classe `BarCodeReader` di questa libreria supporta il tipo di decodifica `MacroPdf417` necessario per l’estrazione completa di PDF417.

## Passo 1: Come decodificare PDF417 in C# – inizializzare il lettore

Il primo passo crea un’istanza di `BarCodeReader` che punta a un’immagine Macro PDF417. Il flag `DecodeType.MacroPdf417` indica alla libreria di analizzare i campi Macro estesi.

```csharp
using System;
using Aspose.BarCode;               // Core barcode classes
using Aspose.BarCode.BarCodeRecognition; // Reader and result types

// Path to the Macro PDF417 image
string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

// Initialise the reader for Macro PDF417 decoding
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Continue with step 2...
```

**Perché è importante:** Inizializzare con `MacroPdf417` abilita la proprietà `Extended.Pdf417` su ogni `BarCodeResult`, fornendoti l’accesso ai metadati a livello di file come ID segmento e timestamp.

## Passo 2: Leggere i codici a barre dall’immagine

Un’immagine PDF417 può contenere più segmenti macro. Il metodo `ReadBarCodes()` restituisce un enumerabile di tutti i codici a barre rilevati, così da poterli scorrere in modo sicuro.

```csharp
    // Step 2: Read every barcode present in the image
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // Continue with step 3...
```

**Suggerimento:** Se ti aspetti un solo codice a barre, puoi interrompere il ciclo dopo la prima iterazione, ma iterare su tutti i risultati garantisce di catturare ogni segmento in documenti multi‑pagina.

## Passo 3: Decodificare il codice a barre PDF417 – estrarre dati di base ed estesi

All’interno del ciclo, stampa sia le informazioni generiche del codice a barre sia i campi specifici della Macro. L’oggetto `Extended.Pdf417` contiene tutti i metadati definiti dallo standard PDF417.

```csharp
        // Basic barcode information
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");

        // Macro PDF417 extended data
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

**Spiegazione dei campi chiave**

| Campo | Significato |
|-------|-------------|
| `MacroPdf417FileID` | Identificatore che raggruppa tutti i segmenti appartenenti allo stesso file logico |
| `MacroPdf417SegmentID` | Indice del segmento corrente (parte da 0) |
| `MacroPdf417SegmentsCount` | Numero totale di segmenti attesi per il file |
| `MacroPdf417FileName` | Nome file opzionale incorporato nella macro |
| `MacroPdf417Checksum` | Checksum CRC‑16 per l’integrità dei dati |
| `MacroPdf417FileSize` | Dimensione originale del file in byte |
| `MacroPdf417TimeStamp` | Timestamp di generazione della macro |
| `MacroPdf417Addressee` | Destinatario previsto dei dati macro |
| `MacroPdf417Sender` | Mittente dei dati macro |
| `MacroPdf417Terminator` | Flag booleano che indica il segmento finale |

Avere accesso a questi campi ti consente di ricostruire il documento originale, verificare l’integrità o instradare i dati in base alle informazioni di mittente/ricevente.

## Passo 4: Esempio completo di lettore di codici a barre C# – metti tutto insieme

Di seguito trovi il programma completo, eseguibile. Sostituisci `YOUR_DIRECTORY` con la cartella che contiene il tuo file `MacroPdf417.png`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417Decoder
{
    class Program
    {
        static void Main()
        {
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            // Initialise the reader for Macro PDF417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate through all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic information
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // Extended Macro PDF417 data
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

            Console.WriteLine("Decoding complete.");
        }
    }
}
```

**Output console previsto (esempio)**

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 452312
Pdf417MacroTimeStamp: 2024-03-15T14:27:00Z
Pdf417MacroAddressee: LogisticsDept
Pdf417MacroSender: Warehouse01
MacroPdf417Terminator: False
----------------------------------------
Decoding complete.
```

I valori esatti varieranno in base al contenuto del tuo codice a barre Macro PDF417.

## Gestione dei casi limite più comuni

| Situazione | Approccio consigliato |
|------------|-----------------------|
| **Nessun codice a barre rilevato** | Verifica il percorso dell’immagine, assicurati che il file non sia corrotto e conferma che il codice a barre sia visibile (contrasto adeguato). |
| **Segmenti macro parziali** | Usa `MacroPdf417SegmentsCount` per individuare parti mancanti. Puoi richiedere i segmenti rimanenti al sistema sorgente e rieseguire il decoder. |
| **Immagini grandi che causano pressione sulla memoria** | Carica l’immagine in un `System.Drawing.Bitmap` con risoluzione ridotta prima di passarla a `BarCodeReader`. |
| **PDF417 non‑Macro** | Cambia `DecodeType.MacroPdf417` in `DecodeType.Pdf417` se ti serve solo il testo semplice del codice a barre. |

## Pro tip

- **Elaborazione batch:** Avvolgi la logica del lettore in un metodo che accetta un elenco di percorsi file. Riutilizza una singola istanza di `BarCodeReader` per thread per ridurre l’overhead di allocazione.  
- **Prestazioni:** Per scenari ad alto volume, abilita la proprietà `ReaderOptions` `ReadQuality` per bilanciare velocità e accuratezza.  
- **Sicurezza:** Convalida `CodeText` prima di usarlo in operazioni sul file system per prevenire attacchi di traversal dei percorsi.

## Conclusione

In questo tutorial hai imparato a decodificare PDF417 in C# leggendo i codici a barre da un’immagine, estraendo ogni campo Macro PDF417 e costruendo un esempio completo di lettore di codici a barre C#. La soluzione funziona con l’ultima versione della libreria Aspose.BarCode, gestisce macro a più segmenti e fornisce indicazioni pratiche per progetti reali.

Successivamente, esplora argomenti correlati come **lettura di QR code**, **elaborazione batch di codici a barre** e **generazione di codici a barre PDF417** per ampliare il tuo toolkit di automazione documentale. Sentiti libero di sperimentare con diverse fonti di immagine, integrare il codice in servizi ASP.NET o estenderlo per memorizzare i metadati estratti in un database. Buona programmazione!

## Cosa dovresti imparare dopo?


I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [How to Read PDF417 in C# – Complete Barcode Reader Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Read barcode from image – C# barcode reader example](/barcode/english/net/one-dimensional-barcode-types/read-barcode-from-image-c-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}