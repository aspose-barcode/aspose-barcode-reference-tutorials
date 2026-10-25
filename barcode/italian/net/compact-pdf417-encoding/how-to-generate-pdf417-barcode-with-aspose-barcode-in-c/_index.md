---
category: general
date: 2026-10-24
description: Scopri come generare un codice a barre PDF417 usando Aspose.BarCode in
  C# con impostazioni compatte e controllo della XDimension del codice a barre.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode
- compact PDF417
- barcode XDimension
- PDF417 columns
language: it
lastmod: 2026-10-24
og_description: Genera codici a barre PDF417 in C# con Aspose.BarCode. Segui questa
  guida completa per creare immagini PDF417 compatte, controllare la XDimension e
  impostare le colonne.
og_image_alt: Screenshot of generated PDF417 barcode using Aspose.BarCode
og_title: Genera codice a barre PDF417 con Aspose.BarCode – C# passo‑passo
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  headline: How to generate PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  name: How to generate PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: 1. Changing the image format
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 2. Encoding large amounts of data
    text: 'PDF417 can store up to ~1.1 KB of text. When the payload exceeds the capacity
      of three columns, the library automatically adds rows. To keep the barcode compact,
      you can:'
  - name: 3. Using a license to remove the trial watermark
    text: '```csharp Aspose.BarCode.License license = new Aspose.BarCode.License();
      license.SetLicense("Aspose.BarCode.lic"); ```'
  - name: 4. Handling exceptions
    text: '```csharp try { generator.Save(outputPath, BarCodeImageFormat.Png); } catch
      (Exception ex) { Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
      } ```'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- PDF417
- C#
title: Come generare il codice a barre PDF417 con Aspose.BarCode in C#
url: /it/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come generare il codice a barre PDF417 con Aspose.BarCode in C#

Se hai bisogno di **generare un codice a barre PDF417** in un'applicazione .NET, questa guida ti mostra una soluzione completa, pronta‑all'uso. Vedrai come Aspose.BarCode renda il processo semplice fornendo al contempo un controllo dettagliato su **PDF417 compatto**, **barcode XDimension** e **colonne PDF417**.

Creare un codice a barre è una necessità comune per sistemi di inventario, piattaforme di biglietteria e flussi di lavoro documentali. Alla fine di questo tutorial avrai un programma C# autonomo che produce un'immagine PNG nitida di un codice a barre PDF417, pronta per essere incorporata in qualsiasi interfaccia utente o stampata su un'etichetta.

## Cosa ti servirà

- .NET 6.0 SDK o versioni successive (il codice funziona anche con .NET Framework 4.6+)
- Visual Studio 2022 o qualsiasi editor C# tu preferisca
- Una licenza valida di Aspose.BarCode per .NET (la versione di prova gratuita funziona per lo sviluppo)
- Familiarità di base con la sintassi C#

> **Consiglio professionale:** Se stai valutando Aspose.BarCode, scarica la versione di prova dal sito ufficiale e aggiungi il pacchetto NuGet `Aspose.BarCode` al tuo progetto. La versione di prova aggiunge una piccola filigrana all'immagine generata, che scompare una volta applicata una licenza.

## Passo 1: Installa il pacchetto NuGet Aspose.BarCode

Apri un terminale nella cartella della tua soluzione ed esegui:

```bash
dotnet add package Aspose.BarCode
```

Il comando scarica l'ultima versione stabile (a ottobre 2026, versione 23.12). L'aggiunta del pacchetto ripristina lo spazio dei nomi `Aspose.BarCode.Generation` che utilizzerai per **generare immagini di codice a barre PDF417**.

## Passo 2: Crea un progetto console C# di base

Se non hai ancora un progetto, creane uno:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

Apri `Program.cs`. Lo scheletro contiene già un metodo `Main` dove inseriremo il codice per la generazione del codice a barre.

## Passo 3: Inizializza il generatore di codici a barre

First, import the required namespace:

```csharp
using Aspose.BarCode.Generation;
```

Then, inside `Main`, instantiate `BarcodeGenerator` with the PDF417 symbology and the data you want to encode:

```csharp
// Step 3: Initialize the generator for a PDF417 barcode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

La stringa include caratteri Unicode per dimostrare che Aspose.BarCode gestisce correttamente input non‑ASCII. Se ti serve solo ASCII, sostituisci il testo con qualsiasi stringa semplice.

## Passo 4: Regola il barcode XDimension (dimensione del modulo)

Il **barcode XDimension** determina la larghezza della barra più piccola (il modulo). Impostarlo in pixel ti dà un controllo pixel‑perfect sulla dimensione finale dell'immagine:

