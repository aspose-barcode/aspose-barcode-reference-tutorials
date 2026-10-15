---
category: general
date: 2026-10-12
description: Impara a creare un codice a barre micro PDF417 e a convertire il codice
  a barre in PNG usando C#. Guida passo passo con codice completo e consigli.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro PDF417 barcode
- convert barcode to PNG
- micro PDF417 C# example
- GS1 micro PDF417 generation
- barcode image settings
language: it
lastmod: 2026-10-12
og_description: Crea un codice a barre micro PDF417 e converti il codice a barre in
  PNG con C#. Segui questa guida completa per generare sia le versioni standard che
  GS1.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Crea un codice a barre micro PDF417 e convertilo in PNG – tutorial C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn to create micro PDF417 barcode and convert barcode to PNG using
    C#. Step‑by‑step guide with full code and tips.
  headline: How to create micro PDF417 barcode and convert it to PNG in C#
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Come creare un codice a barre micro PDF417 e convertirlo in PNG in C#
url: /it/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-convert-it-to-png-in/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un codice a barre micro PDF417 e convertirlo in PNG in C#

Se hai bisogno di **creare un codice a barre micro PDF417** in un'applicazione .NET, questo tutorial ti mostra esattamente come fare. Vedrai un esempio completo e eseguibile che genera sia un codice a barre Micro PDF417 standard sia una versione conforme a GS1, quindi **convertire il codice a barre in PNG** per usi successivi come la stampa o la visualizzazione web.

Generare un codice a barre è più che chiamare un unico metodo: scegliere la giusta dimensione del modulo, il numero di colonne e il formato di codifica determina l'affidabilità della scansione. Alla fine di questa guida comprenderai perché ogni impostazione è importante e come regolarla per i tuoi progetti.

## Prerequisiti

