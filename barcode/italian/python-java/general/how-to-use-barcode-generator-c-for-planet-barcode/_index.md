---
category: general
date: 2026-09-19
description: La guida al generatore di codici a barre C# mostra come generare un codice
  a barre Planet e esportare l'immagine del codice a barre come PNG in poche righe.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- how to generate barcode
- create planet barcode
- export barcode image
language: it
lastmod: 2026-09-19
og_description: Il generatore di codici a barre C# ti consente di creare rapidamente
  un codice a barre Planet e di esportare l'immagine come PNG per qualsiasi app .NET.
og_image_alt: Screenshot of a Planet barcode generated with barcode generator C# showing
  empty bars
og_title: Generatore di codici a barre C# – crea codice a barre Planet ed esporta
  immagine
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator C# guide shows how to generate a Planet barcode and
    export barcode image as PNG in just a few lines.
  headline: How to use barcode generator C# for Planet barcode
  type: TechArticle
tags:
- barcode
- C#
- image export
title: Come usare il generatore di codici a barre C# per il codice a barre Planet
url: /it/python-java/general/how-to-use-barcode-generator-c-for-planet-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come utilizzare il generatore di codici a barre C# per il codice Planet

Se ti serve un **generatore di codici a barre C#** in grado di produrre un codice Planet, questa guida ti offre una soluzione completa. Imparerai **come generare i dati del codice a barre**, personalizzare l'aspetto e **esportare l'immagine del codice a barre** come file PNG con poche righe di codice.

La creazione di codici a barre è una necessità comune per sistemi di inventario, piattaforme di biglietteria e dispositivi IoT. Alla fine di questo tutorial avrai un'applicazione console autonoma che genera un codice Planet pulito, disabilita il riempimento delle barre e salva il risultato su disco. Non sono necessari strumenti esterni oltre alla libreria di codici a barre.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6.0 SDK o versioni successive installate  
* Una libreria di codici a barre compatibile con C# (l'esempio utilizza **Aspose.BarCode for .NET**, che supporta la simbologia Planet)  
* Un IDE o editor come Visual Studio 2022, VS Code o Rider  

La libreria può essere aggiunta tramite NuGet:

```bash
dotnet add package Aspose.BarCode
```

> **Consiglio:** Usa l'ultima versione stabile del pacchetto per beneficiare di correzioni di bug e miglioramenti delle prestazioni.

## Utilizzare il generatore di codici a barre C# per creare un codice Planet

Il primo passo è istanziare il generatore con la simbologia Planet e i dati che desideri codificare.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for the Planet symbology with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

`BarcodeGenerator` è il punto di ingresso per tutte le operazioni sui codici a barre. Il costruttore riceve la simbologia (`EncodeTypes.Planet`) e i dati grezzi (`"123456"`). Questo codice **crea un codice Planet** che può successivamente essere renderizzato come immagine.

## Regolare i parametri del codice a barre

Per controllare la qualità visiva puoi modificare la dimensione X (larghezza del modulo) e decidere se le barre siano riempite.

```csharp
        // Step 2: Adjust the X-dimension (module width) to 4 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 3: Disable filling of the bars so that only the outlines are drawn
        generator.Parameters.Barcode.FilledBars = false;
```

* Impostare `XDimension.Pixels` a **4** produce un codice a barre ad alta risoluzione senza aumentare drasticamente le dimensioni del file.  
* `FilledBars = false` genera uno stile solo contorno, utile quando vuoi che il codice a barre si integri con lo sfondo o quando stampi su dispositivi a basso consumo di inchiostro.

## Esportare l'immagine del codice a barre

Dopo aver configurato il generatore, salva il risultato in un file PNG. Il metodo `Save` accetta un percorso completo e il formato immagine desiderato.

```csharp
        // Step 4: Save the generated barcode image as a PNG file
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "PlanetEmptyBars.png");

        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

Il codice scrive **esporta immagine del codice a barre** `PlanetEmptyBars.png` sul Desktop dell'utente. PNG è un formato lossless che preserva i bordi nitidi del codice a barre, rendendolo ideale sia per la visualizzazione su schermo sia per la stampa ad alta risoluzione.

> **Caso limite:** Se ti serve un formato diverso (JPEG, BMP, GIF), sostituisci `BarCodeImageFormat.Png` con il valore enum appropriato. JPEG introduce artefatti di compressione che possono influire sulla leggibilità da parte dello scanner, quindi usalo solo quando la dimensione del file è un requisito critico.

## Esempio completo, eseguibile

Di seguito trovi il programma completo che puoi copiare, incollare ed eseguire subito.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Create a barcode generator for the Planet symbology with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Adjust the X-dimension (module width) to 4 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 4;

        // Disable filling of the bars so that only the outlines are drawn
        generator.Parameters.Barcode.FilledBars = false;

        // Define the output file path (Desktop folder is used for convenience)
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "PlanetEmptyBars.png");

        // Export the barcode image as a PNG file
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

Quando esegui il programma, dovresti vedere un messaggio simile a:

```
Barcode saved to: C:\Users\YourName\Desktop\PlanetEmptyBars.png
```

L'apertura del file PNG mostra un codice Planet pulito con barre vuote, esattamente come configurato.

![barcode generator C# example](/images/barcode-generator-csharp.png){alt="esempio di generatore di codici a barre C#"}

## Domande frequenti e risoluzione dei problemi

| Domanda | Risposta |
|----------|----------|
| **Posso generare altre simbologie con lo stesso codice?** | Sì. Sostituisci `EncodeTypes.Planet` con qualsiasi tipo supportato, ad esempio `EncodeTypes.Code128` o `EncodeTypes.QR`. |
| **E se il codice a barre non viene letto?** | Verifica che la lunghezza dei dati rispetti la specifica Planet (esattamente 6 caratteri numerici). Assicurati anche di avere un contrasto sufficiente tra il codice a barre e lo sfondo. |
| **Come modifico le dimensioni dell'immagine?** | Regola `generator.Parameters.ImageWidth` e `generator.Parameters.ImageHeight` oppure modifica `XDimension` per scalare il codice a barre proporzionalmente. |
| **È possibile aggiungere una didascalia sotto il codice a barre?** | Usa `generator.Parameters.Barcode.CodeTextVisible = true;` e personalizza `CodeTextParameters` per font, allineamento e margine. |

## Prossimi passi

Ora che hai padroneggiato **come generare immagini di codici a barre** con un **generatore di codici a barre C#**, puoi approfondire:

* Generare file di codici a barre in batch usando un elenco CSV di valori.  
* Incorporare il PNG in fatture PDF con Aspose.PDF.  
* Passare a formati di **esporta immagine del codice a barre** come SVG per grafica web scalabile.  

Queste estensioni approfondiranno la tua comprensione dell'automazione dei codici a barre in .NET e ti prepareranno a scenari di integrazione reali.

---

**Riepilogo:** Questo tutorial ha mostrato un flusso di lavoro completo per un **generatore di codici a barre C#**—creazione di un codice Planet, personalizzazione dell'aspetto e **esportazione dell'immagine del codice a barre** come PNG. Puoi adattare lo stesso modello ad altre simbologie, formati immagine e destinazioni di output. Buona programmazione!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare ulteriori funzionalità dell'API e a esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Barcode generator C# – generate barcode image](/barcode/english/python-java/general/barcode-generator-c-generate-barcode-image/)
- [Create Planet Barcode Image in C# – How to Generate Postal Barcode](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}