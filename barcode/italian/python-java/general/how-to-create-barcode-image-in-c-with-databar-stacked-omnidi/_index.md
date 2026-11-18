---
category: general
date: 2026-11-17
description: Crea un’immagine di codice a barre in C# usando la libreria Barcode Generator.
  Segui questa guida per imparare a generare codici DataBar stacked omnidirectional
  passo dopo passo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- how to generate databar
language: it
lastmod: 2026-11-17
og_description: Crea un'immagine di codice a barre in C# con un esempio conciso. Scopri
  come generare codici a barre DataBar stacked omnidirectional usando la libreria
  Barcode Generator.
og_image_alt: Screenshot showing a generated barcode image created with C# code
og_title: Crea immagine di codice a barre in C# – guida completa per i codici DataBar
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Create barcode image in C# using the Barcode Generator library. Follow
    this guide to learn how to generate DataBar stacked omnidirectional codes step‑by‑step.
  headline: How to create barcode image in C# with DataBar stacked omnidirectional
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Come creare un'immagine di codice a barre in C# con DataBar stacked omnidirezionale
url: /it/python-java/general/how-to-create-barcode-image-in-c-with-databar-stacked-omnidi/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un'immagine di codice a barre in C# con DataBar impilato omnidirezionale

Se hai bisogno di **create barcode image** in un'applicazione .NET, questo tutorial ti mostra una soluzione completa, pronta all'uso. Vedrai esattamente come utilizzare l'API **Barcode Generator C#** per produrre un DataBar impilato omnidirezionale, il formato trattato nella query *how to generate databar*.

La guida percorre tutti i passaggi necessari—dall'installazione della libreria alla messa a punto del rapporto d'aspetto—così potrai copiare il codice, eseguirlo e ottenere immediatamente un file PNG. Non è necessario consultare documentazione esterna.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6.0 SDK o versioni successive installate (il campione funziona anche con .NET Framework 4.7+)
* Un ambiente di sviluppo come Visual Studio 2022 o VS Code
* Il pacchetto NuGet **Aspose.BarCode for .NET** (la libreria che fornisce `BarcodeGenerator`)

Puoi aggiungere il pacchetto con il seguente comando:

```bash
dotnet add package Aspose.BarCode
```

> **Suggerimento:** Usa il flag `--version` per bloccare il pacchetto all'ultima versione stabile, ad es. `dotnet add package Aspose.BarCode --version 23.9`.

## Passo 1: Configura il progetto e importa i namespace

Crea un nuovo progetto console e aggiungi i namespace richiesti. Questo passaggio prepara l'ambiente per il codice **barcode generator c#** che segue.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // All barcode generation logic lives here
```

Il namespace `Aspose.BarCode.Generation` contiene la classe `BarcodeGenerator`, che è il fulcro del flusso di lavoro **create barcode image**.

## Passo 2: Inizializza il BarcodeGenerator per un DataBar impilato omnidirezionale

Il generatore necessita di due informazioni: il tipo di codice a barre e i dati da codificare. Il valore enum `EncodeTypes.DatabarStackedOmniDirectional` seleziona la variante DataBar esatta richiesta negli scenari *how to generate databar*.

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // Example GTIN-14 payload
```

*Perché è importante:* Selezionare il valore corretto di `EncodeTypes` garantisce che l'immagine risultante rispetti le specifiche di settore per la scansione al dettaglio.

## Passo 3: Definisci la dimensione del modulo (X‑dimension) in pixel

La densità visiva di un codice a barre è controllata dalla X‑dimension. Impostarla a un valore pixel sensato assicura che l'immagine sia leggibile sia su schermo che su stampa.

```csharp
            // Step 3: Define the module size (X‑dimension) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Se ti serve un codice a barre più grande per stampe a bassa risoluzione, aumenta di conseguenza il valore in pixel.

## Passo 4: Regola il rapporto d'aspetto del DataBar per rendere le righe più alte

Il DataBar impilato omnidirezionale è composto da due righe. Modificando `AspectRatio` puoi controllare l'altezza di ciascuna riga, utile quando le dimensioni predefinite risultano troppo compresse.

```csharp
            // Step 4: Adjust the DataBar aspect ratio to make rows taller
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

