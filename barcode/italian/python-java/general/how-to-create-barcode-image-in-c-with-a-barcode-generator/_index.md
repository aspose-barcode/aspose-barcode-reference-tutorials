---
category: general
date: 2026-10-02
description: Crea un'immagine di codice a barre in C# utilizzando un generatore di
  codici a barre, controlla la dimensione dei pixel del codice a barre e regola l'altezza
  del codice a barre per dimensioni personalizzate.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- barcode pixel size
- adjust barcode height
- custom barcode dimensions
language: it
lastmod: 2026-10-02
og_description: Crea un'immagine di codice a barre in C# con un generatore di codici
  a barre. Impara a impostare la dimensione dei pixel del codice a barre, regolare
  l'altezza del codice a barre e definire dimensioni personalizzate del codice a barre.
og_image_alt: Sample DataBar Omnidirectional barcode saved at 30 px height and 60 px
  height
og_title: Crea immagine di codice a barre in C# – guida al generatore di codici a
  barre e alle dimensioni personalizzate
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create barcode image in C# using a barcode generator, control barcode
    pixel size and adjust barcode height for custom barcode dimensions.
  headline: How to create barcode image in C# with a barcode generator
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: Come creare un'immagine di codice a barre in C# con un generatore di codici
  a barre
url: /it/python-java/general/how-to-create-barcode-image-in-c-with-a-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un'immagine di codice a barre in C# con un generatore di codici a barre

Se hai bisogno di **creare immagini di codice a barre** programmaticamente, questa guida ti mostra una soluzione completa, pronta‑all'uso in C#. Utilizzando un generatore di codici a barre puoi controllare la **dimensione dei pixel del codice a barre**, **regolare l'altezza del codice a barre** e definire **dimensioni personalizzate del codice a barre** senza uscire dal tuo IDE.

Imparerai a generare due file PNG—uno con un'altezza delle barre di 30 px e un altro con 60 px—mantenendo costante la larghezza del modulo. I passaggi funzionano con qualsiasi tipo di codice a barre supportato dalla libreria, così potrai adattarli a QR code, Code 128 o altre simbologie.

## Cosa ti serve

- .NET 6.0 o versioni successive (il codice si compila anche con .NET Framework 4.8)
- Un riferimento alla libreria di codici a barre (ad es., Aspose.BarCode per .NET o qualsiasi classe `BarcodeGenerator` compatibile)
- Conoscenza di base di C#
- Permessi di scrittura su una cartella dove verranno salvati i file PNG

## Passo 1: Inizializzare il generatore di codici a barre per **creare un'immagine di codice a barre**

Per prima cosa, importa gli spazi dei nomi necessari e istanzia un `BarcodeGenerator`. Il costruttore riceve il tipo di codice a barre (`EncodeTypes.DatabarOmniDirectional`) e la stringa di dati che desideri codificare.

```csharp
using Aspose.BarCode.Generation;   // or the namespace of your barcode library
using Aspose.BarCode;               // for BarCodeImageFormat
using System.IO;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator to create barcode image
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Creare il generatore è la base per qualsiasi flusso di lavoro **barcode generator c#**. Alloca la tela di disegno interna e prepara i dati per il rendering.

## Passo 2: Definire la **dimensione dei pixel del codice a barre** e l'altezza iniziale delle barre

La qualità visiva dell'immagine finale dipende da due parametri:

| Parametro | Significato |
|-----------|------------|
| `XDimension.Pixels` | Larghezza di un singolo modulo (l'elemento più piccolo nero/bianco). |
| `BarHeight.Pixels` | Altezza delle barre per l'immagine corrente. |

```csharp
        // Step 2: Set common visual parameters – module size and initial bar height
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // barcode pixel size (module width)
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first image height in pixels
```

Mantenere costante la **dimensione dei pixel del codice a barre** cambiando l'altezza ti consente di creare **dimensioni personalizzate del codice a barre** che corrispondono alle linee guida del brand o ai requisiti di scansione.

## Passo 3: Salvare il primo file PNG (altezza 30 px)

Ora scrivi l'immagine su disco. Il metodo `Save` accetta il percorso del file e il formato immagine desiderato.

```csharp
        // Step 3: Save the first barcode image (30 px height)
        string outputFolder = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputFolder); // ensure the folder exists

        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);
```

Il file risultante è una **barcode image** con un'altezza delle barre di 30 px e una larghezza del modulo di 2 px, perfetta per etichette compatte.

## Passo 4: **Regolare l'altezza del codice a barre** per una versione più grande

Per generare una seconda immagine con una dimensione visiva diversa, è necessario modificare solo la proprietà `BarHeight.Pixels`. Questo dimostra quanto sia semplice **regolare l'altezza del codice a barre** senza ricreare il generatore.

```csharp
        // Step 4: Change the bar height to 60 px for a larger barcode
        barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

