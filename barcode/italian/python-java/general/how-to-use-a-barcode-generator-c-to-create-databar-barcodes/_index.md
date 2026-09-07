---
category: general
date: 2026-09-07
description: Tutorial C# per generatore di codici a barre che mostra come generare
  file PNG di codici a barre e creare codici DataBar con righe e colonne personalizzabili.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- generate barcode PNG
- create DataBar barcode
language: it
lastmod: 2026-09-07
og_description: 'tutorial generatore di codici a barre C#: impara a generare file
  PNG di codici a barre e a creare codici DataBar con righe e colonne personalizzate
  in pochi minuti'
og_image_alt: Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator
  C#
og_title: generatore di codici a barre C# – crea codici DataBar e immagini PNG
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: barcode generator C# tutorial that shows you how to generate barcode
    PNG files and create DataBar barcodes with customizable rows and columns
  headline: How to use a barcode generator C# to create DataBar barcodes
  type: TechArticle
tags:
- barcode
- C#
- DataBar
title: Come usare un generatore di codici a barre C# per creare codici a barre DataBar
url: /it/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come utilizzare un generatore di codici a barre C# per creare codici a barre DataBar

Se ti serve un **barcode generator C#** per creare codici a barre di alta qualità, questa guida ti mostra come **generare barcode PNG** e **creare DataBar barcodes** con righe e colonne personalizzate. Che tu stia costruendo un sistema di inventario retail o una piattaforma di ticketing, i passaggi seguenti ti permettono di produrre un codice a barre DataBar Expanded Stacked in un unico esempio autonomo.

In questo tutorial imparerai:

* Come istanziare il `BarcodeGenerator` per la simbologia DataBar Expanded Stacked.  
* Come regolare le impostazioni di colonna e riga per soddisfare le specifiche ISO / GS1.  
* Come salvare l'output come immagine PNG che può essere incorporata in pagine web o stampata su etichette.  

Non sono richiesti servizi esterni—solo la libreria Aspose.BarCode per .NET (o qualsiasi libreria compatibile che segua la stessa API). Il codice funziona su .NET 6+ e su Visual Studio, Rider o qualsiasi IDE che supporti C#.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6 SDK o versioni successive installate.  
* Un riferimento al pacchetto NuGet `Aspose.BarCode` (o una libreria equivalente che fornisca `BarcodeGenerator`, `EncodeTypes` e `BarCodeImageFormat`).  
* Familiarità di base con la sintassi C# e la struttura di un progetto.  

Puoi aggiungere il pacchetto dalla riga di comando:

```bash
dotnet add package Aspose.BarCode
```

## Passo 1: Inizializzare il barcode generator C# per DataBar Expanded Stacked

Il primo passo è creare un'istanza di `BarcodeGenerator` che punti alla simbologia **DataBar Expanded Stacked**. Questo oggetto contiene tutti i parametri di rendering, incluso il testo da codificare.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,          // Symbology
    "Databar Expanded Stacked long");            // Data to encode
```

**Perché è importante:** il valore enum `EncodeTypes.DatabarExpandedStacked` indica alla libreria quale standard di codice a barre applicare. Usare l'enum corretto garantisce che l'immagine generata sia conforme alle specifiche GS1 DataBar.

## Passo 2: Configurare il numero di colonne (vengono usate le righe predefinite)

DataBar Expanded Stacked può essere suddiviso in più colonne. Modificare il conteggio delle colonne cambia la densità visiva e può aiutare a far entrare stringhe di dati più lunghe in spazi limitati.

```csharp
// Step 2: Set the number of columns (default rows are used)
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

**Consiglio professionale:** il conteggio predefinito delle colonne è 1. Impostarlo a 4 crea quattro colonne impilate, ideale per stringhe numeriche più lunghe mantenendo l'altezza del codice a barre gestibile.

## Passo 3: Generare barcode PNG con l'impostazione delle colonne applicata

Ora salva il codice a barre come immagine PNG. PNG preserva i bordi nitidi necessari per gli scanner e funziona bene sia sul web sia su supporti di stampa.

