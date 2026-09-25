---
category: general
date: 2026-08-22
description: Hogyan generáljunk vonalkódot C#‑ban az Aspose.BarCode használatával.
  Tanulja meg lépésről lépésre létrehozni a vonalkód képet C#‑ban, letiltani a 2‑D
  komponenst, és PNG fájlokként menteni.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode image c#
language: hu
lastmod: 2026-08-22
og_description: Hogyan generáljunk vonalkódot C#-ban az Aspose.BarCode segítségével.
  Ez az útmutató megmutatja, hogyan hozhatunk létre vonalkód képet C#-ban a DataBar
  Expanded használatával, hogyan kapcsolhatjuk be a 2‑D komponenst, és hogyan menthetünk
  PNG fájlokat.
og_image_alt: C# code screenshot generating a DataBar Expanded barcode image without
  the 2‑D component
og_title: Hogyan generáljunk vonalkódot C#‑ban – teljes útmutató a vonalkód kép létrehozásához
  C#‑ban
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode in C# using Aspose.BarCode. Learn to create
    barcode image c# step‑by‑step, disable the 2‑D component, and save PNG files.
  headline: How to generate barcode in C# – create barcode image c# with DataBar Expanded
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- image generation
title: Hogyan generáljunk vonalkódot C#-ban – vonalkód kép létrehozása C#-ban DataBar
  Expanded használatával
url: /hu/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan generáljunk vonalkódot C#‑ban – vonalkód kép létrehozása C#‑ban DataBar Expanded

A vonalkód generálása C#‑ban gyakori követelmény, amikor géppel olvasható adatot kell beágyazni az alkalmazásokba. Ez az útmutató bemutatja, hogyan hozhatunk létre vonalkód képet C#‑ban az Aspose.BarCode könyvtár segítségével, hogyan tilthatjuk le a 2‑D összetett komponenst, és hogyan menthetjük az eredményt PNG fájlokként.

Megtekint egy teljes, futtatható programot, a konfigurációs beállítások magyarázatát, valamint tippeket a kimenet testreszabásához. Külső dokumentációra nincs szükség – csak az alábbi kódra és egy .NET fejlesztői környezetre.

## Előfeltételek

* .NET 6.0 SDK vagy újabb telepítve  
* Visual Studio 2022 (vagy bármely .NET‑et támogató IDE)  
* Aspose.BarCode for .NET NuGet csomag (`Aspose.BarCode`)  

A csomagot a következő paranccsal adhatja hozzá:

```bash
dotnet add package Aspose.BarCode
```

A könyvtár biztosítja a `BarcodeGenerator` osztályt, amelyet az egész útmutatóban használunk.

## 1. lépés: A projekt beállítása és a névterek importálása

