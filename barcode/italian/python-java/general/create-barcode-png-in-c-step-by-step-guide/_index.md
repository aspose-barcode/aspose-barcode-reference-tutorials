---
category: general
date: 2026-08-03
description: Crea un PNG di codice a barre in C# e impara come modificare il rapporto
  d'aspetto per le immagini DataBar. Segui questo esempio completo con codice e consigli.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode PNG
- how to change aspect ratio
- Aspose.BarCode C#
- DataBar stacked omnidirectional
- barcode image format PNG
language: it
lastmod: 2026-08-03
og_description: Crea un PNG di codice a barre in C# e scopri come modificare il rapporto
  d'aspetto per i codici a barre DataBar. Questa guida ti fornisce codice pronto all'uso
  e consigli pratici.
og_image_alt: Sample barcode PNG generated with aspect ratio 15
og_title: Crea PNG di codice a barre in C# – esempio completo con controllo del rapporto
  d'aspetto
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  headline: Create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  name: Create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: How to change other visual properties?
    text: 'You can adjust foreground color, background color, or add human‑readable
      text through the `generator.Parameters.Barcode` object. For example:'
  - name: What if I need a different image format?
    text: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as needed.
      PNG remains the best choice for lossless barcode images.
  - name: Does the aspect ratio affect scanning speed?
    text: Higher aspect ratios increase the barcode’s height, which can improve scan
      reliability on devices that struggle with short stacked symbols. However, extremely
      tall barcodes may not fit on small labels, so test with your target hardware.
  - name: Can I generate multiple barcodes in a loop?
    text: Yes. Create a new `BarcodeGenerator` instance for each data string or reuse
      the same instance while updating `CodeText` and `DataBar.AspectRatio`. This
      approach reduces object allocation overhead.
  type: HowTo
tags:
- barcode
- C#
- PNG
- Aspose
title: Crea PNG di codice a barre in C# – guida passo passo
url: /it/python-java/general/create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Creare barcode PNG in C# – guida passo‑passo

Se hai bisogno di **creare barcode PNG** in C#, questo tutorial ti mostra esattamente come fare. Genererai un barcode DataBar omnidirezionale impilato, lo salverai come file PNG e imparerai **come modificare il rapporto d'aspetto** per adattarlo a diversi ambienti di scansione.

La guida copre tutto ciò di cui hai bisogno: pacchetti richiesti, un programma completo e eseguibile, e spiegazioni sul perché ogni impostazione è importante. Alla fine avrai due file PNG—uno con un rapporto d'aspetto di 15 e un altro con 30—pronti per test o utilizzo in produzione.

## Prerequisiti

Prima di iniziare, assicurati di avere:

- .NET 6.0 SDK o versioni successive installate
- Visual Studio 2022 (o qualsiasi IDE per C#)
- Un riferimento NuGet a **Aspose.BarCode** (la libreria che fornisce `BarcodeGenerator`)
- Permessi di scrittura nella directory in cui verranno salvati i file PNG

Puoi aggiungere il pacchetto Aspose.BarCode con il seguente comando:

```bash
dotnet add package Aspose.BarCode
```

## Passo 1: Configurare il progetto e importare i namespace

Crea una nuova applicazione console e importa i namespace necessari per la generazione del barcode e per l'I/O dei file.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodePngDemo
{
    class Program
    {
        static void Main()
        {
            // All subsequent steps are inside Main
```

**Perché è importante:** Importare `Aspose.BarCode.Generation` ti dà accesso a `BarcodeGenerator`. Tenere il codice all'interno di `Main` rende l'esempio autonomo e facile da eseguire.

## Passo 2: Creare un generatore di barcode per un DataBar omnidirezionale impilato

Istanzia `BarcodeGenerator` con il tipo `EncodeTypes.DatabarStackedOmniDirectional` e una stringa di dati di esempio GS1‑128.

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");
```

**Perché è importante:** Il tipo di codifica scelto produce un DataBar ad alta densità che può essere letto dalla maggior parte degli scanner moderni. La stringa di dati segue il formato dell'Identificatore di Applicazione GS1 (01), comune per gli identificatori di prodotto.

## Passo 3: Definire la X‑dimension (larghezza del modulo) in pixel

Imposta la larghezza del modulo per controllare le dimensioni complessive del barcode senza influire sulla leggibilità.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Perché è importante:** Una X‑dimension di 2 pixel produce un barcode né troppo piccolo per gli scanner né troppo grande per gli spazi tipici delle etichette.

## Passo 4: Salvare il primo PNG con un rapporto d'aspetto di 15

Regola il rapporto d'aspetto del DataBar, quindi salva l'immagine come file PNG.

```csharp
            // Step 4: Set the DataBar aspect ratio to 15 and save the image
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;
            string outputPath15 = @"YOUR_DIRECTORY\DatabarAspectRatio15.png";
            generator.Save(outputPath15, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath15} (aspect ratio 15).");
```

**Perché è importante:** Il rapporto d'aspetto controlla la relazione altezza‑larghezza del DataBar impilato. Un rapporto di 15 è un valore predefinito comune che bilancia leggibilità e altezza dell'etichetta.

## Passo 5: Cambiare il rapporto d'aspetto a 30 e salvare un secondo PNG

Modifica la stessa istanza del generatore per utilizzare un rapporto d'aspetto più grande, quindi salva la seconda immagine.

```csharp
            // Step 5: Change the aspect ratio to 30 and save another image
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string outputPath30 = @"YOUR_DIRECTORY\DatabarAspectRatio30.png";
            generator.Save(outputPath30, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath30} (aspect ratio 30).");
        }
    }
}
```

**Perché è importante:** Aumentare il rapporto d'aspetto allunga il barcode verticalmente, il che può migliorare l'affidabilità della scansione su dispositivi a bassa risoluzione o quando l'etichetta è stampata su supporti stretti.

## Output previsto

L'esecuzione del programma crea due file PNG:

| File                               | Rapporto d'aspetto | Dimensioni approssimative (pixel) |
|------------------------------------|--------------------|-----------------------------------|
| `DatabarAspectRatio15.png`         | 15                 | 200 × 300 (larghezza × altezza)   |
| `DatabarAspectRatio30.png`         | 30                 | 200 × 600 (larghezza × altezza)   |

Entrambe le immagini contengono un barcode DataBar chiaro e leggibile che codifica l'identificatore GS1 `(01)12345678901231`.

## Domande comuni e casi limite

### Come cambiare altre proprietà visive?

Puoi regolare il colore di primo piano, il colore di sfondo o aggiungere testo leggibile dall'uomo tramite l'oggetto `generator.Parameters.Barcode`. Per esempio:

```csharp
generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
generator.Parameters.Barcode.CodeTextParameters.ShowCodeText = true;
```

### E se avessi bisogno di un formato immagine diverso?

Sostituisci `BarCodeImageFormat.Png` con `Jpeg`, `Bmp` o `Gif` secondo necessità. PNG rimane la scelta migliore per immagini barcode senza perdita.

### Il rapporto d'aspetto influisce sulla velocità di scansione?

Rapporti d'aspetto più alti aumentano l'altezza del barcode, il che può migliorare l'affidabilità della scansione su dispositivi che hanno difficoltà con simboli impilati corti. Tuttavia, barcode estremamente alti potrebbero non stare su etichette piccole, quindi è consigliabile testare con l'hardware di destinazione.

### Posso generare più barcode in un ciclo?

Sì. Crea una nuova istanza di `BarcodeGenerator` per ogni stringa di dati o riutilizza la stessa istanza aggiornando `CodeText` e `DataBar.AspectRatio`. Questo approccio riduce il sovraccarico di allocazione degli oggetti.

## Suggerimenti professionali

- **Riutilizza il generatore**: Modificare solo `CodeText` o `AspectRatio` evita di reinizializzare l'oggetto, velocizzando l'elaborazione in batch.
- **Convalida l'output**: Usa uno scanner portatile o un'app mobile per confermare che il PNG generato venga letto correttamente prima di distribuirlo in produzione.
- **Denominazione dei file**: Includi il rapporto d'aspetto nel nome del file (come mostrato) per tenere traccia delle variazioni durante i test.

## Conclusione

Ora sai come **creare barcode PNG** in C# e precisamente **come modificare il rapporto d'aspetto** per i simboli DataBar omnidirezionali impilati. L'esempio completo dimostra l'inizializzazione, l'impostazione della X‑dimension, la manipolazione del rapporto d'aspetto e il salvataggio dell'immagine—tutto in un unico programma eseguibile.

Da qui puoi esplorare altri tipi di barcode, sperimentare con i colori o integrare il generatore in un sistema più ampio di reporting o gestione inventario. Buona programmazione!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Customize Barcode - Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}