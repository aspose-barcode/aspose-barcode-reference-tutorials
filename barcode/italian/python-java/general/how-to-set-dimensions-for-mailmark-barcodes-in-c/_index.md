---
category: general
date: 2026-08-22
description: Scopri come impostare le dimensioni dei codici a barre Mailmark in C#
  e salvarli come immagini PNG. Include codice completo, spiegazioni e consigli.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set dimensions
- Mailmark barcode C# example
- BarcodeGenerator dimensions
- set barcode size in C#
- save barcode as PNG
language: it
lastmod: 2026-08-22
og_description: Come impostare le dimensioni dei codici a barre Mailmark in C# ed
  esportarli come file PNG. Segui l'esempio completo ed evita gli errori più comuni.
og_image_alt: Screenshot of two generated Mailmark barcode PNG files showing different
  dimensions
og_title: Come impostare le dimensioni dei codici a barre Mailmark in C# – guida passo
  passo
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to set dimensions for Mailmark barcodes in C# and save them
    as PNG images. Includes full code, explanations, and tips.
  headline: How to set dimensions for Mailmark barcodes in C#
  type: TechArticle
tags:
- C#
- barcode
- Mailmark
- image generation
title: Come impostare le dimensioni dei codici a barre Mailmark in C#
url: /it/python-java/general/how-to-set-dimensions-for-mailmark-barcodes-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come impostare le dimensioni per i codici a barre Mailmark in C#

Se hai bisogno di **impostare le dimensioni** per un codice a barre Mailmark in C#, questa guida mostra i passaggi esatti. Vedrai come configurare la X‑dimension e l’altezza delle barre, quindi salvare il codice a barre come immagine PNG senza strumenti aggiuntivi.

Generare codici a barre postali è un compito di routine quando si sviluppa software per etichette di spedizione, ma la dimensione predefinita spesso non corrisponde ai requisiti della stampante o del layout. Alla fine di questo tutorial sarai in grado di controllare con precisione le dimensioni del codice a barre e produrre due tipi validi di Mailmark (tipo C e tipo L) pronti per la stampa.

**Cosa imparerai**

* Come impostare la X‑dimension (larghezza del modulo) e l’altezza delle barre per un `BarcodeGenerator`.
* Come salvare il codice a barre generato come file PNG usando `BarCodeImageFormat`.
* Problemi comuni come percorsi di cartella non validi o valori di dimensione non supportati.
* Suggerimenti per riutilizzare la stessa configurazione su più codici a barre.

## Prerequisiti

* .NET 6.0 o successivo (il codice funziona anche con .NET Framework 4.6+).
* Il pacchetto NuGet **Aspose.BarCode for .NET** (o qualsiasi libreria compatibile che fornisca `BarcodeGenerator`, `EncodeTypes` e `BarCodeImageFormat`).
* Familiarità di base con la sintassi C# e con le operazioni di I/O su file.

> **Pro tip:** Installa il pacchetto con il comando CLI  
> `dotnet add package Aspose.BarCode` per mantenere il progetto ordinato.

## Passo 1: Definire la cartella di output

Prima di creare qualsiasi codice a barre devi decidere dove verranno scritti i file PNG. Usare un percorso assoluto evita sorprese su macchine diverse.

```csharp
// Step 1: Define the folder where the barcode images will be saved
string outputFolder = @"C:\Temp\Barcodes\";

// Ensure the directory exists; create it if necessary
if (!Directory.Exists(outputFolder))
{
    Directory.CreateDirectory(outputFolder);
}
```

*Perché è importante*: Se la cartella non esiste, `Save` genera un `IOException`. La chiamata `Directory.CreateDirectory` è idempotente—non fa nulla se la cartella esiste già.

## Passo 2: Creare un codice a barre Mailmark di tipo C e **impostare le dimensioni**

Il Mailmark di tipo C codifica una stringa alfanumerica di 20 caratteri. Dopo aver inizializzato il generatore puoi **impostare le dimensioni** tramite l’oggetto `Parameters.Barcode`.

```csharp
// Step 2: Create a Mailmark C‑type barcode, configure its size, and save it as PNG
BarcodeGenerator mailmarkC = new BarcodeGenerator(EncodeTypes.Mailmark, "21B2254800659JW5O9QA6Y");

// Set the width of a single module (X‑dimension) to 4 pixels
mailmarkC.Parameters.Barcode.XDimension.Pixels = 4;

// Set the overall bar height to 50 pixels
mailmarkC.Parameters.Barcode.BarHeight.Pixels = 50;

// Save the image; the second argument specifies PNG format
mailmarkC.Save($"{outputFolder}PostalMailmarkCType.png", BarCodeImageFormat.Png);
```

### Perché scegliere questi valori?

* **X‑dimension** controlla la larghezza della barra più piccola (un “modulo”). Un valore di `4` pixel produce un codice a barre facilmente leggibile dalla maggior parte delle stampanti laser mantenendo la dimensione del file contenuta.
* **BarHeight** determina la dimensione verticale delle barre. `50` pixel è un’altezza comune per le etichette di spedizione standard, ma puoi aumentarla per formati più grandi.

