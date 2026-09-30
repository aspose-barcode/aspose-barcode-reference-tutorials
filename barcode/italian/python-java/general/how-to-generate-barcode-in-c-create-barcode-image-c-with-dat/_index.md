---
category: general
date: 2026-08-22
description: Come generare un codice a barre in C# usando Aspose.BarCode. Impara a
  creare un'immagine di codice a barre in C# passo passo, disabilitare il componente
  2‑D e salvare file PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode image c#
language: it
lastmod: 2026-08-22
og_description: Come generare un codice a barre in C# con Aspose.BarCode. Questo tutorial
  mostra come creare un'immagine di codice a barre in C# utilizzando DataBar Expanded,
  attivare il componente 2‑D e salvare file PNG.
og_image_alt: C# code screenshot generating a DataBar Expanded barcode image without
  the 2‑D component
og_title: Come generare un codice a barre in C# – guida completa per creare un'immagine
  di codice a barre in C#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode in C# using Aspose.BarCode. Learn to create
    barcode image c# step‑by‑step, disable the 2‑D component, and save PNG files.
  headline: How to generate barcode in C# – create barcode image c# with DataBar Expanded
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- image generation
title: Come generare un codice a barre in C# – creare un'immagine di codice a barre
  in C# con DataBar Expanded
url: /it/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come generare un codice a barre in C# – creare un'immagine di codice a barre c# con DataBar Expanded

Generare un codice a barre in C# è una necessità frequente quando è necessario incorporare dati leggibili da macchine nelle proprie applicazioni. Questa guida mostra come creare un'immagine di codice a barre c# utilizzando la libreria Aspose.BarCode, disabilitare il componente composito 2‑D e salvare il risultato come file PNG.

Vedrai un programma completo e eseguibile, una spiegazione di ogni opzione di configurazione e suggerimenti per personalizzare l'output. Non è necessaria alcuna documentazione esterna—basta il codice qui sotto e un ambiente di sviluppo .NET.

## Prerequisiti

* .NET 6.0 SDK o versioni successive installato  
* Visual Studio 2022 (o qualsiasi IDE che supporti .NET)  
* Pacchetto NuGet Aspose.BarCode per .NET (`Aspose.BarCode`)  

Puoi aggiungere il pacchetto con il seguente comando:

```bash
dotnet add package Aspose.BarCode
```

La libreria fornisce la classe `BarcodeGenerator` utilizzata in tutta questa guida.

## Passo 1: Configurare il progetto e importare i namespace

