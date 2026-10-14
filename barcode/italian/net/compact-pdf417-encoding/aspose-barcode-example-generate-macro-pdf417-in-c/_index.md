---
category: general
date: 2026-10-09
description: Scopri come creare un codice a barre PDF417 in C# usando Aspose.BarCode
  – genera un Macro PDF417 con pieno supporto dei metadati.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode c#
- macro pdf417 c#
- aspose barcode c#
- barcode generator c#
lastmod: 2026-10-09
og_description: Scopri come creare un codice a barre PDF417 in C# usando Aspose.BarCode
  – genera un Macro PDF417 con pieno supporto dei metadati, inclusi file ID, segment
  data, timestamp e altro.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: Come creare un codice a barre PDF417 in C# con Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- aspose barcode
- pdf417 barcode
- c# barcode generation
- macro pdf417
title: Come creare un codice a barre PDF417 in C# con Aspose.BarCode
url: /it/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un codice a barre PDF417 in C# con Aspose.BarCode

Se hai bisogno di **creare un codice a barre PDF417 C#** rapidamente e in modo affidabile, questo tutorial ti guida attraverso l'intero processo usando Aspose.BarCode. Vedrai tutte le impostazioni necessarie, dalle dimensioni di base al set completo di campi di metadati Macro PDF417, e terminerai con un'immagine PNG pronta per l'elaborazione successiva.

## Risposte rapide
- **Quale libreria genera codici a barre PDF417?** Aspose.BarCode per .NET.  
- **Quale formato produce l'esempio?** Un'immagine PNG senza perdita.  
- **È necessaria una licenza?** Una versione di prova gratuita funziona per l'esempio; è richiesta una licenza commerciale per la produzione.  
- **Quale versione di .NET è supportata?** .NET 6.0 o successive.  
- **Posso aggiungere metadati al codice a barre?** Sì – Macro PDF417 supporta ID file, conteggio segmenti, timestamp e altro.  

## Cos'è un codice a barre PDF417?
Un codice a barre PDF417 è una simbologia lineare impilata che può codificare fino a circa 1 KB di dati per simbolo e supporta metadati macro opzionali per file multi‑segmento. È costituito da più righe di pattern lineari impilati, consentendo un'elevata capacità di dati mantenendo la leggibilità da parte degli scanner 2‑D standard. Il formato include anche livelli di correzione degli errori per migliorare l'affidabilità, e la funzionalità macro opzionale consente di suddividere file di grandi dimensioni in diversi codici a barre con metadati che aiutano a ricomporli.

## Perché usare Aspose.BarCode per PDF417?
Aspose.BarCode supporta **oltre 50 simbologie di codici a barre** e può generare codici a barre Macro PDF417 con fino a **2 000 colonne**, gestendo file più grandi di **10 MB** senza caricare l'intero payload in memoria. Questa capacità quantificata garantisce che gli scenari aziendali ad alto throughput funzionino senza problemi e offre ampie opzioni di personalizzazione.

## Prerequisiti

- .NET 6.0 (o successivo) installato  
- Visual Studio 2022 o qualsiasi IDE compatibile con C#  
- Una licenza valida per **Aspose.BarCode for .NET** (la versione di prova gratuita funziona per questo esempio)  

Aggiungi il pacchetto NuGet Aspose.BarCode al tuo progetto:

```bash
dotnet add package Aspose.BarCode
```

## Come creare un codice a barre PDF417 in C#?

`BarcodeGenerator` è la classe principale per creare immagini di codici a barre.  
`EncodeTypes.MacroPdf417` seleziona la simbologia Macro PDF417 per la generazione del codice a barre.  
`Save` scrive il codice a barre generato in un file immagine.

Carica il `BarcodeGenerator` con l'enumerazione `EncodeTypes.MacroPdf417` e il testo di destinazione, quindi chiama `Save` – questo è il flusso completo di creazione in tre righe. Il generatore gestisce Unicode automaticamente, e l'istruzione `using` garantisce che le risorse non gestite vengano rilasciate dopo il salvataggio dell'immagine.

### Passo 1: creare l'istanza del generatore di codici a barre C#

La classe `BarcodeGenerator` crea e configura le immagini dei codici a barre.  

Istanzia `BarcodeGenerator` con il valore enum `EncodeTypes.MacroPdf417` e il testo che desideri codificare. Il testo può contenere caratteri Unicode, che la libreria gestisce automaticamente.

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*Perché è importante*: `EncodeTypes.MacroPdf417` indica al motore di produrre un simbolo Macro PDF417, che supporta dati segmentati e metadati a livello di file aggiuntivi. L'istruzione `using` garantisce che le risorse non gestite vengano rilasciate dopo il salvataggio dell'immagine.

### Passo 2: definire l'aspetto di base del codice a barre

`XDimension.Pixels` imposta la dimensione di ogni modulo del codice a barre in pixel.

Un codice a barre Macro PDF417 è composto da moduli quadrati. Controllare la dimensione del modulo e il numero di colonne influisce sia sulla leggibilità sia sulla dimensione del file.

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*Perché è importante*: `XDimension.Pixels` determina la densità visiva; un valore di 2 pixel funziona bene per la visualizzazione su schermo mantenendo l'immagine piccola. Regola il conteggio delle colonne per adattarlo ai vincoli del layout—più colonne creano un codice a barre più largo e più corto.

### Passo 3: impostare i metadati specifici Macro PDF417

`MacroPdf417FileID` identifica il file a cui appartengono tutti i segmenti del codice a barre.

