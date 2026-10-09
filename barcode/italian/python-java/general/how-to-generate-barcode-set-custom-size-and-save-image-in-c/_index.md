---
category: general
date: 2026-09-13
description: Scopri come generare un codice a barre in C#, personalizzare le dimensioni
  del codice a barre e salvare l’immagine del codice a barre come PNG usando Aspose.BarCode.
  Guida completa passo‑passo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- custom barcode size
- save barcode image
- Aspose.BarCode C#
- barcode image format
language: it
lastmod: 2026-09-13
og_description: Come generare un codice a barre in C# con dimensioni personalizzate
  del codice a barre e salvare l'immagine del codice a barre come PNG. Segui questa
  guida completa per Aspose.BarCode.
og_image_alt: Screenshot of a DataBar stacked omnidirectional barcode generated in
  C#
og_title: Come generare un codice a barre, impostare dimensioni personalizzate e salvare
  l'immagine in C#
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to generate barcode in C#, customize barcode size, and save
    barcode image as PNG using Aspose.BarCode. Complete step‑by‑step guide.
  headline: How to generate barcode set custom size and save image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Come generare un codice a barre, impostare dimensioni personalizzate e salvare
  l'immagine in C#
url: /it/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come generare un set di codici a barre di dimensioni personalizzate e salvare l'immagine in C#

Se hai bisogno di **come generare un codice a barre** in un'applicazione .NET, questo tutorial ti mostra una soluzione completa. Vedrai come regolare la **dimensione personalizzata del codice a barre** e **salvare l'immagine del codice a barre** con poche righe di codice C#.

Generare codici a barre è una necessità comune per sistemi di inventario, etichette di spedizione e applicazioni point‑of‑sale. Alla fine di questa guida avrai un programma eseguibile che crea due codici a barre DataBar‑Stacked‑Omnidirectional, ciascuno con un rapporto d'aspetto diverso, e li scrive in file PNG su disco.

**Prerequisites**

- .NET 6.0 o versioni successive (il codice funziona anche con .NET Framework 4.7+)
- Visual Studio 2022 o qualsiasi IDE C#
- Aspose.BarCode per .NET (versione di prova gratuita o pacchetto NuGet con licenza)

---

## Come generare un codice a barre con Aspose.BarCode

La libreria Aspose.BarCode astrae i dettagli di basso livello degli standard dei codici a barre, permettendoti di concentrarti sui dati da codificare e sull'aspetto visivo necessario.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar stacked omnidirectional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GS1‑128 format example

        // 2️⃣ Set a basic module width – this influences the overall **custom barcode size**
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First aspect ratio (15) → save the image
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // 4️⃣ Change aspect ratio to 30 → **save barcode image** again
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### Perché ogni riga è importante

| Passo | Spiegazione |
|------|-------------|
| **1️⃣ Crea un generatore** | L'enum `EncodeTypes.DatabarStackedOmniDirectional` indica ad Aspose quale simbologia di codice a barre utilizzare. La stringa `"(01)12345678901231"` segue il formato dati GS1‑128, dove `(01)` è l'Identificatore di Applicazione per un GTIN. |
| **2️⃣ Imposta la X‑dimension** | `XDimension.Pixels` definisce la larghezza di un singolo modulo del codice a barre (la barra più piccola). Modificare questo valore è il modo principale per ottenere una **dimensione personalizzata del codice a barre** senza alterare i dati codificati. |
| **3️⃣ Imposta il rapporto d'aspetto e salva** | `DataBar.AspectRatio` controlla il rapporto altezza‑larghezza dei simboli DataBar. Un rapporto d'aspetto di 15 produce un codice a barre relativamente corto e largo, mentre 30 lo rende più alto. `Save` scrive la rappresentazione visiva in un file PNG, soddisfacendo il requisito di **salvare l'immagine del codice a barre**. |
| **4️⃣ Cambia il rapporto d'aspetto e salva di nuovo** | Riutilizzare la stessa istanza del generatore ti consente di produrre più immagini con caratteristiche visive diverse mantenendo costanti i dati. |

