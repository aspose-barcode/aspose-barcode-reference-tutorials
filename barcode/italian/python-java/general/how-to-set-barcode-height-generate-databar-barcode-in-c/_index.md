---
category: general
date: 2026-10-12
description: Come impostare l'altezza del codice a barre e generare un codice a barre
  DataBar in C# usando Aspose.BarCode. Segui una guida passo‑passo con codice completo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- generate barcode c#
- how to create databar
- create databar barcode
- change barcode height
language: it
lastmod: 2026-10-12
og_description: Come impostare l'altezza del codice a barre in C# e generare un codice
  a barre DataBar con Aspose.BarCode. Scopri il codice completo, perché ogni passaggio
  è importante e come modificare l'altezza del codice a barre.
og_image_alt: Screenshot showing how to set barcode height in a C# barcode generator
og_title: Come impostare l'altezza del codice a barre e generare il codice a barre
  DataBar in C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to set barcode height and generate a DataBar barcode in C# using
    Aspose.BarCode. Follow a step‑by‑step guide with complete code.
  headline: How to set barcode height, generate DataBar barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Come impostare l'altezza del codice a barre, generare il codice a barre DataBar
  in C#
url: /it/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come impostare l'altezza del codice a barre, generare un codice a barre DataBar in C#

Se hai bisogno di **come impostare il codice a barre** dimensioni programmaticamente, questa guida ti mostra i passaggi esatti. Imparerai a generare un codice a barre DataBar Omni‑directional, a regolare la sua altezza e a salvare entrambe le versioni come file PNG.

Modificare l'altezza delle barre di un codice a barre è una necessità comune quando integri i codici a barre in ricevute, etichette di prodotto o schermi mobili. L'esempio seguente utilizza la libreria Aspose.BarCode, che supporta l'intera gamma di simbologie GS1 DataBar.

## Cosa otterrai

* **how to set barcode** altezza per un codice a barre DataBar Omni‑directional  
* **generate barcode c#** codice che crea due immagini con altezze diverse  
* comprendere i simboli **how to create databar** e perché l'altezza delle barre è importante  
* applicare la logica **change barcode height** senza ricreare il generatore  

Non sono necessari strumenti esterni oltre al pacchetto NuGet Aspose.BarCode e a un runtime .NET 6+.

## Prerequisiti

* .NET 6 SDK o versione successiva installata  
* Visual Studio 2022 (o qualsiasi editor C#)  
* Aspose.BarCode per .NET – installa tramite `dotnet add package Aspose.BarCode`  

> **Suggerimento professionale:** Usa la licenza di prova gratuita di Aspose se non hai una chiave commerciale; l'API funziona allo stesso modo.

## Passo 1: Installa il pacchetto Aspose.BarCode

Apri un terminale nella cartella del tuo progetto ed esegui:

```bash
dotnet add package Aspose.BarCode
```

Il pacchetto aggiunge lo spazio dei nomi `Aspose.BarCode`, che contiene la classe `BarcodeGenerator` che utilizzeremo per generare immagini **generate barcode c#**.

## Passo 2: Crea un generatore di codici a barre DataBar

La prima azione concreta per i parametri **how to set barcode** è istanziare `BarcodeGenerator` con la simbologia desiderata e la stringa di dati.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 2: Initialize the generator for a DataBar Omni‑directional barcode
var barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, // symbology
    "(01)12345678901231");               // GS1 data payload
