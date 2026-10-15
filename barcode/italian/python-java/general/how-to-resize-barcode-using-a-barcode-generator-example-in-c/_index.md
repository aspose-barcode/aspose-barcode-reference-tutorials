---
category: general
date: 2026-10-08
description: Scopri come ridimensionare le immagini dei codici a barre con un esempio
  di generatore di codici a barre in C#, regolando l'altezza delle barre da 30 px
  a 60 px in poche righe di codice.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to resize barcode
- barcode generator example c#
language: it
lastmod: 2026-10-08
og_description: Come ridimensionare rapidamente un codice a barre con un esempio di
  generatore di codici a barre in C#. Regola l'altezza delle barre, salva file PNG
  ed evita gli errori più comuni.
og_image_alt: Screenshot showing a resized barcode generated with C# code
og_title: Come ridimensionare il codice a barre in C# – esempio passo‑passo del generatore
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  headline: How to resize barcode using a barcode generator example in C#
  type: TechArticle
- description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  name: How to resize barcode using a barcode generator example in C#
  steps:
  - name: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
    text: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
  - name: Print the images at 100 % scale.
    text: Print the images at 100 % scale.
  - name: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
    text: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
  type: HowTo
tags:
- barcode
- C#
- image processing
title: Come ridimensionare il codice a barre usando un esempio di generatore di codici
  a barre in C#
url: /it/python-java/general/how-to-resize-barcode-using-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come ridimensionare il codice a barre usando un esempio di generatore di codici a barre in C#

Se hai bisogno di **come ridimensionare il codice a barre** in un progetto .NET, questa guida mostra la soluzione completa. Vedrai un conciso **esempio di generatore di codici a barre C#** che cambia l’altezza della barra da 30 px a 60 px e salva ogni versione come file PNG.

Il ridimensionamento di un codice a barre è spesso necessario quando gli stessi dati devono apparire su scontrini, etichette o pagine prodotto a diverse scale visive. Invece di modificare l’immagine raster con un editor esterno, puoi regolare le dimensioni del codice a barre programmaticamente, mantenendo intatta l’integrità dei dati.

In questo tutorial imparerai a:

* Configurare un generatore di codice a barre DataBar Omni‑Directional.  
* Modificare i parametri X‑dimension e altezza della barra.  
* Salvare due immagini con altezze distinte.  
* Comprendere perché la modifica dell’altezza della barra funziona e quali casi limite tenere d’occhio.

> **Prerequisito** – Hai un ambiente di sviluppo .NET (Visual Studio 2022 o successivo) e la libreria di codici a barre che fornisce `BarcodeGenerator`, `EncodeTypes` e `BarCodeImageFormat`. Il codice funziona con l’ultima versione della libreria a partire da ottobre 2026.

## Prerequisiti per l’esempio di generatore di codici a barre C#

Prima di iniziare, assicurati di avere:

| Elemento | Motivo |
|------|--------|
| .NET 6.0 SDK o versioni successive | Fornisce il runtime e le funzionalità linguistiche usate nel campione. |
| Libreria di codici a barre (es. Aspose.BarCode, Dynamsoft o qualsiasi libreria che espone `BarcodeGenerator`) | Fornisce l’enum `EncodeTypes.DatabarOmniDirectional` e i metodi di esportazione immagine. |
| Una cartella in cui è possibile scrivere (es. `C:\Temp\Barcodes\`) | Il campione salva i file PNG in questa posizione. |
| Conoscenza di base di C# | Il tutorial presuppone familiarità con classi, proprietà e interpolazione di stringhe. |

Installa la libreria via NuGet se non l’hai già fatto:

```bash
dotnet add package Aspose.BarCode
```

Sostituisci il nome del pacchetto con quello che utilizzi effettivamente; l’interfaccia API mostrata di seguito è comune alla maggior parte degli SDK di codici a barre.

## Come ridimensionare il codice a barre – passo 1: creare il generatore

Il primo passo è istanziare un `BarcodeGenerator` con la simbologia desiderata e il payload di dati. In questo esempio generiamo un codice a barre **DataBar Omni‑Directional** che codifica un valore GTIN‑14.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a DataBar Omni‑Directional barcode generator with the desired data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

**Perché è importante:** L’enum `EncodeTypes.DatabarOmniDirectional` indica alla libreria quale standard di codice a barre utilizzare. La stringa di dati segue l’Identificatore di Applicazione GS1 `(01)` per un GTIN a 14 cifre, garantendo che il codice a barre sia conforme agli standard commerciali globali.

## Come ridimensionare il codice a barre – passo 2: definire la larghezza del modulo e l’altezza iniziale della barra

La dimensione visiva di un codice a barre dipende da due parametri:

* **X‑dimension** – la larghezza della barra più piccola (modulo). Misurata in pixel o millimetri.  
* **Altezza della barra** – la lunghezza verticale delle barre.

Impostare questi valori prima del salvataggio garantisce che l’immagine renderizzata corrisponda alle dimensioni richieste.

```csharp
// Step 2: Define the X‑dimension (module width) and set the bar height to 30 px
generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2 px per module
generator.Parameters.Barcode.BarHeight.Pixels = 30; // 30 px tall bars
```

**Spiegazione:** Una X‑dimension di 2 px produce un codice a barre compatto che comunque scansiona in modo affidabile. L’altezza di 30 px è un valore predefinito comune per etichette piccole. Puoi regolare la X‑dimension indipendentemente dall’altezza se ti serve un pattern più denso o più distanziato.

## Come ridimensionare il codice a barre – passo 3: salvare la prima immagine (altezza 30 px)

Ora esporta il codice a barre in un file PNG. Il metodo `Save` accetta un percorso file e un enum di formato immagine.

```csharp
// Step 3: Save the barcode image with a 30 px height
string outputPath = @"C:\Temp\Barcodes\";
generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**Risultato:** `DatabarBarHeight30Pixels.png` contiene un codice a barre alto 30 px. Puoi aprire il file con qualsiasi visualizzatore di immagini per verificare le dimensioni.

## Come ridimensionare il codice a barre – passo 4: cambiare l’altezza della barra a 60 px

Per creare una versione più grande, modifica semplicemente la proprietà `BarHeight`. Il generatore riutilizza gli stessi dati e la stessa X‑dimension, quindi il pattern del codice a barre rimane identico—cambia solo la dimensione visiva.

```csharp
// Step 4: Change the bar height to 60 px for a larger barcode
generator.Parameters.Barcode.BarHeight.Pixels = 60;
```

**Perché funziona:** Il motore di rendering del codice a barre calcola la geometria di ogni barra al volo. Aggiornare la proprietà altezza prima della successiva chiamata a `Save` genera una nuova rasterizzazione con le nuove dimensioni.

## Come ridimensionare il codice a barre – passo 5: salvare la seconda immagine (altezza 60 px)

```csharp
// Step 5: Save the barcode image with a 60 px height
generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Ora disponi di due file PNG, uno piccolo (30 px) e uno più grande (60 px), pronti per l’uso su etichette di dimensioni diverse.

## Codice completo per l’esempio di generatore di codici a barre C#

Di seguito trovi il programma completo, pronto per l’esecuzione. Copialo in un nuovo progetto console per testarlo subito.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeResizeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with DataBar Omni‑Directional symbology
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension and initial bar height (30 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 3️⃣ Define output folder (ensure it exists)
            string outputPath = @"C:\Temp\Barcodes\";
            System.IO.Directory.CreateDirectory(outputPath);

            // 4️⃣ Save the 30 px version
            generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30 px barcode.");

            // 5️⃣ Increase bar height to 60 px
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the 60 px version
            generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60 px barcode.");
        }
    }
}
```

**Output previsto nella console:**

```
Saved 30 px barcode.
Saved 60 px barcode.
```

Dopo l’esecuzione, apri i due file PNG per vedere la differenza visiva. Entrambi i codici a barre codificano lo stesso valore GTIN‑14 e verranno scansionati identicamente, indipendentemente dall’altezza.

## Perché modificare l’altezza della barra è sicuro per la scansione

Gli scanner di codici a barre leggono il pattern di moduli chiari e scuri, non il conteggio assoluto di pixel. Finché la **X‑dimension** rimane entro la tolleranza dello scanner (di solito da 0,5 mm a 2 mm in unità fisiche), cambiare l’altezza non influisce sulla leggibilità. La libreria scala automaticamente i moduli, preservando le zone di quiete e i pattern di allineamento richiesti.

## Problemi comuni e come evitarli

| Problema | Come risolverlo |
|---------|------------|
| **La cartella di output non esiste** | Chiama `Directory.CreateDirectory(outputPath)` prima di salvare. |
| **X‑dimension errata che causa scansioni sfocate** | Mantieni `XDimension.Pixels` tra 1 px e 4 px per la maggior parte delle stampanti; verifica con uno scanner fisico. |
| **Uso di un formato raster per codici a barre molto grandi** | Passa a `BarCodeImageFormat.Svg` per scalabilità infinita senza pixelatura. |
| **Dimenticare di reimpostare `BarHeight` prima del secondo salvataggio** | Assicurati di assegnare la nuova altezza **prima** di chiamare nuovamente `Save`. |

## Consiglio professionale: generare più dimensioni in un ciclo

Se ti servono diverse altezze (es. 30 px, 45 px, 60 px), un semplice ciclo `foreach` riduce la duplicazione:

```csharp
int[] heights = { 30, 45, 60 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputPath}DatabarBarHeight{h}Pixels.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {h} px barcode.");
}
```

Questo modello scala bene per l’elaborazione batch di cataloghi prodotto.

## Casi limite: formati immagine diversi e impostazioni DPI

* **Output SVG** – Usa `BarCodeImageFormat.Svg` per produrre un file vettoriale ridimensionabile senza perdita di qualità.  
* **PNG ad alta DPI** – Imposta `generator.Parameters.Image.DpiX` e `DpiY` a 300 o 600 per immagini pronte per la stampa; l’altezza della barra sarà comunque misurata in pixel, quindi aumentala proporzionalmente.  
* **Simbologie non standard** – Alcuni tipi di codice a barre (es. QR Code) hanno una proprietà `Size` separata anziché `BarHeight`. Consulta la documentazione della libreria per questi casi.

## Testare il codice a barre ridimensionato

1. Apri ciascun PNG in un visualizzatore di immagini e verifica le dimensioni in pixel (es. 150 × 30 px vs. 150 × 60 px).  
2. Stampa le immagini al 100 % della scala.  
3. Scansiona con uno scanner di codici a barre portatile o con un’app mobile. I dati decodificati dovrebbero essere

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive e a esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [How to resize barcode in C# with Aspose.BarCode – step‑by‑step guide](/barcode/english/python-java/general/how-to-resize-barcode-in-c-with-aspose-barcode-step-by-step/)
- [How to save barcode images with Barcode Generator C# – step‑by‑step guide](/barcode/english/python-java/general/how-to-save-barcode-images-with-barcode-generator-c-step-by/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}