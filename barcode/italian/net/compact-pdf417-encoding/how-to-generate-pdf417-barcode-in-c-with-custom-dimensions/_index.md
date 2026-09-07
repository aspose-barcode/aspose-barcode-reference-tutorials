---
category: general
date: 2026-09-07
description: Genera il codice a barre PDF417 in C# e impara a impostare le dimensioni
  del codice a barre per un controllo preciso. Segui questa guida passo passo per
  creare un'immagine PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- how to set barcode dimensions
language: it
lastmod: 2026-09-07
og_description: Genera un codice a barre PDF417 in C# e scopri come impostare le dimensioni
  del codice a barre. Questo tutorial mostra un esempio completo e funzionante.
og_image_alt: Generated PDF417 barcode image with custom dimensions
og_title: Genera codice a barre PDF417 in C# – guida completa con dimensioni
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  headline: How to generate PDF417 barcode in C# with custom dimensions
  type: TechArticle
- description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  name: How to generate PDF417 barcode in C# with custom dimensions
  steps:
  - name: Expected output
    text: '- **File:** `Pdf417Layout.png` (PNG, lossless) - **Dimensions:** Determined
      by `XDimension` (2 px) × (columns × rows) matrix - **Content:** A scannable
      PDF417 barcode encoding the Unicode string `Åspóse.Barcóde©`'
  - name: What if I need a larger image for printing?
    text: Increase `XDimension.Pixels` to 4 or 5. Larger values produce a higher‑resolution
      barcode but also increase file size.
  - name: Can I encode more data than the example string?
    text: Yes. PDF417 can hold up to 1,850 characters. Just replace the text argument
      in the `BarcodeGenerator` constructor. If the data exceeds the matrix capacity,
      the library automatically adds extra rows.
  - name: How does error correction work?
    text: 'PDF417 includes built‑in error correction. You can adjust its level via:'
  - name: What if the barcode appears blurry on screen?
    text: 'Make sure the output image’s DPI matches the display environment. You can
      set DPI when saving:'
  - name: Next steps
    text: '- Explore **how to generate PDF417 barcode** with different image formats
      (JPEG, BMP). - Learn **how to set barcode dimensions** dynamically based on
      user input or device DPI. - Integrate the barcode generation into an ASP.NET
      Core API to serve barcodes on demand.'
  type: HowTo
tags:
- barcode generation
- PDF417
- C#
title: Come generare il codice a barre PDF417 in C# con dimensioni personalizzate
url: /it/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come generare un codice a barre PDF417 in C# con dimensioni personalizzate

Se hai bisogno di **generare un codice a barre PDF417** in un'applicazione .NET, questa guida ti mostra esattamente come farlo. Vedrai un esempio completo e eseguibile che crea un'immagine PNG consentendoti di controllare le dimensioni del codice a barre.

Generare un codice a barre PDF417 è una necessità comune per sistemi di inventario, carte d'imbarco e documenti sicuri. In questo tutorial imparerai anche **come impostare le dimensioni del codice a barre** in modo che l'output corrisponda alle esigenze del tuo layout.

## Prerequisiti

