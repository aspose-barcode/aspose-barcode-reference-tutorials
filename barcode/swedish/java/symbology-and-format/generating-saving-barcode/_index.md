---
date: 2026-05-04
description: Lär dig hur du i Java genererar streckkodsbilder och sparar dem med Aspose.BarCode
  för Java. Steg‑för‑steg‑guide med MySQL‑lagring, anpassningstips och fullständig
  kod.
keywords:
- java generate barcode image
- how to generate barcode java
- how to save barcode image
linktitle: Generera och spara streckkod
second_title: Aspose.BarCode Java API
title: Java generera streckkodbild och spara i databasen
url: /sv/java/symbology-and-format/generating-saving-barcode/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# java generera streckkod bild

## Introduktion

Om du snabbt behöver **java generate barcode image** och lagra den tillsammans med produktdata, är den här handledningen för dig. Vi går igenom hur du använder Aspose.BarCode för Java för att skapa en CODE‑39 streckkod, spara bilden på disk och sedan infoga den i en MySQL-databas som en BLOB. När du är klar har du ett återanvändbart mönster som du kan anpassa till vilken streckkodstyp eller lagringskrav som helst.

## Snabba svar
- **Vilket bibliotek skapar streckkoder i Java?** Aspose.BarCode for Java.  
- **Kan jag spara streckkoden som en fil?** Ja – använd `generator.save("path")`.  
- **Hur lagrar jag bilden i MySQL?** Läs filen i en `FileInputStream` och sätt den som en binär ström i ett `PreparedStatement`.  
- **Vilka streckkodstyper stöds?** CODE_39, CODE_128, QR, DataMatrix och många fler.  
- **Behöver jag en licens för produktion?** En kommersiell licens krävs; en gratis provperiod finns tillgänglig.

## Vad är java generate barcode image?
Att generera en streckkodsbild i Java innebär att konvertera vanlig text (t.ex. ett produktnummer) till en visuell representation som skannrar kan läsa. Aspose.BarCode abstraherar de lågnivåkodningsdetaljerna, så att du kan fokusera på din applikationslogik.

## Varför använda Aspose.BarCode för denna uppgift?
- **Fullt utrustad**: Stöder över 50 symboler.  
- **Enkelt API**: Enradskod för att skapa och spara en bild.  
- **Hög kvalitet**: Genererar PNG, JPEG, BMP och PDF-utdata.  
- **Företagsklar**: Fungerar på alla större Java-versioner och integreras enkelt med databaser.

## Förutsättningar

- **Java-utvecklingsmiljö** – JDK 8+ installerad och den IDE du föredrar.  
- **Aspose.BarCode-bibliotek** – Ladda ner och installera Aspose.BarCode-biblioteket. Du kan hitta nedladdningslänken [här](https://releases.aspose.com/barcode/java/).  
- **MySQL-databas** – En körande MySQL-instans där du kommer att lagra produktinformation.  
- **Databasanslutning** – JDBC-drivrutin och giltiga referenser (`HOST_URI`, `USERNAME`, `PASSWORD`).

## Importera paket

I ditt Java‑projekt, importera de nödvändiga paketen för Aspose.BarCode och MySQL‑anslutning.

```java
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generation.BarcodeGenerator;

import java.io.File;
import java.io.FileInputStream;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
```

## Så genererar du streckkod i java

### Steg 1: Generera och spara streckkod

```java
// Step 1 - Generate barcode and save temporarily in a file
String strBarCodeImage = "c:\\temp\\code39.jpg";
String strCodeText = "NOK-E71";

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText(strCodeText);
generator.save(strBarCodeImage);
```

*Förklaring*: Vi skapar en `BarcodeGenerator` för CODE‑39‑standarden, tilldelar produktkoden (`NOK‑E71`) och sparar bilden till `c:\temp\code39.jpg`. Denna fil kommer senare att strömmas in i databasen.

## Så sparar du streckkodsbild

### Steg 2: Infoga post i MySQL-databas

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

*Förklaring*: Efter att ha etablerat en JDBC‑anslutning förbereder vi ett `INSERT`‑statement som inkluderar en BLOB‑kolumn för streckkodsbilden. Bildfilen läses in i en `FileInputStream` och lagras som binär data.

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|-------|-------|-----|
| **FileNotFoundException** när streckkoden sparas | Destinationsmappen finns inte eller saknar skrivbehörighet | Skapa mappen (`c:\temp`) eller välj en skrivbar sökväg |
| **SQLIntegrityConstraintViolationException** vid insättning | Dubblett `ProductNumber` primärnyckel | Säkerställ att produktnumret är unikt eller använd `ON DUPLICATE KEY UPDATE` |
| **ClassNotFoundException: com.mysql.jdbc.Driver** | MySQL JDBC‑drivrutin saknas i klassvägen | Lägg till MySQL Connector/J‑JAR‑filen i projektets beroenden |

## Vanliga frågor

**Q: Är Aspose.BarCode kompatibel med olika streckkodstyper?**  
A: Ja, Aspose.BarCode stöder olika streckkodstyper, inklusive CODE_39_STANDARD, CODE_128, QR och fler.

**Q: Kan jag anpassa utseendet på genererade streckkoder?**  
A: Absolut! Aspose.BarCode erbjuder omfattande anpassningsalternativ för streckkodens utseende, så att du kan skräddarsy den efter dina specifika behov.

**Q: Finns det en gratis provperiod för Aspose.BarCode?**  
A: Ja, du kan få åtkomst till en gratis provperiod [här](https://releases.aspose.com/).

**Q: Var kan jag hitta detaljerad dokumentation för Aspose.BarCode?**  
A: Se dokumentationen [här](https://reference.aspose.com/barcode/java/).

**Q: Hur får jag support för Aspose.BarCode?**  
A: Besök supportforumet [här](https://forum.aspose.com/c/barcode/13) för hjälp eller frågor.

## Slutsats

Grattis! Du har framgångsrikt lärt dig **how to generate barcode java** och **how to save barcode image** med Aspose.BarCode, och sedan lagrat bilden i en MySQL-databas. Detta tillvägagångssätt kan utökas till andra symboler, lagringsmekanismer (t.ex. Azure Blob, AWS S3) eller integreras i större företagsystem.

---

**Last Updated:** 2026-05-04  
**Tested With:** Aspose.BarCode for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}