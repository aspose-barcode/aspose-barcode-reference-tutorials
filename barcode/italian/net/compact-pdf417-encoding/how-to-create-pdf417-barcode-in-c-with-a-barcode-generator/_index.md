---
category: general
date: 2026-11-17
description: Impara a creare il codice a barre PDF417 in C# – una guida completa su
  come generare il codice a barre da una stringa utilizzando un generatore di codici
  a barre in C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to generate barcode
- c# barcode generator
- generate barcode from string
- create gs1 barcode
language: it
lastmod: 2026-11-17
og_description: Crea rapidamente un codice a barre PDF417 in C#. Questo tutorial mostra
  come generare un codice a barre da una stringa con un generatore di codici a barre
  C# e include il codice sorgente completo.
og_image_alt: Screenshot of a generated PDF417 barcode created with a C# barcode generator
og_title: Crea codice a barre PDF417 in C# – guida passo passo
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  headline: How to create PDF417 barcode in C# with a barcode generator
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  name: How to create PDF417 barcode in C# with a barcode generator
  steps:
  - name: Expected output
    text: '![Generated PDF417 barcode showing the GTIN (01)12345678901234](/images/pdf417-sample.png){:
      .center-image alt="Generated PDF417 barcode created with a C# barcode generator"}'
  - name: Changing the image format
    text: If you prefer JPEG or BMP, just replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`
      or `BarCodeImageFormat.Bmp`. The rest of the code stays identical.
  - name: Adjusting error correction level
    text: PDF417 supports error correction levels 0‑8. Higher levels increase redundancy
      but also enlarge the barcode.
  - name: Generating other GS1 barcodes
    text: 'The same `BarcodeGenerator` can produce **create GS1 barcode** for other
      symbologies, such as `EncodeTypes.Gs1DataMatrix` or `EncodeTypes.Gs1Qr`. Just
      swap the enum value:'
  - name: Handling empty or null data
    text: 'When you **generate barcode from string**, always validate the input:'
  type: HowTo
- questions:
  - answer: Yes. The Aspose.BarCode library targets .NET Standard 2.0, which is compatible
      with .NET Framework 4.6 and later.
    question: Can I use this code on .NET Framework 4.6?
  - answer: 'Set the `Resolution` property before saving: ```csharp generator.Parameters.ImageResolution.DpiX
      = 300; generator.Parameters.ImageResolution.DpiY = 300; ```'
    question: What if I need a higher‑resolution image?
  - answer: 'It will be a standard PDF417 barcode, but it won’t be recognized as a
      GS1‑compliant symbol. Include the `(01)` prefix when you need **create GS1 barcode**
      compliance. ## Conclusion You now know how to **create PDF417 barcode** in C#
      using a robust **c# barcode generator**. The tutorial covered: * In'
    question: Is the barcode still valid without the GS1 Application Identifier?
  type: FAQPage
tags:
- barcode
- C#
- PDF417
- GS1
- code generation
title: Come creare un codice a barre PDF417 in C# con un generatore di codici a barre
url: /it/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-a-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare PDF417 barcode in C# con un barcode generator

Se hai bisogno di **create PDF417 barcode** in a .NET application, questa guida mostra esattamente come farlo. Imparerai **how to generate barcode** da una stringa semplice, configurare la dimensione del simbolo e salvare il risultato come file PNG—tutto usando un affidabile **c# barcode generator**.

Generare codici a barre programmaticamente elimina passaggi manuali e garantisce una qualità costante. In questo tutorial copriremo tutto, dalla configurazione del progetto all'immagine finale, così potrai integrare la creazione di codici a barre in qualsiasi soluzione C# oggi.

## Prerequisiti

* .NET 6.0 SDK o successivo (il codice funziona con .NET Core e .NET Framework)
* Visual Studio 2022 (o qualsiasi IDE che supporti C#)
* Una licenza o una prova gratuita di **Aspose.BarCode for .NET** – la libreria usata negli esempi
* Familiarità di base con la sintassi C#

Non sono necessari pacchetti aggiuntivi; il pacchetto NuGet `Aspose.BarCode` contiene tutte le classi di cui avrai bisogno.

## Passo 1 – Configurare il C# barcode generator

La prima cosa da fare quando **create PDF417 barcode** è istanziare un oggetto `BarcodeGenerator`. Questo oggetto rappresenta il **c# barcode generator** che gestirà la codifica, il rendering e il salvataggio.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for PDF417 with the data to encode
        // The data string follows the GS1 Application Identifier (01) for a GTIN
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417, "(01)12345678901234");
```

*Perché è importante*: L'enumerazione `EncodeTypes.Pdf417` indica alla libreria di utilizzare la simbologia PDF417, lo stesso standard usato per carte d'identità e etichette di trasporto. La stringa `"(01)12345678901234"` è un esempio di **generate barcode from string** che dimostra anche come **create GS1 barcode** dati.

## Passo 2 – Configurare la X‑dimension (larghezza modulo)

La X‑dimension controlla la larghezza della barra più piccola (modulo). Un valore comune per il rendering su schermo è 2 pixel.

```csharp
        // Step 2: Set the X‑dimension (module width) to 2 pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Impostare esplicitamente la X‑dimension impedisce al generatore di usare il valore predefinito, che potrebbe produrre un codice a barre troppo piccolo per alcuni scanner.

## Passo 3 – Definire il numero di colonne

PDF417 consente di regolare il numero di colonne, influenzando sia la forma del codice a barre sia la capacità di dati. Per un'etichetta compatta, quattro colonne funzionano bene.

```csharp
        // Step 3: Define the number of columns (e.g., 4) for a compact barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

