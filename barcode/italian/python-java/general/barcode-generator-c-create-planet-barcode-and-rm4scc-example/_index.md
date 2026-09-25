---
category: general
date: 2026-08-03
description: Tutorial C# per generatore di codici a barre che mostra come creare un
  codice a barre Planet con Aspose.BarCode, impostare la dimensione X e salvare come
  immagini PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- create planet barcode
language: it
lastmod: 2026-08-03
og_description: Il tutorial del generatore di codici a barre C# ti guida nella creazione
  di un codice a barre Planet, nella regolazione della dimensione X e nel salvataggio
  come PNG usando Aspose.BarCode.
og_image_alt: Screenshot of generated Planet and RM4SCC barcodes in PNG format
og_title: Generatore di codici a barre C# – crea il codice a barre Planet passo dopo
  passo
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Barcode generator C# tutorial showing how to create Planet barcode
    with Aspose.BarCode, set X‑dimension, and save as PNG images.
  headline: Barcode generator C# – create Planet barcode and RM4SCC example
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Generatore di codici a barre C# – crea esempio di codice Planet e RM4SCC
url: /it/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generatore di codici a barre C# – creare esempio di Planet barcode e RM4SCC

Se hai bisogno di un **barcode generator C#** che possa produrre simboli specifici per la posta, questa guida ti mostra esattamente come **creare Planet barcode** con Aspose.BarCode. Vedrai come configurare la X‑dimension, generare un RM4SCC barcode corrispondente e salvare entrambi come file PNG—tutto in pochi passaggi concisi.

Il tutorial copre tutto ciò di cui hai bisogno per eseguire il codice su .NET 6 o versioni successive, spiega perché ogni impostazione è importante e segnala le insidie comuni, come larghezza del modulo errata o permessi di directory mancanti. Alla fine avrai due immagini di codici a barre pronte per la stampa che rispettano gli standard Planet e RM4SCC.

## Prerequisiti

* .NET 6 SDK (o qualsiasi versione .NET supportata da Aspose.BarCode)
* Visual Studio 2022 o qualsiasi IDE C# che preferisci
* Un riferimento NuGet a **Aspose.BarCode** (`Install-Package Aspose.BarCode`)
* Permesso di scrittura sulla cartella in cui prevedi di memorizzare i file PNG

Non sono richiesti servizi esterni aggiuntivi; la libreria gestisce tutta la codifica localmente.

## Passo 1: Inizializzare l'oggetto barcode generator C# 

Il primo compito è creare un'istanza di `BarcodeGenerator`. Il costruttore accetta la simbologia del codice a barre (`EncodeTypes.Planet`) e i dati da codificare.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*Perché questo passo?*  
`BarcodeGenerator` è il punto di ingresso per ogni codice a barre che generi. Selezionare `EncodeTypes.Planet` indica alla libreria di seguire la specifica ISO/IEC 24723 utilizzata da molti servizi postali.

## Passo 2: Impostare la X‑dimension (larghezza del modulo) per il Planet barcode

La X‑dimension definisce la larghezza di un singolo modulo del codice a barre (la barra o lo spazio più piccolo). Un valore di **4 pixel** funziona bene per la maggior parte delle stampanti di etichette.

```csharp
// Step 2: Define the X‑dimension (module width) in pixels
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Perché è importante*  
Se il modulo è troppo stretto, il codice a barre potrebbe diventare illeggibile; se è troppo largo, la dimensione dell'etichetta aumenta inutilmente. Regolare `Pixels` ti consente di perfezionare il codice a barre per la risoluzione specifica della tua stampante.

## Passo 3: Salvare il Planet barcode come immagine PNG

Aspose.BarCode calcola automaticamente l'altezza del codice a barre in base alla simbologia selezionata, quindi devi solo specificare il percorso del file e il formato.

```csharp
// Step 3: Save the Planet barcode as a PNG image (height is calculated automatically)
planetGenerator.Save("YOUR_DIRECTORY/PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

*Suggerimento*  
Sostituisci `YOUR_DIRECTORY` con un percorso assoluto o relativo che esiste sulla tua macchina. Se la directory non esiste, il metodo `Save` genera una `DirectoryNotFoundException`.

**Output previsto** – un file PNG che appare simile all'illustrazione qui sotto (l'immagine reale non è mostrata, ma vedrai un classico Planet barcode con un payload numerico di `123456`).

## Passo 4: Inizializzare un secondo generatore per il RM4SCC barcode

Molti sistemi postali richiedono sia i simboli Planet sia RM4SCC sullo stesso pezzo di posta. Crea una nuova istanza di `BarcodeGenerator` per la simbologia RM4SCC.

```csharp
// Step 4: Create an RM4SCC barcode generator with the same data
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
```

*Perché un'istanza separata?*  
Ogni simbologia ha il proprio set di parametri. Riutilizzare lo stesso generatore potrebbe trasferire involontariamente impostazioni (come la X‑dimension) che non sono ottimali per il secondo codice a barre.

## Passo 5: Configurare la X‑dimension per il RM4SCC barcode

Anche RM4SCC rispetta l'impostazione della X‑dimension, quindi applichiamo la stessa larghezza in pixel per coerenza visiva.

