---
date: 2026-06-09
description: Lär dig hur du skapar Code128 barcode Java med Aspose.BarCode. Denna
  steg‑för‑steg‑guide visar hur du genererar barcode Java, sätter custom text, justerar
  bar width och sparar bilden.
keywords:
- create code128 barcode java
- how to generate barcode java
- java barcode generator example
linktitle: Ställa in Code Text
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to create Code128 barcode Java using Aspose.BarCode. This
    step‑by‑step guide shows how to generate barcode Java, set custom text, adjust
    bar width, and save the image.
  headline: Create Code128 Barcode Java – Set Code Text using Aspose.BarCode
  type: TechArticle
- description: Learn how to create Code128 barcode Java using Aspose.BarCode. This
    step‑by‑step guide shows how to generate barcode Java, set custom text, adjust
    bar width, and save the image.
  name: Create Code128 Barcode Java – Set Code Text using Aspose.BarCode
  steps:
  - name: Create an Instance of `BarcodeGenerator`
    text: 'The `BarcodeGenerator` constructor takes two arguments: the barcode symbology
      (`CODE_128`) and the **custom code text** you want to encode, such as `"12345678"`.'
  - name: Adjust Barcode Width for Custom Barcode Text
    text: Set the `XDimension` property (bar width) to control how wide each bar appears.
      In this example we use `0.5` mm, a size that balances readability and label
      space for most applications.
  - name: Save the Barcode Image
    text: Call the `save` method, specifying the output path and image format (JPEG,
      PNG, SVG, etc.). The example saves the file as **`setCodeText.jpg`** in the
      project’s document folder.
  type: HowTo
- questions:
  - answer: Aspose.BarCode for Java.
    question: What library should I use?
  - answer: CODE_128.
    question: Which barcode type is demonstrated?
  - answer: Use the `BarcodeGenerator` constructor or the `setCodeText` method.
    question: How do I set custom barcode text?
  - answer: Yes—adjust `XDimension` (bar width) in millimetres.
    question: Can I change the bar width?
  - answer: A commercial license is required for non‑trial deployments.
    question: Do I need a license for production?
  type: FAQPage
second_title: Aspose.BarCode Java API
title: Skapa Code128 barcode Java – Set Code Text med Aspose.BarCode
url: /sv/java/text-and-styling/setting-code-text/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa Code128-streckkod i Java – Ställ in kodtext med Aspose.BarCode

I den här handledningen kommer du att lära dig hur du **skapar Code128-streckkod i Java** med hjälp av Aspose.BarCode Java‑biblioteket. Oavsett om du bygger ett lagersystem, en dokumentspårningslösning eller någon applikation som behöver streckkoder, guidar vi dig genom varje steg—från att instansiera en **Code128**-streckkod till att anpassa kodtexten och finjustera stapelbredden. I slutet har du en färdig bild som du kan bädda in var du än behöver den.

## Snabba svar
- **Vilket bibliotek ska jag använda?** Aspose.BarCode for Java.  
- **Vilken streckkodstyp demonstreras?** CODE_128.  
- **Hur ställer jag in anpassad streckkodstext?** Använd `BarcodeGenerator`‑konstruktorn eller `setCodeText`‑metoden.  
- **Kan jag ändra stapelbredden?** Ja—justera `XDimension` (stapelbredd) i millimeter.  
- **Behöver jag en licens för produktion?** En kommersiell licens krävs för icke‑testdistributioner.

## Så skapar du en Code128-streckkod i Java?
Läs in `BarcodeGenerator` med `CODE_128`‑symbologi och den önskade texten, ställ in stapelbredden via `XDimension` och anropa sedan `save` för att skriva bildfilen. Detta trestegs‑mönster skapar en högkvalitativ streckkod på några sekunder och fungerar på alla Java 8+‑miljöer, Windows, Linux eller macOS.

