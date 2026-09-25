---
category: general
date: 2026-08-22
description: Scopri come generare il codice a barre PDF417 in C# con Aspose.BarCode,
  impostare le dimensioni del codice a barre, regolare le colonne e abilitare la modalità
  compatta.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- set barcode size
language: it
lastmod: 2026-08-22
og_description: Genera codice a barre PDF417 in C# con Aspose.BarCode. Questa guida
  mostra come impostare le dimensioni del codice a barre, controllare le colonne e
  abilitare la modalità compatta per un'immagine più piccola.
og_image_alt: Screenshot of a generated PDF417 barcode in C# showing compact mode
og_title: Genera codice a barre PDF417 in C# – imposta dimensioni, colonne e modalità
  compatta
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to generate PDF417 barcode in C# with Aspose.BarCode, set
    barcode size, adjust columns, and enable compact mode.
  headline: How to generate PDF417 barcode in C# and set barcode size
  type: TechArticle
tags:
- pdf417
- barcode
- csharp
title: Come generare un codice a barre PDF417 in C# e impostare la dimensione del
  codice a barre
url: /it/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come generare PDF417 barcode in C# e impostare le dimensioni del barcode

Se hai bisogno di **generare un codice a barre PDF417** in un'applicazione .NET, questa guida ti accompagna passo passo attraverso l'intero processo. Vedrai esattamente **come generare PDF417** con Aspose.BarCode, regolare le **dimensioni del codice a barre**, e produrre un PNG compatto che può essere incorporato in report o app mobili.

Creare un codice a barre non richiede un editor grafico separato. Alla fine di questo tutorial avrai un metodo C# completamente funzionante che produce un'immagine PDF417 con le dimensioni esatte di cui hai bisogno, pronta per l'elaborazione successiva.

## Cosa imparerai

* Installa e aggiungi riferimento alla libreria Aspose.BarCode.
* Crea un generatore di codice a barre PDF417 e specifica il testo da codificare.
* **Imposta le dimensioni del codice a barre** configurando la X‑dimension e il numero di colonne.
* Abilita la modalità compatta (troncata) per ridurre il simbolo.
* Salva il risultato come file PNG.
* Risolvi i problemi comuni come codici illeggibili e immagini troppo grandi.

### Prerequisiti

* .NET 6.0 o successivo (l'API funziona anche con .NET Framework 4.6+).
* Familiarità di base con C# e Visual Studio (o qualsiasi IDE C#).
* Una licenza valida di Aspose.BarCode (la valutazione gratuita è sufficiente per i test).

> **Consiglio professionale:** se prevedi di generare molti codici a barre in un ciclo, riutilizza una singola istanza di `BarcodeGenerator` e modifica solo la proprietà `CodeText`. Questo riduce le allocazioni di memoria.

## Genera PDF417 barcode con Aspose.BarCode

Il primo passo è istanziare il `BarcodeGenerator` per la simbologia PDF417. Questo oggetto è il punto di ingresso per tutte le operazioni sui codici a barre.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.Pdf417,          // Symbology
    "Sample text for PDF417");   // Data to encode
```

*Perché è importante*: `EncodeTypes.Pdf417` indica alla libreria di utilizzare lo standard PDF417, che supporta grandi volumi di dati e correzione degli errori. Il costruttore accetta anche i dati da codificare, eliminando la necessità di un'assegnazione separata di `CodeText` in seguito.

## Imposta le dimensioni del barcode e il conteggio delle colonne

I simboli PDF417 sono composti da righe e colonne di piccoli moduli rettangolari. Controllare la larghezza del modulo (X‑dimension) e il numero di colonne consente di regolare finemente le dimensioni complessive.

```csharp
// Step 2: Adjust the module size (X‑dimension) – 2 pixels per module
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Define the number of columns for the PDF417 code
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

*Spiegazione*:  
* **X‑dimension** (`Pixels`) determina quanto è largo ogni modulo. Valori più piccoli producono un codice a barre più compatto, mentre valori più grandi aumentano la leggibilità su scanner a bassa risoluzione.  
* **Columns** controlla il layout orizzontale. Meno colonne rendono il codice a barre più alto; più colonne lo rendono più largo. Regola questi due parametri insieme per ottenere le **dimensioni del codice a barre** esatte di cui hai bisogno.

## Abilita la modalità compatta per un barcode più piccolo

PDF417 include una modalità “compact” (o troncata) che rimuove il padding non necessario e riduce l'ingombro complessivo. È particolarmente utile quando lo spazio sullo schermo è limitato.

