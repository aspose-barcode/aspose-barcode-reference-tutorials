---
category: general
date: 2026-07-21
description: Genera rapidamente codici a barre in C# con Aspose.BarCode. Scopri come
  creare un codice a barre DataBar, personalizzare le dimensioni del codice a barre
  ed esportare l'immagine del codice a barre in pochi passaggi.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode c#
- create databar barcode
- customize barcode size
- change barcode dimensions
- export barcode image
language: it
lastmod: 2026-07-21
og_description: Genera barcode C# usando Aspose.BarCode. Crea un codice DataBar, personalizza
  le sue dimensioni ed esporta l'immagine istantaneamente.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode saved as PNG
og_title: Genera barcode C# – Crea codici DataBar con dimensioni personalizzate
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: Generate barcode C# quickly with Aspose.BarCode. Learn to create DataBar
    barcode, customize barcode size, and export barcode image in just a few steps.
  headline: Generate barcode C# – Create DataBar barcode
  type: TechArticle
- questions:
  - answer: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, `Gif`, or `Svg`.
      The API handles the conversion automatically.
    question: What if I need a different image format?
  - answer: Technically you can set both, but Aspose will prioritize the last property
      you modify. It's safer to set *one* dimension and let the library compute the
      other for a valid DataBar.
    question: Can I change both rows and columns simultaneously?
  - answer: 'Use `barcodeGen.Parameters.Barcode.ForegroundColor` and `BackgroundColor`.
      Example:'
    question: How do I apply a foreground/background color?
  - answer: DataBar Expanded Stacked supports up to 74 numeric characters (or 30 alphanumeric).
      Exceeding that throws an exception.
    question: Is there a size limit for the encoded data?
  type: FAQPage
tags:
- barcode
- csharp
- databar
- image-export
- aspnet
title: Genera codice a barre C# – Crea codice a barre DataBar
url: /it/python-java/general/generate-barcode-c-create-databar-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Genera barcode C# – Crea barcode DataBar

Cerchi di **generare barcode C#** senza dover setacciare una quantità infinita di documentazione? Sei nel posto giusto. In questa guida vedremo come creare un **barcode DataBar**, modificare le sue dimensioni e infine **esportare l'immagine del barcode**—tutto con poche righe di C#.

Immagina di aver bisogno di un'etichetta prodotto compatta che si adatti a un piccolo cartellino scaffale. Una simbologia DataBar Expanded Stacked fa al caso tuo, e con Aspose.BarCode puoi controllare esattamente quante colonne o righe utilizza. Pronto? Immergiamoci.

## Cosa otterrai

- **Crea un barcode DataBar** (la variante “expanded stacked”) da zero.  
- **Personalizza le dimensioni del barcode** impostando direttamente colonne o righe.  
- **Modifica le dimensioni del barcode** al volo senza ricostruire il generatore.  
- **Esporta l'immagine del barcode** in PNG (o in qualsiasi formato supportato da Aspose).  

## Prerequisiti

- .NET 6.0 o successivo (il codice funziona anche su .NET Framework 4.7+).  
- Una licenza valida di Aspose.BarCode per .NET (oppure puoi eseguire in modalità di prova).  
- Un IDE a tua scelta—Visual Studio, Rider o VS Code vanno bene.  

Se non hai ancora installato il pacchetto NuGet, esegui:

```bash
dotnet add package Aspose.BarCode
```

Tutto qui—nessuna altra dipendenza.

## Step 1: Configura il generatore di barcode (Come **generare barcode C#**)

Per prima cosa, ci serve un'istanza di `BarcodeGenerator` che punti alla simbologia **DataBar Expanded Stacked**. Questo oggetto è il motore che crea l'immagine in seguito.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Initialize the generator with the desired symbology and data
BarcodeGenerator barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // Symbology
    "Databar Expanded Stacked long");    // Human‑readable text (optional)
```

*Perché è importante*: l'enumerazione `EncodeTypes.DatabarExpandedStacked` indica ad Aspose che vogliamo la versione stacked, ideale per spazi stretti. Il testo che forniamo diventa il valore codificato; puoi sostituirlo con qualsiasi stringa numerica richiesta dalla tua applicazione.

## Step 2: **Personalizza le dimensioni del barcode** – imposta le colonne

I barcode DataBar ti permettono di influenzare la densità visiva specificando il numero di **colonne** *o* **righe**. Iniziamo con le colonne. Il conteggio delle righe verrà calcolato automaticamente per mantenere il barcode valido.

```csharp
// Set the number of columns; rows are computed automatically
barcodeGen.Parameters.Barcode.DataBar.Columns = 4;
```

*Consiglio*: le colonne influenzano la larghezza del barcode. Più colonne → barcode più largo, il che può migliorare l'affidabilità della scansione su stampanti a bassa risoluzione.

## Step 3: **Esporta l'immagine del barcode** con l'impostazione delle colonne

Ora scriviamo l'immagine su disco. Puoi scegliere PNG, JPEG, BMP o anche SVG. Ecco il PNG per un output nitido e senza perdita.

```csharp
// Save the barcode image using the current column configuration
barcodeGen.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

