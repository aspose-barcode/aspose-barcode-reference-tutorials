---
date: 2025-11-30
description: Scopri come valutare la qualità della lettura dei codici a barre in Java
  con Aspose.Barcode. Guida passo‑passo per recuperare la percentuale di qualità del
  riconoscimento.
language: it
linktitle: Getting Barcode Recognition Quality in Percent
second_title: Aspose.Barcode Java API
title: Aspose.Barcode Java – Ottenere la Qualità del Riconoscimento del Codice a Barre
  in Percentuale
url: /java/advanced-settings-and-optimization/getting-barcode-recognition-quality-percent/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Barcode Java – Ottenere la Qualità del Riconoscimento del Codice a Barre in Percentuale

## Introduzione

Se devi **valutare la qualità della lettura dei codici a barre** in un'applicazione Java, **Aspose.Barcode Java** offre un'API semplice che restituisce la qualità del riconoscimento come percentuale. In questo tutorial vedremo passo passo le operazioni necessarie per recuperare tale percentuale, spiegheremo perché la metrica è importante e mostreremo come integrare la chiamata nel tuo codice esistente.

## Risposte Rapide
- **Cosa significa “qualità di lettura”?** È il punteggio di fiducia (0‑100 %) che la libreria assegna a ciascun codice a barre decodificato.  
- **Quale versione della libreria è necessaria?** Qualsiasi versione recente di Aspose.Barcode Java (l'esempio utilizza la serie 24.x più recente).  
- **È necessaria una licenza?** Una licenza temporanea è sufficiente per i test; una licenza completa è obbligatoria per la produzione.  
- **Posso leggere tutti i tipi di codice a barre?** Sì – il flag `DecodeType.ALL_SUPPORTED_TYPES` abilita tutti i formati supportati da Aspose.Barcode.  
- **Il valore di qualità è affidabile per i QR code?** Assolutamente sì – lo stesso algoritmo di fiducia viene applicato a simbologie 1‑D e 2‑D.

## Che cos'è Aspose.Barcode Java e come valutare la qualità della lettura dei codici a barre?

**Aspose.Barcode Java** è una libreria completamente gestita che consente agli sviluppatori di generare, leggere e analizzare codici a barre senza dipendenze esterne. Una delle sue diagnosi più utili è la metrica **reading quality**, che indica quanto il motore ha decodificato il simbolo con fiducia. Questa metrica è fondamentale quando devi decidere se accettare una scansione, richiedere una nuova acquisizione o attivare una logica di gestione degli errori.

## Perché usare Aspose.Barcode Java per la qualità della lettura dei codici a barre?

- **Punteggi di fiducia coerenti** su tutte le simbologie supportate.  
- **Nessuna DLL nativa** – puro Java, quindi funziona su qualsiasi piattaforma compatibile con JVM.  
- **Controllo fine‑grained**: è possibile recuperare la qualità per ogni codice a barre, non solo un risultato globale di pass/fail.  
- **Motore di lettura ottimizzato per le prestazioni** che scala da desktop a servizi cloud.

## Prerequisiti

Prima di iniziare, assicurati di avere:

- **Ambiente di sviluppo Java** – JDK 8 o superiore, con il tuo IDE preferito (IntelliJ, Eclipse, VS Code, ecc.).  
- **Libreria Aspose.Barcode Java** – scarica il JAR più recente dal sito ufficiale: [Aspose.Barcode for Java](https://releases.aspose.com/barcode/java/).  
- **Un'immagine di esempio di codice a barre** – il tutorial utilizza `code39Extended.jpg` situato nella cartella `BarcodeReader/advanced_features/`.

Ora che tutto è pronto, immergiamoci nel codice.

## Importare gli Spazi dei Nomi

Le seguenti importazioni ti danno accesso alle classi del lettore e dei risultati necessarie per estrarre la qualità.

```java
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
```

### Passo 1: Impostare il Percorso della Directory delle Risorse

Definisci la cartella che contiene l'immagine di esempio. `Utils.getDataDir` è un helper che risolve il percorso assoluto per il progetto corrente.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GetBarCodeRecognitionQualityInPercent.class)
        + "BarcodeReader/advanced_features/";
```

### Passo 2: Inizializzare l'Oggetto BarCodeReader

Crea un'istanza di `BarCodeReader`, puntandola al file immagine e indicando di provare **tutti i tipi di codice a barre supportati**.

```java
// Initialize the BarCodeReader object
BarCodeReader reader = new BarCodeReader(dataDir + "code39Extended.jpg",
        com.aspose.barcode.barcoderecognition.DecodeType.ALL_SUPPORTED_TYPES);
```

### Passo 3: Leggere i Codici a Barre e Recuperare la Percentuale di Qualità

Itera su ogni codice a barre rilevato, stampa il suo testo, tipo e la percentuale di **qualità di lettura** restituita da `getReadingQuality()`.

```java
// Call the read method
for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println(result.getCodeText() + " Type: " + result.getCodeType());
    double percent = result.getReadingQuality();
    System.out.println("Percent: " + percent);
}
```

**Cosa sta succedendo?**  
- `readBarCodes()` restituisce una collezione di oggetti `BarCodeResult`, uno per ogni codice a barre trovato.  
- `getReadingQuality()` restituisce un `double` compreso tra `0` e `100`, che rappresenta il livello di fiducia.  
- Puoi usare questo valore per decidere se la scansione è accettabile o se è necessario chiedere all'utente un nuovo tentativo.

## Problemi Comuni e Soluzioni

| Problema | Causa | Soluzione |
|----------|-------|-----------|
| **Qualità sempre 0** | L'immagine è a bassa risoluzione o molto sfocata. | Usa una sorgente ad alta risoluzione o applica pre‑elaborazione dell'immagine (ad es., sharpening). |
| **Nessun codice a barre rilevato** | Flag `DecodeType` errato. | Assicurati di usare `DecodeType.ALL_SUPPORTED_TYPES` o specifica il tipo esatto che ti aspetti. |
| **Eccezione su `Utils.getDataDir`** | La struttura del progetto differisce dall'esempio. | Sostituisci la chiamata helper con un percorso assoluto hard‑coded o un percorso relativo che corrisponda al tuo layout. |

## Domande Frequenti

### Q1: Aspose.Barcode è compatibile con tutti i tipi di codice a barre?

A1: Aspose.Barcode supporta un'ampia gamma di simbologie, incluse 1‑D (Code‑39, Code‑128, UPC) e 2‑D (QR, DataMatrix, PDF417).

### Q2: Posso usare Aspose.Barcode per scopi commerciali?

A2: Sì, puoi utilizzare Aspose.Barcode sia in progetti personali che commerciali. I dettagli sulla licenza sono disponibili [qui](https://purchase.aspose.com/buy).

### Q3: Come posso ottenere una licenza temporanea per scopi di test?

A3: Ottieni una licenza temporanea dal portale Aspose [qui](https://purchase.aspose.com/temporary-license/).

### Q4: Dove posso trovare supporto aggiuntivo e discussioni della community?

A4: Visita il [forum Aspose.Barcode](https://forum.aspose.com/c/barcode/13) per supporto da parte della community e assistenza ufficiale.

### Q5: Sono disponibili esempi di codice nella documentazione?

A5: Sì, esempi di codice completi sono forniti nella documentazione ufficiale [qui](https://reference.aspose.com/barcode/java/).

## Conclusione

Sfruttando **Aspose.Barcode Java**, puoi recuperare facilmente la **percentuale di qualità della lettura del codice a barre** per qualsiasi simbolo scansionato. Questa metrica ti consente di costruire logiche di validazione più intelligenti, migliorare l'esperienza utente e mantenere un'elevata integrità dei dati nelle tue applicazioni Java.

---

**Ultimo aggiornamento:** 2025-11-30  
**Testato con:** Aspose.Barcode Java 24.11  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}