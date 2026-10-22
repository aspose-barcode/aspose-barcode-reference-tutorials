---
category: general
date: 2026-10-21
description: Scopri come generare immagini di codici a barre in C# e come esportare
  i file di codici a barre in PNG usando Aspose.BarCode per risultati rapidi e affidabili.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to export barcode
language: it
lastmod: 2026-10-21
og_description: Come generare immagini di codici a barre in C# e come esportare i
  file di codici a barre in PNG. Segui questo tutorial completo per creare codici
  a barre Planet e RM4SCC con Aspose.BarCode.
og_image_alt: Screenshot showing how to generate barcode images with C# code
og_title: Come generare immagini di codici a barre ed esportarle in C# – guida passo
  passo
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Learn how to generate barcode images in C# and how to export barcode
    files as PNG using Aspose.BarCode for fast, reliable results.
  headline: How to generate barcode images and export them in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Come generare immagini di codici a barre ed esportarle in C#
url: /it/python-java/general/how-to-generate-barcode-images-and-export-them-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come generare immagini di codici a barre ed esportarle in C#

Se hai bisogno di **come generare codici a barre** immagini in un'applicazione .NET, questa guida ti mostra i passaggi esatti per creare codici a barre Planet e RM4SCC e poi **come esportare i codici a barre** come file PNG. Otterrai un esempio di codice pronto all'uso, una descrizione di ogni impostazione e consigli per le difficoltà comuni.

Il tutorial copre:

* Aggiunta del pacchetto NuGet Aspose.BarCode
* Configurazione della larghezza del modulo e dell'altezza opzionale della barra
* Salvataggio dei codici a barre generati su disco
* Verifica dei file di output

> **Prerequisito** – .NET 6+ SDK, Visual Studio 2022 (o qualsiasi IDE), e una connessione internet per scaricare il pacchetto Aspose.BarCode.

## Cosa otterrai

Alla fine di questo articolo sarai in grado di:

* Generare un codice a barre **Planet** con altezza della barra automatica.
* Generare un codice a barre **RM4SCC** con altezza della barra automatica.
* Sovrascrivere l'altezza predefinita e produrre un codice a barre alto 100 pixel.
* Esportare ogni codice a barre in un file PNG in una cartella a tua scelta.

## Passo 1: Installa Aspose.BarCode

Apri un terminale nella cartella del tuo progetto ed esegui:

```bash
dotnet add package Aspose.BarCode
```

Il pacchetto fornisce la classe `BarcodeGenerator` e l'enumerazione `EncodeTypes` utilizzate nel codice che segue.

## Passo 2: Configura la cartella di output

Crea una cartella dove verranno salvati i file PNG. La cartella può essere assoluta o relativa alla radice del progetto.

```csharp
// Define the folder where barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
```

> **Suggerimento:** L'uso di `Path.Combine` evita separatori di percorso hard‑coded e funziona su Windows, macOS e Linux.

## Passo 3: Genera codici a barre con altezza automatica

Quando non specifichi un'altezza della barra, Aspose.BarCode sceglie una dimensione che si adatta ai dati codificati. Il codice seguente crea due codici a barre — Planet e RM4SCC — usando una larghezza del modulo di 4 pixel.

```csharp
using Aspose.BarCode.Generation;

// Planet barcode, automatic height
var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // Set module width
planetAuto.Save(Path.Combine(outputFolder, "PlanetAutoHeight.png"),
                BarCodeImageFormat.Png);

// RM4SCC barcode, automatic height
var rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4; // Set module width
rm4sccAuto.Save(Path.Combine(outputFolder, "RM4SCCAutoHeight.png"),
                BarCodeImageFormat.Png);
```

**Perché funziona:**  
* `EncodeTypes.Planet` e `EncodeTypes.RM4SCC` indicano al generatore quale simbologia utilizzare.  
* `XDimension.Pixels` definisce la larghezza di un singolo modulo del codice a barre; un valore di 4 px produce un'immagine chiara e leggibile.  
* Poiché `BarHeight` non è impostato, la libreria calcola automaticamente l'altezza ottimale.

## Passo 4: Genera codici a barre con altezza fissa di 100 pixel

Se il tuo design richiede un'altezza specifica del codice a barre, puoi sovrascrivere il calcolo automatico:

```csharp
// Planet barcode, fixed 100‑pixel height
var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetFixed.Parameters.Barcode.XDimension.Pixels = 4;      // Module width
planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;   // Fixed height
planetFixed.Save(Path.Combine(outputFolder, "PlanetHeight100.png"),
                 BarCodeImageFormat.Png);

// RM4SCC barcode, fixed 100‑pixel height
var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;      // Module width
rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;   // Fixed height
rm4sccFixed.Save(Path.Combine(outputFolder, "RM4SCCHeight100.png"),
                 BarCodeImageFormat.Png);
```

**Perché potresti aver bisogno di un'altezza fissa:**  
Le specifiche di progettazione per le etichette di spedizione spesso richiedono dimensioni precise delle barre per garantire la compatibilità con gli scanner di codici a barre. Impostare `BarHeight.Pixels` garantisce uniformità in tutte le immagini generate.

## Passo 5: Verifica i file esportati

Dopo l'esecuzione del programma, la cartella `Barcodes` contiene quattro file PNG:

* `PlanetAutoHeight.png`
* `RM4SCCAutoHeight.png`
* `PlanetHeight100.png`
* `RM4SCCHeight100.png`

Apri uno di essi con un visualizzatore di immagini o incorporalo in un PDF per confermare che venga visualizzato correttamente. Se uno scanner non riesce a leggere il codice a barre, aumenta il valore di `XDimension.Pixels` o ricontrolla la lunghezza della stringa di input.

```bash
# Example verification command (Linux/macOS)
file Barcodes/*.png
```

Dovresti vedere un output simile a:

```
Barcodes/PlanetAutoHeight.png: PNG image data, 180 x 100, 8-bit/color RGBA, non-interlaced
```

## Domande comuni e casi particolari

| Domanda | Risposta |
|----------|--------|
| **Posso esportare in formati diversi da PNG?** | Sì. Sostituisci `BarCodeImageFormat.Png` con `Jpeg`, `Bmp`, `Gif` o `Tiff`. |
| **Cosa succede se i miei dati contengono caratteri non consentiti dalla simbologia?** | Il generatore lancia `ArgumentException`. Convalida l'input o passa a una simbologia che supporta il set di caratteri. |
| **Come posso cambiare i colori di primo piano/sfondo?** | Imposta `Parameters.Barcode.ForeColor` e `Parameters.Barcode.BackColor` prima di chiamare `Save`. |
| **Esiste un modo per generare i codici a barre in memoria invece di salvarli su disco?** | Chiama `GenerateBarCodeImage()` per ottenere un oggetto `System.Drawing.Image`, quindi manipolalo o trasmettilo secondo necessità. |

## Consiglio professionale: elaborazione batch

Quando devi creare molti codici a barre (ad esempio per una lista di indirizzi), avvolgi la logica di generazione in un ciclo `foreach`:

```csharp
var values = new[] { "001122", "334455", "667788" };
int index = 0;

foreach (var value in values)
{
    var generator = new BarcodeGenerator(EncodeTypes.Planet, value);
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Save(Path.Combine(outputFolder, $"Planet_{index++}.png"),
                   BarCodeImageFormat.Png);
}
```

Questo schema scala a migliaia di codici a barre mantenendo il codice conciso.

## Conclusione

Ora sai **come generare immagini di codici a barre** in C# e **come esportare i codici a barre** come PNG usando Aspose.BarCode. L'esempio completo mostra sia la generazione automatica che quella a altezza fissa per le simbologie Planet e RM4SCC, fornendoti una solida base per qualsiasi progetto relativo ai codici a barre.

**Passi successivi**

* Esplora altre simbologie come Code128, QR o DataMatrix.  
* Sperimenta la personalizzazione dei colori (`ForeColor`, `BackColor`).  
* Integra i PNG generati in fatture PDF o etichette di spedizione usando una libreria PDF.  

Buon coding, e lascia che i tuoi codici a barre vengano letti senza problemi!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come generare codici DataMatrix usando Aspose.BarCode per .NET – Guida passo‑passo](/barcode/english/net/datamatrix-barcode-configuration/)
- [Crea immagini di codici GS1 in C# – Come generare rapidamente codici a barre in C#](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [come generare un'immagine di codice a barre con Aspose.BarCode in C#](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}