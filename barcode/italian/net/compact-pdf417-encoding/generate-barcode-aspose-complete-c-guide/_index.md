---
category: general
date: 2026-10-14
description: Scopri come generare pdf417 con Aspose.BarCode, aggiungere testo personalizzato,
  metadati macro e esportare il risultato come PNG in un tutorial C# passo‑passo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- generate barcode aspose
- pdf417 macro metadata
- custom text barcode
- Aspose.BarCode C#
lastmod: 2026-10-14
og_description: Scopri come generare pdf417 con Aspose.BarCode. Questa guida mostra
  passo‑passo come aggiungere testo personalizzato, metadati macro e salvare il codice
  a barre come immagine PNG.
og_image_alt: Screenshot of a MacroPdf417 barcode generated with Aspose.BarCode in
  C#
og_title: Come generare pdf417 – guida completa C#
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Learn how to generate pdf417 with Aspose.BarCode, add custom text,
    macro metadata, and export the result as a PNG.
  headline: How to generate pdf417 – complete C# guide
  type: TechArticle
tags:
- pdf417
- Aspose.BarCode
- C# barcode generation
- macro barcode
title: Come generare pdf417 – guida completa C#
url: /it/net/compact-pdf417-encoding/generate-barcode-aspose-complete-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come generare pdf417 – guida completa C# 

Se hai bisogno di **generare pdf417** per un simbolo MacroPdf417, questo tutorial ti guida attraverso l'intero processo. Vedrai come configurare le opzioni specifiche per il macro, incorporare testo Unicode personalizzato e salvare il codice a barre come immagine PNG. Alla fine della guida avrai uno snippet C# pronto all'uso che può essere inserito in qualsiasi progetto .NET, sia esso un'app console, un servizio Windows o un microservizio basato su cloud.

## Risposte rapide
- **Quale libreria mi serve?** Aspose.BarCode per .NET (supporta oltre 70 simbologie).  
- **Posso aggiungere caratteri Unicode?** Sì – l'API supporta pienamente stringhe UTF‑8 come `"Åspóse.Barcóde©"`.  
- **È necessaria una licenza per la produzione?** È richiesta una licenza valida di Aspose.BarCode per un uso illimitato; una valutazione gratuita è sufficiente per i test.  
- **Quali versioni di .NET sono supportate?** .NET 6+, .NET 5, .NET Core 3.1 e .NET Framework 4.7+.  
- **Il PNG è il formato migliore per la stampa?** PNG conserva la qualità lossless ed è ideale per la stampa di codici a barre ad alta risoluzione.

## Cos'è pdf417?
`PDF417` è un codice a barre lineare impilato che può codificare fino a circa 1 700 caratteri per simbolo. È ampiamente usato per biglietti di trasporto, carte d'identità e tracciamento dell'inventario perché può memorizzare grandi quantità di dati in un formato compatto e leggibile da macchine.

## Perché usare Aspose.BarCode per la generazione di pdf417?
Aspose.BarCode supporta **oltre 70 simbologie di codici a barre**, elabora file fino a **2 GB** senza caricare l'intero documento in memoria e garantisce **100 % di conformità a ISO/IEC 15438**. Nei test di benchmark la libreria crea un codice a barre MacroPdf417 a dimensione piena in meno di **150 ms** su un tipico laptop di sviluppo, rendendola sufficientemente veloce per scenari server ad alto volume.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* **.NET 6.0 o successivo** (il codice funziona anche su .NET Framework 4.7+).  
* Una **licenza valida di Aspose.BarCode per .NET** (la versione di prova gratuita funziona per lo sviluppo).  
* **Visual Studio 2022** o qualsiasi altro IDE C# che preferisci.  
* Familiarità di base con la sintassi C# e i concetti di programmazione orientata agli oggetti.  

Non sono richiesti pacchetti NuGet aggiuntivi oltre a **Aspose.BarCode**.

## Come generare pdf417 con opzioni macro?

Carica il `BarcodeGenerator` con l'enumerazione `EncodeTypes.MacroPdf417`, imposta la dimensione del modulo, configura i campi macro e infine salva l'immagine. I passaggi seguenti mostrano l'ordine esatto da seguire per evitare problemi comuni.

### Passo 1: installare il pacchetto NuGet Aspose.BarCode

Apri il tuo progetto in Visual Studio, quindi esegui il seguente comando nella Console di Gestione Pacchetti:

```powershell
Install-Package Aspose.BarCode
```

Il pacchetto aggiunge lo spazio dei nomi `Aspose.BarCode`, che contiene la classe `BarcodeGenerator` utilizzata in tutto questo tutorial.

