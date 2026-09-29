---
category: general
date: 2026-09-29
description: Scopri come creare un codice a barre Databar omnidirezionale in C# con
  Aspose.BarCode. Regola la dimensione X, imposta il rapporto d'aspetto e salva le
  immagini PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional databar barcode
- DataBar stacked omnidirectional barcode
- set barcode aspect ratio
- Aspose.BarCode C#
- generate barcode image
language: it
lastmod: 2026-09-29
og_description: Crea un codice a barre Databar omnidirezionale in C# usando Aspose.BarCode.
  Impara a impostare la dimensione X, regolare il rapporto d'aspetto e esportare file
  PNG.
og_image_alt: Screenshot showing two PNG files of an omnidirectional Databar barcode
  with different aspect ratios
og_title: Crea un codice a barre Databar omnidirezionale in C# – guida passo passo
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  headline: How to create omnidirectional Databar barcode in C#
  type: TechArticle
- description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  name: How to create omnidirectional Databar barcode in C#
  steps:
  - name: What if I need a different X‑dimension?
    text: You can assign any integer value to `XDimension.Pixels`. Values below `1`
      are ignored, and values above `10` may produce oversized modules that exceed
      printer margins. Test the visual output after each change.
  - name: How do I encode other AI‑generated data (e.g., UPC, EAN)?
    text: Replace the data string in the `BarcodeGenerator` constructor with the appropriate
      Application Identifier (AI). For a UPC‑A code, use `"012345678905"` without
      an AI prefix.
  - name: Can I export to formats other than PNG?
    text: Yes. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`,
      `BarCodeImageFormat.Tiff`, and `BarCodeImageFormat.Bmp`. Choose the format that
      matches your downstream workflow.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Come creare un codice a barre Databar omnidirezionale in C#
url: /it/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un codice a barre Databar omnidirezionale in C#

Se hai bisogno di **creare un codice a barre Databar omnidirezionale** in un'applicazione .NET, questa guida ti mostra i passaggi esatti. Vedrai come inizializzare un codice a barre DataBar stacked omnidirectional, configurare la sua X‑dimension, modificare il rapporto d'aspetto e generare immagini PNG con Aspose.BarCode.

Generare un **DataBar stacked omnidirectional barcode** è comune quando devi codificare identificatori di prodotto per scanner al dettaglio. In questo tutorial imparerai a **impostare il rapporto d'aspetto del codice a barre**, controllare la dimensione del modulo e esportare il risultato senza uscire dall'IDE.

## Prerequisiti

- .NET 6.0 o versioni successive installate
- Visual Studio 2022 (o qualsiasi IDE compatibile con C#)
- Il pacchetto NuGet **Aspose.BarCode for .NET** (versione 23.12 o successiva)

Puoi aggiungere il pacchetto tramite il NuGet Package Manager:

```bash
dotnet add package Aspose.BarCode
```

## Passo 1: Inizializzare il codice a barre Databar omnidirezionale

Il primo passo è creare un'istanza di `BarcodeGenerator` che utilizza la simbologia **DataBar stacked omnidirectional**. Il costruttore riceve il tipo di codifica e la stringa dei dati.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialise a DataBar stacked omnidirectional barcode with GTIN data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Perché è importante:** Il valore `EncodeTypes.DatabarStackedOmniDirectional` indica ad Aspose.BarCode di renderizzare il formato Databar omnidirezionale specifico, necessario per la scansione in entrambe le direzioni.

## Passo 2: Definire la X‑dimension (dimensione del modulo)

La X‑dimension controlla la larghezza di un singolo modulo del codice a barre in pixel. Un valore di `2` pixel funziona bene per il rendering su schermo e per la maggior parte delle stampanti.

```csharp
        // Set the basic size of the barcode modules (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Perché è importante:** Una X‑dimension costante garantisce che il codice a barre soddisfi le specifiche di dimensione minima per gli scanner al dettaglio, mantenendo al contempo la dimensione del file immagine gestibile.

## Passo 3: Impostare il primo rapporto d'aspetto e salvare l'immagine

Il **rapporto d'aspetto** determina la relazione altezza‑larghezza del DataBar. Un rapporto d'aspetto di `15` produce un codice a barre compatto e alto, ideale per spazi etichetta stretti.

