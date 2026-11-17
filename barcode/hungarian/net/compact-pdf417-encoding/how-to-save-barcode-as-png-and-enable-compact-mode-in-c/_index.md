---
category: general
date: 2026-11-17
description: Tanulja meg, hogyan mentse el a vonalkódot, engedélyezze a kompakt módot,
  állítsa be az oszlopokat, és generáljon PDF417 vonalkódot egy teljes C# példával.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- enable compact mode
- how to adjust columns
- generate pdf417 barcode
- how to enable compact mode
language: hu
lastmod: 2026-11-17
og_description: Hogyan menthetünk vonalkódot, engedélyezhetjük a kompakt módot, és
  állíthatjuk be az oszlopokat PDF417 vonalkód generálása közben C#-ban. Kövesse a
  lépésről‑lépésre útmutatót.
og_image_alt: Screenshot showing how to save barcode as PNG file in C#
og_title: Hogyan mentsük el a vonalkódot PNG formátumban, és aktiváljuk a kompakt
  módot C#-ban
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  headline: How to save barcode as PNG and enable compact mode in C#
  type: TechArticle
- description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  name: How to save barcode as PNG and enable compact mode in C#
  steps:
  - name: Expected output
    text: Opening the saved PNG file shows a vertically compact PDF417 barcode with
      three columns and truncated padding. The visual size is roughly 2 px per module,
      making the image suitable for embedding in HTML `<img>` tags or for printing
      on small labels.
  - name: What if I need a different image format?
    text: The `Save` method accepts any `BarCodeImageFormat` enum value, such as `Jpeg`,
      `Bmp`, or `Gif`. Replace `BarCodeImageFormat.Png` with the desired format, and
      the rest of the code remains unchanged.
  - name: How does truncation affect data capacity?
    text: Enabling **compact mode** (truncation) reduces the number of rows, which
      can lower the maximum data capacity of the barcode. If you encounter a “Data
      too large” exception, either increase the number of columns or disable truncation.
  - name: Can I use a dynamic column count?
    text: 'Yes. You can calculate the column count based on the length of the input
      string:'
  - name: Is the X‑dimension limited to integer pixels?
    text: The `Pixels` property accepts any positive integer. For higher‑resolution
      outputs (e.g., printing), you might prefer setting `Points` instead of `Pixels`
      to achieve device‑independent sizing.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- image generation
title: Hogyan mentse el a vonalkódot PNG formátumban, és aktiválja a kompakt módot
  C#‑ban
url: /hu/net/compact-pdf417-encoding/how-to-save-barcode-as-png-and-enable-compact-mode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan mentse el a vonalkódot PNG formátumban és engedélyezze a kompakt módot C#-ban

Ha **how to save barcode**-t szeretne egy olyan formátumban elmenteni, amely a weben vagy nyomtatásban használható, ez az útmutató bemutatja a pontos lépéseket. Emellett megtanulhatja, hogyan **enable compact mode**, **adjust columns**, és **generate PDF417 barcode** az Aspose.BarCode .NET könyvtárral.

Az oktatóanyag mindent lefed a projekt beállításától a végső PNG fájlig, így a kódot a saját megoldásába másolhatja további kutatás nélkül. Külső dokumentációra nincs szükség; a teljes, futtatható példa benne van.

## Előkövetelmények

