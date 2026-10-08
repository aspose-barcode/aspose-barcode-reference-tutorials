---
date: 2026-09-28
description: Scopri come creare uno spazio personalizzato per il codice a barre per
  i coupon GS1 con Aspose.BarCode per .NET e aumentare la leggibilità del codice a
  barre. Segui la nostra guida passo‑passo.
keywords:
- create barcode custom space
- GS1 coupon supplement
- Aspose.BarCode .NET
- increase barcode readability
lastmod: 2026-09-28
linktitle: Configurazione dello spazio per il supplemento coupon GS1
og_description: Scopri come creare uno spazio personalizzato per il codice a barre
  per i coupon GS1 con Aspose.BarCode per .NET e aumentare la leggibilità del codice
  a barre. Codice passo‑passo e consigli inclusi.
og_image_alt: Screenshot of a GS1 coupon barcode generated with custom supplement
  space using Aspose.BarCode for .NET
og_title: Crea uno spazio personalizzato per il codice a barre per il supplemento
  coupon GS1 – Aspose.BarCode .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  headline: How to create barcode custom space for GS1 coupon supplement
  type: TechArticle
- description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  name: How to create barcode custom space for GS1 coupon supplement
  steps:
  - name: '**Visual Studio** – The primary IDE for .NET development.'
    text: '**Visual Studio** – The primary IDE for .NET development.'
  - name: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
  - name: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
    text: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
  - name: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
    text: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
  - name: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
    text: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
  - name: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
    text: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
  type: HowTo
