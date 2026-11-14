---
category: general
date: 2026-11-14
description: Crea un codice a barre micro PDF417 in C# con Aspose.BarCode – guida
  passo‑passo che copre la configurazione del generatore, la dimensione X, le colonne
  e l’esportazione PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- micro pdf417 barcode generator
- set XDimension pixels
- define barcode columns
- save barcode as PNG
- Aspose.BarCode C# example
language: it
lastmod: 2026-11-14
og_description: Crea un codice a barre micro PDF417 in C# usando Aspose.BarCode. Impara
  a configurare il generatore, impostare XDimension, scegliere le colonne e esportare
  come PNG.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Crea codice a barre micro PDF417 in C# – guida completa di programmazione
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  headline: How to create micro PDF417 barcode in C#
  type: TechArticle
- description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  name: How to create micro PDF417 barcode in C#
  steps:
  - name: Open the PNG in an image viewer.
    text: Open the PNG in an image viewer.
  - name: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
    text: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
  - name: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
    text: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
- image generation
title: Come creare un codice a barre micro PDF417 in C#
url: /it/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare micro PDF417 barcode in C#  

Se hai bisogno di **creare micro PDF417 barcode** rapidamente, questa guida ti mostra una soluzione completa, pronta‑all‑uso. Vedrai come istanziare il generatore di barcode, configurare la X‑dimension, scegliere il numero di colonne e infine salvare il risultato come immagine PNG—tutto usando la libreria Aspose.BarCode per .NET.

Generare un micro PDF417 barcode non richiede una pipeline di build complessa. Alla fine di questo tutorial avrai un unico file C# che produce un'immagine di barcode ad alta qualità che puoi incorporare in report, etichette o app mobili.

## Prerequisiti  

