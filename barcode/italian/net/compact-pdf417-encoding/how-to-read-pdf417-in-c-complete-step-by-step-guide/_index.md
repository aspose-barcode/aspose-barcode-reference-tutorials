---
category: general
date: 2026-07-15
description: Come leggere il codice a barre PDF417 in C# e leggere più codici a barre
  da un'immagine. Impara a leggere immagini di codici a barre in C# con codice dettagliato
  e consigli.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcode image c#
- Aspose.BarCode PDF417
- C# barcode decoding
language: it
lastmod: 2026-07-15
og_description: Come leggere rapidamente il codice a barre PDF417 in C#. Questa guida
  ti mostra come leggere più codici a barre da un'unica immagine e decodificare ogni
  proprietà.
og_image_alt: Screenshot of C# console output displaying PDF417 barcode details
og_title: Come leggere PDF417 in C# – Esempio di codice completo e spiegazione
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: How to read PDF417 barcode in C# and read multiple barcodes from an
    image. Learn to read barcode image C# with detailed code and tips.
  headline: How to Read PDF417 in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: How to read PDF417 barcode in C# and read multiple barcodes from an
    image. Learn to read barcode image C# with detailed code and tips.
  name: How to Read PDF417 in C# – Complete Step‑by‑Step Guide
  steps:
  - name: Why This Code Works
    text: '* **`BarCodeReader`** is the core class that streams the image, detects
      barcodes, and returns a collection of `BarCodeResult` objects. * Passing **`DecodeType.MacroPdf417`**
      tells the library to treat Macro‑PDF417 specially; it still returns plain PDF417
      symbols, which satisfies the **read multiple '
  - name: What if the image has both Macro‑PDF417 and regular PDF417 symbols?
    text: The same `BarCodeReader` call will return both. You can differentiate them
      by checking `result.CodeType` (`MacroPdf417` vs `Pdf417`). The extended properties
      will be `null` for a plain PDF417, so the `if (macro != null)` guard prevents
      a `NullReferenceException`.
  - name: My barcode is rotated or skewed—will the reader still work?
    text: Aspose.BarCode includes built‑in rotation and distortion compensation. As
      long as the barcode is at least 30 % of the image width, the decoder will usually
      succeed. For extreme cases you can enable `reader.Options.AllowInvertedBarcodes
      = true;` before calling `ReadBarCodes()`.
  - name: How do I handle large batches of images?
    text: Wrap the reading logic in a `foreach (var file in Directory.GetFiles(folder,
      "*.png"))` loop. The `using` pattern ensures each image’s native resources are
      freed before the next iteration, keeping memory usage low.
  type: HowTo
tags:
- C#
- barcode
- PDF417
- Aspose
title: Come leggere PDF417 in C# – Guida completa passo‑passo
url: /it/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come leggere PDF417 in C# – Guida completa passo‑passo

Ti sei mai chiesto **come leggere PDF417** da un'immagine usando C#? Non sei l'unico. La maggior parte degli sviluppatori si imbatte in un ostacolo quando deve estrarre i campi Macro‑PDF417 estesi da un documento scansionato. La buona notizia? Con poche righe di codice puoi decodificare un PDF417, leggere più codici a barre nella stessa immagine e ottenere tutte le proprietà nascoste offerte dalla specifica.

In questo tutorial percorreremo un esempio reale che mostra **come leggere PDF417**, come **leggere più codici a barre** da un unico file e perché il codice **read barcode image C#** appare così. Alla fine avrai un'app console pronta all'uso che stampa ogni informazione di cui potresti aver bisogno — ID file, ID segmento, checksum, timestamp, quello che vuoi.

## Prerequisiti

* .NET 6.0 SDK o versioni successive (il codice funziona anche con .NET Core e .NET Framework).  
* Visual Studio 2022 (o qualsiasi editor tu preferisca).  
* Il pacchetto NuGet **Aspose.BarCode for .NET** – è la libreria che effettivamente analizza PDF417.  
* Un'immagine di esempio che contiene un codice a barre Macro‑PDF417 (ad esempio `ExtPDF417Meta.png`).  

Non è necessaria alcuna configurazione aggiuntiva; la libreria include tutti i decoder di cui hai bisogno.

## Passo 1: Installa Aspose.BarCode

Apri la cartella del tuo progetto in un terminale ed esegui:

```bash
dotnet add package Aspose.BarCode
```

Quel comando scarica l'ultima versione stabile (a luglio 2026 è la 23.12). Se preferisci la Package Manager Console di Visual Studio, usa:

```powershell
Install-Package Aspose.BarCode
```

> **Suggerimento:** blocca la versione (`23.12.0`) nel tuo file `.csproj` per evitare modifiche incompatibili accidentali in futuro.

## Passo 2: Crea lo scheletro di un'app console

Crea un nuovo progetto console se non ne hai già uno:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Sostituisci il file `Program.cs` generato automaticamente con il codice qui sotto. Spiegheremo ogni blocco nelle sezioni successive.

