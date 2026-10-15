---
category: general
date: 2026-10-15
description: Scopri come generare un codice a barre PDF417 in C# utilizzando i parametri
  Macro‑PDF417, impostare le dimensioni del codice a barre e salvarlo come PNG. Esempio
  di codice completo incluso.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417 barcode
- C# PDF417 barcode
- Macro PDF417 parameters
- set barcode dimensions
- barcode image format
- barcode checksum
language: it
lastmod: 2026-10-15
og_description: Come generare un codice a barre PDF417 in C# con configurazione completa
  Macro‑PDF417, controllo delle dimensioni e output PNG. Segui l'esempio completo.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Come generare il codice a barre PDF417 in C# – guida passo passo
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to generate PDF417 barcode in C# using Macro‑PDF417 parameters,
    set barcode dimensions, and save as PNG. Complete code example included.
  headline: How to generate PDF417 barcode in C# with Macro‑PDF417 settings
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- Aspose.Barcode
title: Come generare un codice a barre PDF417 in C# con impostazioni Macro‑PDF417
url: /it/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-macro-pdf417-settin/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come generare un codice a barre PDF417 in C# con le impostazioni Macro‑PDF417

Se hai bisogno di **come generare un codice a barre PDF417** per un flusso di lavoro documentale, questa guida ti mostra i passaggi esatti. Vedrai come configurare i parametri Macro‑PDF417, impostare le dimensioni del codice a barre e esportare il risultato come immagine PNG—tutto in un unico programma C# eseguibile.

Generare un codice a barre PDF417 non richiede librerie multiple o post‑processing complessi. Utilizzando Aspose.Barcode per .NET puoi controllare ogni aspetto del codice a barre, dalla larghezza del modulo al checksum, e produrre un'immagine ad alta qualità pronta per la stampa o la scansione.

## Prerequisiti

* .NET 6.0 (o successivo) SDK installato  
* Visual Studio 2022 o qualsiasi IDE C# tu preferisca  
* Pacchetto NuGet Aspose.Barcode per .NET (`Install-Package Aspose.Barcode`)  

Questi prerequisiti garantiscono che il codice venga compilato senza configurazioni aggiuntive.

## Passo 1: Creare un generatore di codici a barre per un codice Macro‑PDF417

La prima operazione crea un'istanza di `BarcodeGenerator` che utilizza il formato `EncodeTypes.MacroPdf417`. Il costruttore riceve i dati che desideri codificare—in questo caso, la stringa `"Sample text"`.

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

// Step 1: Initialize the generator with Macro‑PDF417 and data to encode
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent steps configure the barcode
```

La creazione del generatore imposta l'oggetto interno `Parameters`, che utilizzerai per regolare le proprietà del **codice a barre PDF417 C#**.

## Passo 2: Impostare l'aspetto di base del codice a barre – impostare le dimensioni del codice a barre

Controllare le dimensioni visive di un codice a barre migliora l'affidabilità della scansione. La proprietà `XDimension.Pixels` definisce la larghezza del modulo (punto), mentre `Pdf417.Columns` determina quante colonne conterrà il codice a barre.

```csharp
    // Step 2: Define module width and column count
    generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width in pixels
    generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

Impostare queste dimensioni garantisce che il codice a barre si adatti alle dimensioni tipiche delle etichette e soddisfi le specifiche dello scanner.

## Passo 3: Fornire l'identificazione del file Macro‑PDF417

Macro‑PDF417 estende il codice a barre PDF417 standard con metadati a livello di file. È necessario assegnare un ID file unico, un ID segmento, il conteggio totale dei segmenti e un nome file leggibile dall'uomo.

```csharp
    // Step 3: Assign macro file identification
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";
```

Questi **parametri Macro PDF417** consentono ai sistemi a valle di ricostruire il file originale da più segmenti di codice a barre.

## Passo 4: Aggiungere metadati macro aggiuntivi – includere il checksum del codice a barre

Oltre all'identificazione, Macro‑PDF417 può memorizzare checksum, dimensione del file, timestamp, destinatario, mittente e un flag di terminazione. Fornire un checksum migliora i controlli di integrità dei dati durante la decodifica.

