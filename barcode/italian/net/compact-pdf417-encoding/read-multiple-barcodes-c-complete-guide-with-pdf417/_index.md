---
category: general
date: 2026-07-30
description: Leggi più codici a barre in C# usando Aspose.BarCode. Impara passo passo
  come decodificare PDF417, rilevare la modalità compatta e gestire molti codici a
  barre in un'unica immagine.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read multiple barcodes c#
- BarCodeReader C#
- PDF417 decoding
- barcode compact mode
- C# barcode library
language: it
lastmod: 2026-07-30
og_description: Leggi più codici a barre in C# con Aspose.BarCode. Questa guida ti
  mostra come decodificare tutti i codici a barre in un'immagine, verificare la modalità
  compatta e integrare nelle applicazioni .NET.
og_image_alt: Screenshot of C# console output showing compact mode status for PDF417
  barcodes
og_title: Leggi più codici a barre C# – Tutorial completo per PDF417
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Read multiple barcodes C# using Aspose.BarCode. Learn step‑by‑step
    how to decode PDF417, detect compact mode, and handle many barcodes in one image.
  headline: Read Multiple Barcodes C# – Complete Guide with PDF417
  type: TechArticle
- description: Read multiple barcodes C# using Aspose.BarCode. Learn step‑by‑step
    how to decode PDF417, detect compact mode, and handle many barcodes in one image.
  name: Read Multiple Barcodes C# – Complete Guide with PDF417
  steps:
  - name: Why This Code Works
    text: '- **`BarCodeReader`** is the workhorse from the **BarCodeReader C#** API.
      It opens the image, applies pre‑processing, and searches for symbols of the
      type you specify. - **`ReadBarCodes()`** returns an array, not just a single
      result. That’s the key to **reading multiple barcodes C#**—the method aut'
  - name: 1️⃣ No Barcodes Detected
    text: 'If `ReadBarCodes()` returns an empty array, the most common culprits are:'
  - name: 2️⃣ Extremely Large Images
    text: 'Processing a 10 MP photo can be memory‑hungry. You can limit the scan area:'
  - name: 3️⃣ Thread‑Safety
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
title: Leggi più codici a barre C# – Guida completa con PDF417
url: /it/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Leggi più codici a barre C# – Guida completa con PDF417

Ti sei mai chiesto come **leggere più codici a barre C#** da un’unica immagine? Forse hai un lotto di etichette di spedizione, un collage di biglietti o un documento PDF417 che raggruppa diversi codici in una sola foto. Nel mio lavoro quotidiano, mi sono imbattuto proprio in questo ostacolo—finché non ho scoperto `BarCodeReader` di Aspose.BarCode. Questo tutorial ti guiderà nella decodifica di ogni codice a barre presente in un’immagine, nel capire se ciascun PDF417 è in modalità compatta (troncata) e nella gestione pulita dei risultati.

Inseriremo anche qualche suggerimento extra—come cosa fare quando l’immagine contiene diverse simbologie di codici a barre, o quando una scansione non restituisce alcun risultato. Alla fine avrai un’app console pronta all’uso che **legge più codici a barre C#** come un professionista.

## Cosa ti servirà

Prima di iniziare, assicurati di avere quanto segue sulla tua macchina:

- **.NET 6.0** SDK o versioni successive (il codice funziona anche con .NET Framework 4.6+, ma .NET 6 è l’opzione consigliata).
- **Aspose.BarCode for .NET** pacchetto NuGet (`Install-Package Aspose.BarCode`).
- Un’immagine di esempio che contenga codici **PDF417**—preferibilmente una che mescoli simboli compatti e a grandezza intera. Il tutorial utilizza `CompactPdf417.png`, ma qualsiasi PNG/JPEG andrà bene.
- Il tuo IDE preferito (Visual Studio, Rider o VS Code).  

Questo è tutto—nessun DLL aggiuntivo, nessuna dipendenza nativa. Aspose.BarCode è puro codice gestito, quindi puoi inserirlo in qualsiasi progetto .NET.

