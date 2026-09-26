---
category: general
date: 2026-09-26
description: Impara a creare rapidamente i codici a barre Planet in C#. Questa guida
  copre i codici a barre Planet pieni e vuoti, le impostazioni della dimensione X
  e l'esportazione dell'immagine.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode C#
- filled planet barcode
- empty planet barcode
- barcode generator parameters
language: it
lastmod: 2026-09-26
og_description: Crea un codice a barre Planet in C# con un esempio di codice completo.
  Genera sia codici a barre Planet pieni che vuoti, imposta la larghezza delle barre
  e salva come PNG.
og_image_alt: Screenshot showing generated filled and empty planet barcode PNG files
og_title: Crea immagini di codici a barre planet in C# – guida passo passo
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create planet barcode in C# quickly. This guide covers
    filled and empty Planet barcodes, X‑dimension settings, and image export.
  headline: How to create planet barcode images in C# with BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Come creare immagini di codici a barre Planet in C# con BarcodeGenerator
url: /it/python-java/general/how-to-create-planet-barcode-images-in-c-with-barcodegenerat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare immagini di barcode Planet in C# con BarcodeGenerator

Se hai bisogno di **creare immagini di barcode Planet** in un'applicazione .NET, questo tutorial ti mostra i passaggi esatti. Imparerai a generare sia un barcode Planet pieno che uno vuoto, a regolare la larghezza delle barre e a esportare i risultati come file PNG — tutto con la libreria Aspose.BarCode per .NET.