Hozzon létre egy új konzolos alkalmazást, és importálja a szükséges névtereket:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The rest of the code lives here
        }
    }
}
```

Az `Aspose.BarCode.Generation` névtér tartalmazza az összes osztályt, amely a vonalkódok konfigurálásához és megjelenítéséhez szükséges.

## 2. lépés: A DataBar Expanded vonalkód generátor inicializálása

Az első funkcionális sor egy `BarcodeGenerator`‑t hoz létre a **DataBar Expanded** szimbólumhoz, és megadja a nyers adatkarakterláncot. Az adatkarakterlánc a GS1 Alkalmazásazonosító formátumot követi: `(01)12345678901231`.

```csharp
// Step 2: Create a DataBar Expanded barcode generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpanded, "(01)12345678901231");
```

A generátor létrehozása lefoglalja a belső bitmap vásznat, így a renderelés előtt beállíthatja a méretet és a megjelenést.

## 3. lépés: A modul szélességének (X‑dimenzió) meghatározása

Az X‑dimenzió szabályozza a legkisebb vonalkódelem szélességét. Pixelben megadva pontos irányítást biztosít a végső kép mérete felett.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

`2` pixel érték jól működik képernyőn való megjelenítéshez; növelje, ha nagy felbontású nyomtatáshoz van szükség.

## 4. lépés: A 2‑D összetett komponens letiltása

A DataBar Expanded opcionálisan tartalmazhat egy 2‑D komponenst, amely további információkat hordoz. Ahhoz, hogy **e komponens nélkül** generáljon vonalkódot, állítsa a jelzőt `false`‑ra.

```csharp
// Step 4: Disable the 2‑D composite component of the DataBar barcode
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
```

A komponens letiltása csökkenti a vizuális komplexitást, és kisebb PNG fájlt eredményez.

## 5. lépés: A vonalkód kép mentése a 2‑D komponens nélkül

Válasszon egy kimeneti könyvtárat, és írja a képet a lemezre. A `BarCodeImageFormat.Png` enum biztosítja a veszteségmentes PNG fájlt.

```csharp
// Step 5: Save the barcode image without the 2‑D component
string outputDir = "YOUR_DIRECTORY/"; // replace with your actual path
barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png", BarCodeImageFormat.Png);
```

E hívás után a `Databar2DComponentDisabled.png` egy tiszta DataBar Expanded vonalkódot tartalmaz.

## 6. lépés: A 2‑D összetett komponens engedélyezése

Ha szüksége van a kiegészítő adatrétegre, állítsa vissza a jelzőt. Ugyanaz a generátor példány újra felhasználható, így elkerülhető egy második objektum létrehozása.

```csharp
// Step 6: Enable the 2‑D composite component
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
```

## 7. lépés: A vonalkód kép mentése a 2‑D komponens engedélyezésével

Renderelje a második képet ugyanazokkal a beállításokkal, kivéve a 2‑D jelzőt.

```csharp
// Step 7: Save the barcode image with the 2‑D component enabled
barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png", BarCodeImageFormat.Png);
```

Most a `Databar2DComponentEnabled.png` a vonalkódot mutatja a kiegészítő 2‑D mintával.

## Teljes forráskód

Másolja az alábbi teljes kódrészletet a `Program.cs` fájlba, és futtassa a projektet. A program létrehozza mindkét PNG fájlt a megadott mappában.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Create a DataBar Expanded barcode generator with the desired data
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpanded, "(01)12345678901231");

            // Set the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the output directory (change to a valid path on your machine)
            string outputDir = "YOUR_DIRECTORY/";

            // ---------- First image: 2‑D component disabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png",
                                 BarCodeImageFormat.Png);

            // ---------- Second image: 2‑D component enabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png",
                                 BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

### Várható kimenet

A program futtatása a következőket írja ki:

```
Barcode images generated successfully.
```

és két fájlt hoz létre:

* `Databar2DComponentDisabled.png` – vonalkód a 2‑D komponens nélkül  
* `Databar2DComponentEnabled.png` – vonalkód a 2‑D komponenssel  

Nyissa meg a PNG fájlokat bármely képnézőben a vizuális különbség ellenőrzéséhez.

## Gyakori variációk és szélsőséges esetek

| Situation | Adjustment |
|-----------|------------|
| **Eltérő szimbólum** | Cserélje le a `EncodeTypes.DatabarExpanded` értéket egy másikra, például `EncodeTypes.Code128`. |
| **Magasabb felbontás** | Növelje a `XDimension.Pixels` értékét 4‑re vagy 5‑re, vagy állítsa be a `Resolution`‑t a `barcodeGenerator.Parameters.Image`‑ben. |
| **Egyéb képformátumok** | Használja a `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp` vagy `BarCodeImageFormat.Svg` értékeket. |
| **Webalkalmazásban futtatás** | Közvetlenül streamelje a kép bájtjait a HTTP válaszba a lemezre mentés helyett. |
| **Memóriakezelés** | Tegye a generátort egy `using` blokkba, ha .NET Framework‑ot céloz, hogy biztosítsa a nem kezelt erőforrások felszabadítását. |

## Profi tippek

* **A generátor újrahasználata** – Csak a 2‑D jelző módosítása elkerüli az objektum újra‑példányosítását, ami CPU‑ciklusokat takarít meg.  
* **Adatok ellenőrzése** – A GS1 adatoknak pontosan meg kell felelniük a hossz- és ellenőrzőösszeg‑szabályoknak; érvénytelen bemenet `ArgumentException`‑t dob.  
* **Kötegelt feldolgozás** – Iteráljon egy adatkarakterlánc‑gyűjteményen, szükség szerint kapcsolja be vagy ki a 2‑D jelzőt, és mentse minden képet egyedi fájlnévvel.  

## Következtetés

Most már tudja, hogyan generáljon vonalkódot C#‑ban és hogyan hozza létre a vonalkód képet C#‑ban teljes irányítással a 2‑D összetett komponens felett. A példa bemutatja a generátor inicializálását, az X‑dimenzió beállítását, a komponens átkapcsolását, valamint a PNG fájlok mentését. Innen tovább felfedezheti a többi szimbólumot, beágyazhatja a képeket PDF‑ekbe, vagy integrálhatja a vonalkód generálást ASP.NET Core szolgáltatásokba.

--- 

*Következő lépések*: próbáljon meg QR kódokat generálni, kísérletezzen különböző képfelbontásokkal, vagy ágyazza be a generált PNG‑ket egy PDF‑be az Aspose.PDF használatával. Ezek a kiterjesztések ugyanazon a `BarcodeGenerator` API‑n alapulnak, és egységes munkafolyamatot biztosítanak.

## Mit érdemes még megtanulni?

Az alábbi útmutatók szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsen elsajátítani további API‑funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeiben.

- [Hogyan generáljunk DataMatrix vonalkódokat az Aspose.BarCode for .NET használatával – Lépésről‑lépésre útmutató](/barcode/english/net/datamatrix-barcode-configuration/)
- [Hogyan generáljunk és állítsuk be a vonalkód magasságát egy‑dimenziós Databar esetén az Aspose.BarCode for .NET használatával](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Hogyan generáljunk Aztec vonalkódot egyedi képaránnyal az Aspose.BarCode for .NET használatával](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}