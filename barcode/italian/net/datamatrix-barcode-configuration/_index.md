---
date: 2026-06-09
description: Scopri come generare datamatrix barcode con Aspose.BarCode per .NET,
  personalizzare i rapporti d'aspetto, le modalità ECC e la codifica c40 datamatrix
  per una creazione efficiente di barcode.
keywords:
- generate datamatrix barcode
- datamatrix c40 encoding
- aspose barcode .net
- datamatrix ecc modes
- barcode aspect ratio
linktitle: Configurazione DataMatrix Barcode
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  headline: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  name: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  steps:
  - name: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
    text: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
  - name: '**Adjust** `AspectRatio` to your desired value.'
    text: '**Adjust** `AspectRatio` to your desired value.'
  - name: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
    text: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
  type: HowTo
- questions:
  - answer: Choose ECC 000‑140 for small data sets with limited error correction,
      or ECC 200 for larger data and higher reliability. Macro mode adds an extra
      data layer for linking.
    question: How do I decide which ECC mode to use?
  - answer: Yes, set the `CodeText` property to your custom string, then select the
      appropriate encoding mode (ASCII, C40, etc.) to control size.
    question: Can I embed custom text in a DataMatrix barcode?
  - answer: Set `EncodeMode` to `Auto`; Aspose.BarCode evaluates the payload and picks
      the most space‑efficient mode automatically.
    question: Is there a way to automatically select the best encoding mode?
  - answer: Reuse a single `BarCodeGenerator` instance, enable multi‑threading, and
      generate PNG images for lossless quality or JPEG for smaller file size. Processing
      10 000 symbols typically completes in under 30 seconds on a standard 8‑core
      server.
    question: What are the performance considerations for large barcode batches?
  - answer: Absolutely – the library is fully compatible with .NET Framework, .NET
      Core, and the latest .NET releases, offering the same feature set across all
      platforms.
    question: Does Aspose.BarCode support .NET Core and .NET 5/6?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Genera DataMatrix Barcode – Guida professionale con Aspose.BarCode
url: /it/net/datamatrix-barcode-configuration/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Genera Codice a Barre DataMatrix – Guida Pro con Aspose.BarCode

Benvenuti alla nostra serie di tutorial completi su **generate datamatrix barcode** utilizzando Aspose.BarCode per .NET. Che siate sviluppatori esperti che perfezionano l'output dei codici a barre o neofiti desiderosi di comprendere le basi, questa guida vi accompagna passo passo—dalla configurazione di base alle tecniche di codifica avanzate—così da poter fornire codici a barre affidabili e pronti alla scansione in qualsiasi applicazione .NET.

## Risposte Rapide
- **Qual è lo scopo principale?** Creare e personalizzare codici a barre DataMatrix in modo programmatico.  
- **Quale libreria viene usata?** Aspose.BarCode per .NET.  
- **È necessaria una licenza?** È disponibile una versione di prova gratuita; per la produzione è richiesta una licenza commerciale.  
- **Versioni .NET supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Posso personalizzare il rapporto d'aspetto?** Sì – vedere la sezione “Come personalizzare il rapporto d'aspetto DataMatrix”.

## Cos'è generate datamatrix barcode?
Un codice a barre DataMatrix è una matrice bidimensionale di celle nere e bianche che può memorizzare fino a 2 300 caratteri alfanumerici. Utilizzando Aspose.BarCode, è possibile **generate datamatrix barcode** immagini, PDF o SVG direttamente dal codice .NET, controllando dimensione, livello di correzione errori e modalità di codifica per soddisfare qualsiasi standard di settore.

## Perché usare Aspose.BarCode per DataMatrix?
Aspose.BarCode rende i simboli DataMatrix fino a **600 dpi** senza pixelatura, garantendo scansioni nitide su stampanti ad alta risoluzione. Supporta **tutte le 50+ modalità ECC e macro**—incluse ECC 000‑140, ECC 200 e Macro 05/06—così da poter scegliere il livello di correzione errori ottimale per la dimensione dei dati. L'API offre opzioni di codifica **ASCII, C40, Text, X12 e Bytes**, consentendo di comprimere i dati in modo efficiente. L'integrazione richiede solo un singolo pacchetto NuGet e nessuna libreria nativa esterna.

## Come personalizzare il rapporto d'aspetto DataMatrix
La proprietà `AspectRatio` di `BarCodeGenerator` controlla la proporzione larghezza‑altezza del simbolo DataMatrix generato. `BarCodeGenerator` è la classe principale in Aspose.BarCode usata per creare immagini di codici a barre.  

**Risposta diretta:** Imposta `generator.Parameters.Barcode.DataMatrix.AspectRatio = 1.2` (o qualsiasi valore tra 0.5 e 2.0) prima di chiamare `GenerateBarCodeImage()`. La libreria ricalcola automaticamente la dimensione del modulo per preservare l'affidabilità della scansione rispettando il rapporto richiesto.