Generare una **soluzione Planet barcode C#** è semplice una volta compresi i principali **parametri del generatore di barcode**. Nelle sezioni successive, esamineremo il codice completo e eseguibile, spiegheremo perché ogni impostazione è importante e indicheremo le insidie più comuni così da evitarle al primo tentativo.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6.0 SDK o versioni successive installate.
* Visual Studio 2022 (o qualsiasi IDE C# tu preferisca).
* Il pacchetto NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`) aggiunto al tuo progetto.

Puoi aggiungere il pacchetto tramite la Console di Gestione Pacchetti NuGet:

```bash
dotnet add package Aspose.BarCode
```

## Passo 1: Configurare il BarcodeGenerator

La classe `BarcodeGenerator` è il punto di ingresso per tutte le operazioni di creazione di barcode. Richiede due argomenti: il tipo di barcode (`EncodeTypes.Planet`) e i dati da codificare.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PlanetBarcodeDemo
{
    static void Main()
    {
        // Create a generator for a filled Planet barcode
        BarcodeGenerator filledPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*Perché è importante:* Istanziare il generatore con `EncodeTypes.Planet` indica alla libreria di utilizzare la simbologia **Planet barcode**, comunemente usata nei servizi postali di alcuni paesi. La stringa `"123456"` è il payload che apparirà nel barcode.

## Passo 2: Configurare la X‑dimensione (larghezza barra)

La X‑dimensione controlla la larghezza fisica di ogni barra. Un valore tipico per il rendering su schermo è 4 pixel, ma puoi modificarlo per soddisfare i requisiti di stampa.

```csharp
        // Define the bar width (X dimension) in pixels
        filledPlanet.Parameters.Barcode.XDimension.Pixels = 4;
```

*Perché è importante:* Impostare `XDimension.Pixels` garantisce che il barcode generato non sia né troppo sottile (causando errori di scansione) né troppo spesso (spreco di spazio). La stessa impostazione verrà riutilizzata per il barcode vuoto.

## Passo 3: Salvare il Planet barcode pieno

Esporta il barcode in un file PNG usando il metodo `Save`. L’enumerazione `BarCodeImageFormat.Png` indica alla libreria di produrre un’immagine lossless adatta a ulteriori elaborazioni.

```csharp
        // Save the filled barcode as a PNG image
        filledPlanet.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

Dopo aver eseguito il programma, troverai `PostalPlanetFilledBars.png` nella cartella di output. Aprilo per verificare che le barre siano solide (piene).

## Passo 4: Creare un generatore per un Planet barcode vuoto

Un **Planet barcode vuoto** visualizza gli stessi dati ma con barre non riempite (bianche). Questo è utile per design visivi che sovrappongono il barcode su sfondi colorati.

```csharp
        // Create a generator for an empty Planet barcode (unfilled bars)
        BarcodeGenerator emptyPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

La chiamata al costruttore è identica a quella della versione piena; la differenza sta nel parametro che cambieremo nel passo successivo.

## Passo 5: Riutilizzare la stessa X‑dimensione

Per mantenere coerente la dimensione visiva, applica la stessa larghezza barra al barcode vuoto.

```csharp
        // Use the same bar width as before
        emptyPlanet.Parameters.Barcode.XDimension.Pixels = 4;
```

Riutilizzare i **parametri del generatore di barcode** garantisce che entrambe le immagini si allineino perfettamente quando affiancate.

## Passo 6: Passare a barre non riempite

Il flag `FilledBars` determina se le barre vengono renderizzate come nero solido (impostazione predefinita) o bianco trasparente.

```csharp
        // Configure the generator to produce empty (unfilled) bars
        emptyPlanet.Parameters.Barcode.FilledBars = false;
```

*Perché è importante:* Impostare `FilledBars = false` inverte la modalità di rendering, che è la differenza chiave tra un Planet barcode pieno e uno vuoto.

## Passo 7: Salvare il Planet barcode vuoto

Infine, esporta la versione vuota in PNG.

```csharp
        // Save the empty barcode as a PNG image
        emptyPlanet.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

Quando esegui il programma, compaiono due file:

* `PostalPlanetFilledBars.png` – barre nere solide.
* `PostalPlanetEmptyBars.png` – barre trasparenti (vuote).

Entrambe le immagini contengono gli stessi dati (`123456`) e condividono la stessa X‑dimensione, rendendole intercambiabili nella maggior parte degli scenari UI.

## Esempio completo, eseguibile

Mettendo tutto insieme, ecco il file sorgente completo che puoi copiare‑incollare in un nuovo progetto console:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PlanetBarcodeDemo
{
    static void Main()
    {
        // ----------- Filled Planet barcode -----------
        BarcodeGenerator filledPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        filledPlanet.Parameters.Barcode.XDimension.Pixels = 4;
        filledPlanet.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // ----------- Empty Planet barcode ------------
        BarcodeGenerator emptyPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        emptyPlanet.Parameters.Barcode.XDimension.Pixels = 4;
        emptyPlanet.Parameters.Barcode.FilledBars = false;
        emptyPlanet.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

**Output previsto**

L’esecuzione del programma crea due file PNG nella directory di lavoro dell’eseguibile. Aprili con qualsiasi visualizzatore di immagini:

* **Versione piena** – barre scure e solide, facilmente leggibili dagli scanner standard.
* **Versione vuota** – barre appaiono come spazi bianchi su sfondo nero, utili per effetti di sovrapposizione.

## Problemi comuni e consigli professionali

| Problema | Perché accade | Come risolverlo |
|----------|---------------|-----------------|
| Le barre appaiono troppo sottili | X‑dimensione lasciata al valore predefinito (1 pixel) | Imposta `XDimension.Pixels` a 3‑5 pixel per uso su schermo; aumentala per stampe ad alta risoluzione. |
| Il barcode vuoto appare completamente nero | `FilledBars` non impostato a `false` | Assicurati che `emptyPlanet.Parameters.Barcode.FilledBars = false;` venga eseguito **dopo** aver impostato la X‑dimensione. |
| Il file PNG manca | Il percorso di output è errato o la directory non esiste | Fornisci un percorso completo (`@"C:\Barcodes\PostalPlanetFilledBars.png"`) o crea la directory in anticipo con `Directory.CreateDirectory`. |
| Il barcode non viene letto | La stringa dati contiene caratteri non consentiti per la simbologia Planet | I barcode Planet accettano solo payload numerici; valida l’input con `int.TryParse`. |

**Consiglio pro:** Se devi incorporare il barcode in un PDF, puoi caricare il PNG generato in un `PdfDocument` usando Aspose.PDF, oppure aggiungere direttamente il barcode come stream immagine senza scriverlo su disco.

## Prossimi passi

Ora che sai **creare immagini di planet barcode**, considera di approfondire i seguenti argomenti correlati:

* **Planet barcode C#** – personalizzare colori, aggiungere testo leggibile dall’uomo o incorporare il barcode in un PDF.
* **Parametri del generatore di barcode** – regolare il livello di correzione errori, la zona silenziosa o la rotazione.
* **Generazione batch** – iterare su un elenco di codici postali per produrre un file zip di PNG.
* **Formati alternativi** – esportare in SVG o JPEG per una consegna web‑friendly.

Sperimenta con valori diversi di `XDimension` e con il flag `FilledBars` per vedere come influenzano l’affidabilità della scansione e lo stile visivo. Quando sei pronto, integra il codice di generazione nella tua API web o nell’applicazione desktop per automatizzare la creazione di barcode postali al volo.

---


## Cosa dovresti imparare dopo?


I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare ulteriori funzionalità dell’API e a esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Create Planet Barcode in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Barcode generator C# – create Planet barcode and RM4SCC example](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)
- [Generate Postal Barcode in C# – Complete Guide with Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}