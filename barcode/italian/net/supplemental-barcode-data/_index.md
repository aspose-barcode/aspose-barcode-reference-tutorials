---
date: 2026-03-07
description: Scopri come creare un codice a barre EAN‑2 e generare codici a barre
  in .NET usando Aspose.BarCode per .NET. Padroneggia oggi la personalizzazione dei
  dati supplementari del codice a barre!
linktitle: Supplemental Barcode Data
second_title: Aspose.BarCode .NET API
title: Crea codice a barre EAN-2 con Aspose.BarCode per .NET
url: /it/net/supplemental-barcode-data/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea un codice a barre EAN-2 con Aspose.BarCode per .NET

## Introduzione

Se sei uno sviluppatore .NET e desideri **creare un codice a barre EAN-2** e sfruttare la potenza dei dati supplementari del codice a barre, sei nel posto giusto. In questa guida completa ti accompagneremo passo passo attraverso tutto ciò che devi sapere—dalla configurazione di base alla messa a punto dello spazio attorno ai simboli. Che tu stia costruendo un nuovo sistema di inventario o migliorando un’applicazione point‑of‑sale esistente, padroneggiare queste funzionalità renderà i tuoi progetti .NET di generazione di codici a barre più flessibili e affidabili.

## Risposte rapide
- **Cosa posso generare?** Codici a barre supplementari EAN‑2 e EAN‑5.  
- **È necessaria una licenza?** Una versione di prova gratuita è sufficiente per lo sviluppo; per la produzione è richiesta una licenza commerciale.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Quante righe di codice servono?** Solo poche—Aspose.BarCode si occupa del lavoro pesante.  
- **Posso personalizzare la spaziatura?** Sì, puoi controllare direttamente la X‑dimension e lo spazio supplementare.

## Cos’è il dato supplementare del codice a barre?

Il dato supplementare del codice a barre si riferisce ai piccoli simboli aggiuntivi (EAN‑2, EAN‑5) che appaiono accanto a un codice a barre principale, tipicamente usati per numeri di edizione, estensioni di prezzo o altre informazioni ausiliarie. Aspose.BarCode per .NET ti consente di generare questi simboli programmaticamente, offrendoti il pieno controllo su aspetto e posizionamento.

## Perché usare Aspose.BarCode per .NET?

- **Integrazione completa con .NET** – funziona con C#, VB.NET e F#.  
- **Rendering di alta qualità** – produce codici a barre leggibili a qualsiasi risoluzione.  
- **Ampia personalizzazione** – dal tipo di simbologia a X‑dimension, zone silenziose e spazio supplementare.  
- **Nessuna dipendenza esterna** – libreria gestita pura, facile da distribuire.

## Configurazione dei dati supplementari del codice a barre

Iniziamo esplorando la configurazione dei dati supplementari del codice a barre. Aspose.BarCode per .NET ti offre gli strumenti per generare codici a barre supplementari senza sforzo, garantendoti il controllo completo su EAN‑2 e EAN‑5. Ma da dove cominciare?

Per prima cosa, scarica e installa Aspose.BarCode per .NET. Puoi provare la versione di valutazione gratuita per testare le funzionalità. Una volta configurato, segui la nostra guida passo‑passo, che ti accompagnerà attraverso il processo, assicurandoti di padroneggiare la configurazione dei dati supplementari con facilità.

Al termine di questa sezione avrai una solida comprensione di come creare codici a barre EAN‑2 e EAN‑5, diventando uno sviluppatore .NET più versatile.

## Come creare un codice a barre EAN-2? (Passaggi di configurazione)

1. **Istanzia il generatore di codici a barre** – scegli la classe `BarcodeGenerator` e imposta la simbologia su `EncodeTypes.EAN13` (o un altro tipo primario).  
2. **Abilita la parte supplementare** – imposta la proprietà `SupplementData` sulla stringa numerica desiderata (ad es., `"12"` per un supplemento EAN‑2).  
3. **Regola le impostazioni visive** – opzionalmente modifica `XDimension`, `BarHeight` e `QuietZone` per adattarle ai requisiti del layout.  
4. **Salva o renderizza** – chiama `Save` per scrivere l’immagine su file o stream.

