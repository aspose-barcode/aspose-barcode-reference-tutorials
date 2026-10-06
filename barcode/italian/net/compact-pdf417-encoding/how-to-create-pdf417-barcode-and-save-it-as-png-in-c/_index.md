---
category: general
date: 2026-10-05
description: Scopri come creare un codice a barre PDF417 in C# e generare un PNG del
  codice a barre con codice passo‑passo e consigli sulle migliori pratiche.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- generate barcode PNG
- how to generate PDF417
language: it
lastmod: 2026-10-05
og_description: Crea un codice a barre PDF417 in C# e genera immediatamente un PNG
  del codice a barre. Segui questo tutorial completo per una soluzione pronta per
  la produzione.
og_image_alt: Example of a compact PDF417 barcode created with C#
og_title: Crea codice a barre PDF417 in C# – guida completa per generare PNG
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
    step‑by‑step code and best‑practice tips.
  headline: How to create PDF417 barcode and save it as PNG in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
    step‑by‑step code and best‑practice tips.
  name: How to create PDF417 barcode and save it as PNG in C#
  steps:
  - name: Expected output
    text: When you open `CompactPdf417.png`, you should see a vertical, high‑density
      barcode that encodes the string *Åspóse.Barcóde©*. Scanning the image with any
      PDF417 reader returns the original text.
  - name: Generating other image formats
    text: 'If you prefer JPEG or BMP, change the `BarCodeImageFormat` enum:'
  - name: Adjusting error correction
    text: 'For harsh environments (e.g., outdoor signage), increase the error‑correction
      level:'
  - name: Encoding binary data
    text: 'PDF417 can encode binary payloads. Pass a `byte[]` instead of a string:'
  - name: Handling very long strings
    text: 'When the data exceeds the default capacity, the generator automatically
      creates additional rows. You can limit the row count to avoid oversized images:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- image generation
title: Come creare un codice a barre PDF417 e salvarlo come PNG in C#
url: /it/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un codice a barre PDF417 e salvarlo come PNG in C#

Se hai bisogno di **creare un codice a barre PDF417** in un'applicazione .NET, questa guida ti mostra esattamente come farlo. Otterrai uno snippet C# pronto all'uso che genera un file **PNG del codice a barre** di alta qualità, e comprenderai ogni impostazione che influenza il risultato.

Generare codici a barre è una necessità comune per sistemi di biglietteria, tracciamento dell'inventario e codifica di documenti sicuri. Alla fine di questo tutorial potrai rispondere alla domanda “**come generare PDF417**” con un esempio completo e eseguibile.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6.0 SDK o versioni successive installate  
* Un ambiente di sviluppo come Visual Studio 2022 o VS Code  
* Il pacchetto NuGet **Aspose.BarCode for .NET** (o qualsiasi libreria compatibile che supporti PDF417)  

Puoi aggiungere il pacchetto con il seguente comando:

```bash
dotnet add package Aspose.BarCode
```

Il codice sottostante utilizza l'API Aspose perché offre un controllo granulare sui parametri PDF417 e supporta l'esportazione PNG subito pronto all'uso.

## Passo 1: Configurare il progetto e importare i namespace

Crea un nuovo progetto console e importa i namespace richiesti:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Il namespace `Aspose.BarCode.Generation` contiene la classe `BarcodeGenerator`, che è il punto di ingresso per **creare immagini di codice a barre PDF417**.

## Passo 2: Creare il codice a barre PDF417 con il testo desiderato

Istanzia il generatore con l'enumerazione `EncodeTypes.Pdf417` e i dati che desideri codificare. L'esempio utilizza una stringa che contiene caratteri speciali per dimostrare la gestione Unicode:

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

Il generatore ora contiene un oggetto barcode che puoi configurare prima del rendering.

## Passo 3: Configurare i parametri visivi

La messa a punto del codice a barre migliora la leggibilità e riduce le dimensioni dell'immagine. Le impostazioni più frequentemente regolate sono **X‑dimension**, **columns** e **compact mode**.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 4: Define the number of columns for the PDF417 code
generator.Parameters.Barcode.Pdf417.Columns = 3;

// Step 5: Enable compact (truncated) mode to reduce the barcode size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

* **X‑dimension** controlla la larghezza di ogni modulo; un valore di `2` pixel produce un barcode compatto ma leggibile.  
* **Columns** determina quante colonne di dati utilizza il codice. Meno colonne rendono il barcode più stretto ma più alto.  
* **Truncate** attiva la modalità “compact” definita dalla specifica PDF417, che rimuove le righe di riempimento non necessarie.

Puoi sperimentare con `Rows` e `ErrorCorrectionLevel` se il tuo caso d'uso richiede una maggiore resilienza ai danni.

## Passo 4: Salvare il codice a barre come immagine PNG

Infine, esporta il barcode in un file PNG. PNG preserva i bordi nitidi e supporta la trasparenza, rendendolo ideale per scenari web e di stampa.

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Eseguendo il programma viene creato `CompactPdf417.png` nella directory specificata. L'immagine appare così:

