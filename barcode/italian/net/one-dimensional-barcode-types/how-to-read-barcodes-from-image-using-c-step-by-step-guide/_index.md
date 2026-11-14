---
category: general
date: 2026-11-14
description: Impara a leggere i codici a barre da un'immagine in C# con un tutorial
  completo sul lettore di codici a barre in C#. Include configurazione, codice completo
  e gestione dei campi Macro PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcodes from image
- barcode reader tutorial c#
language: it
lastmod: 2026-11-14
og_description: Leggi i codici a barre da un'immagine in C# con questo tutorial sul
  lettore di codici a barre in C#. Ottieni un esempio completo funzionante e impara
  a estrarre i dati Macro PDF417.
og_image_alt: C# code screenshot that reads barcodes from image using BarCodeReader
og_title: Leggi i codici a barre da un'immagine in C# – tutorial completo
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to read barcodes from image in C# with a complete barcode
    reader tutorial c#. Includes setup, full code, and handling Macro PDF417 fields.
  headline: How to read barcodes from image using C# – step‑by‑step guide
  type: TechArticle
- description: Learn how to read barcodes from image in C# with a complete barcode
    reader tutorial c#. Includes setup, full code, and handling Macro PDF417 fields.
  name: How to read barcodes from image using C# – step‑by‑step guide
  steps:
  - name: Prerequisites
    text: '- .NET 8 SDK (or .NET 6+ if you prefer) installed. - Basic familiarity
      with C# console applications. - An image file that contains a Macro PDF417 barcode
      (e.g., `MacroPdf417.png`).'
  - name: Explanation of each step
    text: '| Step | Why it matters | |------|----------------| | **1️⃣ Define image
      path** | The reader works with a file path or stream. Using a relative path
      makes the example easy to copy‑paste. | | **2️⃣ Create BarCodeReader** | Passing
      `DecodeType.MacroPdf417` restricts the scan to that symbology, which i'
  - name: Reading other symbologies
    text: 'If you need to **read barcodes from image** that are not Macro PDF417,
      replace `DecodeType.MacroPdf417` with a comma‑separated list, e.g.:'
  - name: Handling large images
    text: 'Large PNG or JPEG files can increase memory usage. To keep the process
      lightweight, you can downscale the image before passing it to `BarCodeReader`:'
  - name: Working with streams instead of file paths
    text: 'When the image comes from a database or a web request, pass a `Stream`:'
  type: HowTo
tags:
- C#
- barcode
- image processing
title: Come leggere i codici a barre da un'immagine usando C# – guida passo passo
url: /it/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come leggere i codici a barre da un'immagine usando C# – guida passo‑passo

Se hai bisogno di **leggere i codici a barre da un'immagine** in un'applicazione .NET, questa guida ti mostra esattamente come fare. Alla fine del tutorial avrai un programma completo e eseguibile che estrae sia i dati di base del codice a barre sia i campi specifici di Macro PDF417.

In questo **barcode reader tutorial c#** copriremo la configurazione del progetto, il pacchetto NuGet necessario e un esempio di codice completo che funziona con l'ultimo SDK .NET 8. Non sono necessari servizi esterni—tutto viene eseguito localmente.

## Cosa imparerai

- Come aggiungere la libreria Aspose.BarCode (o simile) a un progetto C#.
- Come creare un `BarCodeReader` che punta a un file immagine specifico.
- Come iterare tutti i codici a barre rilevati e stampare il loro tipo, testo e i metadati Macro PDF417.
- Suggerimenti per gestire immagini con più codici a barre o diversi tipi di decodifica.

### Prerequisiti

- .NET 8 SDK (o .NET 6+ se preferisci) installato.  
- Familiarità di base con le applicazioni console C#.  
- Un file immagine che contiene un codice a barre Macro PDF417 (ad es., `MacroPdf417.png`).  

---

## Passo 1: Configura un nuovo progetto console

Open a terminal and run:

```bash
dotnet new console -n BarcodeReaderDemo
cd BarcodeReaderDemo
```

Questo crea un'app console minimale chiamata **BarcodeReaderDemo**. Il file di progetto (`BarcodeReaderDemo.csproj`) sarà usato nel passo successivo.

## Passo 2: Installa la libreria per la lettura dei codici a barre

Per questo tutorial usiamo la libreria **Aspose.BarCode for .NET** perché supporta Macro PDF417 out of the box. Installala via NuGet:

```bash
dotnet add package Aspose.BarCode --version 23.12
```

> **Perché questa libreria?** Fornisce una singola classe `BarCodeReader`, supporta decine di simbologie e espone la proprietà `Extended` che contiene i campi Macro PDF417.

## Passo 3: Scrivi il codice del lettore di codici a barre (barcode reader tutorial c#)

Sostituisci il contenuto di `Program.cs` con il seguente esempio completo. Dimostra **come leggere i codici a barre da un'immagine** e stampa sia le informazioni generiche sia quelle specifiche di Macro PDF417.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Recognition;

