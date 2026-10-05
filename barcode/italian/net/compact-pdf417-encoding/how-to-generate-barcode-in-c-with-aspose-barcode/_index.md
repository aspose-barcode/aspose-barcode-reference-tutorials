---
category: general
date: 2026-09-16
description: Scopri come generare un codice a barre e impostare le dimensioni del
  codice a barre in C#. Guida passo passo che utilizza Aspose.BarCode per creare un'immagine
  Micro PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- set barcode size
language: it
lastmod: 2026-09-16
og_description: Come generare un codice a barre in C# e impostare le dimensioni del
  codice a barre con Aspose.BarCode. Segui questo conciso tutorial per produrre un
  PNG Micro PDF417.
og_image_alt: Example output showing how to generate barcode using C#
og_title: Come generare un codice a barre in C# – guida completa ad Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to generate barcode and set barcode size in C#. Step‑by‑step
    guide using Aspose.BarCode to create a Micro PDF417 image.
  headline: How to generate barcode in C# with Aspose.BarCode
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Come generare un codice a barre in C# con Aspose.BarCode
url: /it/net/compact-pdf417-encoding/how-to-generate-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come generare un codice a barre in C# con Aspose.BarCode

Se hai bisogno di sapere **come generare un codice a barre** in un progetto .NET, questo tutorial ti guida attraverso l'intero processo usando la libreria Aspose.BarCode. Imparerai anche come **impostare le dimensioni del codice a barre** affinché l'immagine si adatti alla tua interfaccia utente o ai requisiti di stampa.

La guida copre tutto, dall'installazione del pacchetto NuGet alla configurazione di un simbolo Micro PDF417 e al salvataggio come file PNG. Alla fine, avrai un esempio di codice eseguibile da inserire in qualsiasi applicazione console o web C#.

## Cosa ti serve

- .NET 6.0 o successivo (il codice funziona anche con .NET Framework 4.6+)
- Visual Studio 2022 o qualsiasi IDE che supporti C#
- Accesso a Internet per scaricare il pacchetto NuGet **Aspose.BarCode**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Familiarità di base con la sintassi C#

## Come generare un codice a barre con Aspose.BarCode

Il primo passo è creare un'istanza di `BarcodeGenerator` che sappia quale simbologia utilizzare e quali dati codificare.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a Micro PDF417 barcode generator with the data to encode
var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Micro data");
```

**Perché è importante:** `EncodeTypes.MicroPdf417` indica alla libreria di produrre una variante compatta di PDF417, ideale per etichette piccole o impronte simili a QR‑code. La stringa `"Micro data"` diventa il payload leggibile dall'uomo incorporato nel codice a barre.

## Imposta le dimensioni e le proporzioni del codice a barre

Un codice a barre leggibile deve avere la giusta dimensione del modulo (X) e un numero sufficiente di colonne per contenere i dati. È qui che **imposti le dimensioni del codice a barre**.

```csharp
// Step 2: Define the module size (X dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Set the maximum number of columns for the Micro PDF417 symbol
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

- **XDimension** controlla la larghezza della barra più piccola (il “modulo”). Un valore di `2` pixel funziona bene per la visualizzazione su schermo; aumentalo per la stampa ad alta risoluzione.
- **Pdf417.Columns** limita il numero di colonne verticali. Il formato Micro PDF417 supporta solo fino a 7 colonne; `4` offre una dimensione equilibrata senza sacrificare la capacità dei dati.

> **Consiglio professionale:** Se l'immagine generata appare troppo piccola, aumenta `XDimension.Pixels` a `3` o `4`. Al contrario, per spazi UI ristretti, puoi ridurlo a `1`, ma assicurati che lo scanner che intendi usare possa ancora leggere il simbolo.

## Salva l'immagine del codice a barre

Dopo aver configurato le dimensioni, basta istruire il generatore a scrivere l'immagine su disco.

```csharp
// Step 4: Save the generated barcode as a PNG image
barcodeGenerator.Save("micro.png", BarCodeImageFormat.Png);
```

Il metodo `Save` accetta qualsiasi formato supportato da Aspose.BarCode (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`). PNG è senza perdita, preservando i bordi nitidi necessari per una scansione affidabile.

**Output previsto:** Un file chiamato `micro.png` apparirà nella directory di lavoro del progetto. Aprendolo si vede un piccolo codice a barre Micro PDF417 ad alto contrasto, pronto per i test con qualsiasi scanner standard.

## Esempio completo

Unendo tutti i componenti ottieni un programma autonomo che puoi eseguire immediatamente.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for Micro PDF417
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Micro data");

            // Set size parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
            generator.Parameters.Barcode.Pdf417.Columns = 4;    // column count

            // Choose output path (adjust as needed)
            string outputPath = "micro.png";

            // Save as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Esegui il programma (`dotnet run` dalla console) e vedrai il messaggio di conferma. Il PNG generato può essere incorporato nei report, stampato su etichette di prodotto o visualizzato in una pagina web.

## Domande comuni e casi particolari

| Question | Answer |
|---|---|
| **Posso generare altri tipi di codice a barre?** | Sì. Sostituisci `EncodeTypes.MicroPdf417` con qualsiasi valore dell'enumerazione `EncodeTypes` (ad esempio, `EncodeTypes.Code128`, `EncodeTypes.QR`). |
| **E se ho bisogno di un'immagine più grande?** | Aumenta `XDimension.Pixels` o usa `generator.Parameters.Image.Width/Height` per forzare una dimensione pixel specifica. |
| **La libreria supporta sfondi trasparenti?** | Imposta `generator.Parameters.Barcode.BackColor = System.Drawing.Color.Transparent;` prima di chiamare `Save`. |
| **Come leggo il codice a barre?** | Usa `Aspose.BarCode.BarCodeReader` sull'immagine salvata; rileva automaticamente la simbologia. |
| **Il PNG è adatto per la stampa?** | PNG è senza perdita, ma per la stampa CMYK considera di salvare come TIFF (`BarCodeImageFormat.Tiff`). |

## Conclusione

Ora sai **come generare un codice a barre** in C# e come **impostare le dimensioni del codice a barre** usando Aspose.BarCode. L'esempio completo dimostra la creazione di un simbolo Micro PDF417, la regolazione delle sue dimensioni e l'esportazione di un file PNG. Con questa base puoi esplorare altre simbologie, personalizzare i colori o integrare la generazione di codici a barre nei servizi ASP.NET Core.

### Prossimi passi

- Prova a generare un QR code (`EncodeTypes.QR`) e confronta le dimensioni dei moduli.  
- Sperimenta con `generator.Parameters.Image` per aggiungere margini o modificare DPI per un output pronto per la stampa.  
- Combina la generazione di codici a barre con **Aspose.PDF** per incorporare l'immagine direttamente in un report PDF.

Buon coding e goditi la flessibilità che Aspose.BarCode porta ai tuoi progetti .NET di codici a barre!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come generare un'immagine di codice a barre PDF417 in C# con Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Come generare un codice a barre PDF417 con Aspose – Guida completa](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Come generare un codice a barre in C# – Guida completa Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}