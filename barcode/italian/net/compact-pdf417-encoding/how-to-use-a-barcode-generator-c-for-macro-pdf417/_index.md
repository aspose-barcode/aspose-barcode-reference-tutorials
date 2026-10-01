---
category: general
date: 2026-08-22
description: Il tutorial su come generare barcode C# mostra come creare un codice
  a barre Macro PDF417 con metadati e salvarlo come PNG usando Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- Macro PDF417
- Aspose.BarCode
- C# barcode library
- PDF417 barcode
- barcode metadata
language: it
lastmod: 2026-08-22
og_description: Il generatore di codici a barre C# ti consente di creare un codice
  a barre Macro PDF417 con metadati a livello di file completi e di esportarlo come
  PNG. Segui questa guida per implementare la soluzione.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C#
og_title: generatore di codici a barre C# – crea codici a barre Macro PDF417 passo
  dopo passo
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to create a Macro PDF417 barcode
    with metadata and save it as PNG using Aspose.BarCode.
  headline: How to use a barcode generator C# for Macro PDF417
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Come utilizzare un generatore di codici a barre C# per Macro PDF417
url: /it/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come utilizzare un generatore di codici a barre C# per Macro PDF417

Se hai bisogno di un **barcode generator C#** in grado di generare un simbolo Macro PDF417 con metadati a livello di file, questa guida fornisce una soluzione completa, pronta all'uso. Vedrai come configurare l'aspetto del codice a barre, incorporare le informazioni macro come ID file e conteggio dei segmenti, e infine salvare il risultato come immagine PNG.

L'esempio utilizza la libreria Aspose.BarCode, una **C# barcode library** ampiamente adottata che supporta l'intero set di funzionalità PDF417. Non sono richiesti servizi esterni e il codice funziona con .NET 6 o versioni successive.

## Prerequisiti

* .NET 6 SDK (o qualsiasi versione successiva) installato.  
* Visual Studio 2022, VS Code, o un altro IDE C#.  
* Un riferimento NuGet a **Aspose.BarCode** (`dotnet add package Aspose.BarCode`).

Comprendere la sintassi di base di C# e il concetto dei codici a barre PDF417 ti aiuterà a seguire i passaggi, ma il tutorial spiega in dettaglio ogni opzione di configurazione.

## Cosa copre il tutorial

* Inizializzare un'istanza di **barcode generator C#** per il formato Macro PDF417.  
* Regolare i parametri visivi come X‑dimension e il numero di colonne.  
* Fornire i campi a livello di file Macro PDF417: file ID, segment ID, segment count, file name, checksum, file size, timestamp, addressee, sender e terminator.  
* Salvare il simbolo generato come file PNG.  
* Suggerimenti per gestire casi limite come file di grandi dimensioni o timestamp personalizzati.

Alla fine di questo articolo avrai un programma autonomo che produce un codice a barre Macro PDF417 pienamente conforme.

## Passo 1: Creare l'istanza del barcode generator C# 

La prima operazione è istanziare `BarcodeGenerator` con il valore enum `EncodeTypes.MacroPdf417` e il testo che desideri codificare. Il costruttore accetta anche la stringa payload, che diventa la parte dati del codice a barre macro.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for Macro PDF417
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent configuration goes here
}
```

**Perché è importante** – Il flag `EncodeTypes.MacroPdf417` indica ad Aspose.BarCode di trattare il simbolo come un macro barcode, abilitando i campi aggiuntivi che seguono. Senza questo flag la libreria genererebbe un normale codice a barre PDF417 privo di metadati a livello di file.

## Passo 2: Regolare l'aspetto base del codice a barre (impostazioni visive PDF417)

La chiarezza visiva è fondamentale per una scansione affidabile. Due parametri comuni sono la larghezza del modulo (`XDimension`) e il numero di colonne. Impostare questi valori bilancia dimensione e leggibilità.

```csharp
    // Step 2: Adjust basic barcode appearance
    generator.Parameters.Barcode.XDimension.Pixels = 2;   // width of a single module
    generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol
```

- `XDimension.Pixels` controlla la larghezza di ogni barra nera/bianca. Un valore di **2** funziona bene per la maggior parte delle stampanti di etichette.  
- `Pdf417.Columns` definisce quante colonne utilizzerà il codice a barre. Cinque colonne producono un simbolo compatto senza sacrificare la capacità dei dati.

## Passo 3: Definire le informazioni a livello di file Macro PDF417

Macro PDF417 estende il formato PDF417 standard con campi che descrivono come un file di grandi dimensioni è suddiviso in più segmenti di codice a barre. Fornire questi campi garantisce che gli scanner a valle possano ricostruire il file originale.

```csharp
    // Step 3: Define Macro PDF417 file‑level information
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;          // unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;            // current segment number (0‑indexed)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;       // total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";      // optional logical file name
```

- `MacroPdf417FileID` deve essere lo stesso per ogni segmento appartenente allo stesso file logico.  
- `MacroPdf417SegmentID` incrementa da **0** a `SegmentsCount‑1`.  
- `MacroPdf417SegmentsCount` indica al decoder quante parti aspettarsi.  
- `MacroPdf417FileName` è opzionale ma utile per un'identificazione leggibile dall'uomo.

## Passo 4: Impostare metadati macro aggiuntivi

Oltre alle informazioni di base del file, la specifica consente campi extra come checksum, dimensione del file, timestamp, destinatario, mittente e un flag terminatore. Popolare questi campi migliora l'integrità dei dati e la tracciabilità.

```csharp
    // Step 4: Set additional macro metadata
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                     // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;                  // file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2024, 4, 1);
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

