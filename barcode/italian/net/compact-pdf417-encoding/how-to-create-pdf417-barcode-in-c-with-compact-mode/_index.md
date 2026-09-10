---
category: general
date: 2026-09-10
description: Crea rapidamente un codice a barre PDF417 in C#. Scopri come abilitare
  la modalità compatta, impostare le colonne e generare un PNG con BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- enable compact mode
- barcode generator C#
- how to generate barcode
- how to set columns
language: it
lastmod: 2026-09-10
og_description: Crea un codice a barre PDF417 in C# abilitando la modalità compatta,
  impostando le colonne e salvando come PNG. Segui la guida completa passo‑passo.
og_image_alt: Screenshot of a compact PDF417 barcode generated with C#
og_title: Crea codice a barre PDF417 in C# – tutorial modalità compatta
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create PDF417 barcode in C# quickly. Learn how to enable compact mode,
    set columns, and generate a PNG with BarcodeGenerator.
  headline: How to create PDF417 barcode in C# with compact mode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Come creare un codice a barre PDF417 in C# con modalità compatta
url: /it/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un codice a barre PDF417 in C# con modalità compatta

Se hai bisogno di **creare un codice a barre PDF417** in un'applicazione .NET, questa guida ti mostra esattamente come farlo. Vedrai come **abilitare la modalità compatta**, impostare il numero di colonne e salvare il risultato come immagine PNG usando la libreria BarcodeGenerator per C#.

Generare un codice a barre è una necessità comune per il tracciamento dell'inventario, i sistemi di biglietteria e le app di scansione mobile. Alla fine di questo tutorial avrai un esempio autonomo e eseguibile che produce un codice a barre PDF417 compatto pronto per l'uso in produzione.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6.0 o versioni successive installate (il codice funziona anche con .NET Framework 4.7+)
* Una versione recente della libreria **BarcodeGenerator** (ad es., Aspose.BarCode per .NET)
* Un IDE o editor come Visual Studio 2022 o VS Code
* Permesso di scrittura su una cartella dove verrà salvato il PNG

Non sono richiesti pacchetti NuGet aggiuntivi oltre alla libreria del codice a barre stessa.

## Passo 1: Creare un generatore di codici a barre PDF417

Il primo passo è istanziare un oggetto `BarcodeGenerator` con l'enumerazione `EncodeTypes.Pdf417` e il testo che desideri codificare. Questo oggetto gestisce l'intero processo di generazione.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

*Perché è importante*: il valore `EncodeTypes.Pdf417` indica alla libreria di utilizzare la simbologia PDF417, mentre il secondo argomento fornisce il payload. Puoi sostituire `"Compact mode"` con qualsiasi stringa alfanumerica tu debba codificare.

## Passo 2: Impostare la dimensione X (larghezza del modulo)

La dimensione X controlla la larghezza di ogni piccolo quadrato (modulo) nel codice a barre. Valori più piccoli producono un'immagine più stretta, utile quando lo spazio è limitato.

```csharp
// Step 2: Set the X dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Un valore di `2` pixel è un buon compromesso tra leggibilità e compattezza per la maggior parte degli scanner basati su schermo.

## Passo 3: Definire il numero di colonne

PDF417 può disporre i dati in una griglia di righe e colonne. Regolare il conteggio delle colonne modifica il rapporto d'aspetto del codice a barre.

```csharp
// Step 3: Define the number of columns for the PDF417 barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

Impostare **come impostare le colonne** a `3` genera un codice a barre corto e largo che si adatta bene a un'etichetta. Puoi sperimentare valori da `1` a `30` a seconda della quantità di dati e dello scanner di destinazione.

## Passo 4: Abilitare la modalità compatta

La modalità compatta rimuove le righe di riempimento non necessarie, rendendo il codice a barre più piccolo senza perdere l'integrità dei dati. Questo è il passaggio chiave per un **PDF417 compatto**.

