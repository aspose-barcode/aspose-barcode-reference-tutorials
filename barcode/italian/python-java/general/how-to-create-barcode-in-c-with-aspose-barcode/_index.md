---
category: general
date: 2026-09-26
description: Impara a creare codici a barre in C# usando Aspose.BarCode. Questa guida
  passo passo include un esempio di generatore di codici a barre e mostra come regolare
  l'altezza delle barre.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode c#
- barcode generator example
- how to adjust bar height
- change barcode height
- generate barcode aspose
language: it
lastmod: 2026-09-26
og_description: Crea un codice a barre in C# con Aspose.BarCode. Segui questa guida
  per generare un codice a barre, regolare l'altezza delle barre e salvare immagini
  PNG.
og_image_alt: Diagram illustrating how to create barcode in C# using Aspose.BarCode
og_title: Crea codice a barre in C# con Aspose.BarCode – guida completa
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
    guide includes a barcode generator example and shows how to adjust bar height.
  headline: How to create barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
    guide includes a barcode generator example and shows how to adjust bar height.
  name: How to create barcode in C# with Aspose.BarCode
  steps:
  - name: Import required namespaces
    text: '```csharp using System; using Aspose.BarCode.Generation; using Aspose.BarCode;
      ```'
  - name: Initialise the barcode generator
    text: We’ll generate a **Databar Omni‑Directional** symbol that encodes a GTIN‑14
      value. The constructor takes the symbology and the raw data string.
  - name: Set common barcode parameters
    text: 'Two visual parameters are most often tweaked: the X‑dimension (the narrow
      bar width) and the overall bar height.'
  - name: Save the first image (30‑pixel height)
    text: '```csharp // Save the barcode as a 30‑pixel‑high PNG generator.Save("DatabarBarHeight30Pixels.png",
      BarCodeImageFormat.Png); ```'
  - name: Change the bar height to 60 pixels
    text: Now we demonstrate **how to adjust bar height** at runtime. The same `generator`
      instance is reused; only the `BarHeight` property changes.
  - name: Full source code
    text: 'Putting everything together yields a concise, runnable program:'
  - name: Switching to a different symbology
    text: 'If you need a QR code instead of a Databar, replace the `EncodeTypes` value:'
  - name: Using `BarHeight` in millimetres
    text: 'Aspose.BarCode also supports physical units. To set a height of 10 mm:'
  - name: Handling errors
    text: 'If the data string does not conform to the selected symbology, `BarcodeGenerator`
      throws an `ArgumentException`. Wrap the generation logic in a try‑catch block
      to provide a friendly message:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Come creare un codice a barre in C# con Aspose.BarCode
url: /it/python-java/general/how-to-create-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un barcode in C# con Aspose.BarCode  

Se hai bisogno di **creare barcode c#** progetti rapidamente, Aspose.BarCode fornisce un'API fluida che gestisce il lavoro pesante. In questo tutorial vedrai un **esempio di generatore di barcode** completo, imparerai **come regolare l'altezza del barcode**, e potrai esportare il risultato come file PNG.  

Che tu stia costruendo un sistema di cassa al dettaglio, generando etichette di inventario, o automatizzando le etichette di spedizione, la capacità di modificare programmaticamente le dimensioni visive di un barcode è essenziale. Questa guida presuppone una conoscenza di base di C# e di un ambiente di sviluppo come Visual Studio 2022.  

## Prerequisiti  

Prima di iniziare, assicurati di avere:  

* .NET 6.0 SDK o versioni successive installate.  
* Visual Studio 2022 (o qualsiasi IDE C#).  
* Una licenza attiva di Aspose.BarCode (la versione di prova gratuita è sufficiente per l'apprendimento).  

Dovrai inoltre aggiungere il pacchetto NuGet Aspose.BarCode al tuo progetto:

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Se prevedi di generare molti barcode in un ciclo, riutilizza una singola istanza di `BarcodeGenerator` e modifica solo i parametri che cambiano. Questo riduce le allocazioni di memoria e migliora le prestazioni.

## Come creare un barcode in C# con Aspose.BarCode  

Le sezioni seguenti illustrano passo per passo l'**esempio di generatore di barcode**. Il codice è autonomo; copialo in una nuova applicazione console ed eseguilo.

### Passo 1: Importare gli spazi dei nomi richiesti  

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Questi spazi dei nomi ti danno accesso alla classe `BarcodeGenerator` e all'enumerazione `EncodeTypes`.

### Passo 2: Inizializzare il generatore di barcode  

Genereremo un simbolo **Databar Omni‑Directional** che codifica un valore GTIN‑14. Il costruttore richiede la simbologia e la stringa di dati grezzi.

```csharp
// Initialise a generator for Databar Omni‑Directional
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Il valore `EncodeTypes.DatabarOmniDirectional` indica ad Aspose.BarCode quale standard di barcode utilizzare. La stringa di dati segue il formato GS1 Application Identifier, comune per i barcode al dettaglio.

### Passo 3: Impostare i parametri comuni del barcode  

Due parametri visivi sono i più spesso modificati: la X‑dimension (larghezza della barra stretta) e l'altezza complessiva della barra.  

