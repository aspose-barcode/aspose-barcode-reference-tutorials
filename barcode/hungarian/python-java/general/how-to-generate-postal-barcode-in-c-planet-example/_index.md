---
category: general
date: 2026-10-28
description: Postai vonalkód generálása C#-ban a Planet formátummal. Ez a Planet vonalkód
  példa bemutatja, hogyan állítható be a vonalkód szélessége, és hogyan menthetők
  a kitöltött és üres sávok.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- set barcode width
- planet barcode example
language: hu
lastmod: 2026-10-28
og_description: Generáljon postai vonalkódot C#-ban egy teljes planet vonalkód példával.
  Tanulja meg beállítani a vonalkód szélességét, kitöltött sávokat előállítani, és
  üres sávú képeket létrehozni.
og_image_alt: Screenshot of a generated Planet postal barcode saved as PNG
og_title: Postai vonalkód generálása C#‑ban – lépésről‑lépésre útmutató
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  headline: How to generate postal barcode in C# – planet example
  type: TechArticle
- description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  name: How to generate postal barcode in C# – planet example
  steps:
  - name: Build the project (`dotnet build`).
    text: Build the project (`dotnet build`).
  - name: Run the executable (`dotnet run`).
    text: Run the executable (`dotnet run`).
  - name: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
    text: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
  - name: Open each image; you should see a series of vertical bars representing the
      numeric string
    text: Open each image; you should see a series of vertical bars representing the
      numeric string
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Hogyan generáljunk postai vonalkódot C#‑ban – planet példával
url: /hu/python-java/general/how-to-generate-postal-barcode-in-c-planet-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan generáljunk postai vonalkódot C#‑ban – planet példával

Ha C#‑ban kell postai vonalkódot generálnod, ez az útmutató egy teljes megoldáson keresztül vezet végig. Egy gyakorlati planet vonalkód példát láthatsz, amely numerikus karakterláncot kódol, lehetővé teszi a vonalkód szélességének beállítását, és elmenti mind a kitöltött, mind az üres sávok képeit.

Postai vonalkód létrehozásához nem szükséges összetett build pipeline. A tutorial végére képes leszel a vonalkód generálást bármely .NET alkalmazásba integrálni, testre szabni az X‑dimenziót, és kiválasztani, hogy a sávok kitöltöttek vagy üresek legyenek.

## Előfeltételek

* .NET 6.0 SDK vagy újabb telepítve  
* C# fejlesztői környezet (Visual Studio, VS Code vagy Rider)  
* A **Aspose.BarCode for .NET** NuGet csomag (23.10 vagy újabb verzió)  

A csomagot a következő paranccsal adhatod hozzá:

```bash
dotnet add package Aspose.BarCode
```

Az alábbi kódrészletek feltételezik, hogy a fájlod tetején hozzáadtad a `using Aspose.BarCode.Generation;` sort.

## Postai vonalkód generálása Planet szimbólummal

Az első lépés egy `BarcodeGenerator` példány létrehozása, amely a Planet szimbólumot használja. A Planet egy postai vonalkód formátum, amelyet több nemzeti postai szolgáltató is alkalmaz.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a Planet barcode generator with the data to encode
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Additional configuration will be applied here (see next steps)

        // Save the filled‑bars image
        barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // Switch to empty bars and save the second image
        barcodeGenerator.Parameters.Barcode.FilledBars = false;
        barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

**Miért fontos:**  
`EncodeTypes.Planet` azt mondja a könyvtárnak, hogy a Planet vonalkód szabványt használja, amely numerikus adatot kódol sávok és hézagok sorozatában. A konstruktor megkapja a kódolandó adatkarakterláncot (`"123456"` ebben az esetben).

A program futtatása két PNG fájlt hoz létre a végrehajtható munkakönyvtárában:

* **PostalPlanetFilledBars.png** – a sávok szilárd fekete téglalapokként jelennek meg.  
* **PostalPlanetEmptyBars.png** – a sávok fehér téglalapok fekete körvonallal, ami sötét háttérre nyomtatáskor hasznos.

## A vonalkód szélességének (X‑dimenzió) beállítása pixelekben

A vonalkód vizuális méretét az X‑dimenzió szabályozza, amely egyetlen sáv szélességét határozza meg. Ennek az értéknek a módosítása biztosítja, hogy a vonalkód a kívánt nyomtatási felbontásnál megfelelően olvasható legyen.

