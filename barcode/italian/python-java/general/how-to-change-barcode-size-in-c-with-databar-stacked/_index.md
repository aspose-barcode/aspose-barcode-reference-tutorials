---
category: general
date: 2026-08-22
description: Come modificare la dimensione del codice a barre in C# usando il generatore
  DataBar Stacked Omni‑Directional. Impara a impostare la dimensione X e il rapporto
  d'aspetto per l'output PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to change barcode size
- DataBar Stacked Omni‑Directional barcode
- C# barcode generator
- barcode aspect ratio
- X‑dimension pixels
- BarCodeImageFormat PNG
language: it
lastmod: 2026-08-22
og_description: Come modificare le dimensioni del codice a barre in C# con il generatore
  DataBar Stacked Omni‑Directional. Segui la guida passo‑passo per regolare la dimensione
  X e il rapporto d'aspetto.
og_image_alt: Screenshot showing how to change barcode size in C#
og_title: Come modificare le dimensioni del codice a barre in C# – guida completa
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to change barcode size in C# using the DataBar Stacked Omni‑Directional
    generator. Learn to set X‑dimension and aspect ratio for PNG output.
  headline: How to change barcode size in C# with DataBar Stacked
  type: TechArticle
- description: How to change barcode size in C# using the DataBar Stacked Omni‑Directional
    generator. Learn to set X‑dimension and aspect ratio for PNG output.
  name: How to change barcode size in C# with DataBar Stacked
  steps:
  - name: Create a DataBar Stacked Omni‑Directional barcode generator
    text: The generator object holds all barcode settings. By passing `EncodeTypes.DatabarStackedOmniDirectional`
      and sample data, you create a valid barcode ready for further customization.
  - name: Set the basic module size (X‑dimension) in pixels
    text: The X‑dimension defines the width of a single barcode module. Adjusting
      it changes the overall width and height proportionally.
  - name: Change the barcode aspect ratio to 15 and save the image
    text: The **barcode aspect ratio** controls the height‑to‑width relationship.
      An aspect ratio of 15 yields a relatively tall barcode.
  - name: Change the barcode aspect ratio to 30 and save the new image
    text: Increasing the aspect ratio to 30 makes the barcode even taller, illustrating
      the flexibility of size adjustments.
  - name: Verify the generated images
    text: Open the PNG files in any image viewer. You should see two barcodes with
      identical width (controlled by the X‑dimension) but different heights (controlled
      by the aspect ratio). If the images appear blurry, increase the X‑dimension
      pixels; if they are too tall, lower the aspect ratio.
  - name: What to explore next
    text: '* **Custom colors** – experiment with `barcodeGenerator.Parameters.Barcode.ForeColor`
      and `BackColor` to match brand guidelines. * **Different barcode types** – replace
      `EncodeTypes.DatabarStackedOmniDirectional` with `EncodeTypes.QR` or `EncodeTypes.Code128`
      to see how size parameters differ across'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Come cambiare la dimensione del codice a barre in C# con DataBar Stacked
url: /it/python-java/general/how-to-change-barcode-size-in-c-with-databar-stacked/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come modificare le dimensioni del codice a barre in C# con DataBar Stacked

Se hai bisogno di **come modificare le dimensioni del codice a barre** in un'applicazione .NET, questa guida mostra i passaggi esatti usando il generatore di codici a barre DataBar Stacked Omni‑Directional. Vedrai come controllare la X‑dimension in pixel, regolare il rapporto d'aspetto del codice a barre e salvare il risultato come file PNG.

Modificare le dimensioni del codice a barre è spesso necessario quando lo spazio dell'etichetta stampata è limitato o quando è richiesta un'immagine ad alta risoluzione per i canali digitali. Questo tutorial copre tutto ciò di cui hai bisogno, dall'inizializzazione del generatore alla produzione di due immagini con dimensioni diverse.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6.0 SDK o versioni successive installate  
* Un riferimento al pacchetto NuGet **Aspose.BarCode for .NET**  
* Familiarità di base con la sintassi C#  

