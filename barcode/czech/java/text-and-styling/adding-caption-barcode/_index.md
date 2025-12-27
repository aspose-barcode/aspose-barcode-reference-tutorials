---
date: 2025-12-27
description: Naučte se, jak přidat popisek k obrázkům čárových kódů v Javě pomocí
  Aspose.BarCode. Tento příklad generátoru čárových kódů v Javě ukazuje, jak snadno
  vytvořit obrázek čárového kódu v Javě.
linktitle: Adding Caption to Barcode
second_title: Aspose.BarCode Java API
title: Jak přidat popisek k čárovému kódu v Javě pomocí Aspose.BarCode
url: /cs/java/text-and-styling/adding-caption-barcode/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat popisek k čárovému kódu v Javě pomocí Aspose.BarCode

## Úvod

Pokud potřebujete **přidat popisek** k čárovému kódu pro lepší čitelnost a značku, jste na správném místě. V tomto tutoriálu vás provedeme přesnými kroky, jak přidat popisky nad a pod obrázek čárového kódu pomocí Aspose.BarCode pro Javu. Na konci budete mít plně stylizovaný čárový kód, který nejen kóduje data, ale také zobrazuje užitečný text – ideální pro produktové štítky, inventární systémy nebo jakýkoli scénář, kde uživatelé těží z doplňujícího kontextu.

## Rychlé odpovědi
- **Jaká knihovna je vyžadována?** Aspose.BarCode for Java.  
- **Mohu změnit písmo a barvu?** Ano – jak rodina písma popisku, tak barva textu jsou přizpůsobitelné.  
- **Které typy čárových kódů fungují?** Všechny symbologie podporované Aspose.BarCode (např. CODE_128, QR, DataMatrix).  
- **Potřebuji licenci pro testování?** K dispozici je bezplatná zkušební verze; pro produkci je vyžadována komerční licence.  
- **Jak dlouho trvá implementace?** Obvykle méně než 10 minut po přidání knihovny.

## Co je popisek v čárovém kódu?
Popisek je prostý text, který se zobrazuje buď nad, nebo pod grafikou čárového kódu. Může sdělovat názvy produktů, ceny nebo jakékoli další informace, které doplňují kódovaná data.

## Proč přidávat popisky pomocí Aspose.BarCode?
- **Zlepšená uživatelská zkušenost:** Uživatelé mohou okamžitě přečíst význam čárového kódu bez skenování.  
- **Konzistence značky:** Můžete použít vlastní písma, barvy a zarovnání, aby odpovídaly firemním stylovým příručkám.  
- **Plná kontrola:** API Aspose.BarCode vám umožňuje přepínat viditelnost, nastavit zarovnání a stylovat každý popisek samostatně.

## Předpoklady

- Java Development Kit (JDK) nainstalován.
- Knihovna Aspose.BarCode pro Java stažena a přidána do vašeho projektu. Odkaz ke stažení najdete [zde](https://releases.aspose.com/barcode/java/).
- IDE, jako je IntelliJ IDEA nebo Eclipse.

## Import balíčků

Ve vašem Java zdrojovém souboru importujte požadované třídy Aspose.BarCode a třídu AWT `Color`:

```java
import com.aspose.barcode.*;
import java.awt.*;
```

## Krok 1: Nastavení dokumentu a adresářů zdrojů

Určete, kam chcete uložit vygenerovaný obrázek čárového kódu. Přizpůsobte cesty tak, aby odpovídaly vašemu prostředí.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

## Krok 2: Vytvoření instance BarcodeGenerator

Vytvořte instanci `BarcodeGenerator` s požadovanou symbologií (např. CODE_128) a textem kódu, který chcete zakódovat.

```java
BarcodeGenerator bb = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

## Krok 3: Nastavení popisku nad čárovým kódem

Nastavte popisek, který se zobrazí nad čárovým kódem. Můžete ovládat zarovnání, text, viditelnost, rodinu písma, velikost a barvu.

```java
bb.getParameters().getCaptionAbove().setAlignment(TextAlignment.LEFT);
bb.getParameters().getCaptionAbove().setText("Aspose.Demo");
bb.getParameters().getCaptionAbove().setVisible(true);
bb.getParameters().getCaptionAbove().getFont().setFamilyName("Pristina");
bb.getParameters().getCaptionAbove().getFont().getSize().setPoint(14);
bb.getParameters().getCaptionAbove().setTextColor(Color.RED);
```

## Krok 4: Nastavení popisku pod čárovým kódem

Podobně definujte popisek pod čárovým kódem. V případě potřeby můžete použít jiné zarovnání nebo styl.

```java
bb.getParameters().getCaptionBelow().setAlignment(TextAlignment.RIGHT);
bb.getParameters().getCaptionBelow().setText("Aspose.Demo");
bb.getParameters().getCaptionBelow().setVisible(true);
bb.getParameters().getCaptionBelow().getFont().setFamilyName("Pristina");
bb.getParameters().getCaptionBelow().getFont().getSize().setPoint(14);
bb.getParameters().getCaptionBelow().setTextColor(Color.RED);
```

## Krok 5: Uložení obrázku čárového kódu

Nakonec zapište čárový kód (s popisky) do souboru obrázku. Formát je odvozen z přípony souboru.

```java
bb.save(dataDir + "barcodeCaption.jpg");
```

Můžete opakovat výše uvedené kroky a experimentovat s různými písmy, barvami nebo zarovnáním, nebo generovat více obrázků čárových kódů ve smyčce.

## Časté problémy a tipy

- **Popisek není viditelný?** Ujistěte se, že je pro požadovaný popisek zavolána metoda `setVisible(true)`.
- **Nesprávné barvy?** Použijte konstanty `java.awt.Color` nebo vytvořte vlastní barvy pomocí `new Color(r, g, b)`.
- **Problémy s cestou?** Ověřte, že `dataDir` ukazuje na existující zapisovatelnou složku; jinak `bb.save()` vyhodí `IOException`.
- **Tip pro výkon:** Při generování mnoha čárových kódů znovu použijte jednu instanci `BarcodeGenerator`; měňte jen `EncodeTypes` nebo `codetext` podle potřeby.

## Často kladené otázky (FAQ)

### Můžu přizpůsobit styl písma popisků čárových kódů?
Ano, můžete přizpůsobit rodinu písma, velikost a barvu jak popisku nad, tak pod čárovým kódem.

### Je Aspose.BarCode kompatibilní s různými symbologiemi čárových kódů?
Rozhodně! Aspose.BarCode podporuje širokou škálu symbologií, což zajišťuje flexibilitu při generování čárových kódů.

### Jak mohu integrovat Aspose.BarCode do svého Java projektu?
Podrobný průvodce integrací najdete [zde](https://reference.aspose.com/barcode/java/) s krok‑za‑krokem instrukcemi.

### Je k dispozici bezplatná zkušební verze Aspose.BarCode pro Java?
Ano, bezplatnou zkušební verzi můžete získat [zde](https://releases.aspose.com/) a vyzkoušet všechny funkce před zakoupením.

### Kde mohu získat pomoc, pokud narazím na problémy?
Komunitní fórum Aspose.BarCode je vynikajícím místem pro podporu a diskusi. Navštivte fórum [zde](https://forum.aspose.com/c/barcode/13).

---

**Poslední aktualizace:** 2025-12-27  
**Testováno s:** Aspose.BarCode for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}