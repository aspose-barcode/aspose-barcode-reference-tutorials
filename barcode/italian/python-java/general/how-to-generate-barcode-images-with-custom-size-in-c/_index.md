---
category: general
date: 2026-08-22
description: Come generare rapidamente un codice a barre e imparare a modificare le
  dimensioni del codice a barre durante l'esportazione dell'immagine in PNG usando
  Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- change barcode size
- export barcode image
language: it
lastmod: 2026-08-22
og_description: Come generare un codice a barre in C# e modificare facilmente le dimensioni
  del codice a barre prima di esportare l'immagine del codice a barre come PNG. Segui
  questa guida completa.
og_image_alt: Screenshot showing how to generate barcode with Aspose.BarCode in C#
og_title: Come generare immagini di codice a barre con dimensioni personalizzate in
  C#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode quickly and learn how to change barcode size
    while exporting the barcode image as PNG using Aspose.BarCode.
  headline: How to generate barcode images with custom size in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Come generare immagini di codice a barre con dimensioni personalizzate in C#
url: /it/python-java/general/how-to-generate-barcode-images-with-custom-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come generare immagini di codici a barre con dimensioni personalizzate in C#

Se hai bisogno di **come generare barcode** per l'automazione postale, il tracciamento dell'inventario o i biglietti per eventi, questa guida ti mostra una soluzione completa, pronta all'uso in C#. Imparerai anche **come cambiare la dimensione del barcode** e **esportare l'immagine del barcode** in formato PNG senza uscire dal tuo IDE.

Utilizzeremo la libreria Aspose.BarCode perché supporta la simbologia OneCode, consente di controllare le dimensioni pixel per pixel e gestisce l'esportazione dell'immagine con una singola chiamata di metodo. Alla fine del tutorial avrai quattro file PNG—ognuno dei quali rappresenta un codice a barre OneCode con un diverso numero di cifre.

## Prerequisiti

- .NET 6.0 o successivo (il codice funziona anche con .NET Framework 4.6+)
- Visual Studio 2022 (o qualsiasi editor C# tu preferisca)
- Un riferimento NuGet a **Aspose.BarCode** (`Install-Package Aspose.BarCode`)
- Familiarità di base con la sintassi C#

> **Suggerimento professionale:** Se stai valutando la libreria, Aspose offre una prova gratuita di 30 giorni che include tutte le funzionalità dei barcode.

## Passo 1: Configura un progetto console minimale

Crea una nuova applicazione console e aggiungi il pacchetto Aspose.BarCode:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Il file `Program.cs` generato conterrà tutta la logica di generazione del barcode.

## Passo 2: Come generare barcode – crea un metodo riutilizzabile

Di seguito è riportato un metodo autonomo che riceve la stringa dei dati, il nome file desiderato e parametri di dimensione opzionali. Questo metodo dimostra il modello principale per **come generare barcode**.

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
            // Example calls for different digit lengths
            GenerateOneCode("12345678901234567890", "PostalOneCodeBarcode20Digits.png");
            GenerateOneCode("1234567890123456789012345", "PostalOneCodeBarcode25Digits.png");
            GenerateOneCode("12345678901234567890123456789", "PostalOneCodeBarcode29Digits.png");
            GenerateOneCode("1234567890123456789012345678901", "PostalOneCodeBarcode31Digits.png");
        }

        /// <summary>
        /// Generates a OneCode barcode, applies size settings, and saves as PNG.
        /// </summary>
        /// <param name="data">Numeric string to encode (OneCode supports 20‑31 digits).</param>
        /// <param name="fileName">Target PNG file name.</param>
        /// <param name="xDimension">Width of a single module in pixels (default 4).</param>
        /// <param name="barHeight">Height of the barcode in pixels (default 50).</param>
        static void GenerateOneCode(string data, string fileName,
                                    int xDimension = 4, int barHeight = 50)
        {
            // 1️⃣ Initialize the generator for OneCode symbology
            var generator = new BarcodeGenerator(EncodeTypes.OneCode, data);

            // 2️⃣ **Change barcode size** – adjust module width and total height
            generator.Parameters.Barcode.XDimension.Pixels = xDimension; // module width
            generator.Parameters.Barcode.BarHeight.Pixels = barHeight;   // overall height

            // 3️⃣ **Export barcode image** as PNG; you can also choose JPEG, BMP, etc.
            generator.Save(fileName, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {fileName}");
        }
    }
}
```

### Perché questo metodo è importante

- **Incapsulamento:** Tutte le impostazioni relative alle dimensioni sono in un unico posto, rendendo banale chiamare il metodo con dimensioni diverse.
- **Riutilizzabilità:** Puoi riutilizzare lo stesso metodo per qualsiasi lunghezza di stringa OneCode, il che è essenziale perché OneCode accetta solo da 20 a 31 cifre.
- **Chiarezza:** I commenti contrassegnati con emoji guidano i lettori attraverso le tre fasi logiche—inizializzazione, modifica della dimensione e esportazione.

## Passo 3: Cambia la dimensione del barcode per requisiti diversi

A volte uno scanner si aspetta un barcode più alto, o il layout di stampa richiede un modulo più stretto. La proprietà `XDimension.Pixels` controlla la larghezza di un singolo modulo del barcode, mentre `BarHeight.Pixels` imposta l'altezza complessiva.

```csharp
// Example: generate a larger barcode (8‑pixel modules, 80‑pixel height)
GenerateOneCode(
    data: "12345678901234567890",
    fileName: "LargeOneCode.png",
    xDimension: 8,
    barHeight: 80);
