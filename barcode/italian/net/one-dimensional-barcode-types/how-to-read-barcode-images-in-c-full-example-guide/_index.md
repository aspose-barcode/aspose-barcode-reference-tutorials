---
category: general
date: 2026-10-15
description: Come leggere rapidamente le immagini di codici a barre in C# usando BarCodeReader.
  Impara a leggere più codici a barre e visualizza un esempio di lettore di codici
  a barre in C# che funziona con Macro‑PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode
- read multiple barcodes
- c# barcode reader example
- Macro‑PDF417 decoding
- barcode metadata extraction
language: it
lastmod: 2026-10-15
og_description: Come leggere i codici a barre in C# usando BarCodeReader. Questo tutorial
  mostra un esempio completo di lettore di codici a barre in C# che gestisce più codici
  a barre ed estrae i metadati Macro‑PDF417.
og_image_alt: Screenshot showing how to read barcode with C# BarCodeReader
og_title: Come leggere un codice a barre in C# – esempio passo‑passo
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  headline: How to read barcode images in C# – full example guide
  type: TechArticle
- description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  name: How to read barcode images in C# – full example guide
  steps:
  - name: Initialise the `BarCodeReader`
    text: '```csharp using Aspose.BarCode; using Aspose.BarCode.BarCodeRecognition;'
  - name: Read all barcodes present in the image
    text: '```csharp // Step 2: Read all barcodes in the image BarCodeResult[] results
      = reader.ReadBarCodes(); ```'
  - name: Display basic barcode details
    text: '```csharp foreach (BarCodeResult result in results) { Console.WriteLine($"CodeType:
      {result.CodeTypeName}"); Console.WriteLine($"CodeText: {result.CodeText}");
      ```'
  - name: Retrieve and show Macro‑PDF417 specific metadata
    text: '```csharp // Macro‑PDF417 extended data Console.WriteLine($"FileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Segment: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Count: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
      Console.WriteLine($"FileName'
  - name: Full runnable program
    text: Below is a self‑contained console application that puts all four steps together.
      Copy the code into a new `.cs` file, adjust the `imagePath`, and run `dotnet
      run`.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Come leggere le immagini di codici a barre in C# – guida completa con esempi
url: /it/net/one-dimensional-barcode-types/how-to-read-barcode-images-in-c-full-example-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come leggere le immagini dei codici a barre in C# – guida completa con esempio

Se hai bisogno di **come leggere i codici a barre** da un'immagine in un'applicazione .NET, questa guida ti fornisce una soluzione pronta all'uso. Vedrai un **esempio completo di lettore di codici a barre c#** che funziona con i simboli Macro‑PDF417 e può **leggere più codici a barre** da un'unica immagine.

La lettura dei codici a barre è una necessità comune per i sistemi di inventario, la convalida dei biglietti e l'elaborazione dei documenti. Alla fine di questo tutorial sarai in grado di:

* Inizializzare il `BarCodeReader` per qualsiasi formato supportato.  
* Estrarre informazioni di base come il tipo di codice e il testo decodificato.  
* Recuperare i metadati specifici di Macro‑PDF417 (ID file, segmento, checksum, …).  
* Gestire immagini che contengono diversi codici a barre senza codice aggiuntivo.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6.0 SDK o versioni successive installate.  
* Un ambiente di sviluppo (Visual Studio 2022, VS Code o Rider).  
* Il pacchetto NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`) – fornisce la classe `BarCodeReader` utilizzata nell'esempio.  
* Un file immagine che contiene un codice a barre Macro‑PDF417 (ad esempio `MacroPdf417.png`).  

Puoi installare il pacchetto NuGet con il seguente comando:

```bash
dotnet add package Aspose.BarCode
```

## Come leggere i codici a barre con BarCodeReader in C#

Il cuore della soluzione si sviluppa in quattro passaggi concisi. Ogni passaggio è racchiuso in un blocco `using` per garantire che le risorse non gestite vengano rilasciate tempestivamente.

### Passo 1: Inizializzare il `BarCodeReader`

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Path to the image that contains the Macro‑PDF417 barcode(s)
string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

// Initialise the reader for the specific DecodeType
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The remaining steps are inside this block
}
```

**Perché è importante:**  
`BarCodeReader` accetta un percorso file e un `DecodeType`. Specificare `DecodeType.MacroPdf417` indica alla libreria di cercare solo simboli Macro‑PDF417, migliorando la velocità di rilevamento e riducendo i falsi positivi.

### Passo 2: Leggere tutti i codici a barre presenti nell'immagine

```csharp
    // Step 2: Read all barcodes in the image
    BarCodeResult[] results = reader.ReadBarCodes();
```

**Perché è importante:**  
Il metodo `ReadBarCodes()` restituisce un array che può contenere uno o più oggetti `BarCodeResult`. È qui che la capacità di **leggere più codici a barre** brilla – non è necessario un ciclo separato per ogni possibile codice.

### Passo 3: Visualizzare i dettagli di base del codice a barre

```csharp
    foreach (BarCodeResult result in results)
    {
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

**Perché è importante:**  
`CodeTypeName` indica quale simbologia è stata rilevata (ad esempio “MacroPDF417”), mentre `CodeText` contiene il payload decodificato. Questi due campi sono i più frequentemente usati nella logica successiva.

### Passo 4: Recuperare e mostrare i metadati specifici di Macro‑PDF417

```csharp
        // Macro‑PDF417 extended data
        Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
        Console.WriteLine(new string('-', 40));
    }
}
```

**Perché è importante:**  
Macro‑PDF417 estende il formato PDF417 regolare con metadati a livello di documento. Accedendo alla proprietà `Extended.Pdf417` ottieni tutto il necessario per ricostruire il file originale, convalidare l'integrità o instradare i dati al destinatario corretto.

### Programma completo eseguibile

Di seguito trovi un'applicazione console autonoma che combina tutti e quattro i passaggi. Copia il codice in un nuovo file `.cs`, regola `imagePath` e avvia `dotnet run`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // 1️⃣ Initialise the BarCodeReader for Macro‑PDF417 images
            // ------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // ------------------------------------------------------------
                // 2️⃣ Read all barcodes present in the image
                // ------------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes were detected.");
                    return;
                }

                // ------------------------------------------------------------
                // 3️⃣ Iterate over each result – this is where we **read multiple barcodes**
                // ------------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // ------------------------------------------------------------
                    // 4️⃣ Extract Macro‑PDF417 metadata (c# barcode reader example)
                    // ------------------------------------------------------------
                    Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

#### Output console previsto

```
CodeType: MacroPDF417
CodeText: https://example.com/document
FileID:    12
Segment:   3
Count:     5
FileName:  report.pdf
Checksum:  0x1A2B3C4D
FileSize:  1048576
Time:      2024-08-15T14:23:00Z
Addressee: John Doe
Sender:    Acme Corp.
Terminator:END
----------------------------------------
```

Se l'immagine contiene più di un simbolo Macro‑PDF417, il programma stampa un blocco separato per ciascun codice a barre, dimostrando la capacità di **leggere più codici a barre** senza alcun codice aggiuntivo.

## Gestione dei casi limite più comuni

| Situazione | Cosa fare | Motivo |
|-----------|------------|--------|
| **File non trovato** | Avvolgi la costruzione di `BarCodeReader` in un blocco `try/catch (FileNotFoundException)` e visualizza un messaggio amichevole. | Previene il crash dell'applicazione e informa l'utente dell'asset mancante. |
| **Nessun codice a barre rilevato** | Verifica `results.Length == 0` (come mostrato nel programma completo) e gestiscilo in modo appropriato. | Fornisce un feedback chiaro quando l'immagine non contiene alcuna simbologia supportata. |
| **Tipo di codice a barre diverso** | Cambia `DecodeType.MacroPdf417` in `DecodeType.AllSupportedTypes` o in un altro valore enum specifico. | Consente allo stesso codice di funzionare con QR, Code128, DataMatrix, ecc., mantenendo il supporto per **leggere più codici a barre**. |
| **Immagini di grandi dimensioni** | Imposta `reader.AutoSize = true` o ridimensiona l'immagine prima di passarla al lettore. | Migliora le prestazioni e riduce la pressione sulla memoria della CLR. |
| **Uso thread‑safe** | Crea un'istanza separata di `BarCodeReader` per thread; la classe non è thread‑safe. | Evita condizioni di gara in scanner multi‑thread o servizi web. |

## Consigli professionali per il codice di produzione

* **Dispose presto:** L'istruzione `using` garantisce che le risorse native (ad esempio buffer di immagini) vengano rilasciate prontamente. Nei servizi a lungo termine, rilascia il lettore non appena hai terminato l'elaborazione di ogni immagine.  
* **Batch processing**

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [How to Read PDF417 in C# – Complete Barcode Reader Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}