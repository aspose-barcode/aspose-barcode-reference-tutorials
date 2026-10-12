---
category: general
date: 2026-10-12
description: Hogyan állítsuk be a vonalkód magasságát és generáljunk DataBar vonalkódot
  C#-ban az Aspose.BarCode használatával. Kövesse a lépésről‑lépésre útmutatót a teljes
  kóddal.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- generate barcode c#
- how to create databar
- create databar barcode
- change barcode height
language: hu
lastmod: 2026-10-12
og_description: Hogyan állítsuk be a vonalkód magasságát C#-ban, és generáljunk DataBar
  vonalkódot az Aspose.BarCode segítségével. Ismerje meg a teljes kódot, hogy miért
  fontos minden lépés, és hogyan változtathatja meg a vonalkód magasságát.
og_image_alt: Screenshot showing how to set barcode height in a C# barcode generator
og_title: Hogyan állítsuk be a vonalkód magasságát és generáljunk DataBar vonalkódot
  C#‑ban
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to set barcode height and generate a DataBar barcode in C# using
    Aspose.BarCode. Follow a step‑by‑step guide with complete code.
  headline: How to set barcode height, generate DataBar barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Hogyan állítsuk be a vonalkód magasságát, és generáljunk DataBar vonalkódot
  C#-ban
url: /hu/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan állítsuk be a vonalkód magasságát, generáljunk DataBar vonalkódot C#-ban

Ha programozott módon kell **how to set barcode** méreteket beállítani, ez az útmutató pontos lépéseket mutat. Megtanulja, hogyan generáljon DataBar Omni‑directional vonalkódot, állítsa be a magasságát, és mentse el mindkét változatot PNG fájlokként.

A vonalkód sávmagasságának módosítása gyakori követelmény, amikor vonalkódokat integrálunk nyugtákba, termékcímkékbe vagy mobil képernyőkre. Az alábbi példa az Aspose.BarCode könyvtárat használja, amely támogatja a GS1 DataBar szimbólumok teljes skáláját.

## Mit fog elérni

* **how to set barcode** height for a DataBar Omni‑directional barcode – magasságát egy DataBar Omni‑directional vonalkódhoz  
* **generate barcode c#** code that creates two images with different heights – kód, amely két különböző magasságú képet hoz létre  
* understand **how to create databar** symbols and why the bar height matters – szimbólumokat, és hogy miért fontos a sávmagasság  
* apply **change barcode height** logic without recreating the generator – logikát a **change barcode height** anélkül, hogy újra létrehozná a generátort  

Külső eszközök nem szükségesek az Aspose.BarCode NuGet csomag és egy .NET 6+ futtatókörnyezet mellett.

## Előfeltételek

* .NET 6 SDK vagy újabb telepítve  
* Visual Studio 2022 (vagy bármely C# szerkesztő)  
* Aspose.BarCode for .NET – telepítés: `dotnet add package Aspose.BarCode`  

> **Pro tip:** Használja az Aspose ingyenes próbalicencét, ha nincs kereskedelmi kulcsa; az API ugyanúgy működik.

## 1. lépés: Az Aspose.BarCode csomag telepítése

Nyisson egy terminált a projekt mappájában, és futtassa:

```bash
dotnet add package Aspose.BarCode
```

A csomag hozzáadja az `Aspose.BarCode` névteret, amely tartalmazza a `BarcodeGenerator` osztályt, amelyet a **generate barcode c#** képekhez fogunk használni.

## 2. lépés: DataBar vonalkód generátor létrehozása

Az első konkrét lépés a **how to set barcode** paraméterekhez a `BarcodeGenerator` példányosítása a kívánt szimbólummal és adatstringgel.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 2: Initialize the generator for a DataBar Omni‑directional barcode
var barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, // symbology
    "(01)12345678901231");               // GS1 data payload