```

**Punti chiave quando cambi la dimensione:**

- **Dimensione X minima:** 1 pixel è tecnicamente consentito, ma la maggior parte degli scanner necessita di almeno 2 pixel per una lettura affidabile.
- **Altezza massima:** Non esiste un limite rigido, ma barcode molto alti possono superare l'area stampabile su etichette standard.
- **Rapporto d'aspetto:** Mantieni il rapporto altezza‑larghezza‑modulo equilibrato (≈12‑15 × larghezza modulo) per evitare distorsioni.

## Passo 4: Esporta l'immagine del barcode in altri formati (opzionale)

Il metodo `Save` accetta diversi valori `BarCodeImageFormat`: `Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`. Se ti serve un formato vettoriale senza perdita, puoi esportare in `Svg` invece.

```csharp
// Export to SVG for infinite scaling
generator.Save("OneCode.svg", BarCodeImageFormat.Svg);
```

Esportare in PNG è la scelta più comune perché preserva bordi nitidi ed è ampiamente supportato dai browser web e dalle pipeline di stampa.

## Output previsto

Eseguendo il programma vengono creati quattro file PNG nella cartella del progetto:

- `PostalOneCodeBarcode20Digits.png` – barcode OneCode a 20 cifre
- `PostalOneCodeBarcode25Digits.png` – barcode OneCode a 25 cifre
- `PostalOneCodeBarcode29Digits.png` – barcode OneCode a 29 cifre
- `PostalOneCodeBarcode31Digits.png` – barcode OneCode a 31 cifre

Ogni immagine avrà un aspetto simile al segnaposto qui sotto (il grafico reale dipende dai dati numerici forniti).

![Esempio di come generare barcode](https://example.com/placeholder.png "Esempio di come generare barcode")

*Il testo alternativo dell'immagine include la parola chiave principale per accessibilità e SEO.*

## Domande comuni e casi limite

| Domanda | Risposta |
|----------|--------|
| **Cosa succede se la stringa dei dati è più corta di 20 cifre?** | OneCode richiede un minimo di 20 cifre. Aggiungi zeri iniziali alla stringa o usa una simbologia diversa (ad esempio, Code128). |
| **Posso generare barcode in un ambiente multi‑thread?** | Sì. `BarcodeGenerator` non è thread‑safe, quindi istanzia un generatore separato per ogni thread. |
| **Come impostare un colore di sfondo?** | Usa `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.White;` prima di chiamare `Save`. |
| **C'è un modo per incorporare l'immagine direttamente in una pagina HTML?** | Salva l'immagine in un `MemoryStream`, convertila in Base64 e incorporala con `<img src="data:image/png;base64,..." />`. |

## Conclusione

Ora sai **come generare barcode** in C# con Aspose.BarCode, come **cambiare la dimensione del barcode** regolando X‑dimension e altezza delle barre, e come **esportare l'immagine del barcode** in formato PNG (o altri). Il metodo riutilizzabile `GenerateOneCode` ti consente di creare qualsiasi barcode OneCode tra 20 e 31 cifre con una singola riga di codice.

Da qui potresti:

- Sperimentare con altre simbologie (`EncodeTypes.Code128`, `EncodeTypes.QR`).
- Integrare il generatore in una web API che restituisce immagini barcode su richiesta.
- Combinare l'output PNG con una libreria PDF per incorporare i barcode nelle etichette di spedizione.

Buon coding, e sentiti libero di condividere le tue varianti nei commenti!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come generare codici DataMatrix usando Aspose.BarCode per .NET – Guida passo‑passo](/barcode/english/net/datamatrix-barcode-configuration/)
- [Come generare barcode Aztec con rapporto d'aspetto personalizzato usando Aspose.BarCode per .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Come generare e regolare l'altezza del barcode One‑Dimensional Databar usando Aspose.BarCode per .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}