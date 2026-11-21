---
category: general
date: 2026-11-20
description: Scopri come generare il codice a barre PDF417 in C# usando BarcodeGenerator.
  Questa guida passo‑passo copre la X‑Dimension, le impostazioni delle colonne e l'esportazione
  PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- PDF417 barcode in C#
- BarcodeGenerator EncodeTypes
- set XDimension pixels
- configure PDF417 columns
- save barcode as PNG
language: it
lastmod: 2026-11-20
og_description: Genera rapidamente un codice a barre PDF417 in C#. Segui questa guida
  per impostare le dimensioni, le colonne e esportare il codice a barre come immagine
  PNG.
og_image_alt: Screenshot of C# code that generates a PDF417 barcode and saves it as
  a PNG file
og_title: Genera codice a barre PDF417 in C# – guida completa passo‑a‑passo
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to generate PDF417 barcode in C# using BarcodeGenerator.
    This step‑by‑step guide covers X‑Dimension, column settings, and PNG export.
  headline: How to generate PDF417 barcode in C# with BarcodeGenerator
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using BarcodeGenerator.
    This step‑by‑step guide covers X‑Dimension, column settings, and PNG export.
  name: How to generate PDF417 barcode in C# with BarcodeGenerator
  steps:
  - name: '**Initialize the generator** – The `BarcodeGenerator` ties the chosen symbology
      (`EncodeTypes.Pdf417`) to the data you want to encode. Without this object you
      cannot access any further configuration.'
    text: '**Initialize the generator** – The `BarcodeGenerator` ties the chosen symbology
      (`EncodeTypes.Pdf417`) to the data you want to encode. Without this object you
      cannot access any further configuration.'
  - name: '**Set X‑Dimension** – PDF417 is built from tiny rectangular modules. Changing
      `XDimension.Pixels` lets you control the barcode’s visual density, which is
      crucial for readability on low‑resolution displays or printers.'
    text: '**Set X‑Dimension** – PDF417 is built from tiny rectangular modules. Changing
      `XDimension.Pixels` lets you control the barcode’s visual density, which is
      crucial for readability on low‑resolution displays or printers.'
  - name: '**Configure columns** – PDF417 can arrange its codewords in a variable
      number of columns. Fewer columns produce a taller barcode, while more columns
      flatten it. Adjust this to fit the space where the image will be placed.'
    text: '**Configure columns** – PDF417 can arrange its codewords in a variable
      number of columns. Fewer columns produce a taller barcode, while more columns
      flatten it. Adjust this to fit the space where the image will be placed.'
  - name: '**Save as PNG** – PNG is a loss‑less format, preserving the sharp edges
      required for accurate scanning. You could also choose JPEG or BMP, but PNG is
      the safest default.'
    text: '**Save as PNG** – PNG is a loss‑less format, preserving the sharp edges
      required for accurate scanning. You could also choose JPEG or BMP, but PNG is
      the safest default.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose.BarCode
title: Come generare un codice a barre PDF417 in C# con BarcodeGenerator
url: /it/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come generare il codice a barre PDF417 in C# con BarcodeGenerator

Se hai bisogno di **generare un codice a barre PDF417** in un'applicazione .NET, questa guida ti mostra esattamente come farlo. Vedrai un esempio completo e eseguibile che imposta la X‑Dimension, sceglie il numero di colonne e salva il risultato come immagine PNG.

Generare un codice a barre PDF417 è comune quando devi codificare una grande quantità di dati — come una patente di guida, una carta d'imbarco o un record di inventario — in un'immagine compatta e leggibile da macchina. In questo tutorial usiamo la classe **BarcodeGenerator** della libreria Aspose.BarCode, ma i concetti si applicano a qualsiasi libreria che supporti PDF417.

Entro la fine di questo articolo sarai in grado di:

* Inizializzare un `BarcodeGenerator` per la codifica PDF417.  
* Regolare la dimensione del modulo con **set XDimension pixels**.  
* Controllare il layout usando **configure PDF417 columns**.  
* **Salvare il codice a barre come PNG** per l'uso in pagine web, app mobili o materiale stampato.  

