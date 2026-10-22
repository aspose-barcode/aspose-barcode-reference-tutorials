---
category: general
date: 2026-10-21
description: Crea rapidamente un codice a barre Databar impilato usando C#. Impara
  a impostare la dimensione X, regolare il rapporto d'aspetto e salvare le immagini
  PNG in questo tutorial completo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode generator C#
- set aspect ratio
- save barcode image
language: it
lastmod: 2026-10-21
og_description: crea un codice a barre databar stacked in C# con Aspose.BarCode. Segui
  questa guida per configurare la dimensione X, modificare il rapporto d'aspetto e
  esportare file PNG.
og_image_alt: C# generated DataBar stacked barcode saved as PNG with aspect ratio
  15
og_title: Crea un codice a barre Databar impilato in C# – guida completa alla programmazione
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: create databar stacked barcode quickly using C#. Learn to set X‑dimension,
    adjust aspect ratio, and save PNG images in this complete tutorial.
  headline: How to create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- DataBar
title: Come creare un codice a barre Databar impilato in C# – guida passo passo
url: /it/python-java/general/how-to-create-databar-stacked-barcode-in-c-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un databar stacked barcode in C# – guida passo‑passo

Se hai bisogno di **creare un databar stacked barcode** in un'applicazione .NET, questa guida ti mostra esattamente come fare. Vedrai come configurare la X‑dimension, modificare il rapporto d'aspetto e salvare il codice a barre come file PNG.

Generare un DataBar stacked barcode non richiede una pipeline di build complessa. Questo tutorial copre tutto ciò di cui hai bisogno: pacchetti richiesti, spiegazione riga per riga del codice e consigli per le difficoltà comuni. Alla fine potrai produrre più immagini di codici a barre con diversi rapporti d'aspetto in un unico metodo.

## Cosa ti serve

