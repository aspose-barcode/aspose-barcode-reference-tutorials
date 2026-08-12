---
category: general
date: 2026-08-12
description: Crea un'immagine di codice a barre in C# usando BarCodeGenerator. Scopri
  come generare DataBar, controllare le dimensioni dell'immagine del codice a barre
  e creare più codici a barre in modo efficiente.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- create multiple barcodes
- how to generate databar
- barcode image size
language: it
lastmod: 2026-08-12
og_description: Crea un'immagine di codice a barre in C# con BarCodeGenerator. Questo
  tutorial mostra passo passo come generare codici DataBar, regolare le dimensioni
  dell'immagine del codice a barre e produrre più codici a barre.
og_image_alt: Screenshot of a generated DataBar barcode image saved as PNG
og_title: Crea immagine di codice a barre in C# – guida completa a BarCodeGenerator
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  headline: Create barcode image in C# with BarCodeGenerator
  type: TechArticle
- description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  name: Create barcode image in C# with BarCodeGenerator
  steps:
  - name: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
    text: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
  - name: Adjusting **barcode image size** by changing X‑dimension and bar height.
    text: Adjusting **barcode image size** by changing X‑dimension and bar height.
  - name: Using a loop to **create multiple barcodes** with different heights.
    text: Using a loop to **create multiple barcodes** with different heights.
  - name: Saving the images as PNG files and verifying the output.
    text: Saving the images as PNG files and verifying the output.
  type: HowTo
tags:
- barcode
- csharp
- barcodegenerator
- databar
- image-processing
title: Crea immagine di codice a barre in C# con BarCodeGenerator
url: /it/python-java/general/create-barcode-image-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea immagine barcode in C# con BarCodeGenerator

Se hai bisogno di **creare un'immagine barcode** in un'applicazione .NET, questa guida ti mostra esattamente come farlo con la classe `BarCodeGenerator`. Che tu stia costruendo un sistema POS per il retail o uno strumento di tracciamento dell'inventario, imparerai a generare simboli DataBar, controllare le dimensioni dell'immagine barcode e produrre diversi barcode in un'unica esecuzione.

Scoprirai anche come l'API **barcode generator c#** ti consente di regolare le dimensioni, cambiare i formati di output e gestire casi limite come stringhe di dati non valide. Alla fine del tutorial potrai **creare più barcode** con sicurezza senza scrivere codice ripetitivo.

## Prerequisiti

- .NET 6.0 o versioni successive installate  
- Un ambiente di sviluppo (Visual Studio, Rider o VS Code)  
- Il pacchetto NuGet Aspose.BarCode per .NET (o qualsiasi libreria compatibile che fornisca `BarCodeGenerator`)  

Puoi aggiungere il pacchetto con:

```bash
dotnet add package Aspose.BarCode
```

## Cosa copre questo tutorial

1. Configurare un'istanza **barcode generator c#** per la codifica DataBar Omni‑directional.  
2. Regolare la **dimensione dell'immagine barcode** modificando X‑dimension e altezza delle barre.  
3. Utilizzare un ciclo per **creare più barcode** con altezze diverse.  
4. Salvare le immagini come file PNG e verificare il risultato.  

Tutti gli snippet di codice sono completi e pronti per il copia‑incolla in un nuovo progetto console.

![Esempio di creazione immagine barcode](barcode-example.png){alt="Esempio di creazione immagine barcode"}

## Passo 1: Inizializzare il generatore – nozioni di base per creare l'immagine barcode

Il primo passo è istanziare `BarCodeGenerator` con la simbologia desiderata. Per un simbolo DataBar Omni‑directional si utilizza `EncodeTypes.DatabarOmniDirectional`.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for DataBar Omni‑directional.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarCodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // The rest of the steps are performed below.
        }
    }
}
```

**Perché è importante:** L'istanziazione del generatore definisce le regole di codifica e il payload dei dati. Se ometti il valore corretto di `EncodeTypes`, la libreria produrrà un barcode non supportato o genererà un'eccezione.

## Passo 2: Configurare X‑dimension e altezza della barra – controllare le dimensioni dell'immagine barcode

Le dimensioni visive di un barcode sono determinate da due parametri:

| Parametro | Cosa controlla | Intervallo tipico |
|-----------|----------------|-------------------|
| `x_dimension.pixels` | Larghezza del modulo più piccolo (il “punto”) | 1 – 4 px |
| `bar_height.pixels`  | Altezza delle barre verticali                 | 30 – 150 px |

```csharp
// Set the module width to 2 px for a crisp, readable image.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set an initial bar height of 30 px.
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

**Consiglio professionale:** Una X‑dimension più piccola produce un'immagine ad alta risoluzione ma può risultare più difficile da leggere su stampanti di bassa qualità. Regola il valore in base all'apparecchiatura di scansione prevista.

## Passo 3: Salvare il primo barcode – creare l'immagine barcode per altezza di 30 px

