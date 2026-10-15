---
category: general
date: 2026-10-12
description: Scopri come creare un esempio di codice a barre Aspose in C# che genera
  un codice a barre MacroPdf417 con metadati completi e lo legge nuovamente usando
  BarCodeReader.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode example
- macroPdf417 barcode
- barcode metadata
- c# barcode generation
- BarCodeReader
language: it
lastmod: 2026-10-12
og_description: Esempio di barcode Aspose in C# che mostra come generare un codice
  a barre MacroPdf417 con metadati incorporati e leggerlo nuovamente usando BarCodeReader.
og_image_alt: Screenshot of an Aspose barcode example displaying a MacroPdf417 barcode
  with metadata
og_title: Crea un esempio di codice a barre Aspose con MacroPdf417 in C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn how to create an Aspose barcode example in C# that generates
    a MacroPdf417 barcode with full metadata and reads it back using BarCodeReader.
  headline: How to build an Aspose barcode example with MacroPdf417 in C#
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- Barcode
title: Come creare un esempio di codice a barre Aspose con MacroPdf417 in C#
url: /it/net/compact-pdf417-encoding/how-to-build-an-aspose-barcode-example-with-macropdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un esempio di barcode Aspose con MacroPdf417 in C#

Se ti serve un **esempio di barcode Aspose** che crea un barcode MacroPdf417 e ne legge i metadati incorporati, questa guida mostra l'intero flusso di lavoro. Vedrai come configurare il generatore, incorporare informazioni a livello di file, salvare l'immagine e quindi decodificare gli stessi dati con `BarCodeReader`.

Il tutorial copre tutto ciò che devi sapere per la **generazione di barcode C#** con Aspose.BarCode, includendo le insidie più comuni e consigli per gestire ID di file grandi o timestamp personalizzati.

## Cosa ti serve

Prima di iniziare, assicurati di avere:

* .NET 6.0 SDK o successivo (il codice funziona con .NET Core e .NET Framework)
* Visual Studio 2022 o qualsiasi IDE che supporti C#
* Una licenza attiva di Aspose.BarCode (la versione di prova gratuita è sufficiente per lo sviluppo)
* Il pacchetto NuGet `Aspose.BarCode` installato nel tuo progetto

Questi prerequisiti garantiscono che l'esempio venga eseguito senza configurazioni aggiuntive.

## Passo 1: Configurare il progetto di esempio per il barcode Aspose

Crea una nuova applicazione console e aggiungi la libreria Aspose.BarCode:

```bash
dotnet new console -n AsposeMacroPdf417Demo
cd AsposeMacroPdf417Demo
dotnet add package Aspose.BarCode
```

Il pacchetto `Aspose.BarCode` fornisce `BarcodeGenerator`, `BarCodeReader` e tutti i tipi necessari per la gestione di MacroPdf417.

### Perché questo passo è importante
Aggiungere il pacchetto NuGet risolve le enum `EncodeTypes`, `DecodeType` e `BarCodeImageFormat` usate più avanti. Senza il pacchetto, il compilatore non riconoscerebbe questi simboli e l'esempio fallirebbe in fase di build.

## Passo 2: Creare il generatore di barcode MacroPdf417

Apri **Program.cs** e sostituisci il codice di esempio con il blocco seguente. Questo blocco crea un `BarcodeGenerator` configurato per la simbologia MacroPdf417 e imposta i parametri di base dell'aspetto.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Enums;
using System;

