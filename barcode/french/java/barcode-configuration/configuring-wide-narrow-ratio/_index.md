---
date: 2026-08-12
description: Découvrez comment améliorer la lisibilité du code-barres en personnalisant
  le wide‑narrow ratio CODE_128 en Java avec Aspose.BarCode, et générer des images
  PNG efficacement. Suivez notre tutoriel pas à pas de génération de code-barres en
  Java.
keywords:
- improve barcode readability
- customize code128 barcode
- barcode generation tutorial java
- step by step barcode
lastmod: 2026-08-12
linktitle: Configuration du wide‑narrow ratio
og_description: Découvrez comment améliorer la lisibilité du code-barres en personnalisant
  le wide‑narrow ratio CODE_128 en Java avec Aspose.BarCode. Ce tutoriel pas à pas
  vous montre comment générer rapidement des codes-barres PNG.
og_image_alt: Guide to creating CODE_128 barcode with custom wide‑narrow ratio in
  Java
og_title: Améliorer la lisibilité du code-barres avec le wide‑narrow ratio CODE_128
  (58 caractères)
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Learn how to improve barcode readability by customizing the CODE_128
    wide‑narrow ratio in Java using Aspose.BarCode, and generate PNG images efficiently.
    Follow our step‑by‑step barcode generation tutorial Java.
  headline: Improve barcode readability with CODE_128 wide‑narrow ratio
  type: TechArticle
