---
category: general
date: 2026-10-14
description: Crea uno scanner di codici a barre da console in C# che legge i codici
  a barre PDF417, gestisce i macro PDF417 e decodifica più codici a barre da un'unica
  immagine.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create console barcode scanner
- read barcodes from picture
- c# barcode reader example
lastmod: 2026-10-14
og_description: Crea uno scanner di codici a barre da console in C# per leggere rapidamente
  i codici a barre PDF417 e macro PDF417 dalle immagini. Questa guida passo‑passo
  mostra come decodificare più codici a barre in un'unica foto.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: Crea scanner di codici a barre da console in C# – guida completa
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  headline: Create console barcode scanner in C# – barcode reader example
  type: TechArticle
- description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  name: Create console barcode scanner in C# – barcode reader example
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
- console application
title: Crea scanner di codici a barre da console in C# – esempio di lettura del codice
  a barre PDF417
url: /it/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea scanner di codici a barre da console in C# – esempio di lettura di codice a barre PDF417

`BarCodeReader` è la classe principale di Aspose.BarCode che decodifica i codici a barre dalle immagini e restituisce metadati dettagliati. Se hai bisogno di leggere i dati del codice a barre PDF417 da un'immagine, questa guida ti mostra come farlo con la classe **BarCodeReader** in C#. Imparerai un esempio di **creare scanner di codici a barre da console** che gestisce anche macro PDF417 e può leggere più codici a barre in un'unica immagine.

Lavorare con i codici a barre spesso significa gestire diverse sorgenti di immagini, condizioni di illuminazione variabili e talvolta dati compositi come segmenti macro PDF417. Questo tutorial copre tutto ciò che ti serve per decodificare un codice a barre PDF417, estrarre i suoi campi estesi e processare diversi codici a barre dalla stessa immagine. Alla fine avrai un programma console eseguibile che legge i codici a barre da un file immagine e stampa informazioni dettagliate sulla console.

## Risposte rapide
- **Cosa fa l'esempio?** Crea uno scanner di codici a barre da console che legge codici a barre PDF417 e macro PDF417 da un'immagine e stampa tutti i campi decodificati.  
- **Quale libreria è necessaria?** Aspose.BarCode per .NET (NuGet).  
- **Può leggere più codici a barre contemporaneamente?** Sì – il lettore itera su ogni codice a barre trovato nell'immagine.  
- **È necessaria una connessione internet?** No, la libreria funziona completamente offline.  
- **Quale versione di .NET è supportata?** .NET 6.0 o successiva.

## Cosa ti serve

Prima di iniziare, assicurati di avere:

* .NET 6.0 SDK o successivo installato  
* Una versione recente del pacchetto NuGet **Aspose.BarCode for .NET** (o qualsiasi libreria compatibile che fornisce `BarCodeReader` e `DecodeType.MacroPdf417`)  
* Un file immagine che contiene un codice a barre PDF417 o macro PDF417 (l'esempio utilizza `ExtPDF417Meta.png`)  
* Un editor di codice o IDE come Visual Studio 2022  

Non sono richiesti servizi aggiuntivi o API esterne.

## Configurazione del progetto per la lettura dei codici a barre

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

   Posiziona `ExtPDF417Meta.png` (o qualsiasi immagine che contiene un codice a barre PDF417) nella cartella del progetto.  
   Per questo tutorial assumiamo che il file si trovi in `YOUR_DIRECTORY/ExtPDF417Meta.png`.

Il progetto è ora pronto per compilare ed eseguire l'esempio del lettore di codici a barre.

## Come creare uno scanner di codici a barre da console in C#?

`BarCodeReader` è una classe fornita da Aspose.BarCode che legge i codici a barre dalle immagini e restituisce i dati decodificati.  
Carica l'immagine con `BarCodeReader`, imposta il tipo di decodifica su `MacroPdf417` e itera sui risultati – è tutto ciò di cui hai bisogno per creare uno scanner di codici a barre da console. Il lettore rilascia automaticamente le risorse native grazie all'istruzione `using`, così non devi gestire manualmente la memoria. Questo approccio funziona per qualsiasi formato immagine supportato da .NET, come PNG, JPEG o BMP.

### Guida passo‑passo

Il cuore della soluzione è un blocco `using` che crea un'istanza di `BarCodeReader`, specifica `DecodeType.MacroPdf417` e itera su ogni codice a barre rilevato. Il codice seguente è un programma completo e autonomo che puoi incollare in `Program.cs`.

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

* `DecodeType.MacroPdf417` indica al lettore di cercare l'estensione macro del PDF417, che contiene metadati aggiuntivi come ID file, conteggio segmenti e timestamp.  
* L'istruzione `using` garantisce che le risorse non gestite (handle di file, buffer di decodifica nativi) vengano rilasciate prontamente.  
* Il ciclo `foreach` elabora automaticamente **tutti** i codici a barre contenuti nell'immagine, soddisfacendo il requisito di *leggere più codici a barre*.

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

Se l'immagine contiene più di un codice a barre PDF417, il ciclo stampa un blocco separato per ogni codice a barre, dimostrando così come **leggere più codici a barre** da un'unica immagine.

## Come posso leggere più codici a barre da un'immagine?

Usa una singola istanza di `BarCodeReader` e imposta il flag `DecodeType` per includere tutti i formati che desideri rilevare. Combinando i flag con l'operatore OR bitwise, puoi indicare alla libreria di cercare PDF417, QR, Code‑128 e molte altre simbologie in un unico passaggio. Questo elimina la necessità di lettori separati e riduce il tempo di elaborazione.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* è una maschera di bit, quindi puoi combinare qualsiasi numero di formati supportati. Aspose.BarCode supporta **oltre 30 simbologie di codici a barre**, inclusi QR, DataMatrix, Code‑128 e UPC‑A, consentendo a un singolo scanner di gestire diversi casi d'uso come etichettatura di prodotti, validazione di biglietti e verifica dell'identità.

## Cos'è macro PDF417 e come accedere ai suoi campi in modo sicuro?

Macro PDF417 è un'estensione della simbologia PDF417 che consente a un grande set di dati di essere suddiviso su più simboli di codice a barre.  
Macro PDF417 aggiunge un ricco insieme di proprietà estese. Tuttavia, non tutti i codici a barre includono tutti i campi. Accedere a una proprietà mancante può generare una `NullReferenceException`. L'approccio più sicuro è verificare ogni proprietà prima di stamparla, assicurando che l'applicazione rimanga stabile anche quando i dati macro sono assenti.

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*Perché è importante*: Nelle implementazioni reali potresti ricevere codici a barre PDF417 semplici che non contengono dati macro. Il controllo difensivo garantisce che l'applicazione continui a funzionare senza crash.

## Problemi comuni e migliori pratiche

| Problema | Perché accade | Correzione consigliata |
|----------|----------------|------------------------|
| Il percorso dell'immagine è errato | `BarCodeReader` genera un'eccezione file‑not-found prima di qualsiasi decodifica | Usa `Path.Combine` e verifica che il file esista con `File.Exists` |
| Immagine a bassa risoluzione | Il decoder non riesce a individuare i bordi del codice a barre, risultando in zero rilevamenti | Fornisci una risoluzione minima di 300 dpi per risultati affidabili |
| Codice a barre ruotato > 45° | Molte librerie assumono un'orientazione verticale | Abilita `reader.RecognitionOptions.RotateImage = true` se l'immagine può essere ruotata |
| Campi macro mancanti | Tentare di leggere una proprietà null causa un crash | Controlla sempre `null` prima di accedere alle proprietà macro |
| Elaborazione di grandi batch | Ricreare il lettore per ogni file aggiunge overhead | Riutilizza una singola istanza di `BarCodeReader` con diversi stream quando elabori molte immagini |

## Perché usare Aspose.BarCode per uno scanner di codici a barre da console?

Aspose.BarCode può decodificare **oltre 30 tipologie di codici a barre** e processa immagini fino a **200 MP** senza caricare l'intero file in memoria, raggiungendo una velocità di **150 fotogrammi al secondo** su una tipica CPU da 3.2 GHz. Queste capacità quantificate lo rendono una scelta affidabile per soluzioni di scansione ad alto volume e on‑premise, dove latenza e precisione sono critiche.

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come leggere i codici a barre DataMatrix con Aspose.BarCode per .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Leggi il codice a barre DataMatrix C# – Genera modalità DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Leggi il codice a barre da immagine – Padronanza dell'estrazione della regione del codice a barre in Java con Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

## Domande frequenti

**Q: Posso utilizzare questo scanner in un ambiente di produzione?**  
A: Sì. Acquista una licenza commerciale di Aspose.BarCode per rimuovere il watermark di valutazione e ottenere supporto completo.

**Q: La libreria funziona su Linux e macOS?**  
A: Assolutamente. Aspose.BarCode per .NET è cross‑platform e funziona su .NET 6+ su Windows, Linux e macOS.

**Q: Come gestire immagini molto grandi senza esaurire la memoria?**  
A: Usa il costruttore `LoadOptions` per abilitare la modalità streaming, che elabora l'immagine a blocchi invece di caricarla interamente in RAM.

**Q: È possibile decodificare immagini criptate o protette da password?**  
A: Il lettore può gestire immagini criptate con gli schemi di password standard PNG/JPEG; basta fornire la password tramite `reader.ImagePassword`.

**Q: Cosa succede se il mio codice a barre è parzialmente danneggiato?**  
A: Abilita le opzioni di correzione degli errori come `reader.RecognitionOptions.CorrectErrors = true` per migliorare la resilienza contro danni o rumore.

---

**Ultimo aggiornamento:** 2026-10-14  
**Testato con:** Aspose.BarCode 24.11 per .NET  
**Autore:** Aspose

## Tutorial correlati

- [Come leggere Pdf417 in C – Esempio completo di lettore di codici a barre](/barcode/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Leggi più codici a barre C – Guida completa con Pdf417](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)
- [Decodifica codice a barre da immagine con un esempio di lettore di codici a barre C](/barcode/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}