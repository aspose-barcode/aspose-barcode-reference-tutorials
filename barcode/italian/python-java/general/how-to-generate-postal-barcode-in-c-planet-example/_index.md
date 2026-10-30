---
category: general
date: 2026-10-28
description: Genera codice a barre postale in C# usando il formato Planet. Questo
  esempio di codice a barre Planet mostra come impostare la larghezza del codice a
  barre e salvare sia le barre piene che quelle vuote.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- set barcode width
- planet barcode example
language: it
lastmod: 2026-10-28
og_description: Genera il codice a barre postale in C# con un esempio completo di
  codice a barre Planet. Impara a impostare la larghezza del codice a barre, a produrre
  barre riempite e a creare immagini di barre vuote.
og_image_alt: Screenshot of a generated Planet postal barcode saved as PNG
og_title: Genera il codice a barre postale in C# – guida passo passo
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  headline: How to generate postal barcode in C# – planet example
  type: TechArticle
- description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  name: How to generate postal barcode in C# – planet example
  steps:
  - name: Build the project (`dotnet build`).
    text: Build the project (`dotnet build`).
  - name: Run the executable (`dotnet run`).
    text: Run the executable (`dotnet run`).
  - name: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
    text: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
  - name: Open each image; you should see a series of vertical bars representing the
      numeric string
    text: Open each image; you should see a series of vertical bars representing the
      numeric string
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Come generare il codice a barre postale in C# – esempio planet
url: /it/python-java/general/how-to-generate-postal-barcode-in-c-planet-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come generare un codice a barre postale in C# – esempio Planet

Se hai bisogno di generare un codice a barre postale in C#, questa guida ti accompagna passo passo verso una soluzione completa. Vedrai un esempio pratico di codice a barre Planet che codifica una stringa numerica, ti permette di impostare la larghezza del codice a barre e salva sia le immagini delle barre piene che quelle vuote.

Creare un codice a barre postale non richiede una pipeline di build complessa. Alla fine di questo tutorial potrai integrare la generazione del codice a barre in qualsiasi applicazione .NET, personalizzare la X‑dimension e scegliere se le barre appaiono piene o vuote.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* SDK .NET 6.0 o successivo installato  
* Un ambiente di sviluppo C# (Visual Studio, VS Code o Rider)  
* Il pacchetto NuGet **Aspose.BarCode for .NET** (versione 23.10 o successiva)  

Puoi aggiungere il pacchetto con il seguente comando:

```bash
dotnet add package Aspose.BarCode
```

Gli snippet di codice qui sotto presumono che tu abbia aggiunto `using Aspose.BarCode.Generation;` all'inizio del tuo file.

## Genera codice a barre postale con simbologia Planet

Il primo passo è creare un'istanza di `BarcodeGenerator` che utilizzi la simbologia Planet. Planet è un formato di codice a barre postale usato da diversi servizi postali nazionali.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a Planet barcode generator with the data to encode
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Additional configuration will be applied here (see next steps)

        // Save the filled‑bars image
        barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // Switch to empty bars and save the second image
        barcodeGenerator.Parameters.Barcode.FilledBars = false;
        barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

**Perché è importante:**  
`EncodeTypes.Planet` indica alla libreria di utilizzare lo standard di codice a barre Planet, che codifica dati numerici in una serie di barre e spazi. Il costruttore riceve la stringa di dati (`"123456"` in questo caso) che desideri codificare.

L'esecuzione del programma produce due file PNG nella directory di lavoro dell'eseguibile:

* **PostalPlanetFilledBars.png** – le barre sono renderizzate come rettangoli neri solidi.  
* **PostalPlanetEmptyBars.png** – le barre sono renderizzate come rettangoli bianchi con contorno nero, utile per la stampa su sfondi scuri.

## Imposta la larghezza del codice a barre (X‑dimension) in pixel

La dimensione visiva di un codice a barre è controllata dalla X‑dimension, che definisce la larghezza di una singola barra. Regolare questo valore garantisce che il codice a barre venga letto correttamente alla risoluzione di stampa prevista.

