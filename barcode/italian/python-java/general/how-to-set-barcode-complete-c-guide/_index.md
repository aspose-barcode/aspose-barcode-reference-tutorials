---
category: general
date: 2026-08-15
description: Come impostare i parametri del codice a barre in C# e generare immagini
  di codici a barre. Impara passo passo a creare un codice a barre Databar e salvare
  file PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- how to generate barcode
- create databar barcode
- generate barcode image c#
language: it
lastmod: 2026-08-15
og_description: Come impostare il codice a barre in C# con Aspose.Barcode, quindi
  generare l’immagine del codice a barre in C#. Segui questa guida per creare un codice
  a barre Databar e salvare i file PNG.
og_image_alt: Screenshot of a Databar barcode saved as PNG using C# code
og_title: Come impostare il codice a barre in C# – guida passo passo
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: How to set barcode parameters in C# and generate barcode images. Learn
    step‑by‑step to create Databar barcode and save PNG files.
  headline: How to set barcode – complete C# guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: Come impostare il codice a barre – guida completa C#
url: /it/python-java/general/how-to-set-barcode-complete-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come impostare il codice a barre – guida completa C#

Se stai cercando **come impostare il codice a barre** nei parametri di un progetto .NET, questo tutorial mostra i passaggi esatti di cui hai bisogno. Imparerai **come generare codici a barre** immagini, creare un codice a barre Databar e controllare l’altezza delle barre pixel per pixel, il tutto con codice C# pulito e pronto per la produzione.

In questa guida:

* Installa il pacchetto NuGet richiesto.  
* Crea un codice a barre Databar Omnidirezionale (la parte “crea codice a barre Databar”).  
* Regola la X‑dimension e l’altezza della barra per dimostrare **come impostare il codice a barre** le dimensioni.  
* Salva il risultato come file PNG, coprendo lo scenario **generare immagine codice a barre C#**.

Il codice funziona con l’ultima versione di Aspose.Barcode per .NET (v 24.12 al momento della stesura) e gira su .NET 6 o versioni successive.

---

## Prerequisiti

Prima di iniziare, assicurati di avere:

* .NET 6 SDK (o qualsiasi versione successiva).  
* Un IDE come Visual Studio 2022 o VS Code.  
* Accesso a Internet per scaricare il pacchetto NuGet Aspose.Barcode.

Nessuna libreria di terze parti aggiuntiva è richiesta.

---

## Passo 1: Installa Aspose.Barcode per .NET

Il modo più affidabile per **generare codici a barre** immagini in C# è utilizzare Aspose.Barcode. Apri un terminale nella cartella del tuo progetto ed esegui:

```bash
dotnet add package Aspose.BarCode
```

Il comando aggiunge l’ultima versione stabile al tuo file di progetto, garantendo la presenza della classe `BarcodeGenerator` e dell’enumerazione `EncodeTypes`.

*Consiglio professionale:* Mantieni il pacchetto aggiornato (`dotnet list package --outdated`) per beneficiare di correzioni di bug e nuove simbologie di codici a barre.

---

## Passo 2: Crea un codice a barre Databar (crea codice a barre Databar)

Databar Omnidirezionale è ideale per il retail e la logistica perché può codificare un valore GTIN‑14 più dati aggiuntivi. Il codice seguente crea l’oggetto codice a barre:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 2: Initialize the generator for a Databar Omnidirectional barcode
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

*Perché è importante:* L’enum `EncodeTypes.DatabarOmniDirectional` indica alla libreria di usare la simbologia Databar, mentre la stringa `"(01)12345678901231"` segue il formato GS1 Application Identifier per un GTIN a 14 cifre.

---

## Passo 3: Definisci i parametri comuni – X‑dimension e altezza di base

La maggior parte degli scanner di codici a barre si aspetta una X‑dimension minima (la larghezza della barra più stretta). Impostarla a 2 pixel fornisce un’immagine compatta ma leggibile.

```csharp
// Step 3: Set a 2‑pixel X‑dimension (common for most scanners)
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Puoi successivamente regolare l’altezza della barra senza ricreare il generatore—questo è il fulcro di **come impostare il codice a barre** gli attributi dopo l’instanziazione.

---

## Passo 4: Imposta la prima altezza della barra e salva l’immagine (generare immagine codice a barre C#)

Ora dimostriamo la prima parte di **come impostare il codice a barre** altezza. L’altezza della barra controlla la lunghezza visiva di ogni barra; un valore di 30 pixel produce un codice a barre corto, mentre 60 pixel ne crea una versione più alta.

```csharp
// Step 4a: 30‑pixel bar height
generator.Parameters.Barcode.BarHeight.Pixels = 30;

