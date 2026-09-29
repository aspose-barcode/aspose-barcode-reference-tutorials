---
category: general
date: 2026-08-06
description: Genera un'immagine di codice a barre in C# usando Aspose.BarCode. Scopri
  come generare Databar, regolare la dimensione personalizzata del codice a barre
  e modificare l'altezza del codice a barre con un codice semplice.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- how to generate databar
- custom barcode size
- create databar barcode
- change barcode height
language: it
lastmod: 2026-08-06
og_description: Genera immagine di codice a barre in C# con Aspose.BarCode. Questo
  tutorial ti mostra come creare un codice a barre Databar Omnidirezionale, personalizzare
  le sue dimensioni e modificare l'altezza del codice a barre in modo efficiente.
og_image_alt: Screenshot of a Databar barcode generated with custom height in C#
og_title: Genera immagine di codice a barre in C# – guida completa ad Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Generate barcode image in C# using Aspose.BarCode. Learn how to generate
    Databar, adjust custom barcode size, and change barcode height with simple code.
  headline: Generate barcode image in C# with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: The evaluation version of Aspose.BarCode works without a license but adds
      a small watermark. For production use, apply a purchased license using `License
      license = new License(); license.SetLicense("Aspose.BarCode.lic");`.
    question: Can I generate a barcode without installing a license?
  - answer: Yes. Very small X‑dimensions can make the barcode unreadable on low‑resolution
      printers. A minimum of 1 px for screen rendering is recommended; for print,
      use at least 0.25 mm.
    question: Does changing the X‑dimension affect readability?
  - answer: 'Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. You
      may also set `generator.Parameters.ImageQuality` to control compression. ##
      Conclusion You now know how to **generate barcode image** in C# using Aspose.BarCode,
      how to **create Databar barcode**, adjust a **custom barcode size**, '
    question: What if I need to generate a barcode in JPEG format?
  type: FAQPage
tags:
- barcode
- C#
- Aspose.BarCode
title: Genera immagine di codice a barre in C# con Aspose.BarCode
url: /it/python-java/general/generate-barcode-image-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generare immagine di codice a barre in C# con Aspose.BarCode

Se hai bisogno di **generare un'immagine di codice a barre** programmaticamente, questa guida ti mostra esattamente come fare. Che tu stia costruendo un sistema di inventario al dettaglio o un portale di tracciamento logistico, vedrai l'intero flusso di lavoro per creare un codice a barre Databar Omnidirectional, regolare le sue dimensioni e salvare il risultato come file PNG.

