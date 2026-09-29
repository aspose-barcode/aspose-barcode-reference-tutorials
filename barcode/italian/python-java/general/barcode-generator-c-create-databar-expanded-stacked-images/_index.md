---
category: general
date: 2026-07-24
description: Tutorial C# per generatore di codici a barre che mostra come generare
  un'immagine di codice a barre, impostare le colonne, impostare le righe e creare
  un codice a barre Databar in poche righe di codice.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- generate barcode image
- how to set columns
- how to set rows
- create databar barcode
language: it
lastmod: 2026-07-24
og_description: Il tutorial Barcode Generator C# ti guida nella generazione di un'immagine
  di codice a barre, nella configurazione di colonne e righe e nella creazione di
  un codice a barre Databar con esempi di codice chiari.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: Generatore di Codici a Barre C# – Crea rapidamente codici a barre DataBar
  impilati
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Barcode Generator C# tutorial that shows how to generate barcode image,
    set columns, set rows, and create Databar barcode in just a few lines of code.
  headline: Barcode Generator C# – Create DataBar Expanded Stacked Images
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Generatore di Codici a Barre C# – Crea Immagini DataBar Expanded Stacked
url: /it/python-java/general/barcode-generator-c-create-databar-expanded-stacked-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generatore di Codici a Barre C# – Guida Completa a DataBar Expanded Stacked

Ti sei mai chiesto come usare **barcode generator c#** per produrre immagini nitide e leggibili in pochi secondi? Forse hai fissato un progetto vuoto, incerto su dove vadano le colonne o le righe, o su come effettivamente *generate barcode image* file senza mal di testa. Bene, sei nel posto giusto. In questo tutorial configureremo una piccola app console, creeremo un codice a barre DataBar Expanded Stacked, ne regoleremo il layout e salveremo il risultato come PNG—tutto con la libreria **barcode generator c#**.

Copriremo tutto quello che devi sapere: installare il pacchetto, configurare colonne e righe (sì, risponderemo a *how to set columns* e *how to set rows*), e infine come **create databar barcode** oggetti che puoi inserire in fatture, ticket o qualsiasi cosa richieda un'etichetta leggibile da una macchina. Nessuna documentazione esterna necessaria; basta copiare‑incollare, eseguire, e vedrai due file PNG apparire nella tua cartella.

## Cosa Ti Serve

