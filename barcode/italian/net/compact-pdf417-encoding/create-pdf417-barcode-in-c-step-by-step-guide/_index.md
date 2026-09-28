---
category: general
date: 2026-08-03
description: Crea rapidamente un codice a barre PDF417 in C#. Scopri come generare
  un codice a barre PDF417 e come salvare l'immagine del codice a barre come PNG con
  Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417 barcode
- how to save barcode image
language: it
lastmod: 2026-08-03
og_description: Crea un codice a barre PDF417 in C# con Aspose.Barcode. Segui questa
  guida per generare il codice a barre PDF417 e per salvare l'immagine del codice
  a barre in modo efficiente.
og_image_alt: Screenshot of a generated compact PDF417 barcode saved as PNG
og_title: Crea codice a barre PDF417 in C# – tutorial completo di programmazione
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  headline: Create PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  name: Create PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: Why this matters
    text: '* **EncodeTypes.Pdf417** tells the library to use the PDF417 standard,
      which supports large data payloads and error correction. * Providing Unicode
      characters proves the generator handles non‑ASCII input without extra configuration.'
  - name: Practical tip
    text: If you need a taller barcode for limited horizontal space, increase `Columns`.
      Setting `Truncate` to `true` reduces the overall height by removing quiet zones,
      which is ideal for mobile screens.
  - name: Expected result
    text: Running the program creates `CompactPdf417.png` in the project folder. Opening
      the file shows a compact PDF417 barcode that encodes the string *Åspóse.Barcóde©*.
      The image can be embedded in HTML, PDF reports, or printed on labels.
  - name: Verifying the output
    text: 'After the program finishes, you can verify the file exists with a quick
      command:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: Crea codice a barre PDF417 in C# – guida passo passo
url: /it/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea un codice a barre PDF417 in C# – guida passo‑passo

Se hai bisogno di **creare un codice a barre PDF417** in un'applicazione .NET, questa guida ti mostra esattamente come generare il codice a barre PDF417 e come salvare l’immagine del codice a barre. Otterrai un file PNG che potrà essere usato in report, ticket o app di scansione mobile.

Il tutorial copre tutto, dall’impostazione del progetto al file PNG finale. Non è necessaria alcuna documentazione esterna; basta seguire i passaggi e eseguire il codice.

## Cosa ti servirà

Prima di iniziare, assicurati di avere:

* .NET 6.0 SDK o successivo (il codice funziona anche con .NET Framework 4.7+)
* Visual Studio 2022 o qualsiasi IDE che supporti C#
* Accesso a Internet per installare il pacchetto NuGet **Aspose.Barcode for .NET**

Questi prerequisiti garantiscono che il codice si compili senza configurazioni aggiuntive.

## Crea un codice a barre PDF417 – configurazione del progetto

1. Apri un prompt dei comandi e crea un nuovo progetto console:

   ```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

2. Aggiungi la libreria Aspose.Barcode:

   ```bash
   dotnet add package Aspose.Barcode
   ```

3. Apri il file `Program.cs` generato. Le istruzioni `using` in cima ti danno accesso alle classi del barcode:

   ```csharp
   using System;
   using Aspose.Barcode.Generation;
   using Aspose.Barcode;
   ```

Il progetto è ora pronto per **creare un codice a barre PDF417**.

## Come generare un codice a barre PDF417 con Aspose.Barcode

Il cuore della creazione del codice a barre risiede nella classe `BarcodeGenerator`. Specifici la simbologia (`EncodeTypes.Pdf417`) e i dati che vuoi codificare.

```csharp
// Step 1: Initialise the generator with PDF417 symbology and sample text.
// The text includes Unicode characters to demonstrate full‑range support.
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

### Perché è importante

* **EncodeTypes.Pdf417** indica alla libreria di utilizzare lo standard PDF417, che supporta grandi quantità di dati e correzione d'errore.
* L’inserimento di caratteri Unicode dimostra che il generatore gestisce input non‑ASCII senza configurazioni aggiuntive.

