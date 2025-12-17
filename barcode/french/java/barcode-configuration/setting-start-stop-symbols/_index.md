---
date: 2025-12-17
description: Apprenez à créer une image de code-barres en Java et à définir les symboles
  à l’aide d’Aspose.BarCode. Ce guide étape par étape vous montre comment générer
  un code-barres Codabar avec des symboles de début/fin personnalisés.
linktitle: Setting Start and Stop Symbols
second_title: Aspose.BarCode Java API
title: Créer une image de code-barres Java – Définir les symboles de début et de fin
url: /fr/java/barcode-configuration/setting-start-stop-symbols/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une image de code‑barres Java – Définir les symboles de début et de fin

## Introduction

Dans ce tutoriel complet, vous **create barcode image java** avec Aspose.BarCode for Java et apprendrez **comment définir les symboles** pour les codes‑barres Codabar. Que vous construisiez un système de point de vente, une application logistique ou toute solution nécessitant une génération fiable de codes‑barres, la personnalisation des symboles de début et de fin vous donne un contrôle total sur le format du code‑barres. Nous parcourrons chaque étape, expliquerons pourquoi chaque paramètre est important et vous montrerons comment produire une image PNG prête à l’emploi.

## Quick Answers
- **What library creates barcode images in Java?** Aspose.BarCode for Java.
- **Can I customize start/stop symbols?** Yes, using `setCodabarStartSymbol` and `setCodabarStopSymbol`.
- **Which barcode type is used in this example?** CODABAR.
- **Do I need a license for production?** A commercial license is required for non‑trial use.
- **What output format is generated?** PNG image saved to disk.

## What is “create barcode image java”?

Générer une image de code‑barres en Java signifie produire programmétiquement une représentation visuelle (généralement PNG, JPG ou BMP) d’une symbologie de code‑barres qui peut être lue par des lecteurs standards. Aspose.BarCode fournit une API fluide qui abstrait les détails d’encodage de bas niveau, vous permettant de vous concentrer sur la logique métier.

## Why use Aspose.BarCode to generate barcode with Aspose?

Aspose.BarCode offre :
- **Broad symbology support** (including CODABAR, QR, DataMatrix, etc.).
- **Fine‑grained control** over appearance, size, and encoding options.
- **Cross‑platform compatibility** with any Java runtime.
- **No external dependencies**, making deployment straightforward.

## Prerequisites

Avant de commencer, assurez‑vous d’avoir :

1. **Java Development Kit (JDK)** – Installez le dernier JDK depuis [Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2. **Aspose.BarCode for Java library** – Téléchargez‑le depuis le [download link](https://releases.aspose.com/barcode/java/).

Disposer de ces éléments vous garantit de pouvoir **generate barcode image java** sans aucun composant manquant.

## Import Packages

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.CodabarSymbol;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Step‑by‑Step Guide

### Step 1: Define the Document Directory

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Remplacez `"Your Document Directory"` par le chemin absolu ou relatif où vous souhaitez enregistrer l’image du code‑barres.

### Step 2: Create Barcode Generator Instance

```java
// Create instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "12345678");
```

Ici nous indiquons à Aspose.BarCode d’utiliser la symbologie **CODABAR** et la chaîne de données `"12345678"`.

### Step 3: Set Codabar Start Symbol

```java
// Set the Codabar start symbol to A
generator.getParameters().getBarcode().getCodabar().setCodabarStartSymbol(CodabarSymbol.A);
```

La méthode `setCodabarStartSymbol` vous permet **comment définir les symboles** pour le caractère de début. Dans ce cas nous choisissons `A`.

### Step 4: Set Codabar Stop Symbol

```java
// Set the Codabar stop symbol to D
generator.getParameters().getBarcode().getCodabar().setCodabarStopSymbol(CodabarSymbol.D);
```

De même, `setCodabarStopSymbol` définit le caractère de fin. L’utilisation de `D` complète le format CODABAR requis par de nombreux systèmes hérités.

### Step 5: Save the Generated Image

```java
// Save the image to disk in PNG format
generator.save(dataDir + "startAndStopSymbols.png");
```

L’appel `save` écrit le code‑barres dans un fichier PNG nommé **startAndStopSymbols.png** dans le répertoire que vous avez spécifié précédemment.

### Common Pitfalls & Tips

- **Incorrect directory path** – Ensure `dataDir` ends with a file separator (`/` or `\`) or concatenate using `Paths.get`.
- **Unsupported start/stop symbols** – CODABAR only supports A, B, C, D as start/stop symbols. Using any other value will raise an exception.
- **License not applied** – In trial mode the generated image may contain a watermark. Apply your license before deploying to production.

## Conclusion

Vous avez maintenant appris comment **create barcode image java** et précisément **comment définir les symboles** pour un code‑barres Codabar à l’aide d’Aspose.BarCode. Cette technique vous offre la flexibilité nécessaire pour répondre aux spécifications de code‑barres propres à chaque secteur tout en conservant un code propre et maintenable.

Explorez des options de personnalisation supplémentaires — comme changer les couleurs, ajouter du texte lisible par l’homme, ou passer à d’autres symbologies—en consultant la documentation officielle de l’API à l’adresse [documentation](https://reference.aspose.com/barcode/java/).

## Frequently Asked Questions

### Can I use Aspose.BarCode for Java in a commercial project?
Yes, you can. For commercial usage, consider purchasing a license [here](https://purchase.aspose.com/buy).

### Is there a free trial available?
Yes, you can explore a free trial version [here](https://releases.aspose.com/).

### How can I get support for Aspose.BarCode for Java?
Visit the Aspose.BarCode forum [here](https://forum.aspose.com/c/barcode/13) for any support or queries.

### How do I obtain a temporary license?
If needed, you can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).

### Are there more barcode symbologies supported by Aspose.BarCode for Java?
Yes, Aspose.BarCode supports a wide range of barcode symbologies. Refer to the documentation for a complete list.

**Additional Q&A**

**Q: What image formats can I export besides PNG?**  
A: Aspose.BarCode supports PNG, JPEG, BMP, GIF, and TIFF. Use the appropriate file extension in the `save` method.

**Q: Can I generate barcode images in memory without writing to disk?**  
A: Yes, call `generator.save(OutputStream)` to write directly to a stream, useful for web responses.

**Q: Does the library work on Android?**  
A: The Java version is compatible with Android, but you must include the required dependencies manually.

---

**Last Updated:** 2025-12-17  
**Tested With:** Aspose.BarCode for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}