```csharp
        // Apply aspect ratio 15 and save the first PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Perché è importante:** Regolare il rapporto d'aspetto ti consente di adattare il codice a barre a diversi layout di etichette senza sacrificare la leggibilità. Il PNG salvato può essere visualizzato con qualsiasi visualizzatore di immagini.

## Passo 4: Modificare il rapporto d'aspetto e generare una seconda immagine

A volte è necessario un codice a barre più largo — ad esempio, quando l'etichetta ha più spazio orizzontale. Cambiare il rapporto a `30` crea un aspetto più piatto.

```csharp
        // Change aspect ratio to 30 and save a second PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Perché è importante:** Esporre la proprietà **set barcode aspect ratio** ti permette di produrre più varianti di codice a barre da una singola base di codice, semplificando le pipeline di generazione automatica di etichette.

## Output previsto

Eseguendo il programma vengono prodotti due file PNG nella cartella di output dell'applicazione:

| Nome file | Rapporto d'aspetto | Descrizione visiva |
|--------------------------|--------------|--------------------|
| `DatabarAspectRatio15.png` | 15 | Codice a barre alto e stretto adatto a etichette strette |
| `DatabarAspectRatio30.png` | 30 | Codice a barre più largo che riempie più spazio orizzontale |

![Esempio di creazione di codice a barre Databar omnidirezionale](databar-example.png "Esempio di creazione di codice a barre Databar omnidirezionale")

*Lo screenshot mostra i due file PNG generati affiancati.*

## Domande comuni e casi particolari

### E se avessi bisogno di una X‑dimension diversa?

Puoi assegnare qualsiasi valore intero a `XDimension.Pixels`. I valori inferiori a `1` vengono ignorati, e i valori superiori a `10` possono produrre moduli troppo grandi che superano i margini della stampante. Testa l'output visivo dopo ogni modifica.

### Come codifico altri dati generati da AI (ad es., UPC, EAN)?

Sostituisci la stringa dei dati nel costruttore `BarcodeGenerator` con l'Application Identifier (AI) appropriato. Per un codice UPC‑A, usa `"012345678905"` senza prefisso AI.

### Posso esportare in formati diversi da PNG?

Sì. Il metodo `Save` accetta `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`, `BarCodeImageFormat.Tiff` e `BarCodeImageFormat.Bmp`. Scegli il formato che corrisponde al tuo flusso di lavoro successivo.

## Suggerimento professionale: riutilizzare il generatore per l'elaborazione batch

Se devi generare decine di codici a barre con rapporti d'aspetto variabili, mantieni viva l'istanza `BarcodeGenerator` e modifica solo `DataBar.AspectRatio` prima di ogni `Save`. Questo evita l'overhead di ricreare il generatore per ogni immagine.

```csharp
var ratios = new[] { 10, 15, 20, 30 };
foreach (var ratio in ratios)
{
    generator.Parameters.Barcode.DataBar.AspectRatio = ratio;
    generator.Save($"DatabarAspectRatio{ratio}.png", BarCodeImageFormat.Png);
}
```

## Conclusione

Ora sai come **creare un codice a barre Databar omnidirezionale** in C# usando Aspose.BarCode. Inizializzando un `BarcodeGenerator`, impostando la X‑dimension, regolando il **set barcode aspect ratio**, e salvando file PNG, puoi produrre immagini di codici a barre che soddisfano diversi requisiti di etichettatura.  

Successivamente, esplora argomenti correlati come **generate barcode image** per codici QR, la validazione del **DataBar stacked omnidirectional barcode**, o l'integrazione dei PNG generati in fatture PDF con Aspose.PDF. Sperimenta con diversi rapporti d'aspetto e dimensioni dei moduli per trovare la configurazione ottimale per la tua specifica attrezzatura di stampa.

---

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come usare un generatore di codici a barre C# per creare codici a barre DataBar omnidirezionali](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [databar stacked omnidirectional barcode in C# – Guida completa](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [Come generare un codice a barre in C# – creare immagine di codice a barre c# con DataBar Expanded](/barcode/english/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}