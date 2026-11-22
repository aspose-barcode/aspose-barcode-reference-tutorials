---
category: general
date: 2026-11-20
description: Crea rapidamente un'immagine di codice a barre postale in C#. Scopri
  come generare i codici a barre Planet e RM4SCC con stili di barra personalizzabili.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- postal barcode C#
- Aspose.BarCode example
- barcode image generation
language: it
lastmod: 2026-11-20
og_description: Crea un'immagine di codice a barre postale in C# con Aspose.BarCode.
  Questo tutorial mostra come generare il codice a barre Planet, personalizzare gli
  stili delle barre e produrre immagini RM4SCC.
og_image_alt: Create postal barcode image example showing filled and empty bars
og_title: Crea immagine di codice a barre postale in C# – guida passo‑passo
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Create postal barcode image in C# quickly. Learn how to generate planet
    barcode and RM4SCC barcodes with customizable bar styles.
  headline: Create postal barcode image and generate planet barcode
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Crea immagine di codice a barre postale e genera codice a barre planetario
url: /it/python-java/general/create-postal-barcode-image-and-generate-planet-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea immagine di codice a barre postale e genera codice a barre planet

Crea un'immagine di codice a barre postale in C# utilizzando la libreria Aspose.BarCode. Se hai bisogno di generare codici a barre planet o RM4SCC per applicazioni di spedizione, questo tutorial fornisce una soluzione completa, pronta all'uso.

