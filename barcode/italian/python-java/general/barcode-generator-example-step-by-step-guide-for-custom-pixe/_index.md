---
category: general
date: 2026-08-12
description: Esempio di generatore di codici a barre che mostra come generare un codice
  a barre con dimensioni di pixel precise. Impara a impostare la larghezza del modulo,
  l'altezza della barra e a creare codici a barre Planet.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to generate barcode
- barcode pixel size
- generate planet barcode
- barcode height setting
language: it
lastmod: 2026-08-12
og_description: L'esempio di generatore di codici a barre dimostra come generare un
  codice a barre con dimensioni pixel esatte. Segui questa guida per controllare la
  larghezza del modulo e l'altezza della barra per i codici Planet e RM4SCC.
og_image_alt: Screenshot of a barcode generator example showing a Planet barcode with
  custom pixel size
og_title: Esempio di generatore di codici a barre – personalizza la dimensione dei
  pixel in C#
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: barcode generator example that shows how to generate barcode with precise
    pixel size. Learn to set module width, bar height and create Planet barcodes.
  headline: barcode generator example – step‑by‑step guide for custom pixel sizes
  type: TechArticle
- description: barcode generator example that shows how to generate barcode with precise
    pixel size. Learn to set module width, bar height and create Planet barcodes.
  name: barcode generator example – step‑by‑step guide for custom pixel sizes
  steps:
  - name: Install the Aspose.BarCode package
    text: 'Open a terminal in your project folder and run:'
  - name: Add the necessary `using` directives
    text: '```csharp using Aspose.BarCode.Generation; using Aspose.BarCode.BarCodeImageFormat;
      ```'
  - name: – generate a Planet barcode with automatically calculated height
    text: '```csharp // Step 1: Generate a Planet barcode with automatically calculated
      height BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet,
      "123456");'
  - name: – generate a Planet barcode with an explicit 100‑pixel height
    text: '```csharp // Step 2: Generate a Planet barcode with an explicit 100‑pixel
      height BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet,
      "123456");'
  - name: – generate an RM4SCC barcode with the same explicit height
    text: '```csharp // Step 3: Generate an RM4SCC barcode with the same explicit
      height BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC,
      "123456");'
  - name: What is **barcode pixel size**?
    text: '*Pixel size* refers to the physical number of screen or printer pixels
      that represent a single module (`XDimension`). A larger pixel size yields a
      bigger barcode, which can be easier for low‑resolution scanners but consumes
      more label real‑estate.'
  - name: How does `BarHeight` affect readability?
    text: The `BarHeight` property controls the vertical length of the bars. Standards
      for most 1‑D barcodes (including Planet and RM4SCC) recommend a minimum height
      of 10 mm when printed at 300 dpi, which translates to roughly 118 pixels. Setting
      a height below that can cause read errors, especially on mobil
  - name: When should you let the library calculate height automatically?
    text: If you’re generating barcodes for on‑screen display only, the automatic
      calculation keeps the aspect ratio consistent and reduces the amount of manual
      tweaking needed. For printed labels that must meet strict ISO specifications,
      you should **explicitly set the bar height**.
  - name: Pro tip on performance
    text: When generating thousands of barcodes in a batch job, reuse a single `BarcodeGenerator`
      instance and only change the `CodeText` and size parameters between saves. This
      avoids repeated allocation of internal rendering objects and can cut execution
      time by up to 30 %.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Esempio di generatore di codici a barre – guida passo passo per dimensioni
  pixel personalizzate
url: /it/python-java/general/barcode-generator-example-step-by-step-guide-for-custom-pixe/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# esempio di generatore di codici a barre – guida passo‑passo per dimensioni pixel personalizzate

Se ti serve un **esempio di generatore di codici a barre** che ti consenta di controllare ogni pixel, questa guida mostra esattamente come farlo. Imparerai a impostare la larghezza del modulo, definire un’altezza fissa delle barre e generare sia codici Planet che RM4SCC con dimensioni prevedibili.

La maggior parte degli sviluppatori ha difficoltà a creare immagini di “come generare codice a barre” che appaiano identiche su ogni schermo o stampante. Gli snippet di codice qui sotto risolvono il problema esponendo i parametri a livello di pixel della libreria Aspose.BarCode per .NET, così potrai produrre output coerenti senza indovinare.

## Cosa imparerai

* Come installare il pacchetto NuGet richiesto.  
* Come generare un codice Planet con altezza calcolata automaticamente.  
* Come generare un codice Planet con un’altezza esplicita di 100 pixel.  
* Come generare un codice RM4SCC usando la stessa altezza esplicita.  
* Perché la **dimensione pixel del codice a barre** è importante per l’affidabilità della scansione.  
* Suggerimenti per risolvere i problemi più comuni quando generi immagini di codici Planet.

