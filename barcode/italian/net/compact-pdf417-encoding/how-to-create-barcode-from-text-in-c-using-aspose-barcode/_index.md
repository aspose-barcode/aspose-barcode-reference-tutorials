---
category: general
date: 2026-10-28
description: Crea un codice a barre da testo in C# con Aspose.BarCode. Impara a generare
  un’immagine di codice a barre PDF417, impostare le colonne, regolare la dimensione
  X e abilitare la modalità compatta.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate barcode c#
- generate pdf417 barcode
- pdf417 barcode image
language: it
lastmod: 2026-10-28
og_description: Crea un codice a barre da testo in C# usando Aspose.BarCode. Questo
  tutorial mostra come generare un'immagine di codice a barre PDF417, personalizzare
  dimensioni, colonne e modalità compatta.
og_image_alt: Screenshot showing a compact PDF417 barcode created from text using
  C#
og_title: Crea un codice a barre da testo in C# – guida passo passo
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode from text in C# with Aspose.BarCode. Learn to generate
    PDF417 barcode image, set columns, adjust X‑dimension, and enable compact mode.
  headline: How to create barcode from text in C# using Aspose.BarCode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- image generation
title: Come creare un codice a barre da testo in C# con Aspose.BarCode
url: /it/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un barcode da testo in C# usando Aspose.BarCode

Se hai bisogno di **creare un barcode da testo** in un'applicazione .NET, questa guida fornisce una soluzione pronta all'uso. Vedrai come **generare immagini PDF417 barcode**, controllare la larghezza del modulo, il numero di colonne e abilitare la modalità compatta senza uscire dal tuo IDE.

Il tutorial copre tutto il necessario per **generare codice barcode C#**, dall'installazione della libreria al salvataggio del file PNG finale. Alla fine potrai incorporare un barcode PDF417 ad alta densità in report, biglietti o etichette di inventario.

## Prerequisiti

* .NET 6.0 SDK o versioni successive installate  
* Visual Studio 2022 (o qualsiasi editor che supporti .NET)  
* Accesso a Internet per scaricare il pacchetto NuGet Aspose.BarCode per .NET  

Questi elementi sono sufficienti per compilare ed eseguire l'esempio su Windows, Linux o macOS.

## Passo 1: Installa il pacchetto NuGet Aspose.BarCode

La libreria che alimenta la generazione del barcode è **Aspose.BarCode for .NET**. Installala con la CLI .NET:

```bash
dotnet add package Aspose.BarCode
```

Il pacchetto aggiunge lo spazio dei nomi `Aspose.BarCode`, che contiene la classe `BarcodeGenerator` utilizzata in tutto questo tutorial.

## Passo 2: Crea un progetto console e aggiungi il codice

Crea un nuovo progetto console e sostituisci il file `Program.cs` generato con il seguente codice. Il programma dimostra come **creare un barcode da testo** e salvarlo come **immagine PDF417 barcode**.

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
            // Step 2.1: Define the text to encode.
            // Unicode characters such as Å, ó, and © are supported out of the box.
            string data = "Åspóse.Barcóde©";

            // Step 2.2: Initialize the PDF417 generator with the desired text.
            // EncodeTypes.Pdf417 tells the generator which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // Step 2.3: Set the X‑dimension (module width) to 2 pixels for a denser barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 2.4: Define the number of columns in the PDF417 symbol.
            // Fewer columns produce a taller barcode; three columns keep it compact.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Step 2.5: Enable compact mode by truncating the right‑hand column.
            // Truncate reduces the overall width while preserving data integrity.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Step 2.6: Choose the output folder and file name.
            string outputPath = "CompactPdf417.png";

            // Step 2.7: Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

### Perché ogni riga è importante

* **`EncodeTypes.Pdf417`** seleziona la simbologia PDF417, ideale per codificare grandi quantità di dati in un formato bidimensionale.  
* **`XDimension.Pixels = 2`** riduce la larghezza del modulo, rendendo il barcode più denso e più adatto a spazi limitati.  
* **`Pdf417.Columns = 3`** controlla il numero di colonne di dati verticali; un valore più basso produce un barcode più alto ma più stretto.  
* **`Pdf417.Truncate = true`** attiva la modalità compatta, eliminando le colonne inutilizzate sul lato destro. Questa è l'impostazione chiave che trasforma un PDF417 normale in un **immagine PDF417 barcode compatta**.  