## Come configurare l’aspetto del codice a barre

Puoi controllare la dimensione di ogni modulo, il numero di colonne e se il codice a barre utilizza la modalità compatta (troncata). Queste impostazioni influenzano sia la leggibilità sia la dimensione del file.

```csharp
// Step 2: Set the module (X) dimension – each barcode element will be 2 pixels wide.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Configure PDF417‑specific options.
generator.Parameters.Barcode.Pdf417.Columns = 3;      // Number of columns (affects height)
generator.Parameters.Barcode.Pdf417.Truncate = true; // Enable compact mode
```

### Consiglio pratico

Se ti serve un codice a barre più alto per spazio orizzontale limitato, aumenta `Columns`. Impostare `Truncate` a `true` riduce l’altezza complessiva eliminando le zone silenziose, ideale per schermi mobili.

## Come salvare l’immagine del codice a barre come PNG

Dopo aver configurato il generatore, chiama `Save` passando un percorso file e il formato immagine desiderato. Il metodo scrive l’immagine direttamente su disco.

```csharp
// Step 4: Save the generated barcode as a PNG image.
string outputPath = @"./CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

### Risultato atteso

L’esecuzione del programma crea `CompactPdf417.png` nella cartella del progetto. Aprendo il file vedrai un codice a barre PDF417 compatto che codifica la stringa *Åspóse.Barcóde©*. L’immagine può essere inserita in HTML, report PDF o stampata su etichette.

## Codice sorgente completo

Di seguito trovi il programma completo e pronto all’esecuzione. Copialo in `Program.cs` ed esegui `dotnet run`.

```csharp
using System;
using Aspose.Barcode.Generation;
using Aspose.Barcode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with PDF417 symbology and sample text.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Åspóse.Barcóde©");

            // Set the module width to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Configure PDF417‑specific options.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Define the output file path.
            string outputPath = @"./CompactPdf417.png";

            // Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Verifica dell’output

Al termine del programma, puoi verificare che il file esista con un semplice comando:

```bash
dotnet run && ls -l CompactPdf417.png
```

Se il file appare, il processo di **creazione del codice a barre PDF417** è riuscito.

## Varianti comuni e casi limite

| Situazione | Regolazione |
|------------|-------------|
| **Stringa di dati più lunga** | Aumenta `Columns` o imposta `Rows` per ospitare più codeword. |
| **Formato immagine diverso** | Sostituisci `BarCodeImageFormat.Png` con `Jpeg`, `Bmp` o `Gif`. |
| **Risoluzione più alta** | Imposta `generator.Parameters.ImageResolution` prima di `Save`. |
| **Colore di sfondo** | Usa `generator.Parameters.Barcode.ImageBackgroundColor = Color.White;` |
| **Gestione delle eccezioni** | Avvolgi `generator.Save` in un blocco `try/catch` per catturare errori I/O. |

Queste varianti ti consentono di personalizzare il codice a barre per dispositivi specifici o requisiti di branding.

## Conclusione

Ora sai come **creare un codice a barre PDF417** in C# usando Aspose.Barcode, configurarne l’aspetto e **salvare l’immagine del codice a barre** come file PNG. L’esempio completo dimostra ogni passaggio necessario, dall’impostazione del progetto alla verifica, così da poter integrare la generazione di codici a barre in qualsiasi soluzione .NET.

Successivamente, potresti approfondire argomenti correlati come **come generare codici QR**, **incorporare codici a barre in documenti PDF** o **personalizzare i colori del codice a barre**. Ognuno di questi si basa sulla stessa API del generatore, permettendoti di estendere le capacità di scansione della tua applicazione con il minimo sforzo. Buon coding!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell’API e a esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come creare un codice a barre – PDF417 compatto con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Come generare codici a barre DataMatrix (ECC 200) con Aspose.BarCode per .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Come generare un codice a barre Aztec con rapporto d’aspetto personalizzato usando Aspose.BarCode per .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}