```csharp
// Step 4: Enable compact mode by truncating the barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

Quando `Truncate` è `true`, la libreria calcola automaticamente il numero minimo di righe necessario per memorizzare i dati, per questo l'immagine finale appare “stretta”.

## Passo 5: Salvare il codice a barre generato come immagine PNG

Infine, scrivi il codice a barre su un file. PNG conserva i bordi nitidi necessari per una scansione affidabile.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

Sostituisci `YOUR_DIRECTORY` con un percorso assoluto o relativo a cui la tua applicazione può scrivere. Dopo l'esecuzione, troverai un file `CompactPdf417.png` che contiene il codice a barre.

### Codice sorgente completo

Unendo tutti i passaggi ottieni un unico programma pronto all'uso:

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

        // Set the X dimension (module width) in pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the number of columns for the PDF417 barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;

        // Enable compact mode by truncating the barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("CompactPdf417.png", BarCodeImageFormat.Png);

        Console.WriteLine("PDF417 barcode created successfully.");
    }
}
```

Eseguendo questo programma verrà prodotto `CompactPdf417.png` nella stessa cartella dell'eseguibile. Apri l'immagine con qualsiasi visualizzatore; dovresti vedere un codice a barre PDF417 denso e ad alto contrasto pronto per la scansione.

## Come abilitare la modalità compatta in altri scenari

* **Generazione batch** – Quando crei molti codici a barre, imposta `Truncate` una volta sul generatore e riutilizzalo per ogni nuovo payload.
* **Formati immagine diversi** – Lo stesso metodo `Save` funziona con `BarCodeImageFormat.Jpeg` o `BarCodeImageFormat.Bmp` se ti serve un tipo di file diverso.
* **Conteggio colonne dinamico** – Se la lunghezza della stringa codificata varia, calcola un conteggio di colonne ottimale in base alla lunghezza della stringa e alla risoluzione dello scanner.

## Come impostare le colonne per casi d'uso specifici

* **Stampa etichette** – Usa un conteggio di colonne basso (es., `2`‑`5`) per mantenere il codice a barre sufficientemente corto da stare su etichette strette.
* **Scansione mobile** – Conteggi di colonne più alti (`10`‑`15`) producono codici a barre più alti, più facili da mettere a fuoco con le fotocamere dei telefoni.
* **Compromesso correzione errori** – Più colonne riducono il numero di righe, il che può influire sulla correzione d'errore integrata del codice a barre. Testa con lo scanner di destinazione per trovare il punto ottimale.

## Problemi comuni e consigli professionali

| Problema | Perché accade | Soluzione |
|----------|----------------|-----------|
| Il codice a barre è illeggibile | Dimensione X troppo bassa (es., `1` pixel) | Aumentare `XDimension.Pixels` ad almeno `2` |
| L'immagine è troppo grande | Numero di colonne impostato troppo alto per un payload breve | Ridurre `Pdf417.Columns` o abilitare `Truncate` |
| Il file PNG è vuoto | La cartella di output non esiste o manca del permesso di scrittura | Assicurarsi che la directory esista e che il processo abbia i diritti di scrittura |
| Lo scanner segnala “dati corrotti” | Truncate disabilitato mentre si usano molte colonne | Abilitare `Truncate` o ridurre il numero di colonne |

## Verifica del risultato

Puoi verificare il codice a barre con qualsiasi app scanner PDF417 (esistono molte app gratuite per Android/iOS). Apri `CompactPdf417.png` nell'app e conferma che il testo decodificato corrisponda al payload originale (“Compact mode”). Se il testo differisce, ricontrolla il flag `Truncate` e le impostazioni delle colonne.

## Passi successivi

* **Integrare con ASP.NET Core** – Restituire il PNG direttamente da un'azione del controller invece di salvarlo su disco.
* **Aggiungere testo leggibile** – Utilizzare `barcodeGenerator.Parameters.Barcode.CodeTextParameters` per visualizzare la stringa codificata sotto il codice a barre.
* **Esplorare altre simbologie** – La stessa classe `BarcodeGenerator` supporta QR, Code128, DataMatrix e altro. Cambia `EncodeTypes` per provarle.

---

### Conclusione

Ora sai come **creare un codice a barre PDF417** in C# **abilitando la modalità compatta**, controllando **come impostare le colonne** e usando l'API **barcode generator C#** per **generare un codice a barre** che soddisfa i vincoli di dimensione del mondo reale. Applica questi passaggi a qualsiasi progetto .NET che necessita di codici a barre compatti e ad alta densità, e estendi il modello ad altri formati di codice a barre secondo necessità. Buona programmazione!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API e a esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Crea codice a barre PDF417 in C# – Guida completa passo‑per‑passo](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [Come impostare il livello di errore nel codice a barre PDF417 – Guida completa](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Come salvare il codice a barre in C# – Generare codici a barre PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}