## Passo 3: Compila ed esegui il progetto

Esegui i seguenti comandi nella directory del progetto:

```bash
dotnet build
dotnet run
```

Quando il programma termina, vedrai un messaggio nella console che conferma la posizione del file. Apri `CompactPdf417.png` con qualsiasi visualizzatore di immagini per verificare il risultato.

**Output previsto** – un PNG ad alto contrasto che mostra un PDF417 barcode compatto che codifica la stringa `Åspóse.Barcóde©`. Scansionando l'immagine con un lettore di barcode standard si ottiene il testo originale, confermando che **generate pdf417 barcode** è riuscito.

## Passo 4: Personalizzare il barcode per diversi scenari

Mentre l'esempio utilizza un numero di colonne fisso e X‑dimension, puoi adattare il generatore ad altri requisiti:

| Scenario | Regolazione |
|----------|------------|
| Carico di dati più grande | Aumentare `Pdf417.Columns` o impostare `Pdf417.Rows` manualmente |
| Affidabilità di scansione più alta | Aumentare `XDimension.Pixels` a 3 o 4 |
| Formato immagine diverso | Sostituire `BarCodeImageFormat.Png` con `Jpeg` o `Bmp` |
| Sfondo trasparente | Impostare `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent` |

Queste opzioni ti consentono di **generare barcode C#** soluzioni adatte a app mobili, report desktop o servizi web.

## Passo 5: Gestire casi limite e migliori pratiche

* **Supporto Unicode** – Il generatore codifica automaticamente i caratteri Unicode, ma assicurati che la tua stringa di origine sia codificata in UTF‑8 se la leggi da un file.  
* **Testo lungo** – PDF417 può codificare fino a 1.850 caratteri alfanumerici. Se superi questo limite, la libreria genera un'eccezione; suddividi i dati in più barcode o passa a una simbologia a capacità maggiore.  
* **Gestione degli errori** – Avvolgi il codice di generazione in un blocco `try/catch` per catturare `BarCodeException` e fornire un messaggio di errore amichevole.  
* **Prestazioni** – Generare molti barcode in un ciclo beneficia del riutilizzo di una singola istanza `BarcodeGenerator` e dell'aggiornamento solo di `CodeText` tra le iterazioni.

```csharp
try
{
    generator.CodeText = nextText;
    generator.Save($"barcode_{i}.png", BarCodeImageFormat.Png);
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

## Elenco completo del codice sorgente

Di seguito trovi il programma completo e autonomo che puoi copiare in `Program.cs`. Non sono necessari file aggiuntivi.

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
            string data = "Åspóse.Barcóde©";

            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

Eseguendo questo programma si crea l'**immagine pdf417 barcode** mostrata nell'illustrazione seguente.

![Barcode PDF417 compatto creato da testo usando C#](/images/compact-pdf417.png){.img-fluid alt="esempio di creazione di barcode da testo che mostra un'immagine PDF417 barcode compatta"}

*Descrizione immagine: Il file PNG mostra un barcode PDF417 compatto che codifica la stringa “Åspóse.Barcóde©”.*  

## Conclusione

Ora sai come **creare un barcode da testo** in C# e produrre un **immagine PDF417 barcode** con dimensioni personalizzate e modalità compatta. L'esempio dimostra i passaggi essenziali per **generare barcode C#**, gestire dati Unicode e regolare i parametri visivi per diversi scenari di distribuzione.

Successivamente, esplora argomenti correlati come **generate QR code in C#**, **add barcode to PDF documents**, o **embed barcodes in ASP.NET Core APIs**. Ognuno di questi si basa sugli stessi fondamenti di `BarcodeGenerator` trattati qui.

Buon coding e divertiti a integrare i barcode nelle tue soluzioni .NET!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Genera PDF417 Barcode in C# – Crea PDF417 Barcode C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/)
- [Come generare PDF417 barcode con Aspose.BarCode in C#](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/)
- [Come creare immagine PDF417 barcode in C# – guida completa](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}