```csharp
// Step 4: Set the module size – XDimension in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Un valore di `2` pixel produce un'immagine compatta senza sacrificare l'affidabilità della scansione. Aumenta il valore per codici a barre più grandi o diminuiscilo per layout molto densi.

## Passo 5: Configura le opzioni PDF417 compatte

Due impostazioni specifiche di PDF417 influenzano notevolmente l'impronta visiva:

| Impostazione | Significato | Valore tipico per output compatto |
|--------------|-------------|-----------------------------------|
| `Columns` | Number of data columns | `3` |
| `Truncate` (compact mode) | Omits the right‑hand quiet zone and reduces the number of rows | `true` |

Applicaleli come segue:

```csharp
// Step 5: Use a small number of columns and enable compact mode
generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417
```

Usare **colonne PDF417** impostate a `3` insieme a `Truncate = true` crea un codice a barre *PDF417 compatto* che si adatta bene a un'etichetta standard mantenendo la leggibilità dalla maggior parte degli scanner.

## Passo 6: Salva l'immagine del codice a barre

Infine, scrivi il codice a barre su disco. L'esempio salva un PNG, ma Aspose.BarCode supporta anche BMP, JPEG, GIF, TIFF e SVG:

```csharp
// Step 6: Save the barcode as a PNG file
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

La costante `BarCodeImageFormat.Png` indica alla libreria di produrre un PNG senza perdita, ideale per ulteriori elaborazioni o stampe.

## Codice sorgente completo, eseguibile

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator for PDF417 with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size – barcode XDimension in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Configure compact PDF417 options
        generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
        generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417

        // 4️⃣ Save as PNG
        string outputPath = Path.Combine(
            Environment.CurrentDirectory,
            "CompactPdf417.png");

        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

Eseguendo il programma verrà generato `CompactPdf417.png` nella cartella radice del progetto. Apri il file con qualsiasi visualizzatore di immagini; vedrai un codice a barre PDF417 densamente impacchettato che codifica la stringa *Åspóse.Barcóde©*.

![Screenshot del codice a barre PDF417 generato con Aspose.BarCode](placeholder-image.png "Codice a barre PDF417 generato")

*Testo alternativo dell'immagine: Screenshot del codice a barre PDF417 generato con Aspose.BarCode* – questo testo alternativo contiene la parola chiave principale per l'accessibilità e la SEO.

## Verifica del risultato

1. Apri il file PNG. Il codice a barre dovrebbe consistere in tre colonne verticali di dati con un layout compatto (senza zone di silenzio aggiuntive sul lato destro).
2. Scansiona l'immagine con uno scanner di codici a barre per smartphone che supporti PDF417. Il testo decodificato deve corrispondere alla stringa di input originale.
3. Se lo scanner fallisce, prova ad aumentare `XDimension.Pixels` a `3` o `4`. Moduli più grandi migliorano la leggibilità su dispositivi a bassa risoluzione.

## Varianti comuni e casi limite

### 1. Cambiare il formato dell'immagine

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

SVG è basato su vettori, il che mantiene il codice a barre nitido a qualsiasi livello di zoom—utile per le pagine web.

### 2. Codificare grandi quantità di dati

PDF417 può memorizzare fino a ~1,1 KB di testo. Quando il payload supera la capacità di tre colonne, la libreria aggiunge automaticamente righe. Per mantenere il codice a barre compatto, puoi:

- Ridurre la lunghezza dei dati (ad esempio, usare un identificatore invece di un messaggio completo)
- Aumentare il numero di **colonne PDF417** (ad esempio, `generator.Parameters.Barcode.Pdf417.Columns = 5;`)

### 3. Usare una licenza per rimuovere la filigrana di prova

```csharp
Aspose.BarCode.License license = new Aspose.BarCode.License();
license.SetLicense("Aspose.BarCode.lic");
```

Posiziona il file di licenza accanto all'eseguibile. Dopo la licenza, l'immagine generata non contiene filigrane.

### 4. Gestione delle eccezioni

```csharp
try
{
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

I fallimenti tipici includono permessi di scrittura insufficienti o un formato immagine non supportato.

## Perché le impostazioni sono importanti

- **barcode XDimension** – Controlla il peso visivo di ogni barra. Troppo piccolo rende il codice a barre illeggibile; troppo grande spreca spazio.
- **PDF417 columns** – Meno colonne producono un codice a barre più stretto ma aumentano il numero di righe

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare ulteriori funzionalità dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come generare il codice a barre PDF417 con Aspose – Guida completa](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Genera codice a barre PDF417 con impostazioni compatte in C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-with-compact-settings-in-c/)
- [Come salvare il codice a barre e generare PDF417 con Aspose in C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}