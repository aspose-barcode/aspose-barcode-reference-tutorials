---
date: 2025-12-21
description: Lär dig hur du läser streckkodsbilder med Aspose.BarCode Java‑biblioteket,
  inklusive pdf417‑streckkodsgenerering i Java och Unicode‑streckkodigenkänning.
linktitle: Recognizing Unicode Barcodes
second_title: Aspose.BarCode Java API
title: Hur man läser streckkodsbilder med Unicode‑streckkoder i Java
url: /sv/java/document-barcode-recognition/recognizing-unicode-barcodes/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Känna igen Unicode-streckkoder i Java

## Introduktion

Om du behöver **how to read barcode image** i en Java‑applikation, särskilt när streckkoden innehåller Unicode‑tecken, har du kommit till rätt ställe. I den här handledningen går vi igenom varje steg som krävs för att känna igen Unicode‑streckkoder—som arabiska, kinesiska eller kyrillisk text—med det kraftfulla Aspose.BarCode‑biblioteket. I slutet kommer du att kunna generera och läsa dessa streckkoder med självförtroende, vilket utökar din mjukvaras räckvidd till en global publik.

## Snabba svar
- **Vilket bibliotek är bäst för streckkodsläsning i Java?** Aspose.BarCode for Java.
- **Kan jag generera PDF417‑streckkoder med Unicode‑text?** Ja, med klassen `BarcodeGenerator`.
- **Behöver jag en licens för produktionsbruk?** En giltig Aspose.BarCode-licens krävs.
- **Vilken Java‑version stöds?** Java8 och senare.
- **Finns det en gratis provperiod?** Ja, du kan ladda ner en provversion från Asposes webbplats.

## Vad är "hur man läser streckkodsbild" i Java?

Att läsa en streckkodsbild innebär att avkoda det visuella mönstret till den ursprungliga datasträngen. När data innehåller Unicode‑tecken måste biblioteket korrekt hantera teckenkodning och avkodning, vilket Aspose.BarCode gör automatiskt så snart du konverterar texten till rätt kodformat.

## Varför använda Aspose.BarCode för pdf417 streckkodsgenerering i Java?

Aspose.BarCode erbjuder ett enkelt API för **pdf417 barcode generation java**, stödjer ett brett spektrum av symboler och hanterar Unicode-kodning direkt i lådan. Detta gör det idealiskt för företagsapplikationer som kräver pålitlig, högpresterande streckkodshantering.

## Förutsättningar

Innan du dyker ner, se till att du har:

- En fungerande kunskap i Java-programmering.
- Aspose.BarCode för Java‑biblioteket installerat. Du kan ladda ner det [här](https://releases.aspose.com/barcode/java/).
- En giltig licens för Aspose.BarCode. Du kan skaffa en [här](https://purchase.aspose.com/buy).

## Importera paket

För att komma igång, importera de nödvändiga paketen i ditt Java‑projekt. Aspose.BarCode‑biblioteket erbjuder en omfattande uppsättning funktioner för streckkodsgenerering och -igenkänning.

```java
import com.aspose.barcode.*;
import com.aspose.barcode.generation.BarcodeGenerator;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;

import java.io.IOException;
import java.io.UnsupportedEncodingException;
```

## Steg 1: Ställ in resurskatalogen

Definiera sökvägen till din resursmapp.

```java
String dataDir = "Your Document Directory";
```

## Steg 2: Ställ in Aspose.BarCode License

Läs in din Aspose.BarCode‑licens för att låsa upp bibliotekets fulla potential.

```java
try {
    License lic = new License();
    lic.setLicense("aspose.barcode.lic");
} catch (Exception ex) {
    System.out.println(ex.getMessage());
}
```

## Steg 3: Generera Unicode-streckkod

Skapa en Unicode‑streckkod med den angivna texten.

```java
String file = dataDir + "pdf417_un.png";
String scodeText = "منحة";
System.out.println("codetext: " + scodeText);
String codeText = getCodeTextFromUnicode(scodeText);
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.PDF_417, codeText);
generator.save(file);
```

## Steg 4: Läs Unicode-streckkoden

Läs den genererade Unicode‑streckkoden.

```java
BarCodeReader reader = new BarCodeReader(file, DecodeType.PDF_417);
for (BarCodeResult result : reader.readBarCodes()) {
    String rc = result.getCodeText();
    try {
        String s = getUnicodeFromCodeText(rc);
        System.out.println(s);
    } catch (UnsupportedEncodingException e) {
        e.printStackTrace();
    }
}
```

## Steg 5: Konvertera Unicode till kodtext

Implementera metoden för att konvertera Unicode till kodtext.

```java
private static String getCodeTextFromUnicode(String s) throws UnsupportedEncodingException {
    // Implementation details
}
```

## Steg 6: Konvertera kodtext till Unicode

Implementera metoden för att konvertera kodtext till Unicode.

```java
private static String getUnicodeFromCodeText(String cs) throws UnsupportedEncodingException {
    // Implementation details
}
```

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|--------|--------|--------|
| Förvrängd utskrift efter läsning | Fel teckenkodning | Se till att `getUnicodeFromCodeText` använder samma teckenuppsättning (`UTF‑8`) som `getCodeTextFromUnicode`. |
| Läsaren returnerar `null` | Felaktig `DecodeType` | Använd `DecodeType.PDF_417` för PDF417‑streckkoder. |
| Licens tillämpas inte | Licensfilens sökväg är felaktig | Placera `aspose.barcode.lic` i projektets rot eller ange en absolut sökväg. |

## Vanliga frågor

**F: Kan jag använda den här koden med andra streckkodssymboler?**
A: Absolut. Ändra `EncodeTypes.PDF_417` till någon stödjande typ såsom `EncodeTypes.CODE_128` och justera `DecodeType` därefter.

**F: Vad händer om inmatningstexten innehåller emojis?**
S: Emojis är Unicode-tecken; de kommer att kodas korrekt så länge förändringsmetoderna hanterar UTF-8.

**F: Finns det ett sätt att läsa streckkoder från en ström istället för en fil?**
A: Ja, `BarCodeReader` accepterar även en `InputStream` som första argument.

**F: Hur kan jag förbättra igenkänningshastigheten för stora batcher?**
A: Återanvänd en enda `BarCodeReader`‑instans och bearbeta bilder i en loop, och frigör varje resultat omedelbart.

**F: Stöder Aspose.BarCode flersidiga PDF‑filer för streckkodsextraktion?**
A: Ja. Använd `BarCodeReader` med PDF-filens sökväg; biblioteket itererar automatiskt genom alla sidor.

## Slutsats

Grattis! Du har nu bemästrat **how to read barcode image** i Java med Aspose.BarCode, från att generera en Unicode PDF417‑streckkod till att avkoda den tillbaka till dess ursprungliga text. Denna funktion öppnar dörren till internationella applikationer, flerspråkiga lagersystem och alla scenarier där globala teckenuppsättningar krävs.

---

**Senast uppdaterad:** 2025-12-21
**Testat med:** Aspose.BarCode för Java 24.11
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}