---
category: general
date: 2026-08-19
description: Impara a generare un file PNG di codice a barre in C# e a regolarne l’altezza,
  includendo come creare immagini di codici a barre e modificare facilmente l’altezza
  del codice a barre.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode png file
- how to generate barcode
- adjust barcode height
- change barcode height
language: it
lastmod: 2026-08-19
og_description: Crea un file PNG di codice a barre in C# e impara come generare immagini
  di codici a barre, regolare l'altezza del codice a barre e modificarla per scansioni
  ottimali.
og_image_alt: barcode PNG file showing Databar OmniDirectional barcode at two heights
og_title: Crea un file PNG di codice a barre in C# – guida passo passo
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Learn how to generate a barcode PNG file in C# and adjust its height,
    covering how to generate barcode images and change barcode height easily.
  headline: How to create a barcode PNG file with adjustable height in C#
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`,
      `BarCodeImageFormat.Bmp`, etc.
    question: Can I generate other image formats (JPEG, BMP)?
  - answer: Serve the generated PNG via an HTTP endpoint or convert it to a Base64
      string and place it in an `<img>` tag’s `src` attribute.
    question: How do I embed the PNG in a web page?
  - answer: 'Use `generator.Parameters.Image.BackgroundColor = Color.White;` (or any
      `System.Drawing.Color`). ## Conclusion You now know how to **generate a barcode
      PNG file** in C# and precisely **adjust barcode height** to meet scanning or
      design requirements. By changing the `BarHeight.Pixels` property you ca'
    question: Is there a way to set the background color?
  type: FAQPage
tags:
- barcode
- C#
- image generation
title: Come creare un file PNG di codice a barre con altezza regolabile in C#
url: /it/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un file PNG di codice a barre con altezza regolabile in C#

Se hai bisogno di creare un **file PNG di codice a barre** in C#, questa guida ti mostra esattamente come fare. Vedrai un esempio completo e eseguibile che dimostra **come generare codici a barre** e come **regolare l'altezza del codice a barre** per diversi casi d'uso.

Generare un file PNG di codice a barre è una necessità comune per sistemi di inventario, terminali point‑of‑sale e qualsiasi applicazione che deve stampare o visualizzare dati leggibili da macchine. Alla fine di questo tutorial sarai in grado di modificare l'altezza del codice a barre, salvare più file PNG e comprendere l'impatto dell'altezza sull'affidabilità della scansione.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6.0 SDK o versioni successive installate  
* Visual Studio 2022 (o qualsiasi IDE che supporti .NET)  
* Il pacchetto NuGet **Aspose.BarCode for .NET** (il campione di codice utilizza questa libreria)  

Puoi aggiungere il pacchetto dalla riga di comando:

```bash
dotnet add package Aspose.BarCode
```

> **Consiglio professionale:** La versione di valutazione gratuita di Aspose.BarCode funziona per sviluppo e test. Per la produzione, ottieni una chiave con licenza.

## Installa la libreria per i codici a barre

Il primo passo è fare riferimento alla libreria nel tuo progetto. Aggiungi le seguenti direttive `using` all'inizio del tuo file C#:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Questi namespace ti danno accesso a `BarcodeGenerator`, `EncodeTypes` e `BarCodeImageFormat`.

## Crea il file PNG del codice a barre

Ora creiamo un'istanza di `BarcodeGenerator` che produrrà un **file PNG di codice a barre**. L'esempio utilizza la simbologia Databar OmniDirectional, ma puoi sostituire `EncodeTypes.DatabarOmniDirectional` con qualsiasi tipo supportato.

```csharp
// Step 1: Create a DataBar Omnidirectional generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

La stringa `"(01)12345678901231"` segue il formato GS1 Application Identifier per un GTIN a 14 cifre. Regola i dati per corrispondere ai tuoi identificatori di prodotto.

## Imposta la dimensione X (opzionale)

La dimensione X definisce la larghezza di un singolo modulo del codice a barre. Un valore basato sui pixel ti offre un controllo preciso sulla dimensione dell'immagine.

```csharp
// Optional: Set the pixel size of the X‑dimension (module width)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Un valore di `2` pixel funziona bene per la maggior parte dei display. Incrementalo se ti serve un codice a barre più grande in stampa.

## Regola l'altezza del codice a barre e salva il file PNG del codice a barre

La proprietà **BarHeight** controlla la dimensione verticale delle barre. Modificando questo valore puoi **regolare l'altezza del codice a barre** senza influire sui dati codificati.

```csharp
// Step 2: Generate a 30‑pixel‑high barcode and save it as PNG
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Il file `DatabarBarHeight30Pixels.png` è ora un **file PNG di codice a barre** alto 30 pixel.  

