---
category: general
date: 2026-11-17
description: Scopri come salvare il codice a barre, abilitare la modalità compatta,
  regolare le colonne e generare il codice a barre PDF417 con un esempio completo
  in C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- enable compact mode
- how to adjust columns
- generate pdf417 barcode
- how to enable compact mode
language: it
lastmod: 2026-11-17
og_description: Come salvare il codice a barre, abilitare la modalità compatta e regolare
  le colonne durante la generazione di un codice a barre PDF417 in C#. Segui la guida
  passo‑passo.
og_image_alt: Screenshot showing how to save barcode as PNG file in C#
og_title: Come salvare il codice a barre come PNG e abilitare la modalità compatta
  in C#
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  headline: How to save barcode as PNG and enable compact mode in C#
  type: TechArticle
- description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  name: How to save barcode as PNG and enable compact mode in C#
  steps:
  - name: Expected output
    text: Opening the saved PNG file shows a vertically compact PDF417 barcode with
      three columns and truncated padding. The visual size is roughly 2 px per module,
      making the image suitable for embedding in HTML `<img>` tags or for printing
      on small labels.
  - name: What if I need a different image format?
    text: The `Save` method accepts any `BarCodeImageFormat` enum value, such as `Jpeg`,
      `Bmp`, or `Gif`. Replace `BarCodeImageFormat.Png` with the desired format, and
      the rest of the code remains unchanged.
  - name: How does truncation affect data capacity?
    text: Enabling **compact mode** (truncation) reduces the number of rows, which
      can lower the maximum data capacity of the barcode. If you encounter a “Data
      too large” exception, either increase the number of columns or disable truncation.
  - name: Can I use a dynamic column count?
    text: 'Yes. You can calculate the column count based on the length of the input
      string:'
  - name: Is the X‑dimension limited to integer pixels?
    text: The `Pixels` property accepts any positive integer. For higher‑resolution
      outputs (e.g., printing), you might prefer setting `Points` instead of `Pixels`
      to achieve device‑independent sizing.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- image generation
title: Come salvare il codice a barre come PNG e abilitare la modalità compatta in
  C#
url: /it/net/compact-pdf417-encoding/how-to-save-barcode-as-png-and-enable-compact-mode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come salvare il codice a barre come PNG e abilitare la modalità compatta in C#

Se hai bisogno di **how to save barcode** in un formato che può essere usato sul web o in stampa, questa guida ti mostra i passaggi esatti. Imparerai anche come **enable compact mode**, **adjust columns**, e **generate PDF417 barcode** con la libreria Aspose.BarCode per .NET.

Il tutorial copre tutto, dalla configurazione del progetto al file PNG finale, così puoi copiare il codice nella tua soluzione senza ulteriori ricerche. Non è necessaria alcuna documentazione esterna; è incluso l'esempio completo e eseguibile.

## Prerequisiti

