---
category: general
date: 2026-09-29
description: La guida al generatore di codici a barre C# mostra come generare un codice
  a barre MicroPdf417, modificare le dimensioni, impostare le colonne e personalizzare
  la dimensione del codice a barre in poche righe.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- how to generate barcode
- how to change dimensions
- how to set columns
- customize barcode size
language: it
lastmod: 2026-09-29
og_description: La guida al generatore di codici a barre C# mostra come generare un
  codice a barre MicroPdf417, modificare le dimensioni, impostare le colonne e personalizzare
  la dimensione del codice a barre in poche righe.
og_image_alt: Screenshot of a MicroPdf417 barcode generated with a C# barcode generator
og_title: Guida al generatore di codici a barre C# – crea e personalizza MicroPdf417
schemas:
- author: GroupDocs
  dateModified: '2026-09-29'
  description: Barcode generator C# guide shows how to generate a MicroPdf417 barcode,
    change dimensions, set columns, and customize barcode size in just a few lines.
  headline: 'Barcode generator C# guide: create MicroPdf417'
  type: TechArticle
tags:
- barcode
- C#
- MicroPdf417
- barcode generation
title: 'Guida al generatore di codici a barre C#: crea MicroPdf417'
url: /it/net/compact-pdf417-encoding/barcode-generator-c-guide-create-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Guida al generatore di codici a barre C#: creare MicroPdf417

Se hai bisogno di un **barcode generator C#** per il tuo progetto .NET, questo tutorial ti guida nella creazione di un codice a barre MicroPdf417 da zero. Imparerai **come generare il codice a barre**, modificare le dimensioni, impostare le colonne e **personalizzare le dimensioni del codice a barre** senza sforzo.

MicroPdf417 è una simbologia 2‑D compatta che funziona bene per etichettare piccoli componenti, biglietti o tag di inventario. Alla fine di questa guida avrai un'applicazione console completa e eseguibile che genera un'immagine PNG del codice a barre, e comprenderai come ogni parametro influisce sulla dimensione finale.

## Prerequisiti

* .NET 6.0 SDK o versioni successive (il codice funziona anche con .NET Framework 4.7+)
* Un IDE compatibile con C# (Visual Studio, VS Code, Rider, ecc.)
* Il pacchetto NuGet **GroupDocs.Barcode** – installalo con  

  ```bash
  dotnet add package GroupDocs.Barcode
  ```

Non sono necessari strumenti esterni aggiuntivi; la libreria gestisce la codifica, il rendering e il salvataggio dei file.

## Generatore di codici a barre C#: inizializzare il generatore

Il primo passo è creare un'istanza di `BarcodeGenerator` e specificare la simbologia (`EncodeTypes.MicroPdf417`) insieme ai dati che desideri codificare.

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1 – create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // Subsequent configuration steps go here...

            // Save the final image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

**Perché è importante:**  
`BarcodeGenerator` è il punto di ingresso per tutte le operazioni sui codici a barre. Il costruttore associa gli **EncodeTypes** scelti (MicroPdf417) alla stringa di dati grezzi. La libreria gestisce automaticamente i caratteri Unicode come “Å” e “©”, quindi non è necessaria alcuna logica di codifica aggiuntiva.

## Come modificare le dimensioni del codice a barre

La leggibilità di un codice a barre dipende molto dalla larghezza del modulo (la X‑dimension). Impostarla a un numero di pixel più alto rende le barre più larghe e l'immagine più facile da scansionare, soprattutto su display a bassa risoluzione.

```csharp
// Step 2 – adjust the X‑dimension (module width) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Spiegazione:**  
`XDimension.Pixels` controlla la larghezza di un singolo modulo del codice a barre. Il valore predefinito è 1 pixel, che può apparire sottile su monitor ad alta DPI. Incrementandolo a 2 pixel si raddoppia la larghezza complessiva senza influire sui dati codificati.

**Suggerimento:** Se prevedi di stampare il codice a barre a 300 dpi, un valore di 3 o 4 pixel spesso offre il miglior equilibrio tra dimensione e affidabilità della scansione.

## Come impostare le colonne per il controllo delle dimensioni

MicroPdf417 ti consente di specificare il numero di colonne (fino a 4). Meno colonne producono un codice a barre più alto; più colonne lo rendono più largo ma più corto. Regolare questo valore è il modo principale per **personalizzare le dimensioni del codice a barre**.

```csharp
// Step 3 – set the maximum number of columns (4 is the limit for MicroPdf417)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Perché funziona:**  
La proprietà `Pdf417.Columns` è condivisa tra tutte le simbologie basate su PDF417, inclusa MicroPdf417. Impostandola al massimo (4) si distribuiscono i dati nel layout più ampio possibile, riducendo l'altezza complessiva. Se ti serve un'altezza più compatta, riduci il numero di colonne a 2 o 3.

