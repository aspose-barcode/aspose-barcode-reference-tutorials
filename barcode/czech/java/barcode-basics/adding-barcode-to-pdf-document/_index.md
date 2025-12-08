---
date: 2025-12-08
description: Naučte se, jak vytvářet PDF dokumenty v Javě a přidávat čárové kódy pomocí
  Aspose.BarCode. Podrobný návod krok za krokem pro generování a vkládání čárových
  kódů do PDF.
language: cs
linktitle: Adding Barcode to PDF Document
second_title: Aspose.BarCode Java API
title: Jak vytvořit PDF dokument v Javě s čárovým kódem pomocí Aspose.BarCode
url: /java/barcode-basics/adding-barcode-to-pdf-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit PDF Java dokument s čárovým kódem pomocí Aspose.BarCode

## Úvod

Vytváření PDF Java dokumentů, které obsahují strojově čitelné čárové kódy, je běžnou požadavkem pro inventární systémy, přepravní štítky a zabezpečené pracovní postupy s dokumenty. V tomto tutoriálu se naučíte **jak vytvořit PDF Java dokumenty** a vložit čárový kód přímo do souboru pomocí **Aspose.BarCode for Java**. Provedeme vás každým krokem – od generování obrázku čárového kódu po jeho vložení do existujícího PDF – abyste mohli během několika minut přidat funkci čárových kódů do svých Java aplikací.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.BarCode for Java (plus Aspose.PDF pro práci s PDF).  
- **Mohu generovat jakýkoli typ čárového kódu?** Ano – Aspose.BarCode podporuje více než 50 symbologií, včetně Code 39, QR, DataMatrix a dalších.  
- **Potřebuji licenci pro vývoj?** Dočasná licence stačí pro hodnocení; plná licence je vyžadována pro produkční nasazení.  
- **Je kód kompatibilní s Java 8+?** Rozhodně – API cílí na Java 8 a novější verze.  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro základní scénář „přidat čárový kód do PDF“.

## Požadavky

Před začátkem se ujistěte, že máte následující:

- **Java Development Kit (JDK)** – nainstalovaná nejnovější stabilní verze.  
- **Aspose.BarCode for Java** – stáhněte z [download page](https://releases.aspose.com/barcode/java/).  
- **Aspose.PDF for Java** – potřebný pro manipulaci s PDF soubory (součástí balíčku BarCode).  

## Importovat jmenné prostory

Nejprve importujte třídy, které budete potřebovat. Tento krok připraví prostředí jak pro generování čárových kódů, tak pro práci s PDF.

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

Vytvořte nový Java projekt ve svém oblíbeném IDE (IntelliJ IDEA, Eclipse, NetBeans atd.). Přidejte stažený **Aspose.BarCode.jar** (a jeho závislosti) do cesty sestavení projektu. Tím zajistíte, že kompilátor najde výše uvedené třídy.

## Krok 2: Vygenerujte obrázek čárového kódu – *jak přidat čárový kód*

Vytvořte instanci `BarcodeGenerator`, vyberte symbologii a nastavte text kódu. Zde **nastavíte symbologii čárového kódu** a **vygenerujete Java objekty čárového kódu**.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD, "1234567");
generator.save(dataDir + "barcodeToPDF.bmp", BarCodeImageFormat.BMP);
```

> **Pro tip:** Nahraďte `EncodeTypes.CODE_39_STANDARD` libovolnou jinou hodnotou `EncodeTypes` (např. `QR`, `DATA_MATRIX`) pro generování různých formátů čárových kódů.

## Krok 3: Vytvořte PDF dokument – *přidat obrázek pdf java*

Nyní **vytvoříme PDF dokument**, který bude hostit obrázek čárového kódu. Aspose.PDF to umožňuje velmi jednoduše.

```java
Document doc = new Document();
doc.getPages().add();
```

V tomto okamžiku máte prázdný PDF připravený přijmout obsah.

## Krok 4: Přidejte obrázek čárového kódu do PDF dokumentu – *přidat čárový kód do existujícího pdf*

Pokud potřebujete vložit čárový kód do **existujícího PDF**, můžete soubor otevřít pomocí `PdfFileMend`. Následující kód sváže PDF, vloží obrázek čárového kódu a uloží výsledek.

```java
PdfFileMend mender = new PdfFileMend();
mender.bindPdf(doc);
mender.addImage(in, 1, 100, 600, 200, 700);
mender.save(dataDir + "AddImage_out.pdf");
mender.close();
```

- `in` je `InputStream`, který ukazuje na obrázek čárového kódu vygenerovaný dříve.  
- Číselné parametry (`1, 100, 600, 200, 700`) určují číslo stránky a umístění (souřadnice X, Y, šířka, výška). Upravit je podle potřeby, aby odpovídaly vašemu rozvržení.

## Časté problémy a řešení

| Problém | Proč se to stane | Řešení |
|---------|------------------|--------|
| **Obrázek se nezobrazuje** | Špatné souřadnice nebo index stránky. | Ověřte číslo stránky (`1` pro první stránku) a ujistěte se, že stream obrázku není uzavřen před voláním `addImage`. |
| **Není podporován typ čárového kódu** | Použití symbologie, která není zahrnuta v licenci. | Zkontrolujte soubor licence; v případě potřeby proveďte upgrade. |
| **FileNotFoundException** | Cesta `dataDir` je nesprávná. | Použijte absolutní cestu nebo `System.getProperty("user.dir")` pro dynamické vytvoření adresáře. |

## Často kladené otázky

**Q: Mohu přizpůsobit vzhled čárového kódu v PDF dokumentu?**  
A: Ano. Aspose.BarCode vám umožní měnit barvy, písma, okraje a dokonce přidat lidsky čitelný text. Upravit můžete vlastnosti `BarcodeGenerator` před uložením.

**Q: Je Aspose.BarCode kompatibilní s různými symbologiemi čárových kódů?**  
A: Rozhodně. Podporováno je více než 50 symbologií, včetně Code 128, QR, DataMatrix, PDF417 a dalších.

**Q: Jak mohu získat dočasnou licenci pro Aspose.BarCode?**  
A: Navštivte [temporary license page](https://purchase.aspose.com/temporary-license/) na webu Aspose a požádejte o 30‑denní evaluační licenci.

**Q: Kde mohu získat pomoc a podporu pro dotazy související s Aspose.BarCode?**  
A: Fórum [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) je aktivní komunita, kde můžete klást otázky a sdílet řešení.

**Q: Mohu si vyzkoušet Aspose.BarCode pro Java zdarma před zakoupením?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi z [release page](https://releases.aspose.com/) a vyzkoušet všechny funkce bez licence.

## Závěr

Nyní víte **jak vytvořit PDF Java dokumenty** a vložit do nich čárové kódy pomocí Aspose.BarCode. Tato schopnost zjednodušuje pracovní postupy, jako je generování přepravních štítků, tvorba zabezpečených faktur nebo budování systémů sledování zásob. Experimentujte s různými symbologiemi, upravujte umístění obrázku a integrujte kód do větších Java služeb, abyste plně využili technologii čárových kódů.

---

**Last Updated:** 2025-12-08  
**Tested With:** Aspose.BarCode 24.11 for Java, Aspose.PDF 24.11 for Java  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}