- .NET 6.0 SDK o successivo (il codice funziona su .NET Core, .NET Framework e .NET 5+)
- Un nuovo progetto console (`dotnet new console`) – puoi anche usare Visual Studio se preferisci un'interfaccia grafica.
- Il pacchetto NuGet Aspose.BarCode for .NET (la libreria che alimenta **barcode generator c#**). Installalo con:

```bash
dotnet add package Aspose.BarCode
```

È tutto. Una volta ripristinato il pacchetto sei pronto per partire.

## Generatore di Codici a Barre C# – Configurazione del Progetto

Per prima cosa, importiamo gli spazi dei nomi necessari e creiamo un metodo helper che manterrà ordinata la nostra routine principale.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Folder where PNG files will be saved
        string outputFolder = Environment.CurrentDirectory;

        // Build the first barcode with custom columns
        GenerateDatabarWithColumns(outputFolder, columns: 4);

        // Build the second barcode with custom rows
        GenerateDatabarWithRows(outputFolder, rows: 3);
    }

    // -----------------------------------------------------------------
    // Helper: creates a DataBar Expanded Stacked barcode and sets columns
    // -----------------------------------------------------------------
    static void GenerateDatabarWithColumns(string folder, int columns)
    {
        // Step 1: Create a DataBar Expanded Stacked barcode generator with the desired text
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // Step 2: Configure the barcode to use the supplied number of columns
        // This answers the “how to set columns” question.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = columns;

        // Step 3: Save the barcode image as PNG – this is the “generate barcode image” part.
        string filePath = System.IO.Path.Combine(folder, $"DatabarCols{columns}.png");
        barcodeGenerator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ Created barcode with {columns} columns: {filePath}");
    }

    // -----------------------------------------------------------------
    // Helper: creates a DataBar Expanded Stacked barcode and sets rows
    // -----------------------------------------------------------------
    static void GenerateDatabarWithRows(string folder, int rows)
    {
        // Step 4: Create another generator for the same barcode type and text
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // Step 5: Configure the barcode to use the supplied number of rows
        // This answers the “how to set rows” query.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = rows;

        // Step 6: Save the second barcode image as PNG
        string filePath = System.IO.Path.Combine(folder, $"DatabarRows{rows}.png");
        barcodeGenerator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ Created barcode with {rows} rows: {filePath}");
    }
}
```

### Perché Questa Struttura Funziona

- **Separation of concerns** – ogni helper si concentra su una singola configurazione (colonne vs. righe). Questo rende il codice più facile da leggere e riutilizzare.
- **Explicit parameters** – passiamo `columns` o `rows` come argomenti, così puoi chiamare lo stesso metodo con qualsiasi valore senza modificare il corpo.
- **Immediate feedback** – `Console.WriteLine` ti indica esattamente dove è stato salvato il file, utile quando esegui il programma da un terminale.

## Come Impostare le Colonne per DataBar Expanded Stacked

La proprietà `DataBar.Columns` è il parametro che determina quante sezioni verticali conterrà il codice a barre. Il valore predefinito è `4`, ma potresti aver bisogno di `2` o `6` a seconda della quantità di dati che codifichi o dei requisiti dello scanner. Ecco un breve snippet che isola la logica di impostazione delle colonne:

```csharp
var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Sample Text");
generator.Parameters.Barcode.DataBar.Columns = 5;   // ← change this number as needed
generator.Save("databar_columns5.png", BarCodeImageFormat.Png);
```

**Consiglio professionale:** Quando aumenti le colonne, la larghezza complessiva del codice a barre cresce proporzionalmente. Se prevedi di incorporare l'immagine in un PDF o in una pagina web, assicurati che il contenitore possa ospitare la larghezza aggiuntiva, altrimenti lo scanner potrebbe leggerla in modo errato.

## Come Impostare le Righe per DataBar Expanded Stacked

Le righe funzionano allo stesso modo, ma influenzano l'altezza del codice a barre. Il conteggio predefinito delle righe è `3`. Se la tua etichetta ha spazio verticale limitato, potresti ridurlo a `2`. Al contrario, più righe possono migliorare la leggibilità su stampanti a bassa risoluzione.

```csharp
var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Sample Text");
generator.Parameters.Barcode.DataBar.Rows = 2;   // ← adjust rows here
generator.Save("databar_rows2.png", BarCodeImageFormat.Png);
```

**Attenzione:** Impostare le righe a un valore inferiore al minimo richiesto per i dati codificati causerà un'eccezione a runtime. La libreria lancia `ArgumentException` con un messaggio chiaro, così saprai immediatamente se la configurazione è invalida.

## Genera Immagine Codice a Barre – Salvataggio come PNG

Entrambi gli helper sopra terminano con una chiamata a `Save`. L'enumerazione `BarCodeImageFormat.Png` indica ad Aspose.BarCode di generare un file PNG senza perdita, ideale per la maggior parte degli scenari di scansione perché preserva i bordi nitidi. Se preferisci un formato diverso (JPEG per il web, BMP per sistemi legacy), basta scambiare il valore dell'enum—non sono necessarie altre modifiche al codice.

```csharp
generator.Save("mybarcode.jpeg", BarCodeImageFormat.Jpeg);
```

I PNG generati appaiono così (immagina l'immagine; il testo alternativo sotto lo descrive):

> **Testo alternativo per le immagini generate:** *Codice a barre DataBar Expanded Stacked con 4 colonne (sinistra) e 3 righe (destra), renderizzato in nero ad alto contrasto su sfondo trasparente.*

## Crea Codice a Barre DataBar – Esempio Completo Funzionante

Mettendo tutto insieme, ecco una versione compatta che puoi inserire direttamente in `Program.cs`. Dimostra sia la configurazione di colonne che di righe, più un rapido controllo di integrità per verificare che i file esistano dopo il salvataggio.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Demo
{
    static void Main()
    {
        string outDir = Directory.GetCurrentDirectory();

        // ---------- Create barcode with custom columns ----------
        var colGen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked,
                                          "Databar Expanded Stacked long");
        colGen.Parameters.Barcode.DataBar.Columns = 4;   // how to set columns
        string colPath = Path.Combine(outDir, "DatabarCols4.png");
        colGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column barcode → {colPath}");

        // ---------- Create barcode with custom rows ----------
        var rowGen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked,
                                          "Databar Expanded Stacked long");
        rowGen.Parameters.Barcode.DataBar.Rows = 3;      // how to set rows
        string rowPath = Path.Combine(outDir, "DatabarRows3.png");
        rowGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row barcode → {rowPath}");

        // ---------- Verify files exist ----------
        Console.WriteLine(File.Exists(colPath)
            ? "✅ Column image generated successfully."
            : "❌ Column image missing.");
        Console.WriteLine(File.Exists(rowPath)
            ? "✅ Row image generated successfully."
            : "❌ Row image missing.");
    }
}
```

