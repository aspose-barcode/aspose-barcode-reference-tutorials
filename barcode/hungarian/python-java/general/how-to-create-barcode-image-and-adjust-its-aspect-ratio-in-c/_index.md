---
category: general
date: 2026-10-08
description: Tanulja meg, hogyan hozhat létre vonalkód képet C#-ban, és fedezze fel,
  hogyan állíthatja be a képarányt a DataBar rétegezett omni‑directional vonalkódokhoz.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust aspect ratio
- Aspose.BarCode C#
- DataBar stacked omni‑directional
- barcode X‑dimension
language: hu
lastmod: 2026-10-08
og_description: Készítsen vonalkód képet C#‑ban, és tanulja meg, hogyan állítható
  be a képarány a DataBar stacked omni‑directional vonalkódoknál, egy teljes kódrészlettel.
og_image_alt: Result of create barcode image with aspect ratio 15 using Aspose.BarCode
og_title: Vonalkód kép létrehozása C#‑ban – lépésről lépésre útmutató
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  headline: How to create barcode image and adjust its aspect ratio in C#
  type: TechArticle
- description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  name: How to create barcode image and adjust its aspect ratio in C#
  steps:
  - name: Expected output
    text: 'After running the program you will find two PNG files in the execution
      directory:'
  - name: What if I need a different X‑dimension?
    text: You can change `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` to
      any integer greater than zero. For very high‑resolution output (e.g., 300 dpi),
      a value of 3‑4 pixels often yields clearer results.
  - name: How do I choose the right aspect ratio?
    text: 'The optimal ratio depends on the scanning environment: * **Low‑profile
      labels** – use a smaller ratio (e.g., 10‑15) to keep the barcode compact. *
      **Large shipping containers** – a higher ratio (e.g., 25‑35) improves readability
      from a distance. * **Regulatory requirements** – some standards mandate'
  - name: Can I generate other barcode formats with the same code?
    text: Yes. Replace `EncodeTypes.DatabarStackedOmniDirectional` with any other
      `EncodeTypes` value (e.g., `EncodeTypes.Code128`). The rest of the code—X‑dimension,
      aspect ratio (if applicable), and saving—remains the same.
  - name: What if I need to create the image in a different format?
    text: '`BarCodeImageFormat` supports PNG, JPEG, BMP, GIF, and TIFF. Just change
      the second argument of `Save`, for example:'
  - name: Next steps
    text: '* Explore other symbologies such as **Code128** or **QR Code** by swapping
      the `EncodeTypes` value. * Combine the barcode generation with PDF creation
      (e.g., using Aspose.PDF) to embed barcodes directly into invoices. * Experiment
      with dynamic aspect‑ratio selection based on label size—this extends '
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Hogyan lehet vonalkód képet létrehozni és a képarányát C#-ban beállítani
url: /hu/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan hozhatunk létre vonalkód képet, és állíthatjuk be az arányát C#-ban

Ha **programozottan kell vonalkód képet** létrehozni, ez az útmutató egy teljes, azonnal futtatható megoldást mutat be. Megmutatjuk, **hogyan állítható be az arány** egy DataBar stacked omni‑directional vonalkód esetén, ami gyakran előforduló követelmény a kiskereskedelmi és logisztikai alkalmazásokban.

Ebben a tutorialban megtanulod, hogyan:
* Inicializálj egy Aspose.BarCode `BarcodeGenerator`‑t a DataBar stacked omni‑directional szimbólumhoz.  
* Állítsd be az X‑dimenziót (modul szélesség) pixelekben a vonalvastagság szabályozásához.  
* Alkalmazz két különböző arányt, és mentsd el az eredményt PNG fájlként.  
* Ellenőrizd a kimenetet, és értsd meg, miért fontos az arány.

Nem szükséges külső eszköz – csak az Aspose.BarCode for .NET könyvtár és egy .NET 6 (vagy újabb) fejlesztői környezet.

## Hogyan hozhatunk létre vonalkód képet az Aspose.BarCode‑dal

Az első lépés a generátor példányosítása a kívánt szimbólummal és adatkarakterlánccal. Az `EncodeTypes.DatabarStackedOmniDirectional` enum azt mondja az Aspose.BarCode‑nak, hogy DataBar stacked omni‑directional vonalkódot állítson elő, amely széles körben használatos GS1‑128 alkalmazásokban.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a BarcodeGenerator for DataBar stacked omni‑directional.
        // The data string "(01)12345678901231" follows the GS1 Application Identifier format.
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Miért fontos:** A `BarcodeGenerator` objektum a kiindulópont minden vonalkód‑készítési feladathoz. A szimbólum és a nyers adat megadásával már a kezdetektől biztosítható, hogy a generált kép megfeleljen a GS1 szabványnak.

## Az X‑dimenzió (modul szélesség) beállítása

Az X‑dimenzió határozza meg a legkeskenyebb vonal (a modul) szélességét. Nagyobb X‑dimenzió vastagabb vonalkódot eredményez, ami alacsony felbontású nyomtatók esetén hasznos lehet.

