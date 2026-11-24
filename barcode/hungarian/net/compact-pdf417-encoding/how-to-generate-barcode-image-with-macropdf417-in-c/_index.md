---
category: general
date: 2026-11-23
description: Tanulja meg, hogyan generáljon vonalkód képet az Aspose.BarCode for .NET
  használatával MacroPdf417 metaadatokkal C#-ban. Kövesse a teljes lépésről‑lépésre
  útmutatót.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode image
- MacroPdf417 barcode
- Aspose.BarCode for .NET
- set barcode metadata
- barcode image format
- C# barcode generation
language: hu
lastmod: 2026-11-23
og_description: Hogyan generáljunk vonalkód képet az Aspose.BarCode for .NET használatával.
  Ez az útmutató bemutatja a MacroPdf417 metaadat konfigurációját és a C# vonalkód
  generálását.
og_image_alt: Barcode image generated with MacroPdf417 using C#
og_title: Hogyan generáljunk vonalkód képet MacroPdf417 használatával C#-ban
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to generate barcode image using Aspose.BarCode for .NET with
    MacroPdf417 metadata in C#. Follow the complete step‑by‑step guide.
  headline: How to generate barcode image with MacroPdf417 in C#
  type: TechArticle
- description: Learn how to generate barcode image using Aspose.BarCode for .NET with
    MacroPdf417 metadata in C#. Follow the complete step‑by‑step guide.
  name: How to generate barcode image with MacroPdf417 in C#
  steps:
  - name: Open a terminal or the Package Manager Console in Visual Studio.
    text: Open a terminal or the Package Manager Console in Visual Studio.
  - name: 'Run the following command:'
    text: 'Run the following command:'
  - name: '**Visual inspection** – The barcode should display a series of stacked
      columns with a quiet zone (white margin) around it.'
    text: '**Visual inspection** – The barcode should display a series of stacked
      columns with a quiet zone (white margin) around it.'
  - name: '**Decoding test** – Use a barcode scanner app or the Aspose.BarCode `BarCodeReader`
      class to read the image back and confirm that all metadata fields are correctly
      embedded.'
    text: '**Decoding test** – Use a barcode scanner app or the Aspose.BarCode `BarCodeReader`
      class to read the image back and confirm that all metadata fields are correctly
      embedded.'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- PDF417
title: Hogyan generáljunk vonalkód képet MacroPdf417 segítségével C#-ban
url: /hu/net/compact-pdf417-encoding/how-to-generate-barcode-image-with-macropdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan generáljunk vonalkód képet MacroPdf417 használatával C#‑ban

Ha .NET alkalmazásban **vonalkód képet** kell **generálnia**, ez az útmutató pontosan megmutatja, hogyan teheti ezt meg a **Aspose.BarCode for .NET** segítségével. Lépésről lépésre végigvezetünk egy **MacroPdf417 vonalkód** létrehozásán, a metaadatok konfigurálásán, és az eredmény PNG fájlként való mentésén.

Ez a tutorial mindent lefed a könyvtár telepítésétől egy teljes, futtatható konzolprogram írásáig. A végére egy kész, használatra kész kódrészletet kap, amely magas minőségű vonalkód képet állít elő, és megérti, hogyan **állítsa be a vonalkód metaadatait**, válasszon **vonalkód képformátumot**, valamint hogyan hárítsa el a gyakori hibákat. Előzetes Aspose tapasztalat nem szükséges – csak alapvető C# ismeretekkel kell rendelkeznie.

## Telepítés: Aspose.BarCode for .NET

Mielőtt **vonalkód képet** generálna, szüksége van az Aspose.BarCode NuGet csomagra.

1. Nyisson meg egy terminált vagy a Package Manager Console‑t a Visual Studio‑ban.  
2. Futtassa a következő parancsot:

```bash
dotnet add package Aspose.BarCode
```

A csomag hozzáadja az `Aspose.BarCode.Generation` névteret, amely tartalmazza a **C# vonalkód generáláshoz** használt `BarcodeGenerator` osztályt.

> **Pro tip:** Használja a legújabb stabil verziót (2026. november állása szerint a jelenlegi verzió 24.11), hogy a legújabb funkciókat és hibajavításokat kapja.

## A BarcodeGenerator példány létrehozása

