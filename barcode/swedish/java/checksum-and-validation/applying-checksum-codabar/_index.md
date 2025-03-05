---
title: Tillämpa kontrollsumma för CodaBar i Java
linktitle: Tillämpar kontrollsumma för CodaBar
second_title: Aspose.BarCode Java API
description: Lär dig hur du tillämpar kontrollsumma för CodaBar i Java med Aspose.BarCode. Generera och känna igen streckkoder utan ansträngning med denna steg-för-steg-guide.
type: docs
weight: 11
url: /sv/java/checksum-and-validation/applying-checksum-codabar/
---

## Introduktion

Välkommen till denna steg-för-steg handledning om att tillämpa kontrollsumma för CodaBar i Java med Aspose.BarCode. Aspose.BarCode för Java är ett kraftfullt bibliotek som tillåter utvecklare att generera och känna igen streckkoder i Java-applikationer sömlöst. I den här handledningen kommer vi att fokusera på den specifika uppgiften att tillämpa kontrollsumma för CodaBar-streckkoder.

## Förutsättningar

Innan vi dyker in i handledningen, se till att du har följande förutsättningar:

- Java Development Kit (JDK) installerat på din maskin.
-  Aspose.BarCode för Java-bibliotek. Du kan ladda ner den från[här](https://releases.aspose.com/barcode/java/).
- En grundläggande förståelse för Java-programmering.

## Importera paket

I ditt Java-projekt, se till att importera de nödvändiga paketen för att arbeta med Aspose.BarCode:

```java
import java.io.IOException;

import com.aspose.barcode.CodabarChecksumMode;
import com.aspose.barcode.EnableChecksum;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.ChecksumValidation;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Steg 1: Ställ in miljön

Börja med att skapa ett nytt Java-projekt och inkludera Aspose.BarCode-biblioteket i ditt projekts beroenden. Ställ in din utvecklingsmiljö med de resurser som krävs.

```java
// Sökvägen till resurskatalogen.
String dataDir = "Your Document Directory";
```

## Steg 2: Generering av CodaBar-streckkod

Låt oss nu generera en CodaBar-streckkod med kontrollsumma aktiverad.

```java
// Instantiera BarcodeGenerator-objekt
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "1234567890");

// Ställ in egenskapen EnableChecksum till Ja
generator.getParameters().getBarcode().setChecksumEnabled(EnableChecksum.YES);

// Ställ in CodabarChecksumMode
generator.getParameters().getBarcode().getCodabar().setCodabarChecksumMode(CodabarChecksumMode.MOD_10);

// Spara bilden på systemet
generator.save(dataDir + "Codabar_Mod10.png");
```

## Steg 3: Igenkänning av CodaBar streckkod

Låt oss nu implementera igenkänningsdelen av CodaBar-streckkoden med kontrollsumma.

```java
// Initiera läsarobjekt
BarCodeReader reader = new BarCodeReader(dataDir + "Codabar_Mod10.png", DecodeType.CODABAR);

// Ställ in ChecksumValidation-egenskapen för läsaren till På
reader.setChecksumValidation(ChecksumValidation.ON);

for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("CodeText: " + result.getCodeText());
    System.out.println("Symbology type: " + result.getCodeType());

    // Få kontrollsummavärde
    System.out.println("Checksum:" + result.getExtended().getOneD().getCheckSum());
}
```

Följ dessa steg för att använda kontrollsumma för CodaBar i Java utan ansträngning med Aspose.BarCode.

## Slutsats

I den här handledningen undersökte vi hur man tillämpar kontrollsumma för CodaBar-streckkoder i Java med Aspose.BarCode. Det här biblioteket ger ett enkelt sätt att generera och känna igen streckkoder med olika anpassningsalternativ.

---

## Vanliga frågor

### Är Aspose.BarCode kompatibel med alla Java-versioner?
Aspose.BarCode är designad för att fungera med olika Java-versioner. Se till att du kontrollerar dokumentationen för kompatibilitetsdetaljer.

### Kan jag anpassa utseendet på den genererade streckkoden?
Ja, Aspose.BarCode erbjuder omfattande anpassningsalternativ, så att du kan kontrollera utseendet på de genererade streckkoderna.

### Finns tillfälliga licenser tillgängliga för teständamål?
 Ja, du kan få en tillfällig licens för Aspose.BarCode från[här](https://purchase.aspose.com/temporary-license/).

### Var kan jag hitta ytterligare support och resurser?
 Besök[Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) för samhällsstöd och diskussioner.

### Finns det en gratis provperiod?
 Ja, du kan utforska funktionerna i Aspose.BarCode genom att ladda ner den kostnadsfria testversionen från[här](https://releases.aspose.com/).