> *Consiglio esperto:* Mantieni la lunghezza del dato supplementare esattamente a 2 cifre per EAN‑2 e a 5 cifre per EAN‑5; altrimenti il codice a barre potrebbe diventare illeggibile.

## Personalizzazione dello spazio del codice a barre supplementare

Nel mondo dei codici a barre, la personalizzabilità è fondamentale, ed è qui che Aspose.BarCode per .NET brilla. Ora, concentriamoci sulla personalizzazione dello spazio del codice a barre supplementare. Questo aspetto riguarda il controllo della X‑Dimension e dello spazio supplementare nei tuoi codici a barre.

Ancora una volta, inizia installando Aspose.BarCode per .NET e sfruttando la versione di prova gratuita. Poi, segui le nostre indicazioni su come regolare lo spazio nei tuoi codici a barre. Questa personalizzazione può rivelarsi estremamente utile per varie applicazioni, dalla gestione dell’inventario ai sistemi point‑of‑sale.

La libertà di adattare i codici a barre alle tue esigenze specifiche è una competenza preziosa, e questa sezione ti assicurerà di essere ben attrezzato.

## Come personalizzare lo spazio supplementare?

- **X‑Dimension** – definisce la larghezza di un singolo modulo; valori più alti aumentano le dimensioni complessive del codice a barre.  
- **Spazio supplementare** – la distanza tra il codice a barre principale e la parte supplementare; si regola tramite la proprietà `SupplementSpace`.  
- **Quiet Zone** – il margine bianco obbligatorio attorno all’intero codice a barre; mantienilo almeno a 10 unità di X‑Dimension per una scansione affidabile.

Sperimenta con queste impostazioni in un progetto di prova finché non ottieni l’equilibrio visivo richiesto dal tuo hardware di scansione.

## Casi d’uso comuni

| Scenario | Perché i dati supplementari sono utili |
|----------|----------------------------------------|
| **Estensioni di prezzo al dettaglio** | EAN‑5 può codificare direttamente le informazioni di prezzo sull’etichetta. |
| **Numeri di edizione di riviste** | EAN‑2 identifica l’edizione, consentendo una rapida ordinamento. |
| **Logistica e tracciamento** | Aggiungere un piccolo supplemento a un codice a barre principale fornisce dati di instradamento extra senza ingrandire l’etichetta. |

## Tutorial sui dati supplementari del codice a barre
### [Configurazione dei dati supplementari del codice a barre](./supplemental-barcode-data-configuration/)
Genera dati supplementari del codice a barre con Aspose.BarCode per .NET. Personalizza i codici a barre EAN-2 e EAN-5 senza sforzo. Guida passo‑passo per sviluppatori .NET.
### [Personalizzazione dello spazio del codice a barre supplementare](./supplemental-barcode-space-customization/)
Personalizza i codici a barre facilmente con Aspose.BarCode per .NET. Controlla X‑Dimension e spazio supplementare. Prova la versione di valutazione gratuita!

## Domande frequenti

**D: Posso generare sia EAN‑2 che EAN‑5 con lo stesso codice?**  
R: Sì. Basta modificare la lunghezza di `SupplementData` (2 cifre per EAN‑2, 5 cifre per EAN‑5) e la libreria renderà la simbologia corretta.

**D: Devo calcolare i valori di checksum per il supplemento?**  
R: No. Aspose.BarCode calcola e aggiunge automaticamente il checksum necessario.

**D: C’è un limite al numero di codici a barre che posso generare in un ciclo?**  
R: La libreria è ottimizzata per la generazione in batch; fai solo attenzione all’uso della memoria quando gestisci collezioni di immagini molto grandi.

**D: Come inserisco il codice a barre in un documento PDF o Word?**  
R: Salva il codice a barre come immagine (PNG, JPEG, ecc.) e poi inseriscilo usando l’API di generazione documenti che preferisci (ad es., Aspose.PDF o Aspose.Words).

**D: Cosa fare se il mio scanner non legge la parte supplementare?**  
R: Verifica che `SupplementSpace` sia almeno 2 X‑Dimension e che la quiet zone soddisfi le specifiche dello scanner.

---

**Ultimo aggiornamento:** 2026-03-07  
**Testato con:** Aspose.BarCode per .NET 24.12  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}