* .NET 6.0 SDK o successivo (il codice funziona anche con .NET Framework 4.7+).  
* Un ambiente di sviluppo come Visual Studio 2022, VS Code o Rider.  
* Una licenza Aspose.BarCode per .NET (o una chiave di valutazione gratuita). Puoi ottenerla dal [Aspose website](https://purchase.aspose.com/barcode/net).  

> **Consiglio:** Se stai usando la versione di valutazione, il PNG generato conterrà una piccola filigrana “Evaluation”. Una versione con licenza la rimuove automaticamente.

## Passo 1: Configurare il progetto  

Crea un nuovo progetto console e aggiungi il pacchetto NuGet Aspose.BarCode.

```bash
dotnet new console -n MicroPdf417Demo
cd MicroPdf417Demo
dotnet add package Aspose.BarCode --version 24.9.0
```

Il comando `dotnet add package` scarica le dipendenze dell'**esempio Aspose.BarCode C#**, così non devi gestire manualmente i DLL.

## Passo 2: Scrivere il codice completo  

Sostituisci il file `Program.cs` auto‑generato con il codice seguente. Dimostra come **creare micro pdf417 barcode** dall'inizio alla fine.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text.
            // The text can contain Unicode characters; here we use a sample string.
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Åspóse.Barcóde©");

            // 2️⃣ Set the X‑dimension (module width) in pixels.
            // This determines the width of the smallest element (a bar or a space).
            generator.Parameters.Barcode.XDimension.Pixels = 2; // secondary keyword: set XDimension pixels

            // 3️⃣ Define the number of columns (allowed values: 1‑4 for MicroPDF417).
            // More columns mean a wider barcode but fewer rows, which can improve readability.
            generator.Parameters.Barcode.Pdf417.Columns = 4; // secondary keyword: define barcode columns

            // 4️⃣ Choose the output format and save the barcode as a PNG image.
            // PNG preserves the sharp edges of the barcode, which is ideal for scanning.
            string outputPath = "MicroPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png); // secondary keyword: save barcode as PNG

            Console.WriteLine($"Micro PDF417 barcode saved to {outputPath}");
        }
    }
}
```

### Perché ogni riga è importante  

* **BarcodeGenerator constructor** – Istanzia il **micro pdf417 barcode generator** con il testo che desideri codificare.  
* **XDimension.Pixels** – Controlla la larghezza del modulo; impostandola a `2` pixel si ottiene un barcode denso, ad alta risoluzione, adatto alla maggior parte degli scanner.  
* **Pdf417.Columns** – MicroPDF417 supporta solo 1‑4 colonne. Scegliendo `4` si riduce l'altezza del barcode, utile quando lo spazio verticale è limitato.  
* **Save method** – Scrive il barcode in un file PNG. PNG è lossless, garantendo che lo scanner legga esattamente il pattern generato.  

## Passo 3: Compilare ed eseguire  

Compila ed esegui il programma:

```bash
dotnet run
```

Dovresti vedere l'output della console:

```
Micro PDF417 barcode saved to MicroPdf417.png
```

Un file chiamato **MicroPdf417.png** appare nella cartella del progetto. Aprilo con qualsiasi visualizzatore di immagini; vedrai un nitido micro PDF417 barcode che codifica la stringa `"Åspóse.Barcóde©"`.

![Esempio di micro PDF417 barcode generato](MicroPdf417.png "Esempio di micro PDF417 barcode generato"){.center-image width=400 alt="Esempio di immagine di micro PDF417 barcode generato"}

*L'immagine sopra è il risultato del codice mostrato al Passo 2.*

## Passo 4: Varianti comuni e casi limite  

| Situazione | Come adattare il codice |
|-----------|--------------------------|
| **Lunghezza dati diversa** | MicroPDF417 può codificare fino a 1 200 caratteri. Basta cambiare il secondo argomento di `BarcodeGenerator`. |
| **Risoluzione più alta** | Aumenta `XDimension.Pixels` a `3` o `4`. Moduli più grandi migliorano la leggibilità su scanner a bassa risoluzione ma aumentano le dimensioni dell'immagine. |
| **Colori personalizzati** | Dopo aver creato il generatore, imposta `generator.Parameters.Barcode.BarcodeColor = Color.Blue;` e `generator.Parameters.Barcode.BackgroundColor = Color.White;`. |
| **Salvataggio in altri formati** | Sostituisci `BarCodeImageFormat.Png` con `Jpeg`, `Bmp` o `Gif` a seconda dei requisiti successivi. |
| **Incorporamento in PDF** | Usa `generator.Save("barcode.pdf", BarCodeImageFormat.Pdf);` e poi unisci il PDF con altri documenti usando Aspose.PDF. |

> **Attenzione:** Impostare `XDimension.Pixels` al di sotto di `1` genera un `ArgumentOutOfRangeException`. Mantienilo sempre a `1` o più.

## Passo 5: Verificare il barcode  

Per assicurarsi che il barcode venga letto correttamente:

1. Apri il PNG in un visualizzatore di immagini.  
2. Usa qualsiasi app di scansione barcode per smartphone che supporti PDF417 (la maggior parte delle app “scanner QR‑code” lo includono).  
3. Scansiona l'immagine; l'app dovrebbe mostrare il testo originale `"Åspóse.Barcóde©"`.

Se la scansione fallisce, ricontrolla le impostazioni di **X‑dimension** e **column** – una larghezza del modulo troppo piccola o un numero di colonne non supportato possono rendere il pattern illeggibile.

## Conclusione  

Ora sai come **creare micro pdf417 barcode** in C# usando Aspose.BarCode. Il tutorial ha coperto:

* Istanziare un **micro pdf417 barcode generator**.  
* **Set XDimension pixels** per controllare la larghezza del modulo.  
* **Define barcode columns** per regolare la forma.  
* **Save barcode as PNG** per un output immagine lossless.  

Da qui puoi esplorare funzionalità aggiuntive come la personalizzazione dei colori, l'incorporamento del barcode in PDF, o la generazione di barcode al volo in API web ASP.NET Core. Buon coding!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Crea barcode PNG in C# – guida completa a GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [Come creare macro PDF417 barcode in C# usando Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Crea barcode PDF417 in C# usando Aspose.BarCode – guida passo‑passo](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}