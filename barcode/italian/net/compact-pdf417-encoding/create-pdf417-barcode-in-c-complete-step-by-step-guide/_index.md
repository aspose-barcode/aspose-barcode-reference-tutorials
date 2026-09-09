---
category: general
date: 2026-07-18
description: Crea rapidamente codici a barre PDF417 con C#. Scopri come generare il
  codice a barre, impostare i parametri e salvare i file immagine – include la gestione
  AI 10.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate barcode
- how to set parameters
- how to save image
- barcode ai 10
language: it
lastmod: 2026-07-18
og_description: Crea un codice a barre PDF417 in C# con una guida completa. Scopri
  come generare il codice a barre, regolare le impostazioni e salvare le immagini
  gestendo AI 10.
og_image_alt: Screenshot illustrating create pdf417 barcode code in C#
og_title: Crea codice a barre PDF417 in C# – Esempio completo, veloce e flessibile
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create PDF417 barcode quickly with C#. Learn how to generate barcode,
    set parameters, and save image files – includes AI 10 handling.
  headline: Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: Create PDF417 barcode quickly with C#. Learn how to generate barcode,
    set parameters, and save image files – includes AI 10 handling.
  name: Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  steps:
  - name: '**X‑dimension** – controls the width of the smallest bar (in pixels)'
    text: '**X‑dimension** – controls the width of the smallest bar (in pixels)'
  - name: '**Column count** – influences the overall shape; fewer columns = taller
      barcode'
    text: '**Column count** – influences the overall shape; fewer columns = taller
      barcode'
  - name: '**IsLinked** – enables the optional link module that ties the barcode to
      the data string'
    text: '**IsLinked** – enables the optional link module that ties the barcode to
      the data string'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspnet
- barcode-generation
title: Crea codice a barre PDF417 in C# – Guida completa passo passo
url: /it/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Creare un barcode PDF417 in C# – Guida completa passo‑paso

Hai mai dovuto **creare barcode pdf417** ma non sapevi quale libreria o impostazione scegliere? Non sei solo: molti sviluppatori si trovano di fronte a questo ostacolo quando si avvicinano per la prima volta a GS1‑Micro‑PDF417. La buona notizia è che, con poche righe di C#, puoi generare un barcode perfettamente formattato, modificarne l’aspetto e salvare l’immagine direttamente su disco.

In questo tutorial vedremo **come generare barcode** usando la libreria Aspose.BarCode, mostreremo **come impostare i parametri** come X‑dimension e numero di colonne, e dimostreremo **come salvare l’immagine** per le varianti AI 10 e AI 21. Alla fine avrai uno snippet riutilizzabile da inserire in qualsiasi progetto .NET.

## Prerequisiti

Prima di iniziare, assicurati di avere:

- .NET 6+ o .NET Framework 4.7.2 (qualsiasi runtime recente va bene)
- Visual Studio 2022 o il tuo editor C# preferito
- Il pacchetto NuGet **Aspose.BarCode for .NET** (`Install-Package Aspose.BarCode`)
- Una cartella scrivibile su disco dove verranno salvati i file PNG

Tutto qui—nessuno strumento aggiuntivo, nessuna configurazione complessa. Pronto? Iniziamo.

## Passo 1: Creare barcode PDF417 con formato GS1‑Micro

La prima cosa che facciamo è **creare barcode pdf417** e fornire i dati AI iniziali. In GS1‑Micro‑PDF417 l’AI 10 (numero di lotto) è spesso il punto di partenza, quindi lo codifichiamo subito.

```csharp
using Aspose.BarCode.Generation;

// Define where the PNGs will be saved
string outputDir = @"C:\Barcodes\";

// Instantiate the generator for GS1‑Micro‑PDF417
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.GS1MicroPdf417,
    "(10)ABCD12345(240)ABCD");   // AI 10 + additional data
```

> **Perché è importante:** `EncodeTypes.GS1MicroPdf417` indica alla libreria di seguire la specifica GS1‑Micro, che aggiunge automaticamente le parentesi dell’AI. Se ometti questo, otterrai un PDF417 generico che potrebbe non essere leggibile in ambienti retail.

## Passo 2: Come impostare i parametri per il barcode

Ora che abbiamo un’istanza di barcode, dobbiamo affinare le sue caratteristiche visive. È qui che entra in gioco **come impostare i parametri**. Regoleremo tre impostazioni comuni:

1. **X‑dimension** – controlla la larghezza della barra più piccola (in pixel)
2. **Column count** – influenza la forma complessiva; meno colonne = barcode più alto
3. **IsLinked** – abilita il modulo di collegamento opzionale che lega il barcode alla stringa di dati

```csharp
// X‑dimension: 2 pixels per module (good balance of size vs readability)
barcode.Parameters.Barcode.XDimension.Pixels = 2;

// Columns: 3 columns makes the barcode compact yet readable
barcode.Parameters.Barcode.Pdf417.Columns = 3;

// Enable linking (adds a special pattern that some scanners use)
barcode.Parameters.Barcode.Pdf417.IsLinked = true;
```