Ora puoi generare l'immagine e scriverla su disco. Il metodo `Save` accetta un percorso file e un enum del formato immagine.

```csharp
// Save the 30 px high barcode as a PNG file.
string outputFolder = @"C:\Barcodes";
generator.Save($"{outputFolder}\\Databar30.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar30.png (30 px height)");
```

**Risultato atteso:** Un file PNG chiamato `Databar30.png` appare in `C:\Barcodes`. Aprendo il file si visualizza un simbolo DataBar Omni‑directional con un pattern chiaro e ad alto contrasto.

## Passo 4: Modificare l'altezza e generare immagini aggiuntive – creare più barcode

Per **creare più barcode** con dimensioni diverse è sufficiente modificare la proprietà `BarHeight` e chiamare nuovamente `Save`. Questo evita di reinizializzare il generatore, risparmiando memoria e tempo CPU.

```csharp
// Increase the bar height to 60 px for a larger barcode.
generator.Parameters.Barcode.BarHeight.Pixels = 60;
generator.Save($"{outputFolder}\\Databar60.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar60.png (60 px height)");

// You can repeat the process for any height you need.
int[] heights = { 90, 120 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputFolder}\\Databar{h}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved Databar{h}.png ({h} px height)");
}
```

**Perché funziona:** L'oggetto `BarCodeGenerator` conserva tutto lo stato di configurazione. Modificando una singola proprietà si aggiorna il motore di rendering per la successiva chiamata a `Save`, consentendo di **creare più barcode** in modo efficiente.

## Passo 5: Avanzato – come generare DataBar con dati personalizzati

L'esempio sopra utilizza un payload GS1 statico. In scenari reali spesso è necessario incorporare identificatori di prodotto variabili. La libreria accetta qualsiasi stringa che corrisponda alla specifica DataBar.

```csharp
string[] gtins = { "01234567890123", "98765432109876", "12345678901234" };
foreach (var gtin in gtins)
{
    // GS1 Application Identifier (01) + GTIN
    generator.CodeText = $"(01){gtin}";
    generator.Parameters.Barcode.BarHeight.Pixels = 50; // uniform height
    generator.Save($"{outputFolder}\\Databar_{gtin}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode for GTIN {gtin}");
}
```

**Punto chiave:** Impostare `generator.CodeText` aggiorna i dati codificati senza ricreare l'oggetto. Questo è lo schema consigliato **how to generate databar** quando si gestiscono grandi insiemi di dati.

## Passo 6: Verificare e risolvere problemi – garantire la corretta dimensione dell'immagine barcode

Dopo aver generato le immagini, potresti voler confermare programmaticamente che le dimensioni corrispondano alle tue aspettative. La classe `Image` di `System.Drawing` può leggere il file e riportare la sua dimensione.

```csharp
using System.Drawing;

// Verify image dimensions
string[] files = { "Databar30.png", "Databar60.png", "Databar90.png" };
foreach (var file in files)
{
    using var img = Image.FromFile($"{outputFolder}\\{file}");
    Console.WriteLine($"{file}: {img.Width}px × {img.Height}px");
}
```

Se l'altezza non riflette il valore impostato, verifica:

- **X‑dimension**: Un valore molto piccolo può far arrotondare l'altezza da parte del renderer.  
- **Image format**: Alcuni formati (ad esempio JPEG) applicano compressione che può modificare le dimensioni in pixel al salvataggio. PNG conserva le dimensioni esatte.

## Passo 7: Best practice per le dimensioni dell'immagine barcode e le prestazioni

| Raccomandazione | Motivo |
|----------------|--------|
| Mantieni `x_dimension.pixels` tra 2 – 3 px per la maggior parte degli scanner. | Equilibra leggibilità e dimensione del file. |
| Usa PNG per output lossless quando l'immagine verrà stampata. | Garantisce dimensioni esatte e bordi nitidi. |
| Riutilizza una singola istanza di `BarCodeGenerator` quando generi molti barcode. | Riduce l'overhead di allocazione degli oggetti. |
| Convalida la stringa di input rispetto allo standard GS1 prima di assegnarla a `CodeText`. | Previene eccezioni a runtime e scansioni non valide. |
| Memorizza le immagini generate in una cartella dedicata con una convenzione di denominazione chiara (ad esempio `Databar_{GTIN}.png`). | Semplifica l'elaborazione successiva e le tracce di audit. |

## Esempio completo funzionante

Di seguito è riportato il programma completo che incorpora tutti i passaggi dall'inizializzazione alla verifica. Copia il codice in un nuovo progetto console e eseguilo.



## Cosa dovresti imparare dopo?

I tutorial seguenti coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Genera immagine barcode – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Crea immagine barcode DotCode – righe e colonne (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Come creare la zona silenziosa del barcode per ITF-14 usando Aspose.BarCode per .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}