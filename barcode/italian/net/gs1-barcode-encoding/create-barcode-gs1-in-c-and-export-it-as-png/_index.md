---
category: general
date: 2026-09-29
description: Crea un codice a barre GS1 in C# e genera immagini PNG del codice a barre
  usando BarcodeGenerator. Segui una guida passo passo per esportare l'immagine del
  codice a barre in modo efficiente.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode gs1
- generate barcode png
- barcode generator c#
- how to generate barcode
- export barcode image
language: it
lastmod: 2026-09-29
og_description: Crea un codice a barre GS1 in C# e genera file PNG del codice a barre
  con BarcodeGenerator. Segui questa guida completa per esportare rapidamente l'immagine
  del codice a barre.
og_image_alt: Generated GS1 MicroPDF417 barcode saved as a PNG file
og_title: Crea codice a barre GS1 in C# – esporta come PNG in pochi minuti
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create barcode GS1 in C# and generate barcode PNG images using BarcodeGenerator.
    Follow a step‑by‑step guide to export barcode image efficiently.
  headline: Create barcode GS1 in C# and export it as PNG
  type: TechArticle
tags:
- barcode
- C#
- GS1
- PNG
- Aspose
title: Crea codice a barre GS1 in C# ed esportalo come PNG
url: /it/net/gs1-barcode-encoding/create-barcode-gs1-in-c-and-export-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea barcode GS1 in C# ed esportalo come PNG

Se hai bisogno di **creare barcode GS1** in un'applicazione .NET, questa guida ti mostra esattamente come farlo. Vedrai una soluzione concisa che genera un'immagine PNG del barcode e esporta l'immagine del barcode su disco, il tutto con la classe Aspose.BarCode `BarcodeGenerator`.

Generare un barcode GS1 è una necessità comune per sistemi di inventario, spedizione e punto‑vendita. Alla fine di questo tutorial sarai in grado di scrivere un piccolo programma C# che crea un barcode MicroPDF417 conforme a GS1 e lo salva come file PNG ad alta qualità.

## Prerequisiti

* **.NET 6** (o qualsiasi versione .NET successiva) installata.
* **Visual Studio 2022** o qualsiasi IDE che supporti C#.
* Il pacchetto NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`) – fornisce l'API `BarcodeGenerator` utilizzata negli esempi.
* Familiarità di base con la sintassi C#.

> **Consiglio:** Usa l'edizione community gratuita di Aspose.BarCode durante gli esperimenti; la versione completa rimuove eventuali filigrane di valutazione.

## Passo 1 – Crea barcode GS1 con BarcodeGenerator

La prima cosa di cui hai bisogno è istanziare il `BarcodeGenerator` per il formato *MicroPDF417* e fornirgli una stringa di dati GS1. Gli Identificatori di Applicazione GS1 (AI) sono racchiusi tra parentesi, ad es. `(01)` per GTIN‑14 e `(21)` per un numero di serie.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// GS1 data: (01) – GTIN‑14, (21) – serial number
string gs1Data = "(01)12345678901234(21)ABC123";

// Initialise the generator for MicroPDF417 (GS1 compatible)
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);
```

**Perché è importante:**  
`EncodeTypes.MicroPdf417` tratta automaticamente l'input come dati GS1 quando la stringa contiene AI validi. Questo garantisce che il barcode generato sia conforme alla specifica GS1 senza configurazioni aggiuntive.

## Passo 2 – Imposta le dimensioni del barcode per una dimensione ottimale

La dimensione visiva di un barcode è controllata dalla sua **X‑dimension** (larghezza di un singolo modulo). Regolare `XDimension.Pixels` ti consente di perfezionare la dimensione finale dell'immagine mantenendo la leggibilità.

```csharp
// Set the module width to 2 pixels – a good balance for screen and print
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Come generare barcode PNG** – La X‑dimension non influisce sui dati codificati; cambia solo le dimensioni fisiche dell'immagine generata. Se ti serve un barcode più grande per stampa ad alta risoluzione, aumenta questo valore (ad es., `3` o `4`).

## Passo 3 – Genera barcode PNG ed esporta l'immagine del barcode

Ora puoi renderizzare il barcode e scriverlo in un file PNG. Il metodo `Save` accetta il percorso di destinazione e il formato immagine desiderato.

```csharp
// Define the output folder (ensure it exists)
string outputFolder = Path.Combine(Environment.CurrentDirectory, "output");
Directory.CreateDirectory(outputFolder);