```

*Perché è importante:* `EncodeTypes.DatabarOmniDirectional` produce un DataBar compatto e omnidirezionale che può essere scansionato da qualsiasi angolazione—ideale per etichette piccole.

## Passo 3: Imposta i parametri comuni del codice a barre (inclusa l'altezza iniziale della barra)

Ora rispondiamo alla **how to set barcode** X‑dimension e all'altezza della barra prima di salvare la prima immagine.

```csharp
// Step 3: Configure X‑dimension (module width) and initial bar height
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;    // 2‑pixel modules
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;   // 30‑pixel height
```

La X‑dimension controlla la larghezza complessiva di ogni barra; un'impostazione di 2 pixel produce un'immagine leggibile e nitida sulla maggior parte degli schermi. Il passo **change barcode height** successivo riutilizzerà lo stesso generatore, risparmiando tempo e memoria.

## Passo 4: Salva la prima immagine del codice a barre (altezza 30 pixel)

```csharp
// Step 4: Save the 30‑pixel barcode image
barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
```

Il file `DatabarHeight30.png` ora contiene un codice a barre DataBar con un'altezza della barra di 30 pixel.

## Passo 5: Modifica solo l'altezza della barra a 60 pixel

Per dimostrare **change barcode height**, modifichiamo solo la proprietà `BarHeight`. Tutte le altre impostazioni rimangono invariate, il che è il modo più efficiente per produrre più dimensioni da un unico generatore.

```csharp
// Step 5: Update the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

## Passo 6: Salva la seconda immagine del codice a barre (altezza 60 pixel)

```csharp
// Step 6: Save the 60‑pixel barcode image
barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
```

Ora hai due file PNG, ciascuno con un'altezza della barra diversa ma con dati e X‑dimension identici.

## Esempio completo, eseguibile

Di seguito trovi il programma completo che puoi copiare‑incollare in una nuova applicazione console (`dotnet new console`) ed eseguire immediatamente.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator for a DataBar Omni‑directional barcode
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");

        // Set X‑dimension and initial bar height (30 pixels)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image (30‑pixel height)
        barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight30.png");

        // Change only the bar height to 60 pixels
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image (60‑pixel height)
        barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight60.png");
    }
}
```

### Output previsto

L'esecuzione del programma produce due file nella directory di lavoro dell'eseguibile:

* `DatabarHeight30.png` – un codice a barre DataBar con barre alte 30 pixel.  
* `DatabarHeight60.png` – lo stesso codice a barre, ma ogni barra è alta il doppio.

Entrambe le immagini possono essere aperte con qualsiasi visualizzatore di immagini o incorporate direttamente in PDF, pagine HTML o etichette stampate.

## Perché regolare l'altezza della barra è importante

* **Affidabilità della scansione:** Alcuni scanner hanno difficoltà con barre molto corte su supporti a bassa risoluzione; aumentare l'altezza migliora il rilevamento.  
* **Vincoli di design:** Un'app mobile può richiedere un codice a barre compatto (30 px) mentre una ricevuta stampata può necessitare di uno più grande (60 px).  
* **Conformità normativa:** Alcuni settori impongono un'altezza minima della barra per i simboli GS1 DataBar.

Riutilizzando la stessa istanza di `BarcodeGenerator`, eviti l'overhead di riparsare la stringa di dati, il che è particolarmente vantaggioso in ambienti ad alto volume.

## Variazioni comuni e casi limite

| Situazione | Modifica consigliata |
|-----------|-------------------|
| Necessità di una X‑dimension diversa | Cambia `XDimension.Pixels` prima del primo `Save`. |
| Vuoi una simbologia diversa (es. DataBar Stacked) | Usa `EncodeTypes.DatabarStacked` quando costruisci `BarcodeGenerator`. |
| È necessario incorporare il codice a barre in un PDF | Usa `barcodeGenerator.Save(stream, BarCodeImageFormat.Png)` e aggiungi lo stream a una libreria PDF. |
| Esecuzione su .NET Framework 4.6 | Lo stesso codice funziona; basta referenziare l'assembly Aspose.BarCode appropriato. |

## Suggerimenti professionali per una generazione affidabile di codici a barre

* **Cache the generator** quando generi molti codici a barre con gli stessi dati ma dimensioni diverse.  
* **

## Cosa dovresti imparare dopo?

I tutorial seguenti coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare ulteriori funzionalità dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come generare e regolare l'altezza del codice a barre per Databar unidimensionale usando Aspose.BarCode per .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Come creare immagini PNG Databar con C# e Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [Come generare un codice a barre con dimensioni personalizzate e salvare l'immagine in C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}