---
date: 2026-05-04
description: Erfahren Sie, wie Sie einen Data‑Matrix‑Barcode mit einer Java‑Barcode‑Bibliothek
  erstellen und den Barcode‑Text über dem Symbol mit Aspose.BarCode positionieren.
  Folgen Sie unserem Schritt‑für‑Schritt‑Beispiel zur Barcode‑Erstellung.
keywords:
- java barcode library
- barcode generation example
- barcode text above
- customize barcode text
linktitle: Einstellung des Code‑Text‑Standorts
second_title: Aspose.BarCode Java API
title: Data Matrix‑Barcode mit Java‑Barcode‑Bibliothek erstellen und Textposition
  festlegen
url: /de/java/text-and-styling/setting-code-text-location/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erstellen Sie einen Data Matrix Barcode mit der Java Barcode-Bibliothek und legen Sie die Position des Code-Textes fest

## Einleitung

Wenn Sie ein Inventar-, Versand‑ oder Tracking‑System in Java erstellen, werden Sie schnell feststellen, dass eine zuverlässige **java barcode library** unverzichtbar ist. Mit **Aspose.BarCode for Java** können Sie einen **Data Matrix barcode** in nur wenigen Codezeilen erzeugen und das visuelle Layout vollständig steuern, einschließlich der Position des menschenlesbaren Textes. In diesem Tutorial führen wir Sie durch ein vollständiges **barcode generation example**, zeigen Ihnen, wie Sie die **customize barcode text**‑Platzierung anpassen, und erklären, warum das Positionieren des Textes über dem Symbol die Benutzerfreundlichkeit verbessern kann.

## Schnelle Antworten
- **Welche Bibliothek wird verwendet?** Aspose.BarCode for Java  
- **Welcher Barcode‑Typ wird demonstriert?** Data Matrix  
- **Wie positionieren Sie den Code‑Text?** Using `CodeLocation.ABOVE` (you can also use `BELOW`)  
- **Benötigen Sie eine Lizenz für die Produktion?** Yes, a commercial license is required  
- **Kann der Code unter Java 8+ ausgeführt werden?** Absolutely, it supports Java 8 and later  

## Was ist eine Java‑Barcode‑Bibliothek?
Eine **java barcode library** bietet Entwicklern fertige APIs zum Erstellen, Lesen und Gestalten von 1‑D‑ und 2‑D‑Barcodes direkt aus Java‑Anwendungen. Sie abstrahiert die komplexen Kodierungsregeln und ermöglicht es Ihnen, sich auf die Geschäftslogik zu konzentrieren, anstatt sich mit der Low‑Level‑Bildverarbeitung zu befassen.

## Warum eine Java‑Barcode‑Bibliothek für das Barcode‑Generierungsbeispiel verwenden?
- **Geschwindigkeit:** Generate high‑quality barcodes in milliseconds.  
- **Zuverlässigkeit:** Built‑in compliance with ISO/IEC standards.  
- **Flexibilität:** Full control over size, color, margins, and **barcode text** placement.  
- **Plattformübergreifend:** Works on any JVM‑based environment, from desktop apps to cloud services.

## Was ist ein Data Matrix Barcode?
Ein Data Matrix Barcode ist ein zweidimensionales (2‑D) Symbol, das große Datenmengen in einem kompakten quadratischen oder rechteckigen Muster speichert. Er wird häufig zum Kennzeichnen kleiner Gegenstände, Elektronik und medizinischer Geräte verwendet, da er bis zu 2.335 alphanumerische Zeichen codieren kann.

## Warum die Position des Barcode‑Textes festlegen?
Das Platzieren des menschenlesbaren Textes **über**, **unter** oder **neben** dem Barcode hilft Benutzern, die codierten Daten schnell zu überprüfen, ohne zu scannen. Das Anpassen der Textposition verbessert die Konsistenz der Benutzeroberfläche, entspricht den Markenrichtlinien und kann Fehler bei manueller Dateneingabe reduzieren.

## Voraussetzungen

