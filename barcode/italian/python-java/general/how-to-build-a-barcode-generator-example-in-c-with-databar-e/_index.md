---
category: general
date: 2026-09-19
description: Esempio di generatore di codici a barre in C# che mostra come generare
  codici a barre in C# utilizzando Aspose.BarCode per layout a colonne e righe.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- generate barcode c#
language: it
lastmod: 2026-09-19
og_description: L'esempio di generatore di codici a barre dimostra come generare codici
  a barre in C# con layout a colonne e righe utilizzando Aspose.BarCode.
og_image_alt: C# barcode generator example output showing a DataBar Expanded Stacked
  barcode with 4 columns
og_title: esempio di generatore di codici a barre – crea codici a barre DataBar Expanded
  Stacked in C#
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator example in C# showing how to generate barcode C#
    using Aspose.BarCode for column and row layouts
  headline: How to build a barcode generator example in C# with DataBar Expanded Stacked
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Come realizzare un esempio di generatore di codici a barre in C# con DataBar
  Expanded Stacked
url: /it/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# esempio di generatore di codici a barre – crea codici a barre DataBar Expanded Stacked in C#

Se ti serve un **esempio di generatore di codici a barre** che funzioni in un progetto .NET, questa guida ti mostra esattamente come generare barcode C# usando la libreria Aspose.BarCode. Vedrai come configurare un codice a barre DataBar Expanded Stacked sia per un layout a colonne sia per un layout a righe, e otterrai del codice pronto all'uso che produce immagini PNG.

Il tutorial copre tutto, dall'installazione del pacchetto NuGet al salvataggio delle immagini finali, così potrai copiare il codice nella tua soluzione senza ulteriori ricerche.

## Cosa imparerai

* Come installare e referenziare Aspose.BarCode in un progetto C#.  
* Come creare un **esempio di generatore di codici a barre** che codifica una lunga stringa di dati.  
* Come impostare un layout a 4 colonne e un layout a 3 righe sullo stesso tipo di codice a barre.  
* Come salvare le immagini generate come file PNG.  

Al termine di questo articolo avrai due file PNG pronti all'uso: `ExpandedStackedCols4.png` (quattro colonne) e `ExpandedStackedRows3.png` (tre righe).

## Prerequisiti

* .NET 6.0 SDK o successivo (il codice funziona anche con .NET Framework 4.7.2).  
* Visual Studio 2022, VS Code, o qualsiasi IDE C# tu preferisca.  
* Accesso a Internet per scaricare il pacchetto NuGet **Aspose.BarCode**.  

Non sono richiesti servizi esterni aggiuntivi.

## Passo 1: Installa il pacchetto NuGet Aspose.BarCode

Apri un terminale nella cartella del tuo progetto ed esegui:

```bash
dotnet add package Aspose.BarCode
```

Il comando aggiunge l'ultima versione stabile di Aspose.BarCode al tuo file di progetto. Dopo il ripristino del pacchetto, potrai referenziare i suoi namespace nei file sorgente C#.

## Passo 2: Aggiungi le direttive `using` richieste

Crea una nuova applicazione console C# (o aggiungi il codice a un progetto esistente) e includi le seguenti istruzioni `using` all'inizio del file:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Queste direttive ti danno accesso alla classe `BarcodeGenerator` e all'enumerazione `EncodeTypes` usate nel **esempio di generatore di codici a barre**.

## Passo 3: Crea un esempio di generatore di codici a barre con layout a 4 colonne

La prima parte dell'esempio costruisce un codice a barre DataBar Expanded Stacked che utilizza una disposizione a quattro colonne. Il codice qui sotto segue esattamente i passaggi mostrati nello snippet originale, ma aggiunge commenti che spiegano il motivo di ogni riga.

```csharp
// Step 3.1: Initialise the generator with the desired barcode type and data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // DataBar Expanded Stacked type
    "Long data string");                  // The data you want to encode

// Step 3.2: Configure the barcode to use a 4‑column layout
generator.Parameters.Barcode.DataBar.Columns = 4;

// Step 3.3: Save the image as a PNG file
generator.Save("ExpandedStackedCols4.png", BarCodeImageFormat.Png);
```

**Perché funziona**

* `EncodeTypes.DatabarExpandedStacked` indica ad Aspose.BarCode di generare un simbolo DataBar Expanded Stacked, adatto per applicazioni retail.  
* Impostare `DataBar.Columns` a `4` costringe il generatore a suddividere il simbolo in quattro sezioni verticali, migliorando la leggibilità su etichette strette.  
* `Save` scrive il codice a barre su disco; l'argomento `BarCodeImageFormat.Png` garantisce una qualità immagine senza perdita.

Eseguendo questo blocco si crea `ExpandedStackedCols4.png` nella directory di lavoro dell'applicazione. Il file contiene un codice a barre ad alta risoluzione che può essere letto da qualsiasi lettore DataBar standard.

## Passo 4: Re‑inizializza il generatore per un layout diverso

