---
category: general
date: 2026-09-16
description: Scopri come impostare la larghezza, come creare barre vuote e come riempire
  le barre quando generi il codice a barre Planet usando Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to make empty
- how to fill bars
- generate planet barcode
language: it
lastmod: 2026-09-16
og_description: Come impostare la larghezza, creare barre vuote e riempire le barre
  durante la generazione del codice a barre Planet con Aspose.BarCode – guida completa
  passo‑a‑passo.
og_image_alt: Screenshot showing how to set width for a Planet barcode in C#
og_title: Come impostare la larghezza e generare un codice a barre Planet in C#
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set width, how to make empty bars, and how to fill bars
    when you generate Planet barcode using Aspose.BarCode.
  headline: How to set width and generate a Planet barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Come impostare la larghezza e generare un codice a barre Planet in C#
url: /it/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come impostare la larghezza e generare un codice a barre Planet in C#

Se hai bisogno di **impostare la larghezza** per un codice a barre Planet, questa guida mostra l'intero processo. Vedrai anche **come creare barre vuote**, **come riempire le barre**, e i passaggi esatti per **generare un codice a barre Planet** con Aspose.BarCode per .NET.

Generare un codice a barre Planet in stile postale è comune quando si sviluppano applicazioni per etichette di spedizione o integrazioni con servizi postali. Alla fine di questo tutorial avrai un programma console pronto all'uso che crea sia un'immagine con barre riempite sia un'immagine con barre vuote, entrambe usando la stessa stringa di dati.

## Prerequisiti

- .NET 6.0 SDK o versioni successive (il codice funziona anche con .NET Framework 4.7+)
- Visual Studio 2022 o qualsiasi IDE compatibile con C#
- Pacchetto NuGet Aspose.BarCode per .NET (`Aspose.BarCode`)  
  Installa con:

```bash
dotnet add package Aspose.BarCode
```

Non è necessaria alcuna configurazione aggiuntiva; la libreria gestisce internamente la codifica dell'immagine.

## Passo 1: Creare un progetto console e aggiungere la libreria

Apri un terminale ed esegui:

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
dotnet add package Aspose.BarCode
```

Questo crea un file `Program.cs` dove scriveremo la logica del codice a barre.

## Passo 2: Scrivere il codice – impostare la larghezza e generare il codice a barre Planet

Apri `Program.cs` e sostituisci il suo contenuto con il seguente esempio completo:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Data to encode – the same value is used for both images
        const string data = "123456";

        // -----------------------------------------------------------------
        // Part A: Filled‑bars version (default style)
        // -----------------------------------------------------------------
        // Step 2.1: Create a Planet barcode generator
        var filledGenerator = new BarcodeGenerator(EncodeTypes.Planet, data);

        // Step 2.2: How to set width – define the width of a single bar in pixels
        // The XDimension controls bar width; 4 pixels yields a clear, printable image
        filledGenerator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 2.3: Save the filled‑bars image (default is FilledBars = true)
        string filledPath = "PostalPlanetFilledBars.png";
        filledGenerator.Save(filledPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Filled‑bars barcode saved to {filledPath}");

        // -----------------------------------------------------------------
        // Part B: Empty‑bars version (unfilled style)
        // -----------------------------------------------------------------
        // Step 3.1: Re‑instantiate the generator for the same data
        var emptyGenerator = new BarcodeGenerator(EncodeTypes.Planet, data);

        // Step 3.2: How to set width again – required after re‑instantiation
        emptyGenerator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 3.3: How to make empty – disable the filled‑bars flag
        emptyGenerator.Parameters.Barcode.FilledBars = false;

        // Step 3.4: Save the empty‑bars image
        string emptyPath = "PostalPlanetEmptyBars.png";
        emptyGenerator.Save(emptyPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Empty‑bars barcode saved to {emptyPath}");

        // -----------------------------------------------------------------
        // Verification output
        // -----------------------------------------------------------------
        Console.WriteLine("Both barcodes generated successfully.");
    }
}
```

### Perché ogni passaggio è importante

