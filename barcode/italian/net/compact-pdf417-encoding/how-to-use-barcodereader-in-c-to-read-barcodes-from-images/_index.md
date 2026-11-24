---
category: general
date: 2026-11-23
description: Impara come utilizzare BarCodeReader in C# per leggere i codici a barre
  da un'immagine, inclusa la decodifica Macro PDF417, con un esempio di codice completo
  e spiegazioni chiare.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use barcodereader
- read barcodes from image c#
language: it
lastmod: 2026-11-23
og_description: Come utilizzare BarCodeReader in C# per leggere i codici a barre da
  un'immagine. Segui questa guida passo‑passo per decodificare Macro PDF417 e altri
  formati con codice pronto all'uso.
og_image_alt: Screenshot of BarCodeReader console output showing decoded Macro PDF417
  data
og_title: Come usare BarCodeReader in C# – leggere i codici a barre dalle immagini
  rapidamente
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  headline: How to use BarCodeReader in C# to read barcodes from images
  type: TechArticle
- description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  name: How to use BarCodeReader in C# to read barcodes from images
  steps:
  - name: 1. Decoding multiple barcode formats
    text: 'If you need to detect more than one format, pass a combined `DecodeType`
      flag:'
  - name: 2. Managing large images
    text: 'Large images can cause high memory usage. Downscale the image before passing
      it to the reader:'
  - name: 3. Error handling
    text: 'Wrap the reading logic in a try‑catch block to surface decoding failures:'
  type: HowTo
tags:
- barcode
- C#
- image-processing
title: Come utilizzare BarCodeReader in C# per leggere i codici a barre dalle immagini
url: /it/net/compact-pdf417-encoding/how-to-use-barcodereader-in-c-to-read-barcodes-from-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come utilizzare BarCodeReader in C# per leggere i codici a barre dalle immagini

Se hai bisogno di **come utilizzare BarCodeReader** per una scansione rapida di codici a barre, questa guida ti mostra esattamente questo. Che tu stia costruendo un sistema point‑of‑sale o automatizzando l'acquisizione di documenti, imparerai a leggere i codici a barre da immagini in progetti C# con poche righe di codice.

