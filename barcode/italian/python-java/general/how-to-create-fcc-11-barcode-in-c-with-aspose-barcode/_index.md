---
category: general
date: 2026-08-22
description: Crea un codice a barre FCC 11 in C# usando Aspose.BarCode. Impara il
  codice passo‑passo, configura le dimensioni e genera immagini PNG per Australia
  Post.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create fcc 11 barcode
- Australia Post barcode
- Aspose.BarCode C#
- FCC 59 barcode
- FCC 62 barcode
- N‑Table encoding
- C‑Table encoding
language: it
lastmod: 2026-08-22
og_description: Crea il codice a barre FCC 11 in C# con Aspose.BarCode. Segui questo
  conciso tutorial per generare codici a barre PNG per Australia Post, incluse le
  varianti FCC 59 e FCC 62.
og_image_alt: Screenshot showing a generated FCC 11 barcode image
og_title: Crea codice a barre FCC 11 in C# – guida completa di Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  headline: How to create FCC 11 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  name: How to create FCC 11 barcode in C# with Aspose.BarCode
  steps:
  - name: 4.1 FCC 59 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)'
  - name: 4.2 FCC 62 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)'
  - name: 4.3 FCC 62 with C‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix'
  - name: 4.4 FCC 62 with Other encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567321032103210"); // Long payload for "Other" table'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- AustraliaPost
title: Come creare un codice a barre FCC 11 in C# con Aspose.BarCode
url: /it/python-java/general/how-to-create-fcc-11-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un codice a barre FCC 11 in C# con Aspose.BarCode

Se hai bisogno di **creare un codice a barre FCC 11** in un'applicazione .NET, questa guida ti mostra il codice esatto necessario. Vedrai come configurare le dimensioni del codice a barre, scegliere la tabella di codifica corretta e salvare il risultato come file PNG.

Generare codici a barre Australia Post è una necessità comune per la logistica, i sistemi di spedizione e il tracciamento dell'inventario. Questo tutorial copre il formato FCC 11 e dimostra anche come produrre codici a barre FCC 59 e FCC 62 con diverse tabelle di codifica, così da poter riutilizzare lo stesso schema per altri servizi postali.

## Cosa ti servirà

Prima di iniziare, assicurati di avere:

* .NET 6.0 SDK o versioni successive installate  
* Visual Studio 2022 (o qualsiasi IDE compatibile con C#)  
* Una licenza valida per **Aspose.BarCode for .NET** – l'edizione community è sufficiente per la valutazione  
* Permessi di scrittura su una cartella dove verranno salvati i file PNG  

Questi prerequisiti garantiscono che il codice venga compilato ed eseguito senza configurazioni aggiuntive.

## Passo 1: Installa il pacchetto NuGet Aspose.BarCode

Apri un terminale nella cartella del progetto ed esegui:

```bash
dotnet add package Aspose.BarCode
```

Il comando aggiunge l'ultima versione stabile della libreria al tuo file di progetto. Il pacchetto contiene la classe `BarcodeGenerator` utilizzata in tutto il tutorial.

## Passo 2: Definisci la cartella di output

Crea una cartella dove verranno memorizzate le immagini generate. Il percorso può essere assoluto o relativo all'eseguibile.

```csharp
// Step 2: Define the output folder
string outputPath = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputPath);
```

`Directory.CreateDirectory` garantisce che la cartella esista, evitando errori a runtime quando il metodo `Save` scrive il file.

## Passo 3: Genera il codice a barre FCC 11

Il formato FCC 11 è la codifica predefinita per i codici a barre postali di Australia Post. Il codice seguente crea un codice a barre che codifica la stringa numerica `1101234567`.

```csharp
// Step 3: Create a BarcodeGenerator for FCC 11
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,      // Use the Australia Post symbology
    "1101234567");                  // Data for FCC 11

// Configure visual appearance
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;   // Width of a single module
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50; // Height of the barcode

// Save as PNG
string fcc11Path = Path.Combine(outputPath, "PostalAustraliaPostFCC11.png");
barcodeGenerator.Save(fcc11Path, BarCodeImageFormat.Png);
```

**Perché funziona:**  
* `EncodeTypes.AustraliaPost` indica alla libreria di applicare le regole di codifica di Australia Post.  
* La stringa di dati `1101234567` segue la specifica FCC 11: i primi due cifre (`11`) identificano il formato, seguite da un riferimento cliente a 7 cifre.  
* `XDimension` e `BarHeight` controllano la dimensione del codice a barre stampato, importante per la leggibilità da parte degli scanner.  

Dopo aver eseguito il programma, troverai `PostalAustraliaPostFCC11.png` nella cartella `Barcodes`. L'immagine appare così:

![create fcc 11 barcode example](https://example.com/fcc11.png "FCC 11 barcode generated by Aspose.BarCode")

## Passo 4: Crea codici a barre Australia Post aggiuntivi (opzionale)

Mentre l'obiettivo principale è **creare un codice a barre FCC 11**, spesso è necessario generare codici FCC 59 o FCC 62 per classi di posta diverse. Il codice qui sotto riutilizza la stessa istanza di `BarcodeGenerator`, modificando solo la stringa di dati e la tabella di codifica opzionale.

### 4.1 FCC 59 con codifica N‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;

// Use N‑Table for customer information interpretation
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc59Path = Path.Combine(outputPath, "PostalAustraliaPostFCC59NTable.png");
barcodeGenerator.Save(fcc59Path, BarCodeImageFormat.Png);
```

### 4.2 FCC 62 con codifica N‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc62NPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62NTable.png");
barcodeGenerator.Save(fcc62NPath, BarCodeImageFormat.Png);
```

### 4.3 FCC 62 con codifica C‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.CTable;

string fcc62CPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62CTable.png");
barcodeGenerator.Save(fcc62CPath, BarCodeImageFormat.Png);
```

### 4.4 FCC 62 con altra codifica

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567321032103210"); // Long payload for "Other" table

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.Other;

string fcc62OtherPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62OtherTable.png");
barcodeGenerator.Save(fcc62OtherPath, BarCodeImageFormat.Png);
```

Tutte e quattro le immagini vengono salvate affiancate nella stessa cartella, facilitando il confronto delle differenze visive.

## Passo 5: Comprendi le tabelle di codifica

Australia Post definisce tre tabelle di codifica:

* **N‑Table** – interpreta informazioni cliente numeriche. Usala quando il payload contiene solo cifre.  
* **C‑Table** – supporta caratteri alfanumerici, utile per numeri di riferimento che includono lettere.  
* **Other** – un fallback per formati di dati personalizzati o estesi.

Scegliere la tabella corretta assicura che lo scanner decodifichi le informazioni esattamente come previsto. Se ometti la proprietà `AustralianPostEncodingTable`, la libreria utilizza per impostazione predefinita la N‑Table, il che può troncare caratteri non numerici.

## Suggerimenti, casi limite e problemi comuni

| Situazione | Approccio consigliato |
|------------|-----------------------|
| La lunghezza della stringa di dati è più corta del necessario | Aggiungi zeri iniziali alla parte numerica per soddisfare la specifica FCC. |
| Il codice a barre appare sfocato quando stampato | Aumenta `XDimension` a 5 o 6 pixel e verifica le impostazioni DPI della stampante. |
| Lo scanner restituisce “formato non valido” | Verifica che la tabella di codifica corretta (N‑Table, C‑Table, Other) corrisponda al payload dei dati. |
| Esecuzione su Linux senza interfaccia grafica | Assicurati che il pacchetto `System.Drawing.Common` sia referenziato, oppure usa il metodo `Save` con `BarCodeImageFormat.Png` che non richiede un contesto grafico. |
| Necessità di un formato immagine diverso | Sostituisci `BarCodeImageFormat.Png` con `BarCodeImageFormat.Jpeg` o `BarCodeImageFormat.Tiff` secondo necessità. |

Questi consigli pratici derivano da implementazioni reali di soluzioni di codici a barre postali.

## Esempio completo eseguibile

Di seguito trovi un programma autonomo che puoi copiare in un nuovo progetto console (`dotnet new console`) ed eseguire senza modifiche.



## Cosa dovresti imparare dopo?

I seguenti tutorial trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come generare barcode java – Barcode Australia Post con Aspose](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)
- [Crea codifica Databar unidimensionale GS1 con Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Come creare zona silenziosa barcode .NET per Code 16K usando Aspose.BarCode](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}