![Codice a barre PDF417 compatto creato con C#](compact-pdf417.png "Esempio di un codice a barre PDF417 compatto creato con C#")

*Il testo alternativo sopra contiene la parola chiave principale, soddisfacendo sia i requisiti SEO che di accessibilità.*

## Esempio completo e eseguibile

Mettendo insieme tutti i pezzi, ecco un programma autonomo che puoi copiare, incollare ed eseguire:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1. Initialize the generator with PDF417 type and sample data
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

        // 2. Configure size and compactness
        generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
        generator.Parameters.Barcode.Pdf417.Columns = 3;           // number of columns
        generator.Parameters.Barcode.Pdf417.Truncate = true;       // enable compact mode

        // 3. Optional: increase error correction for damaged prints
        // generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;

        // 4. Export to PNG
        string outputPath = @"C:\Barcodes\CompactPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

### Output previsto

Quando apri `CompactPdf417.png`, dovresti vedere un codice a barre verticale ad alta densità che codifica la stringa *Åspóse.Barcóde©*. Scansionando l'immagine con qualsiasi lettore PDF417 otterrai il testo originale.

## Perché queste impostazioni sono importanti

* **X‑dimension** influenza sia le dimensioni fisiche sia la velocità di scansione. Moduli più piccoli aumentano la densità dei dati ma possono richiedere scanner ad alta risoluzione.  
* **Columns** influisce sul rapporto d'aspetto. Per ricevute mobili, un numero basso di colonne mantiene il barcode sufficientemente stretto da adattarsi a carta stretta.  
* **Truncate** riduce il numero di righe, risparmiando inchiostro e spazio senza sacrificare l'integrità dei dati, poiché PDF417 include già parole di correzione degli errori.

Comprendere questi parametri ti consente di adattare il barcode alle limitazioni del tuo supporto di destinazione, sia esso una stampante di etichette, una pagina web o un'app mobile.

## Varianti comuni e casi limite

### Generare altri formati immagine

Se preferisci JPEG o BMP, modifica l'enumerazione `BarCodeImageFormat`:

```csharp
generator.Save(@"C:\Barcodes\Pdf417.jpg", BarCodeImageFormat.Jpeg);
```

JPEG comprime l'immagine ma può introdurre artefatti che influenzano la scansione a piccole dimensioni.

### Regolare la correzione degli errori

Per ambienti difficili (ad es., segnaletica esterna), aumenta il livello di correzione degli errori:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 8; // max is 8
```

Livelli più alti aggiungono più ridondanza, rendendo il barcode più grande ma più robusto.

### Codificare dati binari

PDF417 può codificare payload binari. Passa un `byte[]` invece di una stringa:

```csharp
byte[] binaryData = new byte[] { 0x01, 0xFF, 0xA5 };
generator = new BarcodeGenerator(EncodeTypes.Pdf417, binaryData);
```

La libreria passa automaticamente alla modalità binaria.

### Gestire stringhe molto lunghe

Quando i dati superano la capacità predefinita, il generatore crea automaticamente righe aggiuntive. Puoi limitare il conteggio delle righe per evitare immagini sovradimensionate:

```csharp
generator.Parameters.Barcode.Pdf417.Rows = 30; // max rows
```

Se il contenuto ancora non entra, considera di suddividerlo su più codici a barre.

## Consigli professionali

* **Cache the generator** se devi creare molti codici a barre con le stesse impostazioni. Riutilizzare l'oggetto evita ripetute allocazioni di risorse interne.  
* **Imposta `Resolution`** su `ImageOptions` se ti serve un DPI specifico per la stampa:

  ```csharp
  generator.Parameters.ImageResolution = 300; // DPI
  ```

* **Valida l'output** programmaticamente con `BarCodeReader` per garantire che il PNG generato possa essere decodificato prima di distribuirlo agli utenti.

## Conclusione

Ora sai come **creare un codice a barre PDF417** in C# e **generare file PNG di codice a barre** con pieno controllo su dimensione, colonne e modalità compatta. L'esempio completo dimostra l'approccio standard, spiega perché ogni impostazione è importante e copre variazioni come la correzione degli errori, formati alternativi e dati binari. Usa i consigli sopra per adattare la soluzione al tuo flusso di lavoro specifico, sia che tu stia costruendo un sistema di biglietteria, un generatore di etichette logistiche o un codificatore di documenti sicuri.

---

**Prossimi passi**

* Esplora altre simbologie 2D (DataMatrix, QR) usando la stessa classe `BarcodeGenerator`.  
* Integra la creazione del codice a barre in un'API ASP.NET Core per servire PNG su richiesta.  
* Combina l'immagine del codice a barre con librerie di generazione PDF per incorporarla direttamente nei report.

Buona programmazione!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come creare un codice a barre pdf417 in C# – guida passo‑passo](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [Come generare un codice a barre micro pdf417 in C# – guida passo‑passo](/barcode/english/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/)
- [Come creare un codice a barre PDF417 in C# con modalità compatta](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}