- `MacroPdf417Checksum` fornisce un checksum CCITT a 16 bit per l'intero file; il decoder può verificare l'integrità dopo la ricostruzione.  
- `MacroPdf417FileSize` dovrebbe riflettere il conteggio esatto dei byte del file originale; valori superiori a `2^31‑1` richiedono un campo a 64 bit, che Aspose gestisce automaticamente.  
- `MacroPdf417TimeStamp` registra quando il codice a barre è stato generato. Usa UTC per evitare ambiguità di fuso orario.  
- `MacroPdf417Addressee` e `MacroPdf417Sender` sono stringhe libere che possono contenere informazioni di instradamento.  
- `MacroPdf417Terminator` segnala che questo è il segmento finale; impostalo su `Set` per l'ultimo pezzo, altrimenti lascia il valore predefinito (`NotSet`).  

**Suggerimento per casi limite** – Se la dimensione del tuo file supera i 4 GB, suddividi il contenuto in più segmenti macro e regola `SegmentsCount` di conseguenza. La libreria gestirà il campo di grandi dimensioni senza overflow.

## Passo 5: Salvare il codice a barre come immagine PNG

L'ultimo passaggio scrive il simbolo generato su disco. PNG preserva le dimensioni esatte dei pixel ed è ampiamente supportato dall'hardware di scansione.

```csharp
    // Step 5: Save the generated barcode as a PNG image
    generator.Save("YOUR_DIRECTORY/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

Sostituisci `YOUR_DIRECTORY` con un percorso assoluto o relativo a cui il processo in esecuzione può scrivere. L'enum `BarCodeImageFormat.Png` garantisce un output senza perdita.

**Perché PNG?** – I formati raster come PNG mantengono i bordi dei moduli nitidi, il che è essenziale per gli scanner che si basano su bordi ad alto contrasto. Se ti serve un formato vettoriale, Aspose supporta anche `Pdf` e `Svg`.

## Esempio completo eseguibile

Di seguito trovi il programma completo che puoi copiare in un'applicazione console. Include le direttive `using` necessarie e un metodo `Main`.

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
            // Create a barcode generator for Macro PDF417 with sample payload
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
            {
                // Adjust visual appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // Define macro file‑level fields
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Add optional metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2024, 4, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Export to PNG
                generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

### Output previsto

Eseguendo il programma viene creato un file chiamato **MacroPdf417.png** nella directory di lavoro del progetto. Aprendo l'immagine si vede un codice a barre PDF417 compatto con i campi macro incorporati. Scansionando l'immagine con un lettore compatibile PDF417 (ad es., ZXing, decoder Aspose.BarCode) si ottiene il payload originale `"Sample text"` insieme ai metadati macro.

## Domande comuni e risoluzione dei problemi

| Question | Answer |
|----------|--------|
| *Cosa fare se il codice a barre è troppo grande per l'etichetta target?* | Riduci `XDimension.Pixels` o aumenta `Pdf417.Columns`. Entrambi i parametri influenzano le dimensioni complessive. |
| *Posso generare un'immagine vettoriale invece di PNG?* | Sì. Chiama `generator.Save("MacroPdf417.svg", BarCodeImageFormat.Svg);` per un output scalabile. |
| *Come verificare il checksum dopo la scansione?* | Il decoder Aspose.BarCode valida automaticamente `MacroPdf417Checksum` e segnala le discrepanze nell'oggetto `MacroPdf417Result`. |
| *La libreria è compatibile con .NET Core?* | Il pacchetto NuGet supporta .NET Standard 2.0+, che copre .NET Core, .NET 5, .NET 6 e versioni successive. |
| *Cosa fare se devo incorporare dati binari invece di testo?* | Converti il payload binario in Base64 o utilizza la sovraccarico `EncodeTypes.MacroPdf417` che accetta un array di byte. |

## Suggerimenti professionali per l'uso in produzione

* **Cache the generator** – 

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come creare un codice a barre – PDF417 compatto con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Come leggere un codice a barre da PDF in Java usando Aspose.BarCode](/barcode/english/java/document-barcode-recognition/recognizing-barcodes-from-pdf/)
- [Creare Codabar Barcode con Aspose.Barcode – API Generator & Reader](/barcode/english/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}