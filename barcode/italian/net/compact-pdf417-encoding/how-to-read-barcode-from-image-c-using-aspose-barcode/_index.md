---
category: general
date: 2026-10-02
description: Scopri come leggere i codici a barre da un'immagine in C# con un esempio
  completo che mostra come decodificare il codice a barre PDF417 utilizzando Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image c#
- how to decode pdf417 barcode
language: it
lastmod: 2026-10-02
og_description: Leggi il codice a barre da un'immagine in C# con Aspose.BarCode. Questo
  tutorial spiega come decodificare il codice a barre PDF417 ed estrarre i metadati
  estesi.
og_image_alt: Screenshot showing how to read barcode from image c# in Visual Studio
og_title: Leggi il codice a barre da un'immagine in C# – guida passo passo
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to read barcode from image c# with a complete example that
    shows how to decode PDF417 barcode using Aspose.BarCode.
  headline: How to read barcode from image c# using Aspose.BarCode
  type: TechArticle
- description: Learn how to read barcode from image c# with a complete example that
    shows how to decode PDF417 barcode using Aspose.BarCode.
  name: How to read barcode from image c# using Aspose.BarCode
  steps:
  - name: Create a `BarCodeReader` for a PDF417 image
    text: '```csharp using System; using Aspose.BarCode; using Aspose.BarCode.BarCodeRecognition;'
  - name: Iterate over all detected barcodes
    text: '```csharp // Step 2: Read every barcode found in the image foreach (BarCodeResult
      barcodeResult in barcodeReader.ReadBarCodes()) { // At this point you have successfully
      read barcode from image c#. ```'
  - name: Access the extended PDF417 macro metadata
    text: '```csharp // Step 3: Grab the macro‑PDF417 extended information var macro
      = barcodeResult.Extended.Pdf417;'
  - name: Output the barcode text and macro details
    text: '```csharp // Step 4: Print the basic barcode information Console.WriteLine($"Type:
      {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");'
  - name: Handle errors and clean up resources
    text: 'The `using` statement automatically disposes the `BarCodeReader`. However,
      you should still catch exceptions that may arise from missing files or unsupported
      formats:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Come leggere il codice a barre da un'immagine C# usando Aspose.BarCode
url: /it/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come leggere un barcode da un'immagine c# usando Aspose.BarCode

Se hai bisogno di **leggere un barcode da un'immagine c#**, questa guida ti accompagna passo passo verso una soluzione completa e funzionante. Imparerai a decodificare un barcode PDF417, accedere ai suoi dati macro estesi e stampare i risultati sulla console.

La lettura di barcode da immagini è una necessità comune per sistemi di inventario, validazione di biglietti e elaborazione di documenti. Questo tutorial copre tutto ciò che ti serve: pacchetti richiesti, spiegazione del codice, gestione dei casi limite e output previsto. Nessuna documentazione esterna è necessaria; l'esempio funziona subito con Aspose.BarCode .NET.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6.0 SDK o versioni successive installate  
* Visual Studio 2022 (o qualsiasi IDE C#)  
* Un riferimento NuGet a **Aspose.BarCode** (versione 23.10 o più recente)  
* Un file immagine che contenga un barcode PDF417 – ad esempio `ExtPDF417Meta.png`

Se manca qualcuno di questi elementi, installa il .NET SDK, aggiungi il pacchetto NuGet con `dotnet add package Aspose.BarCode` e posiziona l'immagine in una cartella a cui il tuo progetto possa fare riferimento.

## Come leggere un barcode da un'immagine c# – passo‑passo

Le sezioni seguenti suddividono l'implementazione in passaggi logici. Ogni passaggio include uno snippet di codice, una spiegazione del **perché** è importante e un suggerimento pratico da applicare ai progetti reali.

### Passo 1: Creare un `BarCodeReader` per un'immagine PDF417

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Step 1: Initialise the reader for a Macro PDF417 image
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // The DecodeType enum tells the library which symbology to look for.
        // Using DecodeType.MacroPdf417 restricts the scan to PDF417 macro symbols.
        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // The reader is now ready to read barcode from image c# efficiently.
```

**Perché è importante** – Il costruttore `BarCodeReader` accetta il percorso dell'immagine e il tipo di barcode previsto. Specificare `MacroPdf417` restringe la ricerca, migliorando le prestazioni e riducendo i falsi positivi quando l'immagine contiene più simbologie.

**Suggerimento professionale:** Se non sei sicuro del tipo di barcode, usa `DecodeType.AllSupportedTypes` e filtra i risultati in seguito.

### Passo 2: Iterare su tutti i barcode rilevati

```csharp
            // Step 2: Read every barcode found in the image
            foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
            {
                // At this point you have successfully read barcode from image c#.
```

**Perché è importante** – Un'immagine macro PDF417 può contenere diversi segmenti. Il metodo `ReadBarCodes()` restituisce una collezione, permettendoti di elaborare ogni segmento singolarmente.

**Caso limite:** Se l'immagine non contiene simboli PDF417, la collezione è vuota e il corpo del ciclo non viene mai eseguito. Considera di aggiungere un controllo dopo il ciclo per informare l'utente.

### Passo 3: Accedere ai metadati macro PDF417 estesi

```csharp
                // Step 3: Grab the macro‑PDF417 extended information
                var macro = barcodeResult.Extended.Pdf417;

                // The macro object holds file‑level data that PDF417 uses for
                // multi‑segment documents such as shipping manifests.
```

**Perché è importante** – La proprietà `Extended.Pdf417` espone i campi definiti dalla specifica PDF417, come file ID, segment ID e file name. Questi dati sono essenziali quando devi ricostruire un documento multipagina da scansioni di barcode separate.

**Suggerimento professionale:** Verifica sempre che `barcodeResult.Extended` non sia null prima di accedere a `Pdf417`. La libreria restituisce `null` per le simbologie che non supportano dati estesi.

### Passo 4: Stampare il testo del barcode e i dettagli macro

```csharp
                // Step 4: Print the basic barcode information
                Console.WriteLine($"Type: {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");

                // Print macro‑specific fields
                Console.WriteLine($"Macro File ID: {macro.MacroPdf417FileID}, Segment ID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count: {macro.MacroPdf417SegmentsCount}, File Name: {macro.MacroPdf417FileName}");
            }
        }
    }
}
```

**Perché è importante** – L'output sulla console ti offre visibilità immediata sia sul testo decodificato sia sui metadati macro. Questo è utile per il debug e per l'elaborazione successiva, ad esempio per memorizzare le informazioni in un database.

**Output previsto** (supponendo che l'immagine di esempio contenga un segmento macro):

```
Type: MacroPdf417, Text: https://example.com/document.pdf
Macro File ID: 12, Segment ID: 1
Segments Count: 3, File Name: shipment_manifest.pdf
```

Se l'immagine contiene tre segmenti, il ciclo stampa tre blocchi, ognuno con un diverso `Segment ID`.

### Passo 5: Gestire gli errori e liberare le risorse

L'istruzione `using` elimina automaticamente il `BarCodeReader`. Tuttavia, dovresti comunque catturare le eccezioni che possono derivare da file mancanti o formati non supportati:

```csharp
        try
        {
            // Place the entire reader block here (Steps 1‑4)
        }
        catch (Exception ex)
        {
            Console.Error.WriteLine($"Error while trying to read barcode from image c#: {ex.Message}");
        }
