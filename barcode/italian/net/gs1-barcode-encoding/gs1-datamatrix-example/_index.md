---
date: 2026-02-22
description: Scopri come creare immagini di codici a barre in C# usando Aspose.BarCode
  per .NET e generare codici a barre GS1 DataMatrix in modo rapido ed efficiente.
linktitle: GS1 DataMatrix Example
second_title: Aspose.BarCode .NET API
title: Crea immagine di codice a barre C# – Esempio GS1 DataMatrix
url: /it/net/gs1-barcode-encoding/gs1-datamatrix-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Esempio GS1 DataMatrix

Se stai cercando un modo affidabile per **create barcode image C#** nelle tue applicazioni .NET, Aspose.BarCode per .NET rende il processo semplice. Questa potente libreria supporta un'ampia gamma di simbologie, inclusa GS1 DataMatrix, e fornisce un'API pulita che ti permette di concentrarti sulla logica di business invece che sui dettagli a basso livello del codice a barre. Nei prossimi minuti, ti guideremo attraverso un esempio completo e pratico che mostra come generare un codice a barre GS1 DataMatrix, personalizzarne l'aspetto e salvarlo come file immagine.

## Risposte Rapide
- **Cosa genera l'esempio?** Un codice a barre GS1 DataMatrix contenente dati di prodotto di esempio.  
- **Quale libreria viene utilizzata?** Aspose.BarCode per .NET.  
- **Posso cambiare il formato di output?** Sì, puoi salvare come PNG, JPEG, BMP, ecc.  
- **È necessaria una licenza per lo sviluppo?** Una prova gratuita è sufficiente per i test; è richiesta una licenza commerciale per la produzione.  
- **Il codice è compatibile con .NET Core?** Assolutamente – la stessa API funziona su .NET Framework e .NET Core/5/6.

## Che cos'è un codice a barre GS1 DataMatrix?
Una GS1 DataMatrix è un codice a barre bidimensionale che codifica informazioni a livello di prodotto (come GTIN, numero di serie e identificatori di applicazione aggiuntivi). È ampiamente utilizzata nel retail, nella sanità e nella logistica per l'archiviazione compatta e ad alta densità dei dati.

## Perché usare Aspose.BarCode per creare barcode image C#?
- **API completa** – supporta gli standard GS1, la correzione degli errori e il controllo delle dimensioni.  
- **Nessuna dipendenza esterna** – libreria .NET pura, facile da integrare.  
- **Cross‑platform** – funziona su Windows, Linux e macOS.  
- **Documentazione estesa** – include esempi come questo per iniziare rapidamente.

## Prerequisiti

Prima di immergerci nel tutorial, assicurati di avere i seguenti prerequisiti:

1. **Aspose.BarCode per .NET** – È necessario avere Aspose.BarCode per .NET installato. Se non l'hai ancora fatto, puoi [scaricarlo qui](https://releases.aspose.com/barcode/net/).  
2. **Ambiente di sviluppo** – Dovresti avere un ambiente di sviluppo .NET configurato sul tuo sistema (Visual Studio, VS Code o qualsiasi IDE tu preferisca).

Ora che i prerequisiti sono pronti, iniziamo a generare codici a barre GS1 DataMatrix.

## Importa gli Spazi dei Nomi

Per prima cosa, importa gli spazi dei nomi necessari per lavorare con Aspose.BarCode per .NET. Questi spazi dei nomi ti danno accesso alle funzionalità di generazione del codice a barre.

```csharp
using Aspose.BarCode;
using System;
```

## Come creare barcode image C# – Guida passo‑passo

### Passo 1: Configura il Generatore di Codice a Barre

Per iniziare, crea un'istanza `BarcodeGenerator` e specifica la simbologia **GS1 DataMatrix** insieme ai dati che desideri codificare. In questo esempio codifichiamo la stringa **"(01)12345678901231(21)ASPOSE(30)9876"**, che segue il formato degli Identificatori di Applicazione GS1.

```csharp
// The path to the documents directory.
string path = "Your Directory Path";
System.Console.WriteLine("Gs1DataMatrixExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1DataMatrix, "(01)12345678901231(21)ASPOSE(30)9876");
```

*Consiglio professionale:* Sostituisci i dati di esempio con i tuoi identificatori GS1 per adattarli al catalogo prodotti.

### Passo 2: Personalizza le Proprietà del Codice a Barre

