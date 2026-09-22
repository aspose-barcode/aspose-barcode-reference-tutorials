---
date: 2026-05-04
description: Tanulja meg, hogyan generáljon Java‑ban vonalkód képet, és mentse el
  az Aspose.BarCode for Java segítségével. Lépésről‑lépésre útmutató MySQL tárolással,
  testreszabási tippekkel és teljes kóddal.
keywords:
- java generate barcode image
- how to generate barcode java
- how to save barcode image
linktitle: Vonalkód generálása és mentése
second_title: Aspose.BarCode Java API
title: 'Java: vonalkód kép generálása és adatbázisba mentése'
url: /hu/java/symbology-and-format/generating-saving-barcode/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# java vonalkód kép generálása

## Bevezetés

Ha gyorsan **java generate barcode image** kell, és a termékadatok mellé szeretné tárolni, ez a tutorial Önnek szól. Lépésről lépésre bemutatjuk, hogyan használja az Aspose.BarCode for Java-t CODE‑39 vonalkód létrehozásához, a kép lemezre mentéséhez, majd MySQL adatbázisba BLOB-ként való beszúrásához. A végére egy újrahasználható mintát kap, amelyet bármely vonalkód típusra vagy tárolási követelményre adaptálhat.

## Gyors válaszok
- **Melyik könyvtár hoz létre vonalkódokat Java-ban?** Aspose.BarCode for Java.  
- **Menthetem a vonalkódot fájlként?** Igen – használja a `generator.save("path")`.  
- **Hogyan tároljam a képet MySQL-ben?** Olvassa be a fájlt egy `FileInputStream`-be, és állítsa be bináris áramként egy `PreparedStatement`-ben.  
- **Milyen vonalkód típusok támogatottak?** CODE_39, CODE_128, QR, DataMatrix, és még sok más.  
- **Szükség van licencre a termeléshez?** Kereskedelmi licenc szükséges; ingyenes próba elérhető.

## Mi az java vonalkód kép generálása?
A vonalkód kép generálása Java-ban azt jelenti, hogy egyszerű szöveget (pl. egy termékszámot) vizuális ábrává alakít, amelyet a szkennerek olvasni tudnak. Az Aspose.BarCode elrejti az alacsony szintű kódolási részleteket, így az alkalmazáslogikára koncentrálhat.

## Miért használja az Aspose.BarCode-ot ehhez a feladathoz?
- **Teljes körű**: Több mint 50 szimbólumot támogat.  
- **Egyszerű API**: Egy soros kód a kép létrehozásához és mentéséhez.  
- **Magas minőség**: PNG, JPEG, BMP és PDF kimeneteket generál.  
- **Vállalati szintű**: Minden fő Java verzión működik, és könnyen integrálható adatbázisokkal.

## Előfeltételek