namespace BarcodeReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -------------------------------------------------------------
            // 1️⃣  Define the path to the image that contains the barcode.
            // -------------------------------------------------------------
            string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            // -------------------------------------------------------------
            // 2️⃣  Create a BarCodeReader for the Macro PDF417 symbology.
            // -------------------------------------------------------------
            // DecodeType.MacroPdf417 tells the reader to look for the
            // Macro PDF417 variant and to populate the Extended.Pdf417
            // fields when they are present.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // ---------------------------------------------------------
                // 3️⃣  Iterate through every barcode found in the image.
                // ---------------------------------------------------------
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // -----------------------------------------------------
                    // 4️⃣  Output generic barcode information.
                    // -----------------------------------------------------
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // -----------------------------------------------------
                    // 5️⃣  Output Macro PDF417 specific fields (if any).
                    // -----------------------------------------------------
                    // The Extended property is only populated for
                    // symbologies that expose extra data, such as Macro PDF417.
                    Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");

                    // -----------------------------------------------------
                    // 6️⃣  (Optional) Add more macro fields here as needed.
                    // -----------------------------------------------------
                    Console.WriteLine(new string('-', 40));
                }
            }

            // -------------------------------------------------------------
            // 7️⃣  Keep the console window open when debugging.
            // -------------------------------------------------------------
            Console.WriteLine("Finished reading barcodes. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Spiegazione di ogni passo

| Passo | Perché è importante |
|------|----------------|
| **1️⃣ Definisci il percorso dell'immagine** | Il lettore funziona con un percorso file o stream. Usare un percorso relativo rende l'esempio facile da copiare‑incollare. |
| **2️⃣ Crea BarCodeReader** | Passare `DecodeType.MacroPdf417` limita la scansione a quella simbologia, migliorando la velocità e garantendo che i campi `Extended` siano popolati. |
| **3️⃣ Itera i risultati** | Un'immagine può contenere più codici a barre; il ciclo `foreach` garantisce di catturarli tutti. |
| **4️⃣ Output generico** | `CodeTypeName` e `CodeText` sono le informazioni più comuni di cui gli sviluppatori hanno bisogno. |
| **5️⃣ Campi Macro PDF417** | Macro PDF417 incorpora dati aggiuntivi (ID file, ID segmento, conteggio segmenti). Accedere a `result.Extended.Pdf417` fornisce questi valori senza parsing aggiuntivo. |
| **6️⃣ Campi extra opzionali** | La libreria espone altri campi macro (ad es., `MacroPdf417FileName`). Puoi estendere l'output secondo le esigenze del tuo caso d'uso. |
| **7️⃣ Mantieni la console aperta** | Utile quando si esegue da Visual Studio o `dotnet run` per vedere l'output prima che la finestra si chiuda. |

## Passo 4: Esegui il programma e verifica l'output

Posiziona il tuo file `MacroPdf417.png` nella cartella a cui fa riferimento `imagePath`. Quindi esegui:

```bash
dotnet run
```

Un tipico output della console appare così:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12
Pdf417MacroSegmentID: 3
Pdf417MacroSegmentsCount: 5
----------------------------------------
Finished reading barcodes. Press any key to exit.
```

Se l'immagine contiene più simboli Macro PDF417, il programma elencherà ogni insieme di valori in sequenza.

## Varianti comuni e casi limite

### Lettura di altre simbologie

Se hai bisogno di **leggere i codici a barre da un'immagine** che non siano Macro PDF417, sostituisci `DecodeType.MacroPdf417` con un elenco separato da virgole, ad esempio:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
    DecodeType.QR | DecodeType.Code128 | DecodeType.DataMatrix))
```

La proprietà `Extended` sarà `null` per le simbologie che non forniscono dati extra, quindi controlla sempre `null` prima di accedervi.

### Gestione di immagini grandi

File PNG o JPEG di grandi dimensioni possono aumentare l'uso di memoria. Per mantenere il processo leggero, puoi ridimensionare l'immagine prima di passarla a `BarCodeReader`:

```csharp
using (System.Drawing.Bitmap bmp = new System.Drawing.Bitmap(imagePath))
{
    var resized = new System.Drawing.Bitmap(bmp, new System.Drawing.Size(bmp.Width / 2, bmp.Height / 2));
    using (BarCodeReader reader = new BarCodeReader(resized, DecodeType.MacroPdf417))
    {
        // read as before...
    }
}
```

### Lavorare con stream invece di percorsi file

Quando l'immagine proviene da un database o da una richiesta web, passa uno `Stream`:

```csharp
using (FileStream fs = File.OpenRead(imagePath))
using (BarCodeReader reader = new BarCodeReader(fs, DecodeType.MacroPdf417))
{
    // read as before...
}
```

## Consigli professionali per un'esperienza fluida con il lettore di codici a barre

- **Consiglio:** Imposta sempre `DecodeType` al più ristretto insieme di simbologie che ti aspetti. Questo riduce i falsi positivi e velocizza l'elaborazione.  
- **Attenzione a:** Immagini con basso contrasto o compressione elevata possono causare letture mancate. Pre‑processa l'immagine (regola luminosità/contrasto) se noti tassi di rilevamento bassi.  
- **Suggerimento:** La classe `BarCodeReader` implementa `IDisposable`; usare un blocco `using` garantisce che le risorse native vengano rilasciate prontamente.  

---

## Conclusione

Ora sai come **leggere i codici a barre da un'immagine** in C# ed estrarre sia le informazioni standard sia quelle specifiche di Macro PDF417. Questo **barcode reader tutorial c#** fornisce una soluzione completa e autonoma che puoi inserire in qualsiasi progetto .NET.

Da qui potresti:

- Esplorare altri tipi di decodifica (QR, DataMatrix, Code128).  
- Integrare il lettore in un'API ASP.NET Core per elaborare caricamenti al volo.  
- Memorizzare i campi macro estratti in un database per aggregazioni future.

Buon coding, e sentiti libero di sperimentare con diverse fonti di immagini e formati di codici a barre!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [How to decode PDF417 barcodes in C# and read barcode image C#](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-and-read-barcode-image-c/)
- [How to read barcode from image c# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/)
- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}