---
category: general
date: 2026-09-10
description: Crea rapidamente un'immagine di codice a barre in C# usando un esempio
  di generatore di codici a barre in C# che mostra come impostare le dimensioni e
  salvare file PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image c#
- barcode generator example c#
language: it
lastmod: 2026-09-10
og_description: Crea un'immagine di codice a barre in C# con un esempio conciso di
  generatore di codici a barre C#. Impara a configurare dimensioni, altezza ed esportare
  file PNG in pochi minuti.
og_image_alt: Screenshot of a barcode image created with C# code
og_title: Crea immagine barcode C# – esempio di generatore passo‑passo
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create barcode image C# quickly using a barcode generator example C#
    that shows how to set dimensions and save PNG files.
  headline: Create barcode image C# with barcode generator example
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: Crea immagine di codice a barre in C# con esempio di generatore di codici a
  barre
url: /it/python-java/general/create-barcode-image-c-with-barcode-generator-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea immagine barcode C# con esempio di generatore di barcode

Se hai bisogno di **create barcode image C#** per l'etichettatura dei prodotti, il tracciamento dell'inventario o la scansione mobile, questa guida mostra una soluzione completa. Vedrai un **barcode generator example C#** che configura la larghezza del modulo, l'altezza delle barre e salva file PNG in poche righe di codice.

Il tutorial copre tutto, dall'installazione della libreria necessaria all'esecuzione di un programma console pronto da compilare. Alla fine, avrai due file PNG di barcode — uno con un'altezza della barra di 30 pixel e un altro con un'altezza della barra di 60 pixel — pronti per l'uso in qualsiasi applicazione .NET.

## Prerequisiti

* .NET 6.0 SDK o versioni successive installate  
* Un ambiente di sviluppo come Visual Studio 2022 o VS Code  
* Il pacchetto NuGet **Aspose.BarCode** (il codice utilizza `BarcodeGenerator` di questa libreria)  

Puoi aggiungere il pacchetto con il seguente comando CLI:

```bash
dotnet add package Aspose.BarCode
```

## Passo 1: Configura il progetto console

Crea un nuovo progetto console e aggiungi il riferimento alla libreria barcode.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Il comando crea un file `Program.cs` dove inserirai il codice del **barcode generator example C#**.

## Passo 2: Scrivi il programma completo di generazione del barcode

