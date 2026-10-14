---
category: general
date: 2026-10-02
description: Scopri come impostare colonne e righe in un generatore di codici a barre
  C# per creare codici a barre DataBar. Guida passo‑passo con codice completo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to set columns
- how to set rows
- create databar barcode
language: it
lastmod: 2026-10-02
og_description: Guida al generatore di codici a barre C# – impara come impostare colonne
  e righe per creare codici a barre DataBar con esempi di codice completi.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with a C#
  barcode generator
og_title: 'Generatore di codici a barre C#: impostare colonne e righe per i codici
  DataBar'
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to set columns and rows in a C# barcode generator to create
    DataBar barcodes. Step‑by‑step guide with complete code.
  headline: How to use a C# barcode generator to create DataBar barcodes with custom
    columns and rows
  type: TechArticle
tags:
- barcode
- c#
- databar
title: Come utilizzare un generatore di codici a barre C# per creare codici a barre
  DataBar con colonne e righe personalizzate
url: /it/python-java/general/how-to-use-a-c-barcode-generator-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come utilizzare un generatore di codici a barre C# per creare codici DataBar con colonne e righe personalizzate

Se hai bisogno di un **c# barcode generator** che possa produrre codici DataBar con configurazioni precise di colonne e righe, questo tutorial ti mostra esattamente come fare. Vedrai perché regolare colonne e righe è importante e otterrai un esempio completo, pronto‑da‑eseguire, che crea sia un codice DataBar Expanded Stacked a 4 colonne sia uno a 3 righe.

Nelle sezioni seguenti copriamo:

* I prerequisiti per utilizzare la libreria Aspose.BarCode per .NET.
* Come impostare colonne (`how to set columns`) e righe (`how to set rows`) su un codice DataBar.
* Un programma console C# completo che puoi copiare, compilare ed eseguire.
* I file di output previsti e consigli per la risoluzione dei problemi.

Alla fine di questa guida sarai in grado di **create databar barcode** immagini su misura per i requisiti del tuo layout.

## Prerequisiti

Prima di iniziare, assicurati di avere:

| Requisito | Motivo |
|-----------|--------|
| .NET 6.0 SDK o successivo | Fornisce l'ambiente di esecuzione per il codice C#. |
| Visual Studio 2022 (o qualsiasi IDE che supporti .NET) | Facilita la creazione del progetto e il debug. |
| Pacchetto NuGet Aspose.BarCode per .NET | Fornisce la classe `BarcodeGenerator` usata negli esempi. |
| Permesso di scrittura su una cartella per i file PNG di output | Il generatore scrive le immagini del codice a barre su disco. |

Installa il pacchetto Aspose.BarCode con il seguente comando:

```bash
dotnet add package Aspose.BarCode
```

## Passo 1: Creare un codice DataBar Expanded Stacked di base

Il primo passo è istanziare un **c# barcode generator** con il formato `EncodeTypes.DatabarExpandedStacked`. Questo formato è un codice DataBar bidimensionale che può codificare fino a 74 caratteri numerici.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// ...

// Create a generator for a DataBar Expanded Stacked barcode
var generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

Il costruttore riceve due argomenti:

* `EncodeTypes.DatabarExpandedStacked` – indica alla libreria quale simbologia utilizzare.
* `"Databar Expanded Stacked long"` – il testo che verrà codificato.

## Passo 2: Come impostare le colonne

Le colonne influenzano la densità orizzontale del codice DataBar. Aumentare il numero di colonne rende il codice più largo, il che può migliorare l'affidabilità della scansione su stampanti a bassa risoluzione.

```csharp
// Set the number of columns to 4
generator.Parameters.Barcode.DataBar.Columns = 4;
```

**Perché 4 colonne?**  
Quattro colonne offrono un buon equilibrio tra dimensione e leggibilità per la maggior parte delle applicazioni al dettaglio. Puoi sperimentare valori da 1 a 8; la libreria regolerà automaticamente la larghezza del modulo.

## Passo 3: Salvare il codice configurato con le colonne

```csharp
// Save the image that uses the column setting
generator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

L'immagine viene salvata come file PNG, che preserva i bordi nitidi richiesti dagli scanner di codici a barre.

## Passo 4: Creare un generatore separato per la configurazione delle righe

La configurazione delle righe funziona allo stesso modo ma influisce sulla densità verticale. Per evitare di mescolare le impostazioni di colonne e righe, creiamo una nuova istanza del generatore.

```csharp
var generatorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## Passo 5: Come impostare le righe

```csharp
// Set the number of rows to 3
generatorRows.Parameters.Barcode.DataBar.Rows = 3;
```

