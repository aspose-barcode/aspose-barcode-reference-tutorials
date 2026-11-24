---
category: general
date: 2026-11-23
description: Tanulja meg, hogyan használja a BarCodeReader-t C#-ban a vonalkódok képről
  történő olvasásához, beleértve a Macro PDF417 dekódolást, egy teljes kódrészlettel
  és világos magyarázatokkal.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use barcodereader
- read barcodes from image c#
language: hu
lastmod: 2026-11-23
og_description: Hogyan használjuk a BarCodeReader-t C#‑ban a vonalkódok képből történő
  olvasásához. Kövesd ezt a lépésről‑lépésre útmutatót a Macro PDF417 és más formátumok
  dekódolásához, kész‑futtatható kóddal.
og_image_alt: Screenshot of BarCodeReader console output showing decoded Macro PDF417
  data
og_title: Hogyan használjuk a BarCodeReader-t C#-ban – olvassunk gyorsan vonalkódokat
  képekből
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  headline: How to use BarCodeReader in C# to read barcodes from images
  type: TechArticle
- description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  name: How to use BarCodeReader in C# to read barcodes from images
  steps:
  - name: 1. Decoding multiple barcode formats
    text: 'If you need to detect more than one format, pass a combined `DecodeType`
      flag:'
  - name: 2. Managing large images
    text: 'Large images can cause high memory usage. Downscale the image before passing
      it to the reader:'
  - name: 3. Error handling
    text: 'Wrap the reading logic in a try‑catch block to surface decoding failures:'
  type: HowTo
tags:
- barcode
- C#
- image-processing
title: Hogyan használjuk a BarCodeReader-t C#-ban a képekben lévő vonalkódok olvasásához
url: /hu/net/compact-pdf417-encoding/how-to-use-barcodereader-in-c-to-read-barcodes-from-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan használjuk a BarCodeReader-t C#-ban vonalkódok képekből történő olvasásához

Ha gyors vonalkódolvasásra van szükséged a **BarCodeReader használatával**, ez az útmutató pontosan ezt mutatja be. Akár egy értékesítési pont (POS) rendszert építesz, akár a dokumentumok automatizált feldolgozását valósítod meg, néhány sor kóddal megtanulod, hogyan olvass vonalkódokat képekből C# projektekben.

Ebben a tutorialban egy teljes, futtatható példát látsz, amely dekódolja a Macro PDF417 vonalkódot, kinyeri a kiterjesztett tulajdonságait, és hasznos információkat ír ki a konzolra. Külső dokumentációra nincs szükség – minden, amire szükséged van, itt található.

## Előfeltételek

* .NET 6.0 (vagy újabb) telepítve – a kód a legújabb LTS verziót célozza.
* Hivatkozás a **Aspose.BarCode** (vagy bármely kompatibilis) NuGet csomagra, amely biztosítja a `BarCodeReader`-t.
* Egy képfájl, amely Macro PDF417 vonalkódot tartalmaz (a példa a `ExtPDF417Meta.png` fájlt használja).

> **Pro tipp:** Ha Visual Studio-t használsz, add hozzá a csomagot a `dotnet add package Aspose.BarCode` paranccsal vagy a NuGet Package Manager UI segítségével.

## 1. lépés: BarCodeReader példány létrehozása