Un rapporto d'aspetto di `15` è una scelta comune per le etichette al dettaglio; puoi sperimentare valori tra `10` e `20` per soddisfare requisiti di layout specifici.

## Passo 5: Salva il codice a barre generato come immagine PNG

Infine, scrivi l'immagine su disco. PNG è lossless, il che lo rende ideale per ulteriori elaborazioni o per l'inserimento in PDF.

```csharp
            // Step 5: Save the generated barcode as a PNG image
            string outputPath = "DatabarAspectRatio15.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to {outputPath}");
        }
    }
}
```

L'esecuzione del programma produce un file chiamato **DatabarAspectRatio15.png** nella directory di output del progetto. Aprendo il file vedrai un codice a barre pulito, ad alto contrasto, pronto per la scansione.

### Output previsto

L'immagine salvata è simile all'illustrazione qui sotto (l'effettiva visuale è omessa per brevità).

*Testo alternativo per l'immagine di esempio:* **create barcode image** – un file PNG che mostra un DataBar impilato omnidirezionale con un rapporto d'aspetto di 15.

## Variazioni comuni e casi limite

| Situazione | Regolazione |
|------------|-------------|
| **Lunghezza del payload diversa** | Sostituisci la stringa GTIN con qualsiasi contenuto DataBar valido (es., `(01)01234567890123`). |
| **Risoluzione più alta per stampe grandi** | Aumenta `XDimension.Pixels` a 4 o 5 e opzionalmente imposta `Resolution` in `Parameters.Image`. |
| **Altri formati DataBar** | Usa `EncodeTypes.DatabarStacked` per una variante a due righe impilata senza capacità omnidirezionale. |
| **Salvataggio come JPEG** | Cambia `BarCodeImageFormat.Png` in `BarCodeImageFormat.Jpeg` e opzionalmente imposta `Quality`. |

Queste variazioni rispondono alla più ampia domanda *how to generate databar* mostrando come lo stesso generatore possa essere riconfigurato per più famiglie DataBar.

## Riepilogo del codice sorgente completo

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // Define the module size (X‑dimension) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Adjust the DataBar aspect ratio to make rows taller
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;

            // Save the generated barcode as a PNG image
            string outputPath = "DatabarAspectRatio15.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to {outputPath}");
        }
    }
}
```

Copia il codice in `Program.cs`, ripristina i pacchetti NuGet ed esegui `dotnet run`. La console confermerà la posizione dell'immagine e potrai aprire il PNG per verificare il risultato **create barcode image**.

## Conclusione

Ora sai come **create barcode image** in C# usando la libreria Barcode Generator e come **generate DataBar** con controllo preciso su dimensione e rapporto d'aspetto. L'esempio completo dimostra ogni impostazione necessaria—dall'inizializzazione di `BarcodeGenerator` all'esportazione di un file PNG—così da poter integrare la creazione di codici a barre in qualsiasi applicazione .NET senza ulteriori ricerche.

### Cosa fare dopo?

* Esplora altre simbologie di codici a barre con `EncodeTypes` (es., QR, Code128) – un'estensione naturale del flusso di lavoro **barcode generator c#**.
* Combina l'immagine generata con report PDF o Excel usando Aspose.PDF o Aspose.Cells.
* Regola colore, aggiungi margini o incorpora il codice a barre in un'API web per la generazione on‑demand.

Sentiti libero di sperimentare con i parametri, e lascia che il codice sia una base affidabile per tutti i tuoi futuri progetti legati ai codici a barre. Buona programmazione!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come usare un generatore di codici a barre C# per creare codici DataBar](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)
- [Come usare un generatore di codici a barre C# per creare codici DataBar omnidirezionali](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [Come creare un codice a barre DataBar impilato in C# – guida passo‑passo](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}