---
category: general
date: 2026-08-09
description: Esempio di codice a barre Aspose che mostra come utilizzare un generatore
  di codici a barre C# per creare un Macro PDF417 con pieno supporto dei metadati.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode example
- barcode generator c#
language: it
lastmod: 2026-08-09
og_description: L'esempio di barcode Aspose dimostra l'utilizzo di un generatore di
  barcode C# per produrre un barcode Macro PDF417 che include l'ID del file, i dati
  del segmento, il timestamp e altri metadati.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: Esempio di codice a barre Aspose – crea Macro PDF417 con C#
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- Macro PDF417
title: 'Esempio di codice a barre Aspose: genera Macro PDF417 in C#'
url: /it/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Esempio di Aspose barcode: generare Macro PDF417 in C#

Se hai bisogno di un **aspose barcode example** che crei un Macro PDF417 barcode, questa guida ti mostra come farlo con un **barcode generator C#**. Vedrai tutte le impostazioni necessarie, dalle dimensioni di base all'intero set di campi di metadati Macro PDF417, e otterrai un'immagine PNG pronta per l'elaborazione successiva.

Il tutorial copre l'intero flusso di lavoro, spiega perché ogni parametro è importante e fornisce un esempio di codice pronto all'uso. Non sono necessari riferimenti esterni; puoi copiare il codice, regolare i valori e eseguirlo immediatamente.

## Prerequisiti

- .NET 6.0 (o successivo) installato  
- Visual Studio 2022 o qualsiasi IDE compatibile con C#  
- Una licenza valida per **Aspose.BarCode for .NET** (la versione di prova gratuita funziona per questo esempio)  

Aggiungi il pacchetto NuGet Aspose.BarCode al tuo progetto:

```bash
dotnet add package Aspose.BarCode
```

## Passo 1: Creare l'istanza del barcode generator C#

Il primo passo è istanziare `BarcodeGenerator` con il valore enum `EncodeTypes.MacroPdf417` e il testo che desideri codificare. Il testo può contenere caratteri Unicode, che la libreria gestisce automaticamente.

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*Perché è importante*: `EncodeTypes.MacroPdf417` indica al motore di produrre un simbolo Macro PDF417, che supporta dati segmentati e metadati a livello di file aggiuntivi. L'istruzione `using` garantisce che le risorse non gestite vengano rilasciate dopo il salvataggio dell'immagine.

## Passo 2: Definire l'aspetto di base del codice a barre

Un Macro PDF417 barcode è composto da moduli quadrati. Controllare la dimensione del modulo e il numero di colonne influisce sia sulla leggibilità sia sulla dimensione del file.

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*Perché è importante*: `XDimension.Pixels` determina la densità visiva; un valore di 2 pixel funziona bene per la visualizzazione su schermo mantenendo l'immagine piccola. Regola il conteggio delle colonne per adattarlo ai vincoli del tuo layout—più colonne creano un codice a barre più largo e più corto.

## Passo 3: Impostare i metadati specifici di Macro PDF417

Macro PDF417 estende il formato PDF417 standard con campi che consentono la ricostruzione di file di grandi dimensioni da più segmenti di codice a barre. Ogni campo è opzionale, ma impostarli dimostra tutte le capacità dell'API.

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
- `MacroPdf417FileSize` e `MacroPdf417TimeStamp` consentono ai sistemi a valle di verificare che il file ricostruito corrisponda all'originale.  
- `MacroPdf417Addressee` / `MacroPdf417Sender` sono utili in scenari di logistica o scambio di documenti.  
- Impostare `MacroPdf417Terminator` su `Set` contrassegna questo codice a barre come segmento finale, semplificando l'algoritmo di ricostruzione.

## Passo 4: Salvare l'immagine del codice a barre generato

Infine, scrivi il codice a barre in un file PNG. Puoi scegliere qualsiasi formato supportato (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`).

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Perché è importante*: PNG conserva i dati dei pixel senza perdita, garantendo che gli scanner leggano esattamente il pattern dei moduli configurato. Cambiare formato può influire sulla qualità visiva e sulla dimensione del file.

### Output previsto

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

Esegui il programma (`dotnet run`). Dopo l'esecuzione, verifica che il file PNG sia presente nella posizione specificata. Usa qualsiasi app di lettura di codici a barre che supporti Macro PDF417 per confermare che i metadati siano incorporati correttamente.

## Variazioni comuni e casi limite

- **Formati immagine diversi**: Sostituisci `BarCodeImageFormat.Png` con `Jpeg`, `Bmp` o `Tiff` se il tuo sistema a valle preferisce un altro formato.  
- **Modifica della dimensione del modulo**: Valori più grandi di `XDimension.Pixels` migliorano l'affidabilità della scansione su scanner a bassa risoluzione ma aumentano la dimensione dell'immagine.  
- **Segmenti multipli**: Per produrre un file multi‑segmento, genera una serie di codici a barre, incrementa `MacroPdf417SegmentID` per ciascuno e mantieni costante `MacroPdf417FileID`. Solo l'ultimo segmento dovrebbe avere `MacroPdf417Terminator` impostato.  
- **Supporto Unicode**: Il generatore codifica automaticamente i caratteri Unicode; assicurati che la tua stringa di origine utilizzi la codifica UTF-8 se la leggi da un file esterno.  
- **Gestione degli errori**: Avvolgi il blocco `using` in un try‑catch per catturare `BarCodeException` per parametri non validi (ad esempio, conteggio colonne fuori intervallo).

## Consigli professionali

- **Prestazioni**: Riutilizza una singola istanza di `BarcodeGenerator` quando crei molti codici a barre con le stesse impostazioni; cambia solo la proprietà `CodeText` tra i salvataggi.  
- **Stima della dimensione del file**: Il campo `MacroPdf417FileSize` dovrebbe corrispondere al conteggio dei byte del payload originale; discrepanze possono causare errori di validazione a valle.  
- **Test**: Convalida i codici a barre generati sia con il decoder integrato di Aspose (`BarCodeReader`) sia con uno scanner di terze parti per garantire l'interoperabilità.

## Conclusione

Questo **aspose barcode example**

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come creare un barcode – Compact PDF417 con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Come creare la zona silenziosa del barcode per Code 16K usando Aspose.BarCode per .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Come creare la zona silenziosa del barcode per ITF-14 usando Aspose.BarCode per .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}