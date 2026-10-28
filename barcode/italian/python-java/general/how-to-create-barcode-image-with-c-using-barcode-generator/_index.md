---
category: general
date: 2026-10-28
description: Crea rapidamente un'immagine di codice a barre in C#. Impara l'uso del
  generatore di codici a barre in C#, come impostare la dimensione dei pixel e come
  modificare il rapporto d'aspetto per DataBar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- how to set pixel size
- how to change aspect ratio
- how to generate databar
language: it
lastmod: 2026-10-28
og_description: Crea un'immagine di codice a barre in C# con un generatore di codici
  a barre. Segui questa guida per impostare la dimensione dei pixel, modificare il
  rapporto d'aspetto e generare codici a barre DataBar.
og_image_alt: Screenshot of a generated barcode image created with C#
og_title: Crea immagine di codice a barre in C# – guida passo passo
schemas:
- author: GroupDocs
  dateModified: '2026-10-28'
  description: Create barcode image in C# quickly. Learn barcode generator c# usage,
    how to set pixel size, and how to change aspect ratio for DataBar.
  headline: How to create barcode image with C# using Barcode Generator
  type: TechArticle
tags:
- barcode
- C#
- imaging
title: Come creare un'immagine di codice a barre con C# usando Barcode Generator
url: /it/python-java/general/how-to-create-barcode-image-with-c-using-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un'immagine di codice a barre con C# usando Barcode Generator

Se hai bisogno di **creare un'immagine di codice a barre** in un'applicazione .NET, questa guida ti mostra esattamente come fare. Vedrai un esempio completo e eseguibile che utilizza la libreria Barcode Generator C# per generare un codice a barre DataBar stacked omnidirectional, impostare la dimensione dei pixel e modificare il rapporto d'aspetto.

Generare codici a barre programmaticamente elimina la necessità di strumenti esterni e ti consente di incorporare l'immagine direttamente in PDF, report o controlli UI. Nei passaggi seguenti copriamo anche **come impostare la dimensione dei pixel** e **come modificare il rapporto d'aspetto**, due requisiti comuni quando ti serve un codice a barre nitido e correttamente scalato.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6.0 SDK o versioni successive installato  
* Un IDE compatibile con C# (Visual Studio, Rider o VS Code)  
* Il pacchetto NuGet `BarcodeGenerator` (ad es., `GroupDocs.Barcode` o `Aspose.Barcode`) installato nel tuo progetto  

Puoi aggiungere il pacchetto con il seguente comando:

```bash
dotnet add package GroupDocs.Barcode
```

> **Consiglio:** Verifica che la versione del pacchetto corrisponda al tuo framework di destinazione per evitare incompatibilità a runtime.

## Creare un'immagine di codice a barre con Barcode Generator C#

Il primo passo è istanziare il generatore con il tipo di codice a barre desiderato e i dati. L'esempio qui sotto crea un codice a barre **DataBar stacked omnidirectional**, ideale per scenari di scansione al dettaglio.

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // Step 1: Create a BarcodeGenerator for DataBar stacked omnidirectional
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example data

        // Step 2: Set the pixel size of the X‑dimension (how to set pixel size)
        barcode.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 3: Save an image with the first aspect ratio (how to generate databar)
        barcode.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcode.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // Step 4: Change the aspect ratio (how to change aspect ratio) and save a second image
        barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcode.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### Perché ogni riga è importante

* **Instantiate `BarcodeGenerator`** – Il costruttore accetta una simbologia di codice a barre (`EncodeTypes.DatabarStackedOmniDirectional`) e la stringa di dati grezzi. Scegliere la simbologia corretta garantisce che lo scanner possa leggere il codice.  
* **Set `XDimension.Pixels`** – Questa proprietà controlla la larghezza dell'elemento barra più piccolo. Un valore di `2` produce un'immagine a grana fine che rimane leggibile sulla maggior parte degli schermi. Aumentalo se ti serve un codice a barre più grande per stampanti a bassa risoluzione.  
* **Configure `AspectRatio`** – La famiglia DataBar supporta diversi rapporti d'aspetto che influenzano la relazione altezza‑larghezza. I valori `15` e `30` sono comuni; `15` produce un codice a barre più corto, mentre `30` ne genera uno più alto.  
* **`Save` method** – Salva il codice a barre generato in un file PNG. Puoi sostituire `BarCodeImageFormat.Png` con `Jpeg` o `Bmp` se il tuo sistema a valle richiede un formato diverso.

## Come impostare la dimensione dei pixel per diversi contesti di rendering

La dimensione dei pixel determina la densità visiva del codice a barre. Se il codice a barre verrà visualizzato su un monitor ad alta DPI, potresti aumentare la dimensione dei pixel a `3` o `4`. Al contrario, per stampanti termiche a bassa risoluzione, una dimensione dei pixel più piccola (ad es., `1`) riduce l'uso di inchiostro.