---

## Regolare la dimensione personalizzata del codice a barre oltre la X‑dimension

Mentre `XDimension.Pixels` imposta la larghezza del modulo, è possibile affinare le dimensioni complessive del codice a barre combinando due proprietà:

1. **`BarHeight`** – altezza esplicita in pixel.  
2. **`BarWidth`** – larghezza esplicita in pixel (sovrascrive X‑dimension).

```csharp
// Example: make a larger, more readable barcode
generator.Parameters.Barcode.XDimension.Pixels = 4;      // wider modules
generator.Parameters.Barcode.BarHeight.Pixels = 120;    // taller bars
generator.Parameters.Barcode.DataBar.AspectRatio = 20; // balanced ratio
generator.Save("LargeCustomSize.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved large custom size barcode.");
```

> **Consiglio professionale:** Quando stampi i codici a barre, testa sempre l'immagine generata alla dimensione finale di stampa. Una larghezza del modulo di 2 px è adeguata per la visualizzazione su schermo, ma le etichette stampate spesso richiedono almeno 4 px per rimanere leggibili.

---

## Scegliere il formato immagine corretto per salvare l'immagine del codice a barre

Aspose.BarCode supporta PNG, JPEG, BMP, GIF e TIFF. PNG è senza perdita e preserva bordi nitidi, rendendolo la scelta più sicura per la maggior parte delle applicazioni. Se ti serve un file più piccolo per il web, JPEG con impostazione di qualità 90 funziona bene, ma tieni presente che gli artefatti di compressione possono influire sull'affidabilità della scansione.

```csharp
generator.Save("DatabarAspectRatio15.jpg", BarCodeImageFormat.Jpeg, 90);
Console.WriteLine("Saved JPEG version with quality 90.");
```

---

## Esempio completo e eseguibile

Di seguito trovi un'applicazione console autonoma che puoi copiare, incollare ed eseguire. Dimostra **come generare un codice a barre**, modificare la **dimensione personalizzata del codice a barre** e **salvare l'immagine del codice a barre** in due formati diversi.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with the desired symbology and data
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // ---- Custom size configuration ----
            generator.Parameters.Barcode.XDimension.Pixels = 2;      // module width
            generator.Parameters.Barcode.BarHeight.Pixels = 80;    // optional explicit height
            generator.Parameters.Barcode.DataBar.AspectRatio = 15; // first aspect ratio

            // Save first image as PNG
            string pngPath1 = "DatabarAspectRatio15.png";
            generator.Save(pngPath1, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath1}");

            // Change aspect ratio for a taller barcode
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string pngPath2 = "DatabarAspectRatio30.png";
            generator.Save(pngPath2, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath2}");

            // ---- Larger custom size example ----
            generator.Parameters.Barcode.XDimension.Pixels = 4;
            generator.Parameters.Barcode.BarHeight.Pixels = 120;
            generator.Parameters.Barcode.DataBar.AspectRatio = 20;
            string largePath = "LargeCustomSize.png";
            generator.Save(largePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {largePath}");

            // ---- Save as JPEG for web use ----
            string jpegPath = "DatabarAspectRatio15.jpg";
            generator.Save(jpegPath, BarCodeImageFormat.Jpeg, 90);
            Console.WriteLine($"Saved {jpegPath}");
        }
    }
}
```

**Output previsto sulla console**

```
Saved DatabarAspectRatio15.png
Saved DatabarAspectRatio30.png
Saved LargeCustomSize.png
Saved DatabarAspectRatio15.jpg
```

I quattro file immagine appariranno nel programma


## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come generare codici DataMatrix usando Aspose.BarCode per .NET – Guida passo‑passo](/barcode/english/net/datamatrix-barcode-configuration/)
- [Come generare il codice a barre PDF417 con Aspose – Guida completa](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Come generare un codice a barre Aztec con rapporto d'aspetto personalizzato usando Aspose.BarCode per .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}