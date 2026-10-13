---
category: general
date: 2026-09-29
description: Crea un codice a barre planetario in C# con barre sia piene che vuote
  – guida passo‑passo con Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode XDimension
- filled bars
- empty bars
- Aspose.Barcode C#
language: it
lastmod: 2026-09-29
og_description: Crea rapidamente un codice a barre Planet in C#. Scopri come rendere
  le barre piene, passare alle barre vuote e regolare la dimensione X con Aspose.Barcode.
og_image_alt: 'Screenshot of two Planet barcodes: one with filled bars, one with empty
  bars'
og_title: Crea un codice a barre planet con barre piene e vuote – tutorial C#
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  headline: How to create planet barcode with filled and empty bars
  type: TechArticle
- description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  name: How to create planet barcode with filled and empty bars
  steps:
  - name: Changing the bar width
    text: If your label printer expects a different bar width, modify the `XDimension.Pixels`
      value. For high‑resolution printers, a value of **2** or **3** pixels may be
      preferable; for low‑resolution printers, **5** or **6** pixels can improve scan
      reliability.
  - name: Using a different image format
    text: Aspose.Barcode supports PNG, JPEG, BMP, GIF, and TIFF. Swap `BarCodeImageFormat.Png`
      with another enum value to match your downstream workflow.
  - name: Generating multiple barcodes in a loop
    text: When you need a batch of Planet barcodes (e.g., for a mailing list), wrap
      the generator logic in a `foreach` loop and change the data string each iteration.
  - name: Handling invalid input
    text: The Planet symbology accepts only numeric strings of **5‑8** digits. Supplying
      an invalid value throws an `ArgumentException`. Guard against this with a simple
      validation method.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Come creare un codice a barre planetario con barre piene e vuote
url: /it/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un planet barcode con barre piene e vuote

Se hai bisogno di **creare planet barcode** immagini in C#, questa guida ti mostra esattamente come generare sia versioni con barre piene che con barre vuote. Vedrai come impostare la larghezza della barra (X‑dimension), attivare/disattivare la proprietà `FilledBars` e salvare i risultati come file PNG—tutto con la libreria Aspose.Barcode.

Generare codici a barre postali è una necessità comune per i sistemi di spedizione, le applicazioni di mailing‑list e i cruscotti logistici. Alla fine di questo tutorial avrai due file PNG pronti all'uso che potrai incorporare in report, email o stampe.

## Prerequisiti