* SDK .NET 6.0 o successivo installato  
* Visual Studio 2022 (o qualsiasi IDE che supporti C#)  
* Pacchetto NuGet **Aspose.BarCode for .NET** – la libreria che fornisce `BarcodeGenerator` e `EncodeTypes`  

Puoi aggiungere il pacchetto con il seguente comando:

```bash
dotnet add package Aspose.BarCode
```

## Passo 1: Configura il progetto e importa i namespace

Crea un nuovo progetto console o aggiungi il codice a uno esistente. Importa i namespace richiesti affinché il compilatore riconosca le classi del codice a barre.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Queste istruzioni `using` espongono `BarcodeGenerator`, `EncodeTypes` e `BarCodeImageFormat` utilizzati più avanti nell'esempio.

## Passo 2: Definisci la cartella di output

Scegli una cartella dove verranno scritti i file PNG generati. L'uso di un percorso assoluto o relativo funziona allo stesso modo; l'esempio utilizza una cartella relativa chiamata `Barcodes`.

```csharp
// Step 1: Define the output folder
string path = "Barcodes/";

// Ensure the folder exists
if (!System.IO.Directory.Exists(path))
{
    System.IO.Directory.CreateDirectory(path);
}
```

Creare la cartella programmaticamente previene errori di runtime quando la directory è assente.

## Passo 3: Inizializza il generatore **create databar stacked barcode**

Crea un'istanza di `BarcodeGenerator` con `EncodeTypes.DatabarStackedOmniDirectional`. I dati di esempio `(01)12345678901231` seguono il formato GS1‑128 richiesto da DataBar.

```csharp
// Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

L'oggetto generatore contiene tutti i parametri che influenzano l'aspetto visivo del codice a barre.

## Passo 4: Imposta la X‑dimension (larghezza in pixel della barra più piccola)

La X‑dimension controlla la dimensione complessiva del codice a barre senza modificare i dati codificati. Un valore di `2` pixel fornisce un'immagine chiara e leggibile per la maggior parte delle risoluzioni dello schermo.

```csharp
// Step 3: Set the X-dimension (pixel width of the smallest bar)
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Regola questo valore se ti serve un codice a barre più grande o più piccolo; mantieni costante il rapporto tra larghezza e altezza.

## Passo 5: Configura il rapporto d'aspetto e salva la prima immagine

Il rapporto d'aspetto determina la relazione altezza‑larghezza di un DataBar stacked barcode. Un rapporto d'aspetto di `15` è un valore predefinito comune che produce un'immagine compatta.

```csharp
// Step 4: Configure an aspect ratio of 15 and save the barcode image
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
generator.Save($"{path}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Il metodo `Save` scrive un file PNG nella cartella definita in precedenza. Il nome del file indica chiaramente il rapporto d'aspetto utilizzato.

### Output previsto per il rapporto d'aspetto 15

Il `DatabarAspectRatio15.png` generato appare simile all'illustrazione qui sotto.

![Immagine del codice a barre generata con rapporto d'aspetto 15](https://example.com/images/databar-aspect15.png "Immagine del codice a barre generata con rapporto d'aspetto 15")

*Testo alternativo:* `create databar stacked barcode image saved with aspect ratio 15`

## Passo 6: Cambia il rapporto d'aspetto e salva una seconda immagine

Puoi riutilizzare la stessa istanza di `BarcodeGenerator` per produrre variazioni. Cambiando `AspectRatio` a `30` raddoppia l'altezza di ogni pila di barre, il che può essere necessario per la stampa ad alta risoluzione.

```csharp
// Step 5: Change the aspect ratio to 30 and save the new barcode image
generator.Parameters.Barcode.DataBar.AspectRatio = 30;
generator.Save($"{path}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

### Output previsto per il rapporto d'aspetto 30

L'immagine `DatabarAspectRatio30.png` è più alta, mantenendo la stessa larghezza e aumentando la leggibilità per scanner a distanza.

![Immagine del codice a barre generata con rapporto d'aspetto 30](https://example.com/images/databar-aspect30.png "Immagine del codice a barre generata con rapporto d'aspetto 30")

*Testo alternativo:* `create databar stacked barcode image saved with aspect ratio 30`

## Codice sorgente completo

Unendo tutti i passaggi si ottiene un programma autonomo che puoi eseguire immediatamente.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Define the output folder
            string path = "Barcodes/";
            if (!System.IO.Directory.Exists(path))
                System.IO.Directory.CreateDirectory(path);

            // Initialize the generator with DataBar Stacked Omnidirectional encoding
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");

            // Set X‑dimension (pixel width of the smallest bar)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image: aspect ratio 15
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;
            generator.Save($"{path}DatabarAspectRatio15.png", BarCodeImageFormat.Png);

            // Second image: aspect ratio 30
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            generator.Save($"{path}DatabarAspectRatio30.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images created successfully.");
        }
    }
}
```

Compila ed esegui il programma. Dopo l'esecuzione, la directory `Barcodes` contiene due file PNG, ciascuno rappresentante un **create databar stacked barcode** con un diverso rapporto d'aspetto.

## Consigli professionali e problemi comuni

* **Consiglio:** Mantieni la X‑dimension tra 1 px e 4 px per la maggior parte dei casi d'uso su schermo. Valori più alti aumentano la dimensione del file senza migliorare l'affidabilità della scansione.  
* **Problema:** Modificare il valore di `EncodeTypes` dopo aver creato il generatore non aggiorna la codifica interna. Specifica sempre il `EncodeTypes` corretto nel costruttore.  
* **Consiglio:** Quando hai bisogno di più di due rapporti d'aspetto, itera su un array di valori interi e chiama `Save` all'interno del ciclo. Questo riduce la duplicazione del codice.  
* **Problema:** Salvare in un percorso senza permessi di scrittura genera un'`UnauthorizedAccessException`. Assicurati che l'applicazione venga eseguita con i diritti di file‑system appropriati.

## Conclusione

Ora sai come **creare un databar stacked barcode** in C# usando Aspose.BarCode. La guida ha coperto la configurazione dell'ambiente, la configurazione della X‑dimension, la regolazione del rapporto d'aspetto e il salvataggio dei file PNG. Con questa base puoi generare ulteriori variazioni, integrare la creazione di codici a barre nelle API web o incorporare le immagini nei report PDF.

Successivamente, esplora argomenti correlati come le migliori pratiche di scansione per **DataBar Stacked Omnidirectional**, l'incorporamento di codici a barre nelle risposte **ASP.NET Core**, o la generazione di **QR code** con la stessa libreria. Sperimenta con diversi `EncodeTypes` e formati immagine per soddisfare le esigenze della tua applicazione.

Buona programmazione!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come creare immagini PNG databar con C# e Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [Come impostare le colonne per un Databar Expanded Stacked barcode – guida completa C#](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [databar stacked omnidirectional barcode in C# – Guida completa](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}