In questo tutorial vedrai un esempio completo e eseguibile che decodifica un codice Macro PDF417, ne estrae le proprietà estese e stampa informazioni utili sulla console. Non è necessaria alcuna documentazione esterna – tutto ciò che ti serve è qui.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6.0 (o successivo) installato – il codice è mirato all'ultima versione LTS.
* Un riferimento al pacchetto NuGet **Aspose.BarCode** (o qualsiasi compatibile) che fornisce `BarCodeReader`.
* Un file immagine contenente un codice Macro PDF417 (l'esempio utilizza `ExtPDF417Meta.png`).

> **Pro tip:** Se utilizzi Visual Studio, aggiungi il pacchetto tramite `dotnet add package Aspose.BarCode` o l'interfaccia UI del NuGet Package Manager.

## Passo 1: Creare un'istanza di BarCodeReader

La prima cosa da fare quando si lavora con una libreria di codici a barre è istanziare un lettore che punti all'immagine di origine e indichi all'API quali tipi di codice a barre cercare.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Step 1: Initialise BarCodeReader for a Macro PDF417 image
using (BarCodeReader barcodeReader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png",
           DecodeType.MacroPdf417))
{
    // The using block guarantees proper disposal of native resources.
```

*Perché questo passaggio è importante:*  
`BarCodeReader` apre l'immagine, alloca memoria nativa e prepara gli algoritmi di decodifica per il `DecodeType` specificato. Limitando il tipo a `MacroPdf417`, riduci il carico CPU e migliori l'accuratezza del rilevamento.

## Passo 2: Leggere tutti i codici a barre trovati nell'immagine

Un'unica immagine può contenere più codici a barre, specialmente quando si trattano dati macro‑codificati. Il metodo `ReadBarCodes` restituisce un enumerable di oggetti `BarCodeResult`, ciascuno rappresentante un codice rilevato.

```csharp
    // Step 2: Iterate over every barcode found
    foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
    {
```

*Perché questo passaggio è importante:*  
Iterare sulla collezione garantisce di catturare ogni istanza, fondamentale per scenari di elaborazione batch o quando un documento incorpora diversi codici.

## Passo 3: Accedere alle proprietà estese di Macro PDF417

Macro PDF417 memorizza metadati aggiuntivi come identificatori di file, numeri di segmento e conteggio totale dei segmenti. Questi valori sono esposti tramite la proprietà `Extended.Pdf417` di `BarCodeResult`.

```csharp
        // Step 3: Pull extended Macro PDF417 information
        var macroInfo = barcodeResult.Extended.Pdf417;
```

*Perché questo passaggio è importante:*  
I campi estesi ti permettono di ricostruire documenti multi‑segmento o di convalidare che tutte le parti appartengano alla stessa sorgente. Saltare questo passaggio ti fornirebbe solo il testo grezzo, perdendo contesto prezioso.

## Passo 4: Stampare le informazioni più utili

Infine, scrivi i dati sulla console (o su qualsiasi logger) così da poter verificare l'operazione di lettura. L'esempio stampa il tipo di codice, il testo decodificato e diversi campi macro.

```csharp
        // Step 4: Display key details
        Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
        Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
        Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
        // Additional macro fields are available:
        // macroInfo.MacroPdf417SegmentID
        // macroInfo.MacroPdf417SegmentsCount
    }
}
```

**Output della console previsto**

```
Code Type: MacroPdf417
Code Text: 1234567890
Macro PDF417 File ID: 42
```

> **Nota:** Se l'immagine non contiene un codice Macro PDF417, `ReadBarCodes()` restituisce una collezione vuota e il corpo del ciclo non viene mai eseguito. Controlla sempre un risultato vuoto nel codice di produzione.

## Leggere i codici a barre da un'immagine in C# – gestire scenari comuni

### 1. Decodificare più formati di codice a barre

Se devi rilevare più di un formato, passa una flag `DecodeType` combinata:

```csharp
using (BarCodeReader reader = new BarCodeReader(
           "sample.png",
           DecodeType.Pdf417 | DecodeType.QR | DecodeType.DataMatrix))
{
    // Same iteration logic as before
}
```

### 2. Gestire immagini di grandi dimensioni

Le immagini di grandi dimensioni possono causare un elevato utilizzo di memoria. Ridimensiona l'immagine prima di passarla al lettore:

```csharp
using (Bitmap original = new Bitmap("large.png"))
using (Bitmap resized = new Bitmap(original, new Size(1024, 768)))
{
    // Save resized image to a temporary stream and feed it to BarCodeReader
}
```

### 3. Gestione degli errori

Avvolgi la logica di lettura in un blocco try‑catch per evidenziare i fallimenti di decodifica:

```csharp
try
{
    // reading code from previous steps
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## Esempio completo funzionante

Di seguito trovi il programma completo che puoi copiare, incollare ed eseguire. Include tutti i passaggi, le direttive `using` necessarie e una semplice struttura di gestione degli errori.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        try
        {
            using (BarCodeReader barcodeReader = new BarCodeReader(
                       imagePath,
                       DecodeType.MacroPdf417))
            {
                bool anyFound = false;

                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    anyFound = true;
                    var macroInfo = barcodeResult.Extended.Pdf417;

                    Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
                    Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
                    Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
                    Console.WriteLine($"Segment ID: {macroInfo.MacroPdf417SegmentID}");
                    Console.WriteLine($"Segments Count: {macroInfo.MacroPdf417SegmentsCount}");
                    Console.WriteLine(new string('-', 40));
                }

                if (!anyFound)
                {
                    Console.WriteLine("No barcodes were detected in the image.");
                }
            }
        }
        catch (BarCodeException ex)
        {
            Console.Error.WriteLine($"Error reading barcode: {ex.Message}");
        }
    }
}
```

**Eseguire il programma** stampa ogni codice Macro PDF417 rilevato e i suoi campi estesi, oppure informa che non sono stati trovati codici a barre.

## Conclusione

Ora sai **come utilizzare BarCodeReader** per leggere i codici a barre da applicazioni C# basate su immagini, inclusa l'estrazione dei metadati Macro PDF417. La soluzione copre l'inizializzazione, l'iterazione, l'accesso alle proprietà estese e consigli pratici per gestire più formati, immagini di grandi dimensioni ed errori.

Successivamente, potresti esplorare:

* **Lettura di QR code** – sostituisci `DecodeType.MacroPdf417` con `DecodeType.QR`.
* **Salvataggio dei dati decodificati** in un database o file JSON per l'elaborazione successiva.
* **Integrazione con ASP.NET Core** per accettare immagini caricate tramite un'API web.

Sentiti libero di sperimentare con diversi tipi di codice a barre e fonti di immagine. Buon coding!

## Cosa dovresti imparare dopo?

I tutorial seguenti coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [tutorial barcode reader C# – leggere i codici Macro PDF417 passo passo usando GroupDocs.Barcode](/barcode/english/net/compact-pdf417-encoding/c-barcode-reader-tutorial-read-macro-pdf417-barcodes-step-by/)
- [Come utilizzare un generatore di codici a barre C# per Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/)
- [Leggere un codice a barre da un'immagine C# – guida completa con Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}