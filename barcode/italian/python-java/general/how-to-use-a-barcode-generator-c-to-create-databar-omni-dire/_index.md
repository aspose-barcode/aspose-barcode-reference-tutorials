---
category: general
date: 2026-08-22
description: Il tutorial del generatore di codici a barre C# mostra come generare
  file PNG di codici a barre, creare codici DataBar e regolare l'altezza del codice
  a barre in pochi passaggi.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- how to generate barcode
- generate barcode PNG
- create DataBar barcode
- adjust barcode height
language: it
lastmod: 2026-08-22
og_description: La guida al generatore di codici a barre C# ti mostra come generare
  PNG di codici a barre, creare codici DataBar e regolare l’altezza del codice a barre
  in modo efficiente.
og_image_alt: Screenshot of two DataBar Omni‑directional barcodes with different heights
  saved as PNG files
og_title: generatore di codici a barre C# – crea codici DataBar e regola l'altezza
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to generate barcode PNG files,
    create DataBar barcodes, and adjust barcode height in just a few steps.
  headline: How to use a barcode generator C# to create DataBar Omni‑directional barcodes
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Come utilizzare un generatore di codici a barre C# per creare codici a barre
  DataBar omnidirezionali
url: /it/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come utilizzare un generatore di barcode C# per creare codici a barre DataBar Omni‑directional

Se ti serve un **barcode generator C#** in grado di produrre immagini PNG di alta qualità, questa guida è quello che fa per te. Imparerai a generare file PNG di barcode, a creare un barcode DataBar Omni‑directional e a regolare l’altezza del barcode senza lasciare l’IDE.

Generare i barcode programmaticamente elimina il passaggio manuale di utilizzare un editor grafico. Alla fine di questo tutorial avrai due file PNG — uno con un’altezza delle barre di 30 pixel e l’altro con un’altezza di 60 pixel — pronti per essere inseriti in fatture, etichette o sistemi di inventario.

**Prerequisiti**

- .NET 6.0 o successivo (il codice funziona anche con .NET Framework 4.7+)
- Un riferimento al pacchetto NuGet `Aspose.BarCode` (o a qualsiasi libreria che esponga un’API simile)
- Familiarità di base con C# e Visual Studio o l’IDE di tua scelta

---

## Passo 1: Configurare il progetto barcode generator C#

Creare un’istanza di **barcode generator C#** è il primo passo. Il costruttore accetta due argomenti: il tipo di barcode (`EncodeTypes.DatabarOmniDirectional`) e il payload dei dati. In questo esempio il payload segue il formato GS1 Application Identifier per un GTIN a 14 cifre.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the barcode generator for a DataBar Omni‑directional code
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

**Perché è importante:** L’enumerazione `EncodeTypes.DatabarOmniDirectional` indica alla libreria di renderizzare un DataBar leggibile da qualsiasi direzione, ideale per piccole etichette al dettaglio.

---

## Passo 2: Definire la dimensione del modulo (X‑dimension)

La X‑dimension controlla la larghezza di un singolo modulo del barcode. Impostarla a 2 pixel fornisce un’immagine nitida e leggibile mantenendo ridotto il peso del file.

```csharp
        // Set the module (X) dimension to 2 pixels per module
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Suggerimento:** Se hai spazio limitato, puoi ridurre il valore a 1 pixel, ma verifica comunque la leggibilità con uno scanner.

---

## Passo 3: Generare il primo PNG con altezza barra di 30 pixel

L’altezza della barra determina quanto sono alte le barre. Un’altezza di 30 pixel è il valore predefinito più comune per le etichette standard.

```csharp
        // Set bar height to 30 pixels
        generator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image as PNG
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png",
                       BarCodeImageFormat.Png);
```

Il file `DatabarBarHeight30Pixels.png` ora contiene un **generate barcode PNG** che può essere usato direttamente nelle pagine web o stampato su richiesta.

---

## Passo 4: Regolare l’altezza del barcode a 60 pixel e salvare un secondo PNG

Cambiare l’altezza della barra è semplice: basta assegnare un nuovo valore alla stessa proprietà. Questo dimostra la capacità di **adjust barcode height** del generatore.

```csharp
        // Change bar height to 60 pixels for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png",
                       BarCodeImageFormat.Png);
    }
}
```

Ora hai `DatabarBarHeight60Pixels.png`, ideale per confezioni più grandi dove il barcode deve essere letto da una certa distanza.

**Output previsto**

- `DatabarBarHeight30Pixels.png` – un compatto barcode DataBar Omni‑directional, alto 30 px.
- `DatabarBarHeight60Pixels.png` – lo stesso barcode, raddoppiato in altezza per una migliore visibilità.

Entrambe le immagini sono file PNG, che mantengono la qualità lossless e supportano la trasparenza se necessario.

---

## Come generare file barcode PNG in formati diversi

Sebbene questo tutorial si concentri su PNG, il metodo `Save` accetta altri formati come `Jpeg`, `Bmp` e `Svg`. Per **how to generate barcode** in un altro formato, sostituisci semplicemente `BarCodeImageFormat.Png` con il valore enum desiderato:

```csharp
generator.Save(@"path\barcode.svg", BarCodeImageFormat.Svg);
```

Scegliere SVG è comodo quando ti serve un’immagine vettoriale che si scala senza pixelazione.

---

## Problemi comuni quando **create DataBar barcode** immagini

| Problema | Causa | Soluzione |
|----------|-------|-----------|
| Il barcode appare sfocato | X‑dimension troppo bassa per la risoluzione target | Aumenta `XDimension.Pixels` a 3 o 4 |
| Lo scanner non legge il codice | Altezza della barra troppo corta per l’ottica dello scanner | Usa un minimo di 30 pixel o segui le specifiche dello scanner |
| Stringa di dati rifiutata | Formattazione GS1 errata | Assicurati che la stringa inizi con il corretto Application Identifier, ad es. `(01)` per GTIN‑14 |

Affrontare questi punti fin da subito fa risparmiare tempo quando si integrano i barcode nei flussi di produzione.

---

## Suggerimento avanzato: Riutilizzare lo stesso generatore per più barcode

Se devi **generate barcode PNG** per un batch di prodotti, riutilizza la stessa istanza di `BarcodeGenerator` e aggiorna solo la proprietà `CodeText`:

```csharp
string[] gtins = { "(01)12345678901231", "(01)98765432109876" };
int[] heights = { 30, 60 };

foreach (var gtin in gtins)
{
    generator.CodeText = gtin;          // Change data payload
    foreach (var h in heights)
    {
        generator.Parameters.Barcode.BarHeight.Pixels = h;
        string fileName = $"Databar_{gtin.Substring(4)}_{h}Px.png";
        generator.Save($@"YOUR_DIRECTORY\{fileName}", BarCodeImageFormat.Png);
    }
}
```

Questo schema riduce il sovraccarico di creazione degli oggetti e mantiene il codice conciso.

---

## Conclusione

Ora disponi di un flusso di lavoro completo per **barcode generator C#** che **creates DataBar barcodes**, **generates barcode PNG** e ti permette di **adjust barcode height** con una singola modifica di proprietà. L’esempio copre tutto, dalla configurazione del progetto alla gestione dei casi limite, così potrai integrare la creazione di barcode in qualsiasi applicazione .NET con sicurezza.

**Passi successivi**

- Esplora altre simbologie di barcode (`EncodeTypes.QR`, `EncodeTypes.Code128`) per ampliare la tua soluzione.
- Combina il generatore con ASP.NET Core per servire barcode on‑the‑fly tramite un endpoint API.
- Sperimenta le opzioni di colore (`generator.Parameters.Barcode.ForeColor`) per scopi di branding.

Buona programmazione e che le tue scansioni siano sempre rapide!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi con spiegazioni passo‑passo per aiutarti a padroneggiare ulteriori funzionalità dell’API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generate One-Dimensional Databar 2D Barcodes Using Aspose.BarCode .NET API](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}