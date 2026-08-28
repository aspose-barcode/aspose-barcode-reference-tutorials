---
category: general
date: 2026-08-22
description: Tutorial sul generatore di codici a barre che mostra come generare un'immagine
  di codice a barre, convalidare l'input e gestire le eccezioni di codici a barre
  non validi in C# con Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator tutorial
- generate barcode image
- how to generate barcode
- invalid barcode example
- how to catch barcode
language: it
lastmod: 2026-08-22
og_description: Il tutorial sul generatore di codici a barre spiega come generare
  un'immagine di codice a barre, convalidare i dati e gestire gli errori del codice
  a barre in C# utilizzando Aspose.BarCode.
og_image_alt: barcode generator tutorial showing exception handling for invalid codes
og_title: Tutorial generatore di codici a barre – rileva codici non validi in C#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Barcode generator tutorial showing how to generate barcode image, validate
    input, and catch invalid barcode exceptions in C# with Aspose.BarCode.
  headline: 'Barcode generator tutorial: catch invalid codes in C#'
  type: TechArticle
tags:
- barcode
- C#
- exception‑handling
title: 'Tutorial sul generatore di codici a barre: rileva i codici non validi in C#'
url: /it/python-java/general/barcode-generator-tutorial-catch-invalid-codes-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tutorial generatore di codici a barre – gestire codici non validi in C#

Se stai cercando un **barcode generator tutorial** che non solo crea un'immagine di codice a barre ma protegge anche la tua applicazione da input errati, sei nel posto giusto. Questa guida ti accompagna attraverso l'intero flusso di lavoro: installazione della libreria, configurazione della validazione, generazione dell'immagine e gestione dell'eccezione quando il testo del codice è non valido.

Generare codici a barre è una necessità comune per sistemi di spedizione, inventario e point‑of‑sale. Tuttavia, inserire una stringa errata nel generatore può causare errori di runtime o produrre codici a barre illeggibili. Alla fine di questo tutorial comprenderai **how to generate barcode** immagini in modo sicuro e vedrai un pratico **invalid barcode example** con una corretta gestione degli errori.

## Di cosa avrai bisogno

- .NET 6.0 (o qualsiasi versione recente di .NET)
- Visual Studio 2022 o un altro IDE C#
- Il pacchetto NuGet **Aspose.BarCode for .NET** (`Install-Package Aspose.BarCode`)
- Familiarità di base con la gestione delle eccezioni in C#

## Passo 1: Installa e riferisci Aspose.BarCode

Apri il tuo progetto in Visual Studio, quindi esegui il comando NuGet:

```powershell
Install-Package Aspose.BarCode
```

Il pacchetto aggiunge lo spazio dei nomi `Aspose.BarCode`, che contiene la classe `BarcodeGenerator` utilizzata in tutto questo tutorial.

## Passo 2: Crea un generatore di codici a barre con un valore intenzionalmente errato

La prima parte del **invalid barcode example** mostra come istanziare un generatore per la simbologia *Planet* con un codice che viola la specifica.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 2.1: Planet symbology – the string is too long and contains illegal characters
            BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "1234567WRONG");
```

> **Perché è importante** – `EncodeTypes.Planet` si aspetta una stringa numerica di una lunghezza specifica. Fornire `"1234567WRONG"` attiva la logica di validazione all'interno della libreria.

## Passo 3: Abilita la validazione rigorosa affinché la libreria lanci un'eccezione

Per impostazione predefinita Aspose.BarCode tenta di correggere errori minori. Per uno scenario robusto di **how to catch barcode** dovresti attivare la validazione esplicita:

```csharp
            // Step 3.1: Tell the generator to throw when the code text is incorrect
            planetGenerator.Parameters.Barcode.ThrowExceptionWhenCodeTextIncorrect = true;
```

> **Spiegazione** – Impostare `ThrowExceptionWhenCodeTextIncorrect` a `true` costringe l'API a sollevare un `ArgumentException` se il testo fornito non rispetta le regole della simbologia. Questo è l'approccio consigliato quando è necessario garantire l'integrità dei dati.

## Passo 4: Genera l'immagine del codice a barre all'interno di un blocco try‑catch

Ora proviamo a generare l'immagine e a catturare l'errore previsto:

```csharp
            try
            {
                // Step 4.1: Attempt to create the barcode image
                planetGenerator.GenerateBarCodeImage();
                Console.WriteLine("Planet barcode generated successfully.");
            }
            catch (Exception ex)
            {
                // Step 4.2: Handle the validation error
                Console.WriteLine($"Planet error: {ex.Message}");
            }
