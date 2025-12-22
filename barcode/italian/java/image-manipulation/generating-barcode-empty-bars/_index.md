---
date: 2025-12-22
description: Impara come creare un'immagine di codice a barre con barre vuote usando
  Aspose.BarCode per Java. Questo esempio passo‑passo di generazione di codici a barre
  ti aiuta a generare rapidamente codici a barre in Java.
linktitle: Generating Barcode with Empty Bars
second_title: Aspose.BarCode Java API
title: Come creare un'immagine di codice a barre con barre vuote in Java
url: /it/java/image-manipulation/generating-barcode-empty-bars/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un'immagine di codice a barre con barre vuote in Java

## Introduzione

Nelle moderne applicazioni Java, la capacità di **creare barcode image** file al volo è una funzionalità preziosa per la gestione dell'inventario, i sistemi di biglietteria e molti altri scenari aziendali. Aspose.BarCode per Java fornisce un'API potente e facile‑da‑usare che consente di generare codici a barre di alta qualità in poche righe di codice. In questo tutorial percorreremo un processo di **step‑by‑step barcode** che produce un codice a barre con barre vuote (non riempite), perfetto per design che richiedono un aspetto cavo.

## Risposte rapide
- **Cosa significa “barra vuota”?** Le barre vengono renderizzate senza il riempimento solido predefinito, dando un aspetto cavo.  
- **Quale tipo di codice a barre viene utilizzato?** Code 128 (una simbologia lineare ampiamente supportata).  
- **È necessaria una licenza per provarlo?** È disponibile una versione di prova gratuita; è necessaria una licenza per l'uso in produzione.  
- **Quali formati di output sono supportati?** PNG, JPEG, BMP, GIF, TIFF e altri.  
- **È compatibile con tutte le versioni di Java?** Sì, la libreria funziona con Java 8 e successive.

## Che cos'è la creazione di un'immagine di codice a barre?
Creare un'immagine di codice a barre significa convertire una stringa di dati in una rappresentazione visiva che gli scanner possono leggere. L'immagine risultante può essere salvata come PNG, JPEG o altri formati comuni e incorporata in PDF, stampata su etichette o visualizzata su un'interfaccia utente.

## Perché usare la libreria Aspose.BarCode per Java?
- **Set di funzionalità ricco** – supporta oltre 50 simbologie di codici a barre, inclusi Code 128, QR, DataMatrix e altro.  
- **Controllo fine‑grained** – proprietà come `FilledBars`, colori, margini e dimensione dell'immagine sono facilmente configurabili.  
- **Nessuna dipendenza esterna** – un unico file JAR gestisce tutto, semplificando il deployment.  
- **Documentazione completa** – esempi, riferimento API e forum ti aiutano a prendere velocità rapidamente.

## Prerequisiti

Prima di intraprendere il viaggio della generazione di codici a barre, assicurati di avere i seguenti prerequisiti:

1. **Ambiente di sviluppo Java** – Assicurati di avere Java 8+ installato e un IDE o strumento di build compatibile.  
2. **Libreria Aspose.BarCode per Java** – Scarica e installa la libreria Aspose.BarCode per Java dalla [pagina di download](https://releases.aspose.com/barcode/java/).  
3. **Directory dei documenti** – Crea una directory sul tuo sistema per memorizzare l'immagine del codice a barre generata.

## Importa i pacchetti

Nel tuo progetto Java, importa i pacchetti necessari per lavorare con Aspose.BarCode:

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Come creare un'immagine di codice a barre con barre vuote

### Passo 1: Configura la directory delle risorse

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Sostituisci `"Your Document Directory"` con il percorso reale dove desideri salvare il file di output.

### Passo 2: Crea un'istanza del generatore di codice a barre (Code128 Barcode Java)

```java
// Create an instance of BarcodeGenerator and initialize it with CodeText and Symbology
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

Qui utilizziamo la simbologia **Code 128**—una delle più popolari codifiche lineari—rendendo questo un classico esempio di **code128 barcode java**.

### Passo 3: Imposta la proprietà FilledBars su False

```java
// Set the FilledBars property to false
generator.getParameters().getBarcode().setFilledBars(false);
```

Impostare `FilledBars` su `false` indica ad Aspose.BarCode di renderizzare le barre come forme vuote (cave) invece di blocchi solidi.

### Passo 4: Salva l'immagine del codice a barre

```java
// Save the resultant barcode image on disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

L'immagine viene salvata in formato PNG, ma puoi cambiare l'enumerazione `BarCodeImageFormat` per produrre JPEG, BMP o altri tipi supportati.

Ripeti questi passaggi nella tua applicazione Java per creare facilmente file **create barcode image** con barre vuote usando Aspose.BarCode per Java.

## Conclusione

In conclusione, questo tutorial ti ha guidato attraverso un processo di **step‑by‑step barcode** che mostra come **create barcode image** file con barre vuote in Java. Con la sua API intuitiva e le ampie opzioni di personalizzazione, Aspose.BarCode semplifica l'integrazione dei codici a barre, rendendola una risorsa preziosa per gli sviluppatori che necessitano di una **java barcode library** affidabile.

## Domande frequenti

### Aspose.BarCode è compatibile con tutti gli ambienti di sviluppo Java?
Sì, Aspose.BarCode è progettato per integrarsi perfettamente con vari ambienti di sviluppo Java.

### Posso personalizzare l'aspetto del codice a barre generato?
Assolutamente! Aspose.BarCode offre numerose opzioni di personalizzazione, consentendoti di adattare il codice a barre alle tue esigenze specifiche.

### È disponibile una versione di prova per Aspose.BarCode?
Sì, puoi esplorare le capacità di Aspose.BarCode ottenendo una prova gratuita [qui](https://releases.aspose.com/).

### Come posso ottenere supporto per Aspose.BarCode?
Per qualsiasi domanda o assistenza, visita il [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

### Dove posso trovare la documentazione dettagliata per Aspose.BarCode?
La documentazione completa è disponibile [qui](https://reference.aspose.com/barcode/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ultimo aggiornamento:** 2025-12-22  
**Testato con:** Aspose.BarCode Java 24.11 (latest)  
**Autore:** Aspose