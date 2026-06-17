---
date: 2026-02-25
description: Scopri come generare un'immagine di codice a barre e salvare il PNG del
  codice a barre utilizzando Aspose.BarCode per .NET – un esempio completo di Aspose
  Barcode.
linktitle: One-Dimensional Code 93 Configuration
second_title: Aspose.BarCode .NET API
title: Genera immagine di codice a barre – Code 93 con Aspose.BarCode
url: /it/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Genera immagine barcode – Codice unidimensionale 93 con Aspose.BarCode

## Introduzione

Nel mondo digitale odierno, i codici a barre sono diventati una parte integrante della nostra vita, semplificando processi come la gestione dell'inventario, l'etichettatura dei prodotti e il tracciamento al punto vendita. **Generare un'immagine barcode** è spesso il primo passo per integrare questi identificatori nelle tue applicazioni. Aspose.BarCode per .NET fornisce un'API robusta e facile da usare che ti consente di creare codici a barre Code 93 di alta qualità con poche righe di codice C#. Che tu stia costruendo un sistema di magazzino, un'app retail o uno strumento di reporting personalizzato, questo tutorial ti guida attraverso un **esempio di barcode aspose** completo che mostra come generare, personalizzare e **salvare barcode PNG**.

## Risposte rapide
- **Di cosa tratta il tutorial?** Creare e salvare un'immagine barcode Code 93 con gestione del checksum.  
- **Quale libreria viene utilizzata?** Aspose.BarCode per .NET (ultima versione stabile).  
- **È necessaria una licenza?** Una versione di prova gratuita funziona per lo sviluppo; è necessaria una licenza commerciale per la produzione.  
- **Posso cambiare il formato di output?** Sì – puoi salvare come PNG, JPEG, BMP, ecc., modificando il `BarCodeImageFormat`.  
- **Quali sono i requisiti minimi?** .NET Framework 4.6+ o .NET Core 3.1+ e Visual Studio.

## Cos'è un barcode Code 93?

Code 93 è una simbologia alfanumerica ad alta densità che supporta l'intero set di caratteri ASCII. Viene spesso scelta per le sue dimensioni compatte e per il checksum integrato, che aiuta a garantire l'integrità dei dati durante la scansione.

## Perché generare immagini barcode con Aspose.BarCode?

- **Controllo totale** sul tipo di codifica, checksum, dimensione e formato immagine.  
- **Nessuna dipendenza esterna** – la libreria funziona su qualsiasi piattaforma .NET.  
- **Qualità di rendering eccellente**, adatta sia per la visualizzazione su schermo sia per la stampa ad alta risoluzione.  
- **Documentazione completa** e un ampio set di esempi che accelerano lo sviluppo.

## Prerequisiti

Prima di immergerci nel codice, assicurati di avere quanto segue:

1. **Visual Studio** (qualsiasi edizione recente).  
2. **Aspose.BarCode per .NET** installato – puoi ottenerlo dalla pagina di download ufficiale.  
3. Familiarità di base con **C#** e la struttura dei progetti .NET.

Ora che sei pronto, passiamo alla guida passo‑passo.

## Importa gli spazi dei nomi

Per prima cosa, importa gli spazi dei nomi richiesti in modo da poter accedere alle classi di generazione del barcode.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## Passo 1: Imposta il percorso della directory

Definisci dove verrà salvata l'immagine barcode generata. Sostituisci il segnaposto con una cartella valida sul tuo computer.

```csharp
string path = "Your Directory Path";
```

## Passo 2: Crea un barcode Code 93 unidimensionale

Istanzia un `BarcodeGenerator` con il tipo `Code93Extended` e i dati che desideri codificare.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code93Extended, "CODE");
```

## Passo 3: Abilita il checksum (opzionale)

Code 93 include un checksum per impostazione predefinita. Puoi attivarlo/disattivarlo usando la proprietà `IsChecksumEnabled`.

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
```

## Passo 4: Salva l'immagine barcode (Salva barcode PNG)

Genera l'immagine e salvala come file PNG nella cartella specificata in precedenza.

```csharp
gen.Save($"{path}OneCSCode93WithChecksum.png", BarCodeImageFormat.Png);
```

## Passo 5: Gestione delle eccezioni – Generazione senza checksum

Se devi creare un barcode **senza** checksum, devi gestire le eventuali eccezioni che potrebbero verificarsi.

```csharp
try
{
    gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.No;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

### Problemi comuni e soluzioni
- **Percorso non valido** – assicurati che la directory esista e che l'applicazione abbia i permessi di scrittura.  
- **Caratteri non supportati** – Code 93 supporta l'intero set ASCII, ma i caratteri di controllo possono causare errori.  
- **Licenza non impostata** – senza una licenza valida, la libreria funziona in modalità di valutazione e può aggiungere una filigrana.

## Domande frequenti (FAQ)

### Q: Dove posso trovare la documentazione per Aspose.BarCode per .NET?
A: Puoi trovare la documentazione su [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/).

### Q: Come scarico Aspose.BarCode per .NET?
A: Puoi scaricare Aspose.BarCode per .NET dal sito web su [Aspose.BarCode for .NET Download](https://releases.aspose.com/barcode/net/).

### Q: È disponibile una versione di prova gratuita per Aspose.BarCode per .NET?
A: Sì, puoi ottenere una versione di prova gratuita di Aspose.BarCode per .NET da [qui](https://releases.aspose.com/).

### Q: Come posso acquistare una licenza per Aspose.BarCode per .NET?
A: Puoi acquistare una licenza dalla pagina di acquisto su [Aspose.BarCode for .NET Purchase](https://purchase.aspose.com/buy).

### Q: Dove posso ottenere supporto o fare domande su Aspose.BarCode per .NET?
A: Puoi trovare un forum della community per supporto e discussioni su [Aspose.BarCode for .NET Support](https://forum.aspose.com/c/barcode/13).

---

**Ultimo aggiornamento:** 2026-02-25  
**Testato con:** Aspose.BarCode 24.11 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}