```

**Output previsto**

```
Planet error: The code text is invalid for the selected symbology.
```

Il messaggio dell'eccezione conferma che la libreria ha identificato correttamente il problema.

## Passo 5: Ripeti il processo per un'altra simbologia (Postnet)

Per illustrare che lo stesso schema funziona per qualsiasi tipo di codice a barre, ripetiamo i passaggi per **Postnet**, un comune codice postale:

```csharp
            // Step 5.1: Create a Postnet generator with an invalid code
            BarcodeGenerator postnetGenerator = new BarcodeGenerator(EncodeTypes.Postnet, "1234567WRONG");
            postnetGenerator.Parameters.Barcode.ThrowExceptionWhenCodeTextIncorrect = true;

            try
            {
                // Step 5.2: Attempt to generate the Postnet image
                postnetGenerator.GenerateBarCodeImage();
                Console.WriteLine("Postnet barcode generated successfully.");
            }
            catch (Exception ex)
            {
                // Step 5.3: Capture the validation error
                Console.WriteLine($"Postnet error: {ex.Message}");
            }
        }
    }
}
```

**Output previsto**

```
Postnet error: The code text is invalid for the selected symbology.
```

Entrambi i blocchi dimostrano **how to generate barcode** immagini gestendo in modo sicuro input malformati.

## Passo 6: Salva un'immagine di codice a barre valida (opzionale)

Se in seguito fornisci una stringa corretta, puoi salvare l'immagine generata su un file:

```csharp
            // Valid example – generate and save a QR code
            BarcodeGenerator qrGenerator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
            qrGenerator.Save("qr.png", BarCodeImageFormat.Png);
            Console.WriteLine("QR code saved as qr.png");
```

> **Suggerimento:** Valida sempre l'input dell'utente prima di passarlo a `BarcodeGenerator`. Anche con `ThrowExceptionWhenCodeTextIncorrect` disabilitato, una stringa non valida può produrre codici a barre illeggibili.

## Errori comuni e come evitarli

| Problema | Perché accade | Soluzione |
|----------|----------------|-----------|
| Fornire caratteri alfabetici a simbologie solo numeriche (es. Planet, Postnet) | La libreria tronca o sostituisce silenziosamente i caratteri a meno che la validazione rigorosa non sia abilitata | Set `ThrowExceptionWhenCodeTextIncorrect = true` |
| Dimenticare di fare riferimento allo spazio dei nomi `Aspose.BarCode` | Errore di compilazione “BarcodeGenerator does not exist” | Add `using Aspose.BarCode.Generation;` at the top of the file |
| Utilizzare un pacchetto NuGet obsoleto | Potrebbero mancare nuove simbologie o correzioni di bug | Update the package regularly (`dotnet add package Aspose.BarCode --version x.x.x`) |

## Esempio completo, eseguibile

Di seguito trovi il programma completo che puoi copiare, incollare ed eseguire direttamente:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Planet – invalid code
            BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "1234567WRONG");
            planetGenerator.Parameters.Barcode.ThrowExceptionWhenCodeTextIncorrect = true;

            try
            {
                planetGenerator.GenerateBarCodeImage();
                Console.WriteLine("Planet barcode generated successfully.");
            }
            catch (Exception ex)
            {
                Console.WriteLine($"Planet error: {ex.Message}");
            }

            // Postnet – invalid code
            BarcodeGenerator postnetGenerator = new BarcodeGenerator(EncodeTypes.Postnet, "1234567WRONG");
            postnetGenerator.Parameters.Barcode.ThrowExceptionWhenCodeTextIncorrect = true;

            try
            {
                postnetGenerator.GenerateBarCodeImage();
                Console.WriteLine("Postnet barcode generated successfully.");
            }
            catch (Exception ex)
            {
                Console.WriteLine($"Postnet error: {ex.Message}");
            }

            // Valid QR code – optional saving
            BarcodeGenerator qrGenerator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
            qrGenerator.Save("qr.png", BarCodeImageFormat.Png);
            Console.WriteLine("QR code saved as qr.png");
        }
    }
}
```

Eseguendo questo programma vengono stampati due messaggi di errore per i codici a barre non validi e viene creato un file `qr.png` per il QR code valido.

## Conclusione

Questo **barcode generator tutorial** ti ha mostrato come **generate barcode image** oggetti, applicare una validazione rigorosa e **how to catch barcode**‑related eccezioni in C#. Abilitando `ThrowExceptionWhenCodeTextIncorrect`, trasformi input malformati in un errore gestibile invece di un fallimento silenzioso.

Da qui puoi:

- Esplorare altre simbologie come Code128, EAN13 o DataMatrix.
- Personalizzare colori, dimensioni e margini tramite `GeneratorParameters`.
- Integrare la generazione di codici a barre in API ASP.NET Core o applicazioni Windows Forms.

Ricorda, validare l'input **prima** di chiamare `GenerateBarCodeImage` è il modo più sicuro per mantenere il tuo sistema affidabile e le tue scansioni senza errori. Buon coding!

## Cosa dovresti imparare dopo?

I tutorial seguenti coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [How to Generate Barcode Image with Supplemental Space Customization using Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}