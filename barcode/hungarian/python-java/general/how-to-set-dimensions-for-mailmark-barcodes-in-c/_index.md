---
category: general
date: 2026-08-22
description: Tanulja meg, hogyan állíthatja be a Mailmark vonalkódok méreteit C#-ban,
  és mentheti őket PNG képként. Teljes kód, magyarázatok és tippek.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set dimensions
- Mailmark barcode C# example
- BarcodeGenerator dimensions
- set barcode size in C#
- save barcode as PNG
language: hu
lastmod: 2026-08-22
og_description: Hogyan állítsuk be a Mailmark vonalkódok méreteit C#-ban, és exportáljuk
  őket PNG fájlokként. Kövesse a teljes példát, és kerülje el a gyakori hibákat.
og_image_alt: Screenshot of two generated Mailmark barcode PNG files showing different
  dimensions
og_title: Hogyan állítsuk be a Mailmark vonalkódok méreteit C#-ban – lépésről‑lépésre
  útmutató
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to set dimensions for Mailmark barcodes in C# and save them
    as PNG images. Includes full code, explanations, and tips.
  headline: How to set dimensions for Mailmark barcodes in C#
  type: TechArticle
tags:
- C#
- barcode
- Mailmark
- image generation
title: Hogyan állítsuk be a Mailmark vonalkódok méreteit C#‑ban
url: /hu/python-java/general/how-to-set-dimensions-for-mailmark-barcodes-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan állítsuk be a méreteket a Mailmark vonalkódokhoz C#-ban

Ha **a méretek beállítására** van szükséged egy Mailmark vonalkódhoz C#-ban, ez az útmutató pontos lépéseket mutat. Megmutatjuk, hogyan konfigurálhatod az X‑dimenziót és a vonalmagasságot, majd hogyan mentheted a vonalkódot PNG képként extra eszközök nélkül.

A postai vonalkódok generálása rutinfeladat a címkenyomtató szoftverek fejlesztésekor, de az alapértelmezett méret gyakran nem felel meg a nyomtató vagy a layout követelményeinek. A tutorial végére pontosan tudni fogod, hogyan szabályozhatod a vonalkód méretét, és hogyan állíthatsz elő két érvényes Mailmark típust (C‑type és L‑type) nyomtatásra kész állapotban.

**Mit fogsz megtanulni**

* Hogyan állítsd be az X‑dimenziót (modul szélesség) és a vonalmagasságot egy `BarcodeGenerator` esetén.
* Hogyan mentsd el a generált vonalkódot PNG fájlként a `BarCodeImageFormat` használatával.
* Gyakori buktatók, például érvénytelen mappapath vagy nem támogatott dimenzióértékek.
* Tippek az azonos konfiguráció újra‑használatához több vonalkód esetén.

## Előfeltételek

* .NET 6.0 vagy újabb (a kód .NET Framework 4.6+‑al is működik).
* Az **Aspose.BarCode for .NET** NuGet csomag (vagy bármely kompatibilis könyvtár, amely biztosítja a `BarcodeGenerator`, `EncodeTypes` és `BarCodeImageFormat` osztályokat).
* Alapvető C# szintaxis és fájl‑I/O ismeretek.

> **Pro tipp:** Telepítsd a csomagot a CLI paranccsal  
> `dotnet add package Aspose.BarCode` a projekt tisztasága érdekében.

## 1. lépés: A kimeneti mappa definiálása

Mielőtt bármilyen vonalkódot létrehoznál, el kell döntened, hová kerüljenek a PNG fájlok. Egy abszolút útvonal használata elkerüli a meglepetéseket különböző gépeken.

```csharp
// Step 1: Define the folder where the barcode images will be saved
string outputFolder = @"C:\Temp\Barcodes\";

// Ensure the directory exists; create it if necessary
if (!Directory.Exists(outputFolder))
{
    Directory.CreateDirectory(outputFolder);
}
```

*Miért fontos*: Ha a mappa nem létezik, a `Save` `IOException`‑t dob. A `Directory.CreateDirectory` hívás idempotens – semmit sem csinál, ha a mappa már létezik.

## 2. lépés: Mailmark C‑type vonalkód létrehozása és **méretek beállítása**

A Mailmark C‑type egy 20 karakteres alfanumerikus stringet kódol. A generátor inicializálása után a `Parameters.Barcode` objektumon keresztül **beállíthatod a méreteket**.

```csharp
// Step 2: Create a Mailmark C‑type barcode, configure its size, and save it as PNG
BarcodeGenerator mailmarkC = new BarcodeGenerator(EncodeTypes.Mailmark, "21B2254800659JW5O9QA6Y");

// Set the width of a single module (X‑dimension) to 4 pixels
mailmarkC.Parameters.Barcode.XDimension.Pixels = 4;

// Set the overall bar height to 50 pixels
mailmarkC.Parameters.Barcode.BarHeight.Pixels = 50;

// Save the image; the second argument specifies PNG format
mailmarkC.Save($"{outputFolder}PostalMailmarkCType.png", BarCodeImageFormat.Png);
```

### Miért ezek az értékek?

* **X‑dimension** szabályozza a legkisebb vonal (a „modul”) szélességét. A `4` pixel érték könnyen olvasható vonalkódot eredményez a legtöbb lézernyomtató számára, miközben a fájlméret is alacsony marad.
* **BarHeight** határozza meg a vonalak függőleges méretét. Az `50` pixel gyakori magasság a szabványos címkékhez, de nagyobb formátumokhoz növelhető.

> **Szélsőséges eset:** Egyes nyomtatók legalább 30 px vonalmagasságot igényelnek. Ha a magasságot alacsonyabbra állítod, a nyomtató nem tudja megfelelően olvasni a vonalkódot.

