---
date: 2026-03-07
description: Tanulja meg, hogyan készítsen EAN‑13 vonalkódot kiegészítő adatokkal
  C#‑ban az Aspose.BarCode for .NET segítségével – gyorsan generáljon PNG vonalkódot.
linktitle: Supplemental Barcode Data Configuration
second_title: Aspose.BarCode .NET API
title: EAN-13 vonalkód létrehozása kiegészítő adatokkal – Aspose.BarCode
url: /hu/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# EAN-13 vonalkód létrehozása kiegészítő adatokkal – Aspose.BarCode for .NET

Ebben a gyakorlati útmutatóban **EAN-13 vonalkódot** hozol létre, amely kiegészítő EAN‑2 vagy EAN‑5 adatokat tartalmaz, és megmutatjuk, hogyan **hozz létre vonalkód PNG** fájlokat néhány C# sorral. Akár kiskereskedelmi pénztárrendszert, logisztikai alkalmazást, vagy egyszerű készletkezelő eszközt építesz, a kiegészítő információk hozzáadása sokkal hasznosabbá teszi a vonalkódjaidat.

## Gyors válaszok
- **Mit jelent a „kiegészítő adat”?** Extra számjegyek (EAN‑2/EAN‑5) a fő vonalkód mellett nyomtatva, gyakran ár vagy kiadási számokhoz használva.  
- **Melyik vonalkódtípust használják?** Az EAN‑13 az elsődleges szimbólum, opcionális EAN‑2 vagy EAN‑5 kiegészítőkkel.  
- **Exportálhatok PNG képeket?** Igen – a `Save` metódus lehetővé teszi a közvetlen PNG exportálást.  
- **Szükségem van licencre a fejlesztéshez?** Egy ingyenes próba verzió teszteléshez elegendő; a termeléshez kereskedelmi licenc szükséges.  
- **Kompatibilis a .NET Core / .NET 6-tal?** Teljesen – az Aspose.BarCode támogatja az összes modern .NET futtatókörnyezetet.

## Előfeltételek

Mielőtt belemerülnénk a kódba, győződj meg róla, hogy rendelkezel:

