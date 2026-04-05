---
date: 2026-02-17
description: Apprenez à utiliser Aspose Barcode Java pour créer des images de codes-barres,
  définir les symboles de début et de fin CODABAR, et générer des fichiers PNG sans
  filigrane.
linktitle: Setting Start and Stop Symbols
second_title: Aspose.BarCode Java API
title: Aspose Barcode Java – Créer une image de code‑barres avec les symboles de début/fin
url: /fr/java/barcode-configuration/setting-start-stop-symbols/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Barcode Java – Créer une image de code‑barres avec les symboles de début/fin

## Introduction

Dans ce tutoriel complet, vous **create barcode image java** des fichiers avec **Aspose Barcode Java** et apprenez **comment définir les symboles** pour les codes‑barres Codabar. Que vous construisiez un système de point de vente, une application logistique ou toute solution nécessitant une génération fiable de codes‑barres, la personnalisation des symboles de début et de fin vous donne un contrôle total sur le format du code‑barres. Nous parcourrons chaque étape, expliquerons pourquoi chaque paramètre est important et vous montrerons comment produire une image PNG prête à l’emploi — sans le filigrane d’essai.

## Quick Answers
- **Quelle bibliothèque crée des images de code‑barres en Java ?** Aspose.BarCode for Java.  
- **Puis‑je personnaliser les symboles de début/fin ?** Oui, en utilisant `setCodabarStartSymbol` et `setCodabarStopSymbol`.  
- **Quel type de code‑barres est utilisé dans cet exemple ?** CODABAR.  
- **Ai‑je besoin d’une licence pour la production ?** Une licence commerciale est requise pour une utilisation non‑essai.  
- **Quel format de sortie est généré ?** Image PNG enregistrée sur le disque.

## Qu’est‑ce que Aspose Barcode Java ?

Aspose Barcode Java est une bibliothèque puissante, indépendante de toute dépendance, qui vous permet de générer programmatiquement un large éventail de symbologies de codes‑barres. Elle abstrait la logique d’encodage de bas niveau, vous permettant de vous concentrer sur les règles métier tout en garantissant que la sortie respecte les normes de l’industrie.

## Pourquoi utiliser Aspose Barcode Java pour la génération de codes‑barres sans filigrane ?

- **Pas de filigrane en production** – une fois une licence valide appliquée, les images sont propres.  
- **Prise en charge étendue des symbologies** – des codes 1D classiques comme CODABAR aux codes 2D tels que QR et DataMatrix.  
- **Contrôle fin** – vous pouvez définir les symboles de début/fin, les couleurs, les tailles, et même générer des images directement vers des flux pour les applications web.  
- **Multiplateforme** – fonctionne sur n’importe quel runtime Java, y compris Android (avec gestion manuelle des dépendances).

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

