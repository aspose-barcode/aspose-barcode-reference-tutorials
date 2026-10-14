---
category: general
date: 2026-10-08
description: Genera codici a barre PDF417 in C# e scopri come generare immagini PDF417
  in modo efficiente con Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- create barcode image c#
language: it
lastmod: 2026-10-08
og_description: Genera codice a barre PDF417 in C# con una guida passo‑passo. Scopri
  come generare PDF417 e salvare l'immagine del codice a barre come PNG.
og_image_alt: Generated PDF417 barcode saved as a PNG image
og_title: Genera codice a barre PDF417 e crea immagine del codice a barre in C#
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Generate PDF417 barcode in C# and learn how to generate PDF417 images
    efficiently with Aspose.BarCode.
  headline: Generate PDF417 barcode and create barcode image C#
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Genera codice a barre PDF417 e crea immagine del codice a barre in C#
url: /it/net/compact-pdf417-encoding/generate-pdf417-barcode-and-create-barcode-image-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generare codice a barre PDF417 e creare immagine del codice a barre C#

Se hai bisogno di **generare un codice a barre PDF417** in un'applicazione .NET, questo tutorial ti mostra esattamente come farlo. Vedrai un esempio completo e eseguibile che crea un codice a barre, ne personalizza il layout e salva il risultato come immagine PNG.

Generare un codice a barre PDF417 è una necessità comune per etichette di spedizione, carte d'imbarco e sistemi di inventario. Alla fine di questa guida sarai in grado di **generare PDF417** con controllo granulare su dimensione e layout, e imparerai anche a **creare immagine del codice a barre C#** che può essere visualizzata in un'interfaccia UI o inviata a una stampante.

## Prerequisiti

- .NET 6.0 o successivo (il codice funziona anche con .NET Framework 4.7.2+)
- Visual Studio 2022 o qualsiasi IDE compatibile con C#
- Aspose.BarCode per .NET (versione di prova gratuita o licenziata)  
  Installala tramite NuGet:

```bash
dotnet add package Aspose.BarCode
```

Non è necessaria alcuna configurazione aggiuntiva; la libreria gestisce internamente la codifica PNG.

## Passo 1: Configurare il progetto e importare i namespace

Crea un nuovo progetto console e aggiungi le direttive `using` necessarie. Questo blocco include tutto il necessario per compilare l'esempio.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // All barcode generation code lives here
        }
    }
}
```

*Perché questo passo è importante*: importare il namespace `Aspose.BarCode.Generation` ti dà accesso a `BarcodeGenerator`, `EncodeTypes` e agli oggetti parametro usati per personalizzare il codice a barre.

## Passo 2: Generare il codice a barre PDF417 con il testo desiderato

All'interno di `Main`, istanzia `BarcodeGenerator` con `EncodeTypes.Pdf417`. Il costruttore accetta il tipo di codice a barre e il testo da codificare.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo");
```

*Spiegazione*: `EncodeTypes.Pdf417` indica alla libreria di produrre una simbologia PDF417. La stringa `"Layout demo"` diventa il payload di dati codificato nel codice a barre.

## Passo 3: Regolare finemente la dimensione del codice a barre usando la X‑dimension

La X‑dimension controlla la larghezza di un singolo modulo (il più piccolo quadrato nero/bianco). Impostarla in pixel fornisce un controllo preciso sulla dimensione finale dell'immagine.