Non è necessaria alcuna configurazione aggiuntiva; il codice funziona su Windows, Linux o macOS.

## Come modificare le dimensioni del codice a barre in C# – passo passo

Le sezioni seguenti suddividono il processo in passaggi discreti e riutilizzabili. Ogni passo spiega **perché** il codice è necessario, non solo **cosa** fa.

### Passo 1: Creare un generatore di codice a barre DataBar Stacked Omni‑Directional

L'oggetto generatore contiene tutte le impostazioni del codice a barre. Passando `EncodeTypes.DatabarStackedOmniDirectional` e dati di esempio, crei un codice a barre valido pronto per ulteriori personalizzazioni.

```csharp
// Step 1: Create a DataBar Stacked Omni‑Directional barcode generator with sample data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

*Perché è importante* – La classe **C# barcode generator** incapsula l'algoritmo di codifica. Iniziare con un generatore valido garantisce che le successive modifiche di dimensione influenzino il tipo di codice a barre corretto.

### Passo 2: Impostare la dimensione di base del modulo (X‑dimension) in pixel

La X‑dimension definisce la larghezza di un singolo modulo del codice a barre. Regolandola, si modificano proporzionalmente larghezza e altezza complessive.

```csharp
// Step 2: Define the basic module size (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Perché è importante* – Una X‑dimension più grande produce un codice a barre più grande, utile per stampanti a bassa risoluzione. Al contrario, un valore più piccolo crea un codice a barre compatto adatto a etichette piccole.

### Passo 3: Modificare il rapporto d'aspetto del codice a barre a 15 e salvare l'immagine

Il **barcode aspect ratio** controlla la relazione altezza‑larghezza. Un rapporto d'aspetto di 15 genera un codice a barre relativamente alto.

```csharp
// Step 3: Set the DataBar aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

*Perché è importante* – Diversi dispositivi di scansione hanno requisiti ottimali di rapporto d'aspetto. Impostare il rapporto a 15 dimostra come **come modificare le dimensioni del codice a barre** modificando l'altezza mantenendo la larghezza definita dalla X‑dimension.

#### Output previsto

Il file `DatabarAspectRatio15.png` mostra un codice a barre DataBar Stacked Omni‑Directional più alto rispetto al valore predefinito. La larghezza del codice a barre riflette la X‑dimension di 2 pixel, e l'altezza segue il rapporto 15.

### Passo 4: Modificare il rapporto d'aspetto del codice a barre a 30 e salvare la nuova immagine

Aumentare il rapporto d'aspetto a 30 rende il codice a barre ancora più alto, illustrando la flessibilità delle regolazioni di dimensione.

```csharp
// Step 4: Change the DataBar aspect ratio to 30 and save the new image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

*Perché è importante* – Scambiando il valore del **barcode aspect ratio**, vedi immediatamente come **come modificare le dimensioni del codice a barre** senza ricreare il generatore. Questo fa risparmiare tempo di elaborazione in scenari batch.

#### Output previsto

Il file `DatabarAspectRatio30.png` è visibilmente più alto dell'immagine precedente, confermando che il rapporto d'aspetto influisce direttamente sull'altezza del codice a barre.

### Passo 5: Verificare le immagini generate

