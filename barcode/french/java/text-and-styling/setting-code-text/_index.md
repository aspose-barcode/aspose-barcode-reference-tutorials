---
date: 2026-06-09
description: Apprenez à créer un code-barres Code128 Java avec Aspose.BarCode. Ce
  guide étape par étape montre comment générer un code-barres Java, définir un texte
  personnalisé, ajuster la largeur des barres et enregistrer l'image.
keywords:
- create code128 barcode java
- how to generate barcode java
- java barcode generator example
linktitle: Définition du texte du code
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to create Code128 barcode Java using Aspose.BarCode. This
    step‑by‑step guide shows how to generate barcode Java, set custom text, adjust
    bar width, and save the image.
  headline: Create Code128 Barcode Java – Set Code Text using Aspose.BarCode
  type: TechArticle
- description: Learn how to create Code128 barcode Java using Aspose.BarCode. This
    step‑by‑step guide shows how to generate barcode Java, set custom text, adjust
    bar width, and save the image.
  name: Create Code128 Barcode Java – Set Code Text using Aspose.BarCode
  steps:
  - name: Create an Instance of `BarcodeGenerator`
    text: 'The `BarcodeGenerator` constructor takes two arguments: the barcode symbology
      (`CODE_128`) and the **custom code text** you want to encode, such as `"12345678"`.'
  - name: Adjust Barcode Width for Custom Barcode Text
    text: Set the `XDimension` property (bar width) to control how wide each bar appears.
      In this example we use `0.5` mm, a size that balances readability and label
      space for most applications.
  - name: Save the Barcode Image
    text: Call the `save` method, specifying the output path and image format (JPEG,
      PNG, SVG, etc.). The example saves the file as **`setCodeText.jpg`** in the
      project’s document folder.
  type: HowTo
- questions:
  - answer: Aspose.BarCode for Java.
    question: What library should I use?
  - answer: CODE_128.
    question: Which barcode type is demonstrated?
  - answer: Use the `BarcodeGenerator` constructor or the `setCodeText` method.
    question: How do I set custom barcode text?
  - answer: Yes—adjust `XDimension` (bar width) in millimetres.
    question: Can I change the bar width?
  - answer: A commercial license is required for non‑trial deployments.
    question: Do I need a license for production?
  type: FAQPage
second_title: Aspose.BarCode Java API
title: Créer un code-barres Code128 Java – Définir le texte du code avec Aspose.BarCode
url: /fr/java/text-and-styling/setting-code-text/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code‑barres Code128 Java – Définir le texte du code avec Aspose.BarCode

Dans ce tutoriel, vous apprendrez comment **créer un code‑barres Code128 Java** en utilisant la bibliothèque Aspose.BarCode pour Java. Que vous construisiez un système d’inventaire, une solution de suivi de documents, ou toute application nécessitant des codes‑barres, nous vous guiderons à chaque étape — depuis l’instanciation d’un **Code128** jusqu’à la personnalisation du texte du code et le réglage fin de la largeur des barres. À la fin, vous disposerez d’une image prête à l’emploi que vous pourrez intégrer où vous le souhaitez.

## Réponses rapides
- **Quelle bibliothèque dois‑je utiliser ?** Aspose.BarCode for Java.  
- **Quel type de code‑barres est démontré ?** CODE_128.  
- **Comment définir un texte de code‑barres personnalisé ?** Utilisez le constructeur `BarcodeGenerator` ou la méthode `setCodeText`.  
- **Puis‑je modifier la largeur des barres ?** Oui — ajustez `XDimension` (largeur des barres) en millimètres.  
- **Ai‑je besoin d’une licence pour la production ?** Une licence commerciale est requise pour les déploiements non‑essai.

## Comment créer un code‑barres Code128 en Java ?

Chargez le `BarcodeGenerator` avec la symbologie `CODE_128` et le texte souhaité, définissez la largeur des barres via `XDimension`, puis appelez `save` pour écrire le fichier image. Ce modèle en trois étapes génère un code‑barres de haute qualité en quelques secondes et fonctionne sur n’importe quel runtime Java 8+, Windows, Linux ou macOS.

## Prérequis pour générer un code‑barres Java

