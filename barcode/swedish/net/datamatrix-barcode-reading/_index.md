---
date: 2026-09-28
description: Lär dig hur du läser datamatrix och hur du enkelt genererar datamatrix
  barcodes med Aspose.BarCode för .NET. Utforska reader programming, structured append
  och generation guides.
keywords:
- how to read datamatrix
- datamatrix barcode reading
- Aspose.BarCode .NET
lastmod: 2026-09-28
linktitle: DataMatrix Barcode Reading
og_description: Hur man läser datamatrix barcodes med Aspose.BarCode för .NET – en
  snabb, cross‑platform guide som täcker reading, structured append och generation.
  (150‑160 tecken)
og_image_alt: Screenshot of Aspose.BarCode reading a DataMatrix barcode in a .NET
  app
og_title: Hur man läser datamatrix barcodes med Aspose.BarCode för .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to read datamatrix and how to generate datamatrix barcodes
    effortlessly using Aspose.BarCode for .NET. Explore reader programming, structured
    append and generation guides.
  headline: How to read datamatrix barcodes with Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. A valid commercial license is required for production use, but a
      free trial is available for evaluation.
    question: Can I use Aspose.BarCode for commercial projects?
  - answer: Absolutely. You can load a PDF page as an image stream and pass it directly
      to the barcode reader.
    question: Does the library support reading DataMatrix from PDF files?
  - answer: The API automatically assembles the fragments if you enable the `ReadStructuredAppend`
      property before decoding.
    question: How do I handle Structured Append when a barcode is split across multiple
      images?
  - answer: You can choose from ECC 000, 050, 080, 100, 140, and 200 depending on
      the required data density and robustness.
    question: What error‑correction levels are available when generating a DataMatrix
      barcode?
  - answer: Yes—use the `BarcodeReader` with `ReadMultipleBarcodes` set to `true`
      and process images in parallel threads.
    question: Is there a way to improve read performance on large image batches?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix
- Aspose.BarCode
- .NET barcode processing
title: Hur man läser datamatrix barcodes med Aspose.BarCode för .NET
url: /sv/net/datamatrix-barcode-reading/
weight: 31
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man läser DataMatrix‑streckkoder

Om du behöver **hur man läser datamatrix** effektivt i en .NET‑miljö, ger den här guiden dig en steg‑för‑steg‑genomgång av att läsa, konfigurera structured append och generera DataMatrix‑streckkoder med Aspose.BarCode för .NET. Du får se varför biblioteket är ett förstahandsval, vad du måste förbereda i förväg och var du hittar de mest användbara kodsnuttarna.

## Snabba svar
- **Vad är DataMatrix?** En tvådimensionell matrisstreckkod som lagrar stora mängder data i ett litet utrymme.  
- **Vilket bibliotek hjälper dig att läsa DataMatrix i .NET?** Aspose.BarCode för .NET.  
- **Behöver jag en licens?** En gratis provversion finns tillgänglig; en kommersiell licens krävs för produktion.  
- **Kan jag också generera DataMatrix‑streckkoder?** Ja—använd samma API för att **hur man genererar datamatrix** streckkoder med anpassade inställningar.  
- **Stödda plattformar?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7 på Windows, Linux och macOS.

## Vad är DataMatrix‑streckkodsläsning?
Att läsa en DataMatrix‑streckkod extraherar den kodade texten eller binära data från en bild, PDF‑sida eller en levande videoram. Aspose.BarCode‑avkodaren fungerar direkt med `System.Drawing.Image`, `Stream` eller `PdfPage`‑objekt, så du kan mata den från filer, minnesströmmar eller kamerafångster utan extra konverteringssteg.

## Varför använda Aspose.BarCode för DataMatrix?
Aspose.BarCode bearbetar upp till **5 000 streckkoder per sekund** på en standard‑CPU på 2,5 GHz, hanterar **50+ inmatningsformat** och kräver **inget externt inhemskt beroende**. Biblioteket körs på Windows, Linux och macOS, stödjer felkorrigeringsnivåer från ECC 000 till ECC 200 och erbjuder inbyggd structured‑append‑hantering — allt medan minnesanvändningen hålls under 20 MB för ett batch på 1 000 sidor.

## Förutsättningar
- .NET Framework 4.5+ eller .NET Core 3.1+ (någon recent .NET‑version).  
- Aspose.BarCode för .NET‑NuGet‑paket installerat.  
- Grundläggande kunskap om C# och en IDE såsom Visual Studio eller Rider.

## DataMatrix‑läsarprogrammering: en sömlös integration

### Hur läser man en DataMatrix‑streckkod i .NET?
`BarcodeReader` är Aspose.BarCode‑klassen som avkodar streckkoder från bilder, strömmar eller PDF‑sidor.  
Läs in bilden eller PDF‑sidan, skapa en `BarcodeReader`, aktivera flaggan `ReadMultipleBarcodes` om du förväntar dig mer än en kod, och anropa `Read`. Metoden returnerar en samling av `BarCodeResult` som innehåller det avkodade värdet, symboltyp och förtroendescore.  
`BarCodeResult` representerar en enskild avkodad streckkod, inklusive dess värde, symboltyp och förtroendescore.

### Hur aktiverar man strukturerad append‑hantering?
Ställ in egenskapen `ReadStructuredAppend` till `true` innan du anropar `Read`. Läsaren kommer automatiskt att sammanfoga fragment som tillhör samma logiska meddelande och returnera ett enda kombinerat resultat.

## DataMatrix‑strukturerad append‑konfiguration: organisera data med precision
Structured Append låter ett enskilt logiskt meddelande delas upp över flera DataMatrix‑symboler. När du aktiverar den här funktionen samlar Aspose.BarCode ihop fragmenten baserat på sekvensnummer som är inbäddade i varje symbol. Detta är idealiskt för att koda långa URL:er, stora binära blobbar eller flersidiga dokument.

## Generera DataMatrix‑streckkoder: släpp loss kreativiteten med Aspose.BarCode för .NET
`BarcodeGenerator` är Aspose.BarCode‑klassen som används för att generera streckkods‑bilder med anpassningsbara parametrar. Samma `BarcodeGenerator`‑klass som du använder för läsning skapar också DataMatrix‑symboler. Du kan kontrollera modulstorlek, marginal, ECC‑nivå och till och med bädda in en logobild. Generatorn kan exportera PNG-, JPEG-, SVG- eller PDF‑filer, vilket ger dig full flexibilitet för webb, utskrift eller mobila scenarier.

## DataMatrix‑streckkodsläsningshandledningar
### [DataMatrix‑läsarprogrammering](./datamatrix-reader-programming/)
Utforska DataMatrix‑läsarprogrammering med Aspose.BarCode för .NET. Lär dig hur du genererar och läser DataMatrix‑streckkoder i dina .NET‑applikationer med denna omfattande guide.
### [DataMatrix‑strukturerad append‑konfiguration](./datamatrix-structured-append-configuration/)
Lär dig hur du skapar och läser DataMatrix‑strukturerad append‑konfiguration i .NET med Aspose.BarCode för hög‑effektiv dataorganisation.
### [Generera DataMatrix‑streckkoder](./datamatrix-versions/)
Lär dig hur du genererar DataMatrix‑streckkoder i .NET med Aspose.BarCode för .NET. Anpassade dimensioner, ECC‑stöd och mer.

## Vanliga frågor

**Q: Kan jag använda Aspose.BarCode för kommersiella projekt?**  
A: Ja. En giltig kommersiell licens krävs för produktionsanvändning, men en gratis provversion finns tillgänglig för utvärdering.

**Q: Stöder biblioteket att läsa DataMatrix från PDF‑filer?**  
A: Absolut. Du kan ladda en PDF‑sida som en bildström och skicka den direkt till streckkodsläsaren.

**Q: Hur hanterar jag Structured Append när en streckkod är delad över flera bilder?**  
A: API‑et samlar automatiskt ihop fragmenten om du aktiverar egenskapen `ReadStructuredAppend` innan avkodning.

**Q: Vilka felkorrigeringsnivåer är tillgängliga när man genererar en DataMatrix‑streckkod?**  
A: Du kan välja mellan ECC 000, 050, 080, 100, 140 och 200 beroende på den erforderliga datadensiteten och robustheten.

**Q: Finns det ett sätt att förbättra läshastigheten för stora bildbatchar?**  
A: Ja—använd `BarcodeReader` med `ReadMultipleBarcodes` satt till `true` och bearbeta bilder i parallella trådar.

---

**Senast uppdaterad:** 2026-09-28  
**Testad med:** Aspose.BarCode för .NET 24.12  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man genererar DataMatrix‑streckkoder med Aspose.BarCode för .NET – steg‑för‑steg‑guide](/barcode/net/datamatrix-barcode-configuration/)
- [Hur man läser DataMatrix‑append med Aspose.BarCode för .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)
- [Generera en DataMatrix‑streckkod i ASCII‑läge med Aspose.BarCode för .NET (C#)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}