1. **Java Development Kit (JDK)** – Installez le dernier JDK depuis [Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).  
2. **Aspose.BarCode for Java library** – Téléchargez‑la depuis le [download link](https://releases.aspose.com/barcode/java/).

Disposer de ces éléments vous garantit de pouvoir **generate barcode image java** sans aucun composant manquant.

## Import Packages

Dans votre projet Java, importez les classes nécessaires pour travailler avec Aspose.BarCode :

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.CodabarSymbol;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Step‑by‑Step Guide

### Étape 1 : Définir le répertoire du document

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Remplacez `"Your Document Directory"` par le chemin absolu ou relatif où vous souhaitez enregistrer l’image du code‑barres. N’oubliez pas de terminer le chemin avec le séparateur de fichiers approprié (`/` ou `\`) ou d’utiliser `Paths.get` pour une gestion indépendante de la plateforme.

### Étape 2 : Créer une instance du générateur de code‑barres

```java
// Create instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "12345678");
```

Ici, nous indiquons à Aspose.BarCode d’utiliser la symbologie **CODABAR** et la chaîne de données `"12345678"`.

### Étape 3 : Définir le symbole de début Codabar

```java
// Set the Codabar start symbol to A
generator.getParameters().getBarcode().getCodabar().setCodabarStartSymbol(CodabarSymbol.A);
```

La méthode `setCodabarStartSymbol` vous permet de **définir les symboles du code‑barres** pour le caractère de début. Dans ce cas, nous choisissons `A`.

### Étape 4 : Définir le symbole de fin Codabar

```java
// Set the Codabar stop symbol to D
generator.getParameters().getBarcode().getCodabar().setCodabarStopSymbol(CodabarSymbol.D);
```

De même, `setCodabarStopSymbol` définit le caractère de fin. L’utilisation de `D` complète le format CODABAR requis par de nombreux systèmes hérités.

### Étape 5 : Enregistrer l’image générée

```java
// Save the image to disk in PNG format
generator.save(dataDir + "startAndStopSymbols.png");
```

L’appel `save` écrit le code‑barres dans un fichier PNG nommé **startAndStopSymbols.png** dans le répertoire que vous avez spécifié précédemment.

## Common Pitfalls & Tips

- **Chemin de répertoire incorrect** – Assurez‑vous que `dataDir` se termine par un séparateur de fichiers (`/` ou `\`) ou concaténez‑le avec `Paths.get`.  
- **Symboles de début/fin non pris en charge** – CODABAR ne prend en charge que `A`, `B`, `C`, `D` comme symboles de début/fin. Toute autre valeur déclenchera une exception.  
- **Licence non appliquée** – En mode essai, l’image générée peut contenir un filigrane. Appliquez votre licence avant le déploiement en production pour obtenir **barcode generation without watermark**.

## Frequently Asked Questions

### Puis‑je utiliser Aspose.BarCode pour Java dans un projet commercial ?
Oui, vous pouvez. Pour une utilisation commerciale, envisagez d’acheter une licence [ici](https://purchase.aspose.com/buy).

### Une version d’essai gratuite est‑elle disponible ?
Oui, vous pouvez explorer une version d’essai gratuite [ici](https://releases.aspose.com/).

### Comment obtenir du support pour Aspose.BarCode pour Java ?
Visitez le forum Aspose.BarCode [ici](https://forum.aspose.com/c/barcode/13) pour tout support ou question.

### Comment obtenir une licence temporaire ?
Si besoin, vous pouvez acquérir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

### D’autres symbologies de codes‑barres sont‑elles prises en charge par Aspose.BarCode pour Java ?
Oui, Aspose.BarCode prend en charge un large éventail de symbologies de codes‑barres. Consultez la documentation pour la liste complète.

## Additional Q&A (AI‑Friendly)

**Q :** Quels formats d’image puis‑je exporter en plus du PNG ?  
**A :** Aspose.BarCode prend en charge PNG, JPEG, BMP, GIF et TIFF. Utilisez l’extension de fichier appropriée dans la méthode `save`.

**Q :** Puis‑je générer des images de code‑barres en mémoire sans les écrire sur le disque ?  
**A :** Oui, appelez `generator.save(OutputStream)` pour écrire directement dans un flux, ce qui est idéal pour les réponses web.

**Q :** La bibliothèque fonctionne‑t‑elle sur Android ?  
**A :** La version Java est compatible avec Android, mais vous devez inclure manuellement les dépendances requises.

## Conclusion

Vous avez maintenant appris comment **create barcode image java** des fichiers et définir précisément **les symboles du code‑barres** pour un code‑barres Codabar en utilisant **Aspose Barcode Java**. Cette technique vous offre la flexibilité nécessaire pour répondre aux spécifications de codes‑barres propres à chaque secteur tout en gardant votre code propre et maintenable. Explorez d’autres options de personnalisation — comme changer les couleurs, ajouter du texte lisible par l’homme, ou passer à d’autres symbologies — en consultant la documentation officielle de l’API à l’adresse [documentation](https://reference.aspose.com/barcode/java/).

---

**Last Updated:** 2026-02-17  
**Tested With:** Aspose.BarCode for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}