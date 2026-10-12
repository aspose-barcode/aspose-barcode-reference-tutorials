---
category: general
date: 2026-09-29
description: Come impostare la larghezza di un codice a barre GS1 DataBar Omni‑Directional
  e come cambiare l'altezza usando C#. Segui una guida passo‑passo con codice completo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to change height
language: it
lastmod: 2026-09-29
og_description: Come impostare la larghezza di un codice a barre GS1 DataBar Omni‑Directional
  e come modificare l’altezza in C#. Scopri le chiamate API esatte e visualizza un
  esempio completo e eseguibile.
og_image_alt: Screenshot of two GS1 DataBar barcodes with different heights
og_title: Come impostare la larghezza di un codice a barre GS1 DataBar – Guida C#
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  headline: How to set width and adjust height for a GS1 DataBar Omni‑Directional
    barcode in C#
  type: TechArticle
- description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  name: How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode
    in C#
  steps:
  - name: Why the X‑dimension matters
    text: '* **Scanner tolerance** – Most scanners expect a minimum module width;
      too small a value can cause read errors. * **Print resolution** – When printing
      at 300 dpi, a 2 px module translates to ~0.17 mm, which is within the recommended
      range for GS1 DataBar. * **Image size** – Larger X‑dimension values'
  - name: Tips for reliable width settings
    text: '* **Never set XDimension below 1 px** – the library will clamp the value,
      but the resulting barcode may be unreadable. * **Match the target DPI** – if
      you render to a high‑resolution format (e.g., TIFF at 600 dpi), increase XDimension
      proportionally. * **Test with a real scanner** – after changing t'
  - name: Understanding bar height
    text: '* **Visual balance** – Taller bars improve readability on low‑contrast
      backgrounds but increase the image’s vertical footprint. * **Regulatory limits**
      – Some standards (e.g., retail labeling) specify a maximum bar height; adjust
      accordingly. * **Aspect ratio** – Changing height does not affect the '
  - name: Edge‑case handling for height adjustments
    text: '| Situation | Recommended approach | |-----------|----------------------|
      | Height < 10 px | Increase to at least 10 px; very short bars may be ignored
      by scanners. | | Very tall bars (≥ 100 px) | Verify that the output medium (paper,
      label) can accommodate the extra space. | | Need proportional sca'
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
- GS1 DataBar
title: Come impostare la larghezza e regolare l'altezza per un codice a barre GS1
  DataBar Omni‑Directional in C#
url: /it/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come impostare la larghezza e regolare l'altezza per un codice a barre GS1 DataBar Omni‑Directional in C#

Impostare la larghezza di un codice a barre GS1 DataBar Omni‑Directional è un'operazione frequente quando è necessario un dimensionamento preciso per le apparecchiature di scansione. In questo tutorial imparerai anche **come cambiare l'altezza** in modo che il codice a barre si adatti perfettamente al tuo layout. La guida ti accompagna attraverso l'intero processo, dalla configurazione del progetto a un esempio di codice completamente eseguibile.

Tratteremo:

* Il pacchetto NuGet richiesto e la versione di .NET.
* Perché la X‑dimension (larghezza del modulo) è importante per la leggibilità del codice a barre.
* Le chiamate API esatte per **impostare la larghezza** e **cambiare l'altezza**.
* Gestione dei casi limite, come la larghezza minima del modulo e il rendering ad alta risoluzione.
* Un esempio completo, pronto da copiare e incollare, che genera due file PNG con altezze di barra diverse.

## Prerequisiti

Prima di iniziare, assicurati di avere:

| Requisito | Motivo |
|------------|--------|
| .NET 6.0 SDK o successivo | L'esempio utilizza le funzionalità moderne di C# e funziona su Windows, Linux o macOS. |
| Visual Studio 2022 (o qualsiasi IDE C#) | Fornisce IntelliSense per l'API Aspose.Barcode. |
| **Aspose.Barcode for .NET** NuGet package | Contiene `BarcodeGenerator`, `EncodeTypes` e il supporto ai formati immagine. Installalo con `dotnet add package Aspose.Barcode`. |
| Permesso di scrittura su una cartella dove verranno salvati i file PNG | Il generatore scrive le immagini di output su disco. |

## Come impostare la larghezza del codice a barre

Il passaggio **come impostare la larghezza** viene eseguito configurando la proprietà `XDimension` dei parametri del codice a barre. `XDimension` rappresenta la larghezza del modulo (la barra o lo spazio più piccolo) in pixel, punti o millimetri. Impostarla correttamente garantisce che il codice a barre soddisfi le specifiche dello scanner.

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a generator for a GS1 DataBar Omni‑Directional barcode.
            // The value "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ **How to set width**: define the module width (X‑dimension) in pixels.
            // A value of 2 px is a common choice that balances readability and image size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // The remaining steps (height, saving) are shown in the next section.
```

### Perché la X‑dimension è importante

* **Tolleranza dello scanner** – La maggior parte degli scanner richiede una larghezza minima del modulo; un valore troppo piccolo può causare errori di lettura.
* **Risoluzione di stampa** – Quando si stampa a 300 dpi, un modulo di 2 px corrisponde a ~0,17 mm, che rientra nell'intervallo consigliato per GS1 DataBar.
* **Dimensione dell'immagine** – Valori più alti di X‑dimension aumentano la larghezza complessiva del codice a barre, il che può influire sui vincoli di layout.

### Consigli per impostazioni di larghezza affidabili

* **Non impostare mai XDimension al di sotto di 1 px** – la libreria limiterà il valore, ma il codice a barre risultante potrebbe essere illeggibile.
* **Corrispondi al DPI target** – se renderizzi in un formato ad alta risoluzione (ad es., TIFF a 600 dpi), aumenta XDimension proporzionalmente.
* **Testa con uno scanner reale** – dopo aver modificato la larghezza, valida il codice a barre sul dispositivo che lo leggerà.

## Come cambiare l'altezza del codice a barre

Una volta definita la larghezza, puoi controllare la dimensione verticale con la proprietà `BarHeight`. Il codice seguente dimostra **come cambiare l'altezza** da 30 px a 60 px e salvare due immagini separate.

```csharp
            // 3️⃣ Set the first bar height to 30 pixels and save the image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ **How to change height**: increase the bar height to 60 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            // The program ends here; two PNG files are written to the execution folder.
        }
    }
}
```

### Comprendere l'altezza della barra

* **Equilibrio visivo** – Barre più alte migliorano la leggibilità su sfondi a basso contrasto ma aumentano l'ingombro verticale dell'immagine.
* **Limiti normativi** – Alcuni standard (ad es., etichettatura al dettaglio) specificano un'altezza massima della barra; regola di conseguenza.
* **Rapporto d'aspetto** – Modificare l'altezza non influisce sulla larghezza del modulo; è possibile regolare entrambi in modo indipendente.

### Gestione dei casi limite per le regolazioni dell'altezza

| Situazione | Approccio consigliato |
|-----------|----------------------|
| Altezza < 10 px | Aumentare ad almeno 10 px; barre molto corte potrebbero essere ignorate dagli scanner. |
| Barre molto alte (≥ 100 px) | Verificare che il supporto di output (carta, etichetta) possa accogliere lo spazio aggiuntivo. |
| Necessità di scala proporzionale | Calcolare `BarHeight = XDimension * desiredRatio` per mantenere la coerenza visiva. |

## Esempio completo e eseguibile

Di seguito trovi il programma completo che combina i passaggi **come impostare la larghezza** e **come cambiare l'altezza**. Copia il codice in un nuovo progetto console, ripristina il pacchetto NuGet Aspose.Barcode e avvialo. Due file PNG appariranno nella cartella `bin/Debug/net6.0`.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // Initialize the barcode generator (GS1 DataBar Omni‑Directional)
            // ------------------------------------------------------------
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // ------------------------------------------------------------
            // **How to set width** – define the module width (X‑dimension)
            // ------------------------------------------------------------
            generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px = ~0.17 mm at 300 dpi

            // ------------------------------------------------------------
            // First image: bar height = 30 px
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight30Pixels.png");

            // ------------------------------------------------------------
            // **How to change height** – increase to 60 px and save again
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight60Pixels.png");

            // ------------------------------------------------------------
            // End of demo
            // ------------------------------------------------------------
        }
    }
}
```

**Output previsto**

Eseguendo il programma vengono prodotti due file PNG:

* `DatabarBarHeight30Pixels.png` – un codice a barre alto 30 px, con moduli larghi 2 px.
* `DatabarBarHeight60Pixels.png` – lo stesso codice a barre con il doppio dell'altezza verticale.

Apri una delle immagini in qualsiasi visualizzatore; vedrai un simbolo GS1 DataBar Omni‑Directional pulito, pronto per la scansione.

## Domande frequenti risposte

| Domanda | Risposta |
|----------|--------|
| *Posso usare i millimetri invece dei pixel?* | Sì. Imposta `generator.Parameters.Barcode.XDimension.Millimeters` e `BarHeight.Millimeters`. La libreria converte in pixel del dispositivo in base al DPI dell'immagine. |
| *E se ho bisogno di un tipo di codice a barre diverso?* | Sostituisci `EncodeTypes.DatabarOmniDirectional` con qualsiasi altro valore `EncodeTypes` (ad es., `EncodeTypes.QR`). Le proprietà di larghezza e altezza funzionano allo stesso modo. |
| *È possibile generare SVG invece di PNG?* | Usa `BarCodeImageFormat.Svg` nella chiamata `Save`. Le impostazioni di larghezza/altezza rimangono valide. |
| *Devo chiamare `generator.Dispose()`?* | Il `BarcodeGenerator` implementa `IDisposable`. In un'app console puoi avvolgerlo in un blocco `using`, ma per esempi di breve durata è opzionale. |

## Conclusione

Ora sai **come impostare la larghezza** di un codice a barre GS1 DataBar Omni‑Directional e **come cambiare l'altezza** utilizzando l'API Aspose.Barcode in C#. L'esempio completo dimostra come creare un generatore, configurare `XDimension` e `BarHeight`, e salvare file PNG con diverse dimensioni verticali.

Da qui puoi:

* Sperimentare con altri `EncodeTypes` (ad es., QR, Code128).
* Renderizzare in formati ad alta risoluzione come TIFF per la stampa.
* Integrare il generatore in una web API che restituisce codici a barre al volo.

Buona programmazione, e che i tuoi codici a barre vengano sempre letti correttamente!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo passo per aiutarti a padroneggiare ulteriori funzionalità dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come cambiare l'altezza del codice a barre in C# – Guida completa](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Esempio di generatore di codici a barre in C# – impostare larghezza e altezza](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [Come usare un generatore di codici a barre C# per creare codici a barre DataBar Omni‑directional](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}