Hai bisogno solo di .NET 6 o versioni successive, di un ambiente di sviluppo C# di base e di una connessione internet per scaricare il pacchetto NuGet.

---

## esempio di generatore di codici a barre – configurazione dell’ambiente di sviluppo

Prima di scrivere qualsiasi codice, assicurati che la libreria Aspose.BarCode sia disponibile nel tuo progetto.

### Installa il pacchetto Aspose.BarCode

Apri un terminale nella cartella del progetto ed esegui:

```bash
dotnet add package Aspose.BarCode
```

Il comando aggiunge l’ultima versione stabile di **Aspose.BarCode** al tuo `csproj`. Dopo il completamento del restore, potrai iniziare a usare la classe `BarcodeGenerator`.

> **Consiglio professionale:** Targetizza .NET 6 o .NET 7 per beneficiare delle ultime ottimizzazioni di performance e della gestione predefinita UTF‑8.

### Aggiungi le direttive `using` necessarie

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;
```

Questi namespace espongono la classe `BarcodeGenerator` e l’enum `BarCodeImageFormat` usati più avanti nella guida.

---

## Come generare un codice a barre con dimensione pixel personalizzata

I tre passaggi seguenti illustrano l’intero **esempio di generatore di codici a barre**. Ogni passo si basa sul precedente, così puoi copiare‑incollare l’intero blocco in un’app console e farlo girare così com’è.

### Passo 1 – genera un codice Planet con altezza calcolata automaticamente

```csharp
// Step 1: Generate a Planet barcode with automatically calculated height
BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set module width (x‑dimension) to 4 pixels
planetAuto.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG
planetAuto.Save("PlanetAuto.png", BarCodeImageFormat.Png);
```

**Perché funziona:**  
*La proprietà `XDimension` definisce la larghezza di un singolo modulo del codice a barre (l’elemento più piccolo, nero o bianco). Quando ometti `BarHeight`, la libreria calcola un’altezza che mantiene il rapporto d’aspetto standard per i codici Planet.*

**Output previsto:** Un file PNG chiamato `PlanetAuto.png` contenente un codice Planet pulito. La sua altezza si adatta alla larghezza del modulo di 4 pixel, tipicamente intorno ai 60 pixel per un payload di sei caratteri.

### Passo 2 – genera un codice Planet con un’altezza esplicita di 100 pixel

```csharp
// Step 2: Generate a Planet barcode with an explicit 100‑pixel height
BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same module width
planetFixed.Parameters.Barcode.XDimension.Pixels = 4;

// Force the bar height to 100 pixels
planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the image
planetFixed.Save("PlanetHeight100.png", BarCodeImageFormat.Png);
```

**Perché potresti averne bisogno:**  
Talvolta l’attrezzatura di scansione richiede un’altezza minima delle barre per una rilevazione affidabile. Impostando `BarHeight.Pixels`, garantisci che ogni immagine generata soddisfi tale requisito, indipendentemente dalla lunghezza dei dati codificati.

**Output previsto:** `PlanetHeight100.png` mostra gli stessi dati di prima, ma le barre sono esattamente alte 100 pixel, dandoti pieno controllo sulla dimensione visiva.

### Passo 3 – genera un codice RM4SCC con la stessa altezza esplicita

```csharp
// Step 3: Generate an RM4SCC barcode with the same explicit height
BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Use the same module width for consistency
rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;

