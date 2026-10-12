---
category: general
date: 2026-10-12
description: Tanulja meg, hogyan hozhat létre micro PDF417 vonalkódot, és konvertálja
  azt PNG-re C#-ban. Lépésről lépésre útmutató teljes kóddal és tippekkel.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro PDF417 barcode
- convert barcode to PNG
- micro PDF417 C# example
- GS1 micro PDF417 generation
- barcode image settings
language: hu
lastmod: 2026-10-12
og_description: Készíts micro PDF417 vonalkódot, és konvertáld PNG formátumba C#-val.
  Kövesd ezt a teljes útmutatót, hogy mind a standard, mind a GS1 verziót előállítsd.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Micro PDF417 vonalkód létrehozása és PNG-re konvertálása – C# oktatóanyag
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn to create micro PDF417 barcode and convert barcode to PNG using
    C#. Step‑by‑step guide with full code and tips.
  headline: How to create micro PDF417 barcode and convert it to PNG in C#
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Hogyan készítsünk micro PDF417 vonalkódot, és konvertáljuk PNG-re C#-ban
url: /hu/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-convert-it-to-png-in/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan hozzunk létre micro PDF417 vonalkódot és konvertáljuk PNG-re C#-ban

Ha .NET alkalmazásban **micro PDF417 vonalkódot** kell létrehoznod, ez a bemutató pontosan megmutatja, hogyan. Egy teljes, futtatható példát láthatsz, amely generál egy szabványos Micro PDF417 vonalkódot és egy GS1‑kompatibilis változatot, majd **a vonalkódot PNG-re konvertálja** az olyan további felhasználásokhoz, mint a nyomtatás vagy a webes megjelenítés.

A vonalkód generálása több, mint egyetlen metódus meghívása – a megfelelő modulméret, oszlopszám és kódolási formátum kiválasztása befolyásolja a beolvasás megbízhatóságát. A útmutató végére megérted, miért fontos minden beállítás, és hogyan állíthatod őket a saját projektjeidhez.

## Előfeltételek

