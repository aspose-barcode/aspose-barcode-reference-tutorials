---
category: general
date: 2026-09-22
description: Crea un codice a barre macro PDF417 usando Aspose.BarCode in C#. Impara
  passo passo come generare il codice a barre con Aspose, configurare i metadati e
  salvarlo come PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- generate barcode with Aspose
- Aspose.BarCode PDF417
- C# barcode generation
- barcode metadata configuration
language: it
lastmod: 2026-09-22
og_description: Crea un codice a barre macro PDF417 utilizzando Aspose.BarCode in
  C#. Questa guida ti mostra come generare il codice a barre con Aspose, impostare
  i metadati macro e esportare l'immagine.
og_image_alt: Screenshot of a created macro PDF417 barcode using Aspose.BarCode in
  C#
og_title: Crea un codice a barre macro PDF417 con Aspose.BarCode (C#) – guida passo‑passo
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Create macro PDF417 barcode using Aspose.BarCode in C#. Learn step‑by‑step
    how to generate barcode with Aspose, configure metadata, and save as PNG.
  headline: Create macro PDF417 barcode with Aspose.BarCode (C#)
  type: TechArticle
tags:
- Aspose
- PDF417
- C#
- Barcode
title: Crea codice a barre macro PDF417 con Aspose.BarCode (C#)
url: /it/net/compact-pdf417-encoding/create-macro-pdf417-barcode-with-aspose-barcode-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea un codice a barre macro PDF417 con Aspose.BarCode (C#)

Se hai bisogno di **creare un codice a barre macro PDF417** in un'applicazione .NET, questo tutorial ti mostra esattamente come farlo con Aspose.BarCode. Vedrai un esempio completo e eseguibile che **genera il codice a barre con Aspose**, configura tutti i campi specifici della macro e salva il risultato come immagine PNG.

I codici a barre sono spesso usati per l'inventario, la spedizione o il tracciamento dei documenti, e la variante Macro PDF417 consente di incorporare metadati a livello di file all'interno del codice a barre stesso. Alla fine di questa guida sarai in grado di generare un codice a barre macro PDF417 completo che rispetta lo standard ISO/IEC 15438.

## Cosa ti serve

* .NET 6.0 SDK o versioni successive (il codice funziona con .NET Core e .NET Framework)
* Visual Studio 2022 (o qualsiasi IDE C#)
* Una connessione internet compatibile con NuGet per scaricare il pacchetto Aspose.BarCode
* Familiarità di base con la sintassi C#

Questi prerequisiti garantiscono che il codice venga compilato senza configurazioni aggiuntive.

## Passo 1: Installa il pacchetto NuGet Aspose.BarCode

La libreria Aspose.BarCode fornisce la classe `BarcodeGenerator` utilizzata in tutto questo tutorial.

```bash
dotnet add package Aspose.BarCode
```

Eseguendo il comando si aggiunge l'ultima versione stabile al file di progetto (`*.csproj`). Il pacchetto include il supporto per PDF417, Macro PDF417 e molte altre simbologie.

## Passo 2: Crea un nuovo progetto console (opzionale)

Se preferisci partire da zero, genera un'app console:

```bash
dotnet new console -n MacroPdf417Demo
cd MacroPdf417Demo
```

Il file `Program.cs` generato conterrà il codice per la generazione del codice a barre.

## Passo 3: Inizializza il generatore di codici a barre

Il generatore viene creato con il valore enum `EncodeTypes.MacroPdf417` e il testo che desideri codificare. Aspose.BarCode gestisce automaticamente i caratteri Unicode, quindi puoi includere direttamente lettere accentate o simboli.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

class Program
{
    static void Main()
    {
        // Step 3: Create a Macro PDF417 barcode generator with the desired text
        using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // The rest of the configuration follows...
```

### Perché è importante

`EncodeTypes.MacroPdf417` indica alla libreria di utilizzare la versione macro di PDF417, che aggiunge la possibilità di incorporare metadati a livello di file (ID file, conteggio segmenti, ecc.). Il testo "Åspóse.Barcóde©" dimostra che il generatore codifica correttamente i caratteri UTF‑8.

## Passo 4: Imposta le dimensioni di base del codice a barre

PDF417 consente di controllare il numero di colonne e la X‑dimension (larghezza di un singolo modulo). Modificando questi valori si influenza la dimensione fisica del codice a barre e l'affidabilità della scansione.

```csharp
            // Step 4: Set basic barcode dimensions
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // module width in pixels
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

* **XDimension** – Valori più piccoli producono un codice a barre più denso; valori più grandi lo rendono più facile da leggere per scanner a bassa risoluzione.
* **Columns** – Controlla il numero di colonne di dati; i valori tipici variano da 1 a 30.

## Passo 5: Configura i metadati Macro PDF417

Macro PDF417 contiene campi aggiuntivi che descrivono il file rappresentato dal codice a barre. Ogni campo è opzionale, ma impostarli migliora l'interoperabilità con gli scanner che comprendono il formato macro.

```csharp
            // Step 5: Configure Macro PDF417 metadata
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // demo checksum
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // bytes
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### Spiegazione di ciascun campo

| Property | Scopo | Intervallo tipico |
|----------|-------|--------------------|
| **MacroPdf417FileID** | Identificatore univoco per il file logico che può essere suddiviso in più codici a barre. | 0‑2³²‑1 |
| **MacroPdf417SegmentID** | Indice del segmento corrente (parte da 0). | 0‑(SegmentsCount‑1) |
| **MacroPdf417SegmentsCount** | Numero totale di segmenti che compongono il file completo. | 1‑99 |
| **MacroPdf417FileName** | Nome leggibile del file. | Fino a 255 caratteri |
| **MacroPdf417Checksum** | Checksum opzionale per il rilevamento degli errori. | 0‑65535 |
| **MacroPdf417FileSize** | Dimensione del file originale in byte. | 0‑2³²‑1 |
| **MacroPdf417TimeStamp** | Timestamp di creazione o modifica del file. | Qualsiasi `DateTime` |
| **MacroPdf417Addressee** | Identificatore del destinatario (es. reparto o macchina). | Stringa libera |
| **MacroPdf417Sender** | Identificatore dell'origine (es. nome azienda). | Stringa libera |
| **MacroPdf417Terminator** | Indica se questo segmento è l'ultimo. | `Set` o `Unset` |

**Suggerimento:** Se dividi un file grande in più codici a barre, assicurati che il `SegmentID` di ogni segmento sia sequenziale e che `SegmentsCount` rimanga costante in tutti i segmenti. Gli scanner si basano su questi valori per ricostruire il file originale.

## Passo 6: Salva l'immagine del codice a barre

Aspose.BarCode supporta molti formati di output (PNG, JPEG, BMP, SVG, ecc.). PNG offre qualità lossless, ideale per test e documentazione.

```csharp
            // Step 6: Save the barcode image as PNG
            barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }
    }
}
```

Eseguendo il programma si crea un file chiamato `ExtPDF417Meta.png` nella directory di output del progetto (`bin/Debug/net6.0/`). Apri l'immagine con qualsiasi visualizzatore per verificare che il codice a barre venga renderizzato correttamente.

## Passo 7: Verifica il codice a barre generato (opzionale)

Se disponi di un'app scanner PDF417 (mobile o desktop), scansiona il PNG salvato. Lo scanner dovrebbe restituire:

* Il testo codificato `"Åspóse.Barcóde©"`
* Tutti i campi macro che hai configurato (ID file, ID segmento, ecc.)

Per la verifica automatizzata, Aspose.BarCode offre anche la classe `BarCodeReader`:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

using (var reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Text: {result.CodeText}");
        Console.WriteLine($"Macro File ID: {result.GetMacroPdf417FileID()}");
        // Access other macro properties similarly
    }
}
```

Questo snippet dimostra come leggere nuovamente i metadati macro programmaticamente, confermando che **generare il codice a barre con Aspose** funziona end‑to‑end.

## Casi limite e migliori pratiche

| Situazione | Gestione consigliata |
|------------|----------------------|
| **Caratteri Unicode** | Assicurati che la stringa di origine sia UTF‑8 (predefinito in .NET). Aspose.BarCode codifica automaticamente Unicode, ma verifica il set di caratteri dello scanner. |
| **Dimensione file grande** | Macro PDF417 suddivide i file in fino a 99 segmenti. Se il file supera i 400 KB, aumenta `SegmentsCount` e genera più codici a barre, ciascuno con un `SegmentID` sequenziale. |
| **Precisione del timestamp** | Usa `DateTime.UtcNow` per il tempo universale; alcuni scanner si aspettano UTC. |
| **Validazione checksum** | Fornisci un checksum corretto se prevedi di validare l'integrità sul lato ricevente. |
| **Formati immagine diversi** | Usa `BarCodeImageFormat.Svg` per grafica vettoriale quando hai bisogno di codici a barre scalabili all'infinito. |
| **Prestazioni** | Riutilizza una singola istanza di `BarcodeGenerator` quando generi molti codici a barre; cambia solo i `Parameters` tra le iterazioni. |

## Esempio completo e eseguibile

Di seguito trovi il programma completo che puoi copiare, incollare ed eseguire senza modifiche (supponendo che il pacchetto NuGet sia installato).



## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche illustrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Esempio di codice a barre Aspose: genera Macro PDF417 in C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [Crea metadati del codice a barre PDF417 in C# – Guida completa passo‑passo](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [Come generare l'immagine del codice a barre PDF417 in C# con Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}