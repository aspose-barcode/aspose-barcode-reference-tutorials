---
category: general
date: 2026-09-26
description: Scopri come decodificare PDF417 in C# con un esempio passo‑passo di lettore
  di codici a barre. Questa guida ti mostra come leggere un'immagine di codice a barre
  in C# usando Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcode image c#
- c# barcode reader example
language: it
lastmod: 2026-09-26
og_description: Come decodificare PDF417 in C# rapidamente. Segui questo esempio di
  lettore di codici a barre per leggere l'immagine del codice a barre in C# con Aspose.BarCode
  ed estrarre i dettagli macro.
og_image_alt: Screenshot showing how to decode PDF417 in C# using Aspose.BarCode
og_title: Come decodificare PDF417 in C# – guida completa al lettore di codici a barre
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to decode PDF417 in C# with a step‑by‑step barcode reader
    example. This guide shows you how to read barcode image C# using Aspose.BarCode.
  headline: How to decode PDF417 in C# – barcode reader example
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Come decodificare PDF417 in C# – esempio di lettore di codici a barre
url: /it/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come decodificare PDF417 in C# – esempio di lettore di codici a barre

Se hai bisogno di **come decodificare PDF417** in un'applicazione .NET, questo tutorial fornisce una soluzione completa, pronta all'uso. Vedrai come leggere un'immagine di codice a barre C# usando la libreria Aspose.BarCode, recuperare le informazioni macro estese di PDF417 e visualizzare ogni campo rilevante.

La decodifica di PDF417 non è limitata al solo testo; il formato può contenere dati di segmentazione del file, timestamp e checksum. Questa guida ti accompagna passo passo, spiega perché il codice è strutturato in questo modo e evidenzia le insidie comuni che potresti incontrare implementando un esempio di lettore di codici a barre C#.

## Prerequisiti