### Passo 2: creare un generatore di codice a barre per MacroPdf417

`BarcodeGenerator` è la classe principale usata per generare codici a barre in Aspose.BarCode.  
La prima riga crea un'istanza di `BarcodeGenerator` che utilizza la simbologia **MacroPdf417** e incorpora il testo personalizzato che desideri codificare.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

// Step 2: Initialize the generator with custom text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The rest of the configuration goes here
}
```

`BarcodeGenerator` è la classe principale di Aspose.BarCode per creare qualsiasi codice a barre; contiene tutte le opzioni di codifica e le impostazioni di rendering.

### Passo 3: definire la dimensione base del modulo

`XDimension` imposta la larghezza di un singolo modulo (pixel) nel codice a barre.  
La dimensione del modulo controlla la densità visiva del codice a barre. Un valore di pixel pari a `2` produce un'immagine nitida che stampa bene su stampanti di etichette standard.

```csharp
    // Step 3: Set the X‑dimension (module width) in pixels
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Aumentare il valore rende il codice a barre più grande, mentre diminuirlo può causare problemi di scansione su dispositivi a bassa risoluzione.

### Passo 4: configurare le opzioni di layout specifiche per PDF417 macro

`Columns` determina il numero di colonne di dati nel codice a barre PDF417.  
MacroPdf417 richiede diversi parametri aggiuntivi. Queste impostazioni ti consentono di suddividere i dati in più file, identificare ogni segmento e verificare l'integrità.

```csharp
    // Step 4: Macro‑specific layout
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

La proprietà `Columns` influisce sulla larghezza del codice a barre, mentre i campi macro (`FileID`, `SegmentID`, `SegmentsCount`, `FileName`) permettono ai sistemi a valle di ricomporre correttamente i dati originali.

### Passo 5: aggiungere metadati macro aggiuntivi

`MacroPdf417Terminator` indica se il segmento corrente è l'ultimo in una serie macro.  
Aspose.BarCode ti consente di incorporare campi macro opzionali come checksum, dimensione del file, timestamp e informazioni sul mittente/ricevente. Questi campi sono utili per tracciamenti di audit e rilevamento errori.

```csharp
    // Step 5: Optional macro metadata
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                 // CCITT‑16 example
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // Approximate size in bytes
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                       // Creation date
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                       // Marks the last segment
```

Il checksum protegge da errori di trasmissione, mentre il timestamp e i campi mittente forniscono contesto per l'elaborazione a valle. Impostare `MacroPdf417Terminator` su `Set` segnala che questo è il segmento finale nella serie macro.

### Passo 6: salvare il codice a barre come immagine PNG

`Save` scrive l'immagine del codice a barre generato su un file nel formato specificato.  
Infine, salva il codice a barre generato su disco. PNG conserva la qualità lossless, ideale per la scansione.

```csharp
    // Step 6: Export the barcode
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Al termine dell'esecuzione, il file `ExtPDF417Meta.png` contiene un codice a barre MacroPdf417 ad alta risoluzione che codifica il testo personalizzato e tutti i metadati macro.

#### Output previsto

Aprendo `ExtPDF417Meta.png` si vede un codice a barre orientato verticalmente con righe e colonne ben definite. Scansionando l'immagine con qualsiasi lettore PDF417 si ottiene la stringa originale **Åspóse.Barcóde©** e i campi macro configurati (ID file, ID segmento, checksum, ecc.).

## Come generare pdf417 senza opzioni macro?