Az első kódlépés egy `BarcodeGenerator`‑t hoz létre, amely a **MacroPdf417 vonalkód** típusra van konfigurálva, és megadja a kódolni kívánt adatkarakterláncot.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a BarcodeGenerator for MacroPdf417 with the desired text
            using (BarcodeGenerator barcodeGenerator =
                   new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Subsequent configuration goes here...
```

A `using` blokk biztosítja, hogy a generátor megfelelően legyen felszabadítva, és minden nem kezelt erőforrás felszabaduljon.

## Alapvető megjelenés beállítása

Egy olvasható vonalkód érzékelhető méretekkel kezdődik. Itt állítjuk be az egyes modulok pixel szélességét (`XDimension`) és a PDF417 mátrix oszlopainak számát.

```csharp
                // Step 2: Set basic barcode appearance
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel width of a module
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

*Miért ezek az értékek?*  
- **XDimension** szabályozza, hogy a vonalak mennyire vastagok; 2 pixel jól működik képernyőn és a legtöbb nyomtatón.  
- **Columns** befolyásolja a teljes szélességet; egy kis oszlopszám kompakt vonalkódot eredményez, miközben megőrzi a hibajavítási kapacitást.

## Vonalkód metaadatok beállítása (MacroPdf417 specifikus)

A MacroPdf417 lehetővé teszi, hogy fájlszintű információkat ágyazzunk közvetlenül a vonalkódba. Itt **állítja be a vonalkód metaadatait**, például fájlazonosítót, szegmensazonosítót és időbélyegeket.

```csharp
                // Step 3: Configure MacroPdf417 specific metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### Mit jelent minden tulajdonság

| Tulajdonság | Cél |
|-------------|-----|
| **MacroPdf417FileID** | A logikai fájl egyedi azonosítója, amelyhez a vonalkód tartozik. |
| **MacroPdf417SegmentID** | Az aktuális szegmens indexe (0‑tól kezdődően). |
| **MacroPdf417SegmentsCount** | A teljes fájlt alkotó szegmensek összes száma. |
| **MacroPdf417FileName** | Az eredeti fájl ember által olvasható neve. |
| **MacroPdf417Checksum** | Opcionális CCITT‑16 ellenőrzőösszeg az adat integritásának ellenőrzéséhez. |
| **MacroPdf417FileSize** | Az eredeti fájl várható mérete bájtokban. |
| **MacroPdf417TimeStamp** | A vonalkód generálásának dátuma és időpontja – hasznos verziókövetéshez. |
| **MacroPdf417Addressee / Sender** | Egyedi karakterláncok, amelyek útválasztási információt tartalmazhatnak. |
| **MacroPdf417Terminator** | Jelzi, hogy ez a szegmens az utolsó-e (`Set`) vagy sem (`Unset`). |

> **Edge case:** Ha egy nagy dokumentumot sok szegmensre kíván felosztani, tartsa a `SegmentsCount` értékét konzisztensen az összes generált vonalkódban. A nem egyező számok dekódolási hibákat okoznak.

## A vonalkód képformátum kiválasztása és mentése

Az Aspose számos **vonalkód képformátumot** támogat (PNG, JPEG, BMP, TIFF, stb.). A PNG veszteségmentes, és a legtöbb web‑ és nyomtatási szituációban jól működik.

```csharp
                // Step 4: Save the generated barcode image
                string outputPath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode image saved to: {outputPath}");
            } // end using
        }
    }
}
```

Cserélje le a `YOUR_DIRECTORY`‑t egy abszolút vagy relatív mappára, ahol az alkalmazásnak írási joga van.

A program futtatásakor egy konzolüzenet jelenik meg, amely megerősíti a fájl helyét. Nyissa meg a PNG fájlt bármely képnézegetővel – egy tiszta **MacroPdf417 vonalkód** látható, amely a megadott szöveget és a definiált metaadatokat kódolja.

### Várható kimenet

```
Barcode image saved to: C:\Projects\BarcodeDemo\ExtPDF417Meta.png
```

A képfájl mérete nagyjából 30‑40 KB lesz, a választott `XDimension` és oszlopszám függvényében.

## A vonalkód ellenőrzése és hibakeresés

1. **Vizuális ellenőrzés** – A vonalkódnak egy sor egymásra rakott oszlopot kell mutatnia, körülötte csendes zónával (fehér margóval).  
2. **Dekódolási teszt** – Használjon vonalkód‑olvasó alkalmazást vagy az Aspose.BarCode `BarCodeReader` osztályt a kép visszaolvasásához, és ellenőrizze, hogy minden metaadatmező helyesen be van-e ágyazva.  



## Mit érdemes még megtanulni?

Az alábbi tutorialok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódrészleteket tartalmaz lépésről lépésre magyarázatokkal, hogy segítsenek elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket saját projektjeiben.

- [PDF417 vonalkód kép generálása Aspose.BarCode használatával C#‑ban – lépésről lépésre útmutató](/barcode/english/net/compact-pdf417-encoding/how-to-create-barcode-image-with-pdf417-in-c-step-by-step-gu/)
- [Hogyan generáljunk vonalkódot egyedi szöveggel az Aspose.BarCode for .NET használatával](/barcode/english/net/one-dimensional-barcode-types/how-to-generate-barcode-with-custom-text-using-aspose-barcod/)
- [Hogyan olvassunk vonalkódokat képből C#‑ban az Aspose.BarCode használatával – lépésről lépésre útmutató](/barcode/english/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}