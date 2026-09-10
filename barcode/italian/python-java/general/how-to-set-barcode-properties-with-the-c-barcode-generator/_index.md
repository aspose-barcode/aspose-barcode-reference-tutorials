---
category: general
date: 2026-09-10
description: Come impostare il codice a barre in C# usando un generatore di codici
  a barre. Regola la larghezza del modulo del codice a barre, genera immagini del
  codice a barre e impara a salvare i file del codice a barre.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- c# barcode generator
- barcode module width
- how to generate barcode
- how to save barcode
language: it
lastmod: 2026-09-10
og_description: Come impostare il codice a barre in C# con un generatore di codici
  a barre. Impara a regolare la larghezza del modulo, generare un codice a barre e
  salvare l'immagine del codice a barre in modo efficiente.
og_image_alt: Screenshot showing a Planet barcode with filled and empty bars generated
  by C# code
og_title: Come impostare le proprietà del codice a barre con il generatore di codici
  a barre C#
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: How to set barcode in C# using a Barcode Generator. Adjust barcode
    module width, generate barcode images, and learn how to save barcode files.
  headline: How to set barcode properties with the C# Barcode Generator
  type: TechArticle
tags:
- barcode
- c#
- image generation
title: Come impostare le proprietà del codice a barre con il Generatore di Codici
  a Barre C#
url: /it/python-java/general/how-to-set-barcode-properties-with-the-c-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come impostare le proprietà del codice a barre con il Generatore di Codici a Barre C#

Impostare le proprietà del codice a barre è essenziale quando è necessario un controllo preciso sullo stile visivo di un codice a barre. Questa guida mostra come generare un codice a barre Planet, regolare la larghezza del modulo del codice a barre e salvare l'immagine del codice a barre utilizzando il Generatore di Codici a Barre C#.