```csharp
// Set the narrow bar width to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set the initial bar height to 30 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

La **X‑dimension** controlla la densità del barcode, mentre **BarHeight** determina la dimensione verticale di ogni barra. Regolare **BarHeight** è esattamente ciò di cui hai bisogno quando vuoi **cambiare l'altezza del barcode** per diversi supporti di stampa.

### Passo 4: Salvare la prima immagine (altezza di 30 pixel)  

```csharp
// Save the barcode as a 30‑pixel‑high PNG
generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Il metodo `Save` scrive l'immagine renderizzata su disco. Il nome del file indica chiaramente l'altezza usata, il che aiuta quando confronti output diversi.

### Passo 5: Cambiare l'altezza della barra a 60 pixel  

Ora dimostriamo **come regolare l'altezza del barcode** a runtime. La stessa istanza `generator` viene riutilizzata; solo la proprietà `BarHeight` cambia.

```csharp
// Increase the bar height to 60 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the larger barcode
generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Poiché il generatore mantiene tutte le altre impostazioni (simbologia, dati, X‑dimension), l'unica differenza visiva tra i due file PNG è la dimensione verticale delle barre.

### Codice sorgente completo  

Unendo tutto si ottiene un programma conciso e eseguibile:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for Databar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Configure visual parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // narrow bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // first height

            // 3️⃣ Save the 30‑pixel‑high image
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30‑pixel barcode.");

            // 4️⃣ Change the bar height to 60 pixels (how to adjust bar height)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 5️⃣ Save the 60‑pixel‑high image
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60‑pixel barcode.");

            // Optional: clean up resources
            generator.Dispose();
        }
    }
}
```

**Output previsto**  

L'esecuzione del programma crea due file PNG nella directory di lavoro dell'eseguibile:

* `DatabarBarHeight30Pixels.png` – un barcode con altezza della barra di 30 px.  
* `DatabarBarHeight60Pixels.png` – lo stesso barcode, ma ogni barra è alta il doppio.

Apri le immagini con qualsiasi visualizzatore; vedrai che il modello complessivo rimane identico mentre la dimensione verticale cambia, confermando che l'operazione **cambiare l'altezza del barcode** è riuscita.

## Varianti avanzate  

### Passare a una simbologia diversa  

Se ti serve un QR code invece di un Databar, sostituisci il valore `EncodeTypes`:

```csharp
generator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

Tutte le altre impostazioni dei parametri (X‑dimension, BarHeight) rimangono valide dove hanno senso.

### Usare `BarHeight` in millimetri  

Aspose.BarCode supporta anche unità fisiche. Per impostare un'altezza di 10 mm:

```csharp
generator.Parameters.Barcode.BarHeight.Millimeters = 10;
```

Questo è utile quando generi barcode per layout di stampa che richiedono misurazioni precise.

### Gestione degli errori  

Se la stringa di dati non è conforme alla simbologia selezionata, `BarcodeGenerator` lancia un `ArgumentException`. Avvolgi la logica di generazione in un blocco try‑catch per fornire un messaggio amichevole:

```csharp
try
{
    generator.Save("output.png", BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode data: {ex.Message}");
}
```

## Domande frequenti  

* **Cambiare BarHeight influisce sulla scansibilità?**  
  Il barcode rimane scansionabile finché la X‑dimension e la zona di quiete complessiva rispettano le specifiche della simbologia. Aumentare l'altezza rende solo le barre più lunghe; non riduce mai il contrasto.

* **Posso impostare altezze diverse per barre individuali?**  
  No. La proprietà `BarHeight` si applica uniformemente all'intero simbolo. Per design a altezza variabile dovresti utilizzare una routine di rendering personalizzata al di fuori di Aspose.BarCode.

* **Il PNG è il formato migliore per la stampa?**  
  PNG conserva dati pixel senza perdita, rendendolo ideale per la visualizzazione su schermo. Per lavori di stampa ad alta risoluzione, considera `BarCodeImageFormat.Tiff` o `Pdf` per mantenere le informazioni vettoriali.

## Conclusione  

Ora sai come **creare barcode c#** applicazioni con Aspose.BarCode, hai visto un **esempio completo di generatore di barcode** e comprendi **come regolare l'altezza del barcode** per soddisfare diversi requisiti di layout. Riutilizzando la stessa istanza del generatore e modificando solo `BarHeight`, puoi cambiare l'altezza del barcode in modo efficiente senza ricostruire l'intero oggetto.

Da qui potresti esplorare:

* Generare altre simbologie (`EncodeTypes.Code128`, `EncodeTypes.EAN13`).  
* Esportare in SVG o PDF per grafica scalabile.  
* Incorporare barcode direttamente in documenti Word o Excel usando Aspose.Words o Aspose.Cells.

Buona programmazione e goditi la flessibilità che Aspose.BarCode porta ai tuoi progetti barcode in C#!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come generare e regolare l'altezza del barcode per Databar unidimensionale usando Aspose.BarCode per .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Come creare un file PNG di barcode con altezza regolabile in C#](/barcode/english/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/)
- [Come generare barcode in C# – Guida completa Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}