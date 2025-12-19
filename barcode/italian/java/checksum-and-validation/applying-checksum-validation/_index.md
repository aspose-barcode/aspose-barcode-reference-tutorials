---
date: 2025-12-19
description: Scopri come disabilitare la convalida del checksum in Java con Aspose.BarCode.
  Questa guida passo passo ti mostra come leggere i codici a barre, disattivare il
  checksum e garantire una gestione affidabile dei dati.
linktitle: How to Disable Checksum Validation
second_title: Aspose.BarCode Java API
title: Come disabilitare la convalida del checksum in Java
url: /it/java/checksum-and-validation/applying-checksum-validation/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come disabilitare la convalida del checksum in Java

Nelle moderne applicazioni di inventario e logistica, **come disabilitare il checksum** può essere la chiave per leggere codici a barre legacy che non includono una cifra di checksum. Aspose.BarCode per Java rende semplice disattivare la convalida del checksum mantenendo l'estrazione dei dati codificati. Questo tutorial ti guida attraverso l'intero processo—dalla configurazione del progetto alla lettura di un codice a barre ONE‑CODE senza verifica del checksum.

## Risposte rapide
- **Cosa fa la disattivazione del checksum?** Indica al lettore di ignorare il campo checksum, consentendo la lettura di codici a barre senza un checksum valido.  
- **Quando dovresti disabilitare il checksum?** Quando si lavora con sistemi legacy o codici a barre non standard che omettono o corrompono il checksum.  
- **Quale classe controlla la convalida del checksum?** `BarCodeReader.setChecksumValidation(ChecksumValidation)`  
- **È sicuro disabilitare il checksum?** Solo se ti fidi della fonte del codice a barre; altrimenti, la convalida aiuta a rilevare errori.  
- **Questo influisce su altri tipi di codice a barre?** L'impostazione si applica solo all'istanza corrente di `BarCodeReader`.

## Cos'è la convalida del checksum?
La convalida del checksum è un controllo di integrità dei dati che calcola un piccolo valore dal contenuto del codice a barre e lo confronta con il checksum incorporato. Se non corrispondono, il codice a barre è considerato illeggibile. Disabilitare questo controllo indica ad Aspose.BarCode di saltare il confronto.

## Perché disabilitare il checksum con Aspose.BarCode?
- **Supporto legacy:** I vecchi scanner spesso generavano codici a barre senza checksum.  
- **Prestazioni:** Saltare il calcolo può accelerare la lettura di grandi volumi.  
- **Flessibilità:** Puoi decidere per ogni istanza del lettore se applicare la convalida.

## Prerequisiti
- **Java Development Kit (JDK):** Assicurati di avere installato l'ultima versione del JDK.  
- **Libreria Aspose.BarCode:** Scarica la libreria dal sito ufficiale [qui](https://releases.aspose.com/barcode/java/).  

## Importa i pacchetti
Nel tuo progetto Java, importa le classi Aspose.BarCode necessarie per lavorare con il riconoscimento dei codici a barre.

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.ChecksumValidation;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## Guida passo‑passo

### Passo 1: Configura il tuo progetto
Crea un nuovo progetto Java (IDE a tua scelta) e aggiungi il JAR di Aspose.BarCode al classpath del progetto.

### Passo 2: Inizializza `BarCodeReader`
Carica l'immagine che contiene il codice a barre ONE‑CODE che desideri leggere.

```java
String dataDir = "Your Document Directory";
BarCodeReader reader = new BarCodeReader(dataDir + "onecode.png", DecodeType.ONE_CODE);
```

### Passo 3: Come disabilitare il checksum
Indica al lettore di ignorare la convalida del checksum impostando la proprietà su `OFF`.

```java
reader.setChecksumValidation(ChecksumValidation.OFF);
```

### Passo 4: Leggi i codici a barre
Itera sui risultati e stampa il testo decodificato e il tipo di simbologia.

```java
for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("CodeText: " + result.getCodeText());
    System.out.println("Symbology type: " + result.getCodeType());
}
```

**Risultato:** Il testo del codice a barre viene visualizzato anche se l'immagine originale non contiene un checksum valido.

## Problemi comuni e consigli
- **Percorso file errato:** Verifica che `dataDir` punti alla cartella corretta; usa percorsi assoluti per i test.  
- **Tipo di codice a barre non supportato:** Assicurati che `DecodeType` corrisponda al codice a barre che stai leggendo.  
- **Prestazioni:** Disabilitare il checksum su grandi lotti può migliorare il throughput, ma riattivalo sempre per dati critici.

## Domande frequenti

### Aspose.BarCode è compatibile con diversi tipi di codice a barre?
Sì, Aspose.BarCode supporta un'ampia gamma di simbologie di codici a barre, da QR e DataMatrix a codici lineari tradizionali.

### Posso utilizzare Aspose.BarCode per scopi commerciali?
Assolutamente. Licenze commerciali sono disponibili per le aziende che necessitano di funzionalità pronte per la produzione.

### Come posso ottenere supporto per Aspose.BarCode?
Visita il [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13) per entrare in contatto con la community e ricevere assistenza dal team di prodotto.

### È disponibile una versione di prova gratuita?
Sì, puoi esplorare l'intero set di funzionalità scaricando la [versione di prova gratuita](https://releases.aspose.com/).

### Dove posso trovare la documentazione dettagliata?
Consulta la completa [documentazione](https://reference.aspose.com/barcode/java/) per i dettagli dell'API, esempi di codice e best practice.

---

**Last Updated:** 2025-12-19  
**Tested With:** Aspose.BarCode for Java (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}