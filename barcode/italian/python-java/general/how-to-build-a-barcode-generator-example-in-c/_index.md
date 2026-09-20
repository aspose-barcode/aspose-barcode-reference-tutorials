---
category: general
date: 2026-09-19
description: Esempio di generatore di codici a barre che mostra come modificare l'altezza,
  creare DataBar Omni‑Directional e regolare le dimensioni del codice a barre per
  l'output immagine in C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to change height
- how to create databar
- adjust barcode dimensions
- create barcode image c#
language: it
lastmod: 2026-09-19
og_description: Esempio di generatore di codici a barre che insegna come modificare
  l'altezza, creare DataBar Omni‑Directional e regolare le dimensioni del codice a
  barre per un'immagine PNG in C#.
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode generated in C#
og_title: Esempio di generatore di codici a barre in C# – guida passo passo
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator example showing how to change height, create DataBar
    Omni‑Directional, and adjust barcode dimensions for C# image output
  headline: How to build a barcode generator example in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Come creare un esempio di generatore di codici a barre in C#
url: /it/python-java/general/how-to-build-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Esempio di generatore di codici a barre in C# – guida completa di programmazione

Se hai bisogno di un **barcode generator example** per un progetto .NET, questa guida ti mostra esattamente come creare, configurare e salvare un codice a barre DataBar Omni‑Directional usando C#. Imparerai come modificare l'altezza, regolare le dimensioni del codice a barre e generare un'immagine PNG ad alta qualità—tutto in una singola applicazione console eseguibile.

I passaggi seguenti coprono tutto, dall'installazione dell'SDK necessario alla regolazione della X‑dimension e dell'altezza della barra. Alla fine del tutorial avrai un generatore di codici a barre pronto all'uso da integrare nella fatturazione, nell'inventario o in qualsiasi flusso di lavoro di scansione.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6.0 SDK o versioni successive installate  
* Visual Studio 2022 (o qualsiasi IDE che supporti .NET)  
* Una licenza attiva per **Aspose.BarCode for .NET** (la versione di prova gratuita funziona per i test)  

Se preferisci una libreria diversa, i concetti di regolazione delle dimensioni e salvataggio dell'immagine rimangono gli stessi; basta sostituire le chiamate API di conseguenza.

## Passo 1: Configura il progetto e aggiungi il pacchetto Aspose.BarCode

Crea un nuovo progetto console e fai riferimento alla libreria di codici a barre.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Il comando `dotnet add package` scarica l'ultima versione stabile di Aspose.BarCode, che include il supporto completo per i simboli DataBar Omni‑Directional.

## Passo 2: Scrivi l'esempio completo di generatore di codici a barre

Apri **Program.cs** e sostituisci il suo contenuto con il codice seguente. Questo blocco contiene il **barcode generator example** completo—nessun pezzo mancante.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a barcode generator for a DataBar Omni‑Directional symbol
            // The GTIN‑14 value "(01)12345678901231" is encoded as a numeric string.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Adjust barcode dimensions
            // Set the X‑dimension (module width) to 2 pixels – this controls the thin bar width.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ How to change height
            // Set the bar height to 30 pixels. Height influences readability on larger scanners.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Optional: fine‑tune additional properties (quiet zone, color, etc.)
            generator.Parameters.Barcode.QrCodeErrorLevel = QRErrorLevel.LevelM; // example property
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // 5️⃣ Create barcode image C#
            // Save the generated barcode as a PNG file in the output folder.
            string outputPath = "DatabarOmniDirectional.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Perché ogni riga è importante

* **Crea un generatore di codici a barre** – Il costruttore `BarcodeGenerator` associa il tipo di codifica (`EncodeTypes.DatabarOmniDirectional`) ai dati che vuoi incorporare. Questo è il nucleo del passo **how to create databar**.  
* **Regola le dimensioni del codice a barre** – La proprietà `XDimension.Pixels` definisce la larghezza della barra più stretta. Modificare questo valore influenza le dimensioni complessive e l'affidabilità della scansione.  
* **Come modificare l'altezza** – La proprietà `BarHeight.Pixels` controlla la dimensione verticale. Aumentare l'altezza migliora la leggibilità per gli scanner portatili, mentre diminuirla consente di risparmiare spazio su etichette piccole.  
* **Regolazioni opzionali** – Impostare i colori di primo piano/sfondo o i livelli di correzione degli errori è opzionale ma dimostra come estendere il concetto **adjust barcode dimensions**.  
* **Crea immagine di codice a barre C#** – Il metodo `Save` scrive il codice a barre su disco. Usare `BarCodeImageFormat.Png` garantisce una compressione senza perdita, ideale per la maggior parte delle applicazioni.

## Passo 3: Compila ed esegui l'esempio

Compila ed esegui il programma:

```bash
dotnet run
```

Dovresti vedere l'output della console:

```
Barcode saved to DatabarOmniDirectional.png
```

Un file chiamato **DatabarOmniDirectional.png** appare nella cartella del progetto. Aprire l'immagine rivela un codice a barre DataBar Omni‑Directional nitido, pronto per la scansione.

## Come modificare l'altezza in seguito

Se devi generare codici a barre con altezze variabili, avvolgi l'assegnazione dell'altezza in un metodo:

```csharp
static void SetBarHeight(BarcodeGenerator gen, int heightPixels)
{
    gen.Parameters.Barcode.BarHeight.Pixels = heightPixels;
}
```

Chiama `SetBarHeight(generator, 45);` prima di `Save`. Questo approccio ti consente di **how to change height** in modo dinamico in base all'input dell'utente o a file di configurazione.

## Come creare codici a barre DataBar Omni‑Directional con dati diversi

La simbologia DataBar Omni‑Directional supporta GTIN‑14, GTIN‑13 e altri identificatori numerici. Per codificare un valore diverso, sostituisci semplicemente la stringa nel costruttore:

```csharp
new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)98765432109876");
```

Ricorda di mantenere i dati numerici e formattati correttamente; altrimenti il generatore genera un `BarcodeException`.

## Regola le dimensioni del codice a barre per diversi scenari di stampa

Stampanti e dimensioni delle etichette diverse richiedono X‑dimension e altezze differenti. Usa la tabella seguente come riferimento rapido:

| Scenario                     | X‑Dimension (pixels) | Bar Height (pixels) |
|------------------------------|----------------------|---------------------|
| Etichetta piccola (25 mm × 15 mm)  | 1                    | 20                  |
| Etichetta media (50 mm × 30 mm) | 2                    | 30                  |
| Etichetta grande (100 mm × 50 mm) | 3                    | 45                  |

Applica questi valori impostando `generator.Parameters.Barcode.XDimension.Pixels` e `BarHeight.Pixels` di conseguenza.

## Consiglio professionale: valida il codice a barre generato

Prima di spedire un'etichetta, puoi verificare la sua leggibilità programmaticamente:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.DatabarOmniDirectional);
if (reader.Read())
{
    Console.WriteLine("Validation succeeded: " + reader.GetCodeText());
}
else
{
    Console.WriteLine("Validation failed – barcode may be unreadable.");
}
```

Questo snippet dimostra un rapido controllo di sanità **adjust barcode dimensions**, assicurando che il codice a barre soddisfi i requisiti di scansione.

## Problemi comuni e come evitarli

| Problema                              | Perché succede                              | Correzione                                                                 |
|--------------------------------------|---------------------------------------------|-----------------------------------------------------------------------------|
| Uso di dati non numerici per DataBar    | DataBar si aspetta formati GTIN numerici        | Assicurati che la stringa corrisponda al pattern `(01)XXXXXXXXXXXXX`.         |
| Impostazione di X‑dimension a 0 o negativo  | La libreria lancia `ArgumentOutOfRangeException`| Usa un minimo di 1 pixel; testa prima sulla stampante di destinazione.            |
| Salvataggio in una cartella di sola lettura          | `UnauthorizedAccessException` su `Save`     | Scegli una directory scrivibile o esegui l'app con i permessi appropriati.|
| Dimenticare di liberare `BarCodeReader` | Perdita di memoria in servizi a lunga esecuzione        | Avvolgi il lettore in un blocco `using` o chiama manualmente `Dispose()`.   |

Affrontare questi problemi in anticipo fa risparmiare tempo di debug e migliora la stabilità in produzione.

## Riepilogo del codice sorgente completo

Di seguito trovi il programma completo, pronto per essere copiato, che implementa il **barcode generator example** dall'inizio alla fine.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create generator – how to create databar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Adjust barcode dimensions
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // how to change height

            // Optional visual tweaks
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // Save image – create barcode image c#
            string filePath = "DatabarOmniDirectional.png";
            generator.Save(filePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {filePath}");

            // Validate barcode (optional)
            using (BarCodeReader reader = new BarCodeReader(filePath, DecodeType.DatabarOmniDirectional))
            {
                if (reader.Read())
                    Console.WriteLine($"Validation succeeded: {reader.GetCodeText()}");
                else
                    Console.WriteLine("Validation failed – barcode may be unreadable.");
            }
        }
    }
}
```

Eseguendo questo programma si genera un file PNG che appare così (esemplificativo):

![DataBar Omni‑Directional barcode generated in C#](https://example.com/og-image.png "DataBar Omni‑Directional barcode generated in C#")

*Testo alternativo dell'immagine*: **DataBar Omni‑Directional barcode generated in C#** (matches `og_image_alt`).

## Conclusione

Ora disponi di un **barcode generator example** che dimostra come modificare l'altezza, come creare simboli DataBar Omni‑Directional e come **adjust barcode dimensions** per una scansione ottimale. Il codice C# completo salva un'immagine PNG, la valida e può essere esteso per generazione di massa o integrazione in servizi web.

Successivamente, esplora argomenti correlati come **creare codici QR con Aspose.BarCode**, **elaborazione batch di più valori di codice a barre**, o **incorporare codici a barre in documenti PDF**. Ognuno di questi si basa sugli stessi fondamenti trattati in questa guida.

Buona programmazione, e che i tuoi codici a barre siano sempre leggibili!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Esempio di generatore di codici a barre – Creare immagine DataBar in C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [Come generare e regolare l'altezza del codice a barre per Databar unidimensionale usando Aspose.BarCode per .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Esempio di generatore di codici a barre in C# – impostare larghezza e altezza](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}