| Requirement | Reason |
|-------------|--------|
| .NET 6.0 SDK or later | Biztosítja a futtatókörnyezetet a C# konzolalkalmazáshoz |
| Visual Studio 2022 (or any C# IDE) | Megkönnyíti a szerkesztést és a hibakeresést |
| **Aspose.BarCode for .NET** NuGet package | Biztosítja a `BarcodeGenerator`, `EncodeTypes` és `BarCodeImageFormat` osztályokat |
| Write permission to the output folder | Szükséges a `Save` hívásokhoz, amelyek PNG fájlokat hoznak létre |

Az Aspose.BarCode csomagot a CLI-n keresztül adhatod hozzá:

```bash
dotnet add package Aspose.BarCode
```

## 1. lépés: Minimalista konzolprojekt beállítása

Hozz létre egy új konzolprojektet, és hivatkozz a vonalkód könyvtárra. A következő `Program.cs` tartalmazza az összes szükséges kódot; külső fájlokra nincs szükség.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace MicroPdf417Demo
{
    internal class Program
    {
        static void Main()
        {
            // Define the folder where PNG files will be saved
            string outputFolder = Environment.CurrentDirectory;

            // ------------------------------------------------------------
            // 1️⃣ Create a Micro PDF417 barcode generator with plain data
            // ------------------------------------------------------------
            BarcodeGenerator microGen = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,          // Micro PDF417 symbology
                "Micro data");                    // Simple alphanumeric payload

            // ------------------------------------------------------------
            // 2️⃣ Adjust the X dimension (module size) and set column count
            // ------------------------------------------------------------
            // XDimension controls the physical size of each barcode module.
            // A value of 2 pixels gives a compact yet readable barcode.
            microGen.Parameters.Barcode.XDimension.Pixels = 2;

            // For Micro PDF417 you can limit the number of columns.
            // Four columns keep the barcode small enough for labels.
            microGen.Parameters.Barcode.Pdf417.Columns = 4;

            // ------------------------------------------------------------
            // 3️⃣ Convert barcode to PNG and save the image
            // ------------------------------------------------------------
            string microPath = System.IO.Path.Combine(outputFolder, "MicroPdf417.png");
            microGen.Save(microPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Standard Micro PDF417 saved to: {microPath}");

            // ------------------------------------------------------------
            // 4️⃣ Create a GS1 Micro PDF417 barcode with AI‑encoded data
            // ------------------------------------------------------------
            // GS1 syntax requires Application Identifiers (AIs) wrapped in parentheses.
            // Example: (01) – GTIN, (21) – serial number.
            BarcodeGenerator gs1MicroGen = new BarcodeGenerator(
                EncodeTypes.Gs1MicroPdf417,
                "(01)12345678901231(21)ABC123");

            // ------------------------------------------------------------
            // 5️⃣ Set the X dimension for the GS1 barcode (same as step 2)
            // ------------------------------------------------------------
            gs1MicroGen.Parameters.Barcode.XDimension.Pixels = 2;

            // ------------------------------------------------------------
            // 6️⃣ Convert barcode to PNG and save the GS1 image
            // ------------------------------------------------------------
            string gs1Path = System.IO.Path.Combine(outputFolder, "GS1MicroPdf417.png");
            gs1MicroGen.Save(gs1Path, BarCodeImageFormat.Png);
            Console.WriteLine($"GS1 Micro PDF417 saved to: {gs1Path}");

            // End of demo
            Console.WriteLine("Barcode generation complete.");
        }
    }
}
```

### Miért fontos minden sor

* **`EncodeTypes.MicroPdf417` vs `EncodeTypes.Gs1MicroPdf417`** – Az első egy egyszerű Micro PDF417 vonalkódot hoz létre, míg a második a GS1 szabványt követi, beágyazva az Alkalmazás Azonosítókat (AIs). Válaszd azt, amelyikhez a downstream rendszered GS1 adatot vár.
* **`XDimension.Pixels = 2`** – A modul szélességét szabályozza. A kisebb értékek sűrűbb képet eredményeznek, de alacsony felbontású szkennereknél olvashatatlanná válhatnak. Két pixel a legtöbb címkenyomtató számára biztonságos alapértelmezett.
* **`Pdf417.Columns = 4`** – A Micro PDF417 lehetővé teszi az oszlopok korlátozását, csökkentve a teljes szélességet. Négy oszlop a vonalkódot kompaktan tartja anélkül, hogy a rövid adatmennyiség esetén csökkenne a kapacitás.
* **`BarCodeImageFormat.Png`** – A PNG veszteségmentes minőséget biztosít, ami elengedhetetlen a vonalkód tisztaságához. Ezért **a vonalkódot PNG-re konvertáljuk**, nem JPEG-re.

## 2. lépés: A program futtatása és a kimenet ellenőrzése

1. A projekt felépítése: `dotnet build`.
2. Futtatás: `dotnet run`.

A konzolon a következőhöz hasonló üzeneteket kell látnod:

```
Standard Micro PDF417 saved to: C:\Path\To\Project\MicroPdf417.png
GS1 Micro PDF417 saved to: C:\Path\To\Project\GS1MicroPdf417.png
Barcode generation complete.
```

Nyisd meg a generált PNG fájlokat bármely képnézegetővel. Mindkét kép éles, nagy kontrasztú vonalkódot mutat, amely készen áll a beolvasásra.

### Várható vizuális eredmény

| Barcode type | Appearance |
|--------------|------------|
| **Micro PDF417** | Kis téglalap alakú minta 4 oszloppal, a legtöbb 2‑D vonalkód szkennerrel olvasható. |
| **GS1 Micro PDF417** | Ugyanakkora, de GS1 AIs kódol; egy GS1-et értő szkenner visszaadja a GTIN-t és a sorozatszámot. |

Ha egy szkenner nem tudja beolvasni a képet, próbáld meg növelni a `XDimension.Pixels` értékét **3** vagy **4**-re, vagy csökkentsd az oszlopszámot a szabványos Micro PDF417 esetén.

## Gyakori buktatók és hogyan kerüld el őket

| Issue | Cause | Fix |
|-------|-------|-----|
| Blurry barcode after printing | Alacsony DPI nyomtató beállítások | Exportáld a PNG-t 300 dpi vagy magasabb felbontásban, vagy hagyd, hogy a nyomtató driver kezelje a méretezést. |
| Scanner returns “invalid data” | Hiányzó vagy hibás GS1 AI formátum | Győződj meg arról, hogy minden AI zárójelek közé van téve, és megfelel a GS1 specifikációnak (pl. `(01)` a GTIN‑14-hez). |
| Image file not created | A kimeneti mappának nincs írási joga | Futtasd a programot emelt jogosultságokkal, vagy válassz egy mappát, például `Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments)`. |
| Barcode too large for label | Az alapértelmezett oszlopszám túl magas | Csökkentsd a `Pdf417.Columns` értékét (pl. **3**-ra), vagy növeld az `XDimension`-t a teljes méret csökkentéséhez. |

## A példa kibővítése

* **Különböző képformátumok** – Cseréld le a `BarCodeImageFormat.Png`-t `Jpeg` vagy `Bmp`-re, ha a munkafolyamatod ezt igényli. A PNG továbbra is a legjobb választás a veszteségmentes minőséghez.
* **Dinamikus adatok** – Adj felhasználói bemenetet vagy adatbázis értékeket a `BarcodeGenerator` konstruktorának, hogy helyben hozz létre vonalkódokat.
* **Kötegelt generálás** – Tedd a létrehozási logikát egy ciklusba, amely CSV fájlból olvas sorokat, és minden vonalkódot egyedi fájlnévvel ment.

## Összegzés

Most már tudod, hogyan **hozz létre micro PDF417 vonalkódot** C#-ban, és hogyan **konvertáld a vonalkódot PNG-re** mind szabványos, mind GS1‑kompatibilis esetekben. A teljes, futtatható kód bemutatja a lényeges beállításokat – X dimenzió, oszlopszám és kódolási típus – így a megoldást bármely .NET projekthez alkalmazhatod, amelynek kompakt, magas minőségű 2‑D vonalkódokra van szüksége.

*Következő lépések*: fedezd fel az Aspose.BarCode által támogatott egyéb szimbólumkészleteket (pl. QR, DataMatrix), kísérletezz különböző `XDimension` értékekkel a nagy felbontású nyomtatáshoz, vagy integráld a generált PNG-ket egy web API-ba, amely igény szerint szolgáltat vonalkódokat.

## Mit érdemes még megtanulni?

A következő bemutatók szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás tartalmaz teljes, működő kódrészleteket lépésről‑lépésre magyarázatokkal, hogy segítsenek elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [Hogyan hozzunk létre micro pdf417 vonalkódot C#-ban és mentsük PNG-ként](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-and-save-it-as-png/)
- [Vonalkód PNG létrehozása C#-ban – teljes útmutató a GS1 Micro PDF417-hez](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [Micro PDF417 vonalkód generálása C#-ban – Teljes útmutató](/barcode/english/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}