Per **cambiare l'altezza del codice a barre** e creare una seconda immagine, assegna semplicemente un nuovo valore e chiama nuovamente `Save`:

```csharp
// Step 3: Change the height to 60 pixels and save the new image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
barcodeGenerator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Ora disponi di due file PNG—uno a 30 px e l'altro a 60 px—che dimostrano come **regolare l'altezza del codice a barre** al volo.

### Perché l'altezza delle barre è importante

* **Readability:** Gli scanner si aspettano un'altezza minima per una rilevazione affidabile. Un codice a barre troppo corto può essere ignorato, soprattutto con fotocamere a bassa risoluzione.  
* **Aesthetics:** Abbinare l'altezza del codice a barre agli elementi di design circostanti crea un'interfaccia più pulita.  
* **Print constraints:** Alcune stampanti di etichette hanno slot di altezza fissa; regolare l'altezza del codice a barre garantisce che si adatti.

**Best practice:** Mantieni l'altezza un multiplo della dimensione X (ad esempio, 30 px quando la dimensione X è 2 px) per preservare le proporzioni ed evitare distorsioni.

## Esempio completo

Di seguito trovi il programma completo e autonomo che puoi incollare in un'applicazione console e eseguire immediatamente.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator with Databar OmniDirectional data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set a reasonable X‑dimension (module width)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First height: 30 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode as DatabarBarHeight30Pixels.png");

        // 4️⃣ Second height: 60 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode as DatabarBarHeight60Pixels.png");
    }
}
```

**Output previsto**

L'esecuzione del programma crea due file nella directory di lavoro dell'eseguibile:

* `DatabarBarHeight30Pixels.png` – un file PNG di codice a barre alto 30 pixel  
* `DatabarBarHeight60Pixels.png` – un file PNG di codice a barre alto 60 pixel  

Apri uno dei PNG con qualsiasi visualizzatore di immagini; vedrai un chiaro codice Databar OmniDirectional pronto per la scansione.

## Casi limite e risoluzione dei problemi

| Situazione | Cosa controllare | Correzione consigliata |
|------------|------------------|------------------------|
| Il codice a barre appare sfocato | X‑dimension troppo bassa per l'altezza scelta | Incrementa `XDimension.Pixels` (es., da 2 a 3) |
| Lo scanner fallisce su un codice a barre di bassa altezza | Altezza inferiore al minimo richiesto dallo scanner | Imposta `BarHeight.Pixels` ad almeno 30 px (o secondo le specifiche dello scanner) |
| Il file PNG è vuoto o corrotto | Percorso di output non valido o permessi di scrittura negati | Usa un percorso assoluto o assicurati che l'app abbia i permessi di scrittura |
| Serve una simbologia diversa | L'`EncodeTypes` corrente non è adatto | Sostituisci `EncodeTypes.DatabarOmniDirectional` con un altro valore enum (es., `EncodeTypes.Code128`) |

## Domande frequenti

**D: Posso generare altri formati immagine (JPEG, BMP)?**  
R: Sì. Sostituisci `BarCodeImageFormat.Png` con `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp`, ecc.

**D: Come inserisco il PNG in una pagina web?**  
R: Servi il PNG generato tramite un endpoint HTTP o convertilo in una stringa Base64 e inseriscilo nell'attributo `src` di un tag `<img>`.

**D: È possibile impostare il colore di sfondo?**  
R: Usa `generator.Parameters.Image.BackgroundColor = Color.White;` (o qualsiasi `System.Drawing.Color`).

## Conclusione

Ora sai come **generare un file PNG di codice a barre** in C# e **regolare con precisione l'altezza del codice a barre** per soddisfare requisiti di scansione o di design. Modificando la proprietà `BarHeight.Pixels` puoi **cambiare l'altezza del codice a barre** al volo e produrre più asset PNG da una singola base di codice.

Successivamente, esplora altre opzioni di personalizzazione come colore di primo piano, margini e aggiunta di testo leggibile dall'uomo. Puoi anche sperimentare con diverse simbologie (`EncodeTypes.Code128`, `EncodeTypes.QR`) per ampliare la gamma di dati che puoi codificare.

Buon coding, e che i tuoi codici a barre vengano sempre letti al primo tentativo!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come generare e regolare l'altezza del codice a barre per Databar unidimensionale usando Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Come generare codici a barre - Tipi di codici a barre unidimensionali](/barcode/english/net/one-dimensional-barcode-types/)
- [Come generare un codice Aztec con rapporto d'aspetto personalizzato usando Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}