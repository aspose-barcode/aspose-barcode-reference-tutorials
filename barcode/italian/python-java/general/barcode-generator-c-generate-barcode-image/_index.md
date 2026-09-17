---
category: general
date: 2026-08-03
description: Il tutorial del generatore di codici a barre C# mostra come generare
  un'immagine di codice a barre con Aspose.BarCode, impostare colonne e righe e salvare
  file PNG per DataBar Expanded Stacked.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- generate barcode image
language: it
lastmod: 2026-08-03
og_description: Il tutorial di Barcode generator C# spiega come generare un'immagine
  di codice a barre usando Aspose.BarCode, configurare le colonne e le righe DataBar
  Expanded Stacked e salvare file PNG.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: Generatore di codici a barre C# – guida passo passo per generare l'immagine
  del codice a barre
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Barcode generator C# tutorial shows how to generate barcode image with
    Aspose.BarCode, set columns and rows, and save PNG files for DataBar Expanded
    Stacked.
  headline: Barcode generator C# – generate barcode image
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Generatore di codici a barre C# – genera immagine del codice a barre
url: /it/python-java/general/barcode-generator-c-generate-barcode-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generatore di codici a barre C# – generare immagine del codice a barre

Se hai bisogno di un generatore di codici a barre C# che possa generare un'immagine di codice a barre per DataBar Expanded Stacked, questa guida ti accompagna passo passo nel processo completo. Imparerai come configurare le impostazioni di colonne e righe, salvare il risultato come PNG e adattare il codice ad altre simbologie.

Generare programmaticamente immagini di codici a barre elimina le operazioni manuali e garantisce coerenza su fatture, etichette di spedizione e sistemi di inventario. Questo tutorial copre tutto ciò di cui hai bisogno, dalla configurazione del progetto al codice sorgente completo, così potrai eseguire l'esempio subito.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6.0 o successivo installato  
* Un IDE come Visual Studio 2022 (qualsiasi editor che supporta C# funziona)  
* Una licenza per **Aspose.BarCode for .NET** – la valutazione gratuita è sufficiente per i test  
* Familiarità di base con la sintassi C#  

Se uno di questi elementi manca, installa il .NET SDK da dotnet.microsoft.com e ottieni il pacchetto NuGet Aspose.BarCode con:

```bash
dotnet add package Aspose.BarCode
```

## Step 1: Create a barcode generator C# project

Crea una nuova applicazione console e aggiungi le direttive `using` richieste:

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
            // The implementation starts in the next sections
        }
    }
}
```

La classe `BarcodeGenerator` è il nucleo dell'API del generatore di codici a barre C#. Riceve il tipo di simbologia e il testo da codificare.

## Step 2: Generate a DataBar Expanded Stacked barcode and set columns

Il primo esempio crea un codice a barre con quattro colonne. Modificando la proprietà `Columns` si cambia la densità visiva della simbologia DataBar Expanded Stacked.

```csharp
// Step 2: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