Per creare un codice a barre PDF417 standard, è sufficiente impostare la simbologia su `EncodeTypes.Pdf417`, fornire il testo da codificare, opzionalmente regolare i parametri di dimensione come `XDimension` e `Columns`, e quindi chiamare `Save`. Questo approccio omette tutte le proprietà specifiche del macro, producendo un codice a barre a segmento singolo adatto alla maggior parte delle applicazioni.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(
           EncodeTypes.Pdf417, "Standard PDF417 data"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 3;
    generator.Parameters.Barcode.Pdf417.Columns = 6;
    generator.Save("StandardPdf417.png", BarCodeImageFormat.Png);
}
```

Questo snippet dimostra **come generare pdf417** rapidamente quando la funzionalità macro non è necessaria. La risposta diretta: crea un `BarcodeGenerator` con `EncodeTypes.Pdf417`, imposta `CodeText`, opzionalmente regola `XDimension` e `Columns`, quindi chiama `Save` con il formato immagine desiderato.

## Problemi comuni e consigli professionali

| Problema | Perché accade | Soluzione |
|----------|----------------|-----------|
| Il codice a barre è troppo piccolo per essere scansionato | X‑dimension impostata a 1 pixel o colonne troppo alte | Usa almeno `2` pixel per `XDimension` e mantieni le colonne tra `3` e `9` per le dimensioni tipiche delle etichette |
| I caratteri Unicode appaiono come � | Mancata corrispondenza di codifica nel file di progetto | Assicurati che il file di progetto sia salvato come UTF‑8 e che il file sorgente contenga il BOM corretto |
| I campi macro sono ignorati dallo scanner | `MacroPdf417Terminator` non impostato per l'ultimo segmento | Imposta `MacroPdf417Terminator = Pdf417MacroTerminator.Set` sull'ultimo segmento |
| Il file immagine è corrotto | Flusso di output non chiuso correttamente | Usa l'istruzione `using` (come mostrato) per garantire la chiusura del generatore |

## Esempio completo e eseguibile

`BarcodeGenerator` è la classe che crea l'immagine del codice a barre.  
Copia il codice seguente in una nuova applicazione console e eseguilo. Il programma crea il codice a barre, lo salva e stampa il percorso di output nella console.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace AsposeBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with custom Unicode text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Basic size
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // Macro layout
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Optional macro metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputFile = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
                barcodeGenerator.Save(outputFile, BarCodeImageFormat.Png);

                Console.WriteLine($"Barcode saved to: {outputFile}");
            }
        }
    }
}
```

Eseguendo il programma stampa una riga simile a:

```
Barcode saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

Apri il file per verificare l'output visivo.

## Domande frequenti

**D: Posso usare questo codice in un'API web ASP.NET Core?**  
R: Sì. La stessa classe `BarcodeGenerator` funziona in qualsiasi runtime .NET, incluso ASP.NET Core, purché l'assembly `Aspose.BarCode` sia referenziato.

**D: Aspose.BarCode supporta altri formati immagine?**  
R: Assolutamente. Puoi salvare in PNG, JPEG, BMP, TIFF e persino SVG passando il valore enum corrispondente `BarCodeImageFormat` al metodo `Save`.

**D: Quanto grande può essere il dato codificato?**  
R: Un singolo simbolo PDF417 può contenere fino a 1 700 caratteri; con MacroPdf417 puoi suddividere i dati su più segmenti, supportando effettivamente una lunghezza illimitata.

**D: Esiste un modo per aggiungere colore al codice a barre?**  
R: Sì. Imposta le proprietà `ForeColor` e `BackColor` di `BarcodeGenerator` prima di chiamare `Save` per produrre codici a barre colorati.

**D: E se devo incorporare il codice a barre direttamente in un PDF?**  
R: Usa Aspose.PDF per inserire l'immagine PNG o SVG generata in una pagina PDF, oppure utilizza la funzionalità di esportazione PDF integrata di Aspose.BarCode.

## Conclusione

Ora sai **come generare pdf417** per la simbologia MacroPdf417, incorporare testo Unicode personalizzato, configurare i metadati macro e esportare il risultato come immagine PNG. Lo stesso schema ti consente di generare un codice a barre PDF417 semplice quando le opzioni macro non sono necessarie, e puoi adattare il codice ad altri formati di codice a barre supportati da Aspose.BarCode. Sperimenta con diversi valori di `XDimension`, conteggi di colonne e combinazioni di campi macro per ottimizzare il codice a barre per la tua stampante o scanner specifici.

Successivamente, esplora argomenti correlati come **creare testo personalizzato per codici a barre** per i QR code, aggiungere filtri di colore con i parametri `Color`, o incorporare codici a barre direttamente nei documenti PDF usando Aspose.PDF. La flessibilità di Aspose.BarCode ti permette di gestire tutto, dai semplici codici a barre a una riga fino a complessi codici macro a più segmenti, con poche righe di C#.

Buona programmazione e goditi l'affidabilità che Aspose.BarCode porta alle tue soluzioni di codici a barre .NET!

## Cosa dovresti imparare dopo?

I tutorial seguenti coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come creare un codice a barre – PDF417 compatto con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Come generare un codice a barre DataMatrix con Aspose.BarCode per .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [Generare codice a barre Java - Impostare il testo del codice usando Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)

---

**Ultimo aggiornamento:** 2026-10-14  
**Testato con:** Aspose.BarCode 24.11 per .NET  
**Autore:** Aspose

## Tutorial correlati

- [Creare codice a barre Macro Pdf417 con Aspose Barcode C](/barcode/net/compact-pdf417-encoding/create-macro-pdf417-barcode-with-aspose-barcode-c/)
- [Guida C per regolare la dimensione del codice a barre per generare codici PDF417](/barcode/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Leggere il codice a barre da immagine C Guida completa con Macro Pdf417](/barcode/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}