- Visual Studio (vagy bármely .NET‑kompatibilis IDE).  
- Az Aspose.BarCode for .NET egy példánnyal – töltsd le **[itt](https://releases.aspose.com/barcode/net/)**.  
- Alap C# ismeretekkel.  
- Írási jogosultsággal rendelkező mappával, ahová a generált PNG fájlok mentésre kerülnek.

## Névterek importálása

Először add hozzá az Aspose.BarCode névteret, hogy elérhesd a generátor osztályokat:

```csharp
using Aspose.BarCode.Generation;
```

> **Pro tipp:** Ha .NET Core-t használsz, add hozzá a `Aspose.BarCode` NuGet csomagot a projekthez a DLL kézi hivatkozása helyett.

## Mi az a kiegészítő vonalkód?

Egy kiegészítő vonalkód egy segéd numerikus karakterlánc, amely a fő vonalkód mellett nyomtatott.  
- **EAN‑2** – kétjegyű kiegészítő, gyakran használják magazinok kiadási számaira.  
- **EAN‑5** – ötjegyű kiegészítő, általában árkiegészítésekhez a kiskereskedelmi termékeken.

Ezeknek a kiegészítőknek a hozzáadása nem módosítja az elsődleges EAN‑13 adatot; egyszerűen extra kontextust biztosít, amelyet a szkennerek olvasni tudnak.

## Miért használjuk az Aspose.BarCode-ot kiegészítő adatokhoz?

- **Egy‑soros API** – konfigurálhatod a fő vonalkódot és a kiegészítőt egyetlen objektumban.  
- **Teljes kontroll a méretek felett** – állíthatod az X‑dimenziót, a kiegészítő távolságát és a képformátumot.  
- **Kereszt‑platform** – működik .NET Framework, .NET Core és .NET 5/6+ környezetekben.  

## Lépésről‑lépésre útmutató

### 1. lépés: Kimeneti könyvtár beállítása

Határozd meg, hogy hol legyenek tárolva a PNG fájlok. Cseréld ki a helyőrzőt a gépeden lévő valós útvonalra.

```csharp
string path = "Your Directory Path";
```

### 2. lépés: A Barcode Generator inicializálása (Barcode Generator C#)

Hozz létre egy `BarcodeGenerator` példányt, megadva **EAN‑13**-at fő típusként, és a 13‑jegyű adatot biztosítva.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

### 3. lépés: A vonalkód méreteinek beállítása

Finomhangold a vonalkód vizuális méretét és a kiegészítőnek fenntartott helyet.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

### 4. lépés: EAN‑2 kiegészítő hozzáadása

Állítsd be a kiegészítő adatot egy kétjegyű értékre (pl. „12”). Ez a fő vonalkód jobb oldalán jelenik meg.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

### 5. lépés: Az EAN‑2 vonalkód mentése PNG‑ként

Exportáld a képet. A `BarCodeImageFormat.Png` argument biztosítja a magas minőségű PNG fájlt.

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

### 6. lépés: Váltás EAN‑5 kiegészítőre

Módosítsd a `SupplementData` értékét egy ötjegyű karakterláncra az árkiegészítésekhez.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

### 7. lépés: Az EAN‑5 vonalkód mentése PNG‑ként

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

> **Miért működik ez:** Ugyanazt a `BarcodeGenerator` példányt használod újra, így csak a `SupplementData` tulajdonságot kell módosítanod minden `Save` hívás előtt. Ez a kódot tömörnek tartja és elkerüli a felesleges objektum létrehozást.

## Gyakori problémák és tippek

- **Érvénytelen könyvtárútvonal** – győződj meg róla, hogy a mappa létezik és az alkalmazásnak írási jogosultsága van.  
- **Helytelen kiegészítő hossza** – az EAN‑2 pontosan 2 számjegyet, az EAN‑5 pontosan 5 számjegyet vár; egyébként kivétel keletkezik.  
- **A kép nem látható** – ellenőrizd, hogy `BarCodeImageFormat.Png` van használva; más formátumok (pl. JPEG) tömörítési hibákat okozhatnak, amelyek befolyásolják a szkenner olvashatóságát.  

## Gyakran ismételt kérdések

### Használhatom az Aspose.BarCode for .NET-et a .NET Core projektemben?
Igen, az Aspose.BarCode for .NET teljes mértékben kompatibilis a .NET Core, .NET 5 és .NET 6 verziókkal.

### Van ingyenes próba verzió az Aspose.BarCode for .NET-hez?
Igen, ingyen kipróbálhatod a **[linkre kattintva](https://releases.aspose.com/)**.

### Hol szerezhetek ideiglenes licencet az Aspose.BarCode for .NET-hez?
Ideiglenes licencet a **[linkről](https://purchase.aspose.com/temporary-license/)** szerezhetsz.

### Támogatja az Aspose.BarCode a széles körű vonalkódtípusokat?
Teljesen – támogatja az EAN‑13, QR Code, Code 128, DataMatrix, PDF‑417 és még sok más típusát.

### Testreszabhatom a generált vonalkódok megjelenését?
Igen, módosíthatod a színeket, betűtípusokat, margókat, és még háttérképeket is hozzáadhatsz a kiterjedt `Parameters` API segítségével.

## Összegzés

Most már tudod, hogyan **hozz létre EAN-13 vonalkódot** kiegészítő EAN‑2 vagy EAN‑5 adatokkal, és hogyan **generálj vonalkód PNG** fájlokat az Aspose.BarCode for .NET használatával. Ez a megközelítés teljes kontrollt biztosít a vonalkód méretei, a kiegészítő távolsága és a kimeneti formátum felett, így ideális a kiskereskedelem, logisztika és bármely olyan eset számára, ahol extra numerikus információra van szükség.

A mélyebb elmélyüléshez tekintsd meg a teljes referencia útmutatót: **[Aspose.BarCode for .NET dokumentáció](https://reference.aspose.com/barcode/net/)**.

---

**Utoljára frissítve:** 2026-03-07  
**Tesztelve a következővel:** Aspose.BarCode 24.11 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}