* .NET 6.0 (o successivo) SDK installato  
* Visual Studio 2022 (o qualsiasi IDE compatibile con C#)  
* **Aspose.BarCode for .NET** pacchetto NuGet (`Aspose.BarCode`)  
* Un'immagine di esempio Macro PDF417 (ad es., `ExtPDF417Meta.png`)

Questi requisiti garantiscono che il codice venga compilato ed eseguito senza configurazioni aggiuntive.

## Passo 1: Installa il pacchetto NuGet Aspose.BarCode

Il primo passo in qualsiasi progetto **read barcode image C#** è aggiungere la libreria di codici a barre. Apri il terminale nella cartella della tua soluzione ed esegui:

```bash
dotnet add package Aspose.BarCode
```

Il pacchetto fornisce `BarCodeReader`, `DecodeType` e la proprietà `Extended` utilizzata per accedere ai dati macro. Installandolo una sola volta le classi saranno disponibili in tutto il progetto.

## Passo 2: Crea un lettore di codici a barre per un'immagine Macro PDF417

Ora puoi istanziare `BarCodeReader` con il percorso dell'immagine e specificare `DecodeType.MacroPdf417`. Questo indica alla libreria di cercare il formato PDF417 esteso che contiene le informazioni macro.

```csharp
using Aspose.BarCode.BarCodeRecognition;

// Path to the Macro PDF417 image
string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

// Initialize the reader for Macro PDF417 decoding
using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is ready – next we will extract barcodes.
}
```

**Perché è importante:**  
`DecodeType.MacroPdf417` attiva il parser specifico per le macro. Se lo ometti, il lettore restituisce solo il payload di testo semplice e ignora i campi macro di cui probabilmente hai bisogno per la ricostruzione del file.

## Passo 3: Leggi tutti i codici a barre trovati nell'immagine

Un'unica immagine può contenere più simboli PDF417, specialmente quando i dati sono suddivisi in segmenti. Iterare su `ReadBarCodes()` garantisce di catturare ogni segmento.

```csharp
// Step 3: Iterate over each detected barcode
foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
{
    // Inside the loop we will access both basic and macro data.
}
```

**Perché iterare:**  
I dati macro PDF417 spesso appaiono in diversi segmenti. Elaborare ogni `BarCodeResult` assicura di raccogliere l'intero set di campi macro, come `MacroPdf417FileID` e `MacroPdf417SegmentsCount`.

## Passo 4: Recupera e visualizza i dati di base del codice a barre

L'oggetto `BarCodeResult` contiene il tipo e il testo decodificato. Visualizzare questi valori aiuta a verificare che il lettore abbia identificato correttamente il simbolo prima di approfondire i dettagli macro.

```csharp
Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
Console.WriteLine($"CodeText: {barcodeResult.CodeText}");
```

**Suggerimento:** Se `CodeText` è vuoto, l'immagine potrebbe essere corrotta o la modalità di decodifica è errata. Ricontrolla il `DecodeType` utilizzato durante l'inizializzazione.

## Passo 5: Estrai le informazioni macro PDF417 estese

I dati macro si trovano sotto `barcodeResult.Extended.Pdf417`. Ogni proprietà corrisponde a un campo definito nella specifica PDF417.

```csharp
// Step 5: Access macro-specific fields
var macroInfo = barcodeResult.Extended.Pdf417;

Console.WriteLine($"Pdf417MacroFileID: {macroInfo.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID: {macroInfo.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount: {macroInfo.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName: {macroInfo.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum: {macroInfo.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize: {macroInfo.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp: {macroInfo.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee: {macroInfo.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender: {macroInfo.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator: {macroInfo.MacroPdf417Terminator}");
```

**Cosa significa ogni campo**

| Proprietà | Descrizione |
|----------|-------------|
| `MacroPdf417FileID` | Identificatore che raggruppa tutti i segmenti appartenenti allo stesso file logico. |
| `MacroPdf417SegmentID` | Indice del segmento corrente (a partire da 1). |
| `MacroPdf417SegmentsCount` | Numero totale di segmenti necessari per ricostruire il file originale. |
| `MacroPdf417FileName` | Nome file opzionale incorporato nella macro. |
| `MacroPdf417Checksum` | Checksum CRC‑16 per la verifica dell'integrità. |
| `MacroPdf417FileSize` | Dimensione prevista del file ricostruito (in byte). |
| `MacroPdf417TimeStamp` | Data‑ora in cui la macro è stata generata. |
| `MacroPdf417Addressee` | Identificatore del destinatario opzionale. |
| `MacroPdf417Sender` | Identificatore del mittente opzionale. |
| `MacroPdf417Terminator` | Flag terminatore; dovrebbe essere `true` sull'ultimo segmento. |

Comprendere questi campi ti consente di ricostruire il file originale, convalidare l'integrità dei dati e implementare logiche di business personalizzate (ad es., rifiutare documenti obsoleti).

## Passo 6: Gestisci più segmenti e ricostruisci il file originale (avanzato)

Quando `MacroPdf417SegmentsCount` è maggiore di 1, è necessario raccogliere ogni segmento, ordinarli per `MacroPdf417SegmentID` e concatenare i valori di `CodeText`. Di seguito è riportata un'implementazione concisa:

```csharp
// Collect segments in a dictionary keyed by SegmentID
var segments = new SortedDictionary<int, string>();

foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
{
    var macro = result.Extended.Pdf417;
    segments[macro.MacroPdf417SegmentID] = result.CodeText;
}

// Verify that we received all expected segments
int expectedCount = segments.First().Value != null
    ? barcodeReader.ReadBarCodes().First().Extended.Pdf417.MacroPdf417SegmentsCount
    : 0;

if (segments.Count == expectedCount)
{
    // Reconstruct the full payload
    string fullPayload = string.Concat(segments.Values);
    Console.WriteLine($"Reconstructed payload ({fullPayload.Length} chars):");
    Console.WriteLine(fullPayload);
}
else
{
    Console.WriteLine($"Warning: Expected {expectedCount} segments but received {segments.Count}.");
}
```

**Perché è importante:**  
Senza ordinamento e concatenazione, i dati decodificati sarebbero incompleti o corrotti. Lo snippet dimostra anche la programmazione difensiva controllando il conteggio dei segmenti.

## Passo 7: Concludi con la gestione degli errori e le migliori pratiche

Un **c# barcode reader example** pronto per la produzione dovrebbe anticipare errori di I/O, formati non supportati e immagini corrotte.

```csharp
try
{
    // Existing barcode reading code goes here
}
catch (FileNotFoundException ex)
{
    Console.Error.WriteLine($"Image file not found: {ex.Message}");
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode processing error: {ex.Message}");
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Unexpected error: {ex.Message}");
}
```

**Checklist delle migliori pratiche**

* Convalida il percorso dell'immagine prima di creare `BarCodeReader`.  
* Utilizza le istruzioni `using` per garantire il rilascio delle risorse non gestite.  
* Registra i campi macro per le tracce di audit—soprattutto `MacroPdf417Checksum` e `MacroPdf417TimeStamp`.  
* Quando gestisci file di grandi dimensioni, considera lo streaming del payload concatenato su disco invece di mantenerlo interamente in memoria.

## Output previsto

Eseguendo il programma completo su un `ExtPDF417Meta.png` valido si ottiene un output simile a:

```
CodeType: MacroPdf417
CodeText: <base64‑encoded segment data>
Pdf417MacroFileID: 42
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 254312
Pdf417MacroTimeStamp: 2024-03-15T10:23:45Z
Pdf417MacroAddressee: Acme Corp
Pdf417MacroSender: Warehouse 7
MacroPdf417Terminator: False
...
```

Se tutti e tre i segmenti sono presenti, il blocco di ricostruzione stampa il payload completo dopo il messaggio di verifica.

## Conclusione

Ora sai **come decodificare PDF417** in C# usando un robusto esempio di lettore di codici a barre. Il tutorial ha coperto l'installazione di Aspose.BarCode, l'inizializzazione di un `BarCodeReader` per Macro PDF417, l'iterazione su più codici a barre, l'estrazione dei campi macro, la ricostruzione dei dati segmentati e l'implementazione della gestione degli errori.  

Da qui puoi:

* Integra il lettore in una Web API che accetta immagini caricate.  
* Memorizza i metadati macro in un database per scopi di audit.  
* Estendi la soluzione ad altre simbologie 2‑D sostituendo `DecodeType` (ad es.

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come leggere PDF417 in C# – Esempio completo di lettore di codici a barre](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Come creare un codice a barre PDF417 con Aspose – Guida completa passo‑passo](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Leggi il codice a barre PDF417 in C# – esempio di lettore di codici a barre](/barcode/english/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}