- Grundlegende Kenntnisse in der Java‑Programmierung.  
- Java Development Kit (JDK) installiert.  
- Eine IDE wie Eclipse oder IntelliJ IDEA.  
- Aspose.BarCode for Java Bibliothek (laden Sie sie von [here](https://releases.aspose.com/barcode/java/) herunter).  

## Pakete importieren

Zuerst importieren Sie die wesentlichen Aspose.BarCode‑Klassen in Ihr Projekt:

```java
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.generation.BarcodeGenerator;
```

Diese Importe geben Ihnen Zugriff auf den Barcode‑Generator und die Aufzählung, die die Textposition steuert.

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Verzeichnis‑Pfade festlegen
Geben Sie an, wo Sie Dateien lesen/schreiben möchten. Ersetzen Sie die Platzhalter durch tatsächliche Pfade auf Ihrem Rechner.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

### Schritt 2: Eine BarcodeGenerator‑Instanz erstellen
Instanziieren Sie `BarcodeGenerator` mit dem **Data Matrix**‑Typ und geben Sie den Code‑Text an, den Sie codieren möchten.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DATA_MATRIX,
        "GTIN:898978777776665655 " + "UID: 121212121212121212 " + "Batch:GH768 " + "Exp.Date:150923");
```

### Schritt 3: Barcode‑Textposition festlegen (Barcode‑Text anpassen)
Verwenden Sie die Aufzählung `CodeLocation`, um den menschenlesbaren Text zu verschieben. In diesem Beispiel platzieren wir ihn **über** dem Barcode.

```java
generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.ABOVE);
```

> **Pro Tipp:** Um den Text **unter** dem Symbol zu platzieren, ändern Sie einfach `CodeLocation.ABOVE` zu `CodeLocation.BELOW`.

### Schritt 4: Das erzeugte Barcode‑Bild speichern
Schließlich schreiben Sie das Barcode‑Bild auf die Festplatte. Die Datei enthält das Data Matrix‑Symbol mit dem darüber positionierten Text.

```java
generator.save(dataDir + "codetextAbove.png");
```

## Häufige Probleme und Lösungen
- **Text wird nicht angezeigt:** Ensure you are using a version of Aspose.BarCode that supports `CodeLocation`.  
- **Dateipfad‑Fehler:** Verify that `dataDir` ends with a file separator (`/` or `\\`) appropriate for your OS.  
- **Nicht unterstützte Zeichen:** Data Matrix can encode only a limited set of characters; avoid special symbols not in the ISO/IEC 16022 standard.  

## Häufig gestellte Fragen (FAQs)

### Q: Kann ich das Aussehen des erzeugten Barcodes anpassen?
A: Ja, Aspose.BarCode bietet umfangreiche Anpassungsoptionen, mit denen Sie Farben, Ränder und Schriftstile steuern können.

### Q: Ist Aspose.BarCode mit Java 8 und späteren Versionen kompatibel?
A: Absolut, die Bibliothek funktioniert mit Java 8 und allen nachfolgenden Versionen.

### Q: Wie kann ich Aspose.BarCode in mein bestehendes Java‑Projekt integrieren?
A: Fügen Sie die Aspose.BarCode‑JAR‑Dateien zu Ihrem Projekt‑Classpath hinzu, importieren Sie die erforderlichen Pakete, und Sie können Barcodes erzeugen.

### Q: Gibt es eine Testversion von Aspose.BarCode?
A: Ja, Sie können die Funktionen von Aspose.BarCode testen, indem Sie eine kostenlose Testversion [hier](https://releases.aspose.com/) erhalten.

### Q: Wo kann ich Hilfe oder Support für Aspose.BarCode erhalten?
A: Besuchen Sie das [Aspose.BarCode‑Forum](https://forum.aspose.com/c/barcode/13) für Community‑Unterstützung und offiziellen Support.

## Weitere häufig gestellte Fragen

**Q: Kann ich einen Barcode mit Text unter dem Symbol erzeugen?**  
A: Ja, setzen Sie `CodeLocation.BELOW` in derselben `setLocation`‑Methode.

**Q: Unterstützt die Bibliothek andere 2‑D‑Barcodes wie QR‑Code?**  
A: Absolut, ändern Sie einfach `EncodeTypes.DATA_MATRIX` zu `EncodeTypes.QR`.

**Q: Wie ändere ich die Schriftgröße des Barcode‑Textes?**  
A: Verwenden Sie `generator.getParameters().getBarcode().getCodeTextParameters().setFontSize(double size)`.

## Fazit

Sie haben nun gelernt, wie man in Java mit einer **java barcode library** einen **Data Matrix barcode** erstellt und die **Position des Barcode‑Textes** mit Aspose.BarCode präzise steuert. Experimentieren Sie mit anderen `CodeLocation`‑Werten, Schriftarteinstellungen und Farboptionen, um die Designanforderungen Ihrer Anwendung zu erfüllen.

---

**Zuletzt aktualisiert:** 2026-05-04  
**Getestet mit:** Aspose.BarCode for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}