> **Risultato atteso** – Apri `DatabarCols4.png` e dovresti vedere un DataBar ordinatamente impilato con quattro colonne. Sembra una pila densa di barre verticali, perfetta per una piccola etichetta.

## Step 4: **Modifica le dimensioni del barcode** – imposta le righe invece

A volte hai bisogno di un barcode più alto piuttosto che più largo. Passa al controllo delle righe; Aspose ricalcolerà automaticamente le colonne.

```csharp
// Switch to row control – columns will be derived automatically
barcodeGen.Parameters.Barcode.DataBar.Rows = 3;
```

*Perché cambiare?* Le righe influenzano l'altezza del barcode. Più righe rendono il simbolo più alto, il che può essere utile quando hai spazio verticale ma larghezza limitata.

## Step 5: **Esporta l'immagine del barcode** con l'impostazione delle righe

Salva la seconda variante. Nota che il nome file riflette la modifica; puoi anche conservare entrambe le immagini per un confronto.

```csharp
// Save the barcode image using the new row configuration
barcodeGen.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

> **Risultato** – `DatabarRows3.png` ora mostra una versione più alta degli stessi dati, ancora perfettamente leggibile.

## Esempio completo funzionante

Mettendo tutto insieme, ecco un'app console autonoma che puoi copiare‑incollare ed eseguire subito:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator for DataBar Expanded Stacked
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Customize size – set columns (width)
        barcodeGen.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Export image with column setting
        string colPath = @"C:\Barcodes\DatabarCols4.png";
        barcodeGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column‑based barcode to {colPath}");

        // 4️⃣ Change dimensions – set rows (height)
        barcodeGen.Parameters.Barcode.DataBar.Rows = 3;

        // 5️⃣ Export image with row setting
        string rowPath = @"C:\Barcodes\DatabarRows3.png";
        barcodeGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row‑based barcode to {rowPath}");
    }
}
```

Esegui il programma, poi apri i due file PNG. Hai ora **generato barcode C#**, **personalizzato le dimensioni del barcode**, **modificato le dimensioni del barcode** e **esportato l'immagine del barcode**—tutto in meno di un minuto.

## Domande comuni & casi particolari

- **E se ho bisogno di un formato immagine diverso?**  
  Sostituisci `BarCodeImageFormat.Png` con `Jpeg`, `Bmp`, `Gif` o `Svg`. L'API gestisce automaticamente la conversione.

- **Posso modificare contemporaneamente righe e colonne?**  
  Tecnicamente puoi impostare entrambi, ma Aspose darà priorità all'ultima proprietà modificata. È più sicuro impostare *una* dimensione e lasciare che la libreria calcoli l'altra per un DataBar valido.

- **Come applicare un colore di primo piano/sfondo?**  
  Usa `barcodeGen.Parameters.Barcode.ForegroundColor` e `BackgroundColor`. Esempio:  
  ```csharp
  barcodeGen.Parameters.Barcode.ForegroundColor = Color.DarkBlue;
  barcodeGen.Parameters.Barcode.BackgroundColor = Color.White;
  ```

- **Esiste un limite di dimensione per i dati codificati?**  
  DataBar Expanded Stacked supporta fino a 74 caratteri numerici (o 30 alfanumerici). Superare questo limite genera un'eccezione.

## Prossimi passi

Ora che hai padroneggiato le basi per **creare barcode databar**, considera:

- Aggiungere **annotazioni di testo** sotto il barcode (`barcodeGen.Parameters.CaptionAbove.Text`).
- Incorporare il PNG direttamente in un PDF usando Aspose.PDF.
- Generare barcode in blocco iterando su un CSV di ID prodotto.

Ognuno di questi argomenti si basa sullo stesso oggetto `BarcodeGenerator`, quindi non dovrai ricominciare da zero.

---

**In sintesi**: ora sai come **generare barcode C#**, **personalizzare le dimensioni del barcode**, **modificare le dimensioni del barcode** e **esportare l'immagine del barcode** con Aspose.BarCode. Sperimenta con i valori di colonna/riga, cambia i formati immagine e integra il codice nel tuo sistema di inventario o POS. Buon coding!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Genera immagine barcode – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Come generare barcode Aztec con rapporto d'aspetto personalizzato usando Aspose.BarCode per .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Genera barcode DataMatrix – Guida Pro con Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}