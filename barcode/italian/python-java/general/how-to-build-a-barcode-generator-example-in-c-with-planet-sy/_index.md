---
category: general
date: 2026-10-05
description: Esempio di generatore di codici a barre in C# che mostra come generare
  il codice a barre Planet e creare l'immagine del codice a barre in C#. Segui questa
  guida passo passo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- generate planet barcode
- create barcode image c#
language: it
lastmod: 2026-10-05
og_description: L'esempio di generatore di codici a barre in C# ti guida nella generazione
  di un codice a barre planet e nella creazione di un'immagine del codice a barre
  in C#. Ottieni una soluzione completa e eseguibile.
og_image_alt: Screenshot of a generated Planet barcode image created by a C# barcode
  generator example
og_title: Esempio di generatore di codici a barre in C# – genera rapidamente il codice
  a barre Planet
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: barcode generator example in C# that shows you how to generate planet
    barcode and create barcode image c#. Follow this step‑by‑step guide.
  headline: How to build a barcode generator example in C# with Planet symbology
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Come creare un esempio di generatore di codici a barre in C# con la simbologia
  Planet
url: /it/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-planet-sy/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Esempio di generatore di codici a barre in C# – genera codice a barre Planet e crea immagine del codice a barre

Se hai bisogno di un **esempio di generatore di codici a barre** in C#, questa guida ti mostra esattamente come generare un codice a barre Planet e creare un'immagine del codice a barre c# in poche righe di codice. Vedrai una soluzione completa, pronta‑all‑uso, che puoi inserire in qualsiasi progetto .NET.

Un codice a barre Planet è utilizzato dai servizi postali per codificare le informazioni di instradamento. Alla fine di questo tutorial comprenderai perché la libreria determina automaticamente l’altezza del codice a barre, come controllare la dimensione X e come salvare il risultato come file PNG. Non sono necessari strumenti esterni—solo il pacchetto Aspose.BarCode for .NET e un ambiente di sviluppo .NET.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6.0 SDK o versioni successive installate  
* Visual Studio 2022 (o qualsiasi IDE che supporti .NET)  
* Il pacchetto NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`)  

Puoi installare il pacchetto dalla riga di comando:

```bash
dotnet add package Aspose.BarCode
```

## Passo 1: Inizializzare il generatore di codici a barre per la codifica Planet

Il primo passo in qualsiasi **esempio di generatore di codici a barre** è creare un'istanza di `BarcodeGenerator` e specificare il tipo di codifica. Per un codice a barre Planet utilizzi `EncodeTypes.Planet` e passi la stringa di dati che desideri codificare.

```csharp
using Aspose.BarCode.Generation;

// Create a Planet barcode generator with the data to encode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

**Perché è importante:** L’enumerazione `EncodeTypes.Planet` indica alla libreria di utilizzare la simbologia Planet, che ha un modello di modulo fisso richiesto dagli standard postali. Fornire i dati (`"123456"` in questo caso) garantisce che il codice a barre contenga il corretto codice di instradamento numerico.

## Passo 2: Configurare la dimensione X (larghezza del modulo) in pixel

La dimensione X controlla la larghezza di ogni singolo modulo (la barra più piccola). Modificarla cambia le dimensioni complessive del codice a barre senza influire sulla leggibilità.

```csharp
// Set the X dimension (module width) to 4 pixels
generator.Parameters.Barcode.XDimension.Pixels = 4;
```

**Perché è importante:** Una dimensione X più grande produce un codice a barre più grande, utile quando si stampa su buste di grandi dimensioni. La libreria scala automaticamente l’altezza per mantenere il corretto rapporto d’aspetto per i codici a barre Planet.

## Passo 3: Salvare l’immagine del codice a barre su disco

Infine, salvi l’immagine generata. La libreria determina l’altezza ottimale, quindi devi specificare solo il percorso di output e il formato.

```csharp
using Aspose.BarCode;

// Define the output file path
string outputFile = @"C:\Barcodes\PlanetAutoHeight.png";

// Save the barcode as a PNG image
generator.Save(outputFile, BarCodeImageFormat.Png);
```

**Perché è importante:** Salvare come PNG preserva i bordi nitidi del codice a barre, fondamentale per una scansione affidabile. Il metodo `Save` supporta anche altri formati (JPEG, BMP, TIFF) se hai bisogno di un output diverso.

### Output previsto

Dopo aver eseguito il codice, troverai un file chiamato **PlanetAutoHeight.png** in `C:\Barcodes`. L’immagine avrà un aspetto simile all’illustrazione qui sotto (testo alternativo: *esempio di generatore di codici a barre che mostra un codice a barre Planet*).

