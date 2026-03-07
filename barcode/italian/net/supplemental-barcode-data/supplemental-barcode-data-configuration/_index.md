---
date: 2026-03-07
description: Scopri come creare un codice a barre EAN‑13 con dati supplementari in
  C# usando Aspose.BarCode per .NET – genera rapidamente un PNG del codice a barre.
linktitle: Supplemental Barcode Data Configuration
second_title: Aspose.BarCode .NET API
title: Crea codice a barre EAN‑13 con dati supplementari – Aspose.BarCode
url: /it/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Creare un codice a barre EAN-13 con dati supplementari – Aspose.BarCode per .NET

In questo tutorial pratico **creerai un codice a barre EAN-13** che include dati supplementari EAN‑2 o EAN‑5, e vedrai come **generare file PNG del codice a barre** con poche righe di C#. Che tu stia costruendo un sistema di cassa al dettaglio, un’applicazione logistica o un semplice strumento di inventario, la possibilità di aggiungere informazioni supplementari rende i tuoi codici a barre molto più utili.

## Risposte rapide
- **Cosa significa “dati supplementari”?** Cifre extra (EAN‑2/EAN‑5) stampate accanto al codice a barre principale, spesso usate per prezzi o numeri di edizione.  
- **Quale tipo di codice a barre viene usato?** EAN‑13 come simbolo primario, con supplementi opzionali EAN‑2 o EAN‑5.  
- **Posso generare immagini PNG?** Sì – il metodo `Save` consente di esportare direttamente in PNG.  
- **È necessaria una licenza per lo sviluppo?** Una versione di prova gratuita è sufficiente per i test; per la produzione è richiesta una licenza commerciale.  
- **È compatibile con .NET Core / .NET 6?** Assolutamente – Aspose.BarCode supporta tutti i runtime .NET moderni.

## Prerequisiti

Prima di immergerti nel codice, assicurati di avere:

- Visual Studio (o qualsiasi IDE compatibile con .NET).  
- Una copia di Aspose.BarCode per .NET – scaricala **[qui](https://releases.aspose.com/barcode/net/)**.  
- Conoscenze di base di C#.  
- Una cartella scrivibile dove verranno salvati i file PNG generati.

## Importazione degli spazi dei nomi

Per prima cosa, aggiungi lo spazio dei nomi Aspose.BarCode così da poter accedere alle classi del generatore:

```csharp
using Aspose.BarCode.Generation;
```

> **Suggerimento:** Se utilizzi .NET Core, aggiungi il pacchetto NuGet `Aspose.BarCode` al tuo progetto invece di fare riferimento manualmente al DLL.

## Cos’è un codice a barre supplementare?

Un codice a barre supplementare è una stringa numerica ausiliaria stampata accanto al codice a barre principale.  
- **EAN‑2** – supplemento a due cifre, spesso usato per i numeri di edizione delle riviste.  
- **EAN‑5** – supplemento a cinque cifre, comunemente usato per le estensioni di prezzo sui prodotti al dettaglio.

L’aggiunta di questi supplementi non modifica i dati primari EAN‑13; fornisce semplicemente un contesto extra che gli scanner possono leggere.

## Perché usare Aspose.BarCode per i dati supplementari?

- **API a una riga** – configura sia il codice a barre principale sia il suo supplemento in un unico oggetto.  
- **Controllo totale sulle dimensioni** – regola la dimensione X, lo spazio del supplemento e il formato immagine.  
- **Cross‑platform** – funziona su .NET Framework, .NET Core e .NET 5/6+.  

## Guida passo‑passo

### Passo 1: Configurare la directory di output

Definisci dove verranno salvati i file PNG. Sostituisci il segnaposto con un percorso reale sulla tua macchina.

```csharp
string path = "Your Directory Path";
```

### Passo 2: Inizializzare il generatore di codici a barre (Barcode Generator C#)

Crea un’istanza di `BarcodeGenerator`, specificando **EAN‑13** come tipo principale e fornendo il payload a 13 cifre.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

### Passo 3: Regolare le dimensioni del codice a barre

Affina le dimensioni visive del codice a barre e lo spazio riservato al supplemento.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

### Passo 4: Aggiungere un supplemento EAN‑2

Imposta i dati supplementari a un valore a due cifre (ad es., “12”). Questo apparirà a destra del codice a barre principale.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

### Passo 5: Salvare il codice a barre EAN‑2 come PNG

Esporta l’immagine. L’argomento `BarCodeImageFormat.Png` garantisce un file PNG di alta qualità.

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

### Passo 6: Passare a un supplemento EAN‑5

Modifica la proprietà `SupplementData` con una stringa a cinque cifre per le estensioni di prezzo.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

### Passo 7: Salvare il codice a barre EAN‑5 come PNG

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

> **Perché funziona:** La stessa istanza di `BarcodeGenerator` viene riutilizzata, quindi è sufficiente modificare la proprietà `SupplementData` prima di ogni chiamata a `Save`. Questo mantiene il codice conciso ed evita la creazione di oggetti non necessari.

## Problemi comuni e suggerimenti

- **Percorso della directory non valido** – assicurati che la cartella esista e che l’applicazione abbia i permessi di scrittura.  
- **Lunghezza del supplemento errata** – EAN‑2 richiede esattamente 2 cifre, EAN‑5 richiede 5; altrimenti viene sollevata un’eccezione.  
- **Immagine non visibile** – verifica che venga usato `BarCodeImageFormat.Png`; altri formati (ad es., JPEG) possono introdurre artefatti di compressione che influenzano la leggibilità da parte dello scanner.  

## Domande frequenti

### Posso usare Aspose.BarCode per .NET nel mio progetto .NET Core?
Sì, Aspose.BarCode per .NET è pienamente compatibile con .NET Core, .NET 5 e .NET 6.

### È disponibile una versione di prova gratuita per Aspose.BarCode per .NET?
Sì, puoi provarla gratuitamente visitando **[questo link](https://releases.aspose.com/)**.

### Dove posso ottenere una licenza temporanea per Aspose.BarCode per .NET?
Puoi ottenere una licenza temporanea da **[questo link](https://purchase.aspose.com/temporary-license/)**.

### Aspose.BarCode supporta un’ampia gamma di tipi di codice a barre?
Assolutamente – supporta EAN‑13, QR Code, Code 128, DataMatrix, PDF‑417 e molti altri.

### Posso personalizzare l’aspetto dei codici a barre generati?
Sì, puoi modificare colori, caratteri, margini e persino aggiungere immagini di sfondo usando l’ampia API `Parameters`.

## Conclusione

Ora sai come **creare un codice a barre EAN-13** con dati supplementari EAN‑2 o EAN‑5 e **generare file PNG del codice a barre** usando Aspose.BarCode per .NET. Questo approccio ti offre il pieno controllo su dimensioni, spaziatura del supplemento e formato di output, rendendolo ideale per il retail, la logistica e qualsiasi scenario in cui siano richieste informazioni numeriche aggiuntive.

Per approfondire, consulta la guida di riferimento completa: **[documentazione di Aspose.BarCode per .NET](https://reference.aspose.com/barcode/net/)**.

---

**Ultimo aggiornamento:** 2026-03-07  
**Testato con:** Aspose.BarCode 24.11 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}