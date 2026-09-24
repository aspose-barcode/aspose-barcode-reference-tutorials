---
category: general
date: 2026-08-19
description: Genera codice a barre PDF417 in C# rapidamente. Scopri come generare
  il codice a barre PDF417 in C# usando Aspose.BarCode con modalità compatta e impostazioni
  personalizzate.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode c#
- Aspose.BarCode PDF417
- compact PDF417 barcode
- barcode X‑dimension
language: it
lastmod: 2026-08-19
og_description: Genera codice a barre PDF417 in C# con Aspose.BarCode. Questo tutorial
  mostra come generare un codice a barre PDF417 in C# in modalità compatta, impostare
  la dimensione X e salvare come PNG.
og_image_alt: Screenshot of a compact PDF417 barcode saved as PNG
og_title: Genera codice a barre PDF417 in C# – guida passo passo
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  headline: Generate PDF417 barcode in C# – complete guide with compact layout
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  name: Generate PDF417 barcode in C# – complete guide with compact layout
  steps:
  - name: Why each line matters
    text: '* **`EncodeTypes.Pdf417`** – selects the PDF417 symbology, which supports
      up to ~1.1 KB of data. * **`XDimension.Pixels = 2`** – sets the basic bar width.
      Smaller values make the barcode thinner; larger values improve readability on
      low‑resolution devices. * **`Pdf417.Columns = 3`** – limits the num'
  - name: 4️⃣ Generate a high‑density PDF417 for printing
    text: 'If you need a barcode that fits on a small label, increase the column count
      and lower the X‑dimension:'
  - name: 5️⃣ Change the output format to SVG for vector scaling
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 6️⃣ Encode binary data (e.g., a byte array)
    text: 'If you need to embed binary payloads, convert them to a Base64 string first:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Genera codice a barre PDF417 in C# – guida completa con layout compatto
url: /it/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide-with-compact-lay/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generare PDF417 barcode in C# – guida completa

Se hai bisogno di **generare PDF417 barcode** in un'applicazione .NET, questo tutorial ti mostra esattamente come farlo. Vedrai un esempio conciso, pronto per la produzione, che crea un PDF417 barcode compatto, personalizza la X‑dimension e salva il risultato come immagine PNG.

Generare un PDF417 barcode è comune quando devi codificare grandi quantità di dati — come informazioni sui biglietti, manifesti di spedizione o documenti d'identità — in un formato leggibile da macchine. L'uso di Aspose.BarCode rende il processo semplice, e il codice funziona con .NET 6+ o .NET Framework 4.7.2 e versioni successive.

In questa guida farai:

* Installa il pacchetto NuGet Aspose.BarCode.
* Scrivi un programma C# autonomo che **generi PDF417 barcode** con un piccolo numero di colonne e modalità compatta (troncata).
* Regola la larghezza della barra (X‑dimension) per una resa più nitida.
* Salva il codice a barre come file PNG.
* Esplora variazioni, casi limite e consigli di best‑practice.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* Visual Studio 2022 (o qualsiasi IDE C#) con .NET 6 SDK installato.
* Accesso a Internet per scaricare il pacchetto NuGet **Aspose.BarCode**.
* Permessi di scrittura su una cartella dove verrà salvato il file PNG.

Non sono richieste librerie aggiuntive; Aspose.BarCode gestisce internamente la codifica delle immagini.

## Passo 1: Aggiungi il pacchetto Aspose.BarCode

Apri il tuo progetto in Visual Studio, fai clic con il tasto destro sulla soluzione e seleziona **Manage NuGet Packages**. Cerca `Aspose.BarCode` e installa l'ultima versione stabile.

```bash
dotnet add package Aspose.BarCode
```

> **Consiglio professionale:** mantieni il pacchetto aggiornato. Le nuove versioni includono spesso miglioramenti delle prestazioni e supporto per i runtime .NET più recenti.

## Passo 2: Crea un'applicazione console minimale

Crea un nuovo progetto console C# se non ne hai già uno:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

Sostituisci il contenuto di `Program.cs` con l'esempio completo qui sotto. Questo programma dimostra **come generare PDF417 barcode C#** dall'inizio alla fine.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Define the data you want to encode.
            // -----------------------------------------------------------------
            // The string can contain Unicode characters; Aspose.BarCode handles
            // encoding automatically. Here we use characters with diacritics to
            // prove Unicode support.
            string data = "Åspóse.Barcóde©";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarcodeGenerator for PDF417.
            // -----------------------------------------------------------------
            // EncodeTypes.Pdf417 tells the library which symbology to use.
            // The constructor also accepts the data to encode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // -----------------------------------------------------------------
            // 3️⃣  Configure visual parameters.
            // -----------------------------------------------------------------
            // • XDimension controls the bar width in pixels. A value of 2 gives
            //   a clear, readable barcode on most screens.
            // • Columns define how many data columns the barcode will use.
            //   Fewer columns produce a more compact image but increase the
            //   number of rows.
            // • Truncate enables “compact mode”, which removes the trailing
            //   stop pattern and reduces the overall size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true; // compact mode

            // -----------------------------------------------------------------
            // 4️⃣  Choose the output format and save the image.
            // -----------------------------------------------------------------
            // BarCodeImageFormat.Png yields a lossless PNG file that works
            // well for web, print, and further image processing.
            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to: {outputPath}");
        }
    }
}
```

### Perché ogni riga è importante

* **`EncodeTypes.Pdf417`** – seleziona la simbologia PDF417, che supporta fino a ~1,1 KB di dati.  
* **`XDimension.Pixels = 2`** – imposta la larghezza di base della barra. Valori più piccoli rendono il codice a barre più sottile; valori più grandi migliorano la leggibilità su dispositivi a bassa risoluzione.  
* **`Pdf417.Columns = 3`** – limita il numero di colonne, costringendo il generatore a usare più righe, il che produce un codice a barre più alto ma più stretto.  
* **`Pdf417.Truncate = true`** – attiva la modalità compatta, rimuovendo il pattern di stop e riducendo l'immagine senza perdere l'integrità dei dati.  
* **`Save(..., BarCodeImageFormat.Png)`** – scrive un file PNG. Puoi anche scegliere `Jpeg`, `Bmp` o `Svg` a seconda delle esigenze successive.

Esegui il programma:

```bash
dotnet run
```

Dovresti vedere l'output della console che conferma la posizione del file, e la cartella conterrà `CompactPdf417.png`. Aprendo il PNG vedrai un PDF417 barcode chiaro e compatto che codifica la stringa Unicode.

## Passo 3: Verifica il codice a barre (opzionale ma consigliato)

Per assicurarti che il codice a barre sia leggibile, puoi usare qualsiasi app scanner PDF417 standard su smartphone o una libreria decoder desktop. Il testo codificato dovrebbe corrispondere esattamente alla stringa originale `data`, inclusi i caratteri speciali.

Se incontri problemi di decodifica:

* Aumenta `XDimension` a 3 o 4 pixel.  
* Riduci il numero di colonne (ad esempio imposta `Columns = 2`).  
* Disabilita `Truncate` (`Truncate = false`) per aggiungere il pattern di stop.

Queste regolazioni scambiano dimensione con leggibilità, utile per stampanti o scanner a bassa risoluzione.

## Passo 4: Esplora variazioni comuni

### 4️⃣ Genera un PDF417 ad alta densità per la stampa

Se ti serve un codice a barre che si adatti a un'etichetta piccola, aumenta il conteggio delle colonne e abbassa la X‑dimension:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 1;
generator.Parameters.Barcode.Pdf417.Columns = 6;
generator.Parameters.Barcode.Pdf417.Truncate = false; // keep full pattern
```

