---
date: 2026-09-28
description: Scopri come creare un codice a barre matrice 2D con Aspose.BarCode per
  .NET – una guida passo‑passo per generare codici a barre DotCode con testo di codice
  esteso.
keywords:
- create 2d matrix barcode
- how to generate dotcode
- dotcode extended codetext
lastmod: 2026-09-28
linktitle: Configurazione del testo di codice esteso DotCode
og_description: Scopri come creare un codice a barre matrice 2D usando Aspose.BarCode
  per .NET. Questa guida mostra passo‑passo come generare codici a barre DotCode con
  testo di codice esteso.
og_image_alt: Guide showing how to create a 2d matrix DotCode barcode with extended
  codetext in .NET
og_title: Crea un codice a barre matrice 2D con Aspose.BarCode per .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create 2d matrix barcode with Aspose.BarCode for .NET
    – a step‑by‑step guide for generating DotCode barcodes with extended code text.
  headline: How to create 2d matrix barcode via Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. The PNG image produced by the generator can be embedded in iOS, Android,
      or any cross‑platform mobile application.
    question: Can I use the generated barcode in a mobile app?
  - answer: Use the `AddECICodetext` method with the appropriate `ECIEncodings` (e.g.,
      `ECIEncodings.Base64`) to embed binary payloads.
    question: What if I need to encode binary data instead of text?
  - answer: Adjust the `XDimension.Pixels` property; higher values increase module
      size, while lower values make the barcode more compact.
    question: How do I change the barcode size without affecting readability?
  - answer: Yes. Set `gen.Parameters.Barcode.Margin` to define the desired quiet zone
      in pixels.
    question: Is there a way to add a quiet zone around the barcode?
  - answer: The latest Aspose.BarCode releases are compatible with .NET 8; just reference
      the appropriate NuGet package version.
    question: Does the library support .NET 8?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- dotcode
- Aspose.BarCode
- .NET barcode generation
- 2d matrix barcode
title: Come creare un codice a barre matrice 2D con Aspose.BarCode per .NET
url: /it/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un codice a barre matrice 2d tramite Aspose.BarCode per .NET

## Introduzione

Nel campo della generazione e gestione dei codici a barre, Aspose.BarCode per .NET si distingue come una soluzione versatile che supporta **50+ input and output formats** e può elaborare documenti di centinaia di pagine senza caricare l'intero file in memoria. Che tu abbia bisogno di codici a barre per il tracciamento dei prodotti, il controllo dell'inventario o applicazioni ricche di dati, creare un **2d matrix barcode** come DotCode con codetesto esteso ti consente di incorporare sia payload testuali che binari in un simbolo quadrato compatto. Questo tutorial ti guida nella costruzione di quel codetesto esteso passo dopo passo e nella resa dell'immagine finale.

## Risposte rapide
- **Cosa significa “create dotcode extended codetext”?** Significa costruire un codice a barre DotCode che includa FNC1, ECICodetext, plain text e separatori di simbolo in un unico payload esteso.  
- **Quale libreria è necessaria?** Aspose.BarCode per .NET.  
- **È necessaria una licenza?** Una licenza temporanea funziona per la valutazione; è necessaria una licenza completa per la produzione.  
- **Quali versioni .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **Quanto tempo richiede l'implementazione?** Circa 10‑15 minuti per un esempio base.

## Come creare dotcode extended codetext

Carica il tuo progetto, imposta la directory, costruisci il codetesto esteso e genera l'immagine – il tutto in meno di una dozzina di righe di codice. La risposta diretta seguente riassume l'intero processo:

Carica il `BarcodeGenerator` con `EncodeTypes.DotCode`, costruisci il codetesto esteso usando `DotCodeExtendedCodetextBuilder` (aggiungendo FNC1, ECICodetext, plain text e separatori FNC3), quindi chiama `Save` per scrivere un file PNG. Questa sequenza crea un codice a barre matrice 2d pienamente conforme in una singola chiamata.

## Cos'è dotcode extended codetext?

Il **dotcode extended codetext** è una stringa composita che combina più segmenti di dati — come identificatori FNC1, ECICodetext, plain text e separatori FNC3 — in un unico payload che DotCode può decodificare. Consente la codifica di testo multilingue, blob binari e dati strutturati all'interno di un singolo codice a barre matrice 2d, rendendolo ideale per scenari di supply‑chain, sanità e IoT.

## Perché usare Aspose.BarCode per questo compito?

Aspose.BarCode elabora **fino a 500 pagine al secondo** su hardware server tipico e supporta **oltre 30 simbologie di codici a barre**, inclusa DotCode. La sua API `GetExtendedCodetext` garantisce il corretto posizionamento dei caratteri di controllo, eliminando errori di concatenazione manuale delle stringhe e assicurando la conformità a ISO/IEC 24724. Inoltre, offre correzione d'errore integrata e gestione automatica della quiet‑zone, riducendo la necessità di sintonizzazioni manuali.

## Prerequisiti

