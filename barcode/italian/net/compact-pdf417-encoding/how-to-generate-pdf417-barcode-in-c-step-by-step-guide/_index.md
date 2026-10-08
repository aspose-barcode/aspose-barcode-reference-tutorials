---
category: general
date: 2026-09-10
description: Genera rapidamente un codice a barre PDF417 in C#. Scopri come generare
  PDF417 e come modificare le dimensioni del codice a barre con Aspose.BarCode in
  poche righe.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- how to generate PDF417
- how to change barcode size
language: it
lastmod: 2026-09-10
og_description: Genera codice a barre PDF417 in C# istantaneamente. Questo tutorial
  mostra come generare PDF417 e come modificare le dimensioni del codice a barre usando
  Aspose.BarCode.
og_image_alt: generate PDF417 barcode example showing 4 columns and 9 rows
og_title: Genera codice a barre PDF417 in C# – guida completa di programmazione
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  headline: How to generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  name: How to generate PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Create a new console project:'
    text: 'Create a new console project:'
  - name: Add the Aspose.BarCode reference (see prerequisites).
    text: Add the Aspose.BarCode reference (see prerequisites).
  - name: Open `Program.cs` and replace its content with the full example below.
    text: Open `Program.cs` and replace its content with the full example below.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Come generare il codice a barre PDF417 in C# – guida passo‑passo
url: /it/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come generare un codice a barre PDF417 in C# – guida passo‑passo

Se hai bisogno di **generare un codice a barre PDF417** in un'applicazione .NET, questa guida ti mostra esattamente come farlo. Vedrai un esempio conciso, pronto‑all'uso, che crea un codice a barre PDF417, ti consente di controllarne le dimensioni e salva il risultato come immagine PNG.

Generare un codice a barre PDF417 è una necessità comune per sistemi di inventario, carte d'imbarco e tracciamento dei documenti. In questo tutorial copriamo anche **come modificare le dimensioni del codice a barre** in modo che il codice si adatti a diverse esigenze di stampa o visualizzazione su schermo.

## Prerequisiti

* .NET 6.0 o successivo (il codice funziona anche con .NET Framework 4.6+)
* Visual Studio 2022 o qualsiasi IDE C#
* Il pacchetto NuGet **Aspose.BarCode for .NET**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Conoscenza di base delle applicazioni console C#

## Configurazione del progetto

1. Crea un nuovo progetto console:

   ```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

2. Aggiungi il riferimento Aspose.BarCode (vedi i prerequisiti).  

3. Apri `Program.cs` e sostituisci il suo contenuto con l'esempio completo qui sotto.

## Passo 1: Generare il codice a barre PDF417

Il primo passo è creare un'istanza di `BarcodeGenerator` configurata per la simbologia **PDF417**. Questo oggetto è il punto di ingresso per tutte le operazioni sui codici a barre.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");
```

*Perché è importante* – Il valore enum `EncodeTypes.Pdf417` indica ad Aspose.BarCode di utilizzare lo standard PDF417, mentre il secondo argomento fornisce i dati da codificare. Il generatore ora contiene un oggetto codice a barre completo che puoi personalizzare prima di salvarlo.

## Passo 2: Come modificare le dimensioni del codice a barre (dimensione del modulo)

I codici a barre PDF417 sono composti da piccoli moduli quadrati. Regolare la dimensione del modulo cambia le dimensioni complessive dell'immagine senza alterare i dati codificati.

```csharp
        // Step 2: Define the module size (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module
```

*Perché è importante* – Un `XDimension` più grande produce un codice a barre più grande adatto alla stampa ad alta risoluzione; un valore più piccolo è migliore per la visualizzazione su schermo. Il valore predefinito è solitamente 1 px, che può apparire ristretto sui monitor moderni.

## Passo 3: Configurare il layout – colonne e righe

PDF417 consente di definire il numero di colonne e righe, il che influisce sia sulla forma del codice a barre sia sulla sua capacità di correzione degli errori.

```csharp
        // Step 3: Configure the layout – set the number of columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

*Perché è importante* – Più colonne rendono il codice a barre più largo, mentre più righe lo rendono più alto. Regola questi valori per adattarli allo spazio disponibile nella tua interfaccia o sull'etichetta stampata.

## Passo 4: Salvare l'immagine del codice a barre

Infine, scrivi il codice a barre su un file. Qui usiamo PNG perché conserva bordi nitidi e supporta la trasparenza.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        string outputPath = "LayoutPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode saved to {outputPath}");
    }
}
```