> **Prerequisiti**  
> * .NET 6.0 o successivo (il codice funziona anche con .NET Framework 4.7+).  
> * Un riferimento al pacchetto NuGet **Aspose.BarCode** (`Install-Package Aspose.BarCode`).  
> * Familiarità di base con C# e Visual Studio (o qualsiasi IDE preferisci).

---

## Come generare il codice a barre PDF417 in C#

Il cuore della soluzione è un breve processo in quattro passaggi. Ogni passaggio è racchiuso in un metodo dedicato così da poter riutilizzare la logica in progetti più grandi.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialize the generator with the desired text
            var generator = CreateGenerator("Åspóse.Barcóde©");

            // 2️⃣ Adjust the X‑Dimension (module size)
            SetXDimension(generator, 2);

            // 3️⃣ Define how many columns the barcode should have
            SetPdf417Columns(generator, 3);

            // 4️⃣ Save the barcode as a PNG file
            SaveAsPng(generator, @"YOUR_DIRECTORY\Pdf417Basic.png");

            Console.WriteLine("PDF417 barcode generated successfully.");
        }

        // ---------------------------------------------------------
        // Step 1: Create a BarcodeGenerator for PDF417
        // ---------------------------------------------------------
        private static BarcodeGenerator CreateGenerator(string text)
        {
            // EncodeTypes.Pdf417 tells the library to use the PDF417 symbology.
            return new BarcodeGenerator(EncodeTypes.Pdf417, text);
        }

        // ---------------------------------------------------------
        // Step 2: Set the X‑Dimension (size of a single module)
        // ---------------------------------------------------------
        private static void SetXDimension(BarcodeGenerator generator, int pixels)
        {
            // XDimension controls the width of the smallest black/white bar.
            // A value of 2 pixels works well for most screen resolutions.
            generator.Parameters.Barcode.XDimension.Pixels = pixels;
        }

        // ---------------------------------------------------------
        // Step 3: Configure the number of columns in the PDF417 barcode
        // ---------------------------------------------------------
        private static void SetPdf417Columns(BarcodeGenerator generator, int columns)
        {
            // Columns affect the barcode’s aspect ratio.
            // Small numbers (e.g., 3) produce a tall barcode; larger numbers make it wider.
            generator.Parameters.Barcode.Pdf417.Columns = columns;
        }

        // ---------------------------------------------------------
        // Step 4: Export the barcode as a PNG image
        // ---------------------------------------------------------
        private static void SaveAsPng(BarcodeGenerator generator, string outputPath)
        {
            // BarCodeImageFormat.Png ensures lossless quality.
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Perché questi quattro passaggi sono importanti

1. **Inizializzare il generatore** – Il `BarcodeGenerator` collega la simbologia scelta (`EncodeTypes.Pdf417`) ai dati che vuoi codificare. Senza questo oggetto non è possibile accedere a ulteriori configurazioni.  
2. **Impostare X‑Dimension** – PDF417 è costruito da piccoli moduli rettangolari. Modificando `XDimension.Pixels` controlli la densità visiva del codice a barre, fondamentale per la leggibilità su display o stampanti a bassa risoluzione.  
3. **Configurare le colonne** – PDF417 può disporre i suoi codeword in un numero variabile di colonne. Meno colonne producono un codice a barre più alto, mentre più colonne lo appiattiscono. Regola questo valore per adattarlo allo spazio dove verrà posizionata l'immagine.  
4. **Salvare come PNG** – PNG è un formato loss‑less, che preserva i bordi netti necessari per una scansione accurata. Potresti anche scegliere JPEG o BMP, ma PNG è l'opzione predefinita più sicura.

---

## Configura le dimensioni del codice a barre (X‑Dimension)

Il passaggio **set XDimension pixels** influenza direttamente il modo in cui gli scanner interpretano il codice a barre. Se il modulo è troppo piccolo, le fotocamere di bassa qualità potrebbero non rilevare le singole barre; se è troppo grande, il codice a barre può diventare inutilmente ingombrante.

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 2; // 2‑pixel modules
```

**Best practice:** Testa l'immagine generata alle dimensioni di stampa previste. Per stampe ad alta densità (300 dpi o più), un valore di `1` o `2` funziona bene. Per la visualizzazione su schermo a 96 dpi, `2`–`3` offre una chiara resa visiva.

---

## Imposta le colonne PDF417

Il passaggio **configure PDF417 columns** ti consente di decidere la forma del codice a barre.

```csharp
generator.Parameters.Barcode.Pdf417.Columns = 3; // three columns → tall barcode
```

### Quando modificare il numero di colonne

| Colonne | Forma risultante | Caso d'uso tipico |
|---------|------------------|-------------------|
| 1–3     | Alta, stretta    | Etichette con larghezza limitata |
| 4–9     | Bilanciata       | Scansione di uso generale |
| 10+     | Larga, corta     | Segnaletica grande o grafiche web |

Se il tuo payload di dati supera la capacità predefinita, la libreria aggiunge automaticamente righe extra, ma puoi comunque influenzare il rapporto d'aspetto modificando il numero di colonne.

---

## Esporta il codice a barre in PNG

Salvare il codice a barre come immagine PNG è semplice:

```csharp
generator.Save(@"C:\Barcodes\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**Perché PNG?**  
* La compressione lossless mantiene i bordi nitidi necessari per i lettori di codici a barre.  
* PNG supporta la trasparenza, utile se in seguito sovrapponi il codice a barre su uno sfondo colorato.

Se ti serve un formato diverso, sostituisci `BarCodeImageFormat.Png` con `Jpeg`, `Bmp` o `Svg` — l'API gestisce automaticamente la conversione.

---

## Problemi comuni e risoluzione

| Problema | Probabile causa | Soluzione |
|----------|-----------------|-----------|
| Il codice a barre appare sfocato | X‑Dimension troppo piccola per la risoluzione di output | Aumentare `XDimension.Pixels` a 3 o 4. |
| Lo scanner non riesce a leggere il codice | Caratteri Unicode non supportati dal font scelto | Assicurati che il font della libreria supporti i caratteri, oppure sostituiscili con equivalenti ASCII. |
| Il file di output non è stato creato | Percorso non valido o permessi di scrittura mancanti | Usa un percorso assoluto e verifica i permessi di scrittura della cartella. |
| Troppe righe, il codice a barre diventa alto | Numero di colonne troppo basso per la lunghezza dei dati | Aumenta `Pdf417.Columns` a un numero più alto (ad esempio, 6). |

---

## Riepilogo dell'esempio completo

Di seguito trovi il **programma completo** che puoi copiare‑incollare in un nuovo progetto console. Non è necessario alcun codice aggiuntivo oltre alle istruzioni `using` e al pacchetto Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
            Console.WriteLine("PDF417 barcode generated and saved as PNG.");
        }
    }
}
```

**Output previsto:** Un file chiamato `Pdf417Basic.png` contenente un chiaro codice a barre PDF417 che codifica la stringa `Åspóse.Barcóde©`. Quando aperto, l'immagine dovrebbe mostrare una serie di barre rettangolari impilate con una densità più alta sul lato sinistro (a causa del layout a tre colonne).

---

## Conclusione

Ora sai come **generare un codice a barre PDF417** in C# usando la classe `BarcodeGenerator`. Il tutorial ha coperto l'inizializzazione del generatore, **set XDimension pixels**, **configure PDF417 columns** e **save barcode as PNG** — i passaggi essenziali per qualsiasi flusso di lavoro di codici a barre pronto per la produzione.

Da qui puoi:

* Sperimentare con diversi `EncodeTypes` (ad es., QR, Code128).  
* Aggiungere livelli di correzione errori tramite `generator.Parameters.Barcode.Pdf417.ErrorLevel`.  
* Renderizzare il codice a barre direttamente in un `MemoryStream` per API web.  

Sentiti libero di adattare il codice al tuo progetto e condividere i risultati nei commenti o su Stack Overflow usando il tag `#pdf417`. Buon coding!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che approfondiscono le tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi con spiegazioni passo‑passo per aiutarti a padroneggiare ulteriori funzionalità dell'API e a esplorare approcci alternativi nei tuoi progetti.

- [Genera codice a barre PDF417 come PNG in C# – guida passo‑passo](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-as-png-in-c-step-by-step-guide/)
- [Come generare codice a barre PDF417 in C# – guida passo‑passo](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [Come generare codice a barre PDF417 in C# con dimensioni personalizzate](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}