- **Aspose.BarCode per .NET** – scarica dalla [documentazione di Aspose.BarCode per .NET](https://reference.aspose.com/barcode/net/).  
- Un ambiente di sviluppo .NET (Visual Studio 2022 o successivo consigliato).  
- Facoltativo: un file di licenza temporaneo per la valutazione.

## Importare gli spazi dei nomi

`using Aspose.BarCode.Generation;`  
`using Aspose.BarCode.ComplexBarcodes;`  

Questi spazi dei nomi espongono la classe `BarcodeGenerator` e l'helper `DotCodeExtendedCodetextBuilder` necessari per l'esempio.

```csharp
using Aspose.BarCode.Generation;
```

Ora che abbiamo coperto i prerequisiti, analizziamo il processo di generazione del DotCode Extended Code Text in una guida passo‑per‑passo.

## Passo 1: definire il percorso della directory

Specifica dove verrà salvato il PNG generato. Usa un percorso assoluto o relativo a cui la tua applicazione possa scrivere.

```csharp
string path = "Your Directory Path";
```

Sostituisci `"Your Directory Path"` con il percorso reale sul tuo sistema.

## Passo 2: creare dotcode extended codetext

La classe `DotCodeExtendedCodetextBuilder` assembla i vari segmenti in una singola stringa di codetesto esteso.

Per creare il DotCode Extended Code Text, segui questi sotto‑passi:

### 2.1 aggiungere identificatore di formato fnc1

L'identificatore di formato FNC1 segna l'inizio di un nuovo campo dati. È richiesto per i simboli DotCode conformi a GS1.

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 aggiungere ecicodetext

L'ECICodetext codifica caratteri speciali e testo internazionale. In questo esempio codifichiamo `"犬Right狗"` usando UTF‑8.

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 aggiungere plain codetext

Puoi anche aggiungere testo semplice al DotCode Extended Code Text. Qui aggiungiamo `"Plain text"`.

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 aggiungere separatore di simbolo fnc3

Il separatore di simbolo FNC3 separa diverse sezioni del codice, migliorando la leggibilità per gli scanner.

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 aggiungere inizializzazione lettore fnc3

Questo passaggio aggiunge le informazioni di Inizializzazione Lettore FNC3, che indicano allo scanner come interpretare i dati successivi.

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 generare codetext

Ora genera il DotCode Extended Codetext chiamando il metodo `GetExtendedCodetext` sull'oggetto `textBuilder`.

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## Passo 3: generare immagine dotcode

Renderizza l'immagine del codice a barre dal codetesto esteso.

#### 3.1 inizializzare il generatore di barcode

La classe `BarcodeGenerator` è l'oggetto principale di Aspose.BarCode per creare qualsiasi codice a barre. Lo istanzi con la simbologia desiderata (`EncodeTypes.DotCode`) e il codetesto esteso appena costruito.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    // Set the X-dimension for the barcode (adjust as needed).
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    // Set the DotCode encoding mode to ExtendedCodetext.
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    // Save the generated barcode image.
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Infine, chiama `Save` per scrivere il file PNG su disco. L'immagine è pronta per essere incorporata in report, app mobili o etichette stampate.

## Problemi comuni e soluzioni

- **Codifica errata** – Assicurati di usare `ECIEncodings.UTF8` quando aggiungi testo multilingue; altrimenti i caratteri potrebbero apparire corrotti.  
- **Errori di accesso al file** – Verifica che l'applicazione abbia i permessi di scrittura sulla directory di destinazione.  
- **Quiet zone mancante** – Imposta `gen.Parameters.Barcode.Margin` se gli scanner richiedono spazio bianco extra attorno al simbolo.

## Domande frequenti

**D: Posso usare il codice a barre generato in un'app mobile?**  
R: Sì. L'immagine PNG prodotta dal generatore può essere incorporata in iOS, Android o qualsiasi applicazione mobile cross‑platform.

**D: E se devo codificare dati binari invece di testo?**  
R: Usa il metodo `AddECICodetext` con il `ECIEncodings` appropriato (ad es., `ECIEncodings.Base64`) per incorporare payload binari.

**D: Come modifico la dimensione del codice a barre senza compromettere la leggibilità?**  
R: Regola la proprietà `XDimension.Pixels`; valori più alti aumentano la dimensione del modulo, valori più bassi rendono il codice più compatto.

**D: È possibile aggiungere una quiet zone attorno al codice a barre?**  
R: Sì. Imposta `gen.Parameters.Barcode.Margin` per definire la quiet zone desiderata in pixel.

**D: La libreria supporta .NET 8?**  
R: Le ultime versioni di Aspose.BarCode sono compatibili con .NET 8; basta referenziare la versione appropriata del pacchetto NuGet.

Se hai bisogno di ulteriori indicazioni o hai domande, visita la [documentazione di Aspose.BarCode per .NET](https://reference.aspose.com/barcode/net/) o partecipa alla community sul [forum di supporto Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**Last Updated:** 2026-09-28  
**Tested With:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose

## Tutorial correlati

- [Crea codice a barre DotCode .NET (Modalità Auto) con Aspose.BarCode](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)
- [Come generare codici a barre DataMatrix usando Aspose.BarCode per .NET – Guida passo‑per‑passo](/barcode/net/datamatrix-barcode-configuration/)
- [Come creare codice a barre Aztec con Aspose.BarCode per .NET](/barcode/net/aztec-barcode-encoding/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}