Sostituisci il contenuto di `Program.cs` con l'esempio completo e eseguibile qui sotto. Il programma dimostra come **create barcode image C#** con dimensioni personalizzate e come salvare il risultato come file PNG.

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
            // 1️⃣ Create a DataBar Omnidirectional barcode generator with the desired data.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set the X‑dimension (module width) to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Configure a 30‑pixel bar height and save the first image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            SaveBarcode(generator, "DatabarBarHeight30Pixels.png");

            // 4️⃣ Change the bar height to 60 pixels and save the second image.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            SaveBarcode(generator, "DatabarBarHeight60Pixels.png");

            Console.WriteLine("Barcode images have been saved to the output folder.");
        }

        /// <summary>
        /// Saves the current barcode image as a PNG file.
        /// </summary>
        /// <param name="generator">The configured BarcodeGenerator instance.</param>
        /// <param name="fileName">The file name for the PNG image.</param>
        private static void SaveBarcode(BarcodeGenerator generator, string fileName)
        {
            // Ensure the output directory exists.
            string outputPath = System.IO.Path.Combine(
                AppDomain.CurrentDomain.BaseDirectory, "output");
            System.IO.Directory.CreateDirectory(outputPath);

            // Combine the directory and file name.
            string fullPath = System.IO.Path.Combine(outputPath, fileName);

            // Save the barcode as a PNG image.
            generator.Save(fullPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Perché ogni riga è importante

* **EncodeTypes.DatabarOmniDirectional** – seleziona la simbologia DataBar Omnidirectional, che codifica dati numerici ed è ampiamente usata nel retail.  
* **XDimension.Pixels = 2** – imposta la larghezza del modulo; un valore più piccolo produce un barcode più compatto.  
* **BarHeight.Pixels** – controlla l'altezza visiva delle barre. Modificando questo valore puoi creare barcode che si adattano a diverse dimensioni di etichetta.  
* **Save method** – scrive il barcode in un file PNG, un formato che preserva i bordi nitidi e funziona con la maggior parte delle librerie di imaging.

## Passo 3: Compila ed esegui il programma

Esegui il seguente comando dalla cartella del progetto:

```bash
dotnet run
```

Quando il programma termina, vedrai due file PNG nella sottocartella `output`:

* `DatabarBarHeight30Pixels.png` – altezza barra 30 pixel  
* `DatabarBarHeight60Pixels.png` – altezza barra 60 pixel  

Entrambe le immagini contengono gli stessi dati codificati ma differiscono per altezza visiva, illustrando come il **barcode generator example C#** possa essere adattato a vari requisiti di etichettatura.

## Passo 4: Verifica i barcode generati

Apri i file PNG con qualsiasi visualizzatore di immagini. Dovresti vedere un barcode DataBar chiaro e ad alto contrasto. Per confermare che i barcode siano leggibili, puoi usare un'app scanner mobile (ad es., app basate su ZXing) o una libreria desktop come **Aspose.BarCode** in modalità decodifica:

```csharp
var reader = new BarCodeReader(fullPath, DecodeType.DatabarOmniDirectional);
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    Console.WriteLine($"Decoded value: {result.CodeText}");
}
```

Se l'output corrisponde a `(01)12345678901231`, la generazione è riuscita.

## Variazioni comuni e casi limite

| Situazione | Regolazione | Snippet di codice |
|-----------|------------|--------------|
| **Different symbology** (ad es., QR, Code128) | Modifica il valore di `EncodeTypes` | `new BarcodeGenerator(EncodeTypes.QR, "Hello World")` |
| **Custom image format** (JPEG, BMP) | Usa un enum `BarCodeImageFormat` diverso | `generator.Save(path, BarCodeImageFormat.Jpeg)` |
| **Dynamic data** (input utente) | Sostituisci la stringa hard‑coded con una variabile | `string data = Console.ReadLine(); var generator = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data);` |
| **Invalid data length** | Gestisci l'`ArgumentException` lanciata dal generatore | ```csharp try { ... } catch (ArgumentException ex) { Console.WriteLine(ex.Message); }``` |

Consiglio professionale: valida sempre la lunghezza dell'input per la simbologia selezionata; Aspose.BarCode lancia un'eccezione se i dati non rispettano la specifica.

## Lista di controllo per la risoluzione dei problemi

* **Directory not found** – L'helper `SaveBarcode` crea automaticamente la cartella `output`, ma assicurati che l'applicazione abbia i permessi di scrittura.  
* **Unexpected image size** – Verifica che `XDimension.Pixels` e `BarHeight.Pixels` siano impostati prima di chiamare `Save`. Modificare questi valori dopo il salvataggio non influisce sui file già scritti.  
* **Unreadable barcode** – Assicurati che la stringa codificata segua il formato GS1 quando usi simbologie DataBar. Parentesi mancanti o Application Identifier errati causano errori di decodifica.

## Conclusione

Ora sai come **create barcode image C#** usando un pratico **barcode generator example C#**. Il programma completo imposta la larghezza del modulo, regola l'altezza delle barre e salva file PNG con codice minimo. Da qui puoi esplorare funzionalità aggiuntive come la personalizzazione del colore, l'esportazione PDF multi‑pagina o la generazione in tempo reale in API web ASP.NET Core.

**Prossimi passi**

* Sperimenta altre simbologie (`EncodeTypes.Code128`, `EncodeTypes.QR`) per ampliare le tue opzioni di scansione.  
* Integra il generatore in un servizio web che restituisce immagini barcode su richiesta.  
* Combina il barcode con i metadati del prodotto in una fattura PDF usando Aspose.PDF.

Buon coding e goditi la flessibilità che C# offre per la creazione di immagini barcode!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Esempio di Generatore di Barcode in C# – Imposta Colonne, Righe & Esporta Immagine](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Crea immagine barcode C# – Esempio GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Esempio di Generatore di Barcode – Costruisci Immagine DataBar in C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}