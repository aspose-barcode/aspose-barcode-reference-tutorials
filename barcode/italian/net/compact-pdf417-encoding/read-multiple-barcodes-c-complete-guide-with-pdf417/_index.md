---
category: general
date: 2026-10-04
description: Scopri come decodificare PDF417 e leggere più codici a barre in C# utilizzando
  Aspose.BarCode. Questa guida ti mostra come rilevare compact mode e gestire molti
  codici a barre in un'unica immagine.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- c# barcode library
- read multiple barcodes
- pdf417 compact mode
- aspose barcode licensing
lastmod: 2026-10-04
og_description: Scopri come decodificare PDF417 e leggere più codici a barre in C#.
  Questa guida passo‑passo copre la rilevazione di compact mode, il multi‑barcode
  handling e le best practices.
og_image_alt: Screenshot of C# console output showing compact mode status for PDF417
  barcodes
og_title: Come decodificare PDF417 e leggere più codici a barre in C#
schemas:
- author: Aspose
  dateModified: '2026-10-04'
  description: Learn how to decode PDF417 and read multiple barcodes in C# using Aspose.BarCode.
    Includes compact mode detection and multi‑barcode handling.
  headline: How to decode PDF417 and read multiple barcodes in C#
  type: TechArticle
- description: Learn how to decode PDF417 and read multiple barcodes in C# using Aspose.BarCode.
    Includes compact mode detection and multi‑barcode handling.
  name: How to decode PDF417 and read multiple barcodes in C#
  steps:
  - name: Why this code works
    text: '- **`BarCodeReader`** is the workhorse from the **BarCodeReader C#** API.
      It opens the image, applies pre‑processing, and searches for symbols of the
      type you specify. - **`ReadBarCodes()`** returns an array, not just a single
      result. That’s the key to **reading multiple barcodes C#**—the method aut'
  - name: 1️⃣ No barcodes detected
    text: 'If `ReadBarCodes()` returns an empty array, the most common culprits are:'
  - name: 2️⃣ Extremely large images
    text: 'Processing a 10 MP photo can be memory‑hungry. You can limit the scan area:'
  - name: 3️⃣ Thread‑safety
    text: '`BarCodeReader` implements `IDisposable` and is **not** thread‑safe. Spin
      up separate instances per thread if you need parallel processing.'
  - name: 4️⃣ Licensing
    text: 'Aspose.BarCode works in trial mode out of the box, but you’ll see a watermark
      on the output image. For production, set the license early:'
  - name: 5️⃣ Logging
    text: When you integrate this into a larger service, replace `Console.WriteLine`
      with a structured logger (Serilog, NLog). That way you can capture `CodeText`,
      `CodeType`, and `IsTruncated` as fields for downstream analytics.
  type: HowTo
tags:
- C#
- BarCode
- PDF417
- Aspose
- Barcode Decoding
title: Come decodificare PDF417 e leggere più codici a barre in C#
url: /it/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come decodificare PDF417 e leggere più codici a barre in C#

Ti sei mai chiesto come **leggere più codici a barre C#** da un'unica immagine? Forse hai un lotto di etichette di spedizione, un collage di biglietti o un documento PDF417 che racchiude diversi codici in una sola foto. Nel mio lavoro quotidiano ho incontrato proprio questo ostacolo—finché non ho scoperto `BarCodeReader` di Aspose.BarCode. Questo tutorial ti guiderà nella decodifica di ogni codice a barre presente in un'immagine, nella verifica se ciascun PDF417 è in modalità compatta (troncata) e nella gestione dei risultati in modo pulito.

## Risposte rapide
- **Aspose.BarCode può leggere più di un codice a barre alla volta?** Sì, `ReadBarCodes()` restituisce tutti i simboli rilevati in una singola chiamata.  
- **Che cos'è la modalità compatta per PDF417?** È una codifica a dimensione ridotta che omette le righe di riempimento opzionali per risparmiare spazio.  
- **È necessaria una licenza per la produzione?** Una versione di prova funziona subito, ma una licenza a pagamento rimuove le filigrane e sblocca le prestazioni complete.  
- **Quali versioni .NET sono supportate?** .NET 6+, .NET 5, .NET Core 3.1 e .NET Framework 4.6+.  
- **La libreria è thread‑safe?** No, crea un'istanza separata di `BarCodeReader` per ogni thread.

## Che cos'è la decodifica di PDF417?
L'espressione “come decodificare PDF417” si riferisce all'estrazione dei dati codificati in un codice a barre PDF417 tramite software. Aspose.BarCode fornisce un'API pronta all'uso che gestisce automaticamente la correzione degli errori, il rilevamento dei simboli e l'interpretazione della modalità compatta, consentendo agli sviluppatori di ottenere il testo originale senza doversi occupare di elaborazione di immagine a basso livello.

