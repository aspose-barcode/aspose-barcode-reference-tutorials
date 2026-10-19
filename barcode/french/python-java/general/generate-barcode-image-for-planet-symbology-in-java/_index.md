---
category: general
date: 2026-10-18
description: Générez une image de code‑barres pour la symbologie Planet en utilisant
  Java. Apprenez à créer un code‑barres Planet avec des dimensions de code‑barres
  personnalisées et des barres vides.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- create planet barcode
- custom barcode dimensions
language: fr
lastmod: 2026-10-18
og_description: Générez une image de code-barres pour la symbologie Planète en Java.
  Ce tutoriel montre comment créer un code-barres planétaire avec des dimensions de
  code-barres personnalisées et des barres de contour.
og_image_alt: Generated barcode image showing a Planet barcode with empty outline
  bars
og_title: Générer une image de code-barres pour la symbologie Planet – Guide Java
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Generate barcode image for Planet symbology using Java. Learn to create
    planet barcode with custom barcode dimensions and empty bars.
  headline: Generate barcode image for Planet symbology in Java
  type: TechArticle
tags:
- barcode
- Java
- imaging
title: Générer une image de code-barres pour la symbologie Planet en Java
url: /fr/python-java/general/generate-barcode-image-for-planet-symbology-in-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Générer une image de code-barres pour la symbologie Planet en Java

Si vous devez **générer une image de code-barres** pour la symbologie Planet, ce guide vous accompagne tout au long du processus complet. Que vous construisiez un système d'automatisation postale ou une solution de suivi personnalisée, vous apprendrez comment **créer un planet barcode** avec des **dimensions de code-barres personnalisées** et des barres en contour (vides).

L'exemple utilise la bibliothèque Aspose.BarCode for Java, qui fournit une API fluide pour chaque norme de code-barres majeure. Aucun outil de traitement d'image supplémentaire n'est requis, et le code s'exécute sur n'importe quel runtime Java 8+.

## Prérequis

* Java 8 ou version plus récente installé (le tutoriel a été testé avec JDK 17).
* Maven ou Gradle pour gérer les dépendances.
* Familiarité de base avec la syntaxe Java et le concept de code-barres.

Si vous êtes novice avec Maven, vous pouvez créer un projet simple avec `mvn archetype:generate` et ajouter la dépendance Aspose.BarCode affichée ci-dessous.

## Ajouter la dépendance Aspose.BarCode

```xml
<!-- pom.xml -->
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-barcode</artifactId>
    <version>23.12</version> <!-- Use the latest version available -->
</dependency>
```

> **Astuce :** Verrouillez le numéro de version pour éviter des changements incompatibles inattendus lorsque la bibliothèque est mise à jour.

## Étape 1 : Initialiser le générateur de code-barres pour la symbologie Planet

```java
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generator.BarcodeGenerator;

public class PlanetBarcodeDemo {
    public static void main(String[] args) {
        // Step 1 – create a generator that encodes data using the Planet symbology
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.PLANET,          // Planet is the barcode type
                "123456");                   // Data to encode
```

**Pourquoi cette étape est importante :**  
`EncodeTypes.PLANET` indique à la bibliothèque d'utiliser la spécification du code-barres Planet, couramment utilisée pour les services postaux. La chaîne de données `"123456"` est la charge utile qui apparaîtra dans l'image générée.

## Étape 2 : Définir des dimensions de code-barres personnalisées (dimension X)

```java
        // Step 2 – adjust the X dimension (module width) to 4 pixels.
        // This controls the thickness of each bar.
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .getXDimension()
                        .setPixels(4);
```

**Pourquoi cette étape est importante :**  
La *dimension X* définit la largeur de chaque barre individuelle. En la réglant à **4 pixels**, vous obtenez un code-barres facilement lisible par la plupart des scanners tout en s'adaptant à une étiquette standard. Modifier cette valeur est le moyen principal d'obtenir des **dimensions de code-barres personnalisées**.

## Étape 3 : Utiliser des barres vides (en contour) au lieu de barres pleines

```java
        // Step 3 – configure the generator to draw empty bars (outline only)
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .setFilledBars(false);
```

**Pourquoi cette étape est importante :**  
`setFilledBars(false)` indique au rendu de ne dessiner que les contours des barres, laissant l'intérieur transparent. Ce style est souvent requis pour les codes-barres postaux où le fond peut contenir d'autres informations imprimées.