- questions:
  - answer: It adds a mandatory blank margin around the supplemental data, improving
      scanner reliability and meeting retailer‑specified minimum widths.
    question: What is the purpose of the GS1 Coupon Supplement Space in barcodes?
  - answer: Yes, set `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` to any
      integer value; the library instantly applies the change to the generated image.
    question: Can I customize the width of the GS1 Coupon Supplement Space with Aspose.BarCode
      for .NET?
  - answer: Refer to the [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)
      and visit the [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)
      for community assistance.
    question: Where can I find additional documentation and support for Aspose.BarCode
      for .NET?
  - answer: Absolutely. The API offers straightforward methods for quick tasks and
      advanced options for fine‑tuned barcode generation.
    question: Is Aspose.BarCode for .NET suitable for both beginners and experienced
      developers?
  - answer: Yes, request a trial license from the [Aspose temporary license website](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for Aspose.BarCode for .NET to evaluate
      its features?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- barcode configuration
- GS1 standards
- Aspose.BarCode
- .NET barcode generation
title: Come creare uno spazio personalizzato per il codice a barre per il supplemento
  coupon GS1
url: /it/net/gs1-barcode-encoding/gs1-coupon-supplement-space-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configurazione dello spazio supplementare del coupon GS1

In questo tutorial **creerai uno spazio personalizzato per il codice a barre** per lo Spazio Supplementare del Coupon GS1 utilizzando Aspose.BarCode per .NET. Regolare lo spazio supplementare è essenziale quando è necessario **aumentare la leggibilità del codice a barre** su scanner a bassa risoluzione o rispettare i margini imposti dal rivenditore. Alla fine di questa guida comprenderai perché lo spazio supplementare è importante, come impostarlo programmaticamente e come generare immagini con valori di pixel diversi.

## Risposte rapide
- **Cosa controlla lo spazio supplementare?** Definisce l'area vuota (in pixel) tra i dati del coupon e il resto del codice a barre.  
- **Quale tipo di codice a barre viene utilizzato?** `EncodeTypes.UpcaGs1DatabarCoupon`.  
- **Posso modificare la dimensione dello spazio?** Sì – imposta `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` a qualsiasi valore intero.  
- **È necessaria una licenza per questa funzionalità?** Una licenza temporanea funziona per la valutazione; è necessaria una licenza completa per la produzione.  
- **Quali formati di output sono supportati?** PNG, JPEG, BMP, GIF, TIFF e altri tramite `BarCodeImageFormat`.

## Cos'è lo spazio supplementare del coupon GS1?
Lo Spazio Supplementare del Coupon GS1 è una regione vuota definita che appare nei codici a barre coupon GS1‑Databar. I sistemi di vendita al dettaglio utilizzano questo spazio per migliorare l'affidabilità della scansione e per conformarsi alle specifiche di settore che richiedono un margine minimo attorno ai dati supplementari.

## Perché configurare lo spazio supplementare?
Lo spazio supplementare aumenta direttamente **la leggibilità del codice a barre** e ti aiuta a rispettare le rigide linee guida dei rivenditori. Aggiungendo pixel extra riduci la probabilità di letture errate su scanner a bassa risoluzione, garantisci una scansione coerente su diverse dimensioni di etichette e ottieni flessibilità visiva per bilanciare il codice a barre all'interno di un layout stampato.

## Prerequisiti

Prima di immergerci nella configurazione dello Spazio Supplementare del Coupon GS1 con Aspose.BarCode per .NET, assicurati di avere quanto segue:

1. **Visual Studio** – L'IDE principale per lo sviluppo .NET.  
2. **Aspose.BarCode for .NET** – Scarica la libreria dalla [documentazione di Aspose.BarCode per .NET](https://reference.aspose.com/barcode/net/).  
3. **.NET Framework o .NET 5+** – È necessaria familiarità con C# e il runtime .NET.

Ora che l'ambiente è pronto, passiamo all'implementazione.

## Importa gli spazi dei nomi

Lo spazio dei nomi `Aspose.BarCode.Generation` contiene la classe `BarcodeGenerator` e le impostazioni correlate.

```csharp
using Aspose.BarCode;
```

## Passo 1: definire il percorso

Scegli una cartella in cui verranno salvate le immagini generate. Il percorso deve terminare con il separatore di directory appropriato per il tuo sistema operativo.

```csharp
string path = "Your Directory Path";
```

## Passo 2: generare la configurazione dello spazio supplementare del coupon GS1

Il frammento seguente crea un codice a barre, imposta la dimensione X e regola lo spazio supplementare.

```csharp
System.Console.WriteLine("Gs1CouponSupplementSpace:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.UpcaGs1DatabarCoupon, "123456789012(8110)ASPOSE");
gen.Parameters.Barcode.XDimension.Pixels = 2;

// Set coupon supplement space to 30 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 30;
gen.Save($"{path}Gs1CouponSpace30Pixels.png", BarCodeImageFormat.Png);

// Set coupon supplement space to 50 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 50;
gen.Save($"{path}Gs1CouponSpace50Pixels.png", BarCodeImageFormat.Png);
```

In questo esempio:

1. **Crea** un'istanza `BarcodeGenerator` per il tipo `UpcaGs1DatabarCoupon`.  
2. **Imposta** la dimensione X a 2 pixel, che determina la larghezza della barra più stretta.  
3. **Regola** la proprietà `SupplementSpace.Pixels` a 30 px, genera un'immagine, quindi ripeti con 50 px.  

Sentiti libero di sperimentare altri valori di pixel per adattarli al tuo flusso di lavoro di stampa.

## Problemi comuni e suggerimenti
- **Percorso non valido** – Assicurati che la variabile `path` termini con una barra finale (`\`) o una barra (`/`) appropriata per il tuo OS.  
- **Permessi insufficienti** – Esegui Visual Studio come Amministratore o scegli una cartella in cui l'applicazione abbia accesso in scrittura.  
- **Formato dati errato** – La stringa dei dati deve seguire la sintassi GS1 (`(8110)` indica l'identificatore del supplemento).  

## Perché questo è importante per il tuo business
Aspose.BarCode supporta **oltre 60 simbologie di codici a barre** e può generare immagini fino a **10.000 × 10.000 pixel** senza esaurire la memoria. Per implementazioni retail su larga scala, ciò significa che puoi generare coupon GS1 ad alta risoluzione in modalità batch mantenendo il tempo di elaborazione inferiore a un secondo per immagine su hardware server tipico.

## Domande frequenti
**Q: Qual è lo scopo dello Spazio Supplementare del Coupon GS1 nei codici a barre?**  
A: Aggiunge un margine vuoto obbligatorio attorno ai dati supplementari, migliorando l'affidabilità dello scanner e rispettando le larghezze minime specificate dal rivenditore.

**Q: Posso personalizzare la larghezza dello Spazio Supplementare del Coupon GS1 con Aspose.BarCode per .NET?**  
A: Sì, imposta `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` a qualsiasi valore intero; la libreria applica immediatamente la modifica all'immagine generata.

**Q: Dove posso trovare documentazione aggiuntiva e supporto per Aspose.BarCode per .NET?**  
A: Consulta la [documentazione di Aspose.BarCode per .NET](https://reference.aspose.com/barcode/net/) e visita il [forum di Aspose.BarCode](https://forum.aspose.com/c/barcode/13) per assistenza della community.

**Q: Aspose.BarCode per .NET è adatto sia ai principianti che agli sviluppatori esperti?**  
A: Assolutamente. L'API offre metodi semplici per compiti rapidi e opzioni avanzate per una generazione di codici a barre finemente regolata.

**Q: Posso ottenere una licenza temporanea per Aspose.BarCode per .NET per valutare le sue funzionalità?**  
A: Sì, richiedi una licenza di prova dal [sito della licenza temporanea di Aspose](https://purchase.aspose.com/temporary-license/).

## Conclusione
Seguendo i passaggi sopra, ora sai come **creare uno spazio personalizzato per il codice a barre** per lo Spazio Supplementare del Coupon GS1, una tecnica chiave per **aumentare la leggibilità del codice a barre** e soddisfare gli standard retail. Integra il codice nelle tue soluzioni di scansione esistenti, sperimenta con valori di pixel diversi e scopri altri tipi di codici a barre offerti da Aspose.BarCode per .NET.

---

**Ultimo aggiornamento:** 2026-09-28  
**Testato con:** Aspose.BarCode 24.12 per .NET  
**Autore:** Aspose

## Tutorial correlati
- [Genera codice a barre Databar Aspose.BarCode usando l'API .NET – Configurazione di righe e colonne](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)
- [Come generare codici a barre DataMatrix usando Aspose.BarCode per .NET – Guida passo‑passo](/barcode/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}