- description: Learn how to improve barcode readability by customizing the CODE_128
    wide‑narrow ratio in Java using Aspose.BarCode, and generate PNG images efficiently.
    Follow our step‑by‑step barcode generation tutorial Java.
  name: Improve barcode readability with CODE_128 wide‑narrow ratio
  steps:
  - name: set document directory
    text: Make sure the directory exists and you have write permissions; this is where
      the **saved barcode image** file will be placed.
  - name: instantiate barcode object
    text: The `BarcodeGenerator` class creates barcode images based on the specified
      symbology and encoding options. Here we **create a CODE_128 barcode** by passing
      `EncodeTypes.CODE_128` to the constructor.
  - name: set wide‑narrow ratio
    text: '`setWideNarrowRatio` sets the proportion between wide and narrow bars for
      the generated barcode. The `setWideNarrowRatio` method lets you fine‑tune the
      visual spacing. A value of `3.0f` means the wide bar is three times the width
      of a narrow bar, which falls within the optimal 2.0‑3.0 range for most'
  - name: save image to disk
    text: Calling `save` will **generate a barcode image** and store it as a PNG file,
      completing the **save barcode image** step.
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode works seamlessly with Spring, Java EE, Android, and
      other Java environments.
    question: Can I use Aspose.BarCode with other Java frameworks?
  - answer: Change the symbology type in the `BarcodeGenerator` constructor, for example
      `EncodeTypes.QR` for QR codes.
    question: How can I generate barcodes with different symbologies?
  - answer: Yes, you can access the free trial version on the [Aspose.BarCode free
      trial page](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.BarCode?
  - answer: Refer to the documentation on the [Aspose.BarCode Java API documentation](https://reference.aspose.com/barcode/java/).
    question: Where can I find detailed documentation for Aspose.BarCode?
  - answer: Visit the Aspose.BarCode community forum at [Aspose.BarCode community
      forum](https://forum.aspose.com/c/barcode/13) for support and community discussions.
    question: How to get support for Aspose.BarCode?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- barcode readability
- Aspose.BarCode
- Java barcode tutorial
title: Améliorer la lisibilité du code-barres avec le wide‑narrow ratio CODE_128
url: /fr/java/barcode-configuration/configuring-wide-narrow-ratio/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Améliorer la lisibilité du code-barres avec le rapport large‑étroit CODE_128

## Introduction

Si vous devez **améliorer la lisibilité du code-barres** pour les étiquettes d'inventaire, les balises d'expédition ou toute application utilisant CODE_128, ajuster le rapport large‑étroit est la technique la plus efficace. Dans ce tutoriel, nous parcourrons un processus de création de **code-barres étape par étape** en utilisant Aspose.BarCode pour Java, en vous montrant comment configurer le rapport, **générer des images PNG de code-barres**, et **enregistrer l'image du code-barres** sur le disque. Vous verrez également pourquoi le rapport est important pour les performances du scanner et comment le régler finement pour votre environnement d'impression spécifique.

## Réponses rapides
- **Qu'est‑ce que le rapport large‑étroit ?** Il contrôle la largeur relative des barres larges par rapport aux barres étroites dans un code‑barres.  
- **Quelle symbologie prend en charge le réglage du rapport ?** La plupart des symbologies 1‑D, y compris CODE_128, vous permettent de définir un rapport personnalisé.  
- **Ai‑je besoin d'une licence ?** Une version d'essai gratuite est disponible, mais une licence commerciale est requise pour une utilisation en production.  
- **Puis‑je générer une image de code‑barres au format PNG ?** Oui—utilisez `generator.save(...)` pour générer des images PNG de code‑barres.  
- **Le code est‑il compatible avec Java 8+ ?** Absolument ; Aspose.BarCode fonctionne avec toutes les versions modernes de Java.

## Prérequis

Avant de plonger dans le code, assurez‑vous d'avoir les éléments suivants :

- Java Development Kit (JDK) installé sur votre machine.  
- Bibliothèque Aspose.BarCode pour Java. Téléchargez‑la depuis le [download link](https://releases.aspose.com/barcode/java/).

## Importer les packages

Pour commencer, importez la classe essentielle d'Aspose.BarCode dans votre projet.  
`BarcodeGenerator` est la classe principale utilisée pour générer des images de code‑barres avec la symbologie et les options spécifiées.  

```java
// Import Aspose.BarCode library
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Qu'est‑ce que le rapport large‑étroit et pourquoi l'ajuster ?

Le rapport large‑étroit définit combien de fois une barre « large » est plus large qu'une barre « étroite ». Ajuster ce rapport améliore la compatibilité des scanners (la plupart des scanners lisent mieux avec des rapports compris entre 2,0 et 3,0), compense les limitations de DPI de l'imprimante, et vous permet d'adapter le style visuel d'une marque sans sacrifier la fiabilité.

## Comment améliorer la lisibilité du code‑barres en créant un code‑barres CODE_128 avec un rapport large‑étroit en Java

Commencez par ajouter la bibliothèque Aspose.BarCode à votre projet Java, puis créez une instance de `BarcodeGenerator` en spécifiant `EncodeTypes.CODE_128`. Configurez le générateur avec le rapport large‑étroit souhaité à l'aide de `setWideNarrowRatio`, ajustez éventuellement d'autres paramètres visuels, et enfin appelez `save` pour écrire le code‑barres dans un fichier PNG. Ce flux de travail concis garantit une qualité de code‑barres constante et améliore les taux de lecture des scanners sur divers appareils.

### Étape 1 : définir le répertoire du document

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Assurez‑vous que le répertoire existe et que vous disposez des permissions d'écriture ; c'est ici que le fichier d'**image de code‑barres enregistrée** sera placé.

### Étape 2 : instancier l'objet code‑barres

La classe `BarcodeGenerator` crée des images de code‑barres basées sur la symbologie et les options d'encodage spécifiées.  
```java
// Instantiate barcode object
// Create an instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

Ici, nous **créons un code‑barres CODE_128** en passant `EncodeTypes.CODE_128` au constructeur.

### Étape 3 : définir le rapport large‑étroit

`setWideNarrowRatio` définit la proportion entre les barres larges et étroites pour le code‑barres généré.  
```java
// Set the wide to narrow ratio for the barcode
generator.getParameters().getBarcode().setWideNarrowRatio(3.0f);
```

La méthode `setWideNarrowRatio` vous permet d'ajuster finement l'espacement visuel. Une valeur de `3.0f` signifie que la barre large fait trois fois la largeur d'une barre étroite, ce qui se situe dans la plage optimale de 2,0‑3,0 pour la plupart des scanners.

### Étape 4 : enregistrer l'image sur le disque

```java
// Save the image to disk in PNG format
generator.save(dataDir + "wideNarrowRatio.png");
```

Appeler `save` **générera une image de code‑barres** et la stockera sous forme de fichier PNG, complétant l'étape d'**enregistrement de l'image du code‑barres**.

## Pourquoi ajuster le rapport large‑étroit ?

Ajuster le rapport large‑étroit améliore la compatibilité des scanners car la plupart des scanners industriels lisent mieux lorsque le rapport se situe entre 2,0 et 3,0. Cela améliore également la qualité d'impression en compensant les résolutions d'imprimante de 150–300 dpi, réduisant la distorsion des barres. De plus, le rapport permet aux entreprises d'aligner l'esthétique du code‑barres avec les directives de marque tout en maintenant des performances de lecture fiables.

## Problèmes courants et solutions

| Problème | Raison | Solution |
|----------|--------|----------|
| Le code‑barres apparaît déformé | Rapport trop élevé/bas pour l'imprimante | Ajustez la valeur passée à `setWideNarrowRatio` (par ex., 2.0‑2.5). |
| Fichier non créé | Chemin `dataDir` invalide ou permissions insuffisantes | Vérifiez le chemin du répertoire et assurez‑vous que l'application dispose d'un accès en écriture. |
| Le scanner ne peut pas lire le code‑barres | Rapport hors de la plage recommandée pour la symbologie | Utilisez des rapports standards (2.0‑3.0) ou testez avec le scanner cible. |

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.BarCode avec d'autres frameworks Java ?**  
R : Oui, Aspose.BarCode fonctionne parfaitement avec Spring, Java EE, Android et d'autres environnements Java.

**Q : Comment puis‑je générer des codes‑barres avec différentes symbologies ?**  
R : Changez le type de symbologie dans le constructeur `BarcodeGenerator`, par exemple `EncodeTypes.QR` pour les codes QR.

**Q : Existe‑t‑il une version d'essai disponible pour Aspose.BarCode ?**  
R : Oui, vous pouvez accéder à la version d'essai gratuite sur la [page d'essai gratuit d'Aspose.BarCode](https://releases.aspose.com/).

**Q : Où puis‑je trouver la documentation détaillée d'Aspose.BarCode ?**  
R : Consultez la documentation sur la [documentation de l'API Java d'Aspose.BarCode](https://reference.aspose.com/barcode/java/).

**Q : Comment obtenir du support pour Aspose.BarCode ?**  
R : Visitez le forum communautaire d'Aspose.BarCode à l'adresse [forum communautaire Aspose.BarCode](https://forum.aspose.com/c/barcode/13) pour le support et les discussions communautaires.

---

**Dernière mise à jour :** 2026-08-12  
**Testé avec :** Aspose.BarCode for Java 24.11 (latest at time of writing)  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Générer un code‑barres Java – Définir la résolution d'image avec Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)
- [Détecter l'orientation du code‑barres en Java avec Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/configuring-barcode-orientation/)
- [Comment créer des images de code128 en Java avec Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}