```csharp
// Step 3: Save the barcode image with the column setting applied
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

Il file `DatabarCols4.png` contiene un **barcode PNG** che puoi incorporare direttamente in HTML:

```html
<img src="DatabarCols4.png" alt="Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#">
```

## Passo 4: Creare un'istanza separata del generatore per la configurazione delle righe

Se devi controllare il numero di righe invece delle colonne, istanzia un nuovo `BarcodeGenerator`. Riutilizzare la stessa istanza dopo aver cambiato una dimensione può generare artefatti di layout inattesi, quindi un nuovo oggetto è l'approccio più sicuro.

```csharp
// Step 4: Create a new generator instance for the same barcode type
BarcodeGenerator rowBarcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## Passo 5: Impostare il numero di righe (vengono usate le colonne predefinite)

Le righe influenzano l'impilamento verticale dei moduli del codice a barre. Aumentare le righe può rendere il codice più alto, cosa a volte necessaria per certe dimensioni di etichette.

```csharp
// Step 5: Set the number of rows (default columns are used)
rowBarcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

**Perché righe vs. colonne:** le colonne dividono il codice a barre orizzontalmente, mentre le righe lo estendono verticalmente. Scegli l'orientamento che meglio si adatta al layout della tua etichetta.

## Passo 6: Generare barcode PNG con l'impostazione delle righe applicata

Infine, salva il codice a barre regolato per le righe come file PNG.

```csharp
// Step 6: Save the barcode image with the row setting applied
rowBarcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

Ora disponi di due file PNG distinti:

* `DatabarCols4.png` – 4 colonne, 1 riga.  
* `DatabarRows3.png` – 1 colonna, 3 righe.

Entrambe le immagini sono pronte per l'uso immediato in applicazioni, report o etichette stampate.

## Come generare file barcode PNG in C# con dimensioni personalizzate

Il modello mostrato sopra può essere riutilizzato per qualsiasi variante DataBar o altre simbologie supportate dalla libreria. Ecco un modello compatto che puoi copiare‑incollare in una classe di utilità:

```csharp
public static void GenerateDatabar(string data, int columns = 1, int rows = 1, string outputPath = "output.png")
{
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, data);
    generator.Parameters.Barcode.DataBar.Columns = columns;
    generator.Parameters.Barcode.DataBar.Rows = rows;
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Chiama il metodo così:

```csharp
GenerateDatabar("1234567890123", columns: 4, outputPath: "DatabarCols4.png");
GenerateDatabar("1234567890123", rows: 3, outputPath: "DatabarRows3.png");
```

**Casi limite da considerare**

* **Lunghezza dei dati** – DataBar Expanded Stacked può codificare fino a 74 caratteri numerici. Superare questo limite genera un'eccezione. Convalida la lunghezza dell'input prima di chiamare il generatore.  
* **Dimensioni non valide** – La libreria limita le colonne a 1‑4 e le righe a 1‑3 per questa simbologia. Valori fuori da questi intervalli verranno ignorati o causeranno un errore.  
* **DPI dell'immagine** – Se ti serve una risoluzione più alta per la stampa, imposta `generator.Parameters.ImageResolution` prima di salvare.

## Output previsto

Quando apri `DatabarCols4.png` o `DatabarRows3.png` dovresti vedere un codice a barre DataBar chiaro e ad alto contrasto. Scansionando l'immagine con uno scanner compatibile GS1 otterrai il testo originale `"Databar Expanded Stacked long"`.

![Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#](image.png)

*Testo alternativo: Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#*

## Conclusione

Questo tutorial ha dimostrato come un **barcode generator C#** possa essere usato per **creare DataBar barcodes** e **generare barcode PNG** con impostazioni personalizzate di righe e colonne. Seguendo i sei passaggi—inizializzare il generatore, configurare colonne o righe e salvare come PNG—ottieni immagini pronte per la produzione, adatte a sistemi di inventario, ticketing o qualsiasi scenario che richieda un rendering affidabile dei codici a barre.

Successivamente, potresti esplorare:

* Aggiungere colore o immagini di sfondo al PNG (sempre compatibile con la maggior parte degli scanner).  
* Usare altre simbologie come QR, Code 128 o PDF417 tramite la stessa API `BarcodeGenerator`.  
* Incorporare il PNG generato direttamente nelle viste ASP.NET Core MVC o nei componenti Blazor.

Sentiti libero di sperimentare con diverse stringhe di dati, dimensioni e formati immagine (ad es., JPEG, BMP). Lo stesso schema si applica, rendendo il **barcode generator C#** uno strumento versatile in qualsiasi toolbox di sviluppatore .NET. Buona programmazione!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API e a esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Generate barcode C# – Create DataBar barcode](/barcode/english/python-java/general/generate-barcode-c-create-databar-barcode/)
- [Barcode Generator Example – Build DataBar Image in C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}