// Export the barcode image as PNG
string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
generator.Save(pngPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode image saved to: {pngPath}");
```

**Cosa succede dietro le quinte:**  
`BarcodeGenerator.Save` rasterizza il barcode in una bitmap, applica la X‑dimension impostata in precedenza e codifica la bitmap come file PNG. Il file risultante può essere usato direttamente nelle pagine web, stampato su etichette o incorporato in PDF.

## Esempio completo di codice sorgente

Di seguito trovi un'applicazione console completa e autonoma che puoi copiare, incollare ed eseguire. Dimostra **come generare file barcode PNG**, **esportare l'immagine del barcode**, e include una gestione di base degli errori.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Gs1BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // 1️⃣ Initialise the barcode generator for GS1 MicroPDF417
                string gs1Data = "(01)12345678901234(21)ABC123";
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.MicroPdf417, gs1Data);

                // 2️⃣ Adjust X‑dimension to control the visual size
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // 3️⃣ Prepare output folder
                string outputFolder = Path.Combine(
                    Environment.CurrentDirectory, "output");
                Directory.CreateDirectory(outputFolder);

                // 4️⃣ Save the barcode as PNG (export barcode image)
                string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
                generator.Save(pngPath, BarCodeImageFormat.Png);

                Console.WriteLine($"✅ Barcode created and saved as PNG:");
                Console.WriteLine(pngPath);
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Error: {ex.Message}");
            }
        }
    }
}
```

### Output previsto

Quando esegui il programma, dovresti vedere:

```
✅ Barcode created and saved as PNG:
C:\Path\To\Your\App\output\GS1MicroPdf417.png
```

Aprendo il file PNG si visualizza un chiaro barcode **GS1 MicroPDF417** che codifica il GTIN‑14 `12345678901234` e il numero di serie `ABC123`. Scansionandolo con qualsiasi scanner compatibile GS1 verrà restituita la stringa di dati originale.

## Problemi comuni e migliori pratiche

| Problema | Perché succede | Come evitarlo |
|----------|----------------|---------------|
| **Formattazione AI errata** | Mancano le parentesi o l'ordine è sbagliato, rendendo il barcode non‑GS1. | Avvolgi sempre ogni AI tra parentesi, ad es., `(01)`. |
| **X‑dimension troppo piccola** | Il barcode diventa illeggibile su dispositivi a bassa risoluzione. | Mantieni `XDimension.Pixels` ≥ 2 per la maggior parte delle stampanti; aumentalo per output ad alta DPI. |
| **La cartella di output non esiste** | `Save` genera `DirectoryNotFoundException`. | Usa `Directory.CreateDirectory` prima di chiamare `Save`. |
| **Uso del tipo EncodeType sbagliato** | Alcuni tipi (es., `Code128`) non supportano dati GS1 nativamente. | Scegli `EncodeTypes.MicroPdf417` o qualsiasi tipo compatibile GS1. |
| **Riferimento NuGet mancante** | Errori di compilazione come `The type or namespace name 'Aspose' could not be found`. | Installa il pacchetto `Aspose.BarCode` tramite NuGet. |

## Estendere l'esempio

* **Formati immagine diversi** – Sostituisci `BarCodeImageFormat.Png` con `Jpeg`, `Gif` o `Bmp` se ti serve un altro formato.
* **Output ad alta risoluzione** – Imposta `generator.Parameters.ImageResolution.DpiX` e `DpiY` prima di salvare.
* **Incorporamento in PDF** – Usa `Aspose.Pdf` per inserire il PNG in una fattura o etichetta PDF.

## Conclusione

Ora sai come **creare barcode GS1** in C# usando Aspose.BarCode `BarcodeGenerator`, **generare barcode PNG** e **esportare l'immagine del barcode** nel file system. La guida ha coperto ogni passaggio—dall'inizializzare il generatore con dati GS1, regolare la X‑dimension, al salvare il file PNG finale—affrontando errori comuni e offrendo idee di estensione.

Sentiti libero di sperimentare con altri Identificatori di Applicazione GS1, diverse simbologie di barcode o immagini ad alta risoluzione. Quando padroneggerai queste basi, generare barcode conformi per inventario, spedizione o vendita al dettaglio diventerà una parte di routine del tuo toolbox .NET.

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Crea immagini barcode GS1 in C# – Come generare barcode C# rapidamente](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [Crea barcode PNG in C# – guida passo‑passo](/barcode/english/python-java/general/create-barcode-png-in-c-step-by-step-guide/)
- [Crea immagine barcode in C# – guida completa di programmazione](/barcode/english/python-java/general/create-barcode-image-in-c-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}