Modificare l'altezza mantenendo la **dimensione dei pixel del codice a barre** garantisce che le barre rimangano nitide e che il rapporto d'aspetto complessivo rimanga coerente.

## Passo 5: Salvare il secondo file PNG (altezza 60 px)

Infine, salva la versione più grande.

```csharp
        // Step 5: Save the second barcode image (60 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);
    }
}
```

Ora hai due **dimensioni personalizzate del codice a barre** salvate una accanto all'altra:

- `DatabarBarHeight30Pixels.png` – altezza barra 30 px
- `DatabarBarHeight60Pixels.png` – altezza barra 60 px

Entrambe le immagini condividono la stessa **dimensione dei pixel del codice a barre** di 2 px, garantendo coerenza visiva tra le diverse dimensioni.

## Perché queste impostazioni sono importanti

- **Dimensione dei pixel del codice a barre** (`XDimension`) influenza la leggibilità da parte dello scanner. Una larghezza di 2 px è un valore predefinito comune che bilancia dimensione del file e affidabilità della scansione.
- **Altezza delle barre** determina quanto alta appare il codice a barre su un'etichetta. Alcuni scanner al dettaglio richiedono un'altezza minima; altri consentono barre più alte per motivi estetici.
- Mantenere l'istanza del generatore attiva modificando solo `BarHeight` riduce le allocazioni di memoria e velocizza l'elaborazione in batch.

## Casi limite e consigli di best‑practice

| Situazione | Approccio consigliato |
|------------|-----------------------|
| **Formati immagine diversi** (JPEG, BMP) | Modifica `BarCodeImageFormat.Jpeg` o `.Bmp` nella chiamata `Save`. JPEG è più piccolo ma può introdurre artefatti di compressione. |
| **Output ad alta risoluzione** (es., 300 DPI) | Aumenta `XDimension.Pixels` proporzionalmente (es., 4 px) e regola `BarHeight.Pixels` per mantenere la stessa dimensione fisica. |
| **Stringhe di dati dinamiche** | Racchiudi la creazione del generatore in un metodo che accetta la stringa di dati come parametro, quindi riutilizza la stessa istanza `barcode` per più salvataggi. |
| **Generazione batch thread‑safe** | Istanzia un `BarcodeGenerator` separato per thread o utilizza un pool thread‑local per evitare condizioni di gara. |
| **Errori di permessi del file system** | Verifica che `outputFolder` esista e che il processo abbia i permessi di scrittura; gestisci `IOException` in modo appropriato. |

## Elenco completo del codice sorgente

Di seguito trovi il programma completo e autonomo che puoi copiare, incollare ed eseguire.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.IO;

class Program
{
    static void Main()
    {
        // Create a barcode generator – this is the core of the create barcode image workflow
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // Define barcode pixel size (module width) and initial height
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // barcode pixel size
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first image height

        // Prepare output folder
        string outputFolder = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputFolder);

        // Save first image (30 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);

        // Adjust height for the second image
        barcode.Parameters.Barcode.BarHeight.Pixels = 60; // adjust barcode height

        // Save second image (60 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);
    }
}
```

### Output previsto

Dopo aver eseguito il programma, la cartella `YOUR_DIRECTORY` contiene due file PNG:

- **DatabarBarHeight30Pixels.png** – un codice a barre compatto adatto a etichette piccole.
- **DatabarBarHeight60Pixels.png** – una versione più grande ideale per applicazioni ad alta visibilità.

Entrambi i file possono essere aperti con qualsiasi visualizzatore di immagini, stampati o incorporati in PDF.

## Conclusione

Ora sai come **creare immagini di codice a barre** in C# con un **barcode generator c#**, controllare la **dimensione dei pixel del codice a barre**, **regolare l'altezza del codice a barre** e produrre **dimensioni personalizzate del codice a barre** che soddisfano requisiti specifici di scansione o di branding. L'esempio dimostra un modello pulito e ripetibile che scala alla elaborazione batch o a simbologie diverse.

### Cosa esplorare dopo

- [Come creare un'immagine di codice a barre in C# con altezza regolabile](/barcode/english/python-java/general/how-to-create-barcode-image-in-c-with-adjustable-height/)
- [Come generare un set di codici a barre di dimensioni personalizzate e salvare l'immagine in C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [Creare un'immagine di codice a barre in C# con esempio di generatore di codici a barre](/barcode/english/python-java/general/create-barcode-image-c-with-barcode-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}