### 5️⃣ Cambia il formato di output in SVG per il ridimensionamento vettoriale

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

L'output SVG si scala senza perdita di qualità, perfetto per pagine web responsive.

### 6️⃣ Codifica dati binari (ad esempio, un array di byte)

Se devi incorporare payload binari, converti prima in una stringa Base64:

```csharp
byte[] payload = new byte[] { 0x01, 0xFF, 0xA5 };
string base64 = Convert.ToBase64String(payload);
generator = new BarcodeGenerator(EncodeTypes.Pdf417, base64);
```

Il codice a barre ora trasporta le informazioni binarie, e il decoder dovrà invertire il passaggio Base64.

## Domande frequenti

| Domanda | Risposta |
|----------|--------|
| **Posso generare PDF417 senza Aspose?** | Sì, esistono altre librerie come ZXing.Net o Dynamsoft, ma Aspose.BarCode offre un controllo di layout più ricco (colonne, troncamento) e una migliore gestione Unicode. |
| **Qual è la lunghezza massima dei dati?** | PDF417 può codificare fino a 1 108 byte (≈ 1 KB) di dati binari. Se superi questo limite, considera di suddividere i dati su più codici a barre. |
| **La modalità compatta è conforme agli standard?** | Il PDF417 troncato fa parte della specifica ISO/IEC 15438 ed è ampiamente supportato, ma verifica che lo scanner di destinazione la supporti esplicitamente. |
| **Come cambio il colore di sfondo?** | Imposta `generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;` e `generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;` prima di salvare. |

## Conclusione

Ora sai **come generare PDF417 barcode C#** usando Aspose.BarCode, come affinare la X‑dimension, abilitare la modalità compatta e esportare il risultato come immagine PNG. L'esempio completo, eseguibile, può essere copiato in qualsiasi progetto .NET, e le variazioni mostrate ti permettono di adattare il codice a barre per stampa, web o scenari con payload binari.

Prossimi passi che potresti esplorare:

* Integrare la generazione del codice a barre in un'API ASP.NET Core che restituisce l'immagine su richiesta.  
* Combinare PDF417 con codici QR sulla stessa etichetta per la scansione a doppio formato.  
* Utilizzare la classe `Reader` di Aspose.BarCode per decodificare l'immagine generata e verificare i dati programmaticamente.

Buon coding e goditi la flessibilità che le soluzioni **generate PDF417 barcode** offrono alle tue applicazioni!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API e a esplorare approcci alternativi di implementazione nei tuoi progetti.

- [Come creare un barcode – PDF417 compatto con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Come generare un'immagine barcode con personalizzazione dello spazio supplementare usando Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [Come generare un barcode Aztec con rapporto d'aspetto personalizzato usando Aspose.BarCode per .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}