// Save the first PNG image
generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Dopo l’esecuzione, `DatabarBarHeight30Pixels.png` contiene un codice a barre Databar con una barra alta 30 pixel. Apri il file con qualsiasi visualizzatore di immagini per verificare il risultato.

---

## Passo 5: Modifica l’altezza della barra e salva una seconda immagine

Per illustrare che **come impostare il codice a barre** i valori possono essere cambiati al volo, modifichiamo l’altezza della barra a 60 pixel e scriviamo un secondo file.

```csharp
// Step 5a: 60‑pixel bar height
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second PNG image
generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Ora disponi di due file PNG che mostrano gli stessi dati Databar ma con altezze visive diverse. Questo è utile quando ti serve un codice a barre più grande per etichette stampate o più piccolo per la visualizzazione su schermo.

---

## Passo 6: Esempio completo, eseguibile

Mettendo tutto insieme, ecco un programma console autonomo che esegue tutti i passaggi descritti sopra. Copia il codice in un nuovo file `Program.cs`, sostituisci `YOUR_DIRECTORY` con un percorso di cartella reale e avvialo.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the generator for a Databar Omnidirectional barcode
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // Common parameters
        generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2‑pixel narrow bar

        // First image: 30‑pixel height
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save(@"C:\Barcodes\DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode.");

        // Second image: 60‑pixel height
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save(@"C:\Barcodes\DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode.");

        // Dispose the generator to free native resources
        generator.Dispose();
    }
}
```

**Output previsto**

Quando esegui il programma, la console stampa:

```
Saved 30-pixel barcode.
Saved 60-pixel barcode.
```

E la cartella `C:\Barcodes` (o il percorso che hai fornito) contiene i due file PNG. Entrambe le immagini mostrano un codice a barre Databar Omnidirezionale valido che può essere letto da lettori GS1 standard.

---

## Domande frequenti

**Questo funziona con altri formati immagine?**  
Sì. Sostituisci `BarCodeImageFormat.Png` con `Jpeg`, `Bmp`, `Gif` o `Tiff` per generare il tipo di file corrispondente.

**Posso cambiare il colore di primo piano?**  
Imposta `generator.Parameters.Barcode.ForeColor` a qualsiasi valore `System.Drawing.Color`, ad esempio `Color.Blue`.

**E se ho bisogno di una simbologia diversa?**  
Passa un valore diverso di `EncodeTypes` al costruttore, come `EncodeTypes.Code128` per un codice a barre lineare o `EncodeTypes.QR` per un codice matrice.

**È possibile incorporare il codice a barre in un PDF?**  
Aspose.Barcode fornisce una classe `PdfGenerator`. Dopo aver generato l’immagine, puoi aggiungerla a una pagina PDF usando Aspose.PDF.

---

## Best practice per la generazione di codici a barre in C#

* **Riutilizza l’istanza `BarcodeGenerator`** quando devi solo modificare le dimensioni—questo evita allocazioni di memoria inutili.  
* **Disponi il generatore** (`generator.Dispose()`) dopo aver terminato per rilasciare prontamente le risorse native.  
* **Convalida i dati di input** (ad es. la lunghezza del GTIN) prima di creare il codice a barre per prevenire eccezioni a runtime.  
* **Testa con uno scanner fisico** dopo aver cambiato X‑dimension o altezza della barra; valori estremi possono influire sulla leggibilità.  
* **Mantieni la cartella di output scrivibile** per l’account in esecuzione; altrimenti `Save` genererà un `UnauthorizedAccessException`.

---

## Conclusione

Ora sai **come impostare le proprietà del codice a barre** come X‑dimension e altezza della barra, **come generare immagini di codici a barre** in C#, e i passaggi esatti per **creare file Databar barcode** con Aspose.Barcode. Seguendo l’esempio completo, puoi generare più file PNG con caratteristiche visive diverse, soddisfacendo il requisito **generare immagine codice a barre C#** per qualsiasi applicazione .NET.

Successivamente, esplora argomenti correlati come **come generare codici a barre** in massa, incorporare codici a barre in PDF o passare a altre simbologie come QR o Code 128. Sperimenta con i parametri mostrati qui per perfezionare l’aspetto del codice a barre per il tuo specifico ambiente di scansione. Buon coding!

## Cosa dovresti imparare dopo?

I tutorial seguenti coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come generare codici a barre DataMatrix (ECC 200) con Aspose.BarCode per .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Come generare un codice a barre Aztec con rapporto d'aspetto personalizzato usando Aspose.BarCode per .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Come generare un codice a barre – Configurazione Code 39 con Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}