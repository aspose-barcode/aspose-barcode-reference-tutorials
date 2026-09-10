---
category: general
date: 2026-07-27
description: Crea un'immagine di codice a barre omnidirezionale usando Aspose.BarCode.
  Scopri come generare il codice a barre con Aspose, regolare il rapporto d'aspetto
  e salvare file PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional barcode image
- generate barcode with aspose
language: it
lastmod: 2026-07-27
og_description: Crea un'immagine di codice a barre omnidirezionale usando Aspose.
  Segui questa guida per generare il codice a barre con Aspose, regolare i rapporti
  d'aspetto e esportare i PNG.
og_image_alt: Screenshot of two omnidirectional barcode images with different aspect
  ratios
og_title: Crea immagine di codice a barre omnidirezionale con Aspose – Passo dopo
  passo
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  headline: Create Omnidirectional Barcode Image with Aspose – Full Guide
  type: TechArticle
- description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  name: Create Omnidirectional Barcode Image with Aspose – Full Guide
  steps:
  - name: 1. Different Image Formats
    text: 'Aspose supports BMP, JPEG, TIFF, and SVG in addition to PNG. Swap the enum
      value:'
  - name: 2. Customizing Colors
    text: 'You might need a white barcode on a dark background. Set `ForeColor` and
      `BackColor`:'
  - name: 3. Handling Invalid Aspect Ratios
    text: 'Aspose validates the range (usually 5‑50). If you pass an out‑of‑range
      value, an `ArgumentException` is thrown. Wrap the save call in a try‑catch to
      give a friendly message:'
  - name: 4. Batch Generation
    text: When you have a list of GTINs, loop over them, update `CodeText`, and save
      each file with a unique name. The generator object can be reused, keeping memory
      usage low.
  type: HowTo
tags:
- barcode
- Aspose
- C#
- image-generation
title: Crea immagine di codice a barre omnidirezionale con Aspose – Guida completa
url: /it/python-java/general/create-omnidirectional-barcode-image-with-aspose-full-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea immagine di codice a barre omnidirezionale con Aspose – Guida completa

Hai mai avuto bisogno di **creare un'immagine di codice a barre omnidirezionale** ma non eri sicuro di quale libreria scegliere? Non sei il solo. In molti progetti di logistica e retail, il formato DataBar Stacked Omnidirectional è il segreto per una codifica compatta e ad alta densità.  

La buona notizia? Con **Aspose.BarCode** puoi generare quel codice a barre in poche righe, modificare il suo rapporto d'aspetto e salvare il PNG direttamente su disco. Di seguito vedrai esattamente come **generare un codice a barre con Aspose**, perché ogni impostazione è importante e a cosa fare attenzione quando cambi il rapporto d'aspetto.

---

## Cosa copre questo tutorial

Percorreremo l'intero ciclo di vita:

1. Configurare la cartella di output.  
2. Istanziare un generatore DataBar Stacked Omnidirectional.  
3. Configurare le dimensioni in pixel e i rapporti d'aspetto.  
4. Salvare il codice a barre come file PNG.  
5. Estendere l'esempio per altri formati e casi limite.  

Al termine avrai un'app console C# pronta all'uso che genera due immagini di codice a barre distinte. Nessuno strumento esterno, solo puro codice Aspose.

**Prerequisiti**

- .NET 6.0 SDK o successivo (il codice funziona anche su .NET Framework 4.7.2).  
- Pacchetto NuGet Aspose.BarCode per .NET (`Install-Package Aspose.BarCode`).  
- Una cartella su disco dove poter scrivere le immagini.  

Se hai già tutto questo, immergiamoci.

---

## Passo 1: Prepara la cartella di output

Prima di tutto, indica al programma dove salvare i file PNG. Hard‑coding di un percorso funziona per una demo, ma in produzione probabilmente lo leggerai dalla configurazione.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Define the folder where the images will be saved
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);   // ensures the folder exists
```

*Perché è importante:* `Directory.CreateDirectory` è idempotente; non genera eccezione se la cartella esiste già, risparmiandoti un blocco try‑catch.

---

## Passo 2: Crea un generatore DataBar Stacked Omnidirectional

Ora avviamo il generatore con il tipo di codifica specifico e dati di esempio. La stringa `"(01)12345678901231"` segue la sintassi dell'Identificatore di Applicazione GS1 per un GTIN a 14 cifre.

```csharp
        // Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

*Spiegazione:* `EncodeTypes.DatabarStackedOmniDirectional` indica ad Aspose di usare la variante omnidirezionale, leggibile da qualsiasi direzione—perfetta per etichette piccole che potrebbero essere ruotate.

---

## Passo 3: Imposta i parametri comuni del codice a barre

Prima di renderizzare qualsiasi cosa, definiamo la dimensione dell'elemento più piccolo (X‑Dimension). Un valore di **2 pixel** produce un'immagine nitida senza gonfiare le dimensioni del file.

```csharp
        // Step 3: Set common barcode parameters (pixel size of the smallest element)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Consiglio:* Se ti serve una risoluzione più alta per la stampa, aumenta a 3 o 4. Ricorda che X‑Dimensions più grandi aumentano sia larghezza sia altezza proporzionalmente.

---

## Passo 4: Genera e salva con Rapporto d'aspetto 15

La famiglia DataBar ti permette di regolare il **rapporto d'aspetto**, che controlla la relazione altezza‑larghezza. Un rapporto d'aspetto di **15** è il valore predefinito più comune per i codici a barre omnidirezionali.

```csharp
        // Step 4: Generate a barcode with an aspect ratio of 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