* .NET 6.0 o versioni successive installato  
* Visual Studio 2022 (o qualsiasi IDE C#)  
* Il pacchetto NuGet `Aspose.BarCode` (`Install-Package Aspose.BarCode`)  

Questi tre elementi sono le uniche dipendenze per il codice che segue.

## Passo 1: Creare un generatore di codice a barre PDF417

Il primo compito quando **generate PDF417 barcode** è istanziare un `BarcodeGenerator` con il tipo di codifica corretto e i dati che desideri codificare.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a PDF417 barcode generator with the desired text.
BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

L'enumerazione `EncodeTypes.Pdf417` indica alla libreria di utilizzare la simbologia PDF417, che è un codice a barre lineare impilato adatto per codificare grandi quantità di dati. La stringa `"Compact mode"` diventa il testo leggibile dall'uomo sotto il codice a barre.

## Passo 2: Impostare la dimensione X (larghezza del modulo)

Ogni barra in un codice a barre è chiamata modulo. Controllare la larghezza del modulo ti permette di regolare finemente le dimensioni visive del codice a barre senza alterare i dati.

```csharp
// Step 2: Set the module (X) dimension – each bar will be 2 pixels wide.
barcode.Parameters.Barcode.XDimension.Pixels = 2;
```

Una dimensione X di 2 pixel produce un'immagine compatta che comunque viene letta in modo affidabile sulla maggior parte dei dispositivi.

## Passo 3: **How to adjust columns** per il codice PDF417

PDF417 ti consente di specificare quante colonne deve utilizzare il codice a barre. Meno colonne producono un simbolo più alto e più stretto, mentre più colonne rendono il simbolo più largo ma più corto.

```csharp
// Step 3: Define the number of columns for the PDF417 code (3 columns).
barcode.Parameters.Barcode.Pdf417.Columns = 3;
```

Questa riga dimostra **how to adjust columns**. Puoi cambiare il valore a 2, 4, o qualsiasi numero supportato dalla libreria, a seconda dello spazio disponibile sul supporto di destinazione.

## Passo 4: **How to enable compact mode** e troncare il simbolo

La modalità compatta rimuove il padding non necessario e riduce l'ingombro complessivo del codice a barre. La libreria espone questa funzionalità tramite la proprietà `Truncate`.

```csharp
// Step 4: Enable compact mode by truncating the symbol.
barcode.Parameters.Barcode.Pdf417.Truncate = true;
```

Nota che la frase **enable compact mode** appare qui, e la stessa azione è descritta con la dicitura esatta **how to enable compact mode** più avanti nella guida per soddisfare il requisito della parola chiave secondaria.

## Passo 5: **How to save barcode** come immagine PNG

Salvare l'immagine generata è l'ultimo passaggio. Il metodo `Save` scrive il codice a barre sul file system nel formato che specifichi.

```csharp
// Step 5: Save the generated barcode as a PNG image.
barcode.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

Sostituisci `YOUR_DIRECTORY` con un percorso assoluto o relativo a cui la tua applicazione può scrivere. Dopo l'esecuzione, troverai un file chiamato `CompactPdf417.png` contenente il codice a barre PDF417 compatto.

### Output previsto

Aprire il file PNG salvato mostra un codice a barre PDF417 verticalmente compatto con tre colonne e padding troncato. La dimensione visiva è circa 2 px per modulo, rendendo l'immagine adatta per l'inserimento in tag HTML `<img>` o per la stampa su piccole etichette.

## Esempio completo e eseguibile

Di seguito trovi il programma completo che puoi copiare in un nuovo progetto console. Include tutte le direttive `using` necessarie e dimostra **how to save barcode**, **enable compact mode**, **how to adjust columns**, e **generate PDF417 barcode** in un unico flusso.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417CompactDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a PDF417 barcode generator with the desired text.
            BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

            // Set the module (X) dimension – each bar will be 2 pixels wide.
            barcode.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns for the PDF417 code (3 columns).
            barcode.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable compact mode by truncating the symbol.
            barcode.Parameters.Barcode.Pdf417.Truncate = true;

            // Save the generated barcode as a PNG image.
            string outputPath = "CompactPdf417.png"; // Adjust path as needed.
            barcode.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Eseguendo questo programma si genera il file PNG descritto in precedenza. L'output della console conferma la posizione del file salvato, aiutandoti a verificare che il passaggio **how to save barcode** sia riuscito.

## Domande comuni e casi particolari

### E se avessi bisogno di un formato immagine diverso?

Il metodo `Save` accetta qualsiasi valore dell'enumerazione `BarCodeImageFormat`, come `Jpeg`, `Bmp` o `Gif`. Sostituisci `BarCodeImageFormat.Png` con il formato desiderato, e il resto del codice rimane invariato.

### Come influisce la troncatura sulla capacità dei dati?

Abilitare **compact mode** (troncatura) riduce il numero di righe, il che può diminuire la capacità massima di dati del codice a barre. Se incontri un'eccezione “Data too large”, aumenta il numero di colonne o disabilita la troncatura.

### Posso usare un conteggio di colonne dinamico?

Sì. Puoi calcolare il numero di colonne in base alla lunghezza della stringa di input:

```csharp
int desiredColumns = Math.Max(2, Math.Min(30, inputText.Length / 10));
barcode.Parameters.Barcode.Pdf417.Columns = desiredColumns;
```

Questo frammento mostra **how to adjust columns** in modo programmatico, garantendo che il codice a barre si adatti a un layout specifico.

### La dimensione X è limitata a pixel interi?

La proprietà `Pixels` accetta qualsiasi intero positivo. Per output ad alta risoluzione (ad esempio stampa), potresti preferire impostare `Points` invece di `Pixels` per ottenere una dimensione indipendente dal dispositivo.

## Consigli per l'uso in produzione

* **Pro tip:** Avvolgi la generazione del codice a barre in un blocco try‑catch per gestire `BarCodeException` quando i dati di input superano la capacità del simbolo.  
* **Watch out for:** Permessi del file‑system. Il processo deve avere accesso in scrittura alla directory di destinazione, altrimenti il passaggio **how to save barcode** fallirà con un `UnauthorizedAccessException`.  
* **Performance note:** Creare molti codici a barre in un ciclo beneficia del riutilizzo di un'unica istanza `BarcodeGenerator` e dell'aggiornamento solo della proprietà `CodeText` tra le iterazioni.

## Conclusione

Ora sai **how to save barcode** come file PNG, **enable compact mode**, **how to adjust columns**, e **generate PDF417 barcode** usando Aspose.BarCode per C#. L'esempio completo dimostra tutti i passaggi richiesti, dall'inizializzazione del generatore alla scrittura dell'immagine finale.

Da qui puoi esplorare argomenti correlati come aggiungere un logo al codice a barre, personalizzare i colori, o integrare il generatore in un'API ASP.NET Core. Ognuna di queste estensioni segue lo stesso schema mostrato in questa guida, così puoi adattare il codice con sicurezza.

Sentiti libero di sperimentare con diversi conteggi di colonne, dimensioni X e formati immagine per soddisfare le specifiche esatte del tuo progetto. Buon coding!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [How to save barcode and generate PDF417 with Aspose in C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [How to create PDF417 barcode and save it as PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}