**Caso limite:** Quando la stringa di dati è lunga, la libreria può aumentare automaticamente le righe per contenere il contenuto, indipendentemente dal numero di colonne. Mantieni il payload sotto i 50 caratteri per una dimensione prevedibile.

## Personalizzare le dimensioni del codice a barre per uscite diverse

Oltre alla X‑dimension e alle colonne, puoi influenzare la dimensione finale dell'immagine scegliendo un formato immagine e DPI appropriati. PNG è senza perdita, perfetto per la visualizzazione web, mentre BMP o TIFF possono essere preferibili per stampe di alta qualità.

```csharp
// Step 4 – save as PNG (lossless) with default 96 dpi
generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
```

Se ti serve un DPI più alto, puoi impostarlo esplicitamente:

```csharp
generator.Parameters.Image.DpiX = 300;
generator.Parameters.Image.DpiY = 300;
generator.Save("MicroPdf417_300dpi.png", BarCodeImageFormat.Png);
```

**Risultato:** Il file PNG salvato contiene un codice a barre MicroPdf417 nitido che rispetta le dimensioni configurate. Apri il file in qualsiasi visualizzatore di immagini per verificare la dimensione visiva.

### Output previsto

Eseguendo il programma si genera un file chiamato **MicroPdf417.png** (o **MicroPdf417_300dpi.png** se hai impostato il DPI). Il codice a barre avrà un aspetto simile all'illustrazione seguente:

![Barcode generator C# output showing a MicroPdf417 PNG](barcode-micro-pdf417.png)

*Testo alternativo:* *Output del generatore di codici a barre C# che mostra un PNG MicroPdf417*

Scansionando l'immagine con un lettore di codici a barre 2‑D standard si ottiene la stringa originale `Åspóse.Barcóde©`.

## Codice sorgente completo per copia‑incolla veloce

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // 2️⃣ Change dimensions – make modules 2 pixels wide
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set columns – use the maximum of 4 for a wider, shorter barcode
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // (Optional) Increase DPI for high‑resolution output
            // generator.Parameters.Image.DpiX = 300;
            // generator.Parameters.Image.DpiY = 300;

            // 4️⃣ Save the barcode as a PNG image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

Copia il codice in un nuovo progetto console, ripristina i pacchetti NuGet ed esegui `dotnet run`. La console confermerà la posizione dell'immagine e vedrai il codice a barre generato nella cartella del progetto.

## Domande frequenti e risoluzione dei problemi

| Domanda | Risposta |
|----------|--------|
| **Cosa succede se il codice a barre appare sfocato?** | Aumenta `XDimension.Pixels` o il DPI (`Parameters.Image.DpiX/Y`). Entrambi ingrandiscono i moduli e migliorano la fedeltà visiva. |
| **Posso usare un formato immagine diverso?** | Sì. Sostituisci `BarCodeImageFormat.Png` con `Jpeg`, `Bmp` o `Tiff`. PNG rimane la scelta più sicura per la qualità senza perdita. |
| **I miei dati contengono emoji—verranno codificate?** | MicroPdf417 supporta UTF‑8, quindi la maggior parte delle emoji vengono codificate correttamente. Se incontri errori, verifica che la stringa sia correttamente normalizzata (`System.Text.Encoding.UTF8`). |
| **Come genero altre simbologie?** | Change `EncodeTypes.MicroPdf417` to any other value from `EncodeTypes` ( |

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come generare un'immagine di codice a barre in C# – Guida MicroPdf417](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/)
- [Come generare un codice a barre PDF417 in C# con dimensioni personalizzate](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}