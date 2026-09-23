---
category: general
date: 2026-09-23
description: Come ridimensionare il codice a barre in C# usando Aspose.BarCode. Impara
  a generare il codice a barre in C#, personalizzare le dimensioni e esportare l'immagine
  del codice a barre in modo efficiente.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to resize barcode
- generate barcode c#
- barcode generator example
- create databar barcode
- export barcode image
language: it
lastmod: 2026-09-23
og_description: Come ridimensionare il codice a barre in C# con Aspose.BarCode. Segui
  questa guida per generare il codice C# del codice a barre, regolare le dimensioni
  e esportare l'immagine del codice a barre.
og_image_alt: Screenshot showing resized DataBar Omni‑directional barcode generated
  in C#
og_title: Come ridimensionare il codice a barre in C# – tutorial completo di Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: How to resize barcode in C# using Aspose.BarCode. Learn to generate
    barcode C# code, customize size, and export barcode image efficiently.
  headline: How to resize barcode in C# with Aspose.BarCode – step‑by‑step guide
  type: TechArticle
- description: How to resize barcode in C# using Aspose.BarCode. Learn to generate
    barcode C# code, customize size, and export barcode image efficiently.
  name: How to resize barcode in C# with Aspose.BarCode – step‑by‑step guide
  steps:
  - name: '**Create Databar barcode** objects with custom data.'
    text: '**Create Databar barcode** objects with custom data.'
  - name: Adjust `BarHeight` (the core of resizing).
    text: Adjust `BarHeight` (the core of resizing).
  - name: Export PNG files for any required size.
    text: Export PNG files for any required size.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- image processing
title: Come ridimensionare il codice a barre in C# con Aspose.BarCode – guida passo
  passo
url: /it/python-java/general/how-to-resize-barcode-in-c-with-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come ridimensionare un codice a barre in C# con Aspose.BarCode – guida passo‑passo

Se hai bisogno di **come ridimensionare un codice a barre** in un'applicazione .NET, questo tutorial mostra il codice esatto che puoi copiare‑incollare ed eseguire subito. Imparerai a **generare codice C# per barcode**, a regolare l'altezza delle barre e a **esportare immagini di barcode** senza uscire dal tuo IDE.

Creare codici a barre è comune nei sistemi di inventario, nelle etichette di spedizione e nei terminali point‑of‑sale. Alla fine di questa guida sarai in grado di **creare immagini Databar barcode** a qualsiasi altezza tu richieda, e comprenderai le proprietà chiave che controllano dimensione, risoluzione e formato file.

## Prerequisiti

- .NET 6 o successivo (l'esempio funziona anche con .NET Framework 4.6+)  
- Pacchetto NuGet Aspose.BarCode per .NET (`Install-Package Aspose.BarCode`)  
- Familiarità di base con la sintassi C# e Visual Studio (o qualsiasi IDE C#)

Non sono necessarie librerie aggiuntive; Aspose.BarCode gestisce internamente il rendering, il ridimensionamento e l'esportazione delle immagini.

## Passo 1: Configurare il progetto e importare Aspose.BarCode

Crea un nuovo progetto console (o integralo in uno esistente) e aggiungi lo spazio dei nomi Aspose.BarCode:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;   // required for BarCodeImageFormat
```

> **Suggerimento:** Usa l'ultima versione di Aspose.BarCode (a partire da settembre 2026) per beneficiare di correzioni di bug e nuove simbologie di barcode.

## Passo 2: Inizializzare un generatore di barcode DataBar Omni‑directional

L'**esempio di generatore di barcode** inizia specificando la simbologia (`EncodeTypes.DatabarOmniDirectional`) e il payload dei dati. Il payload segue il formato GS1 Application Identifier `(01)12345678901231`.

```csharp
// Step 2: Create a DataBar Omni‑directional barcode generator with the desired data
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Questo oggetto contiene tutti i parametri che modificherai in seguito, come X‑dimension, altezza della barra e formato immagine.

## Passo 3: Definire i parametri di dimensione comuni

Prima di esportare, imposta la X‑dimension (la larghezza della barra più stretta) e un'altezza iniziale della barra. La X‑dimension è espressa in pixel; un valore di `2` funziona bene per la maggior parte delle risoluzioni dello schermo.

```csharp
// Step 3: Set common barcode parameters – X‑dimension and initial bar height (30 px)
barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
barcode.Parameters.Barcode.BarHeight.Pixels = 30; // initial height
```

> **Perché è importante:** La proprietà `BarHeight` influenza direttamente la dimensione visiva del barcode. Modificarla è il fulcro di **come ridimensionare un barcode** in Aspose.BarCode.

## Passo 4: Esportare la prima immagine del barcode (altezza 30 px)

Ora puoi **esportare l'immagine del barcode** in un file PNG. Il metodo `Save` rende automaticamente il barcode con i parametri correnti.

```csharp
// Step 4: Save the barcode image with a 30‑pixel height
barcode.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Il file risultante appare così:

![How to resize barcode example](https://example.com/images/databar-30px.png){: .align-center alt="Esempio di come ridimensionare un barcode – altezza 30 pixel"}

## Passo 5: Modificare l'altezza della barra per creare un barcode più grande

Per dimostrare **come ridimensionare un barcode** in modo dinamico, regola la proprietà `BarHeight` e salva nuovamente. Questo **non** richiede la creazione di una nuova istanza `BarcodeGenerator`; basta modificare l'oggetto esistente.

```csharp
// Step 5: Change the bar height to 60 pixels for a larger barcode
barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

## Passo 6: Esportare l'immagine del barcode ridimensionata (altezza 60 px)

```csharp
// Step 6: Save the barcode image with the new 60‑pixel height
barcode.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Ora hai due file PNG—uno a 30 px e uno a 60 px—che mostrano come gli stessi dati possano essere renderizzati a dimensioni diverse.

### Output previsto

| File name                     | Bar height (px) | Visual result |
|-------------------------------|----------------|---------------|
| `DatabarBarHeight30Pixels.png`| 30             | ![30 px barcode](https://example.com/images/databar-30px.png){: alt="barcode DataBar Omni‑directional da 30 pixel"} |
| `DatabarBarHeight60Pixels.png`| 60             | ![60 px barcode](https://example.com/images/databar-60px.png){: alt="barcode DataBar Omni‑directional da 60 pixel"} |

Entrambe le immagini sono barcode GS1‑128 DataBar validi, pronti per la scansione.

## Passo 7: Opzionale – Regolare impostazioni visive aggiuntive

Mentre l'obiettivo principale è **come ridimensionare un barcode**, potresti anche voler modificare:

| Property | Description | Typical values |
|----------|-------------|----------------|
| `XDimension.Pixels` | Larghezza della barra più stretta | 1–4 |
| `BarHeight.Pixels`  | Altezza dell'intero barcode | 20–200 |
| `Resolution` | DPI per l'output raster | 72, 150, 300 |
| `ForeColor` / `BackColor` | Colori di primo piano e di sfondo | `Color.Black`, `Color.White` |

Esempio:

```csharp
barcode.Parameters.Barcode.XDimension.Pixels = 3;
barcode.Parameters.Barcode.ForeColor = Color.DarkBlue;
barcode.Parameters.Barcode.BackColor = Color.White;
barcode.Parameters.ImageResolution.DpiX = 300;
barcode.Parameters.ImageResolution.DpiY = 300;
```

Queste modifiche non influenzano la logica di **ridimensionamento**, ma ti danno il pieno controllo sulla qualità finale dell'immagine.

## Problemi comuni e come evitarli

| Problema | Sintomo | Soluzione |
|----------|----------|----------|
| Altezza della barra non cambia | Le immagini salvate sono identiche | Assicurati di modificare `barcode.Parameters.Barcode.BarHeight.Pixels` *prima* di ogni chiamata a `Save`. |
| Il barcode diventa illeggibile | Lo scanner segnala “cannot read” | Mantieni `XDimension` ≥ 2 px per DataBar Omni‑directional; barre molto sottili possono impedire la lettura. |
| Il file PNG è sfocato | Esportato a DPI basso | Imposta `barcode.Parameters.ImageResolution.DpiX/Y` ad almeno 150 per immagini di qualità di stampa. |
| File sovrascritto involontariamente | La nuova immagine sostituisce quella vecchia | Usa nomi file unici o includi il valore dell'altezza nel nome del file, come mostrato sopra. |

## Esempio completo, eseguibile

Copia l'intero blocco qui sotto in una nuova app console (`Program.cs`). Il codice si compila ed esegue così com'è, producendo i due file PNG nella cartella di output del progetto.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar Omni‑directional barcode generator
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set common parameters
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first height

        // 3️⃣ Export first image (30 px height)
        barcode.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode.");

        // 4️⃣ Change height to 60 px
        barcode.Parameters.Barcode.BarHeight.Pixels = 60;

        // 5️⃣ Export second image (60 px height)
        barcode.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode.");

        // Optional: tweak additional settings (uncomment if needed)
        // barcode.Parameters.Barcode.ForeColor = System.Drawing.Color.DarkBlue;
        // barcode.Parameters.ImageResolution.DpiX = 300;
        // barcode.Parameters.ImageResolution.DpiY = 300;
    }
}
```

L'esecuzione del programma produce:

```
Saved 30‑pixel barcode.
Saved 60‑pixel barcode.
```

Controlla la cartella di output per i due file PNG. Entrambi sono pronti per la stampa, l'inserimento in PDF o l'invio a un dispositivo remoto.

## Conclusione

In questa guida abbiamo trattato **come ridimensionare un barcode** in C# usando Aspose.BarCode, mostrato un **esempio completo di generatore di barcode**, e illustrato come **esportare immagini di barcode** a diverse altezze. Ora sai come:

1. **Creare oggetti Databar barcode** con dati personalizzati.  
2. Regolare `BarHeight` (il fulcro del ridimensionamento).  
3. Esportare file PNG per qualsiasi dimensione richiesta.

Da qui puoi esplorare ulteriori personalizzazioni—diverse simbologie, schemi di colore o formati vettoriali come SVG. Lo stesso schema (`barcode.Parameters.Barcode.BarHeight.Pixels = <value>`) funziona per qualsiasi tipo di barcode supportato da Aspose.BarCode, così potrai applicare con sicurezza la conoscenza di **come ridimensionare un barcode** in tutta la tua applicazione.

---

**Passi successivi**

- Prova a ridimensionare altre simbologie (QR, Code128) per vedere come interagiscono altezza e larghezza.  
- Usa `BarCodeImageFormat.Svg` per generare grafica vettoriale scalabile per pagine web.  
- Integra le immagini generate nei report PDF con Aspose.PDF o iTextSharp.  

Buon coding e goditi la flessibilità che deriva dalla generazione programmatica di barcode!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come generare e regolare l'altezza del barcode One-Dimensional Databar usando Aspose.BarCode per .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Come generare un barcode – Configurazione Code 39 con Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Come generare codici DataMatrix usando Aspose.BarCode per .NET – Guida passo‑passo](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}