- **Come impostare la larghezza**: La proprietà `XDimension.Pixels` influenza direttamente la dimensione fisica di ogni barra. Scegliere un valore tra 2 e 6 pixel bilancia la leggibilità sullo schermo e la qualità di stampa.
- **Come creare barre vuote**: Impostare `FilledBars = false` indica al generatore di disegnare solo i contorni delle barre. Questo stile è utile per la stampa “chiaro‑su‑scuro” o quando si desidera che la trama della carta sottostante sia visibile.
- **Come riempire le barre**: Il valore predefinito `FilledBars = true` crea barre nere solide, lo standard per la maggior parte degli scanner postali.
- **Generare codice a barre Planet**: Usare `EncodeTypes.Planet` seleziona la codifica specifica richiesta dal United States Postal Service (USPS) per i codici a barre Planet.

## Passo 3: Compilare ed eseguire il programma

Dalla cartella del progetto esegui:

```bash
dotnet run
```

Dovresti vedere un output della console simile a:

```
Filled‑bars barcode saved to PostalPlanetFilledBars.png
Empty‑bars barcode saved to PostalPlanetEmptyBars.png
Both barcodes generated successfully.
```

Due file PNG compaiono nella directory del progetto:

- `PostalPlanetFilledBars.png` – barre nere solide (stile predefinito)
- `PostalPlanetEmptyBars.png` – barre a contorno (stile vuoto)

Aprili in qualsiasi visualizzatore di immagini per verificare che la larghezza della barra corrisponda all'impostazione di 4 pixel e che la versione vuota mostri barre non riempite.

## Domande comuni e casi particolari

| Domanda | Risposta |
|----------|--------|
| *Posso usare un formato immagine diverso?* | Sì. Sostituisci `BarCodeImageFormat.Png` con `Jpeg`, `Bmp` o `Gif` secondo necessità. |
| *Cosa succede se il codice a barre diventa troppo largo per la mia etichetta?* | Riduci `XDimension.Pixels` (ad es., a `2`) oppure aumenta la larghezza del modulo della stampante di etichette. |
| *Devo impostare manualmente `Height`?* | La libreria calcola automaticamente l'altezza in base alla codifica. Puoi sovrascrivere con `Parameters.Barcode.BarHeight`. |
| *Lo stile a barre vuote è supportato su tutte le stampanti?* | La maggior parte delle stampanti termiche moderne gestisce sia gli stili riempiti che vuoti, ma verifica con una stampa di prova se usi un dispositivo legacy. |
| *Come aggiungere una didascalia leggibile dall'uomo sotto il codice a barre?* | Usa `Parameters.Caption` per abilitare e formattare una didascalia; imposta `CaptionAbove` a `false` per posizionarla sotto. |

## Consigli professionali

- **Riutilizzare lo stesso generatore** solo quando mantieni tutti i parametri identici. Modificare `FilledBars` dopo un salvataggio non influisce sull'immagine già salvata, quindi reinizializzare (come mostrato) garantisce un avvio pulito.
- **Generazione in batch**: Inserisci il codice in un ciclo e cambia `data` ad ogni iterazione per creare una serie di codici a barre Planet per invii massivi.
- **Prestazioni**: Per migliaia di codici a barre, crea un'unica istanza di `BarcodeGenerator`, regola `XDimension` e `FilledBars` secondo necessità e riutilizza l'oggetto per ridurre le allocazioni di memoria.

## Conclusione

Ora sai **come impostare la larghezza**, **come creare barre vuote**, **come riempire le barre**, e i passaggi esatti per **generare un codice a barre Planet** con Aspose.BarCode in C#. L'esempio completo e eseguibile produce sia file PNG con barre riempite sia con barre vuote, pronti per l'integrazione in qualsiasi flusso di lavoro di etichette di spedizione.

Successivamente, esplora argomenti correlati come **come aggiungere codici QR alla stessa etichetta**, **personalizzare i colori del codice a barre**, o **incorporare il codice a barre in un documento PDF**. Ognuno di questi si basa sugli stessi fondamenti trattati qui. Buona programmazione!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Crea immagine di codice a barre Planet in C# – Come generare un codice a barre postale](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Come creare un codice a barre Code128 con barre vuote in Java](/barcode/english/java/image-manipulation/generating-barcode-empty-bars/)
- [Come generare un'immagine di codice a barre in Java con Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}