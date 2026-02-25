---
date: 2026-02-25
description: Tanulja meg, hogyan lehet testre szabni a **databar stacked omnidirectional**
  képarányt, miközben **telepíti az Aspose.BarCode for .NET**. A pontos vonalkód tervezés
  egyszerű.
linktitle: One-Dimensional Databar Aspect Ratio Customization
second_title: Aspose.BarCode .NET API
title: A databar rétegezett omnidirekcionális képarány testreszabása .NET‑ben
url: /hu/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# A databar stacked omnidirectional képarány testreszabása .NET-ben

A vonalkódok világában a pontosság és a testreszabás kulcsfontosságú a kívánt eredmények eléréséhez. Ebben az útmutatóban megtanulja, hogyan **testreszabja a databar stacked omnidirectional képarányt** az Aspose.BarCode for .NET segítségével. Lépésről‑lépésre bontjuk le a folyamatot, elmagyarázzuk, miért fontos minden beállítás, és pontosan megmutatjuk, hogyan generálja a végső képeket. Kezdjünk is!

## Gyors válaszok
- **Mit tudok testreszabni?** A databar stacked omnidirectional vonalkód képarányát.  
- **Melyik könyvtár szükséges?** Aspose.BarCode for .NET (telepítse az Aspose.BarCode for .NET‑et).  
- **Hány pixelt állíthatok be az X‑Dimension‑hez?** Bármely egész szám; a példában 2 pixel van használva.  
- **Hol kerülnek mentésre a generált képek?** Egy, a `path` változóval megadott mappába.  
- **Szükség van licencre?** Ideiglenes licenc teszteléshez elegendő; a teljes licenc a termeléshez kötelező.

## Mi az a databar stacked omnidirectional?
`databar stacked omnidirectional` egy egy‑dimenziós vonalkódtípus, amelyet a GS1 szabvány definiál. Numerikus adatokat kódol kompakt, nagy sűrűségű formátumban, amely bármely irányból olvasható, így ideális kis tárgyakhoz és mobil szkenneléshez.

## Miért érdemes testreszabni a képarányt?
A **képarány** módosítása lehetővé teszi a szélesség és magasság közötti vizuális egyensúly szabályozását. Ez akkor hasznos, amikor a vonalkódnak egy adott címkemérethez kell illeszkednie, a márka irányelveivel kell egyeznie, vagy nyomtatási korlátok mellett kell javítani a beolvasási megbízhatóságot.

## Előfeltételek

Mielőtt elkezdenénk, győződjön meg róla, hogy a következőkkel rendelkezik:

### 1. Telepítse az Aspose.BarCode for .NET‑et  
A legújabb verzió letölthető a hivatalos oldalról **[itt](https://releases.aspose.com/barcode/net/)**. Kövesse a telepítési útmutatót a NuGet‑csomag projektbe való hozzáadásához.

### 2. Hozzon létre egy .NET projektet  
Egy egyszerű konzol‑ vagy Windows‑alkalmazás elegendő. Bizonyosodjon meg róla, hogy .NET 6+ (vagy .NET Framework 4.5+) célkeretrendszert használ, hogy a könyvtár extra konfiguráció nélkül működjön.

### 3. A könyvtár útvonala  
Döntse el, hová szeretné menteni a generált PNG fájlokat, és jegyezze fel a teljes vagy relatív útvonalat.

## Névterek importálása

Mielőtt elkezdené a képarány testreszabását, importálja a szükséges névteret, hogy hozzáférhessen az Aspose.BarCode osztályokhoz.

### 1. lépés: Aspose.BarCode névtér importálása

```csharp
using Aspose.BarCode;
```

Most már készen áll a vonalkód‑generátor létrehozására.

## databar stacked omnidirectional képarány beállítások

### 2. lépés: `BarcodeGenerator` inicializálása

Létrehozunk egy generátort a **databar stacked omnidirectional** típushoz, és egy minta GS1 adatstringet adunk neki.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarAspectRatio:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

*Tippek:* Cserélje le a `"Your Directory Path"`‑t egy valós mappára, például `@"C:\Barcodes\"`.

### 3. lépés: X‑Dimension pixelek beállítása

Az X‑Dimension a keskeny vonal szélességét határozza meg. Ebben a példában 2 pixel van használva, de a nyomtató DPI‑jához igazíthatja.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

### 4. lépés: DataBar képarány testreszabása

Itt jön a tutorial középpontja – a képarány módosítása.

#### 4.1 Képarány beállítása 15‑re

```csharp
gen.Parameters.Barcode.DataBar.AspectRatio = 15;
gen.Save($"{path}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

A vonalkód **DatabarAspectRatio15.png** néven kerül mentésre, viszonylag magas megjelenéssel.

#### 4.2 Képarány beállítása 30‑ra

```csharp
gen.Parameters.Barcode.DataBar.AspectRatio = 30;
gen.Save($"{path}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

A **30**‑as arány növelése szélesebb és alacsonyabb vonalkódot eredményez, ami széles címkék esetén lehet hasznos.

### 5. lépés: Az eredmény ellenőrzése

Nyissa meg a generált PNG fájlokat bármely képnéző programmal. Két változatot kell látnia ugyanabból a vonalkódból, mindegyik más‑más szélesség‑magasság aránnyal. Olvassa be őket egy szabványos vonalkód‑olvasóval, hogy megbizonyosodjon a továbbra is olvashatóságról.

## Gyakori problémák és megoldások

| Probléma | Ok | Megoldás |
|----------|----|----------|
| A vonalkód elmosódott | X‑Dimension túl alacsony a nyomtató DPI‑jához | Növelje az `XDimension.Pixels` értékét (pl. 3 vagy 4). |
| Az olvasó nem tudja beolvasni | Extrém képarány (pl. > 50) | Tartsa a képarányt 10‑40 között a megbízható beolvasáshoz. |
| A fájl nem mentődik | Érvénytelen `path` karakterlánc | Használja a `Path.Combine`‑t, és ellenőrizze, hogy a mappa létezik (`Directory.CreateDirectory`). |

## Gyakran feltett kérdések

**K: Mi a vonalkód képaránya, és miért fontos?**  
V: A képarány a szélesség‑magasság arányát jelenti. Befolyásolja, hogy a vonalkód hogyan illeszkedik egy címkére, és hatással lehet a beolvasási megbízhatóságra.

**K: Más vonalkódtípusok képarányát is módosíthatom az Aspose.BarCode for .NET‑el?**  
V: Igen, sok egy‑ és két‑dimenziós vonalkód rendelkezik `AspectRatio` tulajdonsággal a finomhangoláshoz.

**K: Vannak korlátozások a képarány módosítására?**  
V: Extrém értékek megsérthetik a kódolási szabványokat, és olvashatatlanná tehetik a vonalkódot. Tesztelje a célolvasókkal.

**K: Hol találok további tutorialokat és példákat az Aspose.BarCode for .NET‑hez?**  
V: Tekintse meg a részletes útmutatót a hivatalos **[dokumentációban](https://reference.aspose.com/barcode/net/)**.

**K: Hogyan szerezhetek ideiglenes licencet az Aspose.BarCode for .NET‑hez?**  
V: Kérjen próbaverzió licencet **[itt](https://purchase.aspose.com/temporary-license/)**.

## Összegzés

Most már megtanulta, hogyan **testreszabja a databar stacked omnidirectional képarányt** az Aspose.BarCode for .NET‑el. Az `XDimension` és a `DataBar.AspectRatio` beállításával olyan vonalkódokat hozhat létre, amelyek tökéletesen illeszkednek a címkeméreteihez, javítják a vizuális egységességet, és megőrzik a beolvasási megbízhatóságot. Kísérletezzen különböző arányokkal, integrálja a kódot a készlet‑ vagy csomagolási folyamataiba, és élvezze az Aspose nyújtotta rugalmasságot.

Mélyebb ismeretekért tekintse meg a teljes **[dokumentációt](https://reference.aspose.com/barcode/net/)**, vagy csatlakozzon a közösséghez a **[Aspose.BarCode fórumon](https://forum.aspose.com/c/barcode/13)**.

---

**Utoljára frissítve:** 2026-02-25  
**Tesztelve:** Aspose.BarCode 24.12 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}