Az első dolog, amit egy vonalkód könyvtárral dolgozva megteszel, hogy példányosítod a olvasót, amely a forrásképre mutat, és megmondja az API-nak, mely vonalkódtípus(ok)ra kell keresni.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Step 1: Initialise BarCodeReader for a Macro PDF417 image
using (BarCodeReader barcodeReader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png",
           DecodeType.MacroPdf417))
{
    // The using block guarantees proper disposal of native resources.
```

*Miért fontos ez a lépés:*  
`BarCodeReader` megnyitja a képet, lefoglal natív memóriát, és előkészíti a dekódolási algoritmusokat a megadott `DecodeType` számára. A típus `MacroPdf417`-re korlátozásával csökkented a CPU terhelést és javítod a detektálás pontosságát.

## 2. lépés: Olvasd be az összes a képen található vonalkódot

Egyetlen kép több vonalkódot is tartalmazhat, különösen makró‑kódolt adatok esetén. A `ReadBarCodes` metódus egy `BarCodeResult` objektumok enumerálhatóját adja vissza, amelyek mindegyike egy észlelt kódot képvisel.

```csharp
    // Step 2: Iterate over every barcode found
    foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
    {
```

*Miért fontos ez a lépés:*  
A gyűjteményen való iterálás biztosítja, hogy minden előfordulást elkapj, ami elengedhetetlen kötegelt feldolgozási esetekben vagy amikor egy dokumentum több kódot tartalmaz.

## 3. lépés: A kiterjesztett Macro PDF417 tulajdonságok elérése

A Macro PDF417 extra metaadatokat tárol, mint például fájlazonosítók, szegmensszámok és a teljes szegmensszám. Ezek az értékek a `BarCodeResult` `Extended.Pdf417` tulajdonságán keresztül érhetők el.

```csharp
        // Step 3: Pull extended Macro PDF417 information
        var macroInfo = barcodeResult.Extended.Pdf417;
```

*Miért fontos ez a lépés:*  
A kiterjesztett mezők lehetővé teszik több szegmensből álló dokumentumok újraépítését vagy annak ellenőrzését, hogy minden rész ugyanahhoz a forráshoz tartozik-e. Ennek a lépésnek a kihagyása csak a nyers szöveget adja, elveszítve a fontos kontextust.

## 4. lépés: A leghasznosabb információk kiírása

Végül írd ki az adatokat a konzolra (vagy bármely naplózóba), hogy ellenőrizhesd a beolvasási műveletet. A példa kiírja a kód típusát, a dekódolt szöveget és több makró mezőt.

```csharp
        // Step 4: Display key details
        Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
        Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
        Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
        // Additional macro fields are available:
        // macroInfo.MacroPdf417SegmentID
        // macroInfo.MacroPdf417SegmentsCount
    }
}
```

**Várható konzol kimenet**

```
Code Type: MacroPdf417
Code Text: 1234567890
Macro PDF417 File ID: 42
```

> **Megjegyzés:** Ha a kép nem tartalmaz Macro PDF417 vonalkódot, a `ReadBarCodes()` üres gyűjteményt ad vissza, és a ciklus teste soha nem fut le. Mindig ellenőrizd, hogy a visszatérési érték üres-e a produkciós kódban.

## Vonalkódok olvasása képből C#‑ban – gyakori helyzetek kezelése

### 1. Több vonalkódformátum dekódolása

Ha egynél több formátumot kell észlelned, adj meg egy kombinált `DecodeType` zászlót:

```csharp
using (BarCodeReader reader = new BarCodeReader(
           "sample.png",
           DecodeType.Pdf417 | DecodeType.QR | DecodeType.DataMatrix))
{
    // Same iteration logic as before
}
```

### 2. Nagy képek kezelése

A nagy képek magas memóriahasználatot okozhatnak. Méretezd le a képet, mielőtt átadod az olvasónak:

```csharp
using (Bitmap original = new Bitmap("large.png"))
using (Bitmap resized = new Bitmap(original, new Size(1024, 768)))
{
    // Save resized image to a temporary stream and feed it to BarCodeReader
}
```

### 3. Hibakezelés

Tedd a beolvasási logikát try‑catch blokkba, hogy a dekódolási hibákat felszínre hozd:

```csharp
try
{
    // reading code from previous steps
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## Teljes működő példa

Az alábbiakban a teljes program látható, amelyet másolhatsz, beilleszthetsz és futtathatsz. Tartalmazza az összes lépést, a szükséges `using` direktívákat és egy egyszerű hibakezelő vázat.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        try
        {
            using (BarCodeReader barcodeReader = new BarCodeReader(
                       imagePath,
                       DecodeType.MacroPdf417))
            {
                bool anyFound = false;

                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    anyFound = true;
                    var macroInfo = barcodeResult.Extended.Pdf417;

                    Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
                    Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
                    Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
                    Console.WriteLine($"Segment ID: {macroInfo.MacroPdf417SegmentID}");
                    Console.WriteLine($"Segments Count: {macroInfo.MacroPdf417SegmentsCount}");
                    Console.WriteLine(new string('-', 40));
                }

                if (!anyFound)
                {
                    Console.WriteLine("No barcodes were detected in the image.");
                }
            }
        }
        catch (BarCodeException ex)
        {
            Console.Error.WriteLine($"Error reading barcode: {ex.Message}");
        }
    }
}
```

**A program futtatása** kiírja minden észlelt Macro PDF417 vonalkódot és annak kiterjesztett mezőit, vagy tájékoztat, ha nem található vonalkód.

## Összegzés

Most már tudod, **hogyan használjuk a BarCodeReader-t** vonalkódok képekből történő olvasásához C# alkalmazásokban, beleértve a Macro PDF417 metaadatok kinyerését is. A megoldás lefedi a inicializálást, az iterációt, a kiterjesztett tulajdonságok elérését, valamint gyakorlati tippeket ad a több formátum, nagy képek és hibák kezelésére.

Ezután érdemes lehet:

* **QR kódok olvasása** – cseréld le a `DecodeType.MacroPdf417`-t `DecodeType.QR`-re.
* **Dekódolt adatok mentése** adatbázisba vagy JSON fájlba a további feldolgozáshoz.
* **Integráció ASP.NET Core‑dal** a feltöltött képek web API-n keresztüli fogadásához.

Nyugodtan kísérletezz különböző vonalkódtípusokkal és képforrásokkal. Boldog kódolást!

## Mi legyen a következő tanulnivalód?

A következő tutorialok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsenek elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [c# vonalkód olvasó tutorial – Macro PDF417 vonalkódok lépésről‑lépésre olvasása a GroupDocs.Barcode használatával](/barcode/english/net/compact-pdf417-encoding/c-barcode-reader-tutorial-read-macro-pdf417-barcodes-step-by/)
- [Hogyan használjunk vonalkód generátort C#-ban Macro PDF417-hez](/barcode/english/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/)
- [Vonalkód olvasása képből C#‑ban – teljes útmutató Macro PDF417‑val](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}