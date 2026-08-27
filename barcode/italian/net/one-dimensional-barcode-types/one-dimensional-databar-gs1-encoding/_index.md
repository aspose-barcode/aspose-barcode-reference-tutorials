---
date: 2026-03-07
description: Scopri come creare codici a barre databar unidimensionali codificati
  GS1 in .NET utilizzando Aspose.BarCode. Questa guida mostra come impostare GS1,
  configurare il generatore di codici a barre e generare rapidamente i codici a barre.
linktitle: One-Dimensional Databar GS1 Encoding
second_title: Aspose.BarCode .NET API
title: Crea codifica GS1 DataBar unidimensionale con Aspose.BarCode
url: /it/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea Codici Databar Unidimensionali con Codifica GS1 usando Aspose.BarCode

In questo tutorial **creerai codici a barre databar unidimensionali** conformi allo standard GS1, utilizzando la libreria Aspose.BarCode per .NET. Che tu abbia bisogno di una convalida GS1 rigorosa o di un codice a barre più flessibile, ti guideremo passo passo — dall'installazione della libreria alla gestione delle eccezioni di codifica — così potrai generare codici a barre affidabili nelle tue applicazioni.

## Risposte Rapide
- **Cosa significa “creare un databar unidimensionale”?** Significa generare un codice a barre lineare (1‑D) della famiglia Databar, spesso usato per il retail e la logistica.  
- **Come impostare la convalida GS1?** Imposta `IsAllowOnlyGS1Encoding` su `true` nei parametri `DataBar`.  
- **È necessaria una licenza?** Una versione di prova gratuita è sufficiente per lo sviluppo; per la produzione è necessaria una licenza commerciale.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Dove posso scaricare la libreria?** Dalla pagina ufficiale di rilascio di Aspose (vedi i prerequisiti).

## Cos'è “creare un databar unidimensionale”?
Un Databar unidimensionale (noto anche come RSS) è un codice a barre lineare compatto che può codificare dati numerici, date o stringhe AI (Application Identifier). Quando associato alla codifica GS1, il codice a barre segue una struttura dati riconosciuta a livello globale, rendendolo ideale per scenari di retail, assistenza sanitaria e catena di fornitura.

## Perché utilizzare Aspose.BarCode per .NET?
Aspose.BarCode offre un'API fluida, supporto completo a GS1 e la possibilità di perfezionare ogni aspetto visivo del codice a barre. Elimina le ipotesi della codifica a basso livello e ti consente di concentrarti sulla logica di business.

## Prerequisiti

1. **Aspose.BarCode per .NET** – scaricala e installala da [qui](https://releases.aspose.com/barcode/net/).  
2. **Il tuo percorso di directory** – sostituisci `"Your Directory Path"` nei campioni con una cartella in cui hai i permessi di scrittura.

## Importazione dei Namespace

Aggiungi le istruzioni `using` richieste all'inizio del tuo file C#:

```csharp
using Aspose.BarCode;
using System;
```

## Passo 1: Inizializzare il Generatore di Codici a Barre

Crea un'istanza di `BarcodeGenerator` e specifica la simbologia Databar Expanded:

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## Passo 2: Come impostare GS1 – Generare un codice a barre con convalida GS1 rigorosa

Abilita la codifica solo GS1, assegna un codetext conforme a GS1 e salva l'immagine:

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## Passo 3: Generazione di codici a barre con Aspose – Codifica variabile (senza verifica GS1)

Se ti serve un codice a barre che **non** impone le regole GS1, disattiva il controllo:

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## Passo 4: Controllo GS1 del generatore di codici a barre – Gestione di un'eccezione

Quando `IsAllowOnlyGS1Encoding` è `true` ma il codetext non è conforme a GS1, Aspose genera un'eccezione. Il modello seguente mostra come catturarla e registrarla:

```csharp
try
{
    gen.CodeText = "ASPOSE";
    gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

### Problemi Comuni e Suggerimenti
- **Problema:** Fornire una stringa non‑GS1 mentre il controllo GS1 è abilitato interromperà la generazione del codice a barre.  
- **Suggerimento professionale:** Convalida le tue stringhe AI prima di assegnarle a `CodeText` per evitare errori a runtime.  
- **Consiglio:** Usa percorsi assoluti o `Path.Combine` per costruire i nomi dei file in modo sicuro su tutte le piattaforme.

## Conclusione

Ora sai come **creare codici a barre databar unidimensionali** con codifica GS1, come attivare o disattivare il controllo GS1 e come gestire le relative eccezioni — tutto usando Aspose.BarCode per .NET. Sentiti libero di esplorare ulteriori opzioni di stile come dimensione, colore e margini del codice a barre tramite l'oggetto `Parameters.Barcode`.

Se incontri problemi, la documentazione ufficiale e il forum della community sono ottime risorse:

- [Documentazione di Aspose.BarCode](https://reference.aspose.com/barcode/net/)  
- [Forum di supporto di Aspose.BarCode](https://forum.aspose.com/c/barcode/13)

## Domande Frequenti

### 1. Cos'è la codifica GS1 nei codici a barre?
La codifica GS1 è un metodo standardizzato per strutturare i dati (ad esempio identificatori di prodotto) all'interno di un codice a barre, garantendo l'interoperabilità tra retailer, produttori e fornitori di logistica.

### 2. Posso personalizzare l'aspetto dei codici a barre generati?
Sì. Aspose.BarCode ti consente di regolare dimensioni, colori, margini e persino aggiungere testo leggibile dall'uomo tramite le impostazioni `Parameters.Barcode`.

### 3. Dove posso trovare risorse aggiuntive e documentazione per Aspose.BarCode?
Puoi trovare una documentazione completa e esempi su [Documentazione di Aspose.BarCode](https://reference.aspose.com/barcode/net/). È una risorsa preziosa per apprendere e risolvere problemi.

### 4. È disponibile una versione di prova per Aspose.BarCode?
Sì, puoi ottenere una versione di prova gratuita di Aspose.BarCode per .NET da [qui](https://releases.aspose.com/).

### 5. Come posso acquistare una licenza per Aspose.BarCode per .NET?
Per acquistare una licenza per Aspose.BarCode per .NET, visita la [pagina di acquisto](https://purchase.aspose.com/buy) sul sito Aspose.

---

**Ultimo aggiornamento:** 2026-03-07  
**Testato con:** Aspose.BarCode 24.11 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}