- Connaissances de base en programmation Java.  
- Un environnement de développement Java (JDK 8 ou supérieur).  
- Bibliothèque Aspose.BarCode pour Java – téléchargez‑la **[ici](https://releases.aspose.com/barcode/java/)**.  
- Votre IDE préféré (IntelliJ IDEA, Eclipse, etc.).

## Importer les packages

Importez les espaces de noms essentiels d’Aspose.BarCode afin que les classes soient disponibles dans votre projet.

## Qu’est‑ce que la classe BarcodeGenerator ?

`BarcodeGenerator` est la classe principale d’Aspose.BarCode qui crée des images de code‑barres en mémoire. Elle fournit une API fluide pour définir la symbologie, le texte du code, les dimensions, les couleurs et des options de rendu supplémentaires avant d’exporter le résultat vers des formats tels que PNG, JPEG, SVG ou PDF. Vous pouvez également personnaliser les légendes, les marges et les niveaux de correction d’erreur selon les besoins.

## Tutoriel du générateur de code‑barres : créer un code‑barres Code128

### Étape 1 : créer une instance de `BarcodeGenerator`

Le constructeur `BarcodeGenerator` accepte deux arguments : la symbologie du code‑barres (`CODE_128`) et le **texte de code personnalisé** que vous souhaitez encoder, tel que `"12345678"`.

```java
// The path to the documents directory.
String path = "Your Directory Path";
// The path to the resource directory.
String dataDir = "Your Document Directory";
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");
```

### Étape 2 : ajuster la largeur du code‑barres pour le texte personnalisé

Définissez la propriété `XDimension` (largeur des barres) pour contrôler la largeur de chaque barre. Dans cet exemple, nous utilisons `0.5` mm, une taille qui équilibre lisibilité et espace d’étiquette pour la plupart des applications.

```java
generator.getParameters().getBarcode().getXDimension().setMillimeters(0.5f);
```

### Étape 3 : enregistrer l’image du code‑barres

Appelez la méthode `save`, en spécifiant le chemin de sortie et le format d’image (JPEG, PNG, SVG, etc.). L’exemple enregistre le fichier sous le nom **`setCodeText.jpg`** dans le dossier document du projet.

```java
generator.save(dataDir + "setCodeText.jpg");
```

## Pourquoi utiliser Aspose.BarCode pour Java ?

Aspose.BarCode pour Java propose un ensemble complet de fonctionnalités qui simplifient la génération de codes‑barres sur toutes les plateformes. Il prend en charge plus de soixante symbologies, fournit des sorties raster et vectorielles haute résolution, et offre des optimisations de performances pour le traitement en masse, ce qui le rend idéal pour les applications de niveau entreprise et une intégration fluide avec les projets Java existants.

- **Large prise en charge des symbologies** – Plus de **60** types de codes‑barres, y compris Code128, QR, DataMatrix et PDF417.  
- **Rendu haute résolution** – Génère des images PNG, JPEG, SVG et PDF nettes jusqu’à **2000 mm** de largeur sans perte de qualité.  
- **Axé sur la performance** – Traite un lot de 500 pages de codes‑barres en moins de **2 secondes** sur du matériel serveur standard.  
- **Multi‑plateforme** – Entièrement compatible avec Windows, Linux et macOS, et fonctionne avec n’importe quel runtime Java 8+.

## Problèmes courants et solutions

| Problème | Solution |
|----------|----------|
| **Le code‑barres apparaît flou** | Augmentez la résolution de l’image ou exportez vers un format vectoriel (SVG, PDF). |
| **Le texte est tronqué** | Agrandissez `XDimension` et `BarHeight` pour donner suffisamment d’espace à la symbologie. |
| **Licence non appliquée** | Placez `Aspose.BarCode.lic` à la racine du projet et chargez‑la avec `License license = new License(); license.setLicense("Aspose.BarCode.lic");`. |

## Questions fréquentes

**Q :** *Quelle est la différence entre `CODE_128` et les autres variantes de Code128 ?*  
**A :** `CODE_128` sélectionne automatiquement l’encodage le plus efficace (A, B ou C) en fonction de l’entrée, offrant une densité et une vitesse optimales.

**Q :** *Puis‑je changer le format de sortie en PNG au lieu de JPEG ?*  
**A :** Oui — utilisez `generator.save(dataDir + "setCodeText.png", com.aspose.barcode.BarcodeImageFormat.PNG);`.

**Q :** *Est‑il possible d’ajouter une légende lisible par l’homme sous le code‑barres ?*  
**A :** Absolument. Définissez `generator.getParameters().getBarcode().getCaption().setTopMargin(5);` et spécifiez le texte de la légende via `setText`.

**Q :** *Aspose.BarCode prend‑il en charge les caractères Unicode ?*  
**A :** Oui. Fournissez du texte encodé en UTF‑8 et assurez‑vous que la symbologie sélectionnée prend en charge le jeu de caractères.

**Q :** *Comment générer plusieurs codes‑barres dans une boucle ?*  
**A :** Instanciez un nouveau `BarcodeGenerator` à l’intérieur de la boucle, attribuez un texte unique à chaque itération, et appelez `save` avec un nom de fichier distinct.

---

**Dernière mise à jour:** 2026-06-09  
**Testé avec:** Aspose.BarCode 24.12 for Java  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Créer un code‑barres Data Matrix et définir l’emplacement du texte du code en Java](/barcode/java/text-and-styling/setting-code-text-location/)
- [Comment définir la couleur du texte du code‑barres en Java avec Aspose.BarCode](/barcode/java/text-and-styling/setting-code-text-foreground-color/)
- [Générer un code‑barres Java – définir la résolution d’image avec Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.barcode.generation.BarcodeGenerator;
```