La generazione di codici a barre per i servizi postali richiede spesso dimensioni precise e la possibilità di passare tra stili di barre piene e vuote. Questa guida ti accompagna nella configurazione della cartella di output, nella creazione di codici a barre Planet sia pieni che vuoti, e nella produzione di un codice a barre RM4SCC con le stesse impostazioni visive. Alla fine avrai quattro file PNG che potrai utilizzare direttamente nel tuo flusso di lavoro di mailing.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6.0 o successivo installato  
* Visual Studio 2022 (o qualsiasi IDE C# tu preferisca)  
* Il pacchetto NuGet **Aspose.BarCode** (`Install-Package Aspose.BarCode`)  

Non è necessaria alcuna configurazione aggiuntiva; il codice utilizza solo il font predefinito e l'encoder PNG.

## Crea immagine di codice a barre postale – panoramica

Il cuore del processo è la classe `BarcodeGenerator`. Accetta un valore `EncodeTypes` che determina la simbologia del codice a barre (ad esempio, `EncodeTypes.Planet` per un codice a barre Planet). Dopo aver configurato il generatore, chiami `Save` per scrivere il file immagine.

![Create postal barcode image example](/images/postal_barcode_example.png)

*Alt text: Esempio di creazione di immagine di codice a barre postale che mostra barre piene e vuote.*

## Passo 1: Configura la cartella di output

Per prima cosa definisci una cartella dove verranno salvati i file PNG. L'uso di un percorso assoluto o relativo funziona allo stesso modo; assicurati solo che la cartella esista o lascia che il codice la crei.

```csharp
using System.IO;
using Aspose.BarCode.Generation;

// Define the output folder (change to your own path)
string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
```

Creare la cartella programmaticamente evita `DirectoryNotFoundException` quando il tutorial viene eseguito su una macchina nuova.

## Passo 2: Genera codice a barre planet con barre piene

Un codice a barre Planet a barre piene è lo stile visivo predefinito. Il codice seguente crea il codice a barre, imposta la dimensione X a 4 pixel (una dimensione comune per le applicazioni postali) e salva l'immagine.

```csharp
// Step 2: Generate a Planet barcode with filled bars
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save as PNG
string planetFilledPath = Path.Combine(outputFolder, "PostalPlanetFilledBars.png");
planetFilled.Save(planetFilledPath, BarCodeImageFormat.Png);
```

**Perché funziona:**  
* `EncodeTypes.Planet` indica al generatore di utilizzare la simbologia Planet, richiesta da molti servizi postali.  
* `XDimension.Pixels` controlla la larghezza di ogni barra; 4 px producono un'immagine chiara e leggibile senza dimensioni eccessive del file.  
* Il metodo `Save` seleziona automaticamente l'encoder PNG in base all'enum `BarCodeImageFormat`.

## Passo 3: Genera codice a barre planet con barre vuote

Alcune specifiche postali preferiscono barre vuote (bianche) su uno sfondo scuro. Puoi ottenere questo impostando `FilledBars` a `false`.

```csharp
// Step 3: Generate a Planet barcode with empty bars
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for consistency
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars – the bars become transparent (empty)
planetEmpty.Parameters.Barcode.FilledBars = false;

// Save the result
string planetEmptyPath = Path.Combine(outputFolder, "PostalPlanetEmptyBars.png");
planetEmpty.Save(planetEmptyPath, BarCodeImageFormat.Png);
```

**Suggerimento:** Quando `FilledBars` è `false`, il generatore dipinge le barre nel colore di sfondo (bianco per impostazione predefinita) e gli spazi nel colore di primo piano (nero). Se ti serve uno schema di colori diverso, regola `Parameters.Barcode.ForeColor` e `BackColor`.

## Passo 4: Genera codice a barre RM4SCC con barre piene

RM4SCC è un'altra simbologia postale usata nel Regno Unito. I passaggi di creazione rispecchiano l'esempio Planet; cambia solo il valore `EncodeTypes`.

```csharp
// Step 4: Generate an RM4SCC barcode with filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Reuse the same X‑dimension for a uniform look
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save the PNG file
string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png");
rm4sccFilled.Save(rm4sccPath, BarCodeImageFormat.Png);
```

**Cosa aspettarsi:** Il PNG risultante mostra un compatto codice a barre RM4SCC che rispetta le linee guida postali del Regno Unito. La dimensione dell'immagine sarà simile a quella dei codici Planet perché la dimensione X è identica.

## Passo 5: Verifica le immagini generate

Dopo aver eseguito il programma, apri i quattro file nella cartella `Barcodes`. Dovresti vedere:

* `PostalPlanetFilledBars.png` – barre scure su sfondo chiaro  
* `PostalPlanetEmptyBars.png` – barre chiare su sfondo scuro (inverso)  
* `PostalRM4SCCFilledBars.png` – modello standard RM4SCC  

Se qualche immagine appare distorta, controlla quanto segue:

* **X‑dimension** – troppo piccola (< 2 px) può causare sfocatura; troppo grande (> 10 px) può superare i limiti di dimensione dell'etichetta.  
* **Stringa dati** – il valore `"123456"` deve rispettare i requisiti di lunghezza della simbologia scelta (Planet richiede 6 cifre, RM4SCC richiede anch'esso 6 cifre).  
* **Permessi della cartella** – assicurati che l'applicazione abbia accesso in scrittura alla directory di output.

## Variazioni comuni e casi limite

| Scenario | Adeguamento |
|----------|------------|
| **Dati del codice a barre diversi** | Sostituisci `"123456"` con qualsiasi stringa numerica valida. Per Planet, la lunghezza deve essere esattamente 6 cifre; RM4SCC richiede anch'esso 6 cifre. |
| **Colori personalizzati** | Imposta `planetFilled.Parameters.Barcode.ForeColor = System.Drawing.Color.DarkBlue;` e `BackColor = System.Drawing.Color.LightYellow;`. |
| **Risoluzione più alta** | Aumenta `XDimension.Pixels` a 6 o 8 per stampe più grandi. |
| **Altri formati immagine** | Usa `BarCodeImageFormat.Jpeg` o `BarCodeImageFormat.Bmp` nella chiamata a `Save`. |
| **Generazione batch** | Cicla su una collezione di stringhe e chiama la stessa logica del generatore all'interno del ciclo, riutilizzando il percorso `outputFolder`. |

## Esempio completo, eseguibile

Copia il codice qui sotto in un nuovo progetto console C#. Compila con .NET 6.0 e produce automaticamente tutte e quattro le immagini dei codici a barre.



## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare ulteriori funzionalità dell'API e a esplorare approcci di implementazione alternativi nei tuoi progetti.

- [How to create postal barcode image with custom heights in C#](/barcode/english/python-java/general/how-to-create-postal-barcode-image-with-custom-heights-in-c/)
- [How to create RM4SCC barcode and generate planet barcode in C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-generate-planet-barcode-in/)
- [Create postal barcode image in C# – step‑by‑step guide](/barcode/english/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}