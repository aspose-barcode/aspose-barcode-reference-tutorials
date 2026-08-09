---
category: general
date: 2026-08-09
description: Genera rapidamente codici a barre PDF417 in C#. Scopri come generare
  PDF417 con modalità compatta, controllo delle colonne e output PNG utilizzando l'API
  BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- create pdf417 barcode c#
- barcode generator c#
- compact pdf417 settings
- pdf417 png output
language: it
lastmod: 2026-08-09
og_description: Genera codice a barre PDF417 in C# con un esempio conciso. Questa
  guida ti mostra come configurare la modalità compatta, impostare le colonne e salvare
  il risultato come immagine PNG.
og_image_alt: Generated PDF417 barcode image saved as PNG
og_title: Genera codice a barre PDF417 in C# – tutorial completo
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    with compact mode, column control, and PNG output using the BarcodeGenerator API.
  headline: Generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- C#
- Aspose.BarCode
title: Genera codice a barre PDF417 in C# – guida passo passo
url: /it/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Genera codice a barre PDF417 in C# – guida passo‑passo

Se hai bisogno di **generare un codice a barre PDF417** in un'applicazione .NET, questo tutorial ti mostra esattamente come farlo. Vedrai un programma completo e eseguibile che crea un codice a barre PDF417 compatto, ne personalizza le dimensioni e salva l'immagine come file PNG.

Generare un codice a barre PDF417 è una necessità comune per il ticketing mobile, il tracciamento dell'inventario e la sicurezza dei documenti. Questa guida copre le opzioni di configurazione essenziali, spiega perché ogni impostazione è importante e fornisce consigli pratici per l'uso in scenari reali.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6.0 SDK o versioni successive installate  
* Un IDE C# come Visual Studio 2022 o Visual Studio Code  
* Il pacchetto **Aspose.BarCode for .NET** NuGet (versione 23.10 o più recente)  

Puoi installare il pacchetto con il seguente comando CLI:

```bash
dotnet add package Aspose.BarCode
```

Il codice qui sotto presuppone che il pacchetto sia referenziato e che tu abbia i permessi di scrittura nella cartella di output.

## Passo 1: Configura il progetto e importa i namespace

Crea un nuovo progetto console e aggiungi le direttive `using` richieste. Questi namespace espongono la classe `BarcodeGenerator` e l'enumerazione del formato immagine.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;
```

**Perché è importante:** Importare i namespace corretti garantisce che il compilatore possa trovare il tipo `BarcodeGenerator` e l'enum `BarCodeImageFormat`. L'assenza di un namespace genera un errore di compilazione, che interrompe il processo di generazione del codice a barre.

## Passo 2: Inizializza il `BarcodeGenerator` con codifica PDF417

Il costruttore di `BarcodeGenerator` riceve due argomenti: la simbologia del codice a barre (`EncodeTypes.Pdf417`) e il testo da codificare. PDF417 supporta un'ampia gamma di caratteri, inclusi i simboli Unicode.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

**Spiegazione:**  
* `EncodeTypes.Pdf417` indica alla libreria di utilizzare lo standard PDF417.  
* Il testo di esempio contiene caratteri accentati e un simbolo di copyright per dimostrare la gestione di Unicode.  

Se devi codificare solo dati numerici, puoi passare una stringa semplice come `"1234567890"`.

## Passo 3: Regola la X‑dimension per una risoluzione più fine

La X‑dimension controlla la larghezza di un singolo modulo del codice a barre (l'elemento più piccolo, nero o bianco). Impostare un valore di pixel più piccolo produce un'immagine a più alta risoluzione.

```csharp
// Step 3: Adjust the module (X) dimension for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Perché regolarla?** Una X‑dimension predefinita di 3–4 pixel può produrre un codice a barre dall'aspetto grezzo su schermi ad alta DPI. Ridurla a **2 pixel** bilancia leggibilità e dimensione del file, soprattutto quando attivi la modalità compatta.

## Passo 4: Configura il numero di colonne

PDF417 ti permette di specificare quante colonne deve contenere il codice a barre. Meno colonne rendono il codice più stretto ma più alto, mentre più colonne creano un codice più largo e più corto.

```csharp
// Step 4: Set the number of columns to control the barcode width
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

**Consiglio pratico:** Per i ticket mobili che devono stare entro un'etichetta stretta, un conteggio di colonne **3–5** funziona bene. Aumenta il conteggio se hai molti dati e desideri un codice più corto.

## Passo 5: Abilita la modalità compatta per troncare le righe vuote

La modalità compatta rimuove le righe non necessarie dalla matrice del codice a barre, riducendo la dimensione complessiva dell'immagine senza perdere dati codificati.

```csharp
// Step 5: Enable compact mode to truncate the barcode and reduce size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