```csharp
    // Step 4: Populate extra macro metadata
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;               // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 850_000;             // file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = DateTime.UtcNow;   // UTC timestamp
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "Acme Corp";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "John Doe";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

Includere un **checksum del codice a barre** e altri metadati rende il codice a barre auto‑descrittivo, il che è prezioso per le pipeline di elaborazione documenti automatizzate.

## Passo 5: Salvare il codice a barre generato come immagine PNG – scegliere il formato immagine del codice a barre

L'ultimo passaggio scrive il codice a barre su un file. Il metodo `Save` accetta un percorso di file e un enum `BarCodeImageFormat`. PNG fornisce compressione senza perdita, preservando bordi nitidi per una scansione affidabile.

```csharp
    // Step 5: Export the barcode to PNG
    generator.Save("C:/Barcodes/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

Dopo l'esecuzione, il file `MacroPdf417.png` contiene un codice a barre PDF417 nitido pronto per l'inserimento in PDF, la stampa su etichette o la visualizzazione su schermi.

## Output previsto

Aprendo `C:/Barcodes/MacroPdf417.png` si visualizza un codice a barre rettangolare con il testo codificato “Sample text”. Il codice a barre include i metadati macro impostati, che puoi verificare con qualsiasi scanner PDF417 che supporti Macro‑PDF417. Le dimensioni dell'immagine riflettono la larghezza del modulo (2 px) e il numero di colonne (5), risultando in un codice a barre compatto ma leggibile.

## Variazioni comuni e casi limite

| Situazione | Adeguamento |
|-----------|------------|
| **Lunghezza dati diversa** | Sostituisci `"Sample text"` con qualsiasi stringa UTF‑8; il generatore regola automaticamente le dimensioni del codice a barre. |
| **Risoluzione più alta** | Aumenta `XDimension.Pixels` a 3 o 4 per moduli più grandi, utile per stampanti a bassa risoluzione. |
| **Più segmenti** | Modifica `MacroPdf417SegmentsCount` per corrispondere al numero totale di parti di codice a barre che intendi generare. |
| **Formato immagine alternativo** | Usa `BarCodeImageFormat.Jpeg` o `BarCodeImageFormat.Bmp` se il tuo sistema a valle preferisce questi formati. |
| **Correzione errore personalizzata** | Modifica `generator.Parameters.Barcode.Pdf417.ErrorLevel` (intervallo 0‑8) per bilanciare la densità dei dati con la tolleranza agli errori. |

**Consiglio professionale:** Valida sempre il codice a barre generato con uno scanner fisico prima di distribuirlo in produzione. Gli scanner possono avere limiti specifici del firmware sulla larghezza del modulo o sul numero di colonne.

## Codice sorgente completo

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace Pdf417MacroDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator for Macro‑PDF417 with sample data
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
            {
                // Set visual dimensions
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // column count

                // Provide macro file identification
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";

                // Add macro metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;               // CCITT‑16 checksum
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 850_000;             // file size in bytes
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = DateTime.UtcNow;   // timestamp
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "Acme Corp";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "John Doe";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Export as PNG
                generator.Save("C:/Barcodes/MacroPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("PDF417 barcode generated successfully.");
        }
    }
}
```

Eseguendo questo programma si crea `MacroPdf417.png` nella cartella `C:/Barcodes`. La console conferma la generazione avvenuta con successo.

## Conclusione

Ora sai **come generare un codice a barre PDF417** in C# con controllo completo Macro‑PDF417, come **impostare le dimensioni del codice a barre**, come incorporare **checksum del codice a barre** e altri metadati macro, e come esportare il risultato utilizzando un **formato immagine del codice a barre** scelto. L'esempio completo può essere copiato in qualsiasi progetto .NET, modificato per diversi payload di dati e integrato in pipeline di automazione documentale più ampie.

### Prossimi passi

* Esplora i livelli di correzione errori del **codice a barre PDF417 C#** per migliorare l'affidabilità della scansione.  
* Combina più segmenti Macro‑PDF417 per codificare file di grandi dimensioni come PDF o immagini.  
* Passa al **formato immagine del codice a barre** SVG per grafica vettoriale scalabile nelle applicazioni web.  

Sentiti libero di sperimentare con i parametri e condividere i tuoi risultati nei commenti o nei forum della community. Buon coding!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche illustrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Genera codice a barre C# con Macro PDF417 – esempio completo](/barcode/english/net/compact-pdf417-encoding/generate-barcode-c-with-macro-pdf417-full-example/)
- [Come generare PDF417 Barcode – Guida completa alla programmazione](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)
- [Come generare PDF417 barcode in C# con dimensioni personalizzate](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}