### Passo‑per‑passo
1. **Instantiate** `BarCodeGenerator` con `EncodeTypes.DataMatrix`.  
2. **Adjust** `AspectRatio` al valore desiderato.  
3. **Generate** l'immagine e verifica con uno scanner o con il lettore integrato di Aspose.

## Come generare codici DataMatrix ECC 000‑140
ECC 000‑140 è ideale per stringhe di dati brevi dove è richiesto un simbolo compatto, offrendo fino a 140 codici di correzione errori. `DataMatrixEccMode.Ecc000140` seleziona lo schema di correzione errori ECC 000‑140 per DataMatrix.  

**Risposta diretta:** Usa `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc000140` prima del rendering. Questo commuta l'encoder allo schema ECC 000‑140, producendo la matrice più piccola possibile per i dati forniti mantenendo una robusta correzione errori.

### Consiglio pratico
Quando si codificano dati numerici inferiori a 20 caratteri, ECC 000‑140 genera spesso una matrice 10 × 10, risparmiando spazio prezioso sull'etichetta.

## Come generare codici DataMatrix ECC 200
ECC 200 è la modalità DataMatrix più diffusa, supporta fino a 2 335 caratteri alfanumerici e offre una correzione errori superiore. `DataMatrixEccMode.Ecc200` seleziona lo schema di correzione errori ECC 200 per DataMatrix.  

**Risposta diretta:** Imposta `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc200` e fornisci il tuo payload tramite `CodeText`. La libreria seleziona automaticamente la dimensione ottimale della matrice.

### Quando preferire ECC 200
Usa ECC 200 per stringhe più lunghe, dati misti o quando è necessaria la massima resilienza ai danni—fino al **30 %** del simbolo può essere ripristinato.

## Come padroneggiare la codifica DataMatrix in ASCII
La modalità ASCII codifica i caratteri usando un byte per carattere, risultando la più efficiente in termini di spazio per testo semplice. `DataMatrixEncodeMode.Ascii` indica al generatore di usare la codifica ASCII per il simbolo DataMatrix.  

**Risposta diretta:** Assegna `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Ascii` e imposta `CodeText` sulla tua stringa ASCII. Il motore compatta i dati senza overhead aggiuntivo, producendo la matrice più piccola possibile per contenuti puramente ASCII.

### Scenario d'esempio
Uno SKU di magazzino composto da lettere maiuscole e cifre (es. “AB1234”) si adatta perfettamente alla modalità ASCII, spesso risultando in una matrice 12 × 12.

## Come generare DataMatrix Mode (Auto)
La modalità Auto consente ad Aspose.BarCode di analizzare l'input e scegliere automaticamente la codifica più efficiente (ASCII, C40, Text, X12 o Bytes). `DataMatrixEncodeMode.Auto` abilita questa funzionalità di selezione automatica.  

**Risposta diretta:** Imposta `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Auto`. La libreria valuta il payload, seleziona la modalità ottimale e rende il codice a barre in un unico passaggio.

### Vantaggi
La modalità Auto riduce lo sforzo di sviluppo e garantisce il simbolo più piccolo possibile per dati misti, migliorando la velocità di scansione.

## Come usare la modalità di codifica DataMatrix (Bytes)
La modalità Bytes è progettata per dati binari, come payload criptati o file compressi. `DataMatrixEncodeMode.Bytes` indica al generatore di trattare ogni byte come dato grezzo.  

**Risposta diretta:** Usa `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Bytes` e fornisci una stringa Base64‑encoded come `CodeText`. L'encoder tratta ogni byte come dato grezzo, preservando la rappresentazione binaria esatta.

### Caso d'uso
Incorporare un GUID a 128 bit o un piccolo token criptato direttamente in un simbolo DataMatrix.

## Come padroneggiare la modalità di codifica DataMatrix (C40)
La modalità C40 comprime dati alfanumerici maiuscoli, ottenendo fino al **40 %** di riduzione rispetto ad ASCII. `DataMatrixEncodeMode.C40` attiva questo algoritmo di compressione.  

**Risposta diretta:** Imposta `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.C40` e fornisci una stringa maiuscola (es. “HELLO WORLD”). Il motore raggruppa tre caratteri in due codeword, riducendo la matrice finale.

### Consiglio da professionista
C40 funziona al meglio quando il payload è costituito principalmente da lettere maiuscole, numeri e spazi. Per dati con mix di maiuscole/minuscole, considera la modalità Auto.

## Come configurare il testo del codice DataMatrix
La proprietà `CodeText` definisce i dati esatti memorizzati nel codice a barre. Può includere testo semplice, stringhe numeriche o anche payload XML. `CodeText` è la proprietà stringa principale di `BarCodeGenerator` che contiene il payload del codice a barre.  