> **Caso limite:** Alcune stampanti richiedono un’altezza minima di 30 px. Impostare un’altezza inferiore alla capacità della stampante può generare codici a barre illeggibili.

## Passo 3: Creare un codice a barre Mailmark di tipo L e **impostare le dimensioni**

Il tipo L utilizza una stringa di dati più lunga (fino a 30 caratteri). Lo stesso approccio di impostazione delle dimensioni si applica.

```csharp
// Step 3: Create a Mailmark L‑type barcode, configure its size, and save it as PNG
BarcodeGenerator mailmarkL = new BarcodeGenerator(EncodeTypes.Mailmark, "41038422416563762EF61AH8T");

// Reuse the same dimension settings for consistency
mailmarkL.Parameters.Barcode.XDimension.Pixels = 4;
mailmarkL.Parameters.Barcode.BarHeight.Pixels = 50;

// Save the L‑type barcode image
mailmarkL.Save($"{outputFolder}PostalMailmarkLType.png", BarCodeImageFormat.Png);
```

### Riutilizzare la configurazione

Se generi molti codici a barre con dimensioni identiche, considera di estrarre la configurazione in un metodo di supporto:

```csharp
void ApplyStandardDimensions(BarcodeGenerator generator)
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.BarHeight.Pixels = 50;
}
```

Chiamare `ApplyStandardDimensions(mailmarkC)` e `ApplyStandardDimensions(mailmarkL)` riduce la duplicazione e rende le modifiche future (ad es., passare a moduli da 5 pixel) un’operazione a una riga.

## Passo 4: Verificare i file PNG generati

Dopo aver eseguito il programma, apri i due file PNG in qualsiasi visualizzatore di immagini. Dovresti vedere due distinti codici a barre Mailmark, ciascuno con 4 px per modulo e 50 px di altezza.

*Output previsto*

| Nome file                     | Dimensioni approssimative (px) |
|-------------------------------|-------------------------------|
| `PostalMailmarkCType.png`     | 4 px × modulo × N moduli |
| `PostalMailmarkLType.png`     | 4 px × modulo × N moduli |

La larghezza esatta dipende dalla lunghezza dei dati codificati, ma l’altezza sarà costantemente **50 px** perché abbiamo impostato `BarHeight.Pixels`.

## Problemi comuni e come evitarli

| Problema                                 | Sintomo                                      | Soluzione |
|------------------------------------------|----------------------------------------------|-----------|
| Percorso cartella non valido             | `IOException: Could not find a part of the path` | Usa `Path.Combine` con `Environment.SpecialFolder` o verifica la stringa del percorso. |
| X‑dimension impostata a 0 o valore negativo | Il codice a barre appare come un blocco solido | Assicurati che `XDimension.Pixels` sia un intero positivo (minimo 1). |
| `EncodeTypes.Mailmark` non supportato    | `ArgumentException` durante la costruzione del generatore | Verifica di avere una versione recente della libreria Aspose.BarCode che includa il supporto Mailmark. |
| Salvataggio con formato immagine errato  | File PNG corrotto                           | Usa `BarCodeImageFormat.Png` (o `Jpeg` se ti serve un formato diverso). |

## Estendere l'esempio

* **Dimensioni diverse** – Cambia `XDimension.Pixels` a 3 per un codice a barre più compatto, oppure aumenta `BarHeight.Pixels` a 70 per etichette più grandi.
* **Generazione batch** – Itera su una collezione di stringhe di dati, applicando le stesse impostazioni di dimensione a ogni iterazione.
* **Altri formati immagine** – Sostituisci `BarCodeImageFormat.Png` con `BarCodeImageFormat.Jpeg` o `BarCodeImageFormat.Bmp` se il tuo flusso di lavoro lo richiede.

## Conclusione

Ora sai **come impostare le dimensioni** per i codici a barre Mailmark in C# e esportarli come file PNG. Configurando `XDimension.Pixels` e `BarHeight.Pixels` controlli la dimensione visiva sia dei codici di tipo C sia di tipo L, garantendo che soddisfino le specifiche della stampante e i vincoli di layout.  

Da qui puoi sperimentare con valori di dimensione diversi, integrare il codice in un sistema più ampio di etichette di spedizione, o generare batch di codici a barre per operazioni di mailing di massa.

---

*Passi successivi*: esplora le **dimensioni di BarcodeGenerator** per i QR code, o leggi la documentazione di Aspose.BarCode su **impostare DPI** per stampe ad alta risoluzione. Se devi incorporare il codice a barre in un PDF, combina questo approccio con la libreria **Aspose.PDF** per una soluzione completa end‑to‑end.

## Cosa dovresti imparare dopo?

I tutorial seguenti coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come impostare il bordo per la personalizzazione del codice a barre ITF-14](/barcode/english/net/itf-14-barcode-customization/)
- [Come configurare i codici Patch con Aspose.BarCode per .NET](/barcode/english/net/patch-code-configuration/)
- [Come generare codici DataMatrix usando Aspose.BarCode per .NET – Guida passo‑passo](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}