![Codice a barre Planet generato dall'esempio C#](/images/planet-barcode-example.png){alt="esempio di generatore di codici a barre che mostra un codice a barre Planet"}

## Passo 4: Opzionale – personalizzare i colori di primo piano e di sfondo

Se la tua applicazione richiede uno stile visivo diverso, puoi modificare i colori del codice a barre prima di salvarlo.

```csharp
// Set foreground (bars) to dark blue and background to light gray
generator.Parameters.Barcode.BarColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.LightGray;

// Save the customized image
generator.Save(@"C:\Barcodes\PlanetCustomColors.png", BarCodeImageFormat.Png);
```

**Suggerimento:** Testa sempre il codice a barre personalizzato con uno scanner reale per confermare che le modifiche di colore non influiscano sulla leggibilità.

## Passo 5: Gestione degli errori e convalida

La libreria Aspose.BarCode genera `ArgumentException` se i dati non soddisfano i requisiti della simbologia Planet (ad esempio caratteri non numerici). Avvolgi il codice di generazione in un blocco try‑catch per fornire un feedback chiaro.

```csharp
try
{
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "ABC123");
    generator.Save(@"C:\Barcodes\InvalidPlanet.png", BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid data for Planet barcode: {ex.Message}");
}
```

**Perché è importante:** I codici a barre Planet accettano solo dati numerici di lunghezze specifiche. Una corretta convalida previene errori a runtime e fa risparmiare tempo durante i test di integrazione.

## Esempio completo, eseguibile

Unendo tutti i passaggi ottieni un programma autonomo che puoi copiare, incollare ed eseguire.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 1: Initialize the generator with Planet encoding
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Step 2: Set the X dimension (module width) to 4 pixels
        generator.Parameters.Barcode.XDimension.Pixels = 4;

        // Optional: customize colors (comment out if not needed)
        // generator.Parameters.Barcode.BarColor = System.Drawing.Color.DarkBlue;
        // generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.LightGray;

        // Step 3: Save the barcode image
        string outputFile = @"C:\Barcodes\PlanetAutoHeight.png";
        generator.Save(outputFile, BarCodeImageFormat.Png);

        Console.WriteLine($"Planet barcode saved to {outputFile}");
    }
}
```

Compila ed esegui il programma:

```bash
dotnet run
```

Dovresti vedere il messaggio nella console che conferma la posizione del file, e il file PNG conterrà il codice a barre Planet generato.

## Variazioni comuni e casi limite

| Variazione | Come implementare | Quando usarlo |
|------------|-------------------|---------------|
| **Lunghezza dati diversa** | Cambia il secondo argomento in `new BarcodeGenerator(EncodeTypes.Planet, "987654321")` | Servizi postali che richiedono numeri di instradamento più lunghi |
| **Risoluzione più alta** | Imposta `generator.Parameters.ImageResolution = 300;` prima di `Save` | Stampa su stampanti ad alta risoluzione (dpi) |
| **Formato immagine diverso** | Usa `BarCodeImageFormat.Jpeg` o `BarCodeImageFormat.Tiff` | Quando PNG non è adatto al tuo flusso di lavoro |
| **Nome file dinamico** | `string outputFile = Path.Combine(folder, $"Planet_{DateTime.Now:yyyyMMdd_HHmmss}.png");` | Elaborazione batch di più codici a barre |

## Consigli professionali per un esempio di generatore di codici a barre robusto

* **Riutilizza l’istanza del generatore** quando crei molti codici a barre con le stesse impostazioni; cambia solo `EncodeTypes` o la stringa dei dati per migliorare le prestazioni.  
* **Convalida l’input** prima di passarlo a `BarcodeGenerator`. Una semplice regex come `^\d{6,9}$` garantisce che i dati rispettino i requisiti Planet.  
* **Rilascia le risorse** se generi migliaia di immagini in un servizio a lunga esecuzione. `BarcodeGenerator` implementa `IDisposable`, quindi avvolgilo in un blocco `using` quando opportuno.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, data))
{
    // configure and save...
}
```

## Conclusione

Questo **esempio di generatore di codici a barre** dimostra come **generare un codice a barre Planet** e **creare un’immagine di codice a barre c#** usando Aspose.BarCode for .NET. Hai imparato a inizializzare il generatore, impostare la dimensione X, personalizzare opzionalmente i colori, gestire gli errori di convalida e salvare il risultato come file PNG. Con il codice sorgente completo fornito, puoi integrare la generazione di codici a barre Planet in qualsiasi applicazione C# subito.

Successivamente, potresti esplorare altre simbologie come QR, Code128 o DataMatrix—ognuna segue lo stesso schema di creazione di un `BarcodeGenerator`, configurazione dei parametri e chiamata a `Save`. I principi rimangono gli stessi, facilitando l’estensione delle capacità di generazione di codici a barre in una vasta gamma di scenari aziendali. Buona programmazione!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑a‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell’API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [crea immagine codice a barre Planet – Guida passo‑a‑passo](/barcode/english/python-java/general/create-planet-barcode-image-step-by-step-guide/)
- [Generatore di codici a barre C# – crea codice a barre Planet e esempio RM4SCC](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)
- [Crea immagine di codice a barre C# con esempio di generatore di codici a barre](/barcode/english/python-java/general/create-barcode-image-c-with-barcode-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}