Eseguendo il programma viene creato `LayoutPdf417.png` nella cartella di output del progetto. L'immagine avrà questo aspetto:

![generate PDF417 barcode example showing 4 columns and 9 rows](https://example.com/images/pdf417-sample.png){#barcode-image alt="genera esempio di codice a barre PDF417 che mostra 4 colonne e 9 righe"}

*Suggerimento*: Se hai bisogno di un formato immagine diverso (JPEG, BMP, TIFF), sostituisci `BarCodeImageFormat.Png` con il valore enum appropriato.

## Come generare PDF417 – fonti dati alternative

Il codice sopra utilizza una stringa codificata direttamente `"Layout test"`. In scenari reali spesso si prelevano dati da un database, un file o un input dell'utente.

```csharp
string dataFromDb = GetOrderNumber(); // your own method
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, dataFromDb);
```

Il resto dei passaggi (dimensione, layout, salvataggio) rimane invariato. Questo dimostra **come generare PDF417** da fonti dinamiche senza complessità aggiuntive.

## Problemi comuni e come evitarli

| Problema | Perché accade | Soluzione |
|----------|----------------|-----------|
| Il codice a barre appare sfocato | `XDimension` impostato troppo basso per la risoluzione di output | Aumentare `XDimension.Pixels` o salvare in un formato vettoriale come SVG (`BarCodeImageFormat.Svg`) |
| Il testo non si adatta al layout scelto | Troppi caratteri per le righe/colonne selezionate | Ridurre il numero di righe/colonne o suddividere i dati in più codici a barre |
| Il file immagine non viene creato | La cartella di output non esiste o mancano i permessi di scrittura | Assicurarsi che la directory esista (`Directory.CreateDirectory`) e che l'app venga eseguita con i permessi corretti |

## Verifica del codice a barre

Dopo aver generato l'immagine, puoi verificarla usando qualsiasi app scanner PDF417 (i telefoni cellulari hanno scanner gratuiti) o il lettore integrato di Aspose.BarCode:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// Load the image we just saved
BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
if (reader.Read())
{
    Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
}
else
{
    Console.WriteLine("Failed to decode the barcode.");
}
```

Se l'output corrisponde al testo originale, il processo di **generazione del codice a barre PDF417** è riuscito.

## Esempio completo e eseguibile

Di seguito trovi il programma completo che puoi copiare‑incollare in `Program.cs`. Include tutte le direttive using, la gestione degli errori e i commenti.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Prepare output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);
        string outputPath = Path.Combine(outputDir, "LayoutPdf417.png");

        // 1️⃣ Create the generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");

        // 2️⃣ Change barcode size (module size)
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module

        // 3️⃣ Set layout – columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4;
        generator.Parameters.Barcode.Pdf417.Rows    = 9;

        // 4️⃣ Save as PNG
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"PDF417 barcode saved to {outputPath}");

        // 5️⃣ Verify the barcode by reading it back
        BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
        if (reader.Read())
        {
            Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
        }
        else
        {
            Console.WriteLine("Failed to decode the barcode.");
        }
    }
}
```

Eseguendo questo programma stampa:

```
PDF417 barcode saved to C:\...\output\LayoutPdf417.png
Decoded text: Layout test
```

Ora hai una **soluzione completa e autonoma** per generare codici a barre PDF417 e controllarne le dimensioni.

## Conclusione

In questo tutorial hai imparato come **generare un codice a barre PDF417** in C# usando Aspose.BarCode, come **modificare le dimensioni del codice a barre** regolando la X‑dimension, e come configurare colonne e righe per il controllo del layout. Hai anche visto come verificare il risultato programmaticamente e come adattare il codice a dati dinamici.

Successivamente, potresti esplorare:

* **Come generare PDF417** con la regolazione del livello di correzione degli errori (`generator.Parameters.Barcode.Pdf417.ErrorLevel`)
* Esportare in **formati vettoriali** (SVG, EPS) per una scalabilità infinita
* Incorporare il codice a barre in un documento PDF con **Aspose.PDF**

Sperimenta con diverse dimensioni del modulo e opzioni di layout per adattarle alle tue specifiche esigenze di UI o stampa. Buon coding!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come generare il codice a barre PDF417 con Aspose – Guida completa](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [regola dimensione codice a barre – Guida C# per generare codici a barre PDF417](/barcode/english/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Come salvare il codice a barre in C# – Generare codici a barre PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}