**Quando usarla:** Se generi codici a barre per archiviazione o trasmissione in rete, la modalità compatta può ridurre il file PNG fino al 30 %. Tuttavia, alcuni scanner legacy potrebbero non supportare PDF417 troncati; verifica con l'hardware di destinazione.

## Passo 6: Salva il codice a barre come immagine PNG

Scegli un percorso di output e invoca `Save`. L'enumerazione `BarCodeImageFormat.Png` produce un'immagine lossless adatta alla maggior parte delle applicazioni.

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

**Verifica del risultato:** Apri il file PNG in qualsiasi visualizzatore di immagini. Dovresti vedere un codice a barre denso e ad alto contrasto che corrisponde al testo di esempio. Scansionando l'immagine con un lettore PDF417 (ad es. ZXing o un'app per smartphone) otterrai la stringa originale `"Åspóse.Barcóde©"`.

![Immagine del codice a barre PDF417 generato salvata come PNG](compact-pdf417.png "Generated PDF417 barcode in C#")

*L'immagine sopra dimostra l'output finale del codice del tutorial.*

## Esempio completo, eseguibile

Riunendo tutti i pezzi, ecco un programma console completo che puoi copiare, incollare ed eseguire.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;

namespace Pdf417GeneratorDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with PDF417 encoding
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // 2️⃣ Fine‑tune module size for sharper output
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set a narrow column count to keep the barcode slim
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Activate compact mode to drop empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define where the PNG will be written
            string outputPath = @"C:\Barcodes\CompactPdf417.png";

            // 6️⃣ Save the image
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Output previsto

L'esecuzione del programma stampa:

```
Barcode saved to C:\Barcodes\CompactPdf417.png
```

Il file `CompactPdf417.png` contiene un codice a barre PDF417 compatto che codifica la stringa Unicode fornita. Scansionando l'immagine con un lettore PDF417 standard si ottiene il testo esatto.

## Varianti comuni e casi limite

| Situazione | Regolazione | Motivo |
|------------|-------------|--------|
| **Payload di dati più lungo** (es. > 150 caratteri) | Incrementa `generator.Parameters.Barcode.Pdf417.Columns` a 6‑8 | Più colonne evitano che il codice diventi eccessivamente alto. |
| **Necessità di sfondo trasparente** | Usa `generator.Save(outputPath, BarCodeImageFormat.Png, new ImageSaveOptions { BackgroundColor = Color.Transparent })` | Un PNG trasparente si integra meglio in overlay UI. |
| **Generazione JPEG per il web** | Cambia il formato in `BarCodeImageFormat.Jpeg` e opzionalmente imposta `ImageQuality` | JPEG riduce la dimensione del file a costo di perdita di fedeltà. |
| **Gestione di input nullo o vuoto** | Verifica l'input prima di creare il generatore: `if (string.IsNullOrEmpty(text)) throw new ArgumentException("Text cannot be empty.");` | Previene eccezioni a runtime e garantisce codici a barre significativi. |

## Consigli per l'uso in produzione

* **Gestione delle eccezioni:** Avvolgi la logica di generazione in un blocco `try/catch` per registrare errori come spazio disco insufficiente o parametri non validi.  
* **Prestazioni:** Riutilizza un'unica istanza di `BarcodeGenerator` quando generi molti codici a barre con le stesse impostazioni; aggiorna solo la proprietà `CodeText` tra un salvataggio e l'altro.  
* **Sicurezza:** Quando il testo codificato contiene informazioni sensibili, considera di crittografarlo prima di passarlo al generatore e di decrittografarlo dopo la scansione.  

## Conclusione

Ora sai come **generare un codice a barre PDF417** in C# usando la libreria Aspose.BarCode, configurare la modalità compatta, controllare il numero di colonne e esportare il risultato come immagine PNG. Questo tutorial ha coperto ogni passaggio, dalla configurazione del progetto alla gestione dei casi limite, fornendoti una soluzione pronta all'uso per applicazioni basate su codici a barre.

Successivamente, esplora argomenti correlati come **creare codici QR in C#**, **generazione batch di codici a barre** e **integrazione della scansione di codici a barre con app mobili**. Ognuno di questi si basa sugli stessi fondamenti di `BarcodeGenerator` che hai appena appreso.

Buona programmazione!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}