**Risposta diretta:** Assegna `generator.Parameters.Barcode.CodeText = "YourDataHere"` prima del rendering. La proprietà accetta qualsiasi stringa UTF‑8 fino alla lunghezza massima supportata dalla modalità ECC scelta.

### Suggerimento avanzato
Combina `CodeText` con `ExtendedDataMatrix` per incorporare metadati aggiuntivi senza aumentare la dimensione visibile della matrice.

## Come padroneggiare la configurazione macro DataMatrix
Le modalità macro (Macro 05 e Macro 06) consentono di incorporare un simbolo DataMatrix secondario all'interno di quello primario, utile per collegare a fonti di dati esterne. `DataMatrixMacroMode.Macro05` e `DataMatrixMacroMode.Macro06` abilitano queste funzionalità macro.  

**Risposta diretta:** Abilita la modalità macro con `generator.Parameters.Barcode.DataMatrix.MacroMode = DataMatrixMacroMode.Macro05` (o `Macro06`) e imposta le proprietà `MacroPdf417` per il payload secondario. Il generatore crea un simbolo composito che gli scanner possono interpretare come due codici collegati.

### Esempio reale
Incorporare un URL nella parte macro mantenendo gli identificatori di prodotto nella matrice primaria, consentendo un'integrazione fluida web‑to‑barcode.

---

*Using Aspose.BarCode For .NET Tutorials Listing*

## DataMatrix Barcode Configuration Tutorials
### [Customizing DataMatrix Aspect Ratio](./datamatrix-aspect-ratio-customization/)
Learn how to customize DataMatrix barcode aspect ratios using Aspose.BarCode for .NET. Step-by-step guide for barcode generation.
### [Generate DataMatrix ECC 000-140 Barcodes](./datamatrix-ecc-000-140-configuration/)
Create DataMatrix ECC 000-140 barcodes with ease using Aspose.BarCode for .NET. Boost efficiency in inventory management and more.
### [Generate DataMatrix ECC 200 Barcodes](./datamatrix-ecc-200-configuration/)
Learn how to generate DataMatrix ECC 200 barcodes in .NET using Aspose.BarCode. Streamline operations with efficient barcode creation.
### [Master DataMatrix Encoding in ASCII](./datamatrix-encoding-mode-ascii/)
Learn to create DataMatrix barcodes in ASCII mode using Aspose.BarCode for .NET. Step-by-step guide for developers.
### [Generate DataMatrix Mode (Auto)](./datamatrix-encoding-mode-auto/)
Learn how to generate DataMatrix Mode (Auto) with Aspose.BarCode for .NET. This step-by-step guide covers everything from prerequisites to reading barcodes.
### [DataMatrix Encoding Mode (Bytes)](./datamatrix-encoding-mode-bytes/)
Learn how to encode data in DataMatrix format using Bytes mode with Aspose.BarCode for .NET. Follow our step-by-step guide for barcode generation and recognition.
### [Master DataMatrix Encoding Mode (C40)](./datamatrix-encoding-mode-c40/)
Learn DataMatrix Encoding Mode (C40) with Aspose.BarCode for .NET. Create custom barcodes efficiently. Explore step-by-step guide.
### [Configuring DataMatrix Code Text](./datamatrix-extended-code-text-configuration/)
Learn to configure DataMatrix extended code text using Aspose.BarCode for .NET. Generate, recognize, and integrate barcodes in your .NET applications.
### [Master DataMatrix Macro Configuration](./datamatrix-macro-configuration/)
Learn how to configure DataMatrix Macro barcodes with Aspose.BarCode for .NET. Generate, customize, and recognize DataMatrix barcodes in your .NET applications.

## Frequently Asked Questions

**Q: How do I decide which ECC mode to use?**  
A: Choose ECC 000‑140 for small data sets with limited error correction, or ECC 200 for larger data and higher reliability. Macro mode adds an extra data layer for linking.

**Q: Can I embed custom text in a DataMatrix barcode?**  
A: Yes, set the `CodeText` property to your custom string, then select the appropriate encoding mode (ASCII, C40, etc.) to control size.

**Q: Is there a way to automatically select the best encoding mode?**  
A: Set `EncodeMode` to `Auto`; Aspose.BarCode evaluates the payload and picks the most space‑efficient mode automatically.

**Q: What are the performance considerations for large barcode batches?**  
A: Reuse a single `BarCodeGenerator` instance, enable multi‑threading, and generate PNG images for lossless quality or JPEG for smaller file size. Processing 10 000 symbols typically completes in under 30 seconds on a standard 8‑core server.

**Q: Does Aspose.BarCode support .NET Core and .NET 5/6?**  
A: Absolutely – the library is fully compatible with .NET Framework, .NET Core, and the latest .NET releases, offering the same feature set across all platforms.

---

**Last Updated:** 2026-06-09  
**Tested With:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose

## Related Tutorials

- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Master DataMatrix Encoding in ASCII with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}