Puoi modellare l'aspetto del codice a barre usando l'oggetto `Parameters`. Qui impostiamo la X‑dimension (la dimensione del modulo più piccolo) a 8 pixel e definiamo una dimensione della matrice di 36 colonne per 12 righe. Regola questi valori per soddisfare i requisiti di scansione.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 8;
gen.Parameters.Barcode.DataMatrix.Columns = 36;
gen.Parameters.Barcode.DataMatrix.Rows = 12;
```

*Perché regolare la X‑dimension?* Una X‑dimension più grande rende il codice a barre più facile da leggere su dispositivi a bassa risoluzione, mentre un valore più piccolo riduce le dimensioni dell'immagine.

### Passo 3: Salva l'Immagine del Codice a Barre

Infine, salva il codice a barre generato su disco. L'esempio utilizza PNG, ma puoi scegliere tra JPEG, GIF, BMP e altri formati supportati da Aspose.BarCode.

```csharp
gen.Save($"{path}Gs1DataMatrixExample.png", BarCodeImageFormat.Png);
```

Quando esegui il codice, troverai **Gs1DataMatrixExample.png** nella cartella specificata, pronto per essere usato su etichette, imballaggi o applicazioni digitali.

## Casi d'Uso Comuni

- **Etichettatura di prodotti al dettaglio** – Codifica GTIN, numeri di lotto e date di scadenza.  
- **Tracciamento farmaceutico** – Soddisfa i requisiti normativi con dati conformi a GS1.  
- **Logistica di magazzino** – Memorizza in modo compatto informazioni su posizione e inventario.  

## Risoluzione dei Problemi e Suggerimenti

- **Formato dati errato** – Assicurati che la tua stringa segua la sintassi degli Identificatori di Applicazione GS1; altrimenti il codice a barre potrebbe non essere leggibile.  
- **Problemi di dimensione immagine** – Se l'immagine generata appare sfocata, aumenta il valore di `XDimension.Pixels`.  
- **Errori di licenza** – Una licenza di prova funziona per la valutazione, ma è necessaria una licenza completa per le distribuzioni in produzione.

## Domande Frequenti

### Che cos'è GS1 DataMatrix?
GS1 DataMatrix è una simbologia di codice a barre bidimensionale utilizzata per codificare dati relativi a prodotti e alla loro identificazione, particolarmente nel retail e nella sanità.

### Aspose.BarCode per .NET è adatto ad altri tipi di codice a barre?
Sì, Aspose.BarCode per .NET supporta un'ampia gamma di tipi di codice a barre, rendendolo versatile per diverse applicazioni.

### Posso generare codici a barre in altri formati immagine oltre al PNG?
Sì, Aspose.BarCode per .NET consente di salvare i codici a barre generati in vari formati immagine, come JPEG, GIF e BMP, oltre al PNG.

### È necessaria una licenza per usare Aspose.BarCode per .NET?
Sì, è richiesta una licenza valida per l'uso commerciale di Aspose.BarCode per .NET. Puoi ottenere una licenza dal [sito web di Aspose](https://purchase.aspose.com/buy).

### Dove posso ottenere supporto per Aspose.BarCode per .NET?
Puoi trovare risposte alle tue domande e richiedere assistenza nel [forum di Aspose.BarCode per .NET](https://forum.aspose.com/c/barcode/13).

## FAQ Aggiuntive (Ottimizzate AI)

**D: Come genero un codice a barre DataMatrix in C# senza formattazione GS1?**  
R: Usa `EncodeTypes.DataMatrix` invece di `EncodeTypes.GS1DataMatrix` e fornisci la stringa di dati semplice al `BarcodeGenerator`.

**D: Posso cambiare i colori del codice a barre programmaticamente?**  
R: Sì, imposta `gen.Parameters.Barcode.ForeColor` e `gen.Parameters.Barcode.BackColor` per personalizzare i colori di primo piano e di sfondo.

**D: È possibile incorporare direttamente il codice a barre generato in un PDF?**  
R: Assolutamente – recupera il codice a barre come `System.Drawing.Image` e aggiungilo a un PDF usando Aspose.PDF o qualsiasi altra libreria PDF.

**D: Quali versioni di .NET sono supportate?**  
R: Aspose.BarCode per .NET supporta .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6 e versioni successive.

**D: Come posso migliorare l'affidabilità della scansione per etichette piccole?**  
R: Aumenta la X‑dimension, aggiungi zone di quiete (`gen.Parameters.Barcode.Margin`) e assicurati di avere un contrasto sufficiente tra il codice a barre e lo sfondo.

## Conclusione

In questo tutorial, abbiamo esplorato come **create barcode image C#** usando Aspose.BarCode per .NET per generare un codice a barre GS1 DataMatrix. Con poche righe di codice puoi incorporare codici a barre di alta qualità nelle tue applicazioni, sia che tu stia costruendo soluzioni per il retail, sistemi sanitari o piattaforme logistiche. Esplora ulteriormente la libreria per scoprire simbologie aggiuntive, opzioni di rendering avanzate e scenari di integrazione.

Per ulteriori informazioni e documentazione dettagliata, consulta la [documentazione di Aspose.BarCode per .NET](https://reference.aspose.com/barcode/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ultimo aggiornamento:** 2026-02-22  
**Testato con:** Aspose.BarCode per .NET (latest version)  
**Autore:** Aspose