```csharp
// Step 4: Enable compact mode to truncate the barcode data
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

*Perché abilitare la troncatura?*  
Quando `Truncate` è `true`, il generatore omette il pattern di stop e alcune parole di correzione degli errori che non sono necessarie per la maggior parte degli scenari di scansione. L'immagine risultante è circa il 15‑20 % più piccola senza compromettere l'integrità dei dati per i casi d'uso tipici.

## Salva il barcode come immagine PNG

Dopo aver configurato dimensioni e modalità, scrivi il codice a barre su disco. PNG è senza perdita, garantendo che i bordi dei moduli rimangano nitidi.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save(
    "YOUR_DIRECTORY/CompactPdf417.png",
    BarCodeImageFormat.Png);
```

Il file `CompactPdf417.png` conterrà un simbolo PDF417 nitido che corrisponde alle dimensioni impostate nei passaggi precedenti.

### Output previsto

Aprendo il PNG salvato dovrebbe comparire un codice a barre PDF417 orientato verticalmente, composto da tre colonne, ciascun modulo largo 2 px, e una dimensione totale di circa **120 × 240 px** (larghezza × altezza). La scansione dell'immagine con qualsiasi lettore PDF417 standard restituisce il testo originale “Sample text for PDF417”.

## Problemi comuni e come evitarli

| Sintomo | Causa probabile | Correzione |
|---------|----------------|------------|
| Il codice a barre è illeggibile | X‑dimension troppo piccola per lo scanner | Aumenta `XDimension.Pixels` a 3 o 4 |
| L'immagine è troppo larga per l'interfaccia | Sono state impostate troppe colonne | Riduci `Pdf417.Columns` o abilita `Truncate` |
| Eccezione `ArgumentOutOfRangeException` | Conteggio colonne negativo o zero | Assicurati che `Columns` sia un intero positivo (minimo 1) |
| Il file PNG è vuoto | Il percorso di output non esiste o manca il permesso di scrittura | Verifica che la directory esista e che l'app abbia i diritti di scrittura |

> **Consiglio professionale:** usa `barcodeGenerator.ValidateParameters()` prima di chiamare `Save()` per rilevare gli errori di configurazione in anticipo.

## Esempio completo e eseguibile

Di seguito trovi un programma console autonomo che incorpora tutti i passaggi descritti sopra. Copialo in un nuovo progetto C#, ripristina il pacchetto NuGet Aspose.BarCode e eseguilo per vedere il risultato.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create the generator with the data to encode
            var generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample text for PDF417");

            // Set module width (X‑dimension) – 2 px per module
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Choose a small number of columns to keep the barcode compact
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable truncation for a smaller image
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Optional: validate parameters before saving
            generator.ValidateParameters();

            // Save as PNG
            const string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

**Eseguendo il programma** verrà generato `CompactPdf417.png` nella directory di lavoro dell'eseguibile. Scansiona l'immagine con un'app mobile (ad es., “Barcode Scanner”) per verificare che il testo codificato corrisponda alla stringa di origine.

## Prossimi passi e argomenti correlati

* **Aumenta il livello di correzione degli errori** – regola `Pdf417.ErrorLevel` per ambienti con scansioni rumorose.  
* **Cambia orientamento** – imposta `Pdf417.Rotate` a `RotationAngle.Rotate90` se ti serve un layout orizzontale.  
* **Incorpora il barcode in un PDF** – combina Aspose.PDF con Aspose.BarCode per inserire l'immagine direttamente in un documento.  
* **Genera altri codici a barre 2‑D** – la stessa classe `BarcodeGenerator` supporta DataMatrix, QR e codici Aztec; basta sostituire `EncodeTypes.Pdf417` con la simbologia desiderata.

Padroneggiando le tecniche per **generare PDF417 barcode**, puoi automatizzare la gestione dei biglietti, l'etichettatura dell'inventario e la trasmissione sicura dei dati in una vasta gamma di applicazioni .NET.

## Conclusione

Ora sai come **generare PDF417 barcode** in C#, impostare con precisione le **dimensioni del codice a barre**, configurare le colonne, abilitare la modalità compatta e salvare il risultato come PNG. Applica queste impostazioni per soddisfare qualsiasi vincolo UI o requisito di scansione, e estendi l'approccio ad altri formati di codice a barre secondo necessità. Buona programmazione!

## Cosa dovresti imparare dopo?

I seguenti tutorial trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come generare PDF417 Barcode – Codifica PDF417 compatta](/barcode/english/net/compact-pdf417-encoding/)
- [Come creare Barcode – PDF417 compatto con Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Come generare codici a barre DataMatrix usando Aspose.BarCode per .NET – Guida passo‑passo](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}