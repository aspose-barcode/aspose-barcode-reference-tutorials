---
date: 2025-12-27
description: Scopri come creare un codice a barre Data Matrix e come impostare la
  posizione del testo del codice a barre in Java usando Aspose.BarCode. Segui la nostra
  guida passo‑passo per una personalizzazione completa.
linktitle: Setting Code Text Location
second_title: Aspose.BarCode Java API
title: Crea un codice a barre Data Matrix e imposta la posizione del testo del codice
  in Java
url: /it/java/text-and-styling/setting-code-text-location/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea codice a barre Data Matrix e imposta la posizione del testo del codice in Java

## Introduzione

## Risposte rapide
- **Quale libreria viene utilizzata?** Aspose.BarCode for Java  
- **Quale tipo di codice a barre è mostrato?** Data Matrix  
- **Come si posiziona il testo del codice?** Utilizzando `CodeLocation.ABOVE`  
- **È necessaria una licenza per la produzione?** Sì, è richiesta una licenza commerciale  
- **Il codice può essere eseguito su Java 8+?** Assolutamente, supporta Java 8 e versioni successive  

## Che cos'è un codice a barre Data Matrix?
Un codice a barre Data Matrix è un simbolo bidimensionale (2‑D) che memorizza grandi quantità di dati in un pattern compatto quadrato o rettangolare. È ampiamente utilizzato per contrassegnare piccoli oggetti, elettronica e dispositivi medici perché può codificare fino a 2.335 caratteri alfanumerici.

## Perché impostare la posizione del testo del codice a barre?
Posizionare il testo leggibile dall'uomo **sopra**, **sotto** o **accanto** al codice a barre aiuta gli utenti a verificare rapidamente i dati codificati senza dover scansionare. Regolare la posizione del testo migliora la coerenza dell'interfaccia utente e soddisfa le linee guida del marchio.

## Prerequisiti

- Conoscenze di base della programmazione Java.  
- Java Development Kit (JDK) installato.  
- Un IDE come Eclipse o IntelliJ IDEA.  
- Libreria Aspose.BarCode per Java (download it from [here](https://releases.aspose.com/barcode/java/)).  

## Importa pacchetti

Per prima cosa, importa le classi essenziali di Aspose.BarCode nel tuo progetto:

```java
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Guida passo‑passo

### Passo 1: Definisci i percorsi delle directory
Specifica dove desideri leggere/scrivere i file. Sostituisci i segnaposto con i percorsi reali sul tuo computer.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

### Passo 2: Crea un'istanza di BarcodeGenerator
Istanzia `BarcodeGenerator` con il tipo **Data Matrix** e fornisci il testo del codice che desideri codificare.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DATA_MATRIX,
        "GTIN:898978777776665655 " + "UID: 121212121212121212 " + "Batch:GH768 " + "Exp.Date:150923");
```

### Passo 3: Come impostare la posizione del testo del codice a barre
Utilizza l'enumerazione `CodeLocation` per spostare il testo leggibile dall'uomo. In questo esempio lo posizioniamo **sopra** il codice a barre.

```java
generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.ABOVE);
```

### Passo 4: Salva l'immagine del codice a barre generato
Infine, scrivi l'immagine del codice a barre su disco. Il file conterrà il simbolo Data Matrix con il testo posizionato sopra.

```java
generator.save(dataDir + "codetextAbove.png");
```

## Problemi comuni e soluzioni
- **Testo non visualizzato:** Assicurati di utilizzare una versione di Aspose.BarCode che supporta `CodeLocation`.  
- **Errori di percorso file:** Verifica che `dataDir` termini con un separatore di file (`/` o `\\`) appropriato per il tuo OS.  
- **Caratteri non supportati:** Data Matrix può codificare solo un insieme limitato di caratteri; evita simboli speciali non presenti nello standard ISO/IEC 16022.

## Domande frequenti (FAQ)

### Q: Posso personalizzare l'aspetto del codice a barre generato?
A: Sì, Aspose.BarCode fornisce ampie opzioni di personalizzazione, consentendo di controllare colori, margini e stili di carattere.

### Q: Aspose.BarCode è compatibile con Java 8 e versioni successive?
A: Assolutamente, la libreria funziona con Java 8 e tutte le versioni successive.

### Q: Come posso integrare Aspose.BarCode nel mio progetto Java esistente?
A: Aggiungi i file JAR di Aspose.BarCode al classpath del tuo progetto, importa i pacchetti necessari e sei pronto a generare codici a barre.

### Q: È disponibile una versione di prova per Aspose.BarCode?
A: Sì, puoi esplorare le funzionalità di Aspose.BarCode ottenendo una prova gratuita [here](https://releases.aspose.com/).

### Q: Dove posso trovare aiuto o supporto per Aspose.BarCode?
A: Visita il [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) per assistenza della community e supporto ufficiale.

## Altre domande frequenti

**Q: Posso generare un codice a barre con il testo posizionato sotto il simbolo?**  
A: Sì, imposta `CodeLocation.BELOW` nello stesso metodo `setLocation`.

**Q: La libreria supporta altri codici a barre 2‑D come QR Code?**  
A: Assolutamente, basta cambiare `EncodeTypes.DATA_MATRIX` in `EncodeTypes.QR`.

**Q: Come posso modificare la dimensione del carattere del testo del codice a barre?**  
A: Usa `generator.getParameters().getBarcode().getCodeTextParameters().setFontSize(double size)`.

## Conclusione

Hai ora imparato come **creare un codice a barre Data Matrix** in Java e controllare con precisione **come impostare la posizione del testo del codice a barre** utilizzando Aspose.BarCode. Sperimenta con altri valori di `CodeLocation` e opzioni di stile per soddisfare i requisiti di design della tua applicazione.

---

**Ultimo aggiornamento:** 2025-12-27  
**Testato con:** Aspose.BarCode for Java 24.11  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}