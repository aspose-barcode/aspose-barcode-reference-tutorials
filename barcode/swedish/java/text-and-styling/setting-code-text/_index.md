---
date: 2025-12-30
description: Lär dig hur du genererar streckkod java med Aspose.BarCode. Denna steg‑för‑steg‑guide
  visar hur du ställer in anpassad streckkodstext, justerar bredden och sparar bilden.
linktitle: Setting Code Text
second_title: Aspose.BarCode Java API
title: 'Generera streckkod i Java - Ställ in kodtext med Aspose.BarCode'
url: /sv/java/text-and-styling/setting-code-text/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generera streckkod Java: Ställ in kodtext med Aspose.BarCode

## Introduktion

I den här handledningen kommer du att lära dig hur du **genererar streckkod java** med Aspose.BarCode Java‑biblioteket. Oavsett om du bygger ett lagersystem, en dokumentspårningslösning eller någon applikation som behöver streckkoder, guidar den dig genom varje steg—från att skapa en **Code128**‑streckkod till att anpassa kodtexten och justera stapelbredden. I slutet har du en färdig bild som du kan bädda in var du än behöver den.

## Snabba svar
- **Vilket bibliotek ska jag använda?** Aspose.BarCode for Java.
- **Vilken streckkodstyp demonstreras?** CODE_128.
- **Hur ställer jag in anpassad streckkodstext?** Use the `BarcodeGenerator` constructor or `setCodeText` method.
- **Kan jag ändra stapelbredden?** Yes, via `XDimension` in millimeters.
- **Behöver jag en licens för produktion?** Yes, a commercial license is required.

## Förutsättningar

Innan du dyker ner i handledningen, se till att du har följande:

- Grundläggande förståelse för Java-programmering.  
- En fungerande Java‑utvecklingsmiljö installerad.  
- Aspose.BarCode för Java‑biblioteket. Du kan ladda ner det **[här](https://releases.aspose.com/barcode/java/)**.  
- En kodredigerare, såsom IntelliJ IDEA eller Eclipse.  

## Importera paket

Börja med att importera de nödvändiga paketen i ditt Java‑projekt. Dessa paket är nödvändiga för att arbeta med Aspose.BarCode.

```java
import com.aspose.barcode.generation.BarcodeGenerator;
```

Nu ska vi utforska processen för att ställa in kodtext med Aspose.BarCode i Java. Följ dessa steg:

## Barcode Generator-handledning: Skapa en Code128‑streckkod

### Steg 1: Skapa en instans av `BarcodeGenerator`

```java
// The path to the documents directory.
String path = "Your Directory Path";
// The path to the resource directory.
String dataDir = "Your Document Directory";
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");
```

Här skapar vi en `BarcodeGenerator`‑instans, specificerar streckkodssymbologin (**CODE_128**) och den **anpassade streckkodstexten** `"12345678"`.

### Steg 2: Justera streckkodens bredd för anpassad streckkodstext

```java
generator.getParameters().getBarcode().getXDimension().setMillimeters(0.5f);
```

Justera staplarnas bredd efter dina önskemål. I det här exemplet **justerar vi streckkodens bredd** till `0.5` mm, vilket fungerar bra för de flesta etikettstorlekar.

### Steg 3: Spara streckkodsbilden

```java
generator.save(dataDir + "setCodeText.jpg");
```

Spara den genererade streckkodsbilden till den angivna katalogen. I detta fall sparas filen som **`setCodeText.jpg`** i din dokumentkatalog.

## Varför använda Aspose.BarCode för Java?

- **Omfattande API** – Stöder över 60 streckkodssymbologier, inklusive Code128, QR, DataMatrix och mer.  
- **Högkvalitativ rendering** – Genererar skarpa bilder i PNG, JPEG, SVG och PDF-format.  
- **Enkel anpassning** – Ändra text, storlek, färger och även lägga till mänskligt läsbara bildtexter med några kodrader.  
- **Plattformsoberoende** – Fungerar på Windows, Linux och macOS med vilken Java 8+‑runtime som helst.

## Vanliga problem och lösningar

| Problem | Lösning |
|-------|----------|
| **Streckkoden ser suddig ut** | Öka bildens upplösning eller exportera till vektorformat (SVG, PDF). |
| **Texten är avklippt** | Se till att `XDimension` (staplbredd) och `BarHeight` är tillräckligt stora för den valda symbologin. |
| **Licensen har inte tillämpats** | Placera din licensfil (`Aspose.BarCode.lic`) i projektets rot och ladda den med `License license = new License(); license.setLicense("Aspose.BarCode.lic");`. |

## Ytterligare vanliga frågor

**Q:** *Vad är skillnaden mellan `CODE_128` och andra Code128-varianter?*  
**A:** `CODE_128` är den standard‑symbologi som automatiskt väljer den mest effektiva kodningen (A, B eller C) baserat på inmatningstexten.

**Q:** *Kan jag ändra utdataformatet till PNG istället för JPEG?*  
**A:** Absolut. Använd `generator.save(dataDir + "setCodeText.png", com.aspose.barcode.BarcodeImageFormat.PNG);`.

**Q:** *Är det möjligt att lägga till en mänskligt läsbar bildtext under streckkoden?*  
**A:** Ja. Ställ in `generator.getParameters().getBarcode().getCaption().setTopMargin(5);` och ange bildtexten.

**Q:** *Stöder Aspose.BarCode Unicode‑tecken?*  
**A:** Det gör den. Tillhandahåll texten i UTF‑8 och säkerställ att den valda symbologin stödjer teckenuppsättningen.

**Q:** *Hur kan jag generera flera streckkoder i en loop?*  
**A:** Instansiera en ny `BarcodeGenerator` inom loopen, sätt texten för varje iteration och anropa `save` med ett unikt filnamn.

---

**Senast uppdaterad:** 2025-12-30  
**Testad med:** Aspose.BarCode 24.12 for Java  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}