Generare un'immagine di codice a barre è una necessità comune, ma gli sviluppatori spesso si chiedono **come generare Databar** con le dimensioni esatte di cui hanno bisogno. In questo tutorial imparerai a creare un codice a barre Databar, personalizzarne larghezza e altezza e a modificare l'altezza del codice a barre senza riscrivere l'intero generatore.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* SDK .NET 6.0 o successivo (il codice funziona con .NET Core e .NET Framework)
* Visual Studio 2022 (o qualsiasi IDE che supporti C#)
* Una licenza valida di Aspose.BarCode per .NET (la valutazione gratuita funziona per i test)
* Familiarità di base con la sintassi C#

## Step 1: Install Aspose.BarCode

Aggiungi il pacchetto NuGet Aspose.BarCode al tuo progetto:

```bash
dotnet add package Aspose.BarCode
```

Il pacchetto contiene la classe `BarcodeGenerator` utilizzata in tutto il tutorial. Dopo l'installazione, ripristina il progetto per scaricare le dipendenze.

## Step 2: Create a basic barcode generator

La prima riga di codice crea un **barcode generator** che produrrà un simbolo Databar Omnidirectional. L'enumerazione `EncodeTypes.DatabarOmniDirectional` indica alla libreria quale simbologia utilizzare, e la stringa dei dati segue la sintassi dell'Identificatore di Applicazione GS1.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a Databar Omnidirectional barcode
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231"); // GS1-14 data (example GTIN)
```

**Perché è importante:** L'oggetto `BarcodeGenerator` è il punto di ingresso per ogni operazione di codice a barre. Selezionando `DatabarOmniDirectional` garantisci che l'output sia conforme allo standard GS1 per la scansione al dettaglio.

## Step 3: Set a custom X‑dimension (module width)

La X‑dimension controlla la larghezza della barra più stretta. Impostarla su un valore di pixel piccolo ti fornisce un codice a barre compatto, mentre valori più grandi aumentano la larghezza complessiva.

```csharp
        // Step 3: Define a custom X‑dimension (module width) of 2 px
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Spiegazione:** Una X‑dimension di 2 pixel è una scelta comune per schermi ad alta risoluzione. Regola questo valore se hai bisogno di una densità visiva più stretta o più ampia.

## Step 4: Generate the first barcode image with a specific height

L'altezza del codice a barre è indipendente dalla X‑dimension. Qui impostiamo l'altezza della barra a **30 px**, quindi salviamo l'immagine come PNG.

```csharp
        // Step 4: Set bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**Risultato:** Ora hai un file chiamato `DatabarBarHeight30Pixels.png` che mostra un codice a barre Databar alto 30 px. Questo dimostra la capacità di **dimensionare il codice a barre** per un caso d'uso specifico, come un'etichetta piccola.

## Step 5: Change barcode height for a larger version

Se lo stesso codice a barre deve apparire su un'etichetta più grande, devi solo modificare la proprietà dell'altezza e riutilizzare la stessa istanza del generatore.

```csharp
        // Step 5: Increase the bar height to 60 px for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
    }
}
```

**Perché puoi riutilizzare il generatore:** Cambiare `BarHeight.Pixels` aggiorna il layout interno senza ricreare l'oggetto, risparmiando memoria e mantenendo intatta la stringa dei dati. Questo è il modo consigliato per **modificare l'altezza del codice a barre** al volo.

## Step 6: Verify the output

Apri i due file PNG in qualsiasi visualizzatore di immagini. Dovresti vedere due codici a barre Databar Omnidirectional che codificano lo stesso GTIN ma differiscono per dimensione verticale:

* `DatabarBarHeight30Pixels.png` – 30 px di altezza, adatto per ricevute compatte.
* `DatabarBarHeight60Pixels.png` – 60 px di altezza, ideale per etichette di scaffale più grandi.

Entrambe le immagini mantengono la stessa X‑dimension, quindi il rapporto barra‑spazio rimane coerente mentre l'altezza complessiva si scala.

## Common variations and edge cases

| Situazione | Come gestirla |
|------------|----------------|
| **Simboli di codice a barre diversi** | Sostituisci `EncodeTypes.DatabarOmniDirectional` con un altro valore enum (ad es., `EncodeTypes.Code128`). Il resto del codice rimane invariato. |
| **Dimensioni non in pixel** | Usa `generator.Parameters.Barcode.XDimension.Millimeters` o `BarHeight.Millimeters` se hai bisogno di misurazioni fisiche per output pronto per la stampa. |
| **Sfondo trasparente** | Imposta `generator.Parameters.ImageBackgroundColor = Color.Transparent;` prima di chiamare `Save`. |
| **Output ad alta risoluzione** | Aumenta sia `XDimension.Pixels` sia `BarHeight.Pixels` proporzionalmente, oppure salva come `BarCodeImageFormat.Tiff` per qualità senza perdita. |
| **Più codici a barre in un'immagine** | Crea istanze separate di `BarcodeGenerator`, renderizza ciascuna in un `Bitmap`, poi componile usando `Graphics.DrawImage`. |

**Consiglio professionale:** Testa sempre il codice a barre generato con uno scanner reale prima di passare in produzione. Gli scanner possono interpretare barre molto sottili in modo diverso a seconda dell'illuminazione e della qualità del sensore.

## Full source code for reference

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator for a Databar Omnidirectional barcode
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231"); // Example GTIN

            // Custom X‑dimension (module width) – 2 px
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image: 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // Second image: 60 px height (larger barcode)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

Copia il codice in un nuovo progetto console, eseguilo e vedrai comparire i due file PNG nella cartella di output.

## Frequently asked questions

**Q: Posso generare un codice a barre senza installare una licenza?**  
A: La versione di valutazione di Aspose.BarCode funziona senza licenza ma aggiunge una piccola filigrana. Per l'uso in produzione, applica una licenza acquistata usando `License license = new License(); license.SetLicense("Aspose.BarCode.lic");`.

**Q: La modifica della X‑dimension influisce sulla leggibilità?**  
A: Sì. X‑dimension molto piccole possono rendere il codice a barre illeggibile su stampanti a bassa risoluzione. Si consiglia un minimo di 1 px per il rendering su schermo; per la stampa, utilizza almeno 0,25 mm.

**Q: E se avessi bisogno di generare un codice a barre in formato JPEG?**  
A: Sostituisci `BarCodeImageFormat.Png` con `BarCodeImageFormat.Jpeg`. Puoi anche impostare `generator.Parameters.ImageQuality` per controllare la compressione.

## Conclusion

Ora sai come **generare un'immagine di codice a barre** in C# usando Aspose.BarCode, come **creare un codice a barre Databar**, regolare una **dimensione personalizzata del codice a barre** e **modificare l'altezza del codice a barre** su richiesta. L'esempio completo dimostra il flusso di lavoro più comune, e la tabella delle variazioni ti prepara a gestire casi limite del mondo reale.

Successivamente, esplora argomenti correlati come **incorporare codici a barre in documenti PDF**, **generare in batch più codici a barre** e **utilizzare QR code per pagamenti mobili**. Ognuno di questi scenari si basa sugli stessi principi trattati qui, così potrai estendere questa conoscenza con sicurezza.

Buona programmazione e che i tuoi codici a barre vengano letti perfettamente!

## What Should You Learn Next?

I tutorial seguenti coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Generare immagine di codice a barre – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Come generare un codice a barre Aztec con rapporto d'aspetto personalizzato usando Aspose.BarCode per .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Come generare un codice a barre – Configurazione Code 39 con Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}