```csharp
// Define the width of each bar (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

**Perché dovresti impostarlo:**  
Una X‑dimension più grande rende il codice a barre più facile da leggere con scanner a bassa risoluzione, mentre un valore più piccolo riduce le dimensioni complessive dell'immagine per stampe ad alta densità. La larghezza predefinita è 2 pixel; 4 pixel è un compromesso comune per la maggior parte delle stampanti da desktop.

Puoi sperimentare con valori diversi:

| Pixel | Caso d'uso tipico |
|-------|-------------------|
| 2     | Etichette ad alta densità |
| 4     | Stampa standard in ufficio |
| 6‑8   | Segnaletica di grande formato |

**Suggerimento:** Testa sempre il codice a barre generato con lo scanner di destinazione dopo aver modificato la X‑dimension.

## Esempio di codice a barre Planet – barre piene vs vuote

Un codice a barre Planet può essere renderizzato con barre solide (piene) o con contorni (vuote). La proprietà `FilledBars` commuta questo comportamento.

```csharp
// Save the barcode with the default filled bars
barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// Configure the generator to produce empty (unfilled) bars
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the barcode with empty bars
barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**Perché potresti scegliere barre vuote:**  
Le barre vuote migliorano il contrasto su imballaggi di colore scuro, perché l'interno bianco di ogni barra risalta su uno sfondo scuro. Le barre piene sono l'impostazione predefinita e funzionano bene su supporti chiari.

**Output previsto:**  

*Entrambe le immagini mostrano gli stessi dati codificati (`123456`).* L'unica differenza visiva è lo stile delle barre. Di seguito una descrizione testuale di ciò che vedrai:

* **Immagine barre piene:** Barre verticali nere solide su sfondo bianco.  
* **Immagine barre vuote:** Contorni neri che formano lo stesso schema, con interni bianchi.

Puoi aprire i file PNG in qualsiasi visualizzatore di immagini per verificare che lo schema corrisponda alla specifica Planet.

## Personalizza proprietà aggiuntive del codice a barre (opzionale)

Mentre i passaggi fondamentali sopra coprono la maggior parte degli scenari, potresti voler perfezionare altre impostazioni:

| Proprietà | Descrizione | Valore tipico |
|-----------|-------------|---------------|
| `Barcode.Color` | Colore di primo piano delle barre | `System.Drawing.Color.Black` |
| `Barcode.BackgroundColor` | Colore di riempimento dello sfondo | `System.Drawing.Color.White` |
| `Barcode.CodeText` | Testo leggibile dall'uomo visualizzato sotto il codice a barre | Stesso dei dati codificati o un'etichetta personalizzata |
| `Barcode.ImageFormat` | Formato di output (PNG, JPEG, BMP, ecc.) | `BarCodeImageFormat.Png` |

Esempio di impostazione di un colore di primo piano personalizzato:

```csharp
barcodeGenerator.Parameters.Barcode.Color = System.Drawing.Color.DarkBlue;
```

Queste regolazioni opzionali ti aiutano a rispettare il branding aziendale o a soddisfare requisiti di stampa specifici.

## Problemi comuni e come evitarli

| Problema | Causa | Soluzione |
|----------|-------|-----------|
| Il codice a barre è illeggibile | X‑dimension troppo piccola per i DPI della stampante | Aumentare `XDimension.Pixels` a 4 o più |
| Il file immagine è corrotto | Permessi di scrittura mancanti nella cartella di destinazione | Usare un percorso assoluto o assicurarsi che la directory esista |
| Simbolismo errato usato | Passare `EncodeTypes.Code128` invece di `EncodeTypes.Planet` | Verificare che l'argomento `EncodeTypes` corrisponda al formato postale |

**Consiglio professionale:** Genera sempre un codice a barre di prova e scansionalo con l'hardware previsto prima di passare in produzione.

## Esempio completo e eseguibile

Di seguito trovi un'applicazione console autonoma che incorpora tutti i passaggi discussi. Copia il codice in un nuovo progetto console .NET e eseguilo per vedere i due file PNG apparire nella cartella di output.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a Planet barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Set the width of each bar (X‑dimension) to 4 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the barcode with the default filled bars
            generator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved filled‑bars barcode as PostalPlanetFilledBars.png");

            // 4️⃣ Configure the generator to produce empty (unfilled) bars
            generator.Parameters.Barcode.FilledBars = false;

            // 5️⃣ Save the barcode with empty bars
            generator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved empty‑bars barcode as PostalPlanetEmptyBars.png");
        }
    }
}
```

**Passaggi di verifica:**  

1. Compila il progetto (`dotnet build`).  
2. Esegui l'eseguibile (`dotnet run`).  
3. Individua `PostalPlanetFilledBars.png` e `PostalPlanetEmptyBars.png` nella cartella `bin/Debug/net6.0`.  
4. Apri ciascuna immagine; dovresti vedere una serie di barre verticali che rappresentano la stringa numerica


## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come creare un codice a barre planet con barre piene e vuote](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [Come impostare la larghezza e generare un codice a barre Planet in C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Crea codice a barre postale in C# – esempio completo del generatore](/barcode/english/python-java/general/create-postal-barcode-in-c-full-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}