Crea una nuova applicazione console e importa i namespace richiesti:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The rest of the code lives here
        }
    }
}
```

Il namespace `Aspose.BarCode.Generation` contiene tutte le classi necessarie per configurare e renderizzare i codici a barre.

## Passo 2: Inizializzare il generatore di codice a barre DataBar Expanded

La prima riga funzionale crea un `BarcodeGenerator` per la simbologia **DataBar Expanded** e fornisce la stringa di dati grezzi. La stringa di dati segue il formato GS1 Application Identifier `(01)12345678901231`.

```csharp
// Step 2: Create a DataBar Expanded barcode generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpanded, "(01)12345678901231");
```

La creazione del generatore alloca la canvas bitmap interna, così puoi regolare dimensione e aspetto prima del rendering.

## Passo 3: Definire la larghezza del modulo (X‑dimensione)

La X‑dimensione controlla la larghezza dell'elemento più piccolo del codice a barre. Impostandola in pixel ottieni un controllo preciso sulla dimensione finale dell'immagine.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Un valore di `2` pixel funziona bene per la visualizzazione su schermo; aumentalo per stampe ad alta risoluzione.

## Passo 4: Disabilitare il componente composito 2‑D

DataBar Expanded può includere facoltativamente un componente 2‑D che trasporta informazioni aggiuntive. Per generare un codice a barre **senza** questo componente, imposta il flag a `false`.

```csharp
// Step 4: Disable the 2‑D composite component of the DataBar barcode
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
```

Disabilitare il componente riduce la complessità visiva e produce un file PNG più piccolo.

## Passo 5: Salvare l'immagine del codice a barre senza il componente 2‑D

Scegli una directory di output e scrivi l'immagine su disco. L'enumerazione `BarCodeImageFormat.Png` garantisce un file PNG senza perdita.

```csharp
// Step 5: Save the barcode image without the 2‑D component
string outputDir = "YOUR_DIRECTORY/"; // replace with your actual path
barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png", BarCodeImageFormat.Png);
```

Dopo questa chiamata, `Databar2DComponentDisabled.png` contiene un codice DataBar Expanded pulito.

## Passo 6: Abilitare il componente composito 2‑D

Se hai bisogno del livello di dati aggiuntivo, riattiva il flag. La stessa istanza del generatore può essere riutilizzata, evitando di creare un secondo oggetto.

```csharp
// Step 6: Enable the 2‑D composite component
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
```

## Passo 7: Salvare l'immagine del codice a barre con il componente 2‑D abilitato

Renderizza la seconda immagine usando le stesse impostazioni, eccetto il flag 2‑D.

```csharp
// Step 7: Save the barcode image with the 2‑D component enabled
barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png", BarCodeImageFormat.Png);
```

Ora `Databar2DComponentEnabled.png` mostra il codice a barre con il pattern 2‑D aggiuntivo.

## Codice sorgente completo

Copia l'intero snippet qui sotto in `Program.cs` ed esegui il progetto. Il programma crea entrambi i file PNG nella cartella che specifichi.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Create a DataBar Expanded barcode generator with the desired data
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpanded, "(01)12345678901231");

            // Set the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the output directory (change to a valid path on your machine)
            string outputDir = "YOUR_DIRECTORY/";

            // ---------- First image: 2‑D component disabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png",
                                 BarCodeImageFormat.Png);

            // ---------- Second image: 2‑D component enabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png",
                                 BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

### Output previsto

L'esecuzione del programma stampa:

```
Barcode images generated successfully.
```

e crea due file:

* `Databar2DComponentDisabled.png` – codice a barre senza il componente 2‑D  
* `Databar2DComponentEnabled.png` – codice a barre con il componente 2‑D  

Apri i PNG in qualsiasi visualizzatore di immagini per verificare la differenza visiva.

## Varianti comuni e casi limite

| Situazione | Regolazione |
|-----------|------------|
| **Simbologia diversa** | Sostituire `EncodeTypes.DatabarExpanded` con un altro valore, ad esempio `EncodeTypes.Code128`. |
| **Risoluzione più alta** | Incrementare `XDimension.Pixels` a 4 o 5, oppure impostare `Resolution` in `barcodeGenerator.Parameters.Image`. |
| **Altri formati immagine** | Utilizzare `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp` o `BarCodeImageFormat.Svg`. |
| **Esecuzione in un'app web** | Trasmettere i byte dell'immagine direttamente alla risposta HTTP invece di salvarli su disco. |
| **Gestione della memoria** | Avvolgere il generatore in un blocco `using` se si mira a .NET Framework per garantire il rilascio delle risorse non gestite. |

## Consigli professionali

* **Riutilizzare il generatore** – Modificando solo il flag 2‑D si evita di reinizializzare l'oggetto, risparmiando cicli CPU.  
* **Convalidare i dati** – I dati GS1 devono rispettare esattamente le regole di lunghezza e checksum; un input non valido genera `ArgumentException`.  
* **Elaborazione batch** – Iterare su una collezione di stringhe di dati, attivare/disattivare il flag 2‑D secondo necessità e salvare ogni immagine con un nome file unico.  

## Conclusione

Ora sai come generare un codice a barre in C# e creare un'immagine di codice a barre c# con pieno controllo sul componente composito 2‑D. L'esempio dimostra come inizializzare il generatore, configurare la X‑dimensione, attivare/disattivare il componente e salvare file PNG. Da qui puoi esplorare altre simbologie, incorporare le immagini in PDF o integrare la generazione di codici a barre nei servizi ASP.NET Core.

--- 

*Prossimi passi*: prova a generare codici QR, sperimenta con diverse risoluzioni immagine o incorpora i PNG generati in un PDF usando Aspose.PDF. Queste estensioni si basano sulla stessa API `BarcodeGenerator` e mantengono coerente il tuo flusso di lavoro.

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come generare codici a barre DataMatrix usando Aspose.BarCode per .NET – Guida passo‑passo](/barcode/english/net/datamatrix-barcode-configuration/)
- [Come generare e regolare l'altezza del codice a barre per Databar unidimensionale usando Aspose.BarCode per .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Come generare un codice a barre Aztec con rapporto d'aspetto personalizzato usando Aspose.BarCode per .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}