```csharp
// Define the width of each bar (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

**Miért érdemes beállítani:**  
A nagyobb X‑dimenzió megkönnyíti a vonalkód olvasását alacsony felbontású szkennerekkel, míg a kisebb érték csökkenti a teljes kép méretét nagy sűrűségű nyomtatáshoz. Az alapértelmezett szélesség 2 pixel; 4 pixel a legtöbb asztali nyomtató számára egy gyakori kompromisszum.

Kísérletezhetsz különböző értékekkel:

| Pixel | Tipikus felhasználási eset |
|-------|----------------------------|
| 2     | Nagy sűrűségű címkék |
| 4     | Szokásos irodai nyomtatás |
| 6‑8   | Nagyméretű jelzések |

**Tipp:** Mindig teszteld a generált vonalkódot a cél szkennerrel az X‑dimenzió módosítása után.

## Planet vonalkód példa – kitöltött vs. üres sávok

A Planet vonalkód megjeleníthető szilárd (kitöltött) vagy körvonalas (üres) sávokkal. A `FilledBars` tulajdonság kapcsolja ezt a viselkedést.

```csharp
// Save the barcode with the default filled bars
barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// Configure the generator to produce empty (unfilled) bars
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the barcode with empty bars
barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**Miért választhatod az üres sávokat:**  
Az üres sávok javítják a kontrasztot sötét árnyalatú csomagoláson, mivel minden sáv fehér belseje kiemelkedik a sötét háttérrel szemben. A kitöltött sávok az alapértelmezett beállítás, és jól működnek világos színű anyagokon.

**Várható kimenet:**  

*Mindkét kép ugyanazt a kódolt adatot (`123456`) jeleníti meg.* Az egyetlen vizuális különbség a sávstílus. Az alábbi szöveges leírás mutatja, mit látsz majd:

* **Filled bars image:** Szilárd fekete függőleges sávok fehér háttéren.  
* **Empty bars image:** Fekete körvonalak, amelyek ugyanazt a mintát alkotják, fehér belsőkkel.

A PNG fájlokat bármely képmegjelenítőben megnyitva ellenőrizheted, hogy a minta megfelel-e a Planet specifikációnak.

## További vonalkód tulajdonságok testreszabása (opcionális)

Míg a fenti alaplépések a legtöbb esetet lefedik, előfordulhat, hogy finomhangolni szeretnéd a többi beállítást:

| Tulajdonság | Leírás | Tipikus érték |
|------------|--------|---------------|
| `Barcode.Color` | A sávok előtér színe | `System.Drawing.Color.Black` |
| `Barcode.BackgroundColor` | Háttér kitöltő szín | `System.Drawing.Color.White` |
| `Barcode.CodeText` | Az ember által olvasható szöveg, amely a vonalkód alatt jelenik meg | Same as encoded data or a custom label |
| `Barcode.ImageFormat` | Kimeneti formátum (PNG, JPEG, BMP, stb.) | `BarCodeImageFormat.Png` |

Egy egyedi előtérszín beállításának példája:

```csharp
barcodeGenerator.Parameters.Barcode.Color = System.Drawing.Color.DarkBlue;
```

Ezek az opcionális finomítások segítenek a vállalati arculathoz igazodni vagy specifikus nyomtatási követelményeket teljesíteni.

## Gyakori hibák és elkerülésük módja

| Probléma | Ok | Megoldás |
|----------|----|----------|
| A vonalkód nem olvasható | Az X‑dimenzió túl kicsi a nyomtató DPI-jéhez | Növeld az `XDimension.Pixels` értékét 4‑re vagy nagyobbra |
| A képfájl sérült | Hiányzó írási jogosultság a célmappában | Használj abszolút elérési utat, vagy győződj meg arról, hogy a könyvtár létezik |
| Helytelen szimbólum használva | `EncodeTypes.Code128` átadása `EncodeTypes.Planet` helyett | Ellenőrizd, hogy az `EncodeTypes` argumentum megegyezik a postai formátummal |

**Pro tipp:** Mindig generálj egy teszt vonalkódot, és olvasd be a cél hardverrel, mielőtt éles környezetbe helyeznéd.

## Teljes, futtatható példa

Az alábbi önálló konzolalkalmazás tartalmazza a megbeszélt összes lépést. Másold a kódot egy új .NET konzolprojektbe, és futtasd, hogy a két PNG fájl megjelenjen a kimeneti mappában.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a Planet barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Set the width of each bar (X‑dimension) to 4 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the barcode with the default filled bars
            generator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved filled‑bars barcode as PostalPlanetFilledBars.png");

            // 4️⃣ Configure the generator to produce empty (unfilled) bars
            generator.Parameters.Barcode.FilledBars = false;

            // 5️⃣ Save the barcode with empty bars
            generator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved empty‑bars barcode as PostalPlanetEmptyBars.png");
        }
    }
}
```

**Ellenőrzési lépések:**  

1. Építsd fel a projektet (`dotnet build`).  
2. Futtasd a végrehajtható fájlt (`dotnet run`).  
3. Keresd meg a `PostalPlanetFilledBars.png` és `PostalPlanetEmptyBars.png` fájlokat a `bin/Debug/net6.0` mappában.  
4. Nyisd meg mindkét képet; egy sor függőleges sávot kell látnod, amely a numerikus karakterláncot ábrázolja


## Mit érdemes még megtanulni?

Az alábbi oktatóanyagok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsenek elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [Hogyan hozzunk létre planet vonalkódot kitöltött és üres sávokkal](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [Hogyan állítsuk be a szélességet és generáljunk Planet vonalkódot C#‑ban](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Postai vonalkód létrehozása C#‑ban – Teljes generátor példa](/barcode/english/python-java/general/create-postal-barcode-in-c-full-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}