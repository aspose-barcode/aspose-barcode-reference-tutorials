---
category: general
date: 2026-07-18
description: Esempio di generatore di codici a barre che mostra come impostare le
  dimensioni e generare un'immagine di codice a barre DataBar Stacked Omni‑Directional
  in C#. Impara rapidamente i tipi di codifica dei codici a barre.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to set dimensions
- how to generate databar
- barcode encode types
- create barcode image c#
language: it
lastmod: 2026-07-18
og_description: L'esempio di generatore di codici a barre ti guida nella definizione
  delle dimensioni, nella scelta dei tipi di codifica e nella creazione di progetti
  C# per immagini di codici a barre con un codice minimo.
og_image_alt: Barcode generator example output showing DataBar barcode with aspect
  ratio 15
og_title: Esempio di Generatore di Codici a Barre – Creazione Rapida di Immagini DataBar
  in C#
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Barcode generator example showing how to set dimensions and generate
    a DataBar Stacked Omni‑Directional barcode image in C#. Learn barcode encode types
    quickly.
  headline: Barcode Generator Example – Build DataBar Image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
- image generation
title: Esempio di generatore di codici a barre – Crea immagine DataBar in C#
url: /it/python-java/general/barcode-generator-example-build-databar-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Esempio di Generatore di Codici a Barre – Creare Immagine DataBar in C#

Hai mai avuto bisogno di un **esempio di generatore di codici a barre** che stampi davvero un codice a barre reale senza impazzire? Non sei solo. La maggior parte degli sviluppatori si blocca quando cerca di capire **come impostare le dimensioni** per un codice DataBar Stacked Omni‑Directional, soprattutto quando la documentazione è sepolta sotto strati di gergo tecnico.

In questo tutorial percorreremo un programma C# completo, pronto all'uso, che mostra **come generare immagini databar**, sceglie i giusti **barcode encode types**, e infine **create barcode image c#** file che puoi inserire in qualsiasi progetto. Niente fronzoli—solo il codice da copiare‑incollare, più la spiegazione dietro ogni riga.

## Cosa Ti Serve

- **.NET 6** (o qualsiasi versione recente di .NET) – l'API che usiamo punta a .NET Standard, quindi funziona anche su .NET Framework.  
- **Aspose.BarCode for .NET** – la libreria che fornisce `BarcodeGenerator`. Puoi ottenerla da NuGet con `Install-Package Aspose.BarCode`.  
- Un **IDE C#** – Visual Studio, Rider o VS Code vanno bene.  
- Una cartella su disco dove salvare i file PNG (il codice crea `DatabarAspectRatio15.png` e `DatabarAspectRatio30.png`).

Hai tutto? Ottimo—tuffiamoci.

## Esempio di Generatore di Codici a Barre – Inizializzare il Generatore

Prima di tutto: ci serve un'istanza di `BarcodeGenerator` configurata per la simbologia **DataBar Stacked Omni‑Directional**. Questo è il **barcode encode type** con cui lavoreremo.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Stacked Omni‑Directional barcode generator
        // with the desired GTIN content.
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

> **Perché è importante:** `EncodeTypes.DatabarStackedOmniDirectional` indica ad Aspose esattamente quale simbologia renderizzare. Se scegli il tipo sbagliato, lo scanner non riconoscerà il codice a barre, per quanto bella sia l'immagine.

## Come Impostare le Dimensioni per il Codice a Barre

La leggibilità di un codice a barre dipende dalla sua **X‑dimension** (la larghezza della barra più stretta). Nella maggior parte dei casi un valore di 2 pixel è sufficiente, ma puoi modificarlo per adattarlo alla tua stampante o schermo.

```csharp
        // Step 2: Set a common X‑dimension (pixel width of the narrowest bar)
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Consiglio pro:** Se ti chiedi **come impostare le dimensioni** per un'altra famiglia di codici a barre, la stessa catena di proprietà (`Parameters.Barcode.XDimension`) vale—basta cambiare il valore di `Pixels`.

## Come Generare un Codice DataBar Stacked Omni‑Directional

Ora che il generatore è pronto, giocheremo con la proprietà **aspect ratio**. Questa controlla il rapporto altezza‑larghezza del DataBar, permettendoti di produrre un simbolo corto e quadrato o uno alto e stretto.

```csharp
        // Step 3: Generate and save a barcode with aspect ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