## Étape 4 : Enregistrer l'image du code-barres au format PNG

```java
        // Step 4 – save the generated barcode as a PNG file
        String outputPath = "output/PlanetEmptyBars.png";
        barcodeGenerator.save(outputPath, BarCodeImageFormat.Png);

        System.out.println("Barcode image generated at: " + outputPath);
    }
}
```

**Pourquoi cette étape est importante :**  
Choisir `BarCodeImageFormat.Png` vous fournit une image sans perte qui préserve les bords nets des barres en contour. Le chemin du fichier peut être n'importe quel répertoire où vous avez les droits d'écriture ; l'exemple utilise un dossier `output` relatif à la racine du projet.

### Résultat attendu

L'exécution du programme crée un fichier similaire à l'image ci-dessous :

![Image de code-barres générée pour la symbologie Planet](/images/planet-barcode.png){.align-center alt="Image de code-barres générée montrant un Planet barcode avec des barres vides en contour"}

L'image affiche un **Planet barcode** avec des barres fines et vides, correspondant exactement aux dimensions personnalisées que vous avez définies.

## Variations courantes et cas limites

| Situation | Ajustement |
|-----------|------------|
| **Longueur de données différente** | Les codes-barres Planet supportent jusqu'à 12 caractères numériques. Modifiez le deuxième argument du constructeur en conséquence. |
| **Résolution supérieure** | Augmentez la dimension X (`setPixels`) ou définissez le `YDimension` pour contrôler la hauteur des barres. |
| **Code-barres couleur** | Utilisez `barcodeGenerator.getParameters().getImageOptions().setForeColor(Color.BLUE);` pour changer la couleur des barres. |
| **Enregistrement au format SVG** | Remplacez `BarCodeImageFormat.Png` par `BarCodeImageFormat.Svg` pour obtenir une sortie vectorielle. |
| **Exécution sur Android** | Utilisez la version Android‑compatible d'Aspose.BarCode for Android et remplacez les chemins du système de fichiers par `Context.getFilesDir()`. |

> **Attention :** Régler la dimension X trop basse (par ex., 1 pixel) peut rendre le code-barres illisible sur des imprimantes basse résolution. Testez toujours avec un scanner réel après avoir modifié les dimensions.

## Code source complet pour copier‑coller rapidement

```java
package com.example.barcode;

import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generator.BarcodeGenerator;

public class PlanetBarcodeDemo {
    public static void main(String[] args) {
        // Create the generator for Planet barcode with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.PLANET,
                "123456");

        // Custom X dimension – 4 pixels per module
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .getXDimension()
                        .setPixels(4);

        // Use outline (empty) bars
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .setFilledBars(false);

        // Save as PNG
        String outputPath = "output/PlanetEmptyBars.png";
        barcodeGenerator.save(outputPath, BarCodeImageFormat.Png);

        System.out.println("Barcode image generated at: " + outputPath);
    }
}
```

Copiez le code dans un fichier nommé `PlanetBarcodeDemo.java`, placez-le sous `src/main/java/com/example/barcode/`, exécutez `mvn compile exec:java`, et vous verrez le résultat de **génération d'image de code-barres** dans le dossier `output`.

## Conclusion

Vous savez maintenant comment **générer une image de code-barres** pour la symbologie Planet en Java, comment **créer un planet barcode** avec des **dimensions de code-barres personnalisées**, et comment passer des barres pleines aux barres vides pour un style visuel plus épuré. L'exemple complet montre chaque appel d'API requis, de l'initialisation du générateur à l'enregistrement d'un fichier PNG.

**Prochaines étapes** – explorez d'autres types de code-barres (`EncodeTypes.CODE_128`, `EncodeTypes.QR`) et expérimentez des options d'image supplémentaires telles que la couleur de fond, les marges et les paramètres DPI. Si vous devez intégrer le code-barres dans un PDF, combinez ce code avec Aspose.PDF for Java pour une solution de bout en bout fluide.

Bonne programmation !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités d'API supplémentaires et à explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment créer un planet barcode avec des barres pleines et vides](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [Créer une image de planet barcode – Guide étape par étape](/barcode/english/python-java/general/create-planet-barcode-image-step-by-step-guide/)
- [Comment générer un code-barres en Java : créer une image de code-barres exacte](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}