---
category: general
date: 2026-07-15
description: crea un codice a barre omnidirezionale in C# rapidamente con Aspose.BarCode
  – scopri come generare un codice a barre in C# con altezza della barra e dimensione
  X regolabili.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni-directional barcode
- how to generate barcode c#
- GS1 DataBar Omni-Directional
- barcode XDimension
- barcode BarHeight
language: it
lastmod: 2026-07-15
og_description: Crea un codice a barre omnidirezionale in C# con Aspose.BarCode. Impara
  a generare codici a barre in C# regolando XDimension e BarHeight per risultati perfetti.
og_image_alt: Screenshot showing a create omni-directional barcode generated in C#
  with 60 px bar height
og_title: Crea un codice a barre omnidirezionale in C# – Guida completa alla programmazione
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  headline: create omni-directional barcode in C# – Step‑by‑Step Guide
  type: TechArticle
- description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  name: create omni-directional barcode in C# – Step‑by‑Step Guide
  steps:
  - name: Expected output
    text: '- `DatabarBarHeight30Pixels.png` – a 30 px tall omni‑directional barcode.
      - `DatabarBarHeight60Pixels.png` – the same data, but with a 60 px tall barcode.'
  - name: What if I need a different X‑dimension?
    text: Simply assign a new value before calling `Save`. For ultra‑high‑density
      printing you might go down to 1 px, but test with your scanner first—some devices
      struggle with sub‑2 px bars.
  - name: Can I add human‑readable text below the barcode?
    text: Yes. Set `barcodeGenerator.Parameters.Barcode.CodeText` to a string and
      optionally adjust `barcodeGenerator.Parameters.Barcode.CodeLocation` to `BarCodeTextLocation.Below`.
      This is handy for retail environments where the numeric GTIN must be visible.
  - name: Is PNG the best format for printing?
    text: PNG is lossless, which preserves the sharp edges needed for barcode scanners.
      If your downstream system expects a different format (TIFF, BMP), just change
      the `BarCodeImageFormat` enum.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- GS1
- DataBar
title: Crea un codice a barre omnidirezionale in C# – Guida passo passo
url: /it/python-java/general/create-omni-directional-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# creare codice a barre omni-directional in C# – Guida passo‑passo

Ti sei mai chiesto come generare un barcode C# che rispetti la simbologia GS1 DataBar Omni‑Directional? Non sei solo. In questo tutorial **creeremo codice a barre omni-directional** da zero, regoleremo la X‑dimension e giocheremo con l’altezza delle barre—tutto usando la libreria Aspose.BarCode.

Affronteremo uno scenario reale: hai bisogno di un barcode compatto e ad alta densità per un’etichetta retail e vuoi il controllo totale sulla sua dimensione visiva. Alla fine avrai due file PNG—uno con un’altezza barra di 30 px e l’altro con 60 px—pronti per essere inseriti in qualsiasi flusso di stampa.

## Prerequisiti

- .NET 6 (o qualsiasi runtime .NET recente) installato sulla tua macchina.  
- Visual Studio 2022 o VS Code—qualunque IDE preferito va bene.  
- Un pacchetto NuGet gratuito Aspose.BarCode per .NET (`Aspose.BarCode`).

Non sono richieste altre dipendenze. Se non hai mai usato NuGet, apri semplicemente la Package Manager Console ed esegui:

```powershell
Install-Package Aspose.BarCode
```

## creare codice a barre omni-directional – Comprendere le basi

La simbologia **GS1 DataBar Omni‑Directional** è progettata per la scansione in qualsiasi orientamento, rendendola perfetta per le etichette a bordo scaffale. Quando chiami `new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data)`, la libreria fa il lavoro pesante: codifica i dati, applica le regole della simbologia e prepara un’immagine raster.

> **Pro tip:** Avvolgi sempre i dati grezzi nel formato appropriato di Application Identifier (AI), ad es. `"(01)12345678901231"` per un GTIN‑14. Questo indica allo scanner cosa rappresentano le cifre.

## Passo 1 – Configurare il Barcode Generator (how to generate barcode c#)

Per prima cosa creiamo l’oggetto generatore. È il fondamento di **how to generate barcode c#** con Aspose.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for the GS1 DataBar Omni‑Directional symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Il valore enum `EncodeTypes.DatabarOmniDirectional` indica al motore quale simbologia utilizzare. Il secondo argomento è la stringa dei dati grezzi, già avvolta nell’AI GTIN.

## Passo 2 – Regolare la X‑Dimension (barcode XDimension)

La **barcode XDimension** controlla la larghezza della barra più piccola. Un valore di 2 px è un buon compromesso tra leggibilità e compattezza per la maggior parte delle stampanti di etichette.