Se ti serve un codice a barre più alto, aumenta il conteggio delle colonne; la libreria calcolerà automaticamente le righe necessarie.

## Passo 4 – Salvare il barcode come immagine

Infine, esporta il codice a barre in un file PNG. PNG preserva bordi nitidi e supporta la trasparenza.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("output/Gs1Pdf417.png", BarCodeImageFormat.Png);
    }
}
```

Eseguendo il programma viene creato `output/Gs1Pdf417.png`. Apri il file in qualsiasi visualizzatore di immagini—vedrai un **PDF417 barcode** pulito che codifica i dati GS1 forniti.

### Output previsto

![Codice a barre PDF417 generato che mostra il GTIN (01)12345678901234](/images/pdf417-sample.png){: .center-image alt="Codice a barre PDF417 generato con un generatore di codici a barre C#"}

*L'immagine sopra dimostra il risultato del campione di codice completo. Il codice a barre può essere scansionato da qualsiasi lettore compatibile PDF417.*

## Opzioni aggiuntive e variazioni comuni

### Cambiare il formato immagine

Se preferisci JPEG o BMP, basta sostituire `BarCodeImageFormat.Png` con `BarCodeImageFormat.Jpeg` o `BarCodeImageFormat.Bmp`. Il resto del codice rimane identico.

### Regolare il livello di correzione degli errori

PDF417 supporta livelli di correzione degli errori da 0‑8. Livelli più alti aumentano la ridondanza ma ingrandiscono anche il codice a barre.

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // medium redundancy
```

### Generare altri GS1 barcode

Il medesimo `BarcodeGenerator` può produrre **create GS1 barcode** per altre simbologie, come `EncodeTypes.Gs1DataMatrix` o `EncodeTypes.Gs1Qr`. Basta scambiare il valore dell'enumerazione:

```csharp
BarcodeGenerator gs1Generator = new BarcodeGenerator(
    EncodeTypes.Gs1DataMatrix, "(01)12345678901234");
```

### Gestire dati vuoti o null

Quando **generate barcode from string**, valida sempre l'input:

```csharp
string data = GetUserInput();
if (string.IsNullOrWhiteSpace(data))
{
    throw new ArgumentException("Data to encode cannot be null or empty.");
}
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
```

Ciò previene eccezioni a runtime e garantisce che il codice a barre rispetti le regole di formattazione GS1.

## Esempio completo, eseguibile

Di seguito trovi il programma completo che puoi copiare‑incollare in un nuovo progetto console. Include tutte le direttive `using` necessarie, la creazione della cartella e la gestione degli errori.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Input data – GS1 GTIN with Application Identifier (01)
        const string gs1Data = "(01)12345678901234";

        // Validate input
        if (string.IsNullOrWhiteSpace(gs1Data))
        {
            Console.WriteLine("Error: Barcode data cannot be empty.");
            return;
        }

        // Ensure output directory exists
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);

        // Create the generator for PDF417 (GS1 optional)
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417, gs1Data);

        // Configure appearance
        generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
        generator.Parameters.Barcode.Pdf417.Columns = 4;    // compact layout
        generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // optional

        // Save as PNG
        string outputPath = Path.Combine(outputDir, "Gs1Pdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

**Esegui il programma** (`dotnet run`) e troverai `Gs1Pdf417.png` nella cartella *output*. Scansionalo con qualsiasi lettore PDF417 per verificare che il GTIN `(01)12345678901234` sia correttamente codificato.

## Domande frequenti

**Q: Posso usare questo codice su .NET Framework 4.6?**  
A: Sì. La libreria Aspose.BarCode è destinata a .NET Standard 2.0, che è compatibile con .NET Framework 4.6 e versioni successive.

**Q: E se ho bisogno di un'immagine a risoluzione più alta?**  
A: Imposta la proprietà `Resolution` prima di salvare:

```csharp
generator.Parameters.ImageResolution.DpiX = 300;
generator.Parameters.ImageResolution.DpiY = 300;
```

**Q: Il codice a barre è ancora valido senza l'Identificatore di Applicazione GS1?**  
A: Sarà un codice a barre PDF417 standard, ma non sarà riconosciuto come simbolo conforme a GS1. Includi il prefisso `(01)` quando è necessario **create GS1 barcode** compliance.

## Conclusione

Ora sai come **create PDF417 barcode** in C# usando un robusto **c# barcode generator**. Il tutorial ha coperto:

* Istanziare `BarcodeGenerator` con dati GS1  
* Configurare X‑dimension e conteggio colonne  
* Salvare il risultato come immagine PNG  
* Estendere la soluzione con correzione degli errori, formati diversi e validazione dell'input  

Con questa base puoi generare qualsiasi PDF417 o GS1 barcode direttamente da una stringa, incorporarlo nei report o inviarlo alle stampanti. Esplora l'API Aspose.BarCode per aggiungere colori, margini o combinare più codici a barre in un'unica immagine.

**Passi successivi**: prova a generare un **create GS1 barcode** per DataMatrix, sperimenta con calcoli dinamici delle colonne, o integra il generatore in un servizio web ASP.NET Core che restituisce immagini di codici a barre su richiesta.

Buon coding!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come generare PDF417 barcode in C# – guida completa](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-complete-guide/)
- [Come creare micro PDF417 barcode e generare PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-generate-png-in-c/)
- [Come creare macro PDF417 barcode in C# usando Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}