```

**Perché è importante** – Le applicazioni robuste non vanno in crash perché un file è assente o l'immagine è corrotta. Fornire un messaggio di errore chiaro aiuta te o il tuo team di supporto a diagnosticare rapidamente il problema.

## Come decodificare un barcode PDF417 con Aspose.BarCode

La keyword secondaria **how to decode pdf417 barcode** appare naturalmente in questa sezione. Decodificare un barcode PDF417 segue lo stesso schema mostrato sopra, ma puoi omettere il flag `MacroPdf417` se ti serve solo il testo semplice:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Decoded text: {result.CodeText}");
    }
}
```

**Perché potresti scegliere questa variante** – Quando il barcode non contiene informazioni macro, usare `DecodeType.Pdf417` riduce il carico di elaborazione e semplifica la gestione del risultato.

**Domanda comune:** *E se il barcode è ruotato?*  
Aspose.BarCode rileva automaticamente la rotazione e la corregge, quindi non è necessario aggiungere codice di pre‑elaborazione dell'immagine.

## Esempio completo e funzionante

Copia l'intero programma qui sotto in un nuovo progetto console (`dotnet new console`) e sostituisci `YOUR_DIRECTORY/ExtPDF417Meta.png` con il percorso reale della tua immagine.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        try
        {
            using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    var macro = barcodeResult.Extended?.Pdf417;

                    Console.WriteLine($"Type: {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");

                    if (macro != null)
                    {
                        Console.WriteLine($"Macro File ID: {macro.MacroPdf417FileID}, Segment ID: {macro.MacroPdf417SegmentID}");
                        Console.WriteLine($"Segments Count: {macro.MacroPdf417SegmentsCount}, File Name: {macro.MacroPdf417FileName}");
                    }
                    else
                    {
                        Console.WriteLine("No macro PDF417 metadata available.");
                    }
                }
            }
        }
        catch (Exception ex)
        {
            Console.Error.WriteLine($"Error while trying to read barcode from image c#: {ex.Message}");
        }
    }
}
```

Eseguendo il programma verranno stampati il tipo di barcode, il testo decodificato e eventuali metadati macro. Se l'immagine non contiene un macro PDF417, il programma ti informerà in modo elegante.

## Conclusione

Ora sai come **leggere un barcode da un'immagine c#** con Aspose.BarCode, come **decodificare un barcode PDF417** e come estrarre i campi estesi macro‑PDF417. La soluzione copre l'inizializzazione, l'iterazione, l'accesso ai metadati, la gestione degli errori e una variante per la decodifica PDF417 semplice.

Da qui puoi:

* Memorizzare i dati estratti in un database SQL per un recupero successivo.  
* Combinare più segmenti per ricostruire il documento originale.  
* Esplorare altre simbologie supportate da Aspose.BarCode, come

## Cosa dovresti imparare dopo?


I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare ulteriori funzionalità dell'API e a esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come leggere PDF417 in C# – Esempio completo di barcode](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [Come leggere PDF417 in C# – Esempio completo di lettore di barcode](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Come generare un'immagine barcode PDF417 in C# con Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}