// Set the number of columns to 4
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the barcode image as PNG
string colsPath = @"YOUR_DIRECTORY\DatabarCols4.png";
barcodeGenerator.Save(colsPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 4 columns saved to {colsPath}");
```

**Perché è importante:** Il numero di colonne influenza la quantità di dati che può essere memorizzata in uno spazio compatto. Impostandolo a 4 si ottiene un codice a barre più largo che rimane leggibile dalla maggior parte degli scanner.

## Step 3: Generate a barcode with custom row count

Il secondo esempio mostra come controllare il layout verticale impostando la proprietà `Rows`. Una configurazione a tre righe è utile quando è necessario un codice a barre più alto per spazio orizzontale limitato.

```csharp
// Step 3: Create a second barcode generator for the same type
BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

// Set the number of rows to 3
barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

// Save the barcode image as PNG
string rowsPath = @"YOUR_DIRECTORY\DatabarRows3.png";
barcodeGeneratorRows.Save(rowsPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 3 rows saved to {rowsPath}");
```

**Perché è importante:** Regolare le righe ti permette di inserire il codice a barre in una colonna stretta mantenendo la leggibilità. Il generatore di codici a barre C# ricalcola automaticamente la dimensione del modulo per rispettare le specifiche.

## Step 4: Full, runnable example

Di seguito trovi un programma autonomo che combina i passaggi precedenti. Copia il codice in `Program.cs`, sostituisci `YOUR_DIRECTORY` con un percorso di cartella esistente e avvia l'applicazione.

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
            // ---------- Generate barcode with 4 columns ----------
            BarcodeGenerator colsGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

            colsGenerator.Parameters.Barcode.DataBar.Columns = 4;

            string colsFile = @"YOUR_DIRECTORY\DatabarCols4.png";
            colsGenerator.Save(colsFile, BarCodeImageFormat.Png);
            Console.WriteLine($"Generated barcode image with columns saved to {colsFile}");

            // ---------- Generate barcode with 3 rows ----------
            BarcodeGenerator rowsGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

            rowsGenerator.Parameters.Barcode.DataBar.Rows = 3;

            string rowsFile = @"YOUR_DIRECTORY\DatabarRows3.png";
            rowsGenerator.Save(rowsFile, BarCodeImageFormat.Png);
            Console.WriteLine($"Generated barcode image with rows saved to {rowsFile}");
        }
    }
}
```

### Expected output

Quando esegui il programma, due file PNG compaiono nella directory di destinazione:

* **DatabarCols4.png** – un codice a barre DataBar Expanded Stacked con quattro colonne  
* **DatabarRows3.png** – gli stessi dati codificati in tre righe  

Apri le immagini con qualsiasi visualizzatore; mostrano codici a barre nitidi e scansionabili pronti per la stampa o l'inserimento in PDF.

## How to generate barcode image with custom dimensions

Se ti serve una dimensione specifica dell'immagine, regola le proprietà `ImageHeight` e `ImageWidth` prima di chiamare `Save`:

```csharp
colsGenerator.Parameters.ImageHeight = 150; // pixels
colsGenerator.Parameters.ImageWidth = 300;  // pixels
colsGenerator.Save(colsFile, BarCodeImageFormat.Png);
```

Modificare le dimensioni non influisce sui dati codificati; scala solo la rappresentazione visiva. Questa tecnica è utile quando si integrano codici a barre in componenti UI con vincoli di layout fissi.

## Common pitfalls and pro tips

* **Separatori di percorso:** Usa stringhe verbatim (`@"C:\Path\file.png"`) o `Path.Combine` per evitare problemi di caratteri di escape su Windows.  
* **Applicazione della licenza:** Senza una licenza valida, le immagini generate contengono una filigrana. Applica la tua licenza all'inizio dell'applicazione:

  ```csharp
  Aspose.BarCode.License license = new Aspose.BarCode.License();
  license.SetLicense("Aspose.BarCode.lic");
  ```

* **Limiti di codifica:** DataBar Expanded Stacked supporta fino a 74 caratteri numerici. Superare questo limite genera un'eccezione. Convalida la lunghezza dell'input prima di creare il generatore.  
* **Prestazioni:** Riutilizzare una singola istanza di `BarcodeGenerator` per più salvataggi riduce l'allocazione di memoria. Cambia le proprietà `Rows` o `Columns` tra i salvataggi solo se il testo codificato rimane lo stesso.

## Next steps

Ora che puoi generare immagini di codici a barre con il generatore di codici a barre C#, considera di esplorare:

* **Simbologie diverse** – prova `EncodeTypes.QR`, `EncodeTypes.Code128` o `EncodeTypes.Pdf417`.  
* **Personalizzazione del colore** – imposta `Parameters.Barcode.ForeColor` e `BackColor` per corrispondere al brand.  
* **Incorporamento in PDF** – combina il PNG generato con Aspose.PDF per creare documenti stampabili.  

Queste estensioni ti consentono di costruire una soluzione di codici a barre completa per applicazioni di inventario, logistica o retail.

---


## What Should You Learn Next?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}