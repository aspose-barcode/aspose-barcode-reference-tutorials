---
category: general
date: 2026-08-03
description: Leggi il codice a barre PDF417 da un'immagine usando C# BarCodeReader
  – un esempio completo di lettore di codici a barre che mostra anche come leggere
  più codici a barre.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read PDF417 barcode
- barcode reader example
- read multiple barcodes
- read barcodes image
language: it
lastmod: 2026-08-03
og_description: Leggi rapidamente il codice a barre PDF417 con un esempio di BarCodeReader
  in C#. Segui questa guida passo‑passo per decodificare il macro PDF417 e leggere
  più codici a barre da un'immagine.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: Leggi il codice a barre PDF417 in C# – esempio completo di lettore di codici
  a barre
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  headline: Read PDF417 barcode in C# – barcode reader example
  type: TechArticle
- description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  name: Read PDF417 barcode in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
title: Leggi il codice a barre PDF417 in C# – esempio di lettore di codici a barre
url: /it/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Leggi il codice a barre PDF417 in C# – esempio di lettura del codice a barre

Se hai bisogno di leggere i dati del codice a barre PDF417 da un'immagine, questa guida ti mostra come farlo con la classe **BarCodeReader** in C#. Imparerai un esempio di lettura del codice a barre che gestisce anche il macro PDF417 e può leggere più codici a barre in una singola immagine.

Lavorare con i codici a barre spesso significa gestire diverse fonti di immagini, condizioni di illuminazione variabili e talvolta dati compositi come i segmenti macro PDF417. Questo tutorial copre tutto ciò di cui hai bisogno per decodificare un codice a barre PDF417, estrarre i suoi campi estesi e processare diversi codici a barre dalla stessa immagine. Alla fine avrai un programma console eseguibile che legge i codici a barre da un file immagine e stampa informazioni dettagliate sulla console.

## Cosa ti serve

* .NET 6.0 SDK o versioni successive installate  
* Una versione recente del pacchetto NuGet **Aspose.BarCode for .NET** (o qualsiasi libreria compatibile che fornisca `BarCodeReader` e `DecodeType.MacroPdf417`)  
* Un file immagine che contiene un codice a barre PDF417 o macro PDF417 (l'esempio utilizza `ExtPDF417Meta.png`)  
* Un editor di codice o IDE come Visual Studio 2022  

Non sono richiesti servizi aggiuntivi o API esterne.

## Configurare il progetto per la lettura dei codici a barre

1. **Crea un nuovo progetto console**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **Aggiungi la libreria per i codici a barre**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **Copia l'immagine del codice a barre**  

   Posiziona `ExtPDF417Meta.png` (o qualsiasi immagine che contenga un codice a barre PDF417) nella cartella del progetto.  
   Per questo tutorial assumiamo che il file si trovi in `YOUR_DIRECTORY/ExtPDF417Meta.png`.

Il progetto è ora pronto per compilare ed eseguire l'esempio di lettura del codice a barre.

## Come leggere il codice a barre PDF417 con BarCodeReader

Il nucleo della soluzione è un blocco `using` che crea un'istanza di `BarCodeReader`, specifica `DecodeType.MacroPdf417` e itera su ogni codice a barre rilevato. Il codice seguente è un programma completo e autonomo che puoi incollare in `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
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

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**Perché funziona**:  

* `DecodeType.MacroPdf417` indica al lettore di cercare l'estensione macro del PDF417, che contiene metadati aggiuntivi come ID file, conteggio dei segmenti e timestamp.  
* L'istruzione `using` garantisce che le risorse non gestite (handle di file, buffer di decodifica nativi) vengano rilasciate prontamente.  
* Il ciclo `foreach` elabora automaticamente **tutti** i codici a barre presenti nell'immagine, soddisfacendo il requisito di *leggere più codici a barre*.  

Quando esegui il programma (`dotnet run`), dovresti vedere un output simile al seguente:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

Se l'immagine contiene più di un codice a barre PDF417, il ciclo stampa un blocco separato per ciascun codice a barre, dimostrando così come **leggere più codici a barre** da una singola immagine.

## Leggere più codici a barre da un'immagine

La stessa istanza di `BarCodeReader` può decodificare diversi tipi di codici a barre contemporaneamente. Per ampliare lo scopo da solo macro PDF417 a qualsiasi PDF417 (o anche QR, Code128, ecc.), regola il flag `DecodeType`:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* è una maschera di bit, quindi puoi combinare qualsiasi numero di formati supportati. Questa flessibilità rende lo snippet un **esempio di lettura del codice a barre** che funziona per una vasta gamma di casi d'uso, come la scansione di etichette di prodotto, biglietti o carte d'identità.

## Accedere in modo sicuro ai campi macro PDF417

Macro PDF417 aggiunge un ricco insieme di proprietà estese. Tuttavia, non tutti i codici a barre includono tutti i campi. Accedere a una proprietà mancante può generare una `NullReferenceException`. L'approccio più sicuro è verificare ogni proprietà prima di stamparla:

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*Perché è importante*: Nelle implementazioni reali potresti ricevere codici a barre PDF417 semplici che non contengono dati macro. Il controllo difensivo garantisce che la tua applicazione continui a funzionare senza crash.

## Problemi comuni e migliori pratiche

| Problema | Perché accade | Correzione consigliata |
|----------|----------------|------------------------|
| Il percorso dell'immagine è errato | `BarCodeReader` genera un'eccezione file‑not‑found prima di qualsiasi decodifica | Usa `Path.Combine` e verifica che il file esista con `File.Exists` |
| Immagine a bassa risoluzione | Il decoder non riesce a individuare i bordi del codice a barre, risultando in zero rilevamenti | Fornisci una risoluzione minima di 300 dpi per risultati affidabili |
| Codice a barre ruotato > 45° | Molte librerie assumono un'orientazione verticale | Abilita `reader.RecognitionOptions.RotateImage = true` se il |

## Cosa dovresti imparare dopo?

I tutorial seguenti coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come leggere i codici a barre DataMatrix con Aspose.BarCode per .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Leggi il codice a barre DataMatrix C# – Genera modalità DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Leggi il codice a barre da immagine – Padronanza dell'estrazione della regione del codice a barre in Java con Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}