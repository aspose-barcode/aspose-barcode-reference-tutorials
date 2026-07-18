---
category: general
date: 2026-07-18
description: Crea un codice a barre PDF417 in C# utilizzando il generatore di codici
  a barre PDF417 per C#. Segui un tutorial passo‑passo per costruire il testo codificato
  esteso, impostare l’aspetto e salvare l’immagine.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- c# pdf417 barcode generator
language: it
lastmod: 2026-07-18
og_description: Crea un codice a barre PDF417 in C# istantaneamente. Questa guida
  mostra come utilizzare il generatore di codici a barre PDF417 in C#, configurare
  la modalità estesa e esportare un PNG.
og_image_alt: Generated PDF417 barcode image created with C# PDF417 barcode generator
og_title: Crea codice a barre PDF417 in C# – Guida completa al generatore
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create PDF417 barcode in C# using the C# PDF417 barcode generator.
    Follow a step‑by‑step tutorial to build extended codetext, set appearance, and
    save the image.
  headline: Create PDF417 Barcode in C# – Barcode Generator Guide
  type: TechArticle
- description: Create PDF417 barcode in C# using the C# PDF417 barcode generator.
    Follow a step‑by‑step tutorial to build extended codetext, set appearance, and
    save the image.
  name: Create PDF417 Barcode in C# – Barcode Generator Guide
  steps:
  - name: 1. Install the barcode library
    text: 'Open your terminal in the project folder and run:'
  - name: 2. Build the extended codetext
    text: 'PDF417 supports **extended encoding**, allowing you to mix different character
      sets in a single barcode. Below we create three segments:'
  - name: 3. Initialise the **C# PDF417 barcode generator**
    text: Now that we have a valid codetext string, we hand it to the generator. The
      `using` statement ensures the underlying resources are released automatically.
  - name: 4. Configure appearance and encoding mode
    text: 'The default settings give you a tiny barcode that might be hard to read.
      Let’s tweak a few parameters:'
  - name: 5. Save the barcode image
    text: Finally, write the image to disk. The library supports PNG, JPEG, BMP, and
      several vector formats—PNG is a safe default because it preserves crisp edges.
  - name: Handling Unicode and special characters
    text: When you feed Unicode symbols directly into a plain‑text barcode, the generator
      may fall back to a fallback encoding, resulting in garbled output. By using
      `AddECICodetext` you explicitly tell the encoder which character set to apply,
      eliminating guesswork. If you ever need to support **Arabic**, **
  - name: Adjusting error correction level
    text: 'PDF417 offers four error‑correction levels (0‑8). Higher levels increase
      resilience but also enlarge the barcode. Adjust it via:'
  - name: Scaling for print vs. screen
    text: 'For on‑screen display you might keep the default 96 dpi. For high‑resolution
      printing (300 dpi or more), set:'
  - name: Common pitfalls
    text: '- **Missing `using` directive** – Forgetting `using Aspose.BarCode.Encoding;`
      will cause `ECIEncodings` to be undefined. - **Directory not found** – The `Save`
      method won’t create intermediate folders; create them beforehand or use `Path.Combine`
      with `Environment.CurrentDirectory`. - **Wrong encode'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Crea codice a barre PDF417 in C# – Guida al generatore di codici a barre
url: /it/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-barcode-generator-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea codice a barre PDF417 in C# – Guida al generatore di codici a barre

Ti è mai capitato di **creare un codice a barre PDF417** in un'applicazione C# ma non sapevi da dove cominciare? Non sei solo: molti sviluppatori incontrano lo stesso ostacolo quando si avvicinano per la prima volta ai codici a barre bidimensionali. La buona notizia? Con il **generatore di codici a barre PDF417 C#** integrato puoi generare un codice a barre completo in poche righe di codice.

