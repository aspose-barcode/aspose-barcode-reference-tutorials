---
date: 2025-12-19
description: Scopri come leggere i codici a barre con Aspose.BarCode per Java, ordinarli
  in una sequenza specifica e visualizzare un esempio completo di rilevamento di codici
  a barre in Java.
linktitle: Reading and Sorting Barcodes in Specific Order
second_title: Aspose.BarCode Java API
title: Come leggere i codici a barre e ordinarli in un ordine specifico in Java
url: /it/java/document-barcode-recognition/reading-sorting-barcodes-specific-order/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come leggere i codici a barre e ordinarli in un ordine specifico in Java

## Introduzione

Nelle moderne applicazioni Java, **come leggere i codici a barre** in modo efficiente è una domanda frequente. Che tu stia elaborando elenchi di inventario, etichette di spedizione o biglietti per eventi, una soluzione affidabile per i codici a barre può farti risparmiare ore di lavoro manuale. In questo tutorial ti mostreremo come leggere i codici a barre e ordinarli in un ordine specifico usando **Aspose.BarCode for Java**. Otterrai un esempio completo, pronto‑da‑eseguire, che dimostra la rilevazione del codice a barre, l’estrazione del testo del codice e la logica di ordinamento personalizzata.

## Risposte rapide
- **Quale libreria dovrei usare?** Aspose.BarCode for Java
- **Posso ordinare i codici a barre dopo averli letti?** Sì – basta memorizzare i risultati e applicare un comparatore
- **È necessaria una licenza per lo sviluppo?** Una versione di prova gratuita è sufficiente per i test; è richiesta una licenza commerciale per la produzione
- **Quale versione di Java è supportata?** Java 8 e successive
- **Questo è un esempio Java di rilevazione di codici a barre?** Assolutamente – il codice legge codici a barre CODE_128 e li ordina

## Cos’è “how to read barcodes” in Java?
Leggere i codici a barre significa decodificare il pattern visivo di un’immagine di codice a barre nel suo valore testuale sottostante. Aspose.BarCode fornisce un motore di **lettura dei codici a barre aspose** ad alte prestazioni che supporta decine di simbologie, tra cui CODE_128, QR, DataMatrix e molte altre.

## Perché usare Aspose.BarCode per la lettura dei codici a barre aspose?
- **Alta precisione** – funziona anche con immagini a bassa risoluzione
- **API semplice** – poche righe di codice ti portano dall’immagine al testo
- **Cross‑platform** – funziona in qualsiasi ambiente compatibile con JVM
- **Supporto integrato per l’ordinamento** – puoi facilmente combinare la lettura con le collezioni Java

## Prerequisiti

Prima di immergerti nel codice, assicurati di avere i seguenti prerequisiti:

- Java Development Kit (JDK): Aspose.BarCode for Java richiede un JDK funzionante. Puoi scaricare l’ultima versione [qui](https://www.oracle.com/java/technologies/javase-downloads.html).

- Libreria Aspose.BarCode: Assicurati di avere la libreria Aspose.BarCode. Puoi ottenerla dal [link di download](https://releases.aspose.com/barcode/java/).

## Importa i pacchetti

Inizia importando i pacchetti necessari nel tuo progetto Java. Questi pacchetti forniscono le classi e i metodi essenziali per lavorare con i codici a barre.

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;

import java.awt.Point;
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;
```

Ora, analizziamo il codice passo‑passo:

## Passo 1: Configura la directory delle risorse

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Sostituisci `"Your Document Directory"` con il percorso reale della tua directory dei documenti.

## Passo 2: Specifica il percorso dell’immagine del codice a barre e inizializza il lettore

```java
String path = dataDir + "barcode.png";
List<FoundBarCodes> found = new ArrayList<FoundBarCodes>();

// Initialize BarCodeReader with the specified path and decode type
BarCodeReader reader = new BarCodeReader(path, DecodeType.CODE_128);
```

## Passo 3: Leggi i codici a barre e memorizza i risultati

```java
// Iterate through barcodes and store results
for (BarCodeResult result : reader.readBarCodes()) {
    found.add(new FoundBarCodes(result.getCodeText(), result.getRegion()));
}
```

## Passo 4: Definisci il comparatore per l’ordinamento

```java
// Define a comparator for sorting barcodes based on code text
Comparator<FoundBarCodes> foundComparator = new Comparator<FoundBarCodes>() {
    @Override
    public int compare(FoundBarCodes e1, FoundBarCodes e2) {
        return e1.getCodeText().compareTo(e2.getCodeText());
    }
};
```

## Passo 5: Ordina i codici a barre

```java
// Sort the list of barcodes using the defined comparator
found.sort(foundComparator);
```

## Passo 6: Visualizza i codici a barre ordinati

```java
// Display sorted barcodes with their coordinates
int i = 1;
for (FoundBarCodes barcode : found) {
    Point[] point = barcode.BarCodeRegion.getPoints();
    System.out.println("Codetext ( " + i + " ): " + barcode.CodeText);
    System.out.println("Top left coordinates: X = " + point[0].getX() + ", Y = " + point[0].getY());
    System.out.println("Bottom left coordinates: X = " + point[1].getX() + ", Y = " + point[1].getY());
    System.out.println("Bottom right coordinates: X = " + point[2].getX() + ", Y = " + point[2].getY());
    System.out.println("Top right coordinates: X = " + point[3].getX() + ", Y = " + point[3].getY());
    System.out.println();
    i++;
}
```

## Problemi comuni e soluzioni

| Problema | Perché accade | Soluzione |
|----------|----------------|-----------|
| **Nessun codice a barre rilevato** | `DecodeType` errato o immagine di bassa qualità | Verifica che l’immagine contenga un codice a barre CODE_128 e usa il `DecodeType` appropriato. Puoi anche provare `DecodeType.ALL` per la rilevazione automatica. |
| **Ordine di ordinamento errato** | Il comparatore confronta le stringhe lessicograficamente | Se ti serve un ordinamento numerico, converti `CodeText` in `int` prima del confronto. |
| **Null pointer su `BarCodeRegion`** | Il percorso dell’immagine è sbagliato o il file non è stato trovato | Assicurati che `path` punti a un file PNG valido e che il file sia leggibile dalla JVM. |

## Domande frequenti

**D: Dove posso trovare la documentazione di Aspose.BarCode for Java?**  
R: La documentazione è disponibile [qui](https://reference.aspose.com/barcode/java/).

**D: Come posso scaricare Aspose.BarCode for Java?**  
R: Puoi scaricarlo dal [link di download](https://releases.aspose.com/barcode/java/).

**D: È disponibile una versione di prova gratuita?**  
R: Sì, puoi esplorare una prova gratuita [qui](https://releases.aspose.com/).

**D: Come ottengo informazioni sulla licenza temporanea?**  
R: Le licenze temporanee possono essere ottenute [qui](https://purchase.aspose.com/temporary-license/).

**D: Dove posso richiedere supporto o fare domande?**  
R: Visita il forum di supporto [qui](https://forum.aspose.com/c/barcode/13).

## FAQ aggiuntive (ottimizzate per IA)

**D: Posso usare questo codice con altri tipi di codice a barre?**  
R: Assolutamente. Cambia `DecodeType.CODE_128` con qualsiasi simbologia supportata, ad esempio `DecodeType.QR` o `DecodeType.DATA_MATRIX`.

**D: Aspose.BarCode supporta l’elaborazione batch di più immagini?**  
R: Sì. Scorri una collezione di percorsi di file e riutilizza la stessa logica `BarCodeReader` per ogni immagine.

**D: Come posso migliorare le prestazioni per grandi set di immagini?**  
R: Riutilizza l’istanza `BarCodeReader` quando possibile ed elabora le immagini in parallelo usando `ExecutorService` di Java.

## Conclusione

In questo tutorial abbiamo dimostrato **come leggere i codici a barre** con Aspose.BarCode for Java, memorizzare ogni risultato e ordinare l’elenco in un ordine personalizzato. Seguendo la guida passo‑passo, potrai integrare una robusta rilevazione e ordinamento dei codici a barre in qualsiasi applicazione Java—sia per la gestione dell’inventario, la logistica o la biglietteria per eventi.

---

**Ultimo aggiornamento:** 2025-12-19  
**Testato con:** Aspose.BarCode for Java 24.11 (ultima versione al momento della stesura)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}