class Program
{
    static void Main()
    {
        // Step 2.1: Initialize the generator with source text.
        using (BarcodeGenerator barcodeGenerator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample data"))
        {
            // Adjust the module size – 2 pixels per X‑dimension.
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Reduce the number of columns to keep the barcode compact.
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Step 2.2: Embed MacroPdf417 metadata.
            // ---------------------------------------------------------
            // The following properties are optional but illustrate
            // how a full‑featured barcode can carry file‑level data.
            // ---------------------------------------------------------
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp =
                new DateTime(2024, 9, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator =
                Pdf417MacroTerminator.Set;

            // Step 2.3: Save the barcode image.
            const string outPath = "ExtPDF417Meta.png";
            barcodeGenerator.Save(outPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outPath}");
        }
```

#### Spiegazione delle proprietà chiave

| Property | Scopo | Intervallo tipico / note |
|----------|-------|--------------------------|
| `MacroPdf417FileID` | Identificatore univoco per l'intero file | Deve essere ≤ 2³¹‑1 |
| `MacroPdf417SegmentID` | Indice del segmento corrente | Inizia da 0 |
| `MacroPdf417SegmentsCount` | Numero totale di segmenti nel file | Deve essere ≥ SegmentID |
| `MacroPdf417FileName` | Nome leggibile del file | Fino a 255 caratteri |
| `MacroPdf417Checksum` | Checksum CCITT‑16 del file originale | Calcolato da strumento esterno se necessario |
| `MacroPdf417FileSize` | Dimensione del file originale in byte | Utile per la validazione |
| `MacroPdf417TimeStamp` | Data/ora di creazione del file | Usa UTC per coerenza |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Informazioni di instradamento opzionali | Qualsiasi stringa fino a 255 caratteri |
| `MacroPdf417Terminator` | Contrassegna il segmento finale | Usa `Set` per l'ultimo segmento |

Questi campi costituiscono i **metadati del barcode** che il lettore potrà estrarre in seguito.

## Passo 3: Decodificare il barcode e visualizzare i metadati

Dopo aver salvato l'immagine, lo stesso programma continua aprendo il file con `BarCodeReader`. Aggiungi il codice seguente all'interno del metodo `Main`, dopo il blocco `using` precedente:

```csharp
        // Step 3: Open the saved image with a MacroPdf417 reader.
        using (BarCodeReader barcodeReader =
               new BarCodeReader("ExtPDF417Meta.png", DecodeType.MacroPdf417))
        {
            // Step 3.1: Iterate through all decoded results.
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                // The Extended property holds the MacroPdf417 specific fields.
                var meta = result.Extended.Pdf417;
                Console.WriteLine($"FileID: {meta.MacroPdf417FileID}");
                Console.WriteLine($"SegmentID: {meta.MacroPdf417SegmentID}");
                Console.WriteLine($"SegmentsCount: {meta.MacroPdf417SegmentsCount}");
                Console.WriteLine($"FileName: {meta.MacroPdf417FileName}");
                Console.WriteLine($"Checksum: {meta.MacroPdf417Checksum}");
                Console.WriteLine($"FileSize: {meta.MacroPdf417FileSize}");
                Console.WriteLine($"Timestamp: {meta.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee: {meta.MacroPdf417Addressee}");
                Console.WriteLine($"Sender: {meta.MacroPdf417Sender}");
                Console.WriteLine($"Terminator: {meta.MacroPdf417Terminator}");
            }
        }
    }
}
```

### Perché è importante leggere nuovamente
Il `BarCodeReader` verifica che i metadati incorporati siano codificati correttamente. Se qualche proprietà manca o è fuori intervallo, il lettore restituisce `null` per quel campo, permettendoti di gestire gli errori in modo elegante.

## Passo 4: Eseguire e verificare l'output

Esegui il programma:

```bash
dotnet run
```

Dovresti vedere un output console simile a:

```
Barcode saved to ExtPDF417Meta.png
FileID: 12345678
SegmentID: 12
SegmentsCount: 20
FileName: file01
Checksum: 1234
FileSize: 400000
Timestamp: 9/1/2024 12:00:00 AM
Addressee: street
Sender: aspose
Terminator: Set
```

Se i valori corrispondono a quelli impostati nel Passo 2, l'**esempio di barcode Aspose** funziona come previsto.

## Casi limite e consigli di best‑practice

| Situazione | Cosa controllare | Gestione consigliata |
|------------|------------------|----------------------|
| **FileID supera il range a 32 bit** | Aspose genera `ArgumentOutOfRangeException`. | Mantieni l'ID ≤ 2 147 483 647 o suddividi il file in più blocchi MacroPdf417. |
| **Timestamp in ora locale** | I lettori in altri fusi orari potrebbero interpretare erroneamente il valore. | Memorizza i timestamp in UTC (`DateTime.UtcNow`) e convertili in visualizzazione se necessario. |
| **Dimensione file grande** | `MacroPdf417FileSize` è un `int`; valori > 2 GB provocano overflow. | Usa un campo personalizzato o suddividi il file in segmenti più piccoli. |
| **Segmento mancante** | Se `SegmentID` non è sequenziale, la ricostruzione fallisce. | Convalida l'ordine dei segmenti prima della codifica o utilizza impostazioni di correzione d'errore. |
| **Formato immagine non supportato** | Salvare come BMP può aumentare notevolmente le dimensioni. | PNG è una buona impostazione predefinita; JPEG può essere usato se accetti compressione con perdita. |

**Suggerimento professionale:** quando generi molti barcode in batch, riutilizza una singola istanza di `BarcodeGenerator` e modifica solo `EncodeTypes` e il testo sorgente. Questo riduce le allocazioni di memoria e velocizza l'elaborazione.

## Argomenti correlati da esplorare

* **Altre simbologie macro** – Aspose supporta anche MacroPdf417 con livelli di correzione d'errore.
* **Incorporare barcode in PDF** – Combina `Aspose.PDF` con il generatore di barcode per produrre documenti stampabili.
* **Integrazione ASP.NET Core** – Servi i barcode generati direttamente da un'API web.
* **Scansione tramite dispositivi mobili** – Usa l'SDK `Aspose.BarCode.Cloud` per la decodifica cross‑platform.

Questi argomenti di approfondimento estendono naturalmente l'**esempio di barcode Aspose** e approfondiscono la tua competenza nella **generazione di barcode C#**.

## Conclusione

Ora disponi di un **esempio di barcode Aspose** completamente funzionante che crea un barcode MacroPdf417, incorpora ricchi **metadati del barcode**, salva l'immagine e legge i dati indietro con `BarCodeReader`. Seguendo i passaggi sopra, potrai adattare il codice a diversi ID file, timestamp o persino ad altri tipi di barcode supportati da Aspose.

Sentiti libero di sperimentare con campi di metadati aggiuntivi, cambiare il formato immagine o integrare il generatore in un'applicazione più ampia. Buon coding!

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}