In questo tutorial percorreremo l'intero processo: costruire un codetext esteso che mescola diversi set di caratteri, configurare il generatore per lo stile visivo corretto e infine salvare il codice a barre come file PNG. Alla fine avrai a disposizione uno snippet pronto all'uso da inserire in qualsiasi progetto .NET, oltre a consigli per gestire casi particolari come caratteri Unicode o larghezze di modulo personalizzate.

---

## Cosa ti servirà

Prima di iniziare, assicurati di avere quanto segue sulla tua macchina:

- **.NET 6.0** o versioni successive (l'esempio funziona anche con .NET Framework 4.6+)
- **Aspose.BarCode for .NET** (o qualsiasi libreria compatibile che esponga `BarcodeGenerator`, `EncodeTypes.Pdf417`, ecc.)
- Un editor di codice—Visual Studio, Rider o anche VS Code vanno benissimo
- Una cartella in cui poter scrivere, perché il generatore salverà il PNG lì

Questo è tutto—nessun pacchetto NuGet aggiuntivo oltre alla libreria per i codici a barre stessa.

---

## Guida passo‑passo per **creare un codice a barre PDF417**

### 1. Installa la libreria per i codici a barre

Apri il terminale nella cartella del progetto ed esegui:

```bash
dotnet add package Aspose.BarCode
```

Il pacchetto aggiunge lo spazio dei nomi `Aspose.BarCode`, che contiene la classe `BarcodeGenerator` che utilizzeremo.

### 2. Costruisci il codetext esteso

PDF417 supporta la **codifica estesa**, consentendo di mescolare diversi set di caratteri in un unico codice a barre. Di seguito creiamo tre segmenti:

- Un segmento Windows‑1251 (cirillico)
- Un segmento UTF‑8 contenente caratteri Unicode (i kanji giapponesi per “cane” e “destra”)
- Un segmento di testo semplice

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;

// Step 1: Build the extended codetext for the PDF417 barcode
Pdf417ExtCodetextBuilder builder = new Pdf417ExtCodetextBuilder();

// Add a Win1251‑encoded segment
builder.AddECICodetext(ECIEncodings.Win1251, "Will");

// Add a UTF‑8 segment with Unicode characters
builder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");

// Add a plain‑text segment
builder.AddPlainCodetext("Plain text");

// Retrieve the combined codetext string
string extendedCodetext = builder.GetExtendedCodetext();
```

**Perché è importante:**  
Se utilizzi solo testo semplice, sei limitato al sottoinsieme ASCII predefinito. Dichiarando esplicitamente i segmenti ECI (Extended Channel Interpretation) garantisci che gli scanner interpretino correttamente ogni parte, indipendentemente dalla lingua o dai simboli coinvolti.

### 3. Inizializza il **generatore di codici a barre PDF417 C#**

Ora che abbiamo una stringa di codetext valida, la passiamo al generatore. L'istruzione `using` assicura che le risorse sottostanti vengano rilasciate automaticamente.

```csharp
// Step 2: Create a PDF417 barcode generator using the extended codetext
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, extendedCodetext))
{
    // Configuration goes here (see next step)
}
```

### 4. Configura l'aspetto e la modalità di codifica

Le impostazioni predefinite producono un codice a barre piccolo che potrebbe risultare difficile da leggere. Modifichiamo alcuni parametri:

- **X‑Dimension** – controlla la larghezza di ogni modulo (dimensione in pixel)
- **EncodeMode** – indica al motore di trattare l'input come modalità estesa
- **TwoDDisplayText** – testo opzionale leggibile dall'uomo mostrato sotto il codice a barre

```csharp
    // Step 3: Configure barcode appearance and encoding mode
    generator.Parameters.Barcode.XDimension.Pixels = 15; // Wider modules for better scannability
    generator.Parameters.Barcode.Pdf417.EncodeMode = Pdf417EncodeMode.Extended; // Activate extended encoding
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended mode"; // Display text under the symbol
```

**Consiglio professionale:** Se stampi il codice a barre su una stampante di etichette, aumenta `XDimension` a 20 px o più; la maggior parte degli scanner apprezza un po' di spazio extra.

### 5. Salva l'immagine del codice a barre

Infine, scrivi l'immagine su disco. La libreria supporta PNG, JPEG, BMP e diversi formati vettoriali—PNG è una scelta sicura perché preserva bordi nitidi.

```csharp
    // Step 4: Save the generated barcode image
    generator.Save("YOUR_DIRECTORY/Pdf417Extended.png", BarCodeImageFormat.Png);
}
```

Assicurati che `YOUR_DIRECTORY` esista e sia scrivibile. Dopo aver eseguito il programma dovresti vedere un file simile allo screenshot qui sotto.

![Codice a barre PDF417 generato con il generatore di codici a barre PDF417 C#](https://example.com/images/pdf417-extended.png "Codice a barre PDF417 generato con il generatore di codici a barre PDF417 C#")

---

## Utilizzare il **generatore di codici a barre PDF417 C#** – approfondimento

### Gestione di Unicode e caratteri speciali

Quando inserisci simboli Unicode direttamente in un codice a barre di testo semplice, il generatore potrebbe ricorrere a una codifica di fallback, producendo output illeggibile. Usando `AddECICodetext` indichi esplicitamente all'encoder quale set di caratteri applicare, eliminando le ipotesi. Se devi supportare **Arabic**, **Hebrew** o **emoji**, scegli semplicemente il valore `ECIEncodings` appropriato.

### Regolazione del livello di correzione degli errori

PDF417 offre quattro livelli di correzione degli errori (0‑8). Livelli più alti aumentano la resilienza ma ingrandiscono anche il codice a barre. Regolalo così:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // Balanced level
```