> **Cosa succede?** `AspectRatio = 15` dice al motore di rendere le barre 15 volte più alte della loro larghezza. Il PNG risultante viene salvato accanto all'eseguibile.

## Creare Immagine di Codice a Barre C# – Cambiare l'Aspect Ratio

Dimostriamo la flessibilità cambiando il rapporto a 30 e salvando un secondo file.

```csharp
        // Step 4: Change the aspect ratio to 30 and save another barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been saved successfully.");
    }
}
```

Quando esegui il programma, otterrai due file PNG:

| File | Aspect Ratio | Dimensione Approx. |
|------|--------------|--------------------|
| `DatabarAspectRatio15.png` | 15 | 120 × 180 px |
| `DatabarAspectRatio30.png` | 30 | 120 × 360 px |

Aprili con qualsiasi visualizzatore di immagini—dovresti vedere simboli DataBar puliti e leggibili.

## Panoramica dei Barcode Encode Types (Opzionale ma Utile)

Se sei curioso di conoscere gli altri **barcode encode types** supportati da Aspose, ecco una rapida cheat‑sheet:

| EncodeTypes Enum | Descrizione |
|------------------|-------------|
| `EncodeTypes.Code128` | Alfanumerico ad alta densità |
| `EncodeTypes.QR` | Codice matrice 2‑D |
| `EncodeTypes.DatabarExpanded` | GS1 DataBar per il retail |
| `EncodeTypes.DatabarStackedOmniDirectional` | **Il nostro focus** – compatto, omnidirezionale |

Conoscere l'enum giusto ti salva da molti tentativi ed errori quando cambi progetto.

## Problemi Comuni & Come Evitarli

- **Pacchetto NuGet mancante** – Il codice non compila senza `Aspose.BarCode`. Esegui prima `dotnet add package Aspose.BarCode`.  
- **Percorso file errato** – Se usi un percorso assoluto, controlla le doppie barre rovesciate (`\\`) su Windows. I percorsi relativi (come mostrato) mantengono la portabilità.  
- **Aspect ratio troppo estremo** – Rapporti superiori a 50 possono rendere il codice a barre troppo alto per gli scanner tipici. Attieniti a 15‑30 per la maggior parte dei casi d'uso.

## Codice Sorgente Completo (Pronto per Copia‑Incolla)

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator with DataBar Stacked Omni‑Directional type
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GTIN‑14 sample

        // 2️⃣ Set X‑dimension (how to set dimensions) – 2 pixels is a safe default
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First barcode: aspect ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);

        // 4️⃣ Second barcode: aspect ratio 30
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("✅ Two barcode images saved – check your project folder.");
    }
}
```

Esegui il programma (`dotnet run` o premi **F5** in Visual Studio) e vedrai il messaggio nella console che conferma che i file sono stati salvati su disco.

![Esempio di output del generatore di codici a barre che mostra il DataBar con aspect ratio 15](placeholder/path/to/image.png){: .align-center alt="Esempio di output del generatore di codici a barre che mostra il DataBar con aspect ratio 15"}

## Conclusioni

Abbiamo appena completato un **esempio di generatore di codici a barre** che dimostra **come impostare le dimensioni**, sceglie i corretti **barcode encode types**, e infine **create barcode image c#** file che puoi incorporare ovunque. Il codice è piccolo, i concetti sono cristallini, e ora hai una solida base per estendere la soluzione—magari aggiungendo didascalie di testo, ruotando l'immagine o passando a un'altra simbologia.

### Qual è il Prossimo Passo?

- Sperimenta con **diverse X‑dimension** per vedere come varia la tolleranza dello scanner.  
- Prova altri **EncodeTypes** come `Code128` o `QR` per ampliare il tuo toolkit.  
- Automatizza la generazione in batch: cicla su un CSV di ID prodotto e genera un PNG per ciascuno.

Se incontri difficoltà, lascia un commento qui sotto o consulta la documentazione di Aspose.BarCode—è ricca di esempi che completano quanto trattato qui.

Buon coding, e che i tuoi codici a barre scansionino al primo tentativo!

## Cosa Dovresti Imparare Dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare ulteriori funzionalità dell'API e a esplorare approcci di implementazione alternativi nei tuoi progetti.

- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}