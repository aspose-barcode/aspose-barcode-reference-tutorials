---
date: 2026-08-28
description: Apprenez à créer une image de code-barres Java avec Aspose Barcode Java,
  à définir les symboles de début et de fin CODABAR, et à générer des fichiers PNG
  sans filigrane.
keywords:
- create barcode image java
- barcode generation without watermark
- codabar start stop symbols
lastmod: 2026-08-28
linktitle: Définir les symboles de début et de fin
og_description: Créer une image de code-barres Java avec Aspose Barcode Java. Ce guide
  montre comment définir les symboles de début/fin CODABAR et exporter des PNG sans
  filigrane.
og_image_alt: 'Aspose Barcode Java tutorial: create barcode image with start/stop
  symbols'
og_title: Créer une image de code-barres Java – guide des symboles de début/fin
schemas:
- author: Aspose
  dateModified: '2026-08-28'
  description: Learn how to create barcode image java with Aspose Barcode Java, set
    CODABAR start and stop symbols, and generate PNG files without watermarks.
  headline: Aspose Barcode Java – Create barcode image with start/stop symbols
  type: TechArticle
- questions:
  - answer: Aspose.BarCode for Java.
    question: What library creates barcode images in Java?
  - answer: Yes, using `setCodabarStartSymbol` and `setCodabarStopSymbol`.
    question: Can I customize start/stop symbols?
  - answer: CODABAR.
    question: Which barcode type is used in this example?
  - answer: A commercial license is required for non‑trial use.
    question: Do I need a license for production?
  - answer: PNG image saved to disk.
    question: What output format is generated?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- barcode generation
- Aspose.BarCode
- Java barcode tutorial
title: Aspose Barcode Java – Créer une image de code-barres avec les symboles de début/fin
url: /fr/java/barcode-configuration/setting-start-stop-symbols/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Barcode Java – Créer une image de code-barres avec les symboles de début/fin

## Introduction

Dans ce tutoriel complet, vous allez **créer des images de code-barres java** avec Aspose Barcode Java et apprendre **comment définir les symboles de début et de fin** pour les codes-barres CODABAR. Que vous construisiez un terminal point de vente, un système de gestion d'entrepôt, ou toute application nécessitant une génération fiable de codes-barres, la personnalisation de ces symboles vous permet de répondre aux spécifications héritées tout en gardant le code propre et maintenable. Nous parcourrons chaque étape, expliquerons pourquoi chaque paramètre est important, et vous montrerons comment produire une image PNG qui ne contient aucun filigrane d'évaluation.

## Réponses rapides
- **Quelle bibliothèque crée des images de code-barres en Java ?** Aspose.BarCode for Java.  
- **Puis-je personnaliser les symboles de début/fin ?** Oui, en utilisant `setCodabarStartSymbol` et `setCodabarStopSymbol`.  
- **Quel type de code-barres est utilisé dans cet exemple ?** CODABAR.  
- **Ai‑je besoin d’une licence pour la production ?** Une licence commerciale est requise pour une utilisation hors période d'essai.  
- **Quel format de sortie est généré ?** Image PNG enregistrée sur le disque.

## Qu’est‑ce qu’Aspose Barcode Java ?

Aspose Barcode Java est une **bibliothèque Java indépendante des dépendances qui génère plus de 70 symbologies de codes-barres**, des codes 1D classiques comme le CODABAR aux codes 2D modernes tels que QR et DataMatrix. Elle gère tout l’encodage de bas niveau, vous permettant de vous concentrer sur la logique métier tout en garantissant la conformité aux normes de l'industrie.

## Pourquoi utiliser Aspose Barcode Java pour la génération de codes-barres sans filigrane ?

Chargez d'abord votre licence, et la bibliothèque produit des images nettes—sans superposition « Aspose Evaluation ». Elle offre également un **contrôle granulaire** (symboles de début/fin, couleurs, tailles) et une **compatibilité multiplateforme** (tout environnement Java, y compris Android). Avec la prise en charge de **plus de 50 formats de sortie** et la capacité de diffuser les images directement vers les réponses HTTP, c’est le choix privilégié pour la création de codes-barres à haut débit et de qualité production.

## Prérequis

Avant de commencer, assurez-vous d'avoir :