Macro PDF417 estende il formato standard PDF417 con campi che consentono la ricostruzione di file di grandi dimensioni da più segmenti di codice a barre. Ogni campo è opzionale, ma impostarli dimostra tutte le capacità dell'API.

```csharp
    // Unique identifier for the entire file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (zero‑based)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the file
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Logical name of the source file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // 16‑bit CCITT checksum for error detection
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate size of the original file in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;

    // Timestamp when the file was generated
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields for routing information
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the last segment
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Perché è importante*:  
- `MacroPdf417FileID` collega tutti i segmenti appartenenti allo stesso file logico.  
- `MacroPdf417SegmentID` e `MacroPdf417SegmentsCount` consentono al decoder di riordinare correttamente i frammenti.  
- `MacroPdf417Checksum` fornisce un rapido controllo di integrità senza decodificare l'intero payload.  
- `MacroPdf417FileSize` e `MacroPdf417TimeStamp` permettono ai sistemi a valle di verificare che il file ricostruito corrisponda all'originale.  
- `MacroPdf417Addressee` / `MacroPdf417Sender` sono utili in scenari di logistica o scambio di documenti.  
- Impostare `MacroPdf417Terminator` su `Set` contrassegna questo codice a barre come segmento finale, semplificando l'algoritmo di ricostruzione.

### Passo 4: salvare l'immagine del codice a barre generato

`Save` scrive l'immagine del codice a barre nel percorso file specificato.

Infine, salva il codice a barre in un file PNG. Puoi scegliere qualsiasi formato supportato (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`).

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Perché è importante*: PNG conserva i dati pixel senza perdita, garantendo che gli scanner leggano esattamente il pattern di moduli configurato. Cambiare il formato può influire sulla qualità visiva e sulla dimensione del file.

#### Output previsto

Eseguendo il programma completo viene creato un file chiamato **ExtPDF417Meta.png**. Aprendo l'immagine si vede un codice a barre Macro PDF417 rettangolare con il testo “Åspóse.Barcóde©” codificato, e la densità visiva corrisponde alla dimensione X di 2 pixel impostata. Scansionando l'immagine con un lettore compatibile PDF417 vengono restituiti tutti i campi di metadati definiti nel Passo 3.

## Esempio completo funzionante

Copia il codice qui sotto in un nuovo progetto console (`dotnet new console`) e sostituisci `YOUR_DIRECTORY` con un percorso assoluto o relativo che esista sulla tua macchina.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a barcode generator for Macro PDF417 with the desired text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the basic barcode appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // pixel size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol

                // Step 3: Set Macro PDF417 specific metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the generated barcode image
                generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

Esegui il programma (`dotnet run`). Dopo l'esecuzione, verifica che il file PNG compaia nella posizione specificata. Usa qualsiasi app di lettura di codici a barre che supporti Macro PDF417 per confermare che i metadati siano incorporati correttamente.

## Variazioni comuni e casi limite

- **Formati immagine diversi**: Sostituisci `BarCodeImageFormat.Png` con `Jpeg`, `Bmp` o `Tiff` se il tuo sistema a valle preferisce un altro formato.  
- **Modifica della dimensione del modulo**: Valori più grandi di `XDimension.Pixels` migliorano l'affidabilità della scansione su scanner a bassa risoluzione ma aumentano la dimensione dell'immagine.  
- **Segmenti multipli**: Per produrre un file multi‑segmento, genera una serie di codici a barre, incrementa `MacroPdf417SegmentID` per ciascuno e mantieni costante `MacroPdf417FileID`. Solo l'ultimo segmento dovrebbe avere `MacroPdf417Terminator` impostato.  
- **Supporto Unicode**: Il generatore codifica automaticamente i caratteri Unicode; assicurati che la tua stringa di origine utilizzi la codifica UTF‑8 se la leggi da un file esterno.  
- **Gestione degli errori**: Avvolgi il blocco `using` in un try‑catch per catturare `BarCodeException` per parametri non validi (ad esempio, conteggio colonne fuori intervallo).  

## Consigli professionali

- **Prestazioni**: Riutilizza una singola istanza di `BarcodeGenerator` quando crei molti codici a barre con le stesse impostazioni; cambia solo la proprietà `CodeText` tra i salvataggi.  
- **Stima della dimensione del file**: Il campo `MacroPdf417FileSize` dovrebbe corrispondere al conteggio dei byte del payload originale; discrepanze possono causare errori di validazione a valle.  
- **Test**: Convalida i codici a barre generati sia con il decoder integrato di Aspose (`BarCodeReader`) sia con uno scanner di terze parti per garantire l'interoperabilità.  

## Conclusione

Questo esempio di **Aspose.BarCode** ti mostra come **creare un codice a barre PDF417 C#** con supporto completo ai metadati Macro, fornendoti una solida base per costruire pipeline di scambio dati basate su codici a barre robuste.

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come creare un codice a barre – PDF417 compatto con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Come creare la zona silenziosa del codice a barre per Code 16K usando Aspose.BarCode per .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Come creare la zona silenziosa del codice a barre per ITF-14 usando Aspose.BarCode per .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

---

**Ultimo aggiornamento:** 2026-10-09  
**Testato con:** Aspose.BarCode 24.11 per .NET  
**Autore:** Aspose

## Tutorial correlati

- [Come generare l'immagine del codice a barre Pdf417 in C con Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Come creare un codice a barre – PDF417 compatto con Aspose.BarCode](/barcode/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Tutorial del generatore di codici a barre – Come generare il codice a barre Pdf417 in](/barcode/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}