---
category: general
date: 2026-09-07
description: Scopri come creare un'immagine di codice a barre in C# e regolare altezza,
  larghezza e formato per generare rapidamente file PNG di codici a barre.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to set barcode
- how to adjust barcode
- generate barcode png
- change barcode height
language: it
lastmod: 2026-09-07
og_description: Crea un'immagine di codice a barre in C# e impara come impostare le
  dimensioni del codice a barre, modificare l'altezza del codice a barre e generare
  file PNG del codice a barre per qualsiasi applicazione.
og_image_alt: C# generated barcode image saved as PNG with custom height
og_title: Crea immagine di codice a barre in C# – guida passo passo
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Learn how to create barcode image in C# and adjust its height, width,
    and format to generate barcode PNG files quickly.
  headline: How to create barcode image in C# with adjustable height
  type: TechArticle
- description: Learn how to create barcode image in C# and adjust its height, width,
    and format to generate barcode PNG files quickly.
  name: How to create barcode image in C# with adjustable height
  steps:
  - name: 3.1 Adjust the narrow bar width (X‑dimension)
    text: The X‑dimension controls the thickness of the thinnest bar. A value of **2
      pixels** yields a finer appearance, useful when you need a compact label.
  - name: 3.2 Change barcode height for visual balance
    text: Bar height determines how tall the barcode appears. Below we show two common
      heights—30 pixels for a small label and 60 pixels for a larger visual. This
      demonstrates **how to adjust barcode** height programmatically.
  - name: 4.1 Save the first image (30 px height)
    text: '```csharp // Save a 30‑pixel‑high barcode as PNG generator.Save("DatabarBarHeight30Pixels.png",
      BarCodeImageFormat.Png); ```'
  - name: 4.2 Increase the height and save a second image
    text: '```csharp // Increase height to 60 pixels for a larger visual generator.Parameters.Barcode.BarHeight.Pixels
      = 60;'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Come creare un'immagine di codice a barre in C# con altezza regolabile
url: /it/python-java/general/how-to-create-barcode-image-in-c-with-adjustable-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un'immagine di codice a barre in C# con altezza regolabile

Se devi creare un'immagine di codice a barre in C# per un sistema di punto vendita o per un tracciatore di inventario, questa guida ti mostra l’intero flusso di lavoro. Vedrai come impostare i parametri del codice a barre, modificare l’altezza del codice a barre e generare file PNG del codice a barre che soddisfano i requisiti visivi.

Generare un’immagine di codice a barre è un compito comune quando si integrano hardware di scansione, si stampano etichette o si costruiscono dashboard di report. Alla fine di questo tutorial avrai a disposizione uno snippet di codice riutilizzabile che ti permette di regolare la X‑dimension, l’altezza e il formato di output del codice a barre senza uscire dall’IDE.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6.0 (o successivo) installato – il codice si compila con qualsiasi SDK .NET recente.
* Un riferimento alla libreria **Aspose.BarCode** (disponibile via NuGet `Aspose.BarCode`).
* Familiarità di base con le applicazioni console C#.

Questi requisiti garantiscono che l’esempio funzioni subito su Windows, Linux o macOS.

## Passo 1: Configura il progetto e importa la libreria

Crea un nuovo progetto console e aggiungi il pacchetto barcode:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Ora apri *Program.cs* e aggiungi le direttive `using` necessarie:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;
using Aspose.BarCode;
```

Queste importazioni ti danno accesso a `BarcodeGenerator`, `EncodeTypes` e alle enum dei formati immagine necessarie per **creare immagini di codice a barre**.

## Passo 2: Inizializza il generatore con la simbologia desiderata

La prima riga di codice crea un `BarcodeGenerator` che sa quale tipo di codice a barre codificare. In questo esempio usiamo la simbologia DataBar Omni‑Directional, ma puoi sostituire `EncodeTypes.DatabarOmniDirectional` con qualsiasi altro tipo supportato da Aspose.BarCode.

```csharp
// Initialize a generator for a DataBar Omni‑Directional barcode
var generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

La stringa `"(01)12345678901231"` segue il formato GS1 Application Identifier, richiesto da molti rivenditori. Inizializzare il generatore è la base per ogni operazione **come impostare il codice a barre** che segue.

## Passo 3: Come impostare le dimensioni del codice a barre – X‑dimension e altezza

### 3.1 Regola la larghezza della barra stretta (X‑dimension)

La X‑dimension controlla lo spessore della barra più sottile. Un valore di **2 pixel** produce un aspetto più fine, utile quando serve un’etichetta compatta.

