---
date: 2025-12-27
description: Apprenez à créer un code‑barres Data Matrix et à définir l’emplacement
  du texte du code‑barres en Java avec Aspose.BarCode. Suivez notre guide pas à pas
  pour une personnalisation complète.
linktitle: Setting Code Text Location
second_title: Aspose.BarCode Java API
title: Créer un code‑barres Data Matrix et définir la position du texte du code en
  Java
url: /fr/java/text-and-styling/setting-code-text-location/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code‑barres Data Matrix et définir l'emplacement du texte du code en Java

## Introduction

La génération de codes‑barres est une exigence courante pour l'inventaire, l'expédition et de nombreuses autres applications basées sur Java. Avec **Aspose.BarCode for Java** vous pouvez **créer un code‑barres Data Matrix** rapidement et contrôler chaque aspect visuel, y compris l'endroit où apparaît le texte lisible par l'homme. Dans ce tutoriel, nous parcourrons les étapes exactes pour **créer un code‑barres Data Matrix** et démontrerons **comment définir le texte du code‑barres** au-dessus du symbole afin qu'il corresponde à vos spécifications de conception.

## Réponses rapides
- **Quelle bibliothèque est utilisée ?** Aspose.BarCode for Java
- **Quel type de code‑barres est démontré ?** Data Matrix
- **Comment positionnez‑vous le texte du code ?** En utilisant `CodeLocation.ABOVE`
- **Avez‑vous besoin d’une licence pour la production ?** Oui, une licence commerciale est requise
- **Le code peut‑il s’exécuter sur Java8+ ?** Absolument, il prend en charge Java8 et les versions ultérieures

## Qu'est-ce qu'un code-barres Data Matrix ?
Un code‑barres Data Matrix est un symbole bidimensionnel (2‑D) qui stocke de grandes quantités de données dans un motif carré ou rectangulaire compact. Il est largement utilisé pour marquer de petits objets, l'électronique et les dispositifs médicaux car il peut encoder jusqu'à 2335 caractères alphanumériques.

## Pourquoi définir l'emplacement du texte du code-barres ?
Placer le texte lisible par l'homme **au-dessus**, **en dessous** ou **à côté** du code‑barres aide les utilisateurs à vérifier rapidement les données encodées sans scanner. Ajuster l'emplacement du texte, améliorer la cohérence de l'interface utilisateur et respecter les directives de marque.

## Prérequis

- Connaissances de base en programmation Java.
- Kit de développement Java (JDK) installé.
- Un IDE tel qu'Eclipse ou IntelliJ IDEA.
- Bibliothèque Aspose.BarCode for Java (téléchargez‑la depuis [ici](https://releases.aspose.com/barcode/java/)).

## Importer des packages

Tout d’abord, importez les classes Aspose.BarCode essentielles dans votre projet :

```java
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.generation.BarcodeGenerator;
```

Ces importations vous donnent accès au générateur de codes-barres et à l'énumération qui contrôle le placement du texte.

## Guide étape par étape

### Étape 1 : Définir les chemins d’accès aux répertoires

Indiquez l’emplacement où vous souhaitez lire/écrire les fichiers. Remplacez les espaces réservés par les chemins d’accès réels sur votre ordinateur.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

### Étape 2 : Créer une instance de BarcodeGenerator

Instanciez `BarcodeGenerator` avec le type **Data Matrix** et indiquez le texte du code à encoder.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DATA_MATRIX,
        "GTIN:898978777776665655 " + "UID: 121212121212121212 " + "Batch:GH768 " + "Exp.Date:150923");
```

### Étape 3 : Positionner le texte du code-barres

Utilisez l’énumération `CodeLocation` pour positionner le texte. Dans cet exemple, il est placé **au-dessus** du code-barres.

```java
generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.ABOVE);
```

### Étape 4 : Enregistrer l’image du code-barres généré
Enfin, enregistrez l’image du code-barres sur le disque. Le fichier contiendra le symbole Data Matrix avec le texte positionné au-dessus.

```java
generator.save(dataDir + "codetextAbove.png");
```

## Problèmes courants et solutions

- **Texte absent :** Assurez-vous d'utiliser une version d'Aspose.BarCode compatible avec `CodeLocation`.

- **Erreurs de chemin de fichier :** Vérifiez que `dataDir` se termine par un séparateur de fichiers (`/` ou `\\`) compatible avec votre système d'exploitation.

- **Caractères non pris en charge :** Data Matrix ne peut encoder qu'un nombre limité de caractères ; évitez les symboles spéciaux non conformes à la norme ISO/IEC 16022.

## Foire aux questions (FAQ)

### Q : Puis-je personnaliser l'apparence du code-barres généré ?

R : Oui, Aspose.BarCode offre de nombreuses options de personnalisation, vous permettant de contrôler les couleurs, les marges et les styles de police.

### Q : Aspose.BarCode est-il compatible avec Java 8 et les versions ultérieures ?

R : Absolument, la bibliothèque fonctionne avec Java 8 et toutes les versions ultérieures.

### Q : Comment intégrer Aspose.BarCode à mon projet Java existant ? R : Ajoutez les fichiers JAR d'Aspose.BarCode au classpath de votre projet, importez les packages requis et vous êtes prêt à générer des codes-barres.

### Q : Existe-t-il une version d'essai d'Aspose.BarCode ?

R : Oui, vous pouvez découvrir les fonctionnalités d'Aspose.BarCode en obtenant une version d'essai gratuite [ici](https://releases.aspose.com/).

### Q : Où puis-je trouver de l'aide ou du support pour Aspose.BarCode ?

R : Consultez le [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13) pour obtenir de l'aide de la communauté et du support officiel.

## Questions fréquentes supplémentaires

**Q : Puis-je générer un code-barres avec du texte positionné sous le symbole ?**

R : Oui, définissez `CodeLocation.BELOW` dans la même méthode `setLocation`.

**Q : La bibliothèque prend-elle en charge d’autres codes-barres 2D comme les codes QR ?**

R : Absolument. Il suffit de remplacer `EncodeTypes.DATA_MATRIX` par `EncodeTypes.QR`.

**Q : Comment modifier la taille de la police du texte du code-barres ?**

R : Utilisez `generator.getParameters().getBarcode().getCodeTextParameters().setFontSize(double size)`.

## Conclusion

Vous avez maintenant appris à **créer un code-barres Data Matrix** en Java et à contrôler précisément **l’emplacement du texte du code-barres** à l’aide d’Aspose.BarCode. Expérimentez avec d’autres valeurs de `CodeLocation` et options de style pour répondre aux exigences de conception de votre application.

---

**Dernière mise à jour :** 27/12/2025
**Testé avec :** Aspose.BarCode pour Java 24.11
**Auteur :** Aspose 

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}