- **Java fejlesztői környezet** – JDK 8+ telepítve és a választott IDE.  
- **Aspose.BarCode könyvtár** – Töltse le és telepítse az Aspose.BarCode könyvtárat. A letöltési linket megtalálja [itt](https://releases.aspose.com/barcode/java/).  
- **MySQL adatbázis** – Egy futó MySQL példány, ahol a termékinformációkat tárolja.  
- **Adatbázis kapcsolat** – JDBC driver és érvényes hitelesítő adatok (`HOST_URI`, `USERNAME`, `PASSWORD`).

## Csomagok importálása

A Java projektjében importálja a szükséges csomagokat az Aspose.BarCode és a MySQL kapcsolathoz.

```java
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generation.BarcodeGenerator;

import java.io.File;
import java.io.FileInputStream;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
```

## Hogyan generáljon vonalkódot java-ban

### 1. lépés: Vonalkód generálása és mentése

```java
// Step 1 - Generate barcode and save temporarily in a file
String strBarCodeImage = "c:\\temp\\code39.jpg";
String strCodeText = "NOK-E71";

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText(strCodeText);
generator.save(strBarCodeImage);
```

*Magyarázat*: Létrehozzuk a `BarcodeGenerator`-t a CODE‑39 szabványhoz, beállítjuk a termékkódot (`NOK-E71`), és elmentjük a képet a `c:\temp\code39.jpg` helyre. Ez a fájl később adatbázisba lesz streamelve.

## Hogyan mentse a vonalkód képet

### 2. lépés: Rekord beszúrása MySQL adatbázisba

```java
// Step 2 - Insert a new record in MySQL DB
Connection con = null;

// Open connection
Class.forName("com.mysql.jdbc.Driver").newInstance();
con = DriverManager.getConnection(Common.HOST_URI, Common.USERNAME, Common.PASSWORD);

// Prepare statement
PreparedStatement pre = con.prepareCall(
        "Insert INTO Product (ProductNumber, ProductName, BarCodeImage) " + "VALUES (?, ?, ?) ");

// Set product number and product name
pre.setString(1, "NOK-E71");
pre.setString(2, "Nokia E Series - E71");

// 3rd column is for barcode image. DB type is BLOB
// For saving the image, we need to create a stream from the image file
File imgFile = new File(strBarCodeImage);
FileInputStream fin = new FileInputStream(imgFile);
pre.setBinaryStream(3, fin, (int) imgFile.length());

// Execute the statement
pre.executeUpdate();
System.out.println("Insertion successful.");

// Close connection
pre.close();
con.close();
```

*Magyarázat*: JDBC kapcsolat létrehozása után előkészítünk egy `INSERT` utasítást, amely tartalmaz egy BLOB oszlopot a vonalkód képhez. A képfájlt egy `FileInputStream`-be olvassuk, és bináris adatként tároljuk.

## Gyakori problémák és megoldások

| Probléma | Ok | Megoldás |
|----------|----|----------|
| **FileNotFoundException** a vonalkód mentésekor | A célmappa nem létezik vagy nincs írási jogosultsága | Hozza létre a mappát (`c:\temp`), vagy válasszon írható útvonalat |
| **SQLIntegrityConstraintViolationException** beszúráskor | Duplikált `ProductNumber` elsődleges kulcs | Győződjön meg arról, hogy a termékszám egyedi, vagy használja az `ON DUPLICATE KEY UPDATE`-t |
| **ClassNotFoundException: com.mysql.jdbc.Driver** | A MySQL JDBC driver hiányzik az osztályúton | Adja hozzá a MySQL Connector/J JAR-t a projekt függőségeihez |

## Gyakran ismételt kérdések

**Q: Az Aspose.BarCode kompatibilis különböző vonalkód típusokkal?**  
A: Igen, Aspose.BarCode támogatja a különböző vonalkód típusokat, beleértve a CODE_39_STANDARD, CODE_128, QR, és egyebeket.

**Q: Testreszabhatom a generált vonalkódok megjelenését?**  
A: Természetesen! Az Aspose.BarCode kiterjedt testreszabási lehetőségeket biztosít a vonalkód megjelenéséhez, lehetővé téve, hogy az igényeihez igazítsa.

**Q: Van ingyenes próba az Aspose.BarCode-hoz?**  
A: Igen, ingyenes próbát érhet el [itt](https://releases.aspose.com/).

**Q: Hol találhatók részletes dokumentációk az Aspose.BarCode-hoz?**  
A: A dokumentációt megtalálja [itt](https://reference.aspose.com/barcode/java/).

**Q: Hogyan kaphatok támogatást az Aspose.BarCode-hoz?**  
A: Látogassa meg a támogatási fórumot [itt](https://forum.aspose.com/c/barcode/13) bármilyen segítség vagy kérdés esetén.

## Összegzés

Gratulálunk! Sikeresen megtanulta, hogyan **generáljon vonalkódot java-ban** és **mentse a vonalkód képet** az Aspose.BarCode használatával, majd a képet MySQL adatbázisban tárolta. Ez a megközelítés kiterjeszthető más szimbólumokra, tárolási megoldásokra (pl. Azure Blob, AWS S3), vagy integrálható nagyobb vállalati rendszerekbe.

---

**Last Updated:** 2026-05-04  
**Tested With:** Aspose.BarCode for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}