![Output della console per leggere più codici a barre C#](image.png "Output della console per leggere più codici a barre C#")

*Testo alternativo dell’immagine: Leggi più codici a barre C# – screenshot della console che mostra lo stato della modalità compatta per i codici PDF417.*

## Passo 1 – Installa e fai riferimento alla libreria BarCodeReader C#  

Prima di tutto, ti serve la classe **BarCodeReader C#** che alimenta la decodifica. Apri il terminale (o la Console di Gestione Pacchetti) ed esegui:

```powershell
dotnet add package Aspose.BarCode
```

Oppure, se sei dentro il gestore NuGet di Visual Studio, cerca *Aspose.BarCode* e premi **Install**. Questo scarica l’ultima versione stabile (a luglio 2026 è la 23.9), che supporta PDF417, QR, DataMatrix e decine di altre simbologie.

Perché è importante: la libreria astrae il lavoro pesante di elaborazione immagine, correzione errori e riconoscimento simboli. Potresti scrivere il tuo scanner, ma impiegheresti settimane a gestire i casi limite. Aspose ti fornisce una **libreria di codici a barre C#** collaudata, aggiornata per i runtime .NET moderni.

## Passo 2 – Configura un progetto console minimale  

Crea una nuova app console così da concentrarti solo sulla logica dei codici a barre senza distrazioni UI:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Sostituisci il `Program.cs` generato con l’esempio completo qui sotto. Puoi mantenere lo spazio dei nomi predefinito o rinominarlo—non è richiesto nulla di speciale.

## Passo 3 – Scrivi l'implementazione completa “Read Multiple Barcodes C#”

Di seguito trovi un **codice completo, eseguibile**. Copre tutti e quattro i passaggi dello snippet originale, aggiunge la gestione degli errori e stampa diagnostica utile.

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

### Perché questo codice funziona

- **`BarCodeReader`** è il motore principale dell’API **BarCodeReader C#**. Apre l’immagine, applica il pre‑processing e ricerca i simboli del tipo specificato.
- **`ReadBarCodes()`** restituisce un array, non un singolo risultato. Questa è la chiave per **leggere più codici a barre C#**—il metodo raccoglie automaticamente ogni corrispondenza trovata.
- **`result.Extended.Pdf417.IsTruncated`** indica se il PDF417 è in modalità *compact* (nota anche come troncata). Questa proprietà esiste solo per PDF417, quindi usiamo l’operatore condizionale null (`?.`) per evitare eccezioni se compare un’altra simbologia.
- Il ciclo `foreach` stampa sia il testo decodificato sia lo stato della modalità compatta, fornendoti un rapido controllo di coerenza.

## Passo 4 – Gestione di diversi tipi di codici a barre (Opzionale)

Se la tua immagine può contenere più di PDF417, cambia semplicemente il secondo argomento di `BarCodeReader` in `DecodeType.AllSupported`. Il ciclo rimane invariato, ma dovrai verificare che `result.Extended` sia null per simboli non PDF417:

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

Questa piccola modifica trasforma la tua **libreria di codici a barre C#** in uno scanner universale, perfetto per lotti con simbologie miste.

## Passo 5 – Casi limite e consigli di best practice  

### 1️⃣ Nessun codice a barre rilevato  
Se `ReadBarCodes()` restituisce un array vuoto, i colpevoli più comuni sono:

- Percorso file errato o permessi di lettura mancanti.  
- Qualità dell’immagine troppo bassa (sfocatura, basso contrasto). Considera il pre‑processing con `reader.ImagePreprocessingOptions` (es. `reader.ImagePreprocessingOptions.Denoise = true;`).

### 2️⃣ Immagini estremamente grandi  
Elaborare una foto da 10 MP può consumare molta memoria. Puoi limitare l’area di scansione:

```csharp
reader.SetRegionOfInterest(0, 0, 2000, 2000); // left, top, width, height
```

### 3️⃣ Sicurezza dei thread  
`BarCodeReader` implementa `IDisposable` e **non** è thread‑safe. Crea istanze separate per ogni thread se ti serve l’elaborazione parallela.

### 4️⃣ Licenza  
Aspose.BarCode funziona in modalità trial subito dopo l’installazione, ma vedrai una filigrana sull’immagine di output. Per la produzione, imposta la licenza all’inizio:

```csharp
License license = new License();
license.SetLicense("Aspose.BarCode.lic");
```

### 5️⃣ Logging  
Quando integri questo codice in un servizio più ampio, sostituisci `Console.WriteLine` con un logger strutturato (Serilog, NLog). In questo modo potrai catturare `CodeText`, `CodeType` e `IsTruncated` come campi per analisi successive.

## Riepilogo dell'esempio completo funzionante  

Mettendo tutto insieme, ecco il *programma intero* che puoi copiare‑incollare in `Program.cs`:

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
            const string imagePath = "YOUR_DIRECTORY


## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell’API ed esplorare approcci alternativi nei tuoi progetti.

- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}