> **Suggerimento:** Se il target è la scansione mobile, aumenta la X‑dimension a 3‑4 pixel; i moduli più grandi sopravvivono meglio alle fotocamere a bassa risoluzione.

## Passo 3: Come salvare l’immagine – Prima versione (AI 10)

Con il generatore configurato, possiamo finalmente **come salvare l’immagine**. Il metodo `Save` scrive il barcode su file nel formato specificato. Qui usiamo PNG perché conserva bordi nitidi senza artefatti di compressione.

```csharp
// Save the barcode that encodes AI 10
barcode.Save($"{outputDir}GS1MicroPdf417_AI10.png", BarCodeImageFormat.Png);
```

A questo punto dovresti vedere un file chiamato `GS1MicroPdf417_AI10.png` nella tua `outputDir`. Aprilo con qualsiasi visualizzatore di immagini: vedrai un PDF417 pulito, ad alto contrasto, pronto per la stampa.

## Passo 4: Passare a un AI diverso (AI 21) e salvare di nuovo

Spesso è necessario codificare un identificatore di applicazione diverso, ad esempio AI 21 (numero di serie). Cambiare la proprietà `CodeText` è tutto ciò che serve. Questo dimostra la gestione di **barcode ai 10** rispetto a **barcode ai 21** in un unico passaggio.

```csharp
// Change the encoded data – now using AI 21
barcode.CodeText = "(21)ABCD12345(240)ABCD";

// Save the new variant
barcode.Save($"{outputDir}GS1MicroPdf417_AI21.png", BarCodeImageFormat.Png);
```

> **E se hai bisogno di più AI?** Basta concatenarli nella stessa stringa, ad esempio `"(10)ABCD(21)12345(240)XYZ"`. La libreria interpreta automaticamente le parentesi.

## Esempio completo funzionante

Mettendo tutto insieme, ecco un programma autonomo che puoi copiare‑incollare in una console app:

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Output folder – change to suit your environment
        string outputDir = @"C:\Barcodes\";

        // 2️⃣ Create generator with initial AI 10 data
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.GS1MicroPdf417,
            "(10)ABCD12345(240)ABCD");

        // 3️⃣ Set visual parameters
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // how to set parameters
        barcode.Parameters.Barcode.Pdf417.Columns = 3;
        barcode.Parameters.Barcode.Pdf417.IsLinked = true;

        // 4️⃣ Save first image (AI 10)
        barcode.Save($"{outputDir}GS1MicroPdf417_AI10.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved AI 10 barcode.");

        // 5️⃣ Switch to AI 21 and save second image
        barcode.CodeText = "(21)ABCD12345(240)ABCD";
        barcode.Save($"{outputDir}GS1MicroPdf417_AI21.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved AI 21 barcode.");
    }
}
```

**Output previsto:** Due file PNG compaiono in `C:\Barcodes\`—`GS1MicroPdf417_AI10.png` e `GS1MicroPdf417_AI21.png`. Entrambi contengono un PDF417 leggibile; il primo codifica AI 10, il secondo AI 21.

## Problemi comuni e come evitarli

- **Permessi sulla cartella mancanti:** Se `Save` genera un `UnauthorizedAccessException`, verifica che il percorso esista e che l’app abbia i diritti di scrittura.
- **Formattazione AI errata:** Dimenticare le parentesi (`(10)`) farà sì che il barcode venga trattato come dato semplice, rompendo la validazione GS1.
- **X‑dimension troppo piccola:** Barre più sottili di 1 pixel possono scomparire quando l’immagine viene ridimensionata. Mantieni almeno 2 pixel per la visualizzazione su schermo.

## Prossimi passi e argomenti correlati

Ora che sai **come generare barcode**, **come impostare i parametri** e **come salvare l’immagine**, potresti voler approfondire:

- Aggiungere **testo leggibile dall’uomo** sotto il barcode (`barcode.Parameters.Barcode.CodeTextLocation = CodeLocation.BelowBarcode`)
- Esportare in **PDF** invece di PNG (`BarCodeImageFormat.Pdf`)
- Integrare la generazione di barcode in una **API ASP.NET Core** per la creazione di immagini on‑the‑fly

Ognuno di questi argomenti si basa direttamente sulle fondamenta illustrate in questa guida.

---

### Riepilogo rapido

- **Creare barcode pdf417** usando `BarcodeGenerator` con `EncodeTypes.GS1MicroPdf417`
- **Come impostare i parametri** come X‑dimension, colonne e linking
- **Come salvare l’immagine** come PNG per le varianti AI 10 e AI 21
- Gestito **barcode ai 10** e scambiato a **barcode ai 21** con una singola modifica della proprietà

Provalo, modifica le impostazioni e avrai un motore di barcode robusto pronto per la produzione. Hai domande o vuoi approfondire? Lascia un commento qui sotto—buona programmazione!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi con spiegazioni passo‑paso per aiutarti a padroneggiare funzionalità aggiuntive dell’API e a esplorare approcci alternativi nei tuoi progetti.

- [Come creare barcode – PDF417 compatto con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Come creare zona silenziosa per barcode ITF-14 usando Aspose.BarCode per .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Come creare barcode Aztec con correzione d’errore in .NET](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}