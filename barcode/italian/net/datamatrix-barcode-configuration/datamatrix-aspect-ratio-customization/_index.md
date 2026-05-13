---
date: 2026-01-12
description: Scopri come creare un PNG di codice a barre con un rapporto d'aspetto
  personalizzato per DataMatrix usando Aspose.BarCode per .NET. Guida passo passo
  per la generazione del codice a barre e la personalizzazione delle dimensioni.
linktitle: DataMatrix Aspect Ratio Customization
second_title: Aspose.BarCode .NET API
title: Crea PNG di codice a barre – Rapporto d'aspetto DataMatrix – Aspose.BarCode
url: /it/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea PNG di Codice a Barre – Rapporto d'Aspetto DataMatrix – Aspose.BarCode

Generare un **barcode PNG** con un rapporto d'aspetto DataMatrix personalizzato è una necessità comune quando è necessario far sì che il codice a barre si adatti a vincoli di layout specifici. In questo tutorial illustreremo i passaggi esatti per **creare file barcode PNG** usando Aspose.BarCode per .NET, spiegheremo perché potresti voler regolare il rapporto d'aspetto e ti mostreremo come perfezionare l'output per la tua applicazione.

## Risposte Rapide
- **Cosa controlla il “rapporto d'aspetto”?** Definisce la proporzione larghezza‑altezza dei moduli DataMatrix.  
- **Posso esportare PNG, JPEG o SVG?** Sì – il metodo `Save` supporta PNG, JPEG, BMP, GIF e altro.  
- **Ho bisogno di una licenza per questa funzionalità?** Una versione di prova gratuita è sufficiente per lo sviluppo; è necessaria una licenza completa per la produzione.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.x, .NET Core 3.1+, .NET 5/6/7.  
- **Quanti valori di rapporto d'aspetto sono validi?** Qualsiasi numero in virgola mobile positivo; i valori tipici sono 0,5 – 2,0.

## Cos'è un codice a barre DataMatrix e perché regolare il suo rapporto d'aspetto?
DataMatrix è un codice a barre matriciale bidimensionale che memorizza grandi quantità di dati in uno spazio ridotto. Regolare il **rapporto d'aspetto** consente di allungare o comprimere i moduli orizzontalmente, il che può essere utile per inserire il codice a barre in colonne strette o etichette larghe senza sacrificare la leggibilità.

## Prerequisiti

Prima di iniziare a personalizzare i rapporti d'aspetto DataMatrix, assicurati di avere i seguenti prerequisiti:

1. **Visual Studio** – qualsiasi versione recente va bene.  
2. **Aspose.BarCode for .NET** – scaricalo [qui](https://releases.aspose.com/barcode/net/).  
3. **.NET Framework / .NET Core** – il tuo progetto deve puntare a una versione supportata.

## Importa Namespace

Per prima cosa, devi importare il namespace necessario nel tuo progetto C#:

```csharp
using Aspose.BarCode.Generation;
```

> **Suggerimento:** Mantieni questa istruzione `using` in cima al tuo file in modo che la classe `BarcodeGenerator` sia sempre disponibile.

## Guida Passo‑Passo

### Passo 1: Configura il tuo progetto
Crea un nuovo progetto console o Windows Forms in Visual Studio e aggiungi un riferimento al DLL di Aspose.BarCode.

### Passo 2: Inizializza un Barcode Generator
Istanzia un `BarcodeGenerator` con il tipo DataMatrix e i dati che desideri codificare:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> Questa riga crea un generatore pronto a produrre un codice a barre DataMatrix che contiene il testo di esempio.

### Passo 3: Personalizza il Rapporto d'Aspetto e Salva i File PNG
Ora puoi modificare il **rapporto d'aspetto** e salvare ogni versione come immagine PNG:

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- La prima chiamata crea un codice a barre con proporzioni quadrate (`AspectRatio = 1`).  
- La seconda chiamata comprime il codice a barre orizzontalmente (`AspectRatio = 0.5`), producendo un aspetto più largo.

Ora hai due file **barcode PNG** con diversi rapporti d'aspetto pronti per l'uso in report, etichette o elementi UI.

## Problemi Comuni e Soluzioni
| Problema | Soluzione |
|----------|----------|
| **L'immagine generata è sfocata** | Aumenta il parametro `Resolution` prima di salvare (`gen.Parameters.ImageResolution = 300`). |
| **Il codice a barre non viene letto** | Assicurati che il rapporto d'aspetto rimanga tra 0,5 – 2,0 e mantieni una zona silenziosa sufficiente (`gen.Parameters.Barcode.CodeTextParameters.Margin`). |
| **Errori di percorso file** | Usa `Path.Combine` per costruire il percorso di output e verifica che la cartella esista. |

## Domande Frequenti

**D: Posso personalizzare il rapporto d'aspetto di altri tipi di codice a barre usando Aspose.BarCode per .NET?**  
R: Sì, molti codici a barre 2‑D (ad es., QR, PDF417) supportano la regolazione del rapporto d'aspetto tramite i loro specifici oggetti parametro.

**D: È disponibile una versione di prova gratuita per Aspose.BarCode per .NET?**  
R: Sì, puoi accedere a una versione di prova gratuita di Aspose.BarCode per .NET [qui](https://releases.aspose.com/).

**D: Dove posso acquistare una licenza per Aspose.BarCode per .NET?**  
R: Puoi acquistare una licenza sul sito Aspose [qui](https://purchase.aspose.com/buy).

**D: Aspose.BarCode per .NET è compatibile con diverse versioni di .NET Framework?**  
R: Sì, funziona con .NET Framework 4.x, .NET Core 3.1+ e le ultime versioni di .NET.

**D: Posso generare codici a barre in formati diversi con Aspose.BarCode per .NET?**  
R: Assolutamente – PNG, JPEG, BMP, GIF, TIFF, SVG e PDF sono tutti supportati nativamente.

## Conclusione

Personalizzare il **rapporto d'aspetto** di un codice a barre DataMatrix e **creare file barcode PNG** è semplice con Aspose.BarCode per .NET. Seguendo i passaggi sopra, puoi generare codici a barre di dimensioni perfette che soddisfano i requisiti di layout esatti del tuo progetto. Esplora altri parametri come `Resolution`, `Margin` e `Color` per affinare ulteriormente l'output.

Per un'esplorazione più approfondita, consulta la [documentazione](https://reference.aspose.com/barcode/net/) ufficiale o unisciti alla community sul [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**Ultimo aggiornamento:** 2026-01-12  
**Testato con:** Aspose.BarCode 24.12 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}