---
category: general
date: 2026-10-05
description: Crea un PNG di codice a barre in C# e impara come impostare il rapporto
  d'aspetto 15 per i codici a barre DataBar impilati omnidirezionali.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to set aspect ratio
- set aspect ratio 15
language: it
lastmod: 2026-10-05
og_description: Crea un PNG di codice a barre in C# e scopri come impostare il rapporto
  d'aspetto 15 per i codici a barre DataBar impilati omnidirezionali in pochi passaggi.
og_image_alt: Screenshot showing a generated barcode PNG with aspect ratio 15
og_title: Crea PNG di codice a barre in C# – tutorial per impostare il rapporto d'aspetto
  15
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Create barcode PNG in C# and learn how to set aspect ratio 15 for stacked
    DataBar omnidirectional barcodes.
  headline: How to create barcode PNG with a custom aspect ratio in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Come creare un PNG di codice a barre con un rapporto d'aspetto personalizzato
  in C#
url: /it/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un PNG di codice a barre con un rapporto d'aspetto personalizzato in C#

Se hai bisogno di **creare barcode PNG** in C#, questa guida ti mostra **come impostare il rapporto d'aspetto** 15 per un codice a barre DataBar impilato omnidirezionale. Ti guideremo attraverso ogni chiamata API, spiegheremo perché il rapporto d'aspetto è importante e ti forniremo un esempio completo e eseguibile che puoi inserire in qualsiasi progetto .NET.

Generare un'immagine di codice a barre è una necessità comune per sistemi di inventario, etichette di spedizione e applicazioni di punto vendita al dettaglio. Alla fine di questo tutorial avrai un file PNG che soddisfa le specifiche visive esatte richieste dal tuo partner commerciale. Nessuno strumento esterno, nessuna modifica manuale dell'immagine—solo codice.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6.0 o versioni successive (l'esempio utilizza .NET 6 ma funziona con .NET 5+)
* Visual Studio 2022 (o qualsiasi IDE che supporti .NET)
* Il pacchetto NuGet **Aspose.BarCode for .NET**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Permessi di scrittura sulla cartella in cui desideri salvare il file PNG

Questi requisiti sono minimi; lo stesso codice funziona in .NET Core, .NET Framework o in un'applicazione console.

## Crea barcode PNG con Aspose.BarCode

Il primo passo è istanziare la classe `BarcodeGenerator` con il tipo di barcode corretto. In questo caso usiamo `EncodeTypes.DatabarStackedOmniDirectional`, che produce un DataBar impilato che può essere letto da qualsiasi direzione.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

*Perché è importante:* Il costruttore accetta due argomenti—**la simbologia del barcode** e **la stringa di dati**. Il formato DataBar richiede un identificatore di applicazione GS1, motivo per cui i dati di esempio iniziano con `(01)`.

## Come impostare il rapporto d'aspetto per un DataBar impilato

La larghezza visiva di un DataBar è controllata dalla proprietà **aspect ratio**. Un rapporto più alto rende le barre più larghe, il che può migliorare l'affidabilità della scansione su stampanti a bassa risoluzione.

```csharp
// Step 2: Define the module width (X‑dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Il `XDimension` definisce la dimensione di un singolo modulo (la barra o lo spazio più piccolo). Mantenerlo a 2 px fornisce un'immagine nitida e ad alta densità, adatta alla maggior parte delle stampanti di etichette.

## Imposta rapporto d'aspetto 15 – walkthrough del codice

Ora applichiamo il requisito **set aspect ratio 15**. Questo è il cuore del tutorial e dimostra la chiamata API esatta di cui hai bisogno.

```csharp
// Step 3: Set the DataBar aspect ratio to 15 for a wider appearance
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

*Perché 15?* Il rapporto d'aspetto predefinito per il DataBar impilato è 12. Incrementarlo a 15 espande la larghezza di ogni barra del 25 %, corrispondendo spesso alle specifiche dei fornitori logistici che richiedono un barcode più ampio per una scansione più veloce.

## Salva il barcode come PNG

Con il generatore configurato, l'ultimo passo è scrivere l'immagine su disco. Il metodo `Save` accetta un percorso file e un enum del formato immagine.

```csharp
// Step 4: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Il formato PNG preserva la qualità lossless, garantendo che il barcode venga renderizzato esattamente come progettato su qualsiasi display o stampante.

## Esempio completo e output previsto

Di seguito trovi il programma completo che puoi copiare nel metodo `Main` di un'app console. Include tutti i passaggi descritti sopra, più un piccolo messaggio di verifica.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with stacked DataBar (omnidirectional) and sample GS1 data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Set the DataBar aspect ratio to 15 – this is the key to a wider barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;

        // Choose a folder you have write access to
        string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";

        // Save the barcode as a PNG file
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode PNG created at: {outputPath}");
    }
}
```

**Output previsto**

Eseguendo il programma viene creato un file chiamato `DatabarAspectRatio15.png` contenente un barcode DataBar impilato chiaro e largo. Quando apri il PNG, dovresti vedere un barcode orizzontalmente allungato che rispetta comunque le specifiche GS1 DataBar.

![Barcode PNG with aspect ratio 15](barcode-aspect15.png)

*Image alt text:* **creare barcode PNG che mostra un DataBar impilato con rapporto d'aspetto 15**

### Suggerimenti e problemi comuni

| Situazione | Raccomandazione |
|-----------|----------------|
| **L'immagine appare sfocata** | Incrementa `XDimension.Pixels` a 3 px o più, ma mantieni la dimensione complessiva dell'immagine sotto i 500 px per evitare file troppo grandi. |
| **Lo scanner non riesce a leggere il codice** | Verifica che la stringa di dati segua il formato GS1 (prefisso `(01)`). Inoltre, assicurati che la risoluzione della stampante sia almeno 300 dpi. |
| **Necessità di un formato file diverso** | Sostituisci `BarCodeImageFormat.Png` con `Jpeg`, `Bmp` o `Gif`—l'API supporta tutti i principali formati raster. |
| **Esecuzione in un'applicazione web** | Usa `generator.Save(Stream, BarCodeImageFormat.Png)` per scrivere direttamente alla risposta HTTP senza toccare il file system. |

### Estendere l'esempio

* **Barcodes multipli in un'immagine:** Crea ulteriori istanze di `BarcodeGenerator` e disegnale su un unico `Bitmap` usando `Graphics`.  
* **Aggiunta di testo leggibile dall'uomo:** Imposta `generator.Parameters.Caption.Visible = true` e personalizza il font tramite `generator.Parameters.Caption.Font`.  
* **Rapporto d'aspetto dinamico:** Preleva il valore del rapporto da un file di configurazione o da un database per generare barcode con larghezze variabili al volo.

## Conclusione

In questo tutorial hai imparato come **creare barcode PNG** in C# e impostare con precisione **il rapporto d'aspetto** 15 per un barcode DataBar impilato omnidirezionale. Il codice completo e eseguibile dimostra ogni chiamata API richiesta, spiega perché ogni impostazione è importante e fornisce consigli pratici per implementazioni reali.  

Successivamente, potresti esplorare **come impostare il rapporto d'aspetto** per altri tipi di barcode (ad es. QR Code o Code 128) o integrare il generatore in un servizio ASP .NET Core che restituisce immagini di barcode su richiesta. Buon coding!

## Cosa dovresti imparare dopo?

I tutorial seguenti coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come creare immagini PNG databar con C# e Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [Come creare un barcode databar impilato in C# con Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [Personalizzare il rapporto d'aspetto del databar impilato omnidirezionale in .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}