```csharp
// Set the narrow bar width to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

### 3.2 Cambia l’altezza del codice a barre per bilanciare l’aspetto visivo

L’altezza della barra determina quanto è alto il codice a barre. Di seguito mostriamo due altezze comuni—30 pixel per un’etichetta piccola e 60 pixel per una più grande. Questo dimostra **come regolare l’altezza del codice a barre** programmaticamente.

```csharp
// Height 30 pixels – suitable for compact labels
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

## Passo 4: Genera file PNG del codice a barre con altezze diverse

### 4.1 Salva la prima immagine (altezza 30 px)

```csharp
// Save a 30‑pixel‑high barcode as PNG
generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

### 4.2 Aumenta l’altezza e salva una seconda immagine

```csharp
// Increase height to 60 pixels for a larger visual
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save a 60‑pixel‑high barcode as PNG
generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Queste due chiamate a `Save` illustrano **generare file PNG del codice a barre** con dimensioni distinte riutilizzando la stessa istanza del generatore. Il formato immagine è impostato esplicitamente su PNG, che preserva la qualità lossless—ideale per la stampa o la visualizzazione su schermo.

## Passo 5: Esempio completo e eseguibile

Mettendo tutto insieme ottieni un unico metodo `Main` che puoi copiare in qualsiasi progetto console C#:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar Omni‑Directional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set the narrow bar width (X‑dimension) to 2 pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Create a 30‑pixel‑high barcode and save it as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode as DatabarBarHeight30Pixels.png");

        // 4️⃣ Change barcode height to 60 pixels and save again
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode as DatabarBarHeight60Pixels.png");
    }
}
```

Eseguendo questo programma vengono prodotti due file PNG nella cartella di output del progetto:

* `DatabarBarHeight30Pixels.png` – un codice a barre compatto di 30 px.
* `DatabarBarHeight60Pixels.png` – un codice a barre più grande di 60 px.

Entrambi i file contengono una **creazione di immagine di codice a barre** che può essere incorporata in HTML, stampata su etichette o inviata a un’app mobile per la scansione.

## Domande comuni e gestione dei casi limite

| Domanda | Risposta |
|----------|--------|
| **E se ho bisogno di un formato immagine diverso?** | Sostituisci `BarCodeImageFormat.Png` con `BarCodeImageFormat.Jpeg`, `Bmp` o `Gif`. La libreria gestisce automaticamente la conversione. |
| **Posso cambiare i colori di primo piano/sfondo?** | Sì. Usa `generator.Parameters.Barcode.ForeColor` e `BackColor` per impostare valori `System.Drawing.Color` prima di chiamare `Save`. |
| **Come generare un codice a barre senza creare un file su disco?** | Chiama `generator.GenerateBarCodeImage()` per ottenere un oggetto `System.Drawing.Image`, quindi trasmettilo direttamente a una risposta o a un database. |
| **Cosa succede se la stringa dati supera il limite della simbologia?** | Il generatore lancia `ArgumentException`. Convalida la lunghezza dell’input o tronca secondo le specifiche della simbologia. |
| **Esiste un modo per elaborare più codici a barre in batch?** | Avvolgi i passaggi in un ciclo `foreach` che aggiorna `generator.CodeText` e `BarHeight` per ogni elemento, poi chiama `Save` con un nome file univoco. |

Affrontare questi scenari rende la logica **come regolare il codice a barre** robusta per progetti reali.

## Consigli professionali per una generazione affidabile di codici a barre

* **Cache il generatore** quando crei molti codici a barre dello stesso tipo; riutilizzare l’oggetto riduce l’overhead di allocazione.
* **Imposta `Resolution`** (`generator.Parameters.ImageResolution.Dpi`) se ti servono PNG ad alta risoluzione per la stampa.
* **Convalida i dati GS1** prima di assegnarli a `CodeText` per evitare errori di codifica che potrebbero causare fallimenti di scansione.
* **Testa su scanner reali** dopo aver modificato altezza o X‑dimension—alcuni dispositivi legacy hanno requisiti minimi di dimensione.

## Conclusione

Ora sai **come creare un’immagine di codice a barre** in C#, **come impostare le dimensioni del codice a barre**, **come regolare l’altezza del codice a barre** e **generare file PNG del codice a barre** per qualsiasi requisito visivo. Regolando `XDimension` e `BarHeight` puoi produrre codici a barre compatti o grandi senza modificare i dati sottostanti.

Successivamente, esplora argomenti correlati come **cambiare dinamicamente l’altezza del codice a barre** in base all’input dell’utente, incorporare codici a barre in report PDF usando Aspose.PDF, o passare alla generazione di QR‑code con `EncodeTypes.QR`. Sperimenta con diverse simbologie e formati di output per padroneggiare completamente la creazione di codici a barre in C#.

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare ulteriori funzionalità dell’API e a esplorare approcci alternativi nei tuoi progetti.

- [Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to Generate Barcode Image in C# – MicroPdf417 Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}