1. **Java Development Kit (JDK)** – Installez le dernier JDK depuis [Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).  
2. **Bibliothèque Aspose.BarCode for Java** – Téléchargez‑la depuis le [lien de téléchargement](https://releases.aspose.com/barcode/java/).

Disposer de ces éléments garantit que vous pouvez **créer des images de code-barres java** sans composants manquants.

## Importer les packages

Les importations suivantes vous donnent accès aux classes principales nécessaires à la génération de codes-barres :

L’énumération `CodabarSymbol` définit les caractères de début/fin autorisés pour les codes‑barres CODABAR.  

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.CodabarSymbol;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Guide étape par étape

### Comment définir le dossier de sortie pour l’image du code‑barres ?

Spécifiez le dossier où le fichier PNG sera écrit. L’utilisation de `Paths.get` rend le code portable sur Windows, macOS et Linux.

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

### Comment créer un générateur de code‑barres pour CODABAR ?

La classe `BarcodeGenerator` crée une image de code‑barres pour une symbologie et des données données.  

Instanciez `BarcodeGenerator` avec la symbologie CODABAR et la chaîne de données que vous souhaitez encoder.

```java
// Create instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "12345678");
```

### Comment définir le symbole de début CODABAR ?

`setCodabarStartSymbol` définit le caractère qui marque le début d’un code‑barres CODABAR.  

Appelez `setCodabarStartSymbol` et passez l’un des caractères pris en charge (`A`, `B`, `C`, `D`). Dans cet exemple, nous utilisons `A`.

```java
// Set the Codabar start symbol to A
generator.getParameters().getBarcode().getCodabar().setCodabarStartSymbol(CodabarSymbol.A);
```

### Comment définir le symbole de fin CODABAR ?

`setCodabarStopSymbol` définit le caractère qui marque la fin d’un code‑barres CODABAR.  

Utilisez `setCodabarStopSymbol` avec le caractère de fin correspondant—`D` dans ce cas.

```java
// Set the Codabar stop symbol to D
generator.getParameters().getBarcode().getCodabar().setCodabarStopSymbol(CodabarSymbol.D);
```

### Comment enregistrer le code‑barres généré en fichier PNG ?

L’énumération `SaveFormat` spécifie le format de fichier pour enregistrer l’image du code‑barres.  

Appelez la méthode `save`, en fournissant le nom complet du fichier et la valeur d’énumération `SaveFormat.Png`. L’image est écrite sans aucun filigrane une fois qu’une licence valide est appliquée.

```java
// Save the image to disk in PNG format
generator.save(dataDir + "startAndStopSymbols.png");
```

## Pièges courants et astuces

La classe `License` charge un fichier de licence Aspose pour activer le mode complet.

- **Chemin de répertoire incorrect** – Assurez‑vous que `dataDir` se termine par le séparateur de fichiers approprié ou construisez le chemin avec `Paths.get`.  
- **Caractères de début/fin non pris en charge** – CODABAR accepte uniquement `A`, `B`, `C` ou `D`. Fournir une autre valeur déclenche une `IllegalArgumentException`.  
- **Licence non appliquée** – En mode d’essai, la sortie contient un filigrane. Chargez votre fichier de licence avec `License license = new License(); license.setLicense("Aspose.Total.Java.lic");` avant de créer le générateur pour éviter cela.  
- **Génération à grande échelle** – Lors de la génération de milliers de codes‑barres, réutilisez une seule instance de `BarcodeGenerator` et ne changez que le texte du code afin de réduire la surcharge de création d’objets.

## Questions fréquemment posées

### Puis‑je utiliser Aspose.BarCode pour Java dans un projet commercial ?

Oui. Achetez une licence commerciale [purchase a commercial license](https://purchase.aspose.com/buy) pour supprimer le filigrane d’évaluation et obtenir un support technique complet.

### Une version d’essai gratuite est‑elle disponible ?

Absolument. Téléchargez la version d’essai [download the trial version](https://releases.aspose.com/) pour évaluer toutes les fonctionnalités avant d’acheter.

### Comment obtenir du support pour Aspose.BarCode pour Java ?

Visitez le forum Aspose.BarCode [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) pour obtenir de l’aide de la communauté, ou ouvrez un ticket de support via le portail de votre compte Aspose.

### Comment obtenir une licence temporaire pour les tests ?

Vous pouvez demander une licence temporaire de 30 jours [request a temporary 30‑day license](https://purchase.aspose.com/temporary-license/). Cela vous permet d’effectuer des tests similaires à la production sans achat complet.

### Quelles autres symbologies de codes‑barres Aspose.BarCode prend‑il en charge ?

La bibliothèque prend en charge **plus de 70 symbologies**, y compris Code128, EAN‑13, QR, DataMatrix, PDF417, et bien d’autres. Consultez la liste complète dans la documentation officielle.

## Questions supplémentaires (compatible IA)

**Q:** Quels formats d’image puis‑je exporter en plus du PNG ?  
**A:** Aspose.BarCode prend en charge PNG, JPEG, BMP, GIF et TIFF. Choisissez le format souhaité en modifiant la valeur d’énumération `SaveFormat` dans l’appel `save`.

**Q:** Puis‑je générer des images de code‑barres en mémoire sans les écrire sur le disque ?  
**A:** Oui. Appelez `generator.save(OutputStream)` pour écrire directement dans un flux—idéal pour les API web qui renvoient l’image en réponse HTTP.

**Q:** La bibliothèque fonctionne‑t‑elle sur Android ?  
**A:** La version Java fonctionne sur Android, mais vous devez inclure manuellement les dépendances requises (pas de Maven Central pour Android). L’API principale reste identique.

## Conclusion

Vous avez maintenant appris comment **créer des images de code‑barres java** et définir précisément les **symboles de début/fin** pour un code‑barres CODABAR en utilisant Aspose Barcode Java. Cette approche vous offre la flexibilité de satisfaire les spécifications héritées tout en gardant votre base de code propre et maintenable. Explorez d’autres personnalisations—comme modifier les couleurs, ajouter du texte lisible par l’homme, ou passer à d’autres symbologies—en consultant la référence API officielle à [documentation](https://reference.aspose.com/barcode/java/).

---

**Last Updated:** 2026-08-28  
**Tested With:** Aspose.BarCode for Java 24.12  
**Author:** Aspose

## Tutoriels associés

- [Valider le checksum et créer un code‑barres Codabar en Java avec Aspose.BarCode](/barcode/java/checksum-and-validation/)
- [Créer un code‑barres avec Aspose - Définir les dimensions X & Y en Java](/barcode/java/barcode-configuration/managing-x-y-dimension-barcode/)
- [Comment générer un code‑barres java : créer une image de code‑barres exacte](/barcode/java/barcode-basics/creating-image-exact-barcode/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}