## Passo 3: Scrivi il codice completo “Come leggere PDF417”

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
            // -----------------------------------------------------------------
            // 1️⃣  Set the path to the image that contains one or more PDF417 codes
            // -----------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarCodeReader for MacroPdf417 decoding
            // -----------------------------------------------------------------
            // The DecodeType flag tells Aspose to look specifically for Macro‑PDF417,
            // but it will also pick up plain PDF417 symbols that happen to be in the
            // same image – perfect for the “read multiple barcodes” scenario.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // -----------------------------------------------------------------
                // 3️⃣  Iterate over every barcode found in the image
                // -----------------------------------------------------------------
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // -------------------------------------------------------------
                    // 4️⃣  Basic barcode information – works for any barcode type
                    // -------------------------------------------------------------
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // -------------------------------------------------------------
                    // 5️⃣  Macro‑PDF417 extended properties (the real reason you’re here)
                    // -------------------------------------------------------------
                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40)); // visual separator
                }
            }

            // -----------------------------------------------------------------
            // 6️⃣  Keep the console window open when running from VS
            // -----------------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

### Perché questo codice funziona

* **`BarCodeReader`** è la classe principale che elabora l'immagine, rileva i codici a barre e restituisce una collezione di oggetti `BarCodeResult`.  
* Passare **`DecodeType.MacroPdf417`** indica alla libreria di trattare Macro‑PDF417 in modo speciale; restituisce comunque simboli PDF417 semplici, soddisfacendo il requisito di **read multiple barcodes**.  
* L'oggetto **`Extended.Pdf417.MacroPdf417`** contiene tutti i campi opzionali definiti dallo standard ISO/IEC 15438 – è qui che trovi `FileID`, `SegmentID`, `Checksum`, ecc.  
* Il blocco `using` garantisce il rilascio delle risorse native, evitando perdite di memoria in servizi a lungo termine.

## Passo 4: Esegui l'applicazione e verifica l'output

Dal terminale:

```bash
dotnet run
```

Dovresti vedere qualcosa di simile:

```
Code Type : MacroPdf417
Code Text : 1234567890...
File ID          : 12
Segment ID       : 1
Segments Count   : 3
File Name        : invoice2024.pdf
Checksum         : 9A3F
File Size        : 245760
Time Stamp       : 2024-11-02T14:23:00Z
Addressee        : Acme Corp
Sender           : Logistics Dept
Terminator       : 1
----------------------------------------
Done. Press any key to exit...
```

Se l'immagine contiene più di un codice a barre, il ciclo stamperà una linea di separazione (`----------------------------------------`) e continuerà con il risultato successivo — esattamente ciò che **read multiple barcodes** appare nella pratica.

## Domande comuni e casi particolari

### E se l'immagine contiene sia simboli Macro‑PDF417 sia PDF417 regolari?

La stessa chiamata `BarCodeReader` restituirà entrambi. Puoi differenziarli controllando `result.CodeType` (`MacroPdf417` vs `Pdf417`). Le proprietà estese saranno `null` per un PDF417 semplice, quindi la guardia `if (macro != null)` evita una `NullReferenceException`.

### Il mio codice a barre è ruotato o inclinato — il lettore funzionerà comunque?

Aspose.BarCode include una compensazione integrata per rotazione e distorsione. Finché il codice a barre occupa almeno il 30 % della larghezza dell'immagine, il decoder di solito riesce. Per casi estremi puoi abilitare `reader.Options.AllowInvertedBarcodes = true;` prima di chiamare `ReadBarCodes()`.

### Come gestire grandi lotti di immagini?

Avvolgi la logica di lettura in un ciclo `foreach (var file in Directory.GetFiles(folder, "*.png"))`. Il pattern `using` garantisce che le risorse native di ogni immagine vengano rilasciate prima dell'iterazione successiva, mantenendo basso l'uso di memoria.

## Elenco completo del codice sorgente (pronto per copia‑incolla)

Di seguito trovi l'intero programma in un unico blocco per una rapida copia‑incolla. Nessuna dipendenza nascosta — solo il pacchetto NuGet Aspose.BarCode.

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
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

## Riepilogo – Cosa abbiamo coperto

* **Come leggere PDF417** usando Aspose.BarCode in C#.  
* I passaggi esatti per **leggere più codici a barre** da una singola immagine.  
* Come **read barcode image C#** e estrarre ogni campo Macro‑PDF417.  
* Suggerimenti per rotazione, elaborazione batch e gestione dei dati estesi mancanti.

## Prossimi passi e argomenti correlati

* **Encode PDF417** – genera i tuoi codici a barre Macro‑PDF417 con `BarCodeBuilder`.  
* **Read other 2‑D symbologies** – QR, DataMatrix, Aztec – usando la stessa classe `BarCodeReader`.  
* **Integrate with ASP.NET Core** – espone un endpoint web che accetta un'immagine caricata e restituisce JSON con i campi decodificati.  

Sentiti libero di sperimentare: cambia il percorso dell'immagine, inserisci un PDF417 semplice nella stessa cartella o modifica i flag `DecodeType` per vedere come si comporta la libreria. Più giochi, più ti sentirai a tuo agio con gli scenari **read barcode image C#**.

Hai un'immagine difficile che si rifiuta di decodificare? Lascia un commento qui sotto o apri una issue sul repository GitHub del progetto di esempio. Buon coding!

## Cosa dovresti imparare dopo?

I tutorial seguenti coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come leggere i codici DataMatrix con Aspose.BarCode per .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Come creare un codice a barre – Compact PDF417 con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Leggi il codice DataMatrix C# – Genera modalità DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}