- .NET 6.0 SDK o versioni successive installate  
- Visual Studio 2022 (o qualsiasi IDE compatibile con C#)  
- Il pacchetto NuGet **Aspose.BarCode for .NET** (o qualsiasi libreria compatibile che supporti PDF417)  

Puoi aggiungere il pacchetto con il seguente comando:

```bash
dotnet add package Aspose.BarCode
```

## Passo 1: Creare un generatore di codice a barre PDF417

Il primo passo è istanziare un `BarcodeGenerator` con il tipo `EncodeTypes.Pdf417` e il testo che desideri codificare. L'oggetto generatore contiene tutte le impostazioni per il codice a barre.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");
```

**Perché è importante:** L'enumerazione `EncodeTypes.Pdf417` indica alla libreria di utilizzare la simbologia PDF417, che supporta grandi quantità di dati e correzione degli errori. La stringa di testo può contenere caratteri Unicode, così puoi codificare simboli internazionali senza lavoro aggiuntivo.

## Passo 2: Come impostare le dimensioni del codice a barre

Controllare la dimensione di ogni modulo (il più piccolo quadrato nero/bianco) determina la risoluzione complessiva dell'immagine. La proprietà `XDimension.Pixels` imposta la larghezza in pixel di un modulo.

```csharp
        // Step 2: Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Perché è importante:** Un valore `XDimension` più grande produce un'immagine ad alta risoluzione, utile per la stampa o la scansione da una certa distanza. Al contrario, un valore più piccolo riduce le dimensioni del file per l'uso web.

## Passo 3: Definire il layout PDF417 (colonne e righe)

PDF417 consente di influenzare la forma della matrice specificando il numero di colonne e righe. Questo può influire sulla leggibilità e sulla dimensione fisica del codice a barre.

```csharp
        // Step 3: Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

**Perché è importante:** Regolare colonne e righe ti permette di adattare il codice a barre a uno spazio specifico o di soddisfare i requisiti di rapporto d'aspetto dello scanner. La libreria aggiunge automaticamente del padding se i dati non riempiono completamente la matrice.

## Passo 4: Salvare il codice a barre come immagine PNG

Infine, scrivi il codice a barre generato su un file. PNG conserva la qualità lossless, rendendolo ideale per ulteriori elaborazioni.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

Quando esegui il programma, `Pdf417Layout.png` appare nella cartella di output del progetto. L'immagine è simile a questa:

![Immagine del codice a barre PDF417 generato con dimensioni personalizzate](og_image_placeholder.png)

*Testo alternativo dell'immagine: Immagine del codice a barre PDF417 generato con dimensioni personalizzate*  

**Perché è importante:** Salvare come PNG garantisce che le esatte dimensioni dei moduli impostate vengano mantenute, il che è cruciale per le applicazioni di scansione successive.

## Esempio completo in un unico blocco

Di seguito trovi il programma completo che puoi copiare, incollare ed eseguire senza modifiche (tranne il percorso di output, se desiderato).

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

### Output previsto

- **File:** `Pdf417Layout.png` (PNG, lossless)  
- **Dimensions:** Determinate da `XDimension` (2 px) × matrice (colonne × righe)  
- **Content:** Un codice a barre PDF417 scansionabile che codifica la stringa Unicode `Åspóse.Barcóde©`

## Domande comuni e casi particolari

### E se ho bisogno di un'immagine più grande per la stampa?

Aumenta `XDimension.Pixels` a 4 o 5. Valori più alti producono un codice a barre a risoluzione più alta ma aumentano anche le dimensioni del file.

### Posso codificare più dati rispetto alla stringa di esempio?

Sì. PDF417 può contenere fino a 1.850 caratteri. Basta sostituire l'argomento di testo nel costruttore `BarcodeGenerator`. Se i dati superano la capacità della matrice, la libreria aggiunge automaticamente righe extra.

### Come funziona la correzione degli errori?

PDF417 include la correzione degli errori integrata. Puoi regolare il suo livello tramite:

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // 0‑8, higher = more correction
```

Livelli più alti aumentano la robustezza a costo di codici a barre più grandi.

### E se il codice a barre appare sfocato sullo schermo?

Assicurati che i DPI dell'immagine di output corrispondano all'ambiente di visualizzazione. Puoi impostare i DPI al momento del salvataggio:

```csharp
barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png, 300);
```

## Consigli professionali

- **Consiglio pro:** Testa sempre il codice a barre generato con lo scanner reale che intendi utilizzare. Dispositivi diversi hanno tolleranze variabili per la dimensione dei moduli e le zone silenziose.  
- **Attenzione a:** Valori di `XDimension` molto piccoli (< 1 px) possono apparire come linee invisibili su schermi ad alta DPI.  
- **Suggerimento per app web:** Servi il PNG con `Cache-Control: public, max-age=86400` per ridurre il sovraccarico di generazione ripetuta.

## Conclusione

Ora sai come **generare un codice a barre PDF417** in C# e impostare con precisione **le dimensioni del codice a barre** per soddisfare qualsiasi requisito. L'esempio completo e eseguibile dimostra come creare un'immagine PNG con layout di colonne/righe personalizzato e dimensione del modulo, pronta per la stampa o la distribuzione digitale.

### Prossimi passi

- Esplora **come generare un codice a barre PDF417** con diversi formati immagine (JPEG, BMP).  
- Impara **come impostare le dimensioni del codice a barre** in modo dinamico in base all'input dell'utente o ai DPI del dispositivo.  
- Integra la generazione del codice a barre in un'API ASP.NET Core per fornire codici a barre su richiesta.

Sentiti libero di sperimentare con altre impostazioni PDF417 come correzione degli errori, margini e colore. Buona programmazione!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come impostare il livello di errore nel codice a barre PDF417 – Guida completa](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Come salvare il codice a barre in C# – Generare codici a barre PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Generare codice a barre PDF417 in C# – Guida completa](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}