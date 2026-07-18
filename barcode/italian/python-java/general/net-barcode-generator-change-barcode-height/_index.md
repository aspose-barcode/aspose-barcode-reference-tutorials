---
category: general
date: 2026-07-18
description: Scopri come generare immagini di codici a barre con un generatore di
  codici a barre .net e modifica facilmente l'altezza del codice a barre per i simboli
  GS1‑Databar Omni‑Directional.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- .net barcode generator
- how to generate barcode
- change barcode height
- GS1‑Databar Omni‑Directional
- barcode image export
language: it
lastmod: 2026-07-18
og_description: Il generatore di codici a barre .net ti consente di creare rapidamente
  immagini di codici a barre. Questa guida mostra come generare codici a barre, regolare
  l'altezza delle barre e salvare file PNG.
og_image_alt: Screenshot of a .net barcode generator output showing different bar
  heights
og_title: Modifica l'altezza del codice a barre con il generatore di codici a barre
  .NET
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  headline: .net barcode generator – change barcode height
  type: TechArticle
- description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  name: .net barcode generator – change barcode height
  steps:
  - name: Why each line matters
    text: '| Line | Reason | |------|--------| | `BarcodeGenerator generator = new
      BarcodeGenerator(...);` | Instantiates the **.net barcode generator** with the
      desired symbology and data payload. The `EncodeTypes.DatabarOmniDirectional`
      enum tells the library to use the GS1‑Databar Omni‑Directional format. |'
  - name: Adjusting the X‑dimension for larger prints
    text: '```csharp generator.Parameters.Barcode.XDimension.Pixels = 4; // Double
      the narrow bar width ``` Increasing the X‑dimension makes the whole barcode
      larger without altering the encoded data. This is handy when you print on large
      labels.'
  - name: Switching output formats
    text: '```csharp generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
      ``` SVG scales infinitely, which is perfect for web‑based scanners that need
      crisp vectors.'
  - name: Adding human‑readable text
    text: '```csharp generator.Parameters.Barcode.CodeTextVisible = true; generator.Parameters.Barcode.CodeTextAlignment
      = CodeLocation.Below; ``` Enabling `CodeTextVisible` appends the raw data under
      the barcode, useful for verification during testing.'
  type: HowTo
tags:
- barcode
- .net
- image export
title: .NET generatore di codici a barre – cambia l’altezza del codice a barre
url: /it/python-java/general/net-barcode-generator-change-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generatore di codici a barre .net – modifica altezza del codice a barre

Ti sei mai chiesto **come generare immagini di codici a barre** senza dover gestire una dozzina di strumenti di terze parti? Nel mondo .NET esiste un modo sorprendentemente semplice per farlo, e l'elemento chiave è il **.net barcode generator**. Con poche righe di C# puoi creare un simbolo GS1‑Databar Omni‑Directional, regolare l'altezza delle barre e salvare il risultato in un file PNG.

Se stai costruendo un sistema di inventario, una stampante di etichette di spedizione o qualsiasi app che richieda un codice leggibile, questo tutorial ti porterà da zero a un codice a barre funzionante in pochi minuti. Esamineremo il codice completo, spiegheremo perché ogni impostazione è importante e ti mostreremo come **modificare l'altezza del codice a barre** senza violare le specifiche.

## Cosa ti serve

- .NET 6.0 o versioni successive (l'API funziona allo stesso modo su .NET Framework 4.7+)
- Un riferimento alla libreria di codici a barre (ad esempio, Aspose.BarCode for .NET – le stesse classi sono utilizzate da molti kit commerciali)
- Un ambiente di sviluppo (Visual Studio, Rider o VS Code con l'estensione C#)
- Una cartella in cui hai permessi di scrittura – il tutorial salverà i file PNG lì

Tutto qui. Nessun pacchetto NuGet aggiuntivo oltre alla libreria di codici a barre stessa.

## Utilizzare il generatore di codici a barre .net per modificare l'altezza del codice a barre

Di seguito trovi un **programma console completo e eseguibile**. Incollalo in un nuovo progetto C#, regola la cartella di output e premi F5.

```csharp
using System;
using Aspose.BarCode.Generation;   // Namespace for the barcode generator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a barcode generator for a GS1‑Databar Omni‑Directional symbol.
            // The string "(01)12345678901231" follows the GS1 Application Identifier syntax.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Define common visual parameters.
            // X‑dimension controls the width of the narrowest bar; 2 pixels works well for screen display.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set the initial bar height to 30 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Save the first image – a compact barcode.
            string outFolder = @"YOUR_DIRECTORY"; // ← replace with a real path
            generator.Save($"{outFolder}/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 5️⃣ Increase the bar height to 60 pixels for a larger, more readable code.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the second image – a taller barcode.
            generator.Save($"{outFolder}/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two barcode images have been generated successfully.");
        }
    }
}
```

### Perché ogni riga è importante

| Riga | Motivo |
|------|--------|
| `BarcodeGenerator generator = new BarcodeGenerator(...);` | Istanzia il **.net barcode generator** con la simbologia e i dati desiderati. L'enumerazione `EncodeTypes.DatabarOmniDirectional` indica alla libreria di utilizzare il formato GS1‑Databar Omni‑Directional. |
| `XDimension.Pixels = 2;` | La X‑dimension è la larghezza della barra più sottile. Impostandola a *2 pixel* si ottiene un'immagine nitida sulla maggior parte dei monitor mantenendo ridotto il peso del file. |
| `BarHeight.Pixels = 30;` | Questo è il passaggio di **modifica dell'altezza del codice a barre** che determina l'altezza di ciascuna barra. Un'altezza di 30 pixel è un buon valore predefinito per etichette piccole. |
| `generator.Save(...);` | Salva il codice a barre in un file PNG. PNG è senza perdita, il che significa che gli scanner vedono esattamente il pattern generato. |
| `BarHeight.Pixels = 60;` | Qui **modifichiamo nuovamente l'altezza del codice a barre**, questa volta a 60 pixel. La libreria rigenera automaticamente il simbolo con la nuova dimensione quando chiami `Save` una seconda volta. |
| `Console.WriteLine(...);` | Ti fornisce un rapido feedback che il processo è terminato senza sollevare eccezioni. |

> **Consiglio professionale:** Se hai bisogno di output ad alta risoluzione per la stampa, passa da `BarCodeImageFormat.Png` a `BarCodeImageFormat.Tiff` e aumenta la proprietà `Resolution` (ad esempio, `generator.Parameters.ImageResolution = 300;`). L'altezza delle barre verrà comunque rispettata, ma renderizzata a un DPI più fine.

## Come generare immagini di codici a barre con impostazioni diverse

Il frammento sopra copre le basi, ma scenari reali spesso richiedono ulteriori regolazioni:

### Regolare la X‑dimension per stampe più grandi
```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // Double the narrow bar width
```
Aumentare la X‑dimension rende l'intero codice a barre più grande senza modificare i dati codificati. È utile quando si stampa su etichette di grandi dimensioni.

### Cambiare i formati di output
```csharp
generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
```
SVG si scala all'infinito, il che è perfetto per scanner basati sul web che necessitano di vettori nitidi.

### Aggiungere testo leggibile dall'uomo
```csharp
generator.Parameters.Barcode.CodeTextVisible = true;
generator.Parameters.Barcode.CodeTextAlignment = CodeLocation.Below;
```
Abilitare `CodeTextVisible` aggiunge i dati grezzi sotto il codice a barre, utile per la verifica durante i test.

## Errori comuni quando **modifichi l'altezza del codice a barre**

1. **Altezza troppo piccola** – Alcuni scanner richiedono un'altezza minima della barra (spesso 10 mm in unità fisiche). Se imposti `BarHeight.Pixels` troppo basso, l'immagine generata potrebbe risultare illeggibile su uno scanner reale. Testa sempre con l'hardware di destinazione.
2. **X‑dimension e altezza non corrispondenti** – Un'altezza della barra molto grande associata a una X‑dimension piccola può apparire allungata e causare errori di decodifica. Mira a un rapporto equilibrato (circa 3:1 a 5:1) a meno che le specifiche non indichino diversamente.
3. **Dimenticare di reimpostare i parametri** – Il generatore mantiene lo stato tra i salvataggi. Se cambi `BarHeight` per un'immagine e poi riutilizzi la stessa istanza per un altro codice a barre, l'altezza precedente rimarrà. Reimposta la proprietà o istanzia un nuovo `BarcodeGenerator` per ogni codice a barre distinto.

## Esempio completo end‑to‑end (inclusa l'installazione di NuGet)

Se parti da zero, segui questi passaggi per avviare il progetto:

```bash
dotnet new console -n BarcodeHeightDemo
cd BarcodeHeightDemo
dotnet add package Aspose.BarCode
```

Sostituisci il `Program.cs` generato automaticamente con il blocco di codice mostrato in precedenza, **ricordati di sostituire `YOUR_DIRECTORY`** con qualcosa come `Path.Combine(Environment.CurrentDirectory, "output")`. Poi:

```bash
dotnet run
```

Dovresti vedere due file PNG nella cartella `output`:

- `DatabarBarHeight30Pixels.png` – un codice a barre compatto alto 30 pixel.
- `DatabarBarHeight60Pixels.png` – una versione più alta di 60 pixel.

Entrambe le immagini avranno un aspetto simile, ma la seconda presenterà barre visibilmente più lunghe, facilitando la lettura da parte di scanner a bassa risoluzione.

![Barcode height example](/images/barcode-height.png){alt="output del generatore di codici a barre .net che mostra diverse altezze delle barre"}

## Riepilogo e prossimi passi

Abbiamo coperto come **generare immagini di codici a barre** usando un **.net barcode generator**, affinato la proprietà **change barcode height**, e salvato i risultati in formato PNG. I punti chiave sono:

- Istanziare il generatore con il corretto `EncodeTypes`.
- Controllare le dimensioni visive tramite `XDimension` e `BarHeight`.
- Chiamare `Save` dopo ogni modifica per salvare una nuova immagine.
- Regolare risoluzione, formato,

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come generare un codice a barre Aztec con rapporto d'aspetto personalizzato usando Aspose.BarCode per .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Come creare un dotcode con testo esteso usando Aspose.BarCode per .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Come generare codici a barre DataMatrix (ECC 200) con Aspose.BarCode per .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}