Per dimostrare un layout a righe, è necessario un nuovo istanza di `BarcodeGenerator`. Re‑inizializzare garantisce che l'impostazione di colonna precedente non influisca sulla nuova configurazione.

```csharp
// Step 4.1: Create a new generator with the same data string
generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Long data string");
```

## Passo 5: Configura il codice a barre per usare un layout a 3 righe

L'API DataBar supporta anche una disposizione a righe. Impostare la proprietà `Rows` definisce quante sezioni orizzontali conterrà il simbolo.

```csharp
// Step 5.1: Apply a 3‑row layout
generator.Parameters.Barcode.DataBar.Rows = 3;

// Step 5.2: Save the row‑oriented barcode
generator.Save("ExpandedStackedRows3.png", BarCodeImageFormat.Png);
```

**Perché potresti scegliere le righe anziché le colonne**

Le righe sono utili quando l'altezza dell'etichetta è limitata ma la larghezza è ampia. Un layout a tre righe comprime il codice a barre verticalmente mantenendo la quantità necessaria di dati.

## File sorgente completo

Di seguito trovi un `Program.cs` completo e autonomo che puoi compilare ed eseguire direttamente. Include sia gli esempi a colonna sia a riga, così otterrai due file PNG con una singola esecuzione.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeGeneratorExample
{
    class Program
    {
        static void Main(string[] args)
        {
            // Data to encode – replace with your own value if needed
            const string data = "Long data string";

            // ---------- Column layout (4 columns) ----------
            var columnGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                data);

            // Set 4‑column layout
            columnGenerator.Parameters.Barcode.DataBar.Columns = 4;

            // Save the column image
            columnGenerator.Save("ExpandedStackedCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved ExpandedStackedCols4.png (4‑column layout)");

            // ---------- Row layout (3 rows) ----------
            var rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                data);

            // Set 3‑row layout
            rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

            // Save the row image
            rowGenerator.Save("ExpandedStackedRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved ExpandedStackedRows3.png (3‑row layout)");
        }
    }
}
```

### Output previsto

Dopo aver eseguito il programma vedrai due messaggi nella console che confermano la creazione dei file:

```
Saved ExpandedStackedCols4.png (4‑column layout)
Saved ExpandedStackedRows3.png (3‑row layout)
```

Entrambi i file PNG mostreranno un codice a barre DataBar Expanded Stacked che codifica la stringa `"Long data string"`. La scansione di ciascuna immagine con un lettore di codici a barre standard restituisce i dati originali.

## Domande frequenti e casi particolari

| Domanda | Risposta |
|----------|--------|
| **Posso cambiare il formato immagine?** | Sì. Sostituisci `BarCodeImageFormat.Png` con `Jpeg`, `Bmp` o `Tiff` a seconda delle tue esigenze. |
| **E se la stringa di dati è più corta?** | Il formato DataBar regola automaticamente le dimensioni del simbolo; non è necessario modificare le impostazioni di layout. |
| **Come imposto le dimensioni del codice a barre (larghezza/altezza)?** | Usa `generator.Parameters.Image.Width` e `generator.Parameters.Image.Height` prima di chiamare `Save`. |
| **È possibile aggiungere una didascalia leggibile dall'uomo?** | Imposta `generator.Parameters.Barcode.CodeText` e abilita `generator.Parameters.Barcode.CodeLocation = CodeLocation.Above`. |
| **Quali versioni di .NET sono supportate?** | Aspose.BarCode supporta .NET Standard 2.0, .NET 5/6 e .NET Framework 4.6.1+. |

Affrontare queste variazioni rende l'**esempio di generatore di codici a barre** sufficientemente robusto per l'uso in produzione.

## Consigli professionali

* **Riutilizza l'oggetto generator solo quando il layout rimane invariato.** Creare una nuova istanza per ogni layout, come mostrato nei Passi 4‑5, evita il trasferimento accidentale di proprietà.  
* **Valida il codice a barre generato** con `generator.Validate()` se devi garantire la conformità agli standard ISO/GS1.  
* **Elaborazione batch:** Avvolgi la logica di colonna e riga all'interno di un ciclo che itera su un elenco di configurazioni di layout. Questo riduce la duplicazione del codice quando ti servono molte varianti.

## Conclusione

Questo **esempio di generatore di codici a barre** dimostra come **generare barcode C#** che produce sia un codice a barre DataBar Expanded Stacked a 4 colonne sia uno a 3 righe. Ora disponi di un programma completo e funzionante, di una comprensione delle proprietà chiave (`Columns`, `Rows`) e di consigli pratici per estendere la soluzione.

Successivamente, esplora argomenti correlati come **personalizzare i colori del codice a barre**, **incorporare codici a barre in documenti PDF** o **generare codici QR con Aspose.BarCode**. Ognuno di questi temi si basa sugli stessi principi API trattati qui.

Sentiti libero di sperimentare con diverse stringhe di dati, formati immagine e combinazioni di layout. Buona programmazione!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API e a esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Generate Aspose.BarCode Databar barcode using .NET API – Row & Column Configuration](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}