| Requisito | Perché è importante |
|-----------|----------------------|
| .NET 6.0 o versioni successive | Fornisce l'ambiente di runtime per l'esempio C#. |
| Visual Studio 2022 (o qualsiasi IDE C#) | Consente di compilare ed eseguire il codice. |
| **Aspose.Barcode for .NET** pacchetto NuGet | Fornisce la classe `BarcodeGenerator` e `EncodeTypes.Planet`. Installalo con `dotnet add package Aspose.Barcode`. |
| Permesso di scrittura su una cartella del disco | Il metodo `Save` scrive i file PNG nel percorso specificato. |

## Passo 1: Configurare il progetto e importare i namespace

Crea un nuovo progetto console (o aggiungi il codice a uno esistente) e fai riferimento al namespace Aspose.Barcode.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;
```

Queste direttive `using` ti danno accesso a `BarcodeGenerator`, `EncodeTypes` e agli enum dei formati immagine necessari per il tutorial.

## Passo 2: Creare un codice a barre Planet con barre predefinite (piene)

Il primo codice a barre utilizza il rendering predefinito della libreria, che riempie le barre.

```csharp
// Initialise a generator for the Planet (postal) barcode with sample data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Optional: adjust the bar width (X dimension) to 4 pixels for clearer printing.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image with filled bars.
string filledPath = @"C:\Barcodes\PlanetFilledBars.png";
barcodeGenerator.Save(filledPath, BarCodeImageFormat.Png);

Console.WriteLine($"Filled Planet barcode saved to: {filledPath}");
```

**Perché funziona:**  
`EncodeTypes.Planet` indica ad Aspose.Barcode di utilizzare la simbologia **Planet**, che è un codice a barre postale usato dal United States Postal Service. La proprietà `XDimension` controlla la larghezza di ogni barra; impostandola a 4 pixel si ottiene un codice a barre che stampa bene su stampanti di etichette standard. Per impostazione predefinita, `FilledBars` è `true`, quindi le barre appaiono solide.

## Passo 3: Creare un codice a barre Planet con barre vuote

Per generare gli stessi dati con barre *vuote*, devi solo invertire il flag `FilledBars` mantenendo gli altri parametri identici.

```csharp
// Re‑use the same variable for clarity.
barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for visual consistency.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Render empty bars instead of filled ones.
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the image with empty bars.
string emptyPath = @"C:\Barcodes\PlanetEmptyBars.png";
barcodeGenerator.Save(emptyPath, BarCodeImageFormat.Png);

Console.WriteLine($"Empty Planet barcode saved to: {emptyPath}");
```

**Perché è importante:**  
Alcuni sistemi di mailing richiedono lo stile **empty‑bars** per migliorare la leggibilità quando il codice a barre è stampato su sfondi scuri o quando si utilizza uno schema di colori a contrasto. Impostando `FilledBars = false`, il generatore disegna solo i contorni delle barre, lasciando l'interno trasparente.

## Output previsto

Dopo aver eseguito il programma, la cartella `C:\Barcodes` (o il percorso che hai scelto) contiene due file PNG:

| File | Descrizione visiva |
|------|---------------------|
| `PlanetFilledBars.png` | Le barre sono rettangoli neri solidi su sfondo bianco. |
| `PlanetEmptyBars.png`  | Le barre sono contorni neri; l'interno di ogni barra è trasparente (mostra lo sfondo). |

Entrambe le immagini codificano la stessa stringa numerica `"123456"` e condividono una larghezza di barra di 4 pixel, garantendo un aspetto coerente tranne lo stile di riempimento.

## Varianti comuni e casi limite

### Modificare la larghezza della barra

Se la tua stampante di etichette richiede una larghezza della barra diversa, modifica il valore `XDimension.Pixels`. Per stampanti ad alta risoluzione, un valore di **2** o **3** pixel può essere preferibile; per stampanti a bassa risoluzione, **5** o **6** pixel possono migliorare l'affidabilità della scansione.

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 5; // example for coarse printers
```

### Utilizzare un formato immagine diverso

Aspose.Barcode supporta PNG, JPEG, BMP, GIF e TIFF. Sostituisci `BarCodeImageFormat.Png` con un altro valore enum per adattarlo al tuo flusso di lavoro.

```csharp
barcodeGenerator.Save("Planet.tiff", BarCodeImageFormat.Tiff);
```

### Generare più codici a barre in un ciclo

Quando ti serve un batch di codici a barre Planet (ad esempio per una mailing list), avvolgi la logica del generatore in un ciclo `foreach` e modifica la stringa dei dati ad ogni iterazione.

```csharp
string[] postalCodes = { "123456", "654321", "112233" };
int index = 1;
foreach (var code in postalCodes)
{
    var gen = new BarcodeGenerator(EncodeTypes.Planet, code);
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    gen.Save($@"C:\Barcodes\Planet_{index}_filled.png", BarCodeImageFormat.Png);
    gen.Parameters.Barcode.FilledBars = false;
    gen.Save($@"C:\Barcodes\Planet_{index}_empty.png", BarCodeImageFormat.Png);
    index++;
}
```

### Gestire input non validi

La simbologia Planet accetta solo stringhe numeriche di **5‑8** cifre. Fornire un valore non valido genera un `ArgumentException`. Proteggi il codice con un semplice metodo di validazione.

```csharp
bool IsValidPlanet(string value) => System.Text.RegularExpressions.Regex.IsMatch(value, @"^\d{5,8}$");

string data = "ABC123";
if (!IsValidPlanet(data))
{
    Console.WriteLine("Invalid Planet data – must be 5 to 8 digits.");
    return;
}
```

## Suggerimento professionale: Verificare il codice a barre con un emulatore di scanner

Aspose.Barcode include una classe `BarcodeReader` che puoi usare per confermare che l'immagine generata decodifichi nuovamente i dati originali.

```csharp
using Aspose.Barcode.Reader;

// Verify filled barcode
using (BarCodeReader reader = new BarCodeReader(filledPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from filled image: {reader.GetCodeText()}");
}

// Verify empty barcode
using (BarCodeReader reader = new BarCodeReader(emptyPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from empty image: {reader.GetCodeText()}");
}
```

Se l'output mostra `"123456"` per entrambi i file, il codice a barre è stato generato correttamente.

## Conclusione

Ora sai come **creare planet barcode** immagini in C# con entrambi gli stili di barra (piene e vuote), controllare la **Planet barcode XDimension** e salvare i risultati in formato PNG usando la libreria **Aspose.Barcode**. Regola la larghezza della barra, cambia i formati immagine o esegui un ciclo su una collezione di valori per adattarlo a qualsiasi flusso di lavoro di codici postali.

Successivamente, potresti esplorare:

* **Aggiungere testo leggibile dall'uomo** sotto il codice a barre (`barcodeGenerator.Parameters.Caption.Show = true`).
* **Incorporare codici a barre in documenti PDF** con Aspose.PDF.
* **Generare altre simbologie postali** come **USPS POSTNET** o **Intelligent Mail**.

Sentiti libero di sperimentare con i parametri e integrare il codice nel tuo sistema di spedizione o mailing. Buon coding!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Crea Planet Barcode in C# – Guida completa passo‑passo](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Crea planet barcode in C# – guida di programmazione completa](/barcode/english/python-java/general/create-planet-barcode-in-c-complete-programming-guide/)
- [Generatore di barcode C# – esempio di creazione Planet barcode e RM4SCC](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}