## 3. lépés: Mailmark L‑type vonalkód létrehozása és **méretek beállítása**

Az L‑type hosszabb adatstringet (legfeljebb 30 karakter) használ. Ugyanez a méret‑beállítási módszer alkalmazandó.

```csharp
// Step 3: Create a Mailmark L‑type barcode, configure its size, and save it as PNG
BarcodeGenerator mailmarkL = new BarcodeGenerator(EncodeTypes.Mailmark, "41038422416563762EF61AH8T");

// Reuse the same dimension settings for consistency
mailmarkL.Parameters.Barcode.XDimension.Pixels = 4;
mailmarkL.Parameters.Barcode.BarHeight.Pixels = 50;

// Save the L‑type barcode image
mailmarkL.Save($"{outputFolder}PostalMailmarkLType.png", BarCodeImageFormat.Png);
```

### Konfiguráció újra‑használata

Ha sok vonalkódot generálsz azonos méretekkel, érdemes a konfigurációt egy segédmetódusba kiszervezni:

```csharp
void ApplyStandardDimensions(BarcodeGenerator generator)
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.BarHeight.Pixels = 50;
}
```

Az `ApplyStandardDimensions(mailmarkC)` és `ApplyStandardDimensions(mailmarkL)` hívások csökkentik a duplikációt, és a jövőbeni változtatásokat (például 5‑pixel modulra váltás) egyetlen soros szerkesztéssel elvégezheted.

## 4. lépés: A generált PNG fájlok ellenőrzése

A program futtatása után nyisd meg a két PNG fájlt bármely képnézőben. Két különálló Mailmark vonalkódot kell látnod, mindegyik 4 px modul‑szélességgel és 50 px magassággal.

*Várható kimenet*

| Fájlnév                         | Kb. méretek (px)          |
|--------------------------------|---------------------------|
| `PostalMailmarkCType.png`      | 4 px × modul × N modulok |
| `PostalMailmarkLType.png`      | 4 px × modul × N modulok |

A pontos szélesség az enkódolt adat hossza függvénye, de a magasság mindig **50 px** lesz, mivel a `BarHeight.Pixels` értéket így állítottuk be.

## Gyakori buktatók és megoldások

| Probléma                              | Tünet                                          | Megoldás |
|---------------------------------------|-----------------------------------------------|----------|
| Érvénytelen mappapath                  | `IOException: Could not find a part of the path` | Használd a `Path.Combine`‑t az `Environment.SpecialFolder`‑dal, vagy ellenőrizd a path stringet. |
| X‑dimension 0 vagy negatív értékre állítva | A vonalkód egy szilárd blokk lesz            | Győződj meg róla, hogy az `XDimension.Pixels` pozitív egész szám (minimum 1). |
| Nem támogatott `EncodeTypes.Mailmark` | `ArgumentException` a generátor létrehozásakor | Ellenőrizd, hogy a Aspose.BarCode könyvtár legújabb verzióját használod, amely tartalmazza a Mailmark támogatást. |
| Hibás képformátummal mentés            | Sérült PNG fájl                               | Használd a `BarCodeImageFormat.Png`‑t (vagy `Jpeg`‑et, ha más formátumra van szükséged). |

## A példa kiterjesztése

* **Eltérő méretek** – Állítsd az `XDimension.Pixels`‑t 3‑ra a kompaktabb vonalkódért, vagy növeld a `BarHeight.Pixels`‑t 70‑re nagyobb címkékhez.
* **Kötegelt generálás** – Egy adatstring gyűjteményen iterálva alkalmazd minden iterációban ugyanazt a méretbeállítást.
* **Más képformátumok** – Cseréld a `BarCodeImageFormat.Png`‑t `BarCodeImageFormat.Jpeg`‑re vagy `BarCodeImageFormat.Bmp`‑re, ha a munkafolyamatod más formátumot igényel.

## Összegzés

Most már tudod, **hogyan állítsd be a méreteket** a Mailmark vonalkódokhoz C#‑ban, és hogyan exportáld őket PNG fájlokként. Az `XDimension.Pixels` és a `BarHeight.Pixels` konfigurálásával irányíthatod a C‑type és L‑type vonalkódok vizuális méretét, biztosítva, hogy megfeleljenek a nyomtató specifikációinak és a layout követelményeinek.  

Innen tovább kísérletezhetsz különböző dimenzióértékekkel, beépítheted a kódot egy nagyobb címkenyomtató rendszerbe, vagy kötegelt vonalkódokat generálhatsz tömeges küldeményekhez.

---

*Következő lépések*: fedezd fel a **BarcodeGenerator dimensions** beállításait QR kódokhoz, vagy olvasd el az Aspose.BarCode dokumentációját a **DPI beállításáról** nagy felbontású nyomtatásokhoz. Ha PDF‑be szeretnéd ágyazni a vonalkódot, kombináld ezt a megközelítést az **Aspose.PDF** könyvtárral egy teljes körű end‑to‑end megoldáshoz.

## Mit érdemes még megtanulni?

Az alábbi tutorialok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás komplett, működő kódpéldákat tartalmaz lépésről‑lépésre magyarázatokkal, hogy könnyedén elsajátíthasd az API további funkcióit, és alternatív megvalósítási módokat is felfedezhess a saját projektjeidben.

- [How to Set Border for ITF-14 Barcode Customization](/barcode/english/net/itf-14-barcode-customization/)
- [How to Configure Patch Code Barcodes with Aspose.BarCode for .NET](/barcode/english/net/patch-code-configuration/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}