```csharp
// Step 3: Define the module (X) dimension in pixels for finer control over barcode size
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Perché è importante*: una X‑dimension più piccola genera un codice a barre più compatto, utile quando lo spazio su un'etichetta o su un elemento UI è limitato.

## Passo 4: Personalizzare il layout PDF417 (colonne e righe)

PDF417 permette di specificare il numero di colonne e righe. Modificando questi valori si cambia il rapporto d'aspetto del codice a barre.

```csharp
// Step 4: Set the layout – 4 columns and 9 rows for this example
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9;
```

*Spiegazione*: con 4 colonne e 9 righe, il codice a barre diventa più alto che largo, corrispondente a molti formati di stampa di ticket.

## Passo 5: Salvare il codice a barre generato come immagine PNG

Infine, scrivi il codice a barre su file. L'enumerazione `BarCodeImageFormat.Png` garantisce una compressione senza perdita.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"YOUR_DIRECTORY\LayoutPdf417.png";
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

*Cosa succede qui*: `Save` crea il file immagine sul disco. Puoi sostituire `BarCodeImageFormat.Png` con `Jpeg` o `Bmp` se è necessario un formato diverso.

### Esempio completo in un unico blocco

Di seguito il programma completo, pronto per l'esecuzione. Sostituisci `YOUR_DIRECTORY` con un percorso di cartella reale sul tuo computer.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create a PDF417 barcode generator with the desired text
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo");

            // Define the module (X) dimension in pixels for finer control over barcode size
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Set the layout – 4 columns and 9 rows for this example
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
            barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9;

            // Save the generated barcode as a PNG image
            string outputPath = @"YOUR_DIRECTORY\LayoutPdf417.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Esegui il programma (`dotnet run`) e apri il file `LayoutPdf417.png` generato. Dovresti vedere un codice a barre PDF417 pulito che codifica il testo *Layout demo*.

![Generated PDF417 barcode example](image-placeholder.png){: .responsive-img alt="Barcode PDF417 generato salvato come PNG"}

*Output previsto*: un file PNG di circa 150 × 300 pixel (la dimensione varia con la X‑dimension) contenente un codice a barre PDF417 leggibile.

## Varianti comuni e casi limite

| Scenario | Come adattare il codice |
|----------|--------------------------|
| **Payload di dati diverso** | Cambia il secondo argomento di `BarcodeGenerator` (`"Layout demo"` → qualsiasi stringa, fino a 1 800 caratteri). |
| **Risoluzione più alta** | Incrementa `XDimension.Pixels` (es., `4`) o imposta `Resolution` tramite `barcodeGenerator.Parameters.ImageResolution.Dpi = 300;`. |
| **Sfondo trasparente** | Usa `barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent });`. |
| **Incorporamento in un Windows Forms PictureBox** | Invece di `Save`, chiama `barcodeGenerator.Save(pictureBox1.CreateGraphics(), BarCodeImageFormat.Png);`. |
| **Gestione degli errori** | Avvolgi il codice di generazione in un blocco `try…catch` per catturare `BarCodeException` in caso di caratteri non supportati. |

## Consigli professionali

- **Convalida il codice a barre**: dopo il salvataggio, puoi caricare il PNG con un SDK di scanner di codici a barre per verificare che i dati corrispondano alla stringa originale.
- **Prestazioni**: riutilizzare un'unica istanza di `BarcodeGenerator` per più codici a barre riduce l'overhead di allocazione.
- **Sicurezza**: se i dati codificati contengono informazioni sensibili, considera di crittografarli prima di passarli al generatore.

## Conclusione

Ora sai come **generare un codice a barre PDF417** in C# e **creare file immagine del codice a barre C#** che soddisfano requisiti di layout personalizzati. L'esempio completo dimostra l'inizializzazione del generatore, la regolazione di dimensione e layout, e il salvataggio del risultato come PNG. Da qui puoi esplorare funzionalità aggiuntive come la personalizzazione dei colori, l'incorporamento di loghi o la generazione batch di più codici a barre per stampe di grandi volumi.

---

*Passi successivi*:  
- Sperimenta con altre simbologie (Code128, QR) usando la stessa classe `BarcodeGenerator`.  
- Impara a leggere i codici a barre PDF417 con `BarCodeReader` di Aspose.BarCode.  
- Integra il PNG generato nelle viste ASP.NET Core MVC per la generazione di codici a barre al volo.

## Cosa dovresti imparare dopo?


I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare ulteriori funzionalità dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come salvare il codice a barre e generare PDF417 con Aspose in C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [Come generare codice a barre PDF417 con Aspose – Guida completa](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Come generare codice a barre PDF417 in C# con dimensioni personalizzate](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}