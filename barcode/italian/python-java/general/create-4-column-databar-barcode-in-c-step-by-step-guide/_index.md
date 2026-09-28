---
category: general
date: 2026-08-09
description: Crea rapidamente un codice a barre databar a 4 colonne in C# con Aspose.BarCode.
  Scopri come configurare colonne, righe e salvare immagini PNG in questa guida concisa.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create 4‑column databar barcode
- databar expanded stacked
- barcode generator c#
- set barcode rows
- barcode image format
language: it
lastmod: 2026-08-09
og_description: Crea un codice a barre databar a 4 colonne in C# usando Aspose.BarCode,
  poi personalizza le righe ed esporta le immagini PNG per la tua app.
og_image_alt: Screenshot of a 4‑column DataBar Expanded Stacked barcode generated
  in C#
og_title: Crea un codice a barre Databar a 4 colonne in C# – tutorial rapido
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create 4‑column databar barcode in C# quickly with Aspose.BarCode.
    Learn how to configure columns, rows, and save PNG images in this concise guide.
  headline: Create 4‑column databar barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Create 4‑column databar barcode in C# quickly with Aspose.BarCode.
    Learn how to configure columns, rows, and save PNG images in this concise guide.
  name: Create 4‑column databar barcode in C# – step‑by‑step guide
  steps:
  - name: Configure DataBar Expanded Stacked columns
    text: If you need a different column count, simply change the integer assigned
      to `Columns`. The property accepts values from 1 to 4 for the expanded stacked
      variant.
  - name: Save the barcode image
    text: The `BarCodeImageFormat` enumeration provides several options (`Png`, `Jpeg`,
      `Bmp`, `Gif`, `Tiff`). PNG is loss‑less and works well for most web and desktop
      scenarios.
  - name: Set barcode rows dynamically
    text: 'You can compute the row count at runtime based on input data:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- DataBar
title: Crea un codice a barre Databar a 4 colonne in C# – guida passo passo
url: /it/python-java/general/create-4-column-databar-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea codice a barre databar a 4 colonne in C# – guida passo‑passo

Se hai bisogno di **creare un codice a barre databar a 4 colonne** in C#, questo tutorial ti mostra esattamente come fare. Ti guideremo nella generazione di un codice a barre DataBar Expanded Stacked, nella configurazione di quattro colonne e nel salvataggio del risultato come immagine PNG.

Nel presente tutorial imparerai a:

* Inizializzare il `BarcodeGenerator` per un simbolo **DataBar Expanded Stacked**.  
* Impostare il conteggio delle colonne a 4 (requisito principale).  
* Regolare il conteggio delle righe quando è necessario un layout impilato con tre righe.  
* Esportare il codice a barre come PNG utilizzando il **barcode image format** appropriato.

Hai bisogno solo della libreria Aspose.BarCode per .NET (versione 23.10 o successiva) e di un ambiente di sviluppo .NET 6+ come Visual Studio 2022. Non sono richieste dipendenze aggiuntive.

---

## Come creare un codice a barre databar a 4 colonne

