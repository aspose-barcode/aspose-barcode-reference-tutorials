---
date: 2025-11-29
description: Apprenez à lire les codes‑barres 1D en Java avec Aspose.BarCode – décoder
  rapidement les codes‑barres à partir d’une image grâce à une bibliothèque de codes‑barres
  robuste pour Java.
language: fr
linktitle: read 1d barcodes java
second_title: Aspose.BarCode Java API
title: Comment lire les codes-barres 1D en Java avec Aspose.BarCode
url: /java/advanced-settings-and-optimization/getting-all-possible-1d-barcodes-image/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lire les codes‑barres 1D Java avec Aspose.BarCode

## Introduction

Dans ce guide pratique, vous découvrirez comment **lire des codes‑barres 1D en Java** à l’aide de la puissante bibliothèque **Aspose.BarCode**. Que vous ayez besoin de scanner des étiquettes produit, des balises d’inventaire ou tout autre code‑barres linéaire intégré dans une image, ce tutoriel vous accompagne pas à pas — de la configuration de l’environnement à l’extraction de chaque code‑barres présent dans l’image. À la fin, vous serez capable de **décoder des codes‑barres à partir d’images** avec seulement quelques lignes de code Java.

## Réponses rapides
- **Que fait Aspose.BarCode ?** Elle fournit une bibliothèque de codes‑barres complète pour Java qui peut générer et décoder des codes‑barres 1D/2D.  
- **Puis-je lire plusieurs codes‑barres à partir d’une même image ?** Oui – la méthode `BarCodeReader.readBarCodes()` renvoie tous les symboles détectés.  
- **Ai‑je besoin d’une licence pour le développement ?** Une licence temporaire fonctionne pour les tests ; une licence commerciale est requise pour la production.  
- **Quelles versions de Java sont prises en charge ?** Java 8 + (JDK 11 recommandé).  
- **Cette bibliothèque est‑elle suffisamment rapide pour la lecture en temps réel ?** Absolument – elle est optimisée pour le traitement par lots haute performance.

## Qu’est‑ce que « read 1d barcodes java » ?

Lire des codes‑barres 1D en Java signifie utiliser une **bibliothèque de codes‑barres pour Java** afin d’analyser une image, de localiser les motifs de codes‑barres linéaires et de renvoyer le texte encodé ainsi que des métadonnées telles que le type de symbologie et l’orientation. Aspose.BarCode abstrait le travail intensif de traitement d’image, vous permettant de vous concentrer sur la logique métier.

## Pourquoi choisir Aspose.BarCode pour décoder les codes‑barres à partir d’une image ?

- **Large prise en charge des symbologies** – plus de 50 types 1D et 2D.  
- **Détection précise** – fonctionne même avec des codes‑barres à faible contraste ou tournés.  
- **API simple** – quelques appels de méthode vous donnent tous les résultats.  
- **Aucune dépendance externe** – pur Java, facile à intégrer dans n’importe quel projet.  

## Prérequis

Avant de plonger dans le code, assurez‑vous de disposer de :