### Scalatura per stampa vs. schermo

Per la visualizzazione su schermo potresti mantenere i 96 dpi predefiniti. Per la stampa ad alta risoluzione (300 dpi o più), imposta:

```csharp
generator.Parameters.ImageResolution = 300;
```

In questo modo il PNG salvato conserva abbastanza dettagli per le stampanti laser.

### Errori comuni

- **Direttiva `using` mancante** – Dimenticare `using Aspose.BarCode.Encoding;` farà sì che `ECIEncodings` non sia definito.
- **Directory non trovata** – Il metodo `Save` non crea cartelle intermedie; creale in anticipo o usa `Path.Combine` con `Environment.CurrentDirectory`.
- **Modalità di codifica errata** – Se lasci `EncodeMode` su `Pdf417EncodeMode.Auto`, la libreria potrebbe trattare il tuo codetext esteso come testo semplice, rimuovendo i marcatori ECI.

---

## Esempio completo, pronto all'uso

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;

class Program
{
    static void Main()
    {
        // 1️⃣ Build extended codetext
        Pdf417ExtCodetextBuilder builder = new Pdf417ExtCodetextBuilder();
        builder.AddECICodetext(ECIEncodings.Win1251, "Will");
        builder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
        builder.AddPlainCodetext("Plain text");
        string extendedCodetext = builder.GetExtendedCodetext();

        // 2️⃣ Initialise generator with the extended codetext
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, extendedCodetext))
        {
            // 3️⃣ Configure appearance
            generator.Parameters.Barcode.XDimension.Pixels = 15;
            generator.Parameters.Barcode.Pdf417.EncodeMode = Pdf417EncodeMode.Extended;
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;
            generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended mode";

            // 4️⃣ Save to PNG (ensure the folder exists)
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "Pdf417Extended.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }

        Console.WriteLine("PDF417 barcode generated successfully!");
    }
}
```

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API ed esplorare approcci alternativi nei tuoi progetti.

- [Come creare un codice a barre – PDF417 compatto con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Come creare codetext esteso per dotcode con Aspose.BarCode per .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Crea immagine di codice a barre c# – Configura righe e colonne di Codablock F](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}