| Requisito | Motivo |
|-------------|--------|
| .NET 6.0 SDK or later | Fornisce l'ambiente di esecuzione per l'app console C# |
| Visual Studio 2022 (or any C# IDE) | Rende più semplice la modifica e il debug |
| **Aspose.BarCode for .NET** NuGet package | Fornisce le classi `BarcodeGenerator`, `EncodeTypes` e `BarCodeImageFormat` |
| Write permission to the output folder | Necessario per le chiamate `Save` che creano file PNG |

Puoi aggiungere il pacchetto Aspose.BarCode tramite la CLI:

```bash
dotnet add package Aspose.BarCode
```

## Passo 1: Configurare un progetto console minimale

Crea un nuovo progetto console e aggiungi il riferimento alla libreria del codice a barre. Il seguente `Program.cs` contiene tutto il codice necessario; non sono richiesti file esterni.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace MicroPdf417Demo
{
    internal class Program
    {
        static void Main()
        {
            // Define the folder where PNG files will be saved
            string outputFolder = Environment.CurrentDirectory;

            // ------------------------------------------------------------
            // 1️⃣ Create a Micro PDF417 barcode generator with plain data
            // ------------------------------------------------------------
            BarcodeGenerator microGen = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,          // Micro PDF417 symbology
                "Micro data");                    // Simple alphanumeric payload

            // ------------------------------------------------------------
            // 2️⃣ Adjust the X dimension (module size) and set column count
            // ------------------------------------------------------------
            // XDimension controls the physical size of each barcode module.
            // A value of 2 pixels gives a compact yet readable barcode.
            microGen.Parameters.Barcode.XDimension.Pixels = 2;

            // For Micro PDF417 you can limit the number of columns.
            // Four columns keep the barcode small enough for labels.
            microGen.Parameters.Barcode.Pdf417.Columns = 4;

            // ------------------------------------------------------------
            // 3️⃣ Convert barcode to PNG and save the image
            // ------------------------------------------------------------
            string microPath = System.IO.Path.Combine(outputFolder, "MicroPdf417.png");
            microGen.Save(microPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Standard Micro PDF417 saved to: {microPath}");

            // ------------------------------------------------------------
            // 4️⃣ Create a GS1 Micro PDF417 barcode with AI‑encoded data
            // ------------------------------------------------------------
            // GS1 syntax requires Application Identifiers (AIs) wrapped in parentheses.
            // Example: (01) – GTIN, (21) – serial number.
            BarcodeGenerator gs1MicroGen = new BarcodeGenerator(
                EncodeTypes.Gs1MicroPdf417,
                "(01)12345678901231(21)ABC123");

            // ------------------------------------------------------------
            // 5️⃣ Set the X dimension for the GS1 barcode (same as step 2)
            // ------------------------------------------------------------
            gs1MicroGen.Parameters.Barcode.XDimension.Pixels = 2;

            // ------------------------------------------------------------
            // 6️⃣ Convert barcode to PNG and save the GS1 image
            // ------------------------------------------------------------
            string gs1Path = System.IO.Path.Combine(outputFolder, "GS1MicroPdf417.png");
            gs1MicroGen.Save(gs1Path, BarCodeImageFormat.Png);
            Console.WriteLine($"GS1 Micro PDF417 saved to: {gs1Path}");

            // End of demo
            Console.WriteLine("Barcode generation complete.");
        }
    }
}
```

### Perché ogni riga è importante

* **`EncodeTypes.MicroPdf417` vs `EncodeTypes.Gs1MicroPdf417`** – Il primo crea un codice a barre Micro PDF417 semplice, mentre il secondo segue gli standard GS1, incorporando gli Identificatori di Applicazione (AI). Scegli in base a se il tuo sistema a valle si aspetta dati GS1.  
* **`XDimension.Pixels = 2`** – Controlla la larghezza del modulo. Valori più piccoli creano un'immagine più densa ma potrebbero diventare illeggibili su scanner a bassa risoluzione. Due pixel è un valore predefinito sicuro per la maggior parte delle stampanti di etichette.  
* **`Pdf417.Columns = 4`** – Micro PDF417 consente di limitare le colonne, riducendo la larghezza complessiva. Quattro colonne mantengono il codice a barre compatto senza sacrificare la capacità di dati per payload brevi.  
* **`BarCodeImageFormat.Png`** – PNG conserva la qualità lossless, essenziale per la chiarezza del codice a barre. Per questo **convertiamo il codice a barre in PNG** anziché JPEG.

## Passo 2: Eseguire il programma e verificare l'output

1. Compila il progetto: `dotnet build`.  
2. Esegui: `dotnet run`.

Dovresti vedere messaggi della console simili a:

```
Standard Micro PDF417 saved to: C:\Path\To\Project\MicroPdf417.png
GS1 Micro PDF417 saved to: C:\Path\To\Project\GS1MicroPdf417.png
Barcode generation complete.
```

Apri i file PNG generati con qualsiasi visualizzatore di immagini. Entrambe le immagini mostrano un codice a barre nitido e ad alto contrasto pronto per la scansione.

### Risultato visivo atteso

| Tipo di codice a barre | Aspetto |
|--------------|------------|
| **Micro PDF417** | Piccolo pattern rettangolare con 4 colonne, leggibile dalla maggior parte degli scanner di codici a barre 2‑D. |
| **GS1 Micro PDF417** | Stessa dimensione ma codifica gli AI GS1; uno scanner che comprende GS1 restituirà il GTIN e il numero di serie. |

Se uno scanner non riesce a leggere l'immagine, prova ad aumentare `XDimension.Pixels` a **3** o **4**, oppure riduci il numero di colonne per il Micro PDF417 standard.

## Problemi comuni e come evitarli

| Problema | Causa | Soluzione |
|-------|-------|-----|
| Codice a barre sfocato dopo la stampa | Impostazioni della stampante a bassa DPI | Esporta PNG a 300 dpi o superiore, oppure lascia che il driver della stampante gestisca il ridimensionamento. |
| Lo scanner restituisce “dati non validi” | Formato AI GS1 mancante o malformato | Assicurati che ogni AI sia racchiuso tra parentesi e segua la specifica GS1 (es., `(01)` per GTIN‑14). |
| File immagine non creato | La cartella di output non ha permessi di scrittura | Esegui il programma con privilegi elevati o scegli una cartella come `Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments)`. |
| Codice a barre troppo grande per l'etichetta | Numero di colonne predefinito troppo alto | Riduci `Pdf417.Columns` (es., a **3**) o aumenta `XDimension` per ridurre le dimensioni complessive. |

## Estendere l'esempio

* **Formati immagine diversi** – Sostituisci `BarCodeImageFormat.Png` con `Jpeg` o `Bmp` se il tuo flusso di lavoro lo richiede. PNG rimane la scelta migliore per qualità lossless.  
* **Dati dinamici** – Passa input dell'utente o valori dal database al costruttore `BarcodeGenerator` per creare codici a barre al volo.  
* **Generazione batch** – Avvolgi la logica di creazione in un ciclo che legge righe da un file CSV e salva ogni codice a barre con un nome file unico.  

## Conclusione

Ora sai come **creare un codice a barre micro PDF417** in C# e **convertire il codice a barre in PNG** per scenari sia standard sia conformi a GS1. Il codice completo e eseguibile dimostra le impostazioni essenziali—dimensione X, numero di colonne e tipo di codifica—così puoi adattare la soluzione a qualsiasi progetto .NET che richieda codici a barre 2‑D compatti e di alta qualità.

*Passi successivi*: esplora altre simbologie supportate da Aspose.BarCode (es., QR, DataMatrix), sperimenta valori diversi di `XDimension` per stampe ad alta risoluzione, o integra i PNG generati in un'API web che fornisce codici a barre su richiesta.

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come creare un codice a barre micro pdf417 in C# e salvarlo come PNG](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-and-save-it-as-png/)
- [Crea PNG del codice a barre in C# – guida completa a GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [Genera codice a barre Micro PDF417 in C# – Guida completa](/barcode/english/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}