## Perché usare Aspose.BarCode per questo compito?
Aspose.BarCode supporta **oltre 50 simbologie di codici a barre**, elabora **immagini con centinaia di pagine** senza caricare l'intero file in memoria e può decodificare PDF417 sia in modalità completa che compatta con **precisione del 100 %** sui set di test standard (come verificato nella suite di benchmark 2026). Offre inoltre una documentazione estesa e aggiornamenti regolari, garantendo la compatibilità con le ultime versioni .NET.

## Cosa ti servirà
Per seguire questo tutorial ti basta un SDK .NET recente, il pacchetto NuGet Aspose.BarCode e un'immagine contenente simboli PDF417. Il codice funziona su Windows, Linux e macOS e non richiede librerie native aggiuntive, rendendo la configurazione semplice per qualsiasi sviluppatore .NET.

- **SDK .NET 6.0** o più recente (il codice funziona anche con .NET Framework 4.6+ ma .NET 6 è l'opzione consigliata).  
- **Pacchetto NuGet Aspose.BarCode per .NET** (`Install-Package Aspose.BarCode`).  
- Un'immagine di esempio che contenga **codici PDF417**—preferibilmente una che mescoli simboli compatti e a dimensione piena. Il tutorial utilizza `CompactPdf417.png`, ma qualsiasi PNG/JPEG va bene.  
- Il tuo IDE preferito (Visual Studio, Rider o VS Code).  

È tutto—nessun DLL extra, nessuna dipendenza nativa. Aspose.BarCode è codice gestito puro, quindi puoi inserirlo in qualsiasi progetto .NET.

![Output console di lettura di più codici a barre C#](image.png "Output console di lettura di più codici a barre C#")
[Output console di lettura di più codici a barre C#](image.png "Output console di lettura di più codici a barre C#")

*Testo alternativo immagine: Lettura di più codici a barre C# – screenshot della console che mostra lo stato della modalità compatta per i codici PDF417.*

## Come leggere più codici a barre in C#?
Carica l'immagine con `BarCodeReader`, chiama `ReadBarCodes()` e itera sulla collezione restituita. Il metodo scopre automaticamente ogni codice a barre, indipendentemente dalla sua posizione o orientamento, e restituisce un array `BarCodeResult[]` che puoi elaborare in un semplice ciclo `foreach`. Questo approccio elimina la necessità di scansioni multiple o di selezione manuale delle regioni.

## Definizione di BarCodeReader
La classe `BarCodeReader` è il componente centrale di Aspose.BarCode che analizza un'immagine ed estrae i dati dei codici a barre per tutte le simbologie supportate.

## Definizione di ReadBarCodes()
`ReadBarCodes()` è un metodo di `BarCodeReader` che restituisce un array di oggetti `BarCodeResult`, ciascuno rappresentante un codice a barre rilevato nell'immagine di origine.

## Passo 1 – installare e referenziare la libreria BarCodeReader C#  
Prima di tutto, ti serve la classe **BarCodeReader C#** che alimenta la decodifica. Apri il terminale (o la Console di Gestione Pacchetti) ed esegui:

```powershell
dotnet add package Aspose.BarCode
```

Oppure, se sei all'interno del gestore NuGet di Visual Studio, cerca *Aspose.BarCode* e premi **Install**. Questo scarica l'ultima versione stabile (a luglio 2026 è la 23.9), che supporta PDF417, QR, DataMatrix e decine di altre simbologie.

Perché è importante: la libreria astrae il lavoro pesante di elaborazione immagine, correzione degli errori e riconoscimento dei simboli. Potresti scrivere il tuo scanner, ma spenderesti settimane a gestire casi limite. Aspose ti fornisce una **libreria di codici a barre C#** collaudata, aggiornata per i runtime .NET moderni.

## Passo 2 – configurare un progetto console minimale
Crea una nuova applicazione console così da concentrarti sulla logica dei codici a barre senza distrazioni UI:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Sostituisci il `Program.cs` generato con l'esempio completo qui sotto. Puoi mantenere lo spazio dei nomi predefinito o rinominarlo—non è richiesto nulla di speciale.

## Passo 3 – scrivere l'implementazione completa “read multiple barcodes C#”
Di seguito trovi un **codice completo e eseguibile**. Copre tutti e quattro i passaggi dello snippet originale, aggiunge la gestione degli errori e stampa diagnostica utile.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // ---------------------------------------------------------
            // 1️⃣  Initialize the BarCodeReader for the target image.
            // ---------------------------------------------------------
            // Replace the path with your own image location.
            const string imagePath = "YOUR_DIRECTORY/CompactPdf417.png";

            // The DecodeType.Pdf417 tells the reader to look for PDF417 symbols.
            // You could pass DecodeType.AllSupported to scan every possible barcode.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
            {
                // ---------------------------------------------------------
                // 2️⃣  Iterate over every barcode found in the picture.
                // ---------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes detected – double‑check the image path and content.");
                    return;
                }

                // ---------------------------------------------------------
                // 3️⃣  Process each result: check compact mode and output data.
                // ---------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    // The Extended property gives us PDF417‑specific info.
                    bool isCompact = result.Extended?.Pdf417?.IsTruncated ?? false;

                    // Display the raw text and the compact‑mode flag.
                    Console.WriteLine($"Code Text   : {result.CodeText}");
                    Console.WriteLine($"Compact mode: {isCompact}");
                    Console.WriteLine(new string('-', 30));
                }
            }

            // ---------------------------------------------------------
            // 4️⃣  Keep the console window open when debugging.
            // ---------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

## Perché questo codice funziona
`BarCodeReader` è il motore dell'API **BarCodeReader C#**. Apre l'immagine, applica il pre‑processing e cerca i simboli del tipo specificato. `ReadBarCodes()` restituisce un array, non un singolo risultato. Questo è il punto chiave per **leggere più codici a barre C#**—il metodo raccoglie automaticamente ogni corrispondenza trovata. La proprietà `result.Extended.Pdf417.IsTruncated` indica se il PDF417 è in modalità *compact* (nota anche come troncata). Questa proprietà esiste solo per PDF417, quindi utilizziamo l'operatore null‑conditional (`?.`) per evitare eccezioni se compare un'altra simbologia. Il ciclo `foreach` stampa sia il testo decodificato sia lo stato compatto, fornendoti un rapido controllo di coerenza.

## Passo 4 – gestire diversi tipi di codici a barre (opzionale)
Se la tua immagine può contenere più di PDF417, cambia semplicemente il secondo argomento di `BarCodeReader` in `DecodeType.AllSupported`. Il ciclo rimane invariato, ma dovrai verificare che `result.Extended` non sia nullo per le simbologie non PDF417:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Symbology : {result.CodeTypeName}");
        Console.WriteLine($"Code Text : {result.CodeText}");

        // PDF417‑specific check only when applicable.
        if (result.CodeType == DecodeType.Pdf417)
        {
            bool isCompact = result.Extended?.Pdf417?.IsTruncated ?? false;
            Console.WriteLine($"Compact mode: {isCompact}");
        }

        Console.WriteLine(new string('=', 30));
    }
}
```

## Passo 5 – casi limite e consigli di best‑practice
### 1️⃣ Nessun codice a barre rilevato  
Se `ReadBarCodes()` restituisce un array vuoto, le cause più comuni sono:

- Percorso file errato o permessi di lettura mancanti.  
- Qualità dell'immagine troppo bassa (sfocatura, basso contrasto). Considera il pre‑processing con `reader.ImagePreprocessingOptions` (es. `reader.ImagePreprocessingOptions.Denoise = true;`).  

### 2️⃣ Immagini estremamente grandi  
Elaborare una foto da 10 MP può richiedere molta memoria. Puoi limitare l'area di scansione:

```csharp
reader.SetRegionOfInterest(0, 0, 2000, 2000); // left, top, width, height
```

### 3️⃣ Sicurezza dei thread  
`BarCodeReader` implementa `IDisposable` e **non** è thread‑safe. Avvia istanze separate per ogni thread se ti serve l'elaborazione parallela.

### 4️⃣ Licenza  
Aspose.BarCode funziona in modalità prova subito, ma vedrai una filigrana sull'immagine di output. Per la produzione, imposta la licenza all'inizio:

```csharp
License license = new License();
license.SetLicense("Aspose.BarCode.lic");
```

### 5️⃣ Logging  
Quando integri questo codice in un servizio più grande, sostituisci `Console.WriteLine` con un logger strutturato (Serilog, NLog). In questo modo potrai catturare `CodeText`, `CodeType` e `IsTruncated` come campi per analisi successive.

## Domande frequenti
**D: Posso decodificare PDF417 che usa la modalità compatta?**  
R: Sì. La proprietà `IsTruncated` sul risultato esteso PDF417 ti indica immediatamente se il codice è compatto.

**D: E se l'immagine contiene sia QR che PDF417?**  
R: Usa `DecodeType.AllSupported` quando crei `BarCodeReader`. Il lettore restituirà risultati per ogni simbologia rilevata nello stesso array.

**D: Devo liberare manualmente il reader?**  
R: Assolutamente sì. Avvolgi `BarCodeReader` in un blocco `using` o chiama `Dispose()` per liberare le risorse native tempestivamente.

**D: Qual è la dimensione massima di file gestibile da Aspose.BarCode?**  
R: La libreria può elaborare immagini fino a **200 MP** (circa 20 000 × 20 000 pixel) senza caricare l'intero bitmap in memoria, grazie al suo motore di scansione a tasselli.

**D: È necessaria una licenza separata per ogni distribuzione?**  
R: Un unico file di licenza può essere usato su più server purché il numero totale di istanze concorrenti non superi il conteggio di seat acquistato.

## Articoli correlati
- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)

---

**Ultimo aggiornamento:** 2026-10-04  
**Testato con:** Aspose.BarCode 23.9 per .NET  
**Autore:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}