---
date: 2026-01-27
description: Impara come creare dotcode extended codetext usando Aspose.BarCode per
  .NET – una guida passo‑passo per generare codici a barre DotCode con testo di codice
  esteso.
linktitle: DotCode Extended Code Text Configuration
second_title: Aspose.BarCode .NET API
title: Come creare un codetext esteso DotCode con Aspose.BarCode per .NET
url: /it/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare dotcode extended codetext con Aspose.BarCode per .NET

## Introduzione

Nell'ambito della generazione e gestione dei codici a barre, Aspose.BarCode per .NET si distingue come una soluzione versatile ed efficiente. Che tu abbia bisogno di generare codici a barre per prodotti, inventario o qualsiasi altra applicazione, Aspose.BarCode per .NET ti copre. In questo tutorial completo, **creeremo dotcode extended codetext** e esploreremo perché questa capacità è essenziale per ambienti moderni ricchi di dati. DotCode è un codice a barre matriciale bidimensionale che può codificare sia dati testuali che binari, rendendolo uno strumento prezioso in vari settori.

## Risposte rapide
- **Cosa significa “create dotcode extended codetext”?** Significa creare un codice a barre DotCode che includa FNC1, ECICodetext, testo semplice e separatori di simboli in un unico payload esteso.  
- **Quale libreria è necessaria?** Aspose.BarCode per .NET.  
- **Ho bisogno di una licenza?** Una licenza temporanea è sufficiente per la valutazione; è necessaria una licenza completa per la produzione.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **Quanto tempo richiede l'implementazione?** Circa 10‑15 minuti per un esempio base.

## Come creare dotcode extended codetext

Di seguito trovi una guida concisa, passo‑passo, che mostra esattamente come costruire il codice testuale esteso e renderizzare l'immagine del codice a barre.

## Prerequisiti

Prima di immergerci nella guida passo‑passo, ci sono alcuni prerequisiti che devi avere a disposizione per seguire efficacemente:

1. Aspose.BarCode per .NET: Assicurati di avere la libreria Aspose.BarCode per .NET installata e pronta. In caso contrario, puoi scaricarla dalla [documentazione Aspose.BarCode per .NET](https://reference.aspose.com/barcode/net/).

2. Ambiente di sviluppo: Dovresti avere un ambiente di sviluppo .NET funzionante, preferibilmente Visual Studio, installato sul tuo sistema.

Con questi prerequisiti in ordine, possiamo ora procedere con la generazione del DotCode Extended Code Text.

## Importare gli spazi dei nomi

Per prima cosa, devi importare gli spazi dei nomi necessari nel tuo progetto .NET per accedere alle funzionalità richieste dalla libreria Aspose.BarCode. Ecco come fare:

```csharp
using Aspose.BarCode.Generation;
```

Ora che abbiamo coperto i prerequisiti, suddividiamo il processo di generazione del DotCode Extended Code Text in una guida passo‑passo.

## Passo 1: Definire il percorso della directory

In questo passo, devi specificare il percorso della directory dove vuoi salvare l'immagine generata del DotCode Extended Code Text.

```csharp
string path = "Your Directory Path";
```

Sostituisci `"Your Directory Path"` con il percorso reale sul tuo sistema.

## Passo 2: Creare DotCode Extended Code Text

Per creare il DotCode Extended Code Text, segui questi sotto‑passi:

### 2.1 Aggiungere l'identificatore di formato FNC1

L'identificatore di formato FNC1 è usato per indicare l'inizio di un nuovo campo dati. È una parte essenziale del DotCode Extended Code Text.

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 Aggiungere ECICodetext

L'ECICodetext è dove puoi codificare caratteri speciali e testo internazionale. In questo esempio, abbiamo codificato `"犬Right狗"` usando la codifica UTF‑8.

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 Aggiungere Codetext semplice

Puoi anche aggiungere testo semplice al DotCode Extended Code Text. Qui, abbiamo aggiunto `"Plain text"`.

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 Aggiungere il separatore di simboli FNC3

Il separatore di simboli FNC3 è usato per separare diverse sezioni del codice.

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 Aggiungere l'inizializzazione del lettore FNC3

Questo passo aggiunge le informazioni di inizializzazione del lettore FNC3.

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 Generare il Codetext

Ora, genera il DotCode Extended Codetext chiamando il metodo `GetExtendedCodetext` sull'oggetto `textBuilder`.

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## Passo 3: Generare l'immagine DotCode

Per generare il DotCode Extended Code Text come immagine, segui questi sotto‑passi:

#### 4.1 Inizializzare il generatore di codici a barre

Inizializza il `BarcodeGenerator` con i parametri appropriati. In questo caso, usiamo `EncodeTypes.DotCode` e il codetext generato.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    // Set the X-dimension for the barcode (adjust as needed).
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    // Set the DotCode encoding mode to ExtendedCodetext.
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    // Save the generated barcode image.
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

E questo è tutto! Hai generato con successo il DotCode Extended Code Text usando Aspose.BarCode per .NET.

## Conclusione

Aspose.BarCode per .NET è uno strumento potente che semplifica la generazione di codici a barre. In questo tutorial, ci siamo concentrati su come **creare dotcode extended codetext**, che è essenziale in vari settori, soprattutto dove è richiesta la codifica di caratteri multilingue e specializzati. Seguendo i passaggi descritti sopra, puoi facilmente creare DotCode Extended Code Text per le tue esigenze specifiche.

Se hai bisogno di ulteriori indicazioni o hai domande, non esitare a visitare la [documentazione Aspose.BarCode per .NET](https://reference.aspose.com/barcode/net/) o a interagire con la community sul [forum di supporto Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

## FAQ

### Q1: A cosa serve DotCode?

DotCode è usato per codificare sia dati testuali che binari ed è comunemente applicato in settori come la sanità e la logistica per scopi di tracciamento e codifica dei dati.

### Q2: Posso personalizzare l'aspetto dei codici a barre DotCode?

Sì, Aspose.BarCode per .NET offre opzioni per personalizzare l'aspetto dei codici a barre DotCode, inclusi dimensioni e modalità di codifica.

### Q3: Aspose.BarCode per .NET è compatibile con vari framework .NET?

Sì, Aspose.BarCode per .NET è compatibile con un'ampia gamma di framework .NET, garantendo flessibilità e facilità di integrazione.

### Q4: Come posso ottenere una licenza temporanea per Aspose.BarCode per .NET?

Puoi ottenere una licenza temporanea dal [sito di Aspose](https://purchase.aspose.com/temporary-license/) per scopi di valutazione e test.

### Q5: Aspose.BarCode per .NET è adatto per la generazione di codici a barre a livello enterprise?

Assolutamente, Aspose.BarCode per .NET è progettato per soddisfare le esigenze sia di generazione di codici a barre su piccola scala che a livello enterprise, offrendo scalabilità e affidabilità.

## Domande Frequenti

**Q: Posso usare il codice a barre generato in un'app mobile?**  
A: Sì. L'immagine PNG prodotta dal generatore può essere incorporata in iOS, Android o qualsiasi applicazione mobile cross‑platform.

**Q: E se ho bisogno di codificare dati binari invece di testo?**  
A: Usa il metodo `AddECICodetext` con le appropriate `ECIEncodings` (ad esempio, `ECIEncodings.Base64`) per incorporare payload binari.

**Q: Come posso modificare le dimensioni del codice a barre senza compromettere la leggibilità?**  
A: Regola la proprietà `XDimension.Pixels`; valori più alti aumentano la dimensione del modulo, mentre valori più bassi rendono il codice a barre più compatto.

**Q: Esiste un modo per aggiungere una zona silenziosa attorno al codice a barre?**  
A: Sì. Imposta `gen.Parameters.Barcode.Margin` per definire la zona silenziosa desiderata in pixel.

**Q: La libreria supporta .NET 8?**  
A: Le ultime versioni di Aspose.BarCode sono compatibili con .NET 8; basta fare riferimento alla versione appropriata del pacchetto NuGet.

---

**Ultimo aggiornamento:** 2026-01-27  
**Testato con:** Aspose.BarCode 24.12 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}