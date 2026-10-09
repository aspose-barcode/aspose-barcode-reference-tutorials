---
category: general
date: 2026-10-08
description: Impara a creare un'immagine di codice a barre in C# e scopri come regolare
  il rapporto d'aspetto per i codici a barre DataBar impilati omnidirezionali.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust aspect ratio
- Aspose.BarCode C#
- DataBar stacked omni‑directional
- barcode X‑dimension
language: it
lastmod: 2026-10-08
og_description: Crea un'immagine di codice a barre in C# e scopri come regolare il
  rapporto d'aspetto per i codici a barre DataBar impilati omnidirezionali con un
  esempio di codice completo.
og_image_alt: Result of create barcode image with aspect ratio 15 using Aspose.BarCode
og_title: Crea immagine di codice a barre in C# – guida passo‑passo
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  headline: How to create barcode image and adjust its aspect ratio in C#
  type: TechArticle
- description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  name: How to create barcode image and adjust its aspect ratio in C#
  steps:
  - name: Expected output
    text: 'After running the program you will find two PNG files in the execution
      directory:'
  - name: What if I need a different X‑dimension?
    text: You can change `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` to
      any integer greater than zero. For very high‑resolution output (e.g., 300 dpi),
      a value of 3‑4 pixels often yields clearer results.
  - name: How do I choose the right aspect ratio?
    text: 'The optimal ratio depends on the scanning environment: * **Low‑profile
      labels** – use a smaller ratio (e.g., 10‑15) to keep the barcode compact. *
      **Large shipping containers** – a higher ratio (e.g., 25‑35) improves readability
      from a distance. * **Regulatory requirements** – some standards mandate'
  - name: Can I generate other barcode formats with the same code?
    text: Yes. Replace `EncodeTypes.DatabarStackedOmniDirectional` with any other
      `EncodeTypes` value (e.g., `EncodeTypes.Code128`). The rest of the code—X‑dimension,
      aspect ratio (if applicable), and saving—remains the same.
  - name: What if I need to create the image in a different format?
    text: '`BarCodeImageFormat` supports PNG, JPEG, BMP, GIF, and TIFF. Just change
      the second argument of `Save`, for example:'
  - name: Next steps
    text: '* Explore other symbologies such as **Code128** or **QR Code** by swapping
      the `EncodeTypes` value. * Combine the barcode generation with PDF creation
      (e.g., using Aspose.PDF) to embed barcodes directly into invoices. * Experiment
      with dynamic aspect‑ratio selection based on label size—this extends '
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Come creare un'immagine di codice a barre e regolare il suo rapporto d'aspetto
  in C#
url: /it/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un'immagine di codice a barre e regolare il suo rapporto d'aspetto in C#

Se hai bisogno di **creare un'immagine di codice a barre** programmaticamente, questa guida ti mostra una soluzione completa, pronta all'uso. Vedrai esattamente **come regolare il rapporto d'aspetto** per un codice a barre DataBar stacked omni‑directional, un requisito che appare spesso nelle applicazioni di vendita al dettaglio e logistica.

In questo tutorial imparerai a:
* Inizializzare un `BarcodeGenerator` di Aspose.BarCode per la simbologia DataBar stacked omni‑directional.  
* Impostare la X‑dimension (larghezza del modulo) in pixel per controllare lo spessore delle barre.  
* Applicare due diversi rapporti d'aspetto e salvare ciascun risultato come file PNG.  
* Verificare l'output e capire perché il rapporto d'aspetto è importante.

Non sono richiesti strumenti esterni—solo la libreria Aspose.BarCode per .NET e un ambiente di sviluppo .NET 6 (o successivo).

## Come creare un'immagine di codice a barre con Aspose.BarCode

Il primo passo è istanziare il generatore con la simbologia e la stringa di dati desiderate. L'enumerazione `EncodeTypes.DatabarStackedOmniDirectional` indica ad Aspose.BarCode di produrre un codice a barre DataBar stacked omni‑directional, ampiamente utilizzato per le applicazioni GS1‑128.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a BarcodeGenerator for DataBar stacked omni‑directional.
        // The data string "(01)12345678901231" follows the GS1 Application Identifier format.
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Perché è importante:** L'oggetto `BarcodeGenerator` è il punto di ingresso per tutte le operazioni di creazione di codici a barre. Specificando la simbologia e i dati grezzi fin dall'inizio, garantisci che l'immagine generata sia conforme allo standard GS1.

## Impostare la X‑dimension (larghezza del modulo)

La X‑dimension definisce la larghezza della barra più stretta (il modulo). Una X‑dimension più grande produce un codice a barre più spesso, il che può essere utile per stampanti a bassa risoluzione.

```csharp
        // 2️⃣ Define the X‑dimension in pixels.
        // A value of 2 pixels provides a good balance between readability and file size.
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Perché è importante:** Regolare la X‑dimension è parte del processo di ottimizzazione visiva. Non influisce sui dati codificati, ma influenza l'affidabilità della scansione su diversi dispositivi.

## Come regolare il rapporto d'aspetto – prima versione (15)

Il rapporto d'aspetto controlla la relazione altezza‑larghezza del codice a barre DataBar. La proprietà `DataBar.AspectRatio` accetta valori interi; numeri più grandi producono barre più alte.

```csharp
        // 3️⃣ Set the aspect ratio to 15 and save the first image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Perché è importante:** Un rapporto d'aspetto di 15 è un valore predefinito comune per gli scanner al dettaglio. Il PNG risultante (`DatabarAspectRatio15.png`) avrà un aspetto più alto, il che può migliorare il successo della scansione su dispositivi portatili.

