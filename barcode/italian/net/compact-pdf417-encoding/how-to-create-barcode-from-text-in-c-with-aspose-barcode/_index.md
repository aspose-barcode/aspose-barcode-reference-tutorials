---
category: general
date: 2026-10-02
description: Crea un codice a barre da testo in C# usando Aspose.BarCode. Scopri come
  generare un codice a barre PDF417 e vedi come generare il codice a barre PDF417
  in modalità compatta.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate pdf417 barcode
- how to generate pdf417 barcode
language: it
lastmod: 2026-10-02
og_description: Crea un codice a barre da testo in C# con Aspose.BarCode. Questa guida
  mostra come generare un codice a barre PDF417 e come generare un codice a barre
  PDF417 in modalità compatta.
og_image_alt: Screenshot showing create barcode from text output as a PNG image
og_title: Crea un codice a barre da testo in C# – guida passo passo
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  headline: How to create barcode from text in C# with Aspose.BarCode
  type: TechArticle
- description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  name: How to create barcode from text in C# with Aspose.BarCode
  steps:
  - name: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
    text: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
  - name: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
    text: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
  - name: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
    text: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Come creare un codice a barre da testo in C# con Aspose.BarCode
url: /it/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un codice a barre da testo in C# con Aspose.BarCode

Se hai bisogno di **creare un codice a barre da testo** in un'applicazione .NET, questa guida ti accompagna attraverso l'intero processo. Vedrai un esempio pronto all'uso che **genera un codice a barre PDF417** e risponde anche a **come generare un codice a barre PDF417** in un layout compatto.

Generare un codice a barre programmaticamente elimina i passaggi manuali e garantisce coerenza in tutti i documenti. Alla fine di questo tutorial avrai un file PNG contenente un codice a barre PDF417 che potrai inserire in fatture, biglietti o carte d'identità.

## Cosa ti serve

- .NET 6.0 SDK o successivo (il codice funziona anche con .NET Framework 4.7.2+)
- Visual Studio 2022 o qualsiasi editor che supporti C#
- Una licenza NuGet per **Aspose.BarCode for .NET** (una prova gratuita è sufficiente per i test)

> **Suggerimento professionale:** Aggiungi il pacchetto NuGet tramite la CLI per mantenere pulito il progetto:  
> `dotnet add package Aspose.BarCode`

## Passo 1: Configura un progetto console

Crea una nuova applicazione console e aggiungi il riferimento alla libreria Aspose.BarCode.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Il comando `dotnet new console` genera un file `Program.cs` che sostituiremo con l'esempio completo riportato di seguito.

## Passo 2: Come creare un codice a barre da testo – codice principale

Apri `Program.cs` e sostituisci il suo contenuto con il seguente codice. Ogni riga è commentata per spiegare il motivo della sua presenza.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Image;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Define the text that will be encoded.
            // The PDF417 symbology supports a wide range of Unicode characters.
            string textToEncode = "Åspóse.Barcóde©";

            // 2️⃣ Create a BarcodeGenerator for PDF417 using the desired text.
            // This object holds all settings and performs the rendering.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, textToEncode);

            // 3️⃣ Adjust module (X) dimension for better readability on screen.
            // XDimension defines the width of a single barcode column in pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Set the number of columns – a smaller column count yields a denser image.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 5️⃣ Enable compact mode by truncating the data.
            // Truncate = true removes padding, making the barcode smaller while preserving scannability.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 6️⃣ Choose the output path. Adjust the folder to match your environment.
            string outputPath = "CompactPdf417.png";

            // 7️⃣ Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Perché ogni impostazione è importante

| Impostazione | Scopo |
|--------|----------|
| `EncodeTypes.Pdf417` | Seleziona la simbologia PDF417, che può memorizzare grandi quantità di dati in una matrice bidimensionale. |
| `XDimension.Pixels = 2` | Controlla la larghezza di ogni modulo; un valore di 2 pixel bilancia leggibilità e dimensione del file. |
| `Pdf417.Columns = 3` | Riduce il numero di colonne, rendendo il codice a barre più compatto senza perdere dati. |
| `Pdf417.Truncate = true` | Attiva la modalità compatta, rimuovendo il padding non necessario e accorciando il codice a barre. |
| `BarCodeImageFormat.Png` | PNG conserva la qualità lossless, ideale per ulteriori elaborazioni o stampe. |

## Passo 3: Genera il codice a barre PDF417 – eseguendo l'esempio

Compila ed esegui il progetto:

```bash
dotnet run
```

Al termine dell'esecuzione vedrai:

```
Barcode saved to CompactPdf417.png
```

Apri `CompactPdf417.png` per visualizzare il risultato. L'immagine contiene un codice a barre PDF417 che codifica la stringa **Åspóse.Barcóde©**.

![Create barcode from text example](barcode-example.png)

*Alt text: crea codice a barre da testo – codice a barre PDF417 salvato come PNG*

## Passo 4: Come generare un codice a barre PDF417 con correzione d'errore personalizzata (opzionale)

Se l'ambiente di scansione è rumoroso, puoi aumentare il livello di correzione degli errori:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // Levels 0–5, higher = more redundancy
```

Aumentare il livello di errore rende il codice a barre più grande ma migliora la resilienza contro i danni.

## Passo 5: Problemi comuni e gestione dei casi limite

1. **Caratteri non validi** – PDF417 supporta Unicode, ma alcuni scanner più vecchi potrebbero rifiutare simboli non‑ASCII. Testa con l'hardware di destinazione.
2. **Permessi del percorso file** – Assicurati che la directory in cui scrivi sia scrivibile; altrimenti `Save` genera un `UnauthorizedAccessException`.
3. **Dimensione immagine** – Valori molto alti di `XDimension` producono file PNG di grandi dimensioni. Mantieni la dimensione in pixel tra 1 e 4 per la maggior parte degli scenari di visualizzazione su schermo.

## Riepilogo

Ora sai come **creare un codice a barre da testo** in C# usando Aspose.BarCode, come **generare un codice a barre PDF417** con un layout compatto, e i passaggi esatti per **come generare un codice a barre PDF417** con impostazioni personalizzate. Il codice completo e eseguibile sopra può essere copiato in qualsiasi progetto .NET e adattato a diversi input di testo o formati di output (ad es., JPEG, BMP).

## Prossimi passi

- Esplora altre simbologie come QR Code o Code128 modificando `EncodeTypes`.
- Integra il PNG generato in un PDF usando Aspose.PDF per la creazione di documenti end‑to‑end.
- Sperimenta con `generator.Parameters.Barcode.Pdf417.Rows` per controllare la densità verticale.

Sentiti libero di modificare l'esempio, incorporare il codice a barre nelle tue applicazioni e condividere i tuoi risultati con la community. Buon coding!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come generare un codice a barre PDF417 in C# – esempio compatto](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-compact-example/)
- [Come creare un codice a barre PDF417 in C# con modalità compatta](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [Come generare un codice a barre PDF417 in C# – guida passo‑passo](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}