---
date: 2026-02-07
description: Použijte knihovnu Java barcode k přidání čárového kódu do PDF dokumentů
  pomocí Aspose.BarCode. Podrobný návod krok za krokem pro generování čárových kódů
  a jejich vložení do PDF souborů.
linktitle: Adding Barcode to PDF Document
second_title: Aspose.BarCode Java API
title: java knihovna čárových kódů – Přidat čárový kód do PDF pomocí Aspose
url: /cs/java/barcode-basics/adding-barcode-to-pdf-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit PDF Java dokument s čárovým kódem pomocí Aspose.BarCode

## Úvod

Pokud hledáte **java barcode library**, která dokáže bez problémů generovat čárové kódy a vložit je do PDF souborů, jste na správném místě. V tomto tutoriálu vás provedeme, jak **create PDF Java documents** a **add barcode** obrázky pomocí **Aspose.BarCode for Java**. Ať už potřebujete generovat přepravní štítky, inventární značky nebo zabezpečené faktury, tento průvodce vám ukáže, jak přesně přidat čárový kód do nového nebo existujícího PDF během několika minut.

## Rychlé odpovědi
- **Jakou knihovnu potřebuji?** Aspose.BarCode for Java (plus Aspose.PDF for PDF handling).  
- **Mohu generovat jakýkoli typ čárového kódu?** Ano – Aspose.BarCode podporuje více než 50 symbologií, včetně Code 39, QR, DataMatrix a dalších.  
- **Potřebuji licenci pro vývoj?** Dočasná licence funguje pro hodnocení; plná licence je vyžadována pro produkci.  
- **Je kód kompatibilní s Java 8+?** Rozhodně – API cílí na Java 8 a novější.  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro základní scénář „přidat čárový kód do PDF“.

## Co je java barcode library?

Aspose.BarCode for Java je výkonná **java barcode library**, která vám umožní programově generovat širokou škálu 1‑D a 2‑D čárových kódů. Úzce se integruje s Aspose.PDF, což usnadňuje umístění obrázků čárových kódů na stránky PDF, aniž byste museli řešit nízkoúrovňový grafický kód.

## Proč použít tento přístup?

- **Plná kontrola** nad symbologií čárového kódu, velikostí a vzhledem.  
- **Žádné externí závislosti** – vše běží uvnitř vašeho Java procesu.  
- **Podporuje existující PDF**, takže můžete doplnit starší dokumenty o čárové kódy.  
- **Cross‑platform** – funguje na Windows, Linuxu i macOS.

## Předpoklady

Předtím, než začneme, ujistěte se, že máte následující:

- **Java Development Kit (JDK)** – nainstalovaná nejnovější stabilní verze.  
- **Aspose.BarCode for Java** – stáhněte z [download page](https://releases.aspose.com/barcode/java/).  
- **Aspose.PDF for Java** – potřebný pro manipulaci s PDF soubory (je součástí balíčku BarCode).  

## Import Namespaces

Nejprve importujte třídy, které budete potřebovat. Tento krok nastaví prostředí pro generování čárových kódů i manipulaci s PDF.

```java
// Import Aspose.BarCode namespaces
import com.aspose.pdf.*;
import com.aspose.pdf.facades.*;

import com.aspose.barcode.generation.*;
import com.aspose.barcode.*;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.InputStream;
import java.io.OutputStream;

import com.aspose.barcode.EncodeTypes;
```

## Krok 1: Nastavte svůj Java projekt

Vytvořte nový Java projekt ve svém preferovaném IDE (IntelliJ IDEA, Eclipse, NetBeans atd.). Přidejte stažený **Aspose.BarCode.jar** (a jeho závislosti) do cesty sestavení vašeho projektu. Tím zajistíte, že kompilátor dokáže najít výše zmíněné třídy.

## Krok 2: Vygenerujte obrázek čárového kódu – *how to add barcode*

Vytvořte instanci `BarcodeGenerator`, vyberte symbologii a nastavte text kódu. Zde **set barcode symbology** a **generate barcode Java** objekty.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD, "1234567");
generator.save(dataDir + "barcodeToPDF.bmp", BarCodeImageFormat.BMP);
```

> **Tip:** Nahraďte `EncodeTypes.CODE_39_STANDARD` libovolnou jinou hodnotou `EncodeTypes` (např. `QR`, `DATA_MATRIX`), abyste vygenerovali různé formáty čárových kódů.

## Krok 3: Vytvořte PDF dokument – *add image pdf java*

Nyní **create a PDF document**, který bude hostovat obrázek čárového kódu. Aspose.PDF to usnadňuje.

```java
Document doc = new Document();
doc.getPages().add();
```

V tomto okamžiku máte prázdný PDF připravený k přijímání obsahu.

## Krok 4: Přidejte obrázek čárového kódu do PDF dokumentu – *add barcode existing pdf*

Pokud potřebujete vložit čárový kód do **existing PDF**, můžete soubor otevřít pomocí `PdfFileMend`. Následující kód připojí PDF, vloží obrázek čárového kódu a uloží výsledek.

```java
PdfFileMend mender = new PdfFileMend();
mender.bindPdf(doc);
mender.addImage(in, 1, 100, 600, 200, 700);
mender.save(dataDir + "AddImage_out.pdf");
mender.close();
```

- `in` je `InputStream`, který ukazuje na obrázek čárového kódu vygenerovaný dříve.  
- Číselné parametry (`1, 100, 600, 200, 700`) definují číslo stránky a umístění (souřadnice X, Y, šířka, výška). Přizpůsobte je podle svého rozvržení.

## Časté problémy a řešení

| Problém | Proč se stane | Řešení |
|-------|----------------|-----|
| **Image not showing** | Špatné souřadnice nebo index stránky. | Ověřte číslo stránky (`1` pro první stránku) a ujistěte se, že stream obrázku není uzavřen před `addImage`. |
| **Unsupported barcode type** | Použití symbologie, která není zahrnuta v licenci. | Zkontrolujte svůj licenční soubor; v případě potřeby upgradujte. |
| **FileNotFoundException** | Cesta `dataDir` je nesprávná. | Použijte absolutní cestu nebo `System.getProperty("user.dir")` pro dynamické vytvoření adresáře. |

## Často kladené otázky

**Q: Mohu přizpůsobit vzhled čárového kódu v PDF dokumentu?**  
A: Ano. Aspose.BarCode vám umožní měnit barvy, písma, okraje a dokonce přidat lidsky čitelný text. Upravit vlastnosti `BarcodeGenerator` před uložením.

**Q: Je Aspose.BarCode kompatibilní s různými symbologiemi čárových kódů?**  
A: Rozhodně. Podporuje se více než 50 symbologií, včetně Code 128, QR, DataMatrix, PDF417 a dalších.

**Q: Jak mohu získat dočasnou licenci pro Aspose.BarCode?**  
A: Navštivte [temporary license page](https://purchase.aspose.com/temporary-license/) na webu Aspose a požádejte o 30‑denní evaluační licenci.

**Q: Kde mohu získat pomoc a podporu pro dotazy týkající se Aspose.BarCode?**  
A: Fórum [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) je aktivní komunita, kde můžete klást otázky a sdílet řešení.

**Q: Můžu si Aspose.BarCode pro Java vyzkoušet zdarma před zakoupením?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi z [release page](https://releases.aspose.com/) a vyzkoušet všechny funkce bez licence.

## Závěr

Nyní víte **how to create PDF Java documents** a jak vložit čárové kódy pomocí Aspose.BarCode. Tato schopnost zjednodušuje pracovní postupy, jako je generování přepravních štítků, tvorba zabezpečených faktur nebo budování systémů sledování zásob. Experimentujte s různými symbologiemi, upravujte umístění obrázku a integrujte kód do větších Java služeb, abyste plně využili technologii čárových kódů.

---

**Last Updated:** 2026-02-07  
**Tested With:** Aspose.BarCode 24.11 for Java, Aspose.PDF 24.11 for Java  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}