```csharp
// Step 2: Define common barcode parameters (2 px X‑dimension)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Se ti serve un aspetto più fine o più grossolano, basta cambiare il numero. Ricorda: la X‑dimension è l’unità fondamentale; tutte le altre larghezze delle barre sono multipli di questo valore.

## Passo 3 – Creare la Prima Immagine con un'Altezza Barra di 30 px (barcode BarHeight)

Ora impostiamo la **barcode BarHeight** a 30 px e salviamo l’immagine. Questo produce un barcode di dimensioni moderate che si adatta bene a un’etichetta standard.

```csharp
// Step 3: Set a 30 px bar height and save the first image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Il metodo `Save` scrive un file PNG su disco. Puoi sostituire `BarCodeImageFormat.Jpeg` se preferisci l’output JPEG.

## Passo 4 – Aumentare l'Altezza della Barra a 60 px per Etichette più Grandi (barcode BarHeight)

A volte è necessario un barcode più grande—magari per un’etichetta a scaffale più distante dallo scanner. Raddoppiamo l’altezza.

```csharp
// Step 4: Increase the bar height to 60 px for a larger barcode
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

Nota che **non** è necessario ricreare il generatore; basta modificare il parametro e riutilizzare lo stesso oggetto. Questo salva memoria e mantiene il codice ordinato.

## Passo 5 – Salvare la Seconda Immagine (how to generate barcode c#)

Infine, salviamo il secondo PNG. Ora hai due file che differiscono solo per l’altezza della barra.

```csharp
// Step 5: Save the second image with the updated height
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

### Output previsto

- `DatabarBarHeight30Pixels.png` – un barcode omni‑directional alto 30 px.  
- `DatabarBarHeight60Pixels.png` – gli stessi dati, ma con un barcode alto 60 px.

Apri i file con qualsiasi visualizzatore di immagini; vedrai barre nitide e scansionabili che rispettano la specifica GS1 DataBar Omni‑Directional.

## Domande Frequenti & Casi Limite

### E se avessi bisogno di una X‑dimension diversa?

Assegna semplicemente un nuovo valore prima di chiamare `Save`. Per stampe ultra‑ad alta densità potresti scendere a 1 px, ma testalo prima con il tuo scanner—alcuni dispositivi hanno difficoltà con barre inferiori a 2 px.

### Posso aggiungere testo leggibile dall'uomo sotto il barcode?

Sì. Imposta `barcodeGenerator.Parameters.Barcode.CodeText` su una stringa e, opzionalmente, regola `barcodeGenerator.Parameters.Barcode.CodeLocation` a `BarCodeTextLocation.Below`. È utile in ambienti retail dove il GTIN numerico deve essere visibile.

```csharp
barcodeGenerator.Parameters.Barcode.CodeText = "(01)12345678901231";
barcodeGenerator.Parameters.Barcode.CodeLocation = BarCodeTextLocation.Below;
```

### È il PNG il formato migliore per la stampa?

Il PNG è lossless, il che preserva i bordi netti necessari per gli scanner di barcode. Se il tuo sistema a valle richiede un formato diverso (TIFF, BMP), basta cambiare l’enum `BarCodeImageFormat`.

## Esempio Completo (creare codice a barre omni-directional)

Di seguito trovi il programma completo, pronto per l’esecuzione. Copialo in un nuovo progetto console e premi **F5**.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace OmniDirectionalDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create generator for GS1 DataBar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension (2 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ Second image – 60 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two omni‑directional barcodes created successfully.");
        }
    }
}
```

Esegui il programma, controlla la cartella di output e vedrai i due file PNG esattamente come descritto.

## Riepilogo

Abbiamo mostrato **how to generate barcode C#** che crea un **creare codice a barre omni-directional** usando Aspose.BarCode. Regolando la **barcode XDimension** e la **barcode BarHeight**, ottieni un controllo fine sulla dimensione visiva senza sacrificare l’affidabilità della scansione.

## Cosa segue?

- Sperimenta con altre impostazioni **GS1 DataBar Omni-Directional** come `Color` o `Margin`.  
- Combina più barcode su una singola tela usando `Graphics` per design di etichette complessi.  
- Integra il generatore in una web API così la tua piattaforma e‑commerce può emettere barcode su richiesta.

Hai un trucco da condividere? Lascia un commento e continuiamo la conversazione. Buona programmazione!

## Cosa dovresti imparare dopo?

I tutorial seguenti coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell’API e a esplorare approcci alternativi di implementazione nei tuoi progetti.

- [Come Generare Barcode – Configurazione Code 39 con Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Come Creare la Zona Silenziosa del Barcode per ITF-14 Usando Aspose.BarCode per .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Come creare la zona silenziosa del barcode per Code 16K usando Aspose.BarCode per .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}