```csharp
        // 2️⃣ Define the X‑dimension in pixels.
        // A value of 2 pixels provides a good balance between readability and file size.
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Miért fontos:** Az X‑dimenzió finomhangolása a vizuális beállítás része. Nem befolyásolja a kódolt adatot, de hatással van a különböző eszközökön történő beolvasás megbízhatóságára.

## Hogyan állítsuk be az arányt – első verzió (15)

Az arány szabályozza a DataBar vonalkód magasság‑szélesség arányát. A `DataBar.AspectRatio` tulajdonság egész számokat fogad; a nagyobb számok magasabb vonalakat eredményeznek.

```csharp
        // 3️⃣ Set the aspect ratio to 15 and save the first image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Miért fontos:** A 15‑ös arány a kiskereskedelmi szkennerek számára gyakori alapértelmezett érték. A keletkező PNG (`DatabarAspectRatio15.png`) magasabb megjelenést kap, ami javíthatja a kézi eszközökön történő beolvasás sikerességét.

## Hogyan állítsuk be az arányt – második verzió (30)

Bizonyos címkeformátumokhoz magasabb vonalkódra lehet szükség. Az arány módosítása egyszerűen egy új egész szám értékének hozzárendelésével történik a `Save` hívása előtt.

```csharp
        // 4️⃣ Change the aspect ratio to 30 and save a second image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Miért fontos:** Az **arány beállításának** bemutatásával ugyanabból az adatforrásból több vonalkód képet is előállíthatsz a generátor újbóli létrehozása nélkül. Ez csökkenti a memóriahasználatot és felgyorsítja a kötegelt feldolgozást.

### Várható kimenet

A program futtatása után két PNG fájlt találsz a végrehajtási könyvtárban:

| Fájlnév                       | Arány | Vizuális leírás |
|-------------------------------|-------|-----------------|
| `DatabarAspectRatio15.png`    | 15    | Standard magasság, a legtöbb POS‑szkennerhez megfelelő. |
| `DatabarAspectRatio30.png`    | 30    | Magasabb vonalak, nagy címkékhez vagy alacsony felbontású nyomtatókhoz hasznos. |

Mindkét kép ugyanazt a kódolt GTIN‑t `(01)12345678901231` tartalmazza, de a vizuális arányok a beállított arány szerint különböznek.

## Gyakori kérdések és szélsőséges esetek kezelése

### Mi van, ha más X‑dimenzióra van szükségem?

A `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` értékét bármely, nullánál nagyobb egész számra módosíthatod. Nagyon magas felbontású kimenet (pl. 300 dpi) esetén a 3‑4 pixel gyakran tisztább eredményt ad.

### Hogyan válasszam ki a megfelelő arányt?

Az optimális arány a beolvasási környezettől függ:
* **Alacsony profilú címkék** – használj kisebb arányt (pl. 10‑15), hogy a vonalkód kompakt maradjon.  
* **Nagy szállítócímkék** – a magasabb arány (pl. 25‑35) javítja a távolabbról történő olvashatóságot.  
* **Szabályozási követelmények** – egyes szabványok minimális magasságot írnak elő; a pontos számokért tekintsd meg a GS1 specifikációt.

### Generálhatok más vonalkód formátumokat ugyanazzal a kóddal?

Igen. Cseréld ki az `EncodeTypes.DatabarStackedOmniDirectional`‑t bármely más `EncodeTypes` értékre (pl. `EncodeTypes.Code128`). A többi kódrészlet – X‑dimenzió, arány (ha alkalmazható) és mentés – változatlan marad.

### Mi van, ha más formátumban kell a képet létrehozni?

A `BarCodeImageFormat` támogatja a PNG, JPEG, BMP, GIF és TIFF formátumokat. Csak módosítsd a `Save` második argumentumát, például:

```csharp
barcodeGenerator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
```

## Pro tipp: a generátor újrahasználata kötegelt feldolgozáshoz

Ha tucatnyi vonalkódot kell ugyanazzal a vizuális beállítással létrehozni, példányosítsd a generátort egyszer, csak a `CodeText` tulajdonságot frissítsd, és hívd meg többször a `Save`‑t. Így elkerülhető a belső pufferek ismételt lefoglalása.

```csharp
// Example of batch creation
string[] gtins = { "(01)12345678901231", "(01)98765432109876", "(01)55555555555555" };
foreach (var gtin in gtins)
{
    barcodeGenerator.CodeText = gtin;
    barcodeGenerator.Save($"Barcode_{gtin.Substring(4, 6)}.png", BarCodeImageFormat.Png);
}
```

## Összegzés

Most már tudod, **hogyan hozhatsz létre vonalkód képet** C#‑ban az Aspose.BarCode segítségével, és pontosan **hogyan állítható be az arány** a DataBar stacked omni‑directional szimbólumoknál. Az X‑dimenzió és az arány szabályozásával olyan vonalkódokat készíthetsz, amelyek bármely beolvasási vagy elrendezési követelménynek megfelelnek, miközben a megvalósítás egyszerű és karbantartható marad.

### Következő lépések

* Fedezz fel más szimbólumokat, például **Code128** vagy **QR Code** cserélve az `EncodeTypes` értékét.  
* Kombináld a vonalkód generálást PDF‑készítéssel (pl. Aspose.PDF) a vonalkódok közvetlen beágyazásához számlákba.  
* Kísérletezz dinamikus arányválasztással a címkemérettől függően – ez a **hogyan állítsuk be az arányt** mintát egy teljes funkcionalitású címketervező motorba bővíti.

Nyugodtan módosítsd a mintát, oszd meg az eredményeidet, vagy tegyél fel további kérdéseket a megjegyzésekben. Jó kódolást!

## Mit tanulj meg legközelebb?

A következő tutorialok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás komplett, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy könnyedén elsajátíthasd az API további funkcióit, és alternatív megvalósítási megközelítéseket is felfedezhess a saját projektjeidben.

- [How to create databar stacked barcode in C# with Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [How to create barcode image with Aspose.Barcode in C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}