```

*Cosa vedrai:* Un codice a barre relativamente alto che si adatta comodamente a un'etichetta di 2 × 1 cm. Il formato PNG preserva la qualità lossless, ideale per ulteriori elaborazioni o stampe.

---

## Passo 5: Cambia il rapporto d'aspetto a 30 e salva di nuovo

Vuoi un codice a barre più “schiacciato”? Basta modificare la proprietà `AspectRatio` e chiamare nuovamente `Save`. Non è necessario ricreare il generatore.

```csharp
        // Step 5: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
    }
}
```

*Perché riutilizzare lo stesso generatore?* Gli oggetti Aspose sono leggeri; cambiare una proprietà e risalvare è più veloce che costruire una nuova istanza, e garantisce che le stesse impostazioni di codifica (es. X‑Dimension) rimangano coerenti.

---

## Esempio completo funzionante

Mettendo tutto insieme, ecco il programma completo e autonomo che puoi copiare‑incollare in un nuovo progetto console.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // Initialize generator with omnidirectional DataBar
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Common settings
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // First image – aspect ratio 15
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio15.png");

        // Second image – aspect ratio 30
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio30.png");
    }
}
```

**Output previsto**

L'esecuzione del programma crea una sottocartella `Barcodes` contenente:

- `DatabarAspectRatio15.png` – aspetto più alto, classico.  
- `DatabarAspectRatio30.png` – aspetto più piatto, migliore per etichette larghe.  

Entrambe le immagini codificano gli stessi dati GTIN; differiscono solo nelle proporzioni visive.

---

## Estendere l'esempio (casi limite e variazioni)

### 1. Formati immagine diversi

Aspose supporta BMP, JPEG, TIFF e SVG oltre a PNG. Sostituisci il valore dell'enum:

```csharp
barcodeGenerator.Save(Path.Combine(outputFolder, "Databar.svg"),
                      BarCodeImageFormat.Svg);
```

SVG è basato su vettori, il che significa che puoi scalarlo senza perdere nitidezza—utile per applicazioni web responsive.

### 2. Personalizzare i colori

Potresti aver bisogno di un codice a barre bianco su sfondo scuro. Imposta `ForeColor` e `BackColor`:

```csharp
barcodeGenerator.Parameters.Barcode.ForeColor = System.Drawing.Color.White;
barcodeGenerator.Parameters.Barcode.BackColor = System.Drawing.Color.Black;
```

### 3. Gestire rapporti d'aspetto non validi

Aspose valida l'intervallo (solitamente 5‑50). Se passi un valore fuori intervallo, viene sollevata un'`ArgumentException`. Avvolgi la chiamata a `Save` in un try‑catch per fornire un messaggio amichevole:

```csharp
try
{
    barcodeGenerator.Save(...);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid aspect ratio: {ex.Message}");
}
```

### 4. Generazione batch

Quando hai una lista di GTIN, itera su di essa, aggiorna `CodeText` e salva ogni file con un nome univoco. L'oggetto generatore può essere riutilizzato, mantenendo basso l'uso di memoria.

---

## Trappole comuni e consigli professionali

- **Non dimenticare mai di impostare `XDimension`** prima di salvare; il valore predefinito (0,33 mm) può produrre immagini sfocate su display a bassa risoluzione.  
- **Il rapporto d'aspetto è altezza‑larghezza**, non il contrario. Un numero più grande rende il codice a barre *più corto* verticalmente.  
- **Percorsi file:** Usa `Path.Combine` per evitare problemi di separatori specifici della piattaforma—soprattutto se il tuo codice gira in container Linux.  
- **Licenza:** Aspose.BarCode è commerciale. In modalità trial appare una filigrana sull'immagine. Registra una licenza subito per evitare sorprese in produzione.

---

## Conclusione

Ora sai come **creare un'immagine di codice a barre omnidirezionale** usando Aspose, regolare il rapporto d'aspetto ed esportare file PNG—tutto in meno di 30 righe di C#. Questo tutorial ha mostrato il processo passo‑a‑passo, spiegato perché ogni impostazione è importante e ha coperto estensioni come formati diversi, colori e generazione batch.

Pronto per la prossima sfida? Prova a generare QR code, incorporare il codice a barre in un PDF o integrare l'output in un'API ASP.NET Core. Gli stessi principi di **generare un codice a barre con Aspose** si applicano a tutti i tipi di codice a barre, così potrai riutilizzare ciò che hai imparato oggi.

Hai domande o vuoi condividere le tue personalizzazioni? Lascia un commento qui sotto—buona programmazione!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑a‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API e a esplorare approcci alternativi di implementazione nei tuoi progetti.

- [Come generare un codice a barre Aztec con rapporto d'aspetto personalizzato usando Aspose.BarCode per .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Come creare un codice a barre Aspose Java - Regolare la qualità dell'immagine](/barcode/english/java/image-manipulation/adjusting-image-quality-barcode/)
- [Come generare un'immagine di codice a barre in Java con Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}