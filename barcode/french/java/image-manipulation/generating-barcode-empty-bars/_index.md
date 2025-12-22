---
date: 2025-12-22
description: Apprenez à créer une image de code‑barres avec des barres vides en utilisant
  Aspose.BarCode pour Java. Cet exemple de génération de code‑barres étape par étape
  vous aide à générer rapidement du code‑barres Java.
linktitle: Generating Barcode with Empty Bars
second_title: Aspose.BarCode Java API
title: Comment créer une image de code-barres avec des barres vides en Java
url: /fr/java/image-manipulation/generating-barcode-empty-bars/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer une image de code-barres avec des barres vides en Java

## Introduction

Dans les applications Java modernes, la capacité de **créer une image de code-barres** à la volée est une fonctionnalité précieuse pour la gestion des stocks, les systèmes de billetterie et de nombreux autres scénarios d'entreprise. Aspose.BarCode for Java fournit une API puissante et facile à utiliser qui vous permet de générer des codes-barres de haute qualité en quelques lignes de code seulement. Dans ce tutoriel, nous parcourrons un processus de création de **code‑barres étape par étape** qui produit un code-barres avec des barres vides (non remplies), parfait pour les conceptions nécessitant un aspect creux.

## Réponses rapides
- **Que signifie « barres vides » ?** Les barres sont rendues sans le remplissage solide par défaut, donnant une apparence creuse.  
- **Quel type de code-barres est utilisé ?** Code 128 (une symbologie linéaire largement prise en charge).  
- **Ai‑je besoin d’une licence pour l’essayer ?** Un essai gratuit est disponible ; une licence est requise pour une utilisation en production.  
- **Quels formats de sortie sont pris en charge ?** PNG, JPEG, BMP, GIF, TIFF, et plus.  
- **Est‑ce compatible avec toutes les versions de Java ?** Oui, la bibliothèque fonctionne avec Java 8 et versions ultérieures.  

## Qu’est‑ce que créer une image de code‑barres ?

Créer une image de code‑barres signifie convertir une chaîne de données en une représentation visuelle lisible par les scanners. L’image résultante peut être enregistrée au format PNG, JPEG ou d’autres formats courants et intégrée dans des PDF, imprimée sur des étiquettes ou affichée dans une interface utilisateur.

## Pourquoi utiliser la bibliothèque Aspose.BarCode Java ?

- **Ensemble de fonctionnalités riche** – prend en charge plus de 50 symbologies de code‑barres, y compris Code 128, QR, DataMatrix, et plus.  
- **Contrôle fin** – des propriétés telles que `FilledBars`, les couleurs, les marges et la taille de l’image sont facilement configurables.  
- **Aucune dépendance externe** – un seul fichier JAR gère tout, simplifiant le déploiement.  
- **Documentation complète** – des exemples, la référence API et les forums vous aident à prendre rapidement le rythme.  

## Prérequis

Avant de nous lancer dans le processus de génération de code‑barres, assurez‑vous que les prérequis suivants sont en place :

1. **Environnement de développement Java** – Assurez‑vous d’avoir Java 8+ installé ainsi qu’un IDE ou un outil de construction compatible.  
2. **Bibliothèque Aspose.BarCode for Java** – Téléchargez et installez la bibliothèque Aspose.BarCode for Java depuis la [page de téléchargement](https://releases.aspose.com/barcode/java/).  
3. **Répertoire de documents** – Créez un répertoire sur votre système pour stocker l’image de code‑barres générée.  

## Importer les packages

Dans votre projet Java, importez les packages nécessaires pour travailler avec Aspose.BarCode :

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Comment créer une image de code‑barres avec des barres vides

### Étape 1 : Configurer le répertoire de ressources

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Remplacez `"Your Document Directory"` par le chemin réel où vous souhaitez enregistrer le fichier de sortie.

### Étape 2 : Créer une instance du générateur de code‑barres (Code128 Barcode Java)

```java
// Create an instance of BarcodeGenerator and initialize it with CodeText and Symbology
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

Ici, nous utilisons la symbologie **Code 128**—l’un des codes‑barres linéaires les plus populaires—ce qui fait de cet exemple un classique **code128 barcode java**.

### Étape 3 : Définir la propriété FilledBars sur false

```java
// Set the FilledBars property to false
generator.getParameters().getBarcode().setFilledBars(false);
```

Définir `FilledBars` sur `false` indique à Aspose.BarCode de rendre les barres comme des formes vides (creuses) au lieu de blocs solides.

### Étape 4 : Enregistrer l’image du code‑barres

```java
// Save the resultant barcode image on disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

L’image est enregistrée au format PNG, mais vous pouvez modifier l’énumération `BarCodeImageFormat` pour produire du JPEG, BMP ou d’autres types pris en charge.

Répétez ces étapes dans votre application Java pour créer facilement des fichiers **create barcode image** avec des barres vides en utilisant Aspose.BarCode for Java.

## Conclusion

En conclusion, ce tutoriel vous a guidé à travers un processus de création de **code‑barres étape par étape** montrant comment **create barcode image** avec des barres vides en Java. Grâce à son API intuitive et à ses nombreuses options de personnalisation, Aspose.BarCode simplifie l’intégration des codes‑barres, en faisant un atout précieux pour les développeurs qui ont besoin d’une **java barcode library** fiable.

## FAQ

### Aspose.BarCode est‑il compatible avec tous les environnements de développement Java ?

Oui, Aspose.BarCode est conçu pour s’intégrer parfaitement à divers environnements de développement Java.

### Puis‑je personnaliser l’apparence du code‑barres généré ?

Absolument ! Aspose.BarCode offre de nombreuses options de personnalisation, vous permettant d’adapter le code‑barres à vos besoins spécifiques.

### Une version d’essai est‑elle disponible pour Aspose.BarCode ?

Oui, vous pouvez explorer les fonctionnalités d’Aspose.BarCode en obtenant un essai gratuit [ici](https://releases.aspose.com/).

### Comment obtenir du support pour Aspose.BarCode ?

Pour toute question ou assistance, consultez le [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

### Où puis‑je trouver la documentation détaillée d’Aspose.BarCode ?

La documentation complète est disponible [ici](https://reference.aspose.com/barcode/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-22  
**Tested With:** Aspose.BarCode Java 24.11 (latest)  
**Author:** Aspose