## Förutsättningar för att generera streckkod i Java
- Grundläggande kunskap i Java‑programmering.  
- En Java‑utvecklingsmiljö (JDK 8 eller senare).  
- Aspose.BarCode for Java‑biblioteket – ladda ner det **[här](https://releases.aspose.com/barcode/java/)**.  
- Din föredragna IDE (IntelliJ IDEA, Eclipse, etc.).

## Importera paket
Importera de nödvändiga Aspose.BarCode‑namnutrymmena så att klasserna är tillgängliga i ditt projekt.

## Vad är klassen BarcodeGenerator?
`BarcodeGenerator` är kärnklassen i Aspose.BarCode som skapar streckkods‑bilder i minnet. Den erbjuder ett flytande API för att ställa in symbologi, kodtext, dimensioner, färger och ytterligare renderingsalternativ innan resultatet exporteras till format som PNG, JPEG, SVG eller PDF. Du kan också anpassa bildtexter, marginaler och felkorrigeringsnivåer efter behov.

## Handledning för Barcode Generator: Skapa en Code128‑streckkod

### Steg 1: Skapa en instans av `BarcodeGenerator`
`BarcodeGenerator`‑konstruktorn tar två argument: streckkodssymbologin (`CODE_128`) och den **anpassade kodtexten** du vill koda, till exempel `"12345678"`.

```java
// The path to the documents directory.
String path = "Your Directory Path";
// The path to the resource directory.
String dataDir = "Your Document Directory";
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");
```

### Steg 2: Justera streckkodens bredd för anpassad kodtext
Ställ in egenskapen `XDimension` (stapelbredd) för att kontrollera hur bred varje stapel blir. I detta exempel använder vi `0.5` mm, en storlek som balanserar läsbarhet och etikettutrymme för de flesta tillämpningar.

```java
generator.getParameters().getBarcode().getXDimension().setMillimeters(0.5f);
```

### Steg 3: Spara streckkodsbilden
Anropa `save`‑metoden och ange sökvägen samt bildformatet (JPEG, PNG, SVG, etc.). Exemplet sparar filen som **`setCodeText.jpg`** i projektets dokumentmapp.

```java
generator.save(dataDir + "setCodeText.jpg");
```

## Varför använda Aspose.BarCode för Java?
Aspose.BarCode för Java erbjuder ett omfattande funktionspaket som förenklar streckkodsgenerering på olika plattformar. Det stödjer över sextio symbologier, levererar högupplösta raster‑ och vektorutdata och ger prestandaoptimeringar för massbearbetning, vilket gör det idealiskt för företagsapplikationer och sömlös integration med befintliga Java‑projekt.

- **Brett stöd för symbologier** – Över **60** streckkodstyper, inklusive Code128, QR, DataMatrix och PDF417.  
- **Högupplöst rendering** – Genererar skarpa PNG-, JPEG-, SVG- och PDF‑bilder upp till **2000 mm** breda utan kvalitetsförlust.  
- **Prestandafokuserad** – Bearbetar ett 500‑sidigt parti streckkoder på under **2 sekunder** på standard serverhårdvara.  
- **Plattformsoberoende** – Fullt kompatibel med Windows, Linux och macOS, och fungerar med alla Java 8+‑miljöer.

## Vanliga problem och lösningar

| Problem | Lösning |
|-------|----------|
| **Streckkoden ser suddig ut** | Öka bildens upplösning eller exportera till ett vektorformat (SVG, PDF). |
| **Texten är avklippt** | Öka `XDimension` och `BarHeight` för att ge symbologin tillräckligt med utrymme. |
| **Licensen har inte tillämpats** | Placera `Aspose.BarCode.lic` i projektets rotmapp och ladda den med `License license = new License(); license.setLicense("Aspose.BarCode.lic");`. |

## Vanliga frågor

**Q:** *Vad är skillnaden mellan `CODE_128` och andra Code128‑varianter?*  
**A:** `CODE_128` väljer automatiskt den mest effektiva kodningen (A, B eller C) baserat på indata, vilket ger optimal densitet och hastighet.

**Q:** *Kan jag ändra utdataformatet till PNG istället för JPEG?*  
**A:** Ja—använd `generator.save(dataDir + "setCodeText.png", com.aspose.barcode.BarcodeImageFormat.PNG);`.

**Q:** *Är det möjligt att lägga till en mänskligt läsbar bildtext under streckkoden?*  
**A:** Absolut. Ställ in `generator.getParameters().getBarcode().getCaption().setTopMargin(5);` och definiera bildtexten via `setText`.

**Q:** *Stöder Aspose.BarCode Unicode‑tecken?*  
**A:** Ja. Tillhandahåll UTF‑8‑kodad text och säkerställ att den valda symbologin stödjer teckenuppsättningen.

**Q:** *Hur kan jag generera flera streckkoder i en loop?*  
**A:** Instansiera en ny `BarcodeGenerator` inom loopen, tilldela unik text för varje iteration och anropa `save` med ett unikt filnamn.

---

**Senast uppdaterad:** 2026-06-09  
**Testad med:** Aspose.BarCode 24.12 for Java  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Skapa data matrix-streckkod och ställ in kodtextens placering i Java](/barcode/java/text-and-styling/setting-code-text-location/)
- [Hur man ställer in streckkodstextens färg i Java med Aspose.BarCode](/barcode/java/text-and-styling/setting-code-text-foreground-color/)
- [Generera streckkod i Java – Ställ in bildupplösning med Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.barcode.generation.BarcodeGenerator;
```