```csharp
// Step 5: Set the X‑dimension for the RM4SCC barcode
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Consiglio professionale*  
Se ti serve un codice a barre più alto (ad esempio per etichette più grandi), puoi anche impostare `Height.Pixels`. Lasciandolo non impostato, la libreria calcola automaticamente l'altezza ideale.

## Passo 6: Salvare il RM4SCC barcode come immagine PNG

Infine, salva il RM4SCC barcode su disco.

```csharp
// Step 6: Save the RM4SCC barcode as a PNG image (height is calculated automatically)
rm4sccGenerator.Save("YOUR_DIRECTORY/PostalRM4SCCBarHeightNone.png", BarCodeImageFormat.Png);
```

Ora hai due file PNG—`PostalPlanetBarHeightNone.png` e `PostalRM4SCCBarHeightNone.png`—che puoi incorporare nelle etichette di spedizione, stampare su buste o inviare a un servizio di stampa di terze parti.

## Opzionale: Regolare l'altezza o utilizzare altri formati immagine

Se il tuo flusso di lavoro richiede un'altezza specifica del codice a barre o un formato immagine diverso (ad esempio JPEG o BMP), puoi modificare i parametri prima di chiamare `Save`:

```csharp
// Example: set a fixed height of 100 pixels and save as JPEG
planetGenerator.Parameters.Barcode.Height.Pixels = 100;
planetGenerator.Save("PostalPlanet.jpg", BarCodeImageFormat.Jpeg);
```

**Caso limite** – Quando imposti un'altezza personalizzata, assicurati che il valore rispetti l'altezza minima richiesta dallo standard ISO; altrimenti il codice a barre potrebbe non superare la validazione.

## Problemi comuni e come evitarli

| Problema | Perché succede | Soluzione |
|----------|----------------|-----------|
| `DirectoryNotFoundException` | La cartella di destinazione non esiste o è scritta in modo errato. | Crea prima la cartella o usa `Path.Combine` con `Environment.CurrentDirectory`. |
| Codice a barre illeggibile su stampanti a bassa risoluzione | X‑dimension troppo piccola per i DPI della stampante. | Aumenta `XDimension.Pixels` a 5 – 6 per stampanti a 203 dpi, oppure testa con un'etichetta di esempio. |
| Simbologia errata utilizzata | Passare `EncodeTypes.Code128` invece di `EncodeTypes.Planet`. | Verifica che il valore dell'enum `EncodeTypes` corrisponda allo standard postale richiesto. |
| Riferimento nullo su `Parameters` | Utilizzare una versione più vecchia di Aspose.BarCode in cui l'API è diversa. | Aggiorna all'ultima versione del pacchetto NuGet (v23.12 o successiva). |

## Esempio completo eseguibile

Di seguito trovi il programma completo che puoi copiare, incollare ed eseguire. Include le istruzioni `using`, la gestione degli errori e i commenti che spiegano ogni riga.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define the output directory (change as needed)
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // -------- Planet barcode ----------
        var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string planetPath = Path.Combine(outputDir, "PostalPlanetBarHeightNone.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Planet barcode saved to: {planetPath}");

        // -------- RM4SCC barcode ----------
        var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string rm4sccPath = Path.Combine(outputDir, "PostalRM4SCCBarHeightNone.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);
        Console.WriteLine($"RM4SCC barcode saved to: {rm4sccPath}");
    }
}
```

Eseguendo il programma viene creata una cartella `Barcodes` accanto all'eseguibile e vengono inseriti i due file PNG al suo interno. Aprili con qualsiasi visualizzatore di immagini per verificare il risultato.

## Conclusione

Ora disponi di una soluzione **barcode generator C#** che può **creare Planet barcode** immagini, regolare la X‑dimension per una stampa ottimale e produrre un codice a barre RM4SCC corrispondente—tutto con poche righe di codice. L'approccio funziona con .NET 6+, richiede solo il pacchetto NuGet Aspose.BarCode e può essere esteso ad altre simbologie come Code128, QR o DataMatrix cambiando il valore di `EncodeTypes`.

### Cosa fare dopo?

* Sperimenta con diversi valori di `XDimension.Pixels` per adeguarli ai DPI della tua stampante.  
* Genera codici a barre in altri formati (PDF, SVG) modificando l'enum `BarCodeImageFormat`.  
* Combina i due file PNG in un'unica etichetta usando una libreria grafica come **SkiaSharp**.  
* Esplora l'intera API di Aspose.BarCode per funzionalità avanzate come la validazione del checksum o i font personalizzati.  

Sentiti libero di adattare il codice per l'elaborazione batch o integrarlo in un servizio web ASP.NET Core che restituisce immagini di codici a barre su richiesta. Buon coding!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo passo per aiutarti a padroneggiare ulteriori funzionalità dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Crea Barcode PNG – Rapporto d'Aspetto DataMatrix – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [Come salvare PNG usando DataMatrix C40 con Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [barcode generator tutorial c# – Personalizza i rapporti d'aspetto del Code 16K Barcode con Aspose.BarCode per .NET](/barcode/english/net/code-16k-encoding/code-16k-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}