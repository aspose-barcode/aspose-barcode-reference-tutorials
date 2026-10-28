---
category: general
date: 2026-10-28
description: Crea un'immagine di codice a barre in C# e impara come regolare l'altezza
  utilizzando l'API BarcodeGenerator. Guida passo‑passo per personalizzare l'altezza
  del codice a barre e modificare l'altezza delle barre.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust height
- c# barcode generator
- custom barcode height
- change barcode height
language: it
lastmod: 2026-10-28
og_description: Crea un'immagine di codice a barre in C# e scopri subito come regolare
  l'altezza. Segui questo esempio completo per impostare un'altezza personalizzata
  del codice a barre con BarcodeGenerator.
og_image_alt: Screenshot showing a generated barcode image with a custom height
og_title: Crea immagine di codice a barre con altezza personalizzata in C# – guida
  completa
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode image in C# and learn how to adjust height using the
    BarcodeGenerator API. Step‑by‑step guide for custom barcode height and changing
    bar height.
  headline: Create barcode image with custom height in C#
  type: TechArticle
tags:
- barcode
- C#
- image generation
- GS1‑Databar
title: Crea immagine di codice a barre con altezza personalizzata in C#
url: /it/python-java/general/create-barcode-image-with-custom-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea immagine barcode con altezza personalizzata in C#

Se hai bisogno di **creare un'immagine barcode** e controllare le sue dimensioni, questa guida ti mostra esattamente come fare. Utilizzando la libreria Aspose.BarCode .NET puoi generare un barcode GS1‑Databar Omni‑Directional, quindi **come regolare l'altezza** per soddisfare qualsiasi requisito di layout.

Seguirai un programma completo e eseguibile che dimostra un **generatore di barcode c#**, spiega ogni proprietà impostata e mostra due output diversi — uno con un'altezza delle barre di 30 pixel e un altro con un'altezza delle barre di 60 pixel. Alla fine sarai in grado di **modificare l'altezza del barcode** programmaticamente per qualsiasi tipo di barcode supportato dalla libreria.

## Prerequisiti

- .NET 6.0 SDK o versioni successive (il codice funziona anche con .NET Framework 4.6+)
- Visual Studio 2022 o qualsiasi editor in grado di compilare progetti C#
- Pacchetto NuGet Aspose.BarCode per .NET (`Install-Package Aspose.BarCode`)
- Familiarità di base con la sintassi C#

> **Consiglio professionale:** Se stai usando una pipeline CI, aggiungi il pacchetto NuGet al tuo file `csproj` in modo che la build lo ripristini automaticamente.

## Passo 1: Configura il progetto e importa i namespace

Crea un nuovo progetto console e aggiungi le dichiarazioni `using` richieste. I namespace ti danno accesso a `BarcodeGenerator`, `EncodeTypes` e ai helper per i formati immagine.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // The rest of the tutorial code lives here.
        }
    }
}
```

> **Perché è importante:** Importare i namespace corretti previene errori di compilazione e rende l'API scopri­bile in IntelliSense.

## Passo 2: Inizializza il **generatore di barcode c#** per un codice GS1‑Databar Omni‑Directional

Il costruttore accetta due argomenti: il tipo di barcode (`EncodeTypes.DatabarOmniDirectional`) e la stringa di dati. La stringa di dati deve seguire il formato GS1 Application Identifier, ad esempio `(01)12345678901231`.

```csharp
// Create a barcode generator for a GS1‑Databar Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional,
    "(01)12345678901231");
```

> **Spiegazione:** L'oggetto `BarcodeGenerator` è il punto di ingresso per tutte le impostazioni relative al barcode. Una volta ottenuta questa istanza, puoi modificare dimensioni, colori e formato di output.

## Passo 3: Definisci una X‑dimensione comune (larghezza in pixel della barra più stretta)

Una X‑dimensione di 2 pixel è un buon punto di partenza per la maggior parte degli scenari di visualizzazione su schermo.

```csharp
// Set a 2‑pixel X‑dimension (width of the smallest bar)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Perché impostare la X‑dimensione?** Controlla la larghezza complessiva del barcode. Mantenerla costante garantisce che la modifica dell'altezza delle barre non distorca l'equilibrio visivo.

## Passo 4: **Crea immagine barcode** con un'altezza delle barre di 30 pixel

Ora configuriamo l'altezza delle barre, salviamo la prima immagine, quindi cambiamo l'altezza per la seconda.

```csharp
// Configure a 30‑pixel bar height
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

// Save the first image
string output30 = "DatabarBarHeight30Pixels.png";
barcodeGenerator.Save(output30, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 30 px height to {output30}");
```

> **Risultato:** Ottieni un file PNG in cui ogni barra verticale è alta 30 pixel. La X‑dimensione rimane a 2 pixel, quindi la larghezza complessiva non cambia.

## Passo 5: **Come regolare l'altezza** – cambia l'altezza delle barre a 60 pixel

Per dimostrare **un'altezza barcode personalizzata**, assegna semplicemente un nuovo valore alla stessa proprietà e salva nuovamente.

```csharp
// Change the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second image
string output60 = "DatabarBarHeight60Pixels.png";
barcodeGenerator.Save(output60, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 60 px height to {output60}");
```

> **Osservazione chiave:** La proprietà `BarHeight` è modificabile; non è necessario ricreare l'istanza `BarcodeGenerator`. Questo rende poco costoso generare più dimensioni in un ciclo o in un processo batch.

## Passo 6: Verifica l'output

Esegui il programma console (`dotnet run`). Dopo l'esecuzione dovresti vedere due file PNG nella cartella di output del progetto:

- `DatabarBarHeight30Pixels.png` – barre corte (30 px)
- `DatabarBarHeight60Pixels.png` – barre alte (60 px)

Entrambe le immagini contengono gli stessi dati codificati, ma l'altezza visiva differisce, il che è utile quando si integrano barcode in moduli, etichette prodotto o componenti UI con vincoli di spazio variabili.

![Crea immagine barcode con altezza personalizzata](barcode-example.png){.align-center width="600" alt="Crea immagine barcode con altezza personalizzata"}

> **Suggerimento:** Apri i file PNG in qualsiasi visualizzatore di immagini. Il barcode più alto dovrebbe essere esattamente il doppio dell'altezza verticale di quello più corto, mentre la spaziatura orizzontale rimane identica.

## Passo 7: Variazioni comuni e casi limite

| Situazione | Impostazione consigliata |
|------------|--------------------------|
| **Stampa su una stampante di etichette ad alta risoluzione** | Usa una X‑dimensione più grande (ad es., 4 px) e aumenta `BarHeight` proporzionalmente. |
| **Visualizzazione su schermo a bassa risoluzione (low‑dpi)** | Mantieni `XDimension` a 1 px e `BarHeight` tra 20‑40 px per leggibilità. |
| **Generazione di QR code o barcode 2‑D** | La proprietà `BarHeight` è ignorata; usa `EncodeTypes.QR` e regola `ImageHeight` invece. |
| **Generazione batch di molte altezze** | Itera su un array di altezze e chiama `Save` all'interno del ciclo; non è necessario ricreare il generatore ad ogni iterazione. |

### Gestione altezze non valide

La libreria genera un'`ArgumentOutOfRangeException` se imposti `BarHeight` a un valore non positivo. Proteggi il codice con un semplice controllo:

```csharp
int desiredHeight = 0; // example invalid value
if (desiredHeight <= 0)
{
    throw new ArgumentException("Bar height must be greater than zero.");
}
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = desiredHeight;
```

## Codice sorgente completo (pronto da copiare)

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the barcode generator for GS1‑Databar Omni‑Directional
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set a common 2‑pixel X‑dimension
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = "DatabarBarHeight30Pixels.png";
            barcodeGenerator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 30 px height to {path30}");

            // 4️⃣ Second image – 60 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = "DatabarBarHeight60Pixels.png";
            barcodeGenerator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 60 px height to {path60}");
        }
    }
}
```

> **Perché funziona:** Tutte le impostazioni richieste (`EncodeTypes`, `XDimension`, `BarHeight`) sono applicate prima di ogni chiamata a `Save`. La stessa istanza `BarcodeGenerator` viene riutilizzata, il che è sia efficiente in termini di memoria sia facile da leggere.

## Conclusione

Ora sai come **creare file immagine barcode** in C# e modificare con precisione **l'altezza del barcode** utilizzando l'API `BarcodeGenerator`. Regolando `BarHeight.Pixels` ottieni un'**altezza barcode personalizzata** senza ricostruire il generatore, rendendo la soluzione ideale per la creazione dinamica di etichette, il rendering UI o pipeline di elaborazione batch.

Successivamente, esplora argomenti correlati come **come regolare la larghezza**, **aggiungere testo leggibile dall'uomo**, o **esportare in SVG per uso web scalabile**. Lo stesso schema — impostare una proprietà, chiamare `Save` — si applica a questi scenari, permettendoti di estendere questo esempio con sicurezza.

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come cambiare l'altezza del barcode in C# – Guida completa](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Esempio di generatore di barcode – crea barcode Planet e RM4SCC con altezza personalizzata](/barcode/english/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/)
- [Come creare barcode rm4scc e controllarne l'altezza in C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-control-its-height-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}