// Apply the 100‑pixel bar height
rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the image
rm4sccFixed.Save("RM4SCCHeight100.png", BarCodeImageFormat.Png);
```

**Perché è importante:**  
`EncodeTypes.RM4SCC` è un codice a barre lineare impilato usato nella logistica. Allineare la sua altezza delle barre a quella del codice Planet semplifica l’elaborazione batch quando entrambe le simbologie compaiono sulla stessa etichetta.

**Output previsto:** `RM4SCCHeight100.png` visualizza un codice RM4SCC perfettamente dimensionato, corrispondente all’altezza di 100 pixel impostata per il codice Planet.

> **Verifica del risultato:** Apri ciascun PNG in un visualizzatore di immagini e conferma che le barre nere siano esattamente larghe 4 pixel e, dove specificato, alte 100 pixel. Puoi anche inviare i file a un’app scanner di codici a barre per assicurarti che decodifichino “123456”.

---

## Comprendere la dimensione pixel del codice a barre e l’altezza delle barre

### Che cos’è la **dimensione pixel del codice a barre**?

*Dimensione pixel* indica il numero fisico di pixel dello schermo o della stampante che rappresentano un singolo modulo (`XDimension`). Una dimensione pixel più grande produce un codice più grande, più facile da leggere per scanner a bassa risoluzione, ma occupa più spazio sull’etichetta.

### Come influisce `BarHeight` sulla leggibilità?

La proprietà `BarHeight` controlla la lunghezza verticale delle barre. Gli standard per la maggior parte dei codici 1‑D (inclusi Planet e RM4SCC) raccomandano un’altezza minima di 10 mm quando stampati a 300 dpi, equivalenti a circa 118 pixel. Impostare un’altezza inferiore può provocare errori di lettura, soprattutto con le fotocamere dei dispositivi mobili.

### Quando lasciare che la libreria calcoli l’altezza automaticamente?

Se generi codici a barre solo per la visualizzazione su schermo, il calcolo automatico mantiene il rapporto d’aspetto coerente e riduce la necessità di aggiustamenti manuali. Per etichette stampate che devono rispettare specifiche ISO rigorose, dovresti **impostare esplicitamente l’altezza delle barre**.

---

## Ostacoli comuni e migliori pratiche nella generazione di codici Planet

| Ostacolo | Perché accade | Soluzione |
|----------|----------------|-----------|
| Le barre appaiono troppo sottili o spesse | `XDimension` lasciato al valore predefinito (1 pixel) su display ad alta risoluzione | Imposta `XDimension.Pixels` ad almeno 3‑4 per una migliore chiarezza visiva |
| Lo scanner non riesce a leggere il codice | `BarHeight` è troppo piccolo per la lunghezza focale dello scanner | Usa `BarHeight.Pixels` ≥ 100 per la maggior parte degli scanner mobili |
| L’immagine risulta sfocata dopo il ridimensionamento | Salvataggio in JPEG introduce artefatti di compressione | Salva in PNG (`BarCodeImageFormat.Png`) per output senza perdita |
| Tipo di codice a barre inatteso | Valore enum `EncodeTypes` errato | Ricontrolla di stare usando `EncodeTypes.Planet` per la simbologia Planet |

### Consiglio professionale sulle performance

Quando generi migliaia di codici a barre in un processo batch, riutilizza una singola istanza di `BarcodeGenerator` e modifica solo `CodeText` e i parametri di dimensione tra un salvataggio e l’altro. Questo evita l’allocazione ripetuta di oggetti di rendering interni e può ridurre il tempo di esecuzione fino al 30 %.

---

## Esempio completo – metti tutto insieme

Crea un nuovo progetto console (`dotnet new console -n BarcodeDemo`) e sostituisci il contenuto di `Program.cs` con il seguente:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Directory where PNG files will be saved
            string outputDir = Environment.CurrentDirectory;

            // ---------- Planet barcode – automatic height ----------
            var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
            planetAuto.Save($"{outputDir}/PlanetAuto.png", BarCodeImageFormat.Png);
            Console.WriteLine("PlanetAuto.png generated.");

            // ---------- Planet barcode – fixed 100‑pixel height ----------
            var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
            planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            planetFixed.Save($"{outputDir}/PlanetHeight100.png", BarCodeImageFormat.Png);
            Console.WriteLine("PlanetHeight100.png generated.");

            // ---------- RM4SCC barcode – same fixed height ----------
            var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            rm4sccFixed.Save($"{outputDir}/RM4SCCHeight100.png", BarCodeImageFormat.Png);
            Console.WriteLine("RM4SCCHeight100.png generated.");

            Console.WriteLine("All barcodes created successfully.");
        }
    }
}
```

Esegui il programma con `dotnet run`. Al termine troverai tre file PNG nella cartella del progetto, ognuno dei quali illustra uno scenario diverso del **esempio di generatore di codici a barre**.

---

## Passi successivi e argomenti correlati

* **Come generare codici a barre in altri formati** – esplora `EncodeTypes.Code128`, `EncodeTypes.QR` e `EncodeTypes.DataMatrix` per esigenze 2‑D.  
* **Incorporare codici a barre nei PDF** – combina Aspose.BarCode con Aspose.PDF per inserire i codici direttamente nei modelli di fattura.  
* **Dimensione dinamica del codice a barre basata sull’input dell’utente** – calcola  

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi con spiegazioni passo‑passo per aiutarti a padroneggiare ulteriori funzionalità dell’API e a esplorare approcci alternativi nei tuoi progetti.

- [How to generate barcode java: Create an Exact Barcode Image](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)
- [How to Generate Barcode in Java Create and Set Size for Whole Picture](/barcode/english/java/barcode-basics/creating-setting-size-whole-picture-barcode/)
- [How to create code128 barcode Java and set bar height](/barcode/english/java/barcode-configuration/setting-bars-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}