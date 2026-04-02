---
date: 2025-12-18
description: Lär dig hur du skapar en Codabar-streckkodsbild och se ett Java‑streckkodsläsareexempel
  med Aspose.BarCode. Generera och känna igen streckkoder enkelt med den här steg‑för‑steg‑guiden.
linktitle: Applying Checksum for CodaBar
second_title: Aspose.BarCode Java API
title: Hur man skapar en codabar‑streckkodsbild med kontrollsumma i Java
url: /sv/java/checksum-and-validation/applying-checksum-codabar/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar en Codabar‑streckkodsbild med kontrollsumma i Java

## Introduktion

I den här handledningen kommer du att lära dig hur du **skapar en Codabar‑streckkodsbild** med kontrollsumma i Java med hjälp av Aspose.BarCode. Vi går igenom hur man genererar en CodaBar‑streckkod, aktiverar kontrollsumman och sedan läser tillbaka den med ett **java barcode reader example**. I slutet har du ett färdigt kodexempel som du kan klistra in i vilket Java‑projekt som helst.

## Snabba svar
- **Vad gör kontrollsumman?** Den validerar integriteten hos streckkodens data under skanning.  
- **Vilket bibliotek krävs?** Aspose.BarCode för Java.  
- **Behöver jag en licens för utveckling?** En tillfällig licens fungerar för testning; en full licens krävs för produktion.  
- **Kan jag anpassa streckkodens utseende?** Ja – färg, storlek och teckensnitt kan ändras via generatorparametrar.  
- **Är detta kompatibelt med alla Java‑versioner?** Biblioteket stödjer Java 8 och nyare.

## Vad är en CodaBar‑streckkod?

CodaBar är en linjär (1‑dimensionell) symbologi som används i stor utsträckning i bibliotek, blodbanker och detaljhandel. Den kodar numerisk data och några specialtecken, vilket gör den idealisk för enkla, maskinläsbara taggar. Att lägga till en kontrollsumma (Mod 10) förbättrar läsningsnoggrannheten, särskilt på utskrifter av låg kvalitet.

## Varför använda Aspose.BarCode för Java?

Aspose.BarCode erbjuder ett **java barcode reader example** som abstraherar de lågnivådetaljer som rör streckkodsgenerering och -igenkänning. Det erbjuder:

* Full kontroll över kontrollsumma‑lägen.  
* Sömlös integration med Java‑IDE:er.  
* Omfattande dokumentation och support.  

## Förutsättningar

Innan vi börjar, se till att du har:

- Java Development Kit (JDK) installerat på din maskin.  
- Aspose.BarCode för Java‑biblioteket. Du kan ladda ner det från [here](https://releases.aspose.com/barcode/java/).  
- Grundläggande förståelse för Java‑programmering.  

## Importera paket

I ditt Java‑projekt, importera de nödvändiga klasserna för att arbeta med Aspose.BarCode:

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

## Steg‑för‑steg‑guide

### Steg 1: Ställ in miljön

Skapa ett nytt Java‑projekt och lägg till Aspose.BarCode‑JAR‑filen i din byggsökväg. Definiera en mapp där de genererade bilderna ska sparas.

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

### Steg 2: Generera en CodaBar‑streckkodsbild med kontrollsumma

Instansiera `BarcodeGenerator`, aktivera kontrollsumman, välj Mod 10‑läge och spara bilden.

```java
// Instantiate BarcodeGenerator object
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "1234567890");

// Set the EnableChecksum property to yes
generator.getParameters().getBarcode().setChecksumEnabled(EnableChecksum.YES);

// Set the CodabarChecksumMode
generator.getParameters().getBarcode().getCodabar().setCodabarChecksumMode(CodabarChecksumMode.MOD_10);

// Save the image on the system
generator.save(dataDir + "Codabar_Mod10.png");
```

### Steg 3: Java barcode reader example – Läs av streckkoden

Läs nu av streckkoden igen, slå på kontrollsummevalidering för att säkerställa att data är korrekt.

```java
// Initialize reader object
BarCodeReader reader = new BarCodeReader(dataDir + "Codabar_Mod10.png", DecodeType.CODABAR);

// Set ChecksumValidation property of the reader to On
reader.setChecksumValidation(ChecksumValidation.ON);

for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("CodeText: " + result.getCodeText());
    System.out.println("Symbology type: " + result.getCodeType());

    // Get checksum value
    System.out.println("Checksum:" + result.getExtended().getOneD().getCheckSum());
}
```

När koden körs kommer den att skriva ut den avkodade texten, symbologitypen och den beräknade kontrollsumman, vilket bekräftar att streckkoden genererades och validerades korrekt.

## Vanliga problem och lösningar

| Problem | Lösning |
|-------|----------|
| **Checksum validation fails** | Verifiera att `EnableChecksum` är satt till `YES` och att `CodabarChecksumMode` matchar läget som användes under genereringen (Mod 10). |
| **File not found error** | Säkerställ att `dataDir` pekar på en befintlig mapp och att den genererade bilden (`Codabar_Mod10.png`) är sparad där innan den läses. |
| **Unsupported Java version** | Använd Java 8 eller senare; äldre versioner kan sakna nödvändiga API:er. |

## Vanliga frågor

**Q: Är Aspose.BarCode kompatibel med alla Java‑versioner?**  
A: Aspose.BarCode är designat för att fungera med Java 8 och nyare. Kontrollera den officiella dokumentationen för detaljerad kompatibilitet.

**Q: Kan jag anpassa utseendet på den genererade streckkoden?**  
A: Ja, du kan ändra färger, teckensnitt och bildformat via generatorns parameter‑API.

**Q: Finns tillfälliga licenser tillgängliga för teständamål?**  
A: Ja, du kan skaffa en tillfällig licens för Aspose.BarCode från [here](https://purchase.aspose.com/temporary-license/).

**Q: Var kan jag hitta ytterligare support och resurser?**  
A: Besök [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) för community‑support och diskussioner.

**Q: Finns en gratis provversion tillgänglig?**  
A: Ja, du kan utforska funktionerna i Aspose.BarCode genom att ladda ner gratisprovet från [here](https://releases.aspose.com/).

---

**Senast uppdaterad:** 2025-12-18  
**Testad med:** Aspose.BarCode for Java 24.12  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}