Vedrai un esempio completo e eseguibile che copre ogni passaggio, dalla creazione dell'oggetto barcode alla scrittura dei file PNG su disco. Non è necessaria alcuna documentazione esterna—basta il codice qui sotto e la libreria Aspose.BarCode (o qualsiasi SDK di codici a barre compatibile). Alla fine del tutorial potrai rispondere a domande come “come generare un codice a barre con dimensioni personalizzate?” e “come salvare un codice a barre in formati diversi?”.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6.0 o versioni successive installato  
* Visual Studio 2022 (o qualsiasi IDE C#)  
* Il pacchetto NuGet **Aspose.BarCode** (o un'altra libreria che fornisce `BarcodeGenerator`)  

Puoi aggiungere il pacchetto con il seguente comando:

```bash
dotnet add package Aspose.BarCode
```

## Come impostare la larghezza del modulo del codice a barre

La *larghezza del modulo* (nota anche come X‑dimension) determina la dimensione in pixel di ogni barra stretta nel codice a barre. Impostare questo valore ti consente di controllare la dimensione complessiva e la leggibilità dell'immagine.

```csharp
// Create a barcode generator for the Planet symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width to 4 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Perché è importante*: una X‑dimension più grande produce un codice a barre più grande, più facile da leggere per gli scanner a distanza, mentre un valore più piccolo riduce le dimensioni del file per il rendering su schermo.

## Generazione di un codice a barre con barre riempite

Lo stile predefinito per il codice a barre Planet utilizza **filled bars** (barre nere solide). Il codice seguente crea l'immagine e la salva come PNG.

```csharp
// Save the barcode with filled bars
barcodeGenerator.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

> **Risultato**: `PostalPlanetFilledBars.png` contiene un codice a barre Planet standard in cui ogni barra è riempita.

## Creazione di un codice a barre con barre vuote

A volte è necessario un codice a barre che mostri solo i contorni delle barre (barre vuote). Per ottenerlo, duplichi il generatore, mantieni la stessa larghezza del modulo e disattivi il flag `FilledBars`.

```csharp
// Duplicate the generator for an empty‑bar version
BarcodeGenerator emptyBarGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Apply the same X‑dimension
emptyBarGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars so only the outlines are drawn
emptyBarGenerator.Parameters.Barcode.FilledBars = false;

// Save the empty‑bar barcode
emptyBarGenerator.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

> **Risultato**: `PostalPlanetEmptyBars.png` visualizza gli stessi dati ma con barre non riempite, utile per documenti dal design pesante in cui vuoi che il codice a barre si integri con lo sfondo.

## Come salvare il codice a barre in formati diversi

Il metodo `Save` accetta qualsiasi formato supportato dall'SDK, come **Jpeg**, **Bmp**, **Gif** o **Svg**. Cambiare il formato richiede solo di sostituire il valore dell'enumerazione `BarCodeImageFormat`.

```csharp
// Example: save as SVG for lossless scaling
barcodeGenerator.Save("YOUR_DIRECTORY/PostalPlanet.svg", BarCodeImageFormat.Svg);
```

*Suggerimento*: Usa SVG quando ti serve una grafica vettoriale che si scala senza pixelatura, soprattutto per PDF pronti per la stampa.

## Esempio completo ed eseguibile

Unendo tutti i pezzi ottieni un programma autonomo che puoi incollare in un'app console.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1. Create a filled‑bar Planet barcode
        BarcodeGenerator filledGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        filledGenerator.Parameters.Barcode.XDimension.Pixels = 4; // barcode module width
        filledGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // 2. Create an empty‑bar version of the same barcode
        BarcodeGenerator emptyGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        emptyGenerator.Parameters.Barcode.XDimension.Pixels = 4; // same module width
        emptyGenerator.Parameters.Barcode.FilledBars = false;   // how to set barcode to empty bars
        emptyGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

        // 3. Optional: save as SVG for scalable use
        filledGenerator.Save("PostalPlanet.svg", BarCodeImageFormat.Svg);
    }
}
```

**Output previsto**

| Nome file                     | Descrizione                              |
|-------------------------------|------------------------------------------|
| `PostalPlanetFilledBars.png`  | Codice a barre Planet con barre nere solide |
| `PostalPlanetEmptyBars.png`   | Stessi dati, barre visualizzate come contorni |
| `PostalPlanet.svg`            | Versione vettoriale per scalare senza perdita |

Esegui il programma, apri i file generati e verifica che i codici a barre corrispondano alla stringa numerica “123456”.

## Variazioni comuni e casi limite

| Situazione                               | Regolazione                                                                 |
|------------------------------------------|-----------------------------------------------------------------------------|
| Necessità di un codice a barre più spesso | Incrementa `XDimension.Pixels` (es., `8`)                                   |
| Desideri una dimensione del file più piccola | Usa `BarCodeImageFormat.Jpeg` o riduci la X‑dimension                        |
| Generazione di altre simbologie           | Sostituisci `EncodeTypes.Planet` con `EncodeTypes.Code128`, `QR`, ecc.       |
| Stampa su stampanti ad alta risoluzione   | Salva come `BarCodeImageFormat.Tiff` per output raster senza perdita         |
| Esecuzione su server senza interfaccia grafica | Nessun codice UI necessario; il generatore funziona in un contesto console o service |

**Consiglio professionale**: valida sempre il codice a barre generato con uno scanner o uno strumento di verifica prima di distribuirlo in produzione. Una larghezza del modulo o un formato errati possono causare errori di scansione.

## Conclusione

Ora sai come impostare le proprietà del codice a barre usando il Generatore di Codici a Barre C#, come controllare la larghezza del modulo, come generare sia lo stile a barre riempite che quello a barre vuote e come salvare il codice a barre in formati PNG o SVG. Questi passaggi ti forniscono una solida base per aggiungere la creazione di codici a barre a qualsiasi applicazione .NET.

Successivamente, esplora argomenti correlati come **ottimizzazione delle prestazioni del generatore di codici a barre C#**, **incorporare codici a barre in documenti PDF** e **creare codici QR con colori personalizzati**. Sperimenta con diversi `EncodeTypes` e formati immagine per trovare la soluzione migliore per il tuo progetto.

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come salvare il codice a barre in C# – Generare codici a barre PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Tutorial del Generatore di Codici a Barre: Come generare un codice a barre PDF417 in C#](/barcode/english/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)
- [Come impostare il livello di errore nel codice a barre PDF417 – Guida completa](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}