- **Java Development Kit (JDK)** – version 8 ou plus récente. Téléchargez‑le depuis la page officielle [Oracle JDK page](https://www.oracle.com/java/technologies/javase-downloads.html).  
- **Aspose.BarCode for Java** – récupérez le dernier JAR depuis la [Aspose release page](https://releases.aspose.com/barcode/java/).  

Maintenant que votre environnement est prêt, commençons à coder.

## Importer les espaces de noms

Ajoutez les déclarations `import` nécessaires afin que le compilateur puisse localiser les classes d’Aspose.

```java
import java.awt.Point;

import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## Étape 1 : Initialiser l’objet BarCodeReader

Créez une instance `BarCodeReader` pointant vers votre fichier image. Le paramètre `DecodeType` indique au moteur quelles symbologies rechercher ; utiliser `CODE_128` comme exemple fonctionne pour de nombreux codes‑barres 1D courants.

```java
BarCodeReader reader = new BarCodeReader("path/to/your/image.png", DecodeType.CODE_128);
```

> **Astuce :** Si vous souhaitez scanner *tous* les types 1D pris en charge, passez `DecodeType.ALL_1D` au lieu d’une seule symbologie.

## Étape 2 : Lire tous les codes‑barres possibles

Parcourez la collection renvoyée par `readBarCodes()`. Pour chaque `BarCodeResult` nous affichons le texte décodé, le nom de la symbologie, l’angle de détection et les coordonnées des quatre coins de la région du code‑barres.

```java
int iCount = 0;
for (BarCodeResult result : reader.readBarCodes()) {
    // Display code text, symbology, detected angle, recognition percentage of the barcode
    System.out.println("Code Text: " + result.getCodeText() + " Symbology: " + result.getCodeTypeName()
            + " Recognition percentage: " + result.getRegion().getAngle());

    // Display x and y coordinates of barcode detected
    Point[] point = result.getRegion().getPoints();

    System.out.println("Top left coordinates: X = " + point[0].getX() + ", Y = " + point[0].getY());
    System.out.println("Bottom left coordinates: X = " + point[1].getX() + ", Y = " + point[1].getY());
    System.out.println("Bottom right coordinates: X = " + point[2].getX() + ", Y = " + point[2].getY());
    System.out.println("Top right coordinates: X = " + point[3].getX() + ", Y = " + point[3].getY());

    iCount = iCount + 1;
}
```

La boucle traite automatiquement chaque code‑barres trouvé, vous n’avez donc pas besoin d’appeler le lecteur plusieurs fois. À la fin de la boucle, `iCount` contient le nombre total de codes‑barres détectés.

## Problèmes courants et solutions

| Symptôme | Cause probable | Solution |
|----------|----------------|----------|
| Aucun code‑barres retourné | Image trop floue ou à faible contraste | Pré‑traitez l’image (augmentez le contraste, binarisez) avant de la fournir au lecteur. |
| Symbologie incorrecte signalée | `DecodeType` incorrect utilisé | Utilisez `DecodeType.ALL_1D` pour laisser le moteur détecter automatiquement tout type 1D. |
| Valeurs d’angle incorrectes | Image tournée | L’API renvoie déjà l’angle de rotation ; vous pouvez faire pivoter l’image dans le sens inverse si nécessaire. |

## Questions fréquemment posées

**Q : Aspose.BarCode pour Java convient‑il aux projets commerciaux ?**  
R : Oui. Une licence commerciale supprime toutes les limitations d’évaluation et vous accorde des droits de redistribution complets.

**Q : Puis‑je tester la bibliothèque sans acheter de licence ?**  
R : Absolument. Obtenez une licence temporaire depuis la [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/) pour le développement et les tests.

**Q : Où puis‑je trouver la référence complète de l’API ?**  
R : La documentation exhaustive est disponible [here](https://reference.aspose.com/barcode/java/).

**Q : Comment obtenir de l’aide en cas de problème ?**  
R : Publiez votre question sur le [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) où la communauté et les ingénieurs d’Aspose peuvent vous assister.

**Q : Existe‑t‑il un téléchargement d’essai gratuit ?**  
R : Oui – vous pouvez télécharger une version d’essai depuis la [Aspose releases page](https://releases.aspose.com/).

## Conclusion

Vous avez maintenant appris à **lire des codes‑barres 1D en Java** avec Aspose.BarCode, une bibliothèque de codes‑barres robuste pour Java qui rend le décodage de codes‑barres à partir de fichiers image simple et fiable. Intégrez cet extrait dans vos propres applications pour automatiser les scans d’inventaire, la validation de tickets ou tout scénario où des codes‑barres linéaires apparaissent dans des images.

---

**Dernière mise à jour :** 2025-11-29  
**Testé avec :** Aspose.BarCode 24.11 for Java  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}