```

*Miért fontos:* `EncodeTypes.DatabarOmniDirectional` egy kompakt, minden irányból olvasható DataBar-t hoz létre, amely ideális kis címkékhez.

## 3. lépés: Általános vonalkód paraméterek beállítása (beleértve a kezdeti sávmagasságot)

Most megválaszoljuk a **how to set barcode** X‑dimenzió és sávmagasság beállítását, mielőtt elmentenénk az első képet.

```csharp
// Step 3: Configure X‑dimension (module width) and initial bar height
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;    // 2‑pixel modules
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;   // 30‑pixel height
```

Az X‑dimenzió szabályozza minden sáv teljes szélességét; egy 2‑pixel beállítás olvasható, éles képet eredményez a legtöbb képernyőn. A későbbi **change barcode height** lépés újra felhasználja ugyanazt a generátort, időt és memóriát takarítva meg.

## 4. lépés: Az első vonalkód kép mentése (30‑pixel magasság)

```csharp
// Step 4: Save the 30‑pixel barcode image
barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
```

A `DatabarHeight30.png` fájl most egy 30‑pixel sávmagasságú DataBar vonalkódot tartalmaz.

## 5. lépés: Csak a sávmagasság módosítása 60 pixelre

A **change barcode height** bemutatásához csak a `BarHeight` tulajdonságot módosítjuk. Minden egyéb beállítás változatlan marad, ami a leghatékonyabb módja több méret előállításának egyetlen generátorból.

```csharp
// Step 5: Update the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

## 6. lépés: A második vonalkód kép mentése (60‑pixel magasság)

```csharp
// Step 6: Save the 60‑pixel barcode image
barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
```

Most már két PNG fájlja van, mindkettő különböző sávmagassággal, de azonos adatokkal és X‑dimenzióval.

## Teljes, futtatható példa

Az alábbiakban a teljes program található, amelyet beilleszthet egy új konzolos alkalmazásba (`dotnet new console`), és azonnal futtathat.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator for a DataBar Omni‑directional barcode
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");

        // Set X‑dimension and initial bar height (30 pixels)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image (30‑pixel height)
        barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight30.png");

        // Change only the bar height to 60 pixels
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image (60‑pixel height)
        barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight60.png");
    }
}
```

### Várható kimenet

A program futtatása két fájlt hoz létre a végrehajtható munkakönyvtárában:

* `DatabarHeight30.png` – egy DataBar vonalkód 30‑pixel magas sávokkal.  
* `DatabarHeight60.png` – ugyanaz a vonalkód, de minden sáv kétszer olyan magas.

Mindkét kép megnyitható bármely képnézőben, vagy közvetlenül beágyazható PDF-ekbe, HTML oldalakba vagy nyomtatott címkékbe.

## Miért fontos a sávmagasság beállítása

* **Scanning reliability:** Egyes szkennerek nehezen olvassák a nagyon rövid sávokat alacsony felbontású anyagokon; a magasság növelése javítja a felismerést.  
* **Design constraints:** Egy mobilalkalmazásnak egy kompakt vonalkódra (30 px) lehet szüksége, míg egy nyomtatott nyugta nagyobbat (60 px) igényelhet.  
* **Regulatory compliance:** Bizonyos iparágak előírják a minimum sávmagasságot a GS1 DataBar szimbólumokhoz.  

Az ugyanazon `BarcodeGenerator` példány újrafelhasználásával elkerülhető a adatstring újra‑feldolgozásának terhe, ami különösen előnyös nagy áteresztőképességű környezetekben.

## Gyakori variációk és szélsőséges esetek

| Helyzet | Ajánlott módosítás |
|-----------|-------------------|
| Különböző X‑dimenzióra van szükség | Módosítsa a `XDimension.Pixels` értékét az első `Save` előtt. |
| Másik szimbólumra van szükség (pl. DataBar Stacked) | Használja a `EncodeTypes.DatabarStacked` értéket a `BarcodeGenerator` létrehozásakor. |
| A vonalkód PDF-be való beágyazása szükséges | Használja a `barcodeGenerator.Save(stream, BarCodeImageFormat.Png)` metódust, és adja hozzá a stream-et egy PDF könyvtárhoz. |
| .NET Framework 4.6-on futtatás | Ugyanez a kód működik; csak hivatkozzon a megfelelő Aspose.BarCode összeszerelésre. |

## Pro tippek a megbízható vonalkód generáláshoz

* **Cache the generator** amikor sok vonalkódot generál ugyanazzal az adattal, de különböző méretekben.  
* **

## Mit érdemes következőként megtanulni?

Az alábbi oktatóanyagok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsen elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeiben.

- [Hogyan generáljunk és állítsunk be vonalkód magasságot egy dimenziós Databar számára az Aspose.BarCode for .NET használatával](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Hogyan hozzunk létre databar PNG képeket C#-ban és az Aspose.BarCode használatával](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [Hogyan generáljunk egyedi méretű vonalkódot és mentsük el a képet C#-ban](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}