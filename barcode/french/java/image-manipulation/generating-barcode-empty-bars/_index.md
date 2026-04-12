---
date: 2026-04-12
description: Apprenez à créer un code‑barres Code128 avec des barres vides en Java
  en utilisant Aspose.BarCode. Ce guide vous montre comment générer rapidement des
  images de code‑barres Java.
keywords:
- create code128 barcode
- generate barcode java
- barcode generator java example
- java generate barcode image
linktitle: Génération de code‑barres avec barres vides
second_title: Aspose.BarCode Java API
title: Comment créer un code‑barres Code128 avec des barres vides en Java
url: /fr/java/image-manipulation/generating-barcode-empty-bars/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code-barres Code128 avec des barres vides en Java

## Introduction

Intégrer la génération de codes-barres dans les applications Java est une exigence fréquente, que vous construisiez des systèmes d'inventaire, des plateformes de billetterie ou des solutions de point de vente. Avec **Aspose.BarCode for Java**, vous pouvez **créer un code-barres Code128** en quelques lignes de code seulement. Dans ce tutoriel, nous parcourrons les étapes pour **générer des images de code-barres Java** comportant des barres vides (non remplies), vous offrant un contrôle total sur le style visuel du code-barres.

## Réponses rapides
- **Quelle bibliothèque ?** Aspose.BarCode for Java  
- **Cas d'utilisation principal ?** Création de codes-barres Code128 avec des barres vides pour des conceptions d'interface utilisateur personnalisées  
- **Prérequis ?** Java JDK 8+, Aspose.BarCode JAR, accès en écriture à un dossier pour l'image de sortie  
- **Temps d'implémentation typique ?** 5‑10 minutes pour un exemple de base  
- **Puis-je personnaliser les couleurs ?** Oui – l'API offre de nombreuses options de style  

## Qu'est-ce qu'un code-barres Code128 ?

Code128 est une symbologie de code-barres linéaire à haute densité qui encode l'ensemble complet du jeu de caractères ASCII. Elle est largement utilisée dans la logistique, l'expédition et le commerce de détail car elle peut représenter des données alphanumériques de manière compacte. Par défaut, Aspose.BarCode rend les barres Code128 sous forme de rectangles pleins ; définir la propriété **FilledBars** sur `false` les transforme en barres vides (contour), ce qui est utile pour le branding stylistique.

## Pourquoi utiliser Aspose.BarCode pour Java ?

- **Ensemble riche de fonctionnalités** – prend en charge plus de 50 types de codes-barres, y compris QR, DataMatrix et PDF417.  
- **Aucune dépendance externe** – un seul JAR fonctionne sur n'importe quel runtime Java.  
- **Contrôle granulaire** – vous pouvez ajuster la largeur des barres, les couleurs, les polices, et la propriété `FilledBars`.  
- **Multi‑plateforme** – fonctionne sous Windows, Linux et macOS sans bibliothèques natives.  

## Prérequis

Avant de commencer, assurez‑vous d'avoir :

1. **Java Development Environment** – JDK 8 ou ultérieur installé et `JAVA_HOME` configuré.  
2. **Aspose.BarCode for Java** – téléchargez le dernier JAR depuis la [page de téléchargement](https://releases.aspose.com/barcode/java/).  
3. **Document Directory** – un dossier sur votre ordinateur où l'image du code-barres générée sera enregistrée.  

## Importer les packages

Dans votre projet Java, importez les classes dont vous aurez besoin pour travailler avec Aspose.BarCode :

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

Ces importations vous donnent accès au générateur de code-barres, à l'énumération des formats d'image et à la gestion des exceptions.

## Étape 1 : Configurer le répertoire de ressources

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Remplacez `"Your Document Directory"` par le chemin absolu du dossier que vous avez créé dans les prérequis. C'est là que le fichier PNG sera écrit.

## Étape 2 : Créer une instance du générateur de code-barres Code128

```java
// Create an instance of BarcodeGenerator and initialize it with CodeText and Symbology
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

Ici, nous instancions `BarcodeGenerator` avec la symbologie **CODE_128** et le texte d'exemple `"TEXT"`. Il s'agit d'un **exemple de générateur de code-barres Java** que vous pouvez adapter à n'importe quelle chaîne à encoder.

## Étape 3 : Définir la propriété FilledBars sur false

```java
// Set the FilledBars property to false
generator.getParameters().getBarcode().setFilledBars(false);
```

En définissant `FilledBars` sur `false`, le code-barres généré affichera des barres vides au lieu de barres pleines, obtenant ainsi l'effet visuel recherché.

## Étape 4 : Enregistrer l'image du code-barres

```java
// Save the resultant barcode image on disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

La méthode `save` écrit le code-barres dans le répertoire spécifié au format PNG. Vous pouvez changer `BarCodeImageFormat.PNG` en `JPG`, `BMP` ou `TIFF` si un autre type d'image est requis.

## Cas d'utilisation courants

- **Branding personnalisé** – les barres vides peuvent être superposées à des motifs ou des couleurs d'arrière-plan.  
- **Actifs prêts à imprimer** – générez des PNG haute résolution pour les inclure dans les factures ou les étiquettes d'expédition.  
- **Génération dynamique** – créez des codes-barres à la volée dans les services web ou les applications de bureau.  

## Conseils de dépannage

- **Chemin invalide** – assurez‑vous que `dataDir` se termine par un séparateur de fichier (`/` ou `\\`) ou concaténez en utilisant `File.separator`.  
- **Licence requise** – une version d'essai fonctionne pour l'évaluation, mais une licence complète est nécessaire pour la production.  
- **Caractères non pris en charge** – Code128 prend en charge l'ensemble complet ASCII ; évitez les caractères Unicode sauf si vous passez à une autre symbologie.  

## Conclusion

Vous avez maintenant appris comment **créer des images de code-barres Code128** avec des barres vides en utilisant Aspose.BarCode pour Java. Cette approche simple vous permet de générer rapidement des graphiques de code-barres personnalisables, que vous construisiez un outil d'inventaire de bureau ou une API cloud.

## FAQ

### Aspose.BarCode est‑il compatible avec tous les environnements de développement Java ?

Oui, Aspose.BarCode est conçu pour s'intégrer de manière transparente à n'importe quel IDE Java ou système de construction, y compris Maven, Gradle et les projets JAR simples.

### Puis‑je personnaliser l'apparence du code‑barres généré ?

Absolument ! En plus de `FilledBars`, vous pouvez modifier les couleurs, la largeur des barres, les marges, et même ajouter du texte lisible par l'homme grâce à l'API étendue.

### Une version d'essai est‑elle disponible pour Aspose.BarCode ?

Oui, vous pouvez explorer les fonctionnalités d'Aspose.BarCode en obtenant un essai gratuit [ici](https://releases.aspose.com/).

### Comment obtenir du support pour Aspose.BarCode ?

Pour toute question ou assistance, visitez le [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

### Où puis‑je trouver la documentation détaillée d'Aspose.BarCode ?

La documentation complète est disponible [ici](https://reference.aspose.com/barcode/java/).

**Questions supplémentaires**

**Q : Comment générer une image de code‑barres dans un format différent, comme JPEG ?**  
R : Changez le deuxième argument de `save` en `BarCodeImageFormat.JPEG`.

**Q : Puis‑je générer plusieurs codes‑barres dans une boucle ?**  
R : Oui – instanciez un nouveau `BarcodeGenerator` dans votre boucle ou réutilisez la même instance avec un nouveau `CodeText`.

---

**Dernière mise à jour :** 2026-04-12  
**Testé avec :** Aspose.BarCode for Java 24.11  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}