**Quando usare più righe?**  
Aggiungere righe rende il codice più alto, il che può essere utile quando lo spazio stampato è limitato orizzontalmente ma abbondante verticalmente (ad esempio, su un'etichetta di prodotto più alta che larga).

## Passo 6: Salvare il codice configurato con le righe

```csharp
// Save the image that uses the row setting
generatorRows.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

Entrambi i file PNG (`DatabarCols4.png` e `DatabarRows3.png`) appariranno nella cartella `C:\Barcodes`.

## Esempio completo, eseguibile

Di seguito è riportata un'applicazione console autonoma che incorpora tutti i passaggi descritti sopra. Copia il codice in un nuovo progetto console .NET e eseguilo.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace DatabarDemo
{
    class Program
    {
        static void Main()
        {
            // Output directory – change to a folder that exists on your machine
            const string outputDir = @"C:\Barcodes";

            // -------------------------------------------------
            // 1️⃣ Create a barcode generator for column testing
            // -------------------------------------------------
            var colGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Set the number of columns (how to set columns)
            colGenerator.Parameters.Barcode.DataBar.Columns = 4;

            // Save the column‑based barcode
            string colPath = System.IO.Path.Combine(outputDir, "DatabarCols4.png");
            colGenerator.Save(colPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Column barcode saved to: {colPath}");

            // -------------------------------------------------
            // 2️⃣ Create a barcode generator for row testing
            // -------------------------------------------------
            var rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Set the number of rows (how to set rows)
            rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

            // Save the row‑based barcode
            string rowPath = System.IO.Path.Combine(outputDir, "DatabarRows3.png");
            rowGenerator.Save(rowPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Row barcode saved to: {rowPath}");

            // -------------------------------------------------
            // 3️⃣ Confirmation message
            // -------------------------------------------------
            Console.WriteLine("Both DataBar barcodes have been generated successfully.");
        }
    }
}
```

### Cosa fa il codice

| Sezione | Scopo |
|---------|-------|
| **Importazioni di namespace** | Importa `Aspose.BarCode` e `Aspose.BarCode.Generation`. |
| **Directory di output** | Centralizza il percorso così devi modificare una sola riga se sposti la cartella. |
| **Generatore di colonne** | Dimostra **how to set columns** su un `c# barcode generator`. |
| **Generatore di righe** | Dimostra **how to set rows** su un `c# barcode generator`. |
| **Chiamate Save** | Scrive i file PNG su disco, rendendoli pronti per la scansione o l'inclusione nei report. |
| **Output console** | Fornisce feedback immediato, utile durante lo sviluppo. |

## Output previsto

Dopo aver eseguito il programma dovresti vedere due file PNG:

* **DatabarCols4.png** – un codice più largo che riflette quattro colonne.
* **DatabarRows3.png** – un codice più alto che riflette tre righe.

Entrambe le immagini contengono il testo *“Databar Expanded Stacked long”* codificato nella simbologia DataBar Expanded Stacked. Puoi aprirle con qualsiasi visualizzatore di immagini o passarle a uno scanner di codici a barre per verificare la leggibilità.

## Problemi comuni e come evitarli

| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| **Eccezione di accesso al file** | La cartella di output non esiste o non hai i permessi di scrittura. | Crea la cartella manualmente o esegui il programma con privilegi elevati. |
| **Valori di colonna/riga errati** | La libreria accetta solo valori da 1‑8 per le colonne e da 1‑4 per le righe. | Convalida i valori prima di assegnarli, ad es. `if (value < 1 || value > 8) throw new ArgumentOutOfRangeException();`. |
| **Codice a barre non leggibile** | L'immagine generata è troppo piccola per la risoluzione dello scanner. | Aumenta `ImageHeight` o `ImageWidth` usando `generator.Parameters.Image.Height` / `...Width`. |
| **Troncamento del testo** | Il testo codificato supera la lunghezza massima per la variante DataBar scelta. | Usa una stringa più corta o passa a `EncodeTypes.DatabarExpanded` se ti serve più capacità. |

## Consigli professionali

* **Cache del generatore** – Se devi creare molti codici a barre con le stesse impostazioni di colonna/riga, riutilizza la stessa istanza `BarcodeGenerator` e modifica solo la proprietà `CodeText`.
* **Elaborazione batch** – Itera su una collezione di identificatori di prodotto, imposta `generator.CodeText` all'interno del ciclo e chiama `Save` con un nome file unico per ogni iterazione.
* **Prestazioni** – Per scenari ad alto volume, disabilita l'anti‑aliasing (`generator.Parameters.Image.AntiAlias = false`) per velocizzare la generazione dell'immagine senza influire sulla qualità della scansione.

## Prossimi passi

Ora che sai **how to set columns** e **how to set rows** con un **c# barcode generator**, potresti voler esplorare:

* **Aggiungere testo leggibile dall'uomo** sotto il codice a barre (`generator.Parameters.Barcode.CodeTextLocation`).
* **Modificare i colori** (`generator.Parameters.Image.ForegroundColor` e `BackgroundColor`).
* **Generare altre varianti DataBar** come `DatabarLimited` o `DatabarExpanded`.
* **Incorporare i codici a barre in report PDF** usando Aspose.PDF.

Ognuno di questi argomenti si basa sulle fondamenta trattate qui e ti aiuta a creare soluzioni di codici a barre più ricche e pronte per la produzione.

---

*Buon coding! Se incontri problemi, sentiti libero di lasciare un commento o consultare la documentazione di Aspose.BarCode per approfondire i dettagli dell'API.*

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API e a esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come impostare colonne e righe del codice a barre con C# BarcodeGenerator](/barcode/english/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/)
- [Esempio di Barcode Generator in C# – Impostare colonne, righe ed esportare immagine](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Come utilizzare un generatore di codici a barre C# per creare codici DataBar](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}