Apri i file PNG in qualsiasi visualizzatore di immagini. Dovresti vedere due codici a barre con larghezza identica (controllata dalla X‑dimension) ma altezze diverse (controllate dal rapporto d'aspetto). Se le immagini appaiono sfocate, aumenta i pixel della X‑dimension; se sono troppo alte, riduci il rapporto d'aspetto.

```csharp
// Optional verification code – load images and print dimensions
using (var img15 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio15.png"))
using (var img30 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio30.png"))
{
    Console.WriteLine($"15‑ratio size: {img15.Width}×{img15.Height}");
    Console.WriteLine($"30‑ratio size: {img30.Width}×{img30.Height}");
}
```

*Perché è importante* – La verifica programmatica assicura che le modifiche di dimensione siano state applicate correttamente, cosa cruciale per le pipeline di build automatizzate.

## Varianti comuni e casi limite

| Situazione | Regolazione | Motivo |
|------------|-------------|--------|
| **Etichette molto piccole** | Imposta `XDimension.Pixels = 1` e `AspectRatio = 10` | Riduce l'ingombro complessivo mantenendo la leggibilità |
| **Stampa ad alta risoluzione** | Imposta `XDimension.Pixels = 4` e `AspectRatio = 20` | Aumenta la densità di pixel per un output nitido |
| **Formato immagine diverso** | Sostituisci `BarCodeImageFormat.Png` con `BarCodeImageFormat.Jpeg` | Utile quando il supporto PNG è limitato |
| **Dati dinamici** | Passa una stringa variabile al costruttore `BarcodeGenerator` | Genera codici a barre per ogni prodotto automaticamente |

Quando devi generare molti codici a barre con dimensioni variabili, racchiudi i passaggi in un metodo:

```csharp
void GenerateDatabar(string data, int xDim, int aspectRatio, string filePath)
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
    generator.Parameters.Barcode.XDimension.Pixels = xDim;
    generator.Parameters.Barcode.DataBar.AspectRatio = aspectRatio;
    generator.Save(filePath, BarCodeImageFormat.Png);
}
```

Chiamando `GenerateDatabar("(01)98765432109876", 3, 25, "output.png")` si produce un codice a barre con dimensioni personalizzate in una singola riga di codice.

## Consigli professionali per modifiche di dimensione affidabili

* **Imposta sempre la X‑dimension prima del rapporto d'aspetto.** Modificare prima il rapporto d'aspetto può causare una scalatura inattesa se la X‑dimension assume un valore predefinito non ideale.  
* **Usa una cartella di output coerente.** Hard‑coding `"YOUR_DIRECTORY"` funziona per le demo, ma in produzione è preferibile `Path.Combine(Environment.CurrentDirectory, "Barcodes")`.  
* **Convalida le dimensioni dell'immagine generata.** Piccole variazioni nella X‑dimension potrebbero non essere evidenti sullo schermo; verificare le dimensioni in pixel garantisce che la modifica abbia avuto effetto.  

## Conclusione

Ora sai **come modificare le dimensioni del codice a barre** in C# usando il generatore DataBar Stacked Omni‑Directional. Regolando i **pixel della X‑dimension** e il **rapporto d'aspetto del codice a barre**, puoi produrre immagini PNG che si adattano a qualsiasi dimensione o requisito di risoluzione dell'etichetta. L'esempio completo e eseguibile sopra dimostra l'intero flusso di lavoro, dalla creazione del generatore alla verifica delle dimensioni.

### Cosa esplorare dopo

* **Colori personalizzati** – sperimenta con `barcodeGenerator.Parameters.Barcode.ForeColor` e `BackColor` per allineare il codice a barre alle linee guida del brand.  
* **Tipi di codice a barre diversi** – sostituisci `EncodeTypes.DatabarStackedOmniDirectional` con `EncodeTypes.QR` o `EncodeTypes.Code128` per vedere come i parametri di dimensione variano tra le simbologie.  
* **Elaborazione batch** – combina il metodo `GenerateDatabar` con un'importazione CSV per creare migliaia di codici a barre automaticamente.

Sentiti libero di adattare gli snippet di codice all'architettura del tuo progetto e lascia che le regolazioni di dimensione del codice a barre migliorino l'affidabilità della scansione e il design visivo. Buon coding!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo passo per aiutarti a padroneggiare ulteriori funzionalità dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come regolare le dimensioni del codice a barre – Rapporto d'aspetto Codablock F con Aspose.BarCode per .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [Come generare un codice a barre Aztec con rapporto d'aspetto personalizzato usando Aspose.BarCode per .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Come generare e regolare l'altezza del codice a barre Databar unidimensionale usando Aspose.BarCode per .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}