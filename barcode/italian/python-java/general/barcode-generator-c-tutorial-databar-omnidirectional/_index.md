---
category: general
date: 2026-11-14
description: Tutorial C# sul generatore di codici a barre che mostra come creare codici
  a barre DataBar Omnidirectional, impostare la dimensione X e regolare l'altezza
  delle barre in pixel.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c# tutorial
- DataBar Omnidirectional
- set bar height
- XDimension pixels
- BarCodeImageFormat PNG
language: it
lastmod: 2026-11-14
og_description: Il tutorial C# sul generatore di codici a barre spiega passo passo
  come generare un codice a barre DataBar Omnidirectional, definire la XDimension
  in pixel e modificare l’altezza delle barre per l’output PNG.
og_image_alt: Screenshot of barcode generator C# tutorial output showing a DataBar
  barcode
og_title: Generatore di codici a barre C# tutorial – crea codici a barre DataBar
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Barcode generator C# tutorial that shows how to create DataBar Omnidirectional
    barcodes, set X‑dimension, and adjust bar height in pixels.
  headline: 'Barcode generator C# tutorial: DataBar Omnidirectional'
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- tutorial
title: 'Generatore di codici a barre C# tutorial: DataBar omnidirezionale'
url: /it/python-java/general/barcode-generator-c-tutorial-databar-omnidirectional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tutorial generatore di codici a barre C# – crea codici DataBar Omnidirectional

Se stai cercando un **barcode generator C# tutorial**, sei nel posto giusto. Questa guida ti accompagna nella creazione di un codice DataBar Omnidirectional, nella configurazione della XDimension in pixel e nella regolazione dell'altezza delle barre per generare immagini PNG.

Vedrai un esempio completo e eseguibile che copre tutto, dall'inizializzazione del generatore al salvataggio di più immagini con altezze delle barre diverse. Non è necessaria alcuna documentazione esterna—basta copiare il codice, eseguirlo e avrai due file di codici a barre pronti all'uso.

## Prerequisiti

* .NET 6.0 o versioni successive installate  
* Un riferimento alla libreria di codici a barre che fornisce `BarcodeGenerator`, `EncodeTypes` e `BarCodeImageFormat` (ad esempio, Aspose.BarCode per .NET)  
* Familiarità di base con la sintassi C# e Visual Studio o il tuo IDE preferito  

> **Suggerimento:** Se stai usando Aspose.BarCode, aggiungi il pacchetto NuGet `Aspose.BarCode` al tuo progetto.

## Tutorial generatore di codici a barre C# – passo 1: crea il generatore

Il primo passo è istanziare un `BarcodeGenerator` con il tipo di codifica `DatabarOmniDirectional` e i dati che desideri codificare.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Omnidirectional barcode generator with the desired data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

*Perché è importante:* `EncodeTypes.DatabarOmniDirectional` indica alla libreria di produrre un codice a barre leggibile da qualsiasi direzione, ideale per imballaggi al dettaglio e logistica.

## Imposta i pixel XDimension per il codice a barre

La X‑dimension definisce la larghezza del modulo più piccolo (il “pixel”) nel codice a barre. Impostarla in pixel ti offre un controllo preciso sulla densità visiva del codice.

```csharp
        // Step 2: Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Spiegazione:* Un valore di `2` pixel produce un codice a barre sufficientemente nitido per la maggior parte degli scanner, mantenendo al contempo una dimensione del file immagine contenuta.

## Regola l'altezza delle barre e salva le immagini

L'altezza delle barre determina quanto alte appaiono le barre. Puoi generare più immagini con altezze diverse modificando la proprietà `BarHeight.Pixels` e richiamando nuovamente `Save`.

```csharp
        // Step 3: Set the bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        string outputPath = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
```

Il valore enum `BarCodeImageFormat.Png` garantisce che l'output sia un file PNG senza perdita, il formato consigliato per le grafiche dei codici a barre perché preserva le dimensioni esatte.

## Cambia l'altezza delle barre per creare più immagini

Spesso è necessario lo stesso codice a barre in dimensioni diverse—ad esempio, uno per un'etichetta piccola e un altro per un grande poster. Cambia l'altezza delle barre e riutilizza la stessa istanza del generatore:

```csharp
        // Step 4: Change the bar height to 60 px and save a second image
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        outputPath = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
    }
}
```

*Caso limite:* Se l'altezza delle barre è impostata troppo bassa (ad esempio, inferiore a 10 px), alcuni scanner potrebbero avere difficoltà a leggere il codice. Testa sempre le immagini generate con l'hardware scanner di destinazione.

## Codice sorgente completo

Di seguito trovi il programma completo da copiare‑incollare in un nuovo progetto console. Include tutte le direttive `using` necessarie e dimostra entrambe le variazioni di altezza delle barre.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a DataBar Omnidirectional barcode generator
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Set XDimension to 2 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image – 30 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
            generator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 30 px barcode to {path30}");

            // Second image – 60 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
            generator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 60 px barcode to {path60}");
        }
    }
}
```

Esegui il programma, sostituisci `YOUR_DIRECTORY` con un percorso di cartella valido, e troverai due file PNG:

* `DatabarBarHeight30Pixels.png` – barre alte 30 px  
* `DatabarBarHeight60Pixels.png` – barre alte 60 px  

![output del tutorial generatore di codici a barre C#](images/databar-example.png "Tutorial generatore di codici a barre C# che mostra due immagini DataBar")

## Domande frequenti

| Domanda | Risposta |
|----------|--------|
| **Posso cambiare il formato dell'immagine?** | Sì. Sostituisci `BarCodeImageFormat.Png` con `Jpeg`, `Bmp` o `Gif` secondo necessità. PNG è preferito per la qualità senza perdita. |
| **E se ho bisogno di una XDimension diversa?** | Regola `generator.Parameters.Barcode.XDimension.Pixels` a qualsiasi intero. Valori più grandi aumentano la larghezza complessiva del codice a barre. |
| **Il DataBar Omnidirectional è adatto alla scansione mobile?** | Sì, a condizione che le dimensioni stampate soddisfino la dimensione minima del modulo dello scanner (di solito 0,33 mm). La XDimension basata sui pixel ti aiuta a rispettare tale requisito. |
| **Come inserisco il codice a barre in un PDF?** | Dopo aver salvato il PNG, utilizza una libreria PDF (ad esempio, iTextSharp) per inserire l'immagine in una pagina PDF. |

## Conclusione

Questo **barcode generator C# tutorial** ti ha mostrato come creare un codice DataBar Omnidirectional, impostare la XDimension in pixel e generare file PNG con altezze delle barre diverse. Ora disponi di uno snippet di codice riutilizzabile che puoi adattare a qualsiasi progetto C# che richieda la creazione di codici a barre.

### Cosa fare dopo?

* Esplora altri `EncodeTypes` come `Code128` o `QR` per ampliare il tuo repertorio di codici a barre.  
* Combina il PNG generato con una libreria di generazione PDF per produrre fatture stampabili.  
* Sperimenta con `generator.Parameters.Barcode.Color` per aggiungere colori personalizzati rispettando le specifiche degli scanner.

Sentiti libero di modificare l'esempio, provare altezze delle barre aggiuntive o cambiare il formato di output. Buon coding!

## Cosa dovresti imparare dopo?

I seguenti tutorial trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come impostare la larghezza e regolare l'altezza per un codice GS1 DataBar Omni‑Directional](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [Come impostare l'altezza del codice a barre, generare un codice DataBar in C#](/barcode/english/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/)
- [Come creare un codice Databar omnidirezionale in C#](/barcode/english/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}