Il primo passo è creare un'istanza di `BarcodeGenerator` che punti alla simbologia **DataBar Expanded Stacked**. Questa classe incapsula tutte le opzioni di rendering, rendendo semplice passare da layout basati su colonne a layout basati su righe.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise a generator for DataBar Expanded Stacked
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");
        
        // 2️⃣ Set the barcode to use a 4‑column layout
        generator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image as PNG
        generator.Save("DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**Perché funziona:**  
`EncodeTypes.DatabarExpandedStacked` indica ad Aspose.BarCode di produrre la versione impilata della famiglia DataBar. La proprietà `DataBar.Columns` controlla quante unità verticali occupa il codice a barre. Impostandola a 4 soddisfa il requisito di **creare un codice a barre databar a 4 colonne**. Infine, `Save` scrive la rappresentazione visiva su disco usando il **barcode image format** `Png`.

### Configura le colonne di DataBar Expanded Stacked

Se hai bisogno di un conteggio di colonne diverso, modifica semplicemente l'intero assegnato a `Columns`. La proprietà accetta valori da 1 a 4 per la variante expanded stacked.

```csharp
// Example: switch to a 2‑column layout
generator.Parameters.Barcode.DataBar.Columns = 2;
```

*Consiglio professionale:* Testa sempre il codice a barre generato con uno scanner che supporta la famiglia DataBar, poiché l'aspetto visivo da solo non garantisce la leggibilità.

### Salva l'immagine del codice a barre

L'enumerazione `BarCodeImageFormat` fornisce diverse opzioni (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`). PNG è loss‑less e funziona bene nella maggior parte degli scenari web e desktop.

```csharp
generator.Save("DatabarCols4.png", BarCodeImageFormat.Png);
```

Se ti serve un formato diverso, sostituisci `Png` con il valore enum desiderato. Il file salvato può essere incorporato direttamente in HTML, PDF o stampato su etichette.

## Crea un codice a barre con righe personalizzate

A volte è necessario un layout impilato con un numero specifico di righe anziché colonne. La stessa classe `BarcodeGenerator` espone una proprietà `Rows` a questo scopo.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class RowExample
{
    static void Main()
    {
        // 1️⃣ Initialise a generator for the same symbology
        BarcodeGenerator rowGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the barcode to use a 3‑row layout
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 3️⃣ Save the image as PNG
        rowGenerator.Save("DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**Perché le righe sono importanti:**  
Quando il codice a barre impilato è più alto che largo, la proprietà `Rows` determina in quante sezioni orizzontali è suddiviso il simbolo. Impostare `Rows = 3` crea un codice a barre impilato a tre righe, utile per larghezze di etichetta strette.

### Imposta dinamicamente le righe del codice a barre

Puoi calcolare il numero di righe a runtime in base ai dati di input:

```csharp
int desiredRows = GetRowsFromUser(); // your custom logic
rowGenerator.Parameters.Barcode.DataBar.Rows = desiredRows;
```

Questa flessibilità ti consente di **impostare le righe del codice a barre** senza ricompilare l'applicazione.

## Esempio completo end‑to‑end

Di seguito trovi un unico programma che genera sia un codice a barre a 4 colonne sia un codice a barre a 3 righe, dimostrando come le due configurazioni coesistano.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class FullExample
{
    static void Main()
    {
        // ---------- 4‑column barcode ----------
        BarcodeGenerator colGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");
        colGen.Parameters.Barcode.DataBar.Columns = 4; // create 4‑column databar barcode
        colGen.Save("DatabarCols4.png", BarCodeImageFormat.Png);

        // ---------- 3‑row barcode ----------
        BarcodeGenerator rowGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");
        rowGen.Parameters.Barcode.DataBar.Rows = 3; // set barcode rows to 3
        rowGen.Save("DatabarRows3.png", BarCodeImageFormat.Png);

        // Output confirmation
        System.Console.WriteLine("Barcodes generated:");
        System.Console.WriteLine(" - DatabarCols4.png (4 columns)");
        System.Console.WriteLine(" - DatabarRows3.png (3 rows)");
    }
}
```

**Output previsto:**  
Due file PNG appaiono nella directory di lavoro dell'applicazione:

* `DatabarCols4.png` – un codice a barre DataBar Expanded Stacked con quattro colonne verticali.  
* `DatabarRows3.png` – la stessa simbologia disposta in tre righe orizzontali.

Entrambe le immagini possono essere aperte con qualsiasi visualizzatore di immagini o incorporate in un controllo UI.

---

## Domande comuni e casi particolari

| Domanda | Risposta |
|----------|--------|
| *Posso utilizzare una simbologia di codice a barre diversa?* | Sì. Sostituisci `EncodeTypes.DatabarExpandedStacked` con un altro valore `EncodeTypes` (ad esempio `EncodeTypes.QR`), ma le proprietà `Columns` e `Rows` sono specifiche delle famiglie DataBar. |
| *Cosa succede se la stringa di dati supera la lunghezza massima?* | La simbologia DataBar Expanded Stacked supporta fino a 61 caratteri numerici. Superare questo limite genera un `ArgumentException`. Convalida l'input prima di assegnarlo al generatore. |
| *Devo rilasciare (`dispose`) il `BarcodeGenerator`?* | `BarcodeGenerator` implementa `IDisposable`. In un servizio a lungo termine, avvolgilo in un blocco `using` o chiama manualmente `Dispose()` per liberare le risorse native. |
| *Posso generare SVG invece di PNG?* | Assolutamente. Usa `BarCodeImageFormat.Svg` nel metodo `Save`. |
| *La libreria è compatibile con .NET Core?* | Aspose.BarCode per .NET supporta .NET Core 3.1, .NET 5, .NET 6 e versioni successive. Non sono necessarie modifiche al codice. |

## Conclusione

Ora sai come **creare un codice a barre databar a 4 colonne** in C# usando Aspose.BarCode, come regolare il layout con le righe e come esportare il risultato in un comodo **barcode image format**. L'esempio completo mostra sia le configurazioni basate su colonne sia quelle basate su righe, fornendoti una solida base per qualsiasi scenario di stampa di etichette o di scansione mobile.

**Prossimi passi**

* Sperimenta con diversi payload di dati e verifica la compatibilità dello scanner.  
* Esplora ulteriori opzioni di stile come i colori di primo piano/sfondo (`generator.Parameters.Barcode.Color`).  
* Combina il codice a barre con altre grafiche usando l'API `Graphics` per progetti di etichette personalizzate.  

Sentiti libero di adattare il codice per progetti ASP.NET Core, Windows Forms o Xamarin—Aspose.BarCode funziona su tutte le piattaforme .NET. Buon coding!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Crea immagine di codice a barre DotCode – righe e colonne (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Crea immagine di codice a barre c# – Configura righe e colonne di Codablock F](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Come creare dotcode con testo codificato esteso con Aspose.BarCode per .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}