## Come regolare il rapporto d'aspetto – seconda versione (30)

Potresti aver bisogno di un codice a barre più alto per formati di etichetta specifici. Cambiare il rapporto d'aspetto è semplice come assegnare un nuovo valore intero prima di chiamare nuovamente `Save`.

```csharp
        // 4️⃣ Change the aspect ratio to 30 and save a second image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Perché è importante:** Dimostrando **come regolare il rapporto d'aspetto**, puoi generare più immagini di codici a barre dalla stessa fonte di dati senza ricreare il generatore. Questo riduce l'uso di memoria e velocizza l'elaborazione batch.

### Output previsto

Dopo aver eseguito il programma troverai due file PNG nella directory di esecuzione:

| Nome file                     | Rapporto d'aspetto | Descrizione visiva |
|-------------------------------|--------------------|--------------------|
| `DatabarAspectRatio15.png`    | 15                 | Altezza standard, adatto per la maggior parte degli scanner point‑of‑sale. |
| `DatabarAspectRatio30.png`    | 30                 | Barre più alte, utili per etichette grandi o stampanti a bassa risoluzione. |

Entrambe le immagini contengono lo stesso GTIN codificato `(01)12345678901231`, ma le proporzioni visive differiscono in base al rapporto d'aspetto impostato.

## Domande comuni e gestione dei casi limite

### E se ho bisogno di una X‑dimension diversa?

Puoi modificare `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` a qualsiasi intero maggiore di zero. Per output a altissima risoluzione (ad esempio 300 dpi), un valore di 3‑4 pixel spesso produce risultati più nitidi.

### Come scegliere il rapporto d'aspetto corretto?

Il rapporto ottimale dipende dall'ambiente di scansione:
* **Etichette a basso profilo** – usa un rapporto più piccolo (ad esempio 10‑15) per mantenere il codice a barre compatto.  
* **Grandi contenitori di spedizione** – un rapporto più alto (ad esempio 25‑35) migliora la leggibilità a distanza.  
* **Requisiti normativi** – alcuni standard impongono un'altezza minima; consulta la specifica GS1 per i numeri esatti.

### Posso generare altri formati di codice a barre con lo stesso codice?

Sì. Sostituisci `EncodeTypes.DatabarStackedOmniDirectional` con qualsiasi altro valore `EncodeTypes` (ad esempio `EncodeTypes.Code128`). Il resto del codice—X‑dimension, rapporto d'aspetto (se applicabile) e salvataggio—rimane invariato.

### E se devo creare l'immagine in un formato diverso?

`BarCodeImageFormat` supporta PNG, JPEG, BMP, GIF e TIFF. Basta cambiare il secondo argomento di `Save`, per esempio:

```csharp
barcodeGenerator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
```

## Consiglio professionale: riutilizzare il generatore per l'elaborazione batch

Quando devi creare decine di codici a barre con le stesse impostazioni visive, istanzia il generatore una sola volta, aggiorna solo la proprietà `CodeText` e chiama `Save` ripetutamente. Questo evita l'overhead di allocare continuamente buffer interni.

```csharp
// Example of batch creation
string[] gtins = { "(01)12345678901231", "(01)98765432109876", "(01)55555555555555" };
foreach (var gtin in gtins)
{
    barcodeGenerator.CodeText = gtin;
    barcodeGenerator.Save($"Barcode_{gtin.Substring(4, 6)}.png", BarCodeImageFormat.Png);
}
```

## Conclusione

Ora sai come **creare un'immagine di codice a barre** in C# usando Aspose.BarCode e precisamente **come regolare il rapporto d'aspetto** per i simboli DataBar stacked omni‑directional. Controllando la X‑dimension e il rapporto d'aspetto, puoi produrre codici a barre che soddisfano qualsiasi requisito di scansione o layout mantenendo l'implementazione semplice e manutenibile.

### Prossimi passi

* Esplora altre simbologie come **Code128** o **QR Code** sostituendo il valore `EncodeTypes`.  
* Combina la generazione del codice a barre con la creazione di PDF (ad esempio, usando Aspose.PDF) per incorporare i codici a barre direttamente nelle fatture.  
* Sperimenta la selezione dinamica del rapporto d'aspetto in base alle dimensioni dell'etichetta—questo estende il modello **come regolare il rapporto d'aspetto** in un motore di progettazione di etichette completo.

Sentiti libero di adattare il campione, condividere i tuoi risultati o porre domande di follow‑up nei commenti. Buona programmazione!

## Cosa dovresti imparare dopo?

I tutorial seguenti coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare ulteriori funzionalità dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come creare un codice a barre databar stacked in C# con Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [Come creare un'immagine di codice a barre con Aspose.Barcode in C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [Come regolare la dimensione del codice a barre – Rapporto d'aspetto Codablock F con Aspose.BarCode per .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}