### Output Atteso

Quando esegui il programma (`dotnet run`), dovresti vedere linee della console simili a:

```
Saved column barcode → C:\MyProject\DatabarCols4.png
Saved row barcode → C:\MyProject\DatabarRows3.png
✅ Column image generated successfully.
✅ Row image generated successfully.
```

Apri i due file PNG in qualsiasi visualizzatore di immagini; noterai che il file di sinistra ha quattro moduli verticali (colonne) mentre quello di destra è alto tre moduli (righe). Entrambi sono perfettamente leggibili con qualsiasi lettore DataBar standard.

## Problemi Comuni & Come Evitarli

| Sintomo | Probabile Causa | Soluzione |
|---------|----------------|----------|
| `ArgumentException: Columns value is out of range` | Colonne impostate a 0 o > 8 (la libreria limita a 8). | Usa valori compresi tra **1** e **8**. |
| Il codice a barre appare sfocato nel PDF | PNG salvato con DPI predefinito (96) e poi scalato. | Usa `generator.Parameters.ImageResolution = 300;` prima del salvataggio. |
| Lo scanner fallisce con configurazione solo righe | Righe modificate ma colonne lasciate al valore predefinito che non corrisponde alla lunghezza dei dati. | Regola sia righe **che** colonne insieme, oppure lascia che la libreria dimensioni automaticamente omettendo le impostazioni manuali. |

## Prossimi Passi

Ora che sai come **generate barcode image**, **set columns**, **set rows**, e **create databar barcode** con **barcode generator c#**, puoi:

- Inserire i PNG nei PDF usando `Aspose.PDF` o `iTextSharp`.
- Passare a `EncodeTypes.DatabarLimited` se ti serve un ingombro più piccolo.
- Sperimentare con i colori (`generator.Parameters.Barcode.ForeColor = Color.Blue`).
- Aggiungere QR code o altre simbologie nello stesso progetto—Aspose.BarCode supporta oltre 150 tipologie.

Se incontri problemi, lascia un commento qui sotto o consulta la documentazione ufficiale di Aspose.BarCode (il riferimento API è esaustivo e include decine di esempi di codice live). Buona programmazione, e che i tuoi scanner non manchino mai un segno!

## Cosa Dovresti Imparare Dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Crea immagine di codice a barre DotCode – righe e colonne (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Crea immagine di codice a barre c# – Configura righe e colonne Codablock F](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Genera immagine di codice a barre – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}