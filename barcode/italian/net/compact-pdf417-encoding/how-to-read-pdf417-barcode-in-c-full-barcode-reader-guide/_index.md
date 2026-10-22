---
category: general
date: 2026-10-21
description: Come leggere il codice a barre PDF417 in C# usando un lettore di codici
  a barre da un'immagine. Segui questo esempio passo‑passo di lettore di codici a
  barre in C# per una decodifica affidabile.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode from image c#
- c# barcode reader example
- macro pdf417 decoding
- barcode extended fields c#
language: it
lastmod: 2026-10-21
og_description: Come leggere il codice a barre PDF417 in C# con un esempio completo
  di lettore di codici a barre. Impara a decodificare le immagini Macro PDF417 e ad
  accedere a tutti i campi estesi.
og_image_alt: Console output showing decoded PDF417 barcode fields in a C# application
og_title: Come leggere il codice a barre PDF417 in C# – guida dettagliata
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: How to read PDF417 barcode in C# using a barcode reader from image.
    Follow this step‑by‑step C# barcode reader example for reliable decoding.
  headline: How to read PDF417 barcode in C# – full barcode reader guide
  type: TechArticle
- description: How to read PDF417 barcode in C# using a barcode reader from image.
    Follow this step‑by‑step C# barcode reader example for reliable decoding.
  name: How to read PDF417 barcode in C# – full barcode reader guide
  steps:
  - name: Initialise the `BarCodeReader` for the specific `DecodeType`.
    text: Initialise the `BarCodeReader` for the specific `DecodeType`.
  - name: Iterate through the returned `BarCodeResult` collection.
    text: Iterate through the returned `BarCodeResult` collection.
  - name: Access both basic and extended PDF417 fields.
    text: Access both basic and extended PDF417 fields.
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the Aspose.BarCode package** (as shown earlier).'
    text: '**Add the Aspose.BarCode package** (as shown earlier).'
  - name: '**Copy the image file** into the project folder or reference it with an
      absolute path.'
    text: '**Copy the image file** into the project folder or reference it with an
      absolute path.'
  - name: '**Build and run**'
    text: '**Build and run**'
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Come leggere il codice a barre PDF417 in C# – guida completa al lettore di
  codici a barre
url: /it/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-full-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come leggere il codice a barre PDF417 in C# – guida completa al lettore di codici a barre

Se hai bisogno di **come leggere il codice a barre PDF417** in un'applicazione .NET, questa guida ti mostra una soluzione pronta all'uso. Vedrai come **leggere il codice a barre da un'immagine C#** usando una popolare libreria di codici a barre e ottenere ogni attributo Macro PDF417 senza strumenti aggiuntivi.

Il tutorial copre tutto il necessario per un **esempio di lettore di codici a barre C#**: configurazione del progetto, walkthrough del codice e consigli per gestire i casi limite. Alla fine potrai incollare il codice in un progetto console e iniziare a decodificare le immagini PDF417 all'istante.

## Cosa ti serve

Prima di iniziare, verifica i seguenti prerequisiti:

| Prerequisito | Motivo |
|--------------|--------|
| .NET 6.0 SDK o successivo | Fornisce l'ambiente di runtime per l'app console C# |
| Visual Studio 2022 (o qualsiasi IDE C#) | Consente una facile creazione del progetto e il debug |
| Aspose.BarCode per .NET (pacchetto NuGet) | Fornisce le classi `BarCodeReader` e `DecodeType` |
| Un file immagine Macro PDF417 (es., `MacroPdf417.png`) | Serve come input per la decodifica |

Puoi installare la libreria con la CLI dotnet:

```bash
dotnet add package Aspose.BarCode
```

## Come leggere il codice a barre PDF417 da un'immagine in C#

Il nucleo del flusso di lavoro **leggere il codice a barre da un'immagine C#** consiste in tre azioni:

1. Inizializzare il `BarCodeReader` per il `DecodeType` specifico.  
2. Iterare attraverso la collezione `BarCodeResult` restituita.  
3. Accedere sia ai campi base che a quelli estesi del PDF417.

Di seguito il codice completo e eseguibile. Salvalo come `Program.cs` all'interno di un progetto console.

```csharp
using System;
using Aspose.BarCode;               // Provides BarCodeReader, DecodeType, BarCodeResult
using Aspose.BarCode.BarCodeRecognition; // Contains extended PDF417 structures

class Program
{
    static void Main()
    {
        // Step 1: Initialise a BarCodeReader for a Macro PDF417 image
        // Replace the path with the location of your MacroPdf417.png file
        string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes present in the image
            foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
            {
                // Step 3: Display basic barcode information
                Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
                Console.WriteLine($"CodeText: {barcodeResult.CodeText}");

                // Step 4: Show Macro PDF417 specific extended fields
                Console.WriteLine($"File ID: {barcodeResult.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID: {barcodeResult.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count: {barcodeResult.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name: {barcodeResult.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum: {barcodeResult.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size: {barcodeResult.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"TimeStamp: {barcodeResult.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee: {barcodeResult.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender: {barcodeResult.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator: {barcodeResult.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

### Spiegazione di ogni passaggio

* **Passo 1 – Inizializzare il lettore**  
  Il costruttore `BarCodeReader` riceve il percorso del file immagine e un `DecodeType`. `DecodeType.MacroPdf417` indica alla libreria di cercare i simboli Macro PDF417, che contengono metadati aggiuntivi rispetto ai normali codici a barre PDF417.

* **Passo 2 – ReadBarCodes()**  
  Questo metodo restituisce un `IEnumerable<BarCodeResult>` che può contenere più codici a barre se l'immagine ne contiene più di uno. Il ciclo `foreach` garantisce che ogni simbolo rilevato venga elaborato.

* **Passo 3 – Informazioni di base**  
  `CodeTypeName` identifica il formato del codice a barre (es., “MacroPDF417”). `CodeText` contiene la stringa di dati grezzi codificata nel simbolo.

* **Passo 4 – Campi estesi**  
  Macro PDF417 aggiunge un insieme di proprietà estese sotto `barcodeResult.Extended.Pdf417`. Questi campi espongono dati a livello di file come `FileID`, `SegmentID` e `FileName`. Accedervi direttamente ti consente di ricostruire documenti multi‑segmento o verificare l'integrità.

#### Output console previsto

```
CodeType: MacroPDF417
CodeText: 1234567890
File ID: 5
Segment ID: 1
Segments Count: 3
File Name: invoice_2024.pdf
Checksum: 0A3F
File Size: 254321
TimeStamp: 2024-03-15T10:45:12Z
Addressee: Acme Corp.
Sender: Warehouse 12
Terminator: END
----------------------------------------
```

I valori esatti riflettono il contenuto codificato nel tuo `MacroPdf417.png`. Se l'immagine contiene un singolo segmento, `SegmentsCount` sarà 1 e `SegmentID` sarà 0.

## Configura l'ambiente del lettore di codici a barre C#

Un affidabile **esempio di lettore di codici a barre C#** dipende da una configurazione di progetto pulita:

1. **Crea un nuovo progetto console**  
   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```
2. **Aggiungi il pacchetto Aspose.BarCode** (come mostrato in precedenza).  
3. **Copia il file immagine** nella cartella del progetto o riferiscilo con un percorso assoluto.  
4. **Compila ed esegui**  
   ```bash
   dotnet run
   ```

Se la compilazione fallisce con un errore di riferimento mancante, verifica che le istruzioni `using Aspose.BarCode;` corrispondano alla versione del pacchetto installato. L'API della libreria è stabile tra .NET 6 e .NET 8, quindi puoi aggiornare il runtime senza modifiche al codice.

## Decodifica il codice a barre Macro PDF417

Quando chiami `ReadBarCodes()`, la libreria esegue internamente quanto segue:

* **Pre-elaborazione dell'immagine** – converte il bitmap in una matrice binaria, correggendo rotazione e rumore.  
* **Rilevamento del pattern** – ricerca i pattern di avvio/fine PDF417 ed estrae la larghezza del modulo.  
* **Correzione degli errori** – applica codici Reed‑Solomon per recuperare i codeword danneggiati.  
* **Estrazione Macro** – analizza l'intestazione del segmento PDF417 esteso e popola l'oggetto `Extended.Pdf417`.

Comprendere questa pipeline ti aiuta a decidere quando modificare le opzioni del decoder. Ad esempio, se le tue immagini hanno basso contrasto, puoi abilitare la proprietà `ReadQuality` del `BarCodeReader` (disponibile nelle versioni successive) per migliorare i tassi di rilevamento.

## Interpreta i campi PDF417 estesi

I campi estesi corrispondono direttamente alla specifica Macro PDF417:

| Campo | Significato |
|-------|-------------|
| `MacroPdf417FileID` | Identificatore unico per l'intero file attraverso tutti i segmenti |
| `MacroPdf417SegmentID` | Indice basato su zero del segmento corrente |
| `MacroPdf417SegmentsCount` | Numero totale di segmenti che compongono il file |
| `MacroPdf417FileName` | Nome file originale memorizzato durante la codifica |
| `MacroPdf417Checksum` | Checksum a 16 bit per la verifica dell'integrità |
| `MacroPdf417FileSize` | Dimensione del file originale in byte |
| `MacroPdf417TimeStamp` | Timestamp UTC quando il codice a barre è stato generato |
| `MacroPdf417Addressee` | Destinatario previsto del documento |
| `MacroPdf417Sender` | Mittente del documento |
| `MacroPdf417Terminator` | Stringa letterale “END” che segna l'ultimo segmento |

Puoi usare questi valori per ricostruire un PDF multi‑segmento, verificare che nessun segmento manchi, o registrare informazioni di audit per scopi di conformità.

## Problemi comuni e risoluzione

| Sintomo | Causa probabile | Soluzione |
|---------|-----------------|-----------|
| Nessun output appare | Percorso immagine errato o formato non supportato | Usa un percorso assoluto e assicurati che il file sia un PNG/JPEG supportato da Aspose.BarCode |
| `CodeType` mostra “PDF417” invece di “MacroPDF417” | L'immagine contiene un simbolo PDF417 normale, non una variante macro | Verifica che il codice a barre di origine sia codificato con le estensioni Macro PDF417 |
| Alcuni campi sono vuoti | Il codice a barre è stato generato senza quei campi macro | Codifica il codice a barre con un payload macro completo, o gestisci i valori null nel codice |
| Il decoder lancia `ArgumentException` | Specificato `DecodeType` errato | Cambia `DecodeType.MacroPdf417` in `DecodeType.Pdf417` se ti servono solo i dati PDF417 standard |

**Consiglio professionale:** Avvolgi l'accesso ai campi in controlli null se prevedi codici a barre non macro. L'oggetto `Extended.Pdf417` restituisce valori predefiniti (es., `0` per i campi numerici) quando i dati sono assenti.

```csharp
int fileId = barcodeResult.Extended?.Pdf417?.MacroPdf417FileID ?? -1;
```

## Riepilogo dell'esempio completo funzionante

Mettendo tutto insieme, il programma finale è composto dalle direttive using, dal metodo `Main` e dal ciclo a quattro passaggi mostrato in precedenza. Non sono necessari file di configurazione aggiuntivi. Compila ed esegui il progetto per vedere l'output console con tutte le proprietà Macro PDF417.

## Conclusione

Ora sai **come leggere il codice a barre PDF417** in C# usando un conciso **esempio di lettore di codici a barre C#**. La guida ti ha accompagnato nella configurazione dell'ambiente, nell'implementazione del codice e nell'interpretazione di ogni campo Macro PDF417 esteso. Con questa base puoi integrare la scansione di codici a barre nei sistemi di inventario, nei flussi di lavoro di gestione documenti o nei back‑end mobile.

### Prossimo

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come leggere PDF417 in C# – guida completa al lettore di codici a barre](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/)
- [Come decodificare PDF417 in C# con un esempio di lettore di codici a barre](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/)
- [Come creare un'immagine di codice a barre PDF417 in C# con opzioni Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}