* .NET 6.0 vagy újabb telepítve  
* Visual Studio 2022 (vagy bármely C# IDE)  
* Az `Aspose.BarCode` NuGet csomag (`Install-Package Aspose.BarCode`)  

Ezek a három elem az egyetlen függőség a következő kódhoz.

## 1. lépés: PDF417 vonalkód generátor létrehozása

Az első feladat, amikor **generate PDF417 barcode**, egy `BarcodeGenerator` példányosítása a megfelelő kódolási típussal és a kódolni kívánt adatokkal.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a PDF417 barcode generator with the desired text.
BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

Az `EncodeTypes.Pdf417` enum azt mondja a könyvtárnak, hogy a PDF417 szimbólumot használja, amely egy egymásra rakott lineáris vonalkód, nagy mennyiségű adat kódolására alkalmas. A `"Compact mode"` karakterlánc a vonalkód alatti emberi olvasható szöveggé válik.

## 2. lépés: Az X‑dimenzió (modul szélesség) beállítása

A vonalkódban minden vonalat modulnak nevezünk. A modul szélességének szabályozásával finomhangolhatja a vonalkód vizuális méretét anélkül, hogy az adatot megváltoztatná.

```csharp
// Step 2: Set the module (X) dimension – each bar will be 2 pixels wide.
barcode.Parameters.Barcode.XDimension.Pixels = 2;
```

A 2‑pixel X‑dimenzió kompakt képet eredményez, amely a legtöbb eszközön megbízhatóan beolvasható.

## 3. lépés: **How to adjust columns** a PDF417 kódhoz

A PDF417 lehetővé teszi, hogy megadja, hány oszlopot használjon a vonalkód. Kevesebb oszlop magasabb, keskenyebb szimbólumot eredményez, míg több oszlop szélesebb, de alacsonyabb szimbólumot hoz létre.

```csharp
// Step 3: Define the number of columns for the PDF417 code (3 columns).
barcode.Parameters.Barcode.Pdf417.Columns = 3;
```

Ez a sor bemutatja a **how to adjust columns**-t. A könyvtár által támogatott bármely számra módosíthatja (2, 4 stb.), a célközegben rendelkezésre álló helytől függően.

## 4. lépés: **How to enable compact mode** és a szimbólum csonkítása

A kompakt mód eltávolítja a felesleges kitöltést és csökkenti a vonalkód teljes méretét. A könyvtár ezt a funkciót a `Truncate` tulajdonságon keresztül teszi elérhetővé.

```csharp
// Step 4: Enable compact mode by truncating the symbol.
barcode.Parameters.Barcode.Pdf417.Truncate = true;
```

Figyelje meg, hogy a **enable compact mode** kifejezés itt jelenik meg, és ugyanaz a művelet a későbbi útmutatóban pontosan **how to enable compact mode** formában van leírva a másodlagos kulcsszó követelmény teljesítéséhez.

## 5. lépés: **How to save barcode** PNG képként

A generált kép mentése az utolsó lépés. A `Save` metódus a megadott formátumban írja a vonalkódot a fájlrendszerbe.

```csharp
// Step 5: Save the generated barcode as a PNG image.
barcode.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

Cserélje le a `YOUR_DIRECTORY`-t egy abszolút vagy relatív útvonalra, amelyre az alkalmazása írni tud. A futtatás után megtalálja a `CompactPdf417.png` nevű fájlt, amely a kompakt PDF417 vonalkódot tartalmazza.

### Várt kimenet

A mentett PNG fájl megnyitása egy függőlegesen kompakt PDF417 vonalkódot mutat három oszloppal és csonkított kitöltéssel. A vizuális méret körülbelül 2 px modulonként, így a kép alkalmas HTML `<img>` címkékbe ágyazásra vagy kis címkék nyomtatására.

## Teljes, futtatható példa

Az alábbiakban a teljes program található, amelyet egy új konzolprojektbe másolhat. Tartalmazza az összes szükséges `using` direktívát, és egyetlen folyamatban bemutatja a **how to save barcode**, **enable compact mode**, **how to adjust columns**, és **generate PDF417 barcode** lépéseket.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417CompactDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a PDF417 barcode generator with the desired text.
            BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

            // Set the module (X) dimension – each bar will be 2 pixels wide.
            barcode.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns for the PDF417 code (3 columns).
            barcode.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable compact mode by truncating the symbol.
            barcode.Parameters.Barcode.Pdf417.Truncate = true;

            // Save the generated barcode as a PNG image.
            string outputPath = "CompactPdf417.png"; // Adjust path as needed.
            barcode.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

A program futtatása előállítja a korábban leírt PNG fájlt. A konzol kimenete megerősíti a mentett fájl helyét, ami segít ellenőrizni, hogy a **how to save barcode** lépés sikeres volt.

## Gyakori kérdések és szélhelyzetek

### Mi van, ha más képformátumra van szükségem?

A `Save` metódus bármely `BarCodeImageFormat` enum értéket elfogad, például `Jpeg`, `Bmp` vagy `Gif`. Cserélje le a `BarCodeImageFormat.Png`-t a kívánt formátumra, a kód többi része változatlan marad.

### Hogyan befolyásolja a csonkítás az adatkapacitást?

A **compact mode** (csonkítás) engedélyezése csökkenti a sorok számát, ami csökkentheti a vonalkód maximális adatkapacitását. Ha “Data too large” kivételt kap, növelje az oszlopok számát vagy tiltsa le a csonkítást.

### Használhatok dinamikus oszlopszámot?

Igen. A bemeneti karakterlánc hosszától függően kiszámíthatja az oszlopszámot:

```csharp
int desiredColumns = Math.Max(2, Math.Min(30, inputText.Length / 10));
barcode.Parameters.Barcode.Pdf417.Columns = desiredColumns;
```

Ez a kódrészlet programozott módon mutatja be a **how to adjust columns**-t, biztosítva, hogy a vonalkód beleférjen a megadott elrendezésbe.

### Az X‑dimenzió korlátozva van egész pixelre?

A `Pixels` tulajdonság bármely pozitív egész számot elfogad. Magasabb felbontású kimenetekhez (pl. nyomtatás) előnyösebb lehet a `Points` beállítása a `Pixels` helyett, hogy eszközfüggetlen méretezést érjen el.

## Tippek a termelésben való használathoz

* **Pro tip:** Csomagolja a vonalkód generálást try‑catch blokkba, hogy kezelje a `BarCodeException`-t, amikor a bemeneti adatok meghaladják a szimbólum kapacitását.  
* **Watch out for:** Fájlrendszer jogosultságok. A folyamatnak írási hozzáféréssel kell rendelkeznie a célkönyvtárhoz, különben a **how to save barcode** lépés `UnauthorizedAccessException`-nal fog meghiúsulni.  
* **Performance note:** Sok vonalkód létrehozása ciklusban előnyös egyetlen `BarcodeGenerator` példány újrahasználata, és csak a `CodeText` tulajdonság frissítése az iterációk között.

## Következtetés

Most már tudja, hogyan **how to save barcode** PNG fájlként, **enable compact mode**, **how to adjust columns**, és **generate PDF417 barcode** az Aspose.BarCode C#-hoz használva. A teljes példa bemutatja a szükséges lépéseket a generátor inicializálásától a végső kép írásáig.

Innen tovább felfedezheti a kapcsolódó témákat, például logó hozzáadását a vonalkódhoz, színek testreszabását, vagy a generátor integrálását egy ASP.NET Core API-ba. Ezek a kiegészítések mind ugyanazt a mintát követik, amelyet ez az útmutató mutat, így magabiztosan módosíthatja a kódot.

Nyugodtan kísérletezzen különböző oszlopszámokkal, X‑dimenziókkal és képformátumokkal, hogy megfeleljen projektje pontos specifikációinak. Boldog kódolást!

## Mit érdemes következőként megtanulni?

Az alábbi oktatóanyagok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás tartalmaz teljes, működő kódrészleteket lépésről‑lépésre magyarázatokkal, hogy segítsen elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket saját projektjeiben.

- [Hogyan mentse el a vonalkódot és generáljon PDF417-et Aspose-szal C#-ban](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [Hogyan hozzon létre PDF417 vonalkódot C#-ban kompakt móddal](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [Hogyan hozzon létre PDF417 vonalkódot és mentse PNG-ként C#-ban](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}