```csharp
// Example: increase pixel size for a high‑resolution display
barcode.Parameters.Barcode.XDimension.Pixels = 4;
```

**Caso limite:** Impostare la dimensione dei pixel troppo bassa (< 1) genera un `ArgumentOutOfRangeException`. Convalida sempre il valore prima di assegnarlo.

## Come modificare il rapporto d'aspetto senza ricreare il generatore

Modificare il rapporto d'aspetto è un semplice aggiornamento di proprietà; **non** è necessario ricreare l'istanza `BarcodeGenerator`. Questo risparmia memoria e migliora le prestazioni quando hai bisogno di più immagini con forme diverse.

```csharp
// Switch from a short to a tall barcode
barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
barcode.Save("TallDatabar.png", BarCodeImageFormat.Png);
```

Se ti servono più di due rapporti, puoi iterare su un array:

```csharp
int[] ratios = { 15, 20, 25, 30 };
foreach (int ratio in ratios)
{
    barcode.Parameters.Barcode.DataBar.AspectRatio = ratio;
    string fileName = $"DatabarAspectRatio{ratio}.png";
    barcode.Save(fileName, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {fileName}");
}
```

## Output previsto

Eseguendo il programma vengono creati due file PNG (o più, se usi il ciclo). Aprili con qualsiasi visualizzatore di immagini; dovresti vedere un codice a barre DataBar pulito:

* **DatabarAspectRatio15.png** – codice a barre corto e largo adatto a spazi etichetta stretti.  
* **DatabarAspectRatio30.png** – codice a barre più alto che migliora l'affidabilità della scansione su scanner inclinati.

Entrambe le immagini condividono la stessa dimensione dei pixel (2 px per modulo) ma differiscono solo in altezza, dimostrando **come modificare il rapporto d'aspetto** mantenendo costanti gli altri parametri.

## Problemi comuni e come evitarli

| Sintomo | Causa | Correzione |
|---------|-------|------------|
| Il codice a barre appare sfocato | `XDimension.Pixels` impostato troppo basso per la risoluzione di output | Aumenta la dimensione dei pixel ad almeno `2` per la visualizzazione su schermo, `3` per la stampa |
| Lo scanner non riesce a leggere il codice | `EncodeTypes` errato per il formato dei dati | Verifica che i dati GTIN‑14 corrispondano alla simbologia scelta |
| `ArgumentOutOfRangeException` sul rapporto d'aspetto | Valore del rapporto non supportato dalla libreria (intervallo valido: 15‑30) | Usa solo i valori documentati dalla libreria, oppure cattura l'eccezione e ricorri a un valore predefinito |
| File non trovato dopo `Save` | Il percorso relativo punta a una directory inesistente | Usa un percorso assoluto o assicurati che `Directory.CreateDirectory` sia chiamato prima |

```csharp
// Ensure the output folder exists
string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputDir);
barcode.Save(Path.Combine(outputDir, "DatabarAspectRatio15.png"), BarCodeImageFormat.Png);
```

## Prossimi passi – estendere il flusso di lavoro del codice a barre

Ora che puoi **creare un'immagine di codice a barre**, potresti voler:

* **Incorporare il PNG in un PDF** usando una libreria come `PdfSharp` o `iTextSharp`.  
* **Generare altre simbologie** (QR, Code128, PDF417) cambiando l'enum `EncodeTypes`.  
* **Applicare trasformazioni di colore** accedendo a `barcode.Parameters.Barcode.Image.Color`.  
* **Servire l'immagine tramite un endpoint ASP.NET Core** per la generazione on‑the‑fly nelle app web.

Ognuno di questi argomenti si basa sugli stessi concetti fondamentali trattati in questo tutorial, come l'uso di **barcode generator c#**, il controllo della dimensione dei pixel e la manipolazione del rapporto d'aspetto.

## Conclusione

Ora sai come **creare un'immagine di codice a barre** in C# con Barcode Generator, come impostare la dimensione dei pixel, come modificare il rapporto d'aspetto e come generare codici a barre DataBar in modo efficiente. L'esempio completo e eseguibile può essere copiato in qualsiasi progetto .NET, adattato ad altre simbologie e ampliato per adattarsi a flussi di lavoro reali.

Sentiti libero di sperimentare con diversi valori di `XDimension`, rapporti d'aspetto e formati di output. Se incontri problemi, ricontrolla la tabella “Problemi comuni” o consulta la documentazione ufficiale della libreria per opzioni di configurazione più approfondite. Buon coding!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come creare un'immagine di codice a barre e regolare il suo rapporto d'aspetto in C#](/barcode/english/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/)
- [Come generare un set di codici a barre con dimensione personalizzata e salvare l'immagine in C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [Come usare un generatore di codici a barre C# per creare codici DataBar](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}