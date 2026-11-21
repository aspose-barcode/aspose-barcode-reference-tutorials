---
category: general
date: 2026-11-20
description: Scopri come creare un codice a barre macro PDF417 in C# usando Aspose.BarCode.
  Questa guida copre i metadati, i parametri e il salvataggio dell'immagine.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- macro PDF417 metadata
- Aspose.BarCode C#
- PDF417 macro parameters
- barcode generator example
language: it
lastmod: 2026-11-20
og_description: Crea un codice a barre macro PDF417 in C# con Aspose.BarCode. Segui
  questo tutorial completo per impostare i metadati, configurare i parametri e esportare
  un PNG.
og_image_alt: Screenshot of a generated macro PDF417 barcode image
og_title: Crea codice a barre macro PDF417 in C# – guida passo passo
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to create macro PDF417 barcode in C# using Aspose.BarCode.
    This guide covers metadata, parameters, and saving the image.
  headline: How to create macro PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to create macro PDF417 barcode in C# using Aspose.BarCode.
    This guide covers metadata, parameters, and saving the image.
  name: How to create macro PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: Expected output
    text: 'Running the program prints a confirmation line similar to:'
  - name: What if I need more than 20 segments?
    text: The `MacroPdf417SegmentsCount` property can be set up to `255`. Ensure the
      receiving system can handle the larger segment count, and consider splitting
      the data into a manageable number of symbols.
  - name: How does the checksum affect scanning?
    text: The CCITT‑16 checksum (`MacroPdf417Checksum`) provides an additional error‑checking
      layer. If a scanner detects a mismatch, it will reject the barcode. You can
      omit the checksum if your workflow does not require it.
  - name: Can I generate a PDF417 macro barcode without Aspose?
    text: Yes, other libraries (e.g., ZXing.Net, Dynamsoft) support PDF417, but macro‑specific
      fields are often missing. Aspose.BarCode offers the most complete implementation
      for macro metadata.
  - name: What image formats are supported for saving?
    text: The `Save` method accepts any format defined in `BarCodeImageFormat`, such
      as `Png`, `Jpeg`, `Gif`, `Bmp`, and `Tiff`. Choose a format that matches your
      downstream processing pipeline.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Come creare un codice a barre macro PDF417 con Aspose.BarCode in C#
url: /it/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un codice a barre macro PDF417 con Aspose.BarCode in C#

Se hai bisogno di **creare un codice a barre macro PDF417** in un'applicazione .NET, questo tutorial mostra i passaggi esatti. Vedrai come configurare i metadati specifici per il macro, regolare le impostazioni visive e salvare il risultato come file PNG.

Generare un codice a barre macro PDF417 è utile quando vuoi suddividere un grande set di dati in più simboli mantenendo un identificatore a livello di file. Nell'esempio seguente utilizziamo la libreria Aspose.BarCode, che fornisce un'API fluida per tutte le funzionalità PDF417.

Al termine di questa guida avrai un programma console pronto all'uso che produce un'immagine di codice a barre contenente tutte le informazioni macro.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6.0 SDK o versioni successive installate.
* Visual Studio 2022 (o qualsiasi IDE che supporti C#).
* Il pacchetto NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`).

Puoi aggiungere il pacchetto con il seguente comando:

```bash
dotnet add package Aspose.BarCode
```

## Passo 1: Inizializzare il generatore di codici a barre per macro PDF417

Il primo passo è istanziare un `BarcodeGenerator` con il valore enum `EncodeTypes.MacroPdf417`. Questo indica alla libreria di trattare il codice a barre come un simbolo macro PDF417.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The generator is now ready for further configuration.
```

*Perché è importante*: Selezionare `MacroPdf417` abilita tutte le proprietà correlate al macro sull'oggetto parametro `Pdf417`.

## Passo 2: Impostare l'aspetto visivo di base

Un codice a barre leggibile inizia con una dimensione del modulo e un conteggio di colonne appropriati. La proprietà `XDimension.Pixels` controlla la larghezza di un singolo modulo, mentre `Pdf417.Columns` definisce quante colonne di dati contiene ogni riga.

```csharp
    // Set module width to 2 pixels.
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

    // Use 5 columns per row – a compact layout for this example.
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
```

Regolare questi valori influisce sia sull'affidabilità dello scanner sia sulla dimensione dell'immagine.

## Passo 3: Definire i dettagli di identificazione del file macro

Il macro PDF417 richiede un identificatore di file, un identificatore di segmento e il conteggio totale dei segmenti. Questi tre campi consentono a uno scanner di ricomporre il set di dati originale.

```csharp
    // Unique file identifier for the whole macro file.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (starting at 0 or 1 based on your protocol).
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the complete file.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Optional human‑readable file name.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

Questi **parametri macro PDF417** sono il cuore della funzionalità macro. Senza di essi uno scanner non può collegare i simboli tra loro.

## Passo 4: Aggiungere metadati macro opzionali

Oltre agli identificatori obbligatori, il formato macro supporta campi aggiuntivi come checksum, dimensione del file, timestamp, destinatario, mittente e un flag terminatore. Fornire questi dati migliora il rilevamento degli errori e fornisce contesto ai sistemi a valle.

```csharp
    // CCITT‑16 checksum example.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate file size in bytes (helps the receiver allocate buffers).
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;

    // Timestamp of when the macro file was generated.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the final segment.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Suggerimento*: Se il tuo flusso di lavoro non richiede un campo particolare, puoi lasciarlo al valore predefinito. La libreria ometterà l'elemento dati corrispondente dal codice a barre.

## Passo 5: Salvare l'immagine del codice a barre

Dopo aver configurato tutti i parametri, chiama `Save` per esportare il codice a barre. L'esempio salva il file PNG in una directory specificata dall'utente.

```csharp
    // Replace with a valid folder on your machine.
    string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

    // Save as PNG – other formats (Jpeg, Gif, etc.) are also supported.
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Al termine del programma, `ExtPDF417Meta.png` contiene un codice a barre macro PDF417 che codifica il testo `"Åspóse.Barcóde©"` insieme a tutti i metadati macro.

## Codice sorgente completo

Di seguito trovi il programma completo e autonomo. Copialo in un nuovo progetto console e avvialo dopo aver installato il pacchetto NuGet Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a macro PDF417 barcode generator.
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Visual appearance.
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

                // Step 3: Core macro identifiers.
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Step 4: Optional macro metadata.
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 5: Export the image.
                string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Macro PDF417 barcode saved to {outputPath}");
            }
        }
    }
}
```

### Output previsto

L'esecuzione del programma stampa una riga di conferma simile a:

```
Macro PDF417 barcode saved to YOUR_DIRECTORY/ExtPDF417Meta.png
```

Aprendo il file PNG si visualizza un codice a barre denso e ad alto contrasto. Scansionandolo con uno scanner compatibile PDF417 si ottiene il testo originale più tutti i campi macro.

## Domande comuni e casi particolari

### E se avessi bisogno di più di 20 segmenti?

La proprietà `MacroPdf417SegmentsCount` può essere impostata fino a `255`. Assicurati che il sistema di destinazione possa gestire un conteggio di segmenti più elevato e considera di suddividere i dati in un numero gestibile di simboli.

### Come influisce il checksum sulla scansione?

Il checksum CCITT‑16 (`MacroPdf417Checksum`) fornisce un ulteriore livello di verifica degli errori. Se uno scanner rileva una discrepanza, rifiuterà il codice a barre. Puoi omettere il checksum se il tuo flusso di lavoro non lo richiede.

### Posso generare un codice a barre PDF417 macro senza Aspose?

Sì, altre librerie (ad es., ZXing.Net, Dynamsoft) supportano PDF417, ma spesso mancano i campi specifici per il macro. Aspose.BarCode offre l'implementazione più completa per i metadati macro.

### Quali formati immagine sono supportati per il salvataggio?

Il metodo `Save` accetta qualsiasi formato definito in `BarCodeImageFormat`, come `Png`, `Jpeg`, `Gif`, `Bmp` e `Tiff`. Scegli un formato che corrisponda al tuo flusso di elaborazione a valle.

## Conclusione

Ora sai come **creare un codice a barre macro PDF417** in C# usando Aspose.BarCode. Il tutorial ha coperto l'inizializzazione del generatore, le impostazioni visive, gli identificatori di file macro, i metadati opzionali e l'esportazione dell'immagine. Con questa base puoi incorporare macro PDF nei sistemi di inventario, nel tracciamento dei documenti o in qualsiasi scenario che richieda la trasmissione di dati segmentati.

I prossimi passi includono sperimentare con valori diversi di `XDimension` per una risoluzione più alta, aggiungere regolazioni del livello di correzione degli errori o integrare il codice a barre in un'API web che restituisce direttamente lo stream PNG. Per argomenti correlati, consulta i tutorial su **barcode generator example**, **PDF417 macro parameters** e **macro PDF417 metadata** handling.

Buona programmazione!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [How to create PDF417 barcode image in C# with Macro PDF417 options](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}