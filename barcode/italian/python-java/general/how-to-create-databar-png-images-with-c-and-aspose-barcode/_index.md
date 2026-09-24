---
category: general
date: 2026-08-19
description: Crea file PNG databar in C# con Aspose.BarCode. Scopri come generare
  immagini databar, configurare i parametri databar e salvare l'output PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar png
- how to generate databar
- configure databar parameters
language: it
lastmod: 2026-08-19
og_description: Crea file PNG databar in C# usando Aspose.BarCode. Questo tutorial
  ti guida nella generazione di immagini databar, nella configurazione dei parametri
  databar come la dimensione X e il rapporto d'aspetto, e nel salvataggio di file
  PNG ad alta qualità per la stampa o l'uso web.
og_image_alt: create databar PNG example
og_title: Crea immagini PNG databar in C# – guida passo passo
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Create databar PNG files in C# with Aspose.BarCode. Learn how to generate
    databar images, configure databar parameters, and save PNG output.
  headline: How to create databar PNG images with C# and Aspose.BarCode
  type: TechArticle
tags:
- barcode
- databar
- C#
- PNG
- Aspose.BarCode
title: Come creare immagini PNG databar con C# e Aspose.BarCode
url: /it/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare immagini PNG databar con C# e Aspose.BarCode

Se hai bisogno di **creare file PNG databar** in un'applicazione .NET, questa guida ti mostra esattamente come fare. Vedrai un esempio completo e eseguibile che genera codici DataBar impilati omnidirezionali, configura i parametri chiave e salva due file PNG con diversi rapporti di aspetto.

Generare un'immagine DataBar non consiste solo nel chiamare un singolo metodo. Devi anche **configurare i parametri databar** come la X‑dimension (larghezza del modulo) e il rapporto di aspetto per soddisfare le specifiche di stampa o scansione. Alla fine di questo tutorial comprenderai **come generare grafica databar** che funziona in modo affidabile in scenari reali.

## Prerequisiti

- .NET 6.0 o versioni successive (il codice funziona anche con .NET Framework 4.7+)
- Visual Studio 2022 o qualsiasi IDE compatibile con C#
- Una licenza valida per **Aspose.BarCode for .NET** (la valutazione gratuita è sufficiente per i test)
- Familiarità di base con la sintassi C#

> **Consiglio:** Se non hai ancora una licenza, puoi richiedere una chiave di valutazione temporanea dal portale Aspose. L'API si comporta allo stesso modo; solo la filigrana cambia.

## Passo 1: Installa il pacchetto NuGet Aspose.BarCode

Apri il tuo progetto in Visual Studio, fai clic con il tasto destro sulla soluzione e seleziona **Manage NuGet Packages**. Cerca `Aspose.BarCode` e installa l'ultima versione stabile.

```bash
dotnet add package Aspose.BarCode
```

Questo comando aggiunge l'assembly `Aspose.BarCode` al tuo progetto e rende disponibile la classe `BarcodeGenerator`.

## Passo 2: Inizializza il generatore di codici a barre per un DataBar impilato omnidirezionale

Il costruttore `BarcodeGenerator` riceve due argomenti: il tipo di codice a barre e la stringa di dati grezzi. Per un DataBar impilato omnidirezionale si utilizza `EncodeTypes.DatabarStackedOmniDirectional`.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace DatabarPngDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Initialize the generator with the desired DataBar type
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // GS1 Application Identifier for a 14‑digit GTIN
```

**Perché è importante:** La costante `EncodeTypes.DatabarStackedOmniDirectional` indica alla libreria di produrre un codice a barre leggibile da qualsiasi orientamento, ideale per le etichette sugli scaffali dei negozi.

## Passo 3: Configura la X‑dimension (larghezza del modulo) in pixel

La X‑dimension controlla la dimensione dell'elemento barra più piccolo. Impostarla in pixel ti offre un controllo preciso sulla dimensione finale dell'immagine.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Un valore di **2 pixel** è un buon compromesso tra leggibilità e compattezza per la maggior parte delle stampanti di etichette. Regola questo valore se ti servono moduli più grandi o più piccoli.

## Passo 4: Imposta il primo rapporto di aspetto e salva il PNG

Il rapporto di aspetto influenza l'altezza del DataBar impilato. Un rapporto di aspetto di **15** produce un codice a barre relativamente corto, mentre **30** lo rende più alto.

```csharp
            // Step 4: Set an aspect ratio of 15 and save the image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Il metodo `Save` scrive il codice a barre generato in un file PNG. PNG è senza perdita, il che preserva i bordi nitidi richiesti dagli scanner di codici a barre.

## Passo 5: Cambia il rapporto di aspetto e salva un secondo PNG

Puoi riutilizzare la stessa istanza `BarcodeGenerator` per produrre variazioni semplicemente cambiando il rapporto di aspetto.

```csharp
            // Step 5: Change the aspect ratio to 30 and save a new image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        }
    }
}
```

Ora hai due file PNG—`DatabarAspectRatio15.png` e `DatabarAspectRatio30.png`—ognuno con una diversa densità visiva.

## Passo 6: Verifica l'output

Apri i file PNG generati in qualsiasi visualizzatore di immagini. Dovresti vedere un codice DataBar pulito e ad alto contrasto. La scansione delle immagini con uno scanner di codici a barre per smartphone conferma che entrambi i rapporti di aspetto decodificano il valore GTIN originale `12345678901231`.

![crea esempio PNG databar](databar_example.png)

*L'immagine sopra mostra i due file PNG affiancati. L'immagine di sinistra utilizza il rapporto di aspetto 15, quella di destra utilizza il rapporto di aspetto 30.*

## Variazioni comuni e casi limite

| Scenario | Cosa modificare | Motivo |
|----------|----------------|--------|
| **Dati diversi** | Sostituisci la stringa `(01)12345678901231` con qualsiasi identificatore di applicazione GS1 valido e dati | Ti consente di codificare ID prodotto, numeri di serie, ecc. |
| **Risoluzione più alta** | Aumenta `XDimension.Pixels` a 3 o 4 | Necessario quando il codice a barre verrà stampato in grandi dimensioni o scansionato da una distanza. |
| **Altri tipi di DataBar** | Usa `EncodeTypes.DatabarStacked` o `EncodeTypes.DatabarExpanded` | Scegli il tipo che meglio si adatta al layout della tua etichetta. |
| **Sfondo trasparente** | Passa `BarCodeImageFormat.Png` con `barcodeGenerator.Save(..., BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })` | Utile per sovrapporre il codice a barre su etichette colorate. |

> **Attenzione:** Impostare una X‑dimension troppo piccola (< 1 pixel) può produrre un codice a barre che appare sfocato dopo

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come generare e regolare l'altezza del codice a barre One-Dimensional Databar usando Aspose.BarCode per .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Creare codifica GS1 One-Dimensional Databar con Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Generare codice a barre Databar Aspose.BarCode usando l'API .NET – Configurazione di righe e colonne](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}