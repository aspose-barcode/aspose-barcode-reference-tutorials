---
date: 2025-12-25
description: Naučte se, jak extrahovat text z obrázků čárových kódů, konkrétně PDF417
  s čínskými znaky, pomocí Aspose.BarCode pro Javu. Postupujte podle našeho krok‑za‑krokem
  průvodce, jak efektivně číst data z čárových kódů.
linktitle: 'Extract Text from Barcode: PDF417 Chinese Characters'
second_title: Aspose.BarCode Java API
title: 'Extrahovat text z čárového kódu: PDF417 čínské znaky v Javě'
url: /cs/java/multilingual-support/recognizing-pdf417-chinese-characters/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extrahovat text z čárového kódu: PDF417 čínské znaky v Javě

## Úvod

Integrace rozpoznávání čárových kódů do aplikací v Javě je cenná dovednost, zejména když potřebujete **extrahovat text z čárového kódu** z obrázků obsahujících vícejazyčná data. V tomto tutoriálu vás provedeme používáním Aspose.BarCode pro Java k rozpoznání PDF417 čárových kódů s čínskými znaky. Na konci přesně budete vědět, jak číst data z čárového kódu a dekódovat je do čitelného textu.

## Rychlé odpovědi
- **Jaká knihovna podporuje PDF417 s čínskými znaky?** Aspose.BarCode pro Java.  
- **Jaká znaková sada je potřeba pro čínské dekódování?** MS936 (GBK).  
- **Potřebuji licenci pro produkční použití?** Ano, je vyžadována komerční licence.  
- **Mohu to spustit na jakékoli verzi Javy?** Funguje s Java 8 a novějšími.  
- **Je k dispozici bezplatná zkušební verze?** Rozhodně – stáhněte ji ze stránek Aspose.

## Co je “extrahovat text z čárového kódu”?

Extrahování textu z čárového kódu znamená převést zakódovaná data zpět do jejich původní lidsky čitelné podoby. Pro PDF417 čárové kódy, které ukládají čínské znaky, to také zahrnuje výběr správného kódování znaků, aby bajty odpovídaly správným glyfům## Proč použít Aspose.BarCode pro Java?

Aspose.BarCode poskytuje robustní podporu pro širokou škálu symbologií čárových kódů, včetně PDF417, a zajišťuje zpracování složitých znakových sad přímo z krabice. Abstrahuje nízkoúrovňové zpracování obrazu, což vám umožní soustředit se na obchodní logiku místo na detaily dekódování.

## Předpoklady

Předtím, než se ponoříme, ujistěte se, že máte:

1. **Java Development Kit (JDK)** – doporučuje se nejnovější verze.  
2. **Aspose.BarCode pro Java** – stáhněte ji z [zde](https://releases.aspose.com/barcode/java/).  
3. **Obrázek PDF417 čárového kódu**, který obsahuje čínské znaky (např. `barcode.png`).

## Importovat balíčky

Ve svém Java projektu importujte potřebné třídy pro práci s Aspose.BarCode:

```java
import java.nio.ByteBuffer;
import java.nio.charset.Charset;

import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## Krok 1: Nastavit adresář dokumentu

Zadejte složku, kde se nachází váš obrázek čárového kódu:

```java
String dataDir = "Your Document Directory";
```

Nahraďte `"Your Document Directory"` skutečnou cestou na vašem počítači.

## Krok 2: Načíst obrázek čárového kódu

Vytvořte instanci `BarCodeReader`, která ukazuje na soubor PNG a řekne čtečce, aby hledala symbologii PDF417:

```java
BarCodeReader reader = new BarCodeReader(dataDir + "barcode.png", DecodeType.PDF_417);
```

## Krok 3: Přečíst čárový kód

Iterujte přes výsledky detekce, získávejte surové pole bajtů a dekódujte jej pomocí znakové sady GBK (MS936):

```java
for (BarCodeResult result : reader.readBarCodes()) {
    byte[] bytes = result.getCodeBytes();
    ByteBuffer bytebuf = ByteBuffer.wrap(bytes);
    System.out.println(Charset.forName("MS936").decode(bytebuf).toString());
}
```

Tato smyčka **extrahuje text z čárového kódu** a vypíše dekódované čínské znaky do konzole.

## Jak číst čárový kód s PDF417?

Kód výše demonstruje **jak číst data z čárového kódu** krok za krokem:

1. **Inicializujte** čtečku s správným `DecodeType`.  
2. **Iterujte** přes každý vrácený `BarCodeResult`.  
3. **Převěďte** surové bajty pomocí odpovídající znakové sady (`MS936` pro čínštinu).  

Pokud váš čárový kód obsahuje jiné jazyky, stačí přepnout znakovou sadu na tu, která odpovídá vašim datům.

## Časté problémy a řešení

| Problém | Řešení |
|---------|--------|
| Poškozené znaky po dekódování | Ověřte, že používáte správnou znakovou sadu (`MS936` pro GBK). |
| Nebyl detekován žádný čárový kód | Zajistěte vysokou kvalitu obrázku a že čárový kód není otočen; v případě potřeby můžete obrázek předzpracovat. |
| Vráceno více výsledků | PDF417 může uložit více segmentů; iterujte přes všechny výsledky, jak je ukázáno. |

## Často kladené otázky (FAQ)

### Mohu použít Aspose.BarCode pro Java v komerčních projektech?
Ano, můžete použít Aspose.BarCode pro Java v komerčních projektech. Podrobnosti o licencování najdete [zde](https://purchase.aspose.com/buy).

### Je k dispozici bezplatná zkušební verze?
Ano, můžete získat bezplatnou zkušební verzi Aspose.BarCode pro Java [zde](https://releases.aspose.com/).

### Jak mohu získat podporu pro Aspose.BarCode?
Navštivte fórum Aspose.BarCode [zde](https://forum.aspose.com/c/barcode/13) pro jakoukoli podporu nebo dotazy.

### Mohu získat dočasnou licenci pro testovací účely?
Ano, můžete získat dočasnou licenci [zde](https://purchase.aspose.com/temporary-license/).

### Kde najdu dokumentaci?
Dokumentace je k dispozici [zde](https://reference.aspose.com/barcode/java/).

**Additional Q&A**

**Q: Co když je můj obrázek čárového kódu ve formátu JPEG?**  
**A:** `BarCodeReader` funguje s JPEG, PNG, BMP a dalšími běžnými formáty obrázků – stačí podle toho změnit příponu souboru.

**Q: Mohu dekódovat čárové kódy ze streamu místo souboru?**  
**A:** Ano, můžete předat `InputStream` konstruktoru `BarCodeReader` pro dekódování za běhu.

**Q: Podporuje Aspose.BarCode jiné znakové sady?**  
**A:** Rozhodně. Použijte `Charset.forName("<your‑charset>")` pro dekódování bajtů pro UTF‑8, ISO‑8859‑1 atd.

## Závěr

Nyní jste se naučili, jak **extrahovat text z čárového kódu** z obrázků, konkrétně PDF417 čárových kódů obsahujících čínské znaky, pomocí Aspose.BarCode pro Java. Tato schopnost otevírá dveře k vícejazyčným inventárním systémům, automatizaci dokumentů a dalšímu. Klidně experimentujte s dalšími symbologiemi a znakovými sadami, abyste rozšířili dosah své aplikace.

---

**Poslední aktualizace:** 2025-12-25  
**Testováno s:** Aspose.BarCode pro Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}