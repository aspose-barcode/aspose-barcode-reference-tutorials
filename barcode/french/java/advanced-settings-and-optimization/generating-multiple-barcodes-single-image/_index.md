---
date: 2026-04-03
description: Apprenez à créer des codes QR en Java et à générer plusieurs codes‑barres
  sur une seule image à l’aide d’Aspose.BarCode pour Java. Comprend la configuration,
  le code et le dépannage.
keywords:
- create qr code java
- aspose barcode java
- generate barcodes java
linktitle: Générer plusieurs codes-barres sur une seule image
second_title: Aspose.BarCode Java API
title: Créer un QR Code en Java – Générer plusieurs codes-barres sur une même image
url: /fr/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code QR Java – Générer plusieurs codes-barres sur une image

## Introduction

Dans ce tutoriel, vous apprendrez **comment créer un code QR Java** et combinerez plusieurs types de codes-barres différents sur une seule image en utilisant **Aspose.BarCode for Java**. Que vous ayez besoin d'une étiquette QR compacte, d'un code-barres produit, ou d'un mélange de symbologies 2‑D et linéaires, ce guide vous accompagne à chaque étape — de la configuration du projet à l'enregistrement de l'image combinée finale — afin que vous puissiez commencer à intégrer la génération de codes-barres dans vos applications Java dès maintenant.

## Réponses rapides
- **Quelle bibliothèque devrais-je utiliser ?** Aspose.BarCode for Java provides the most complete set of symbologies.  
- **Puis-je générer différents types de codes-barres ensemble ?** Yes, you can mix CODE_39, QR, AZTEC, and more on a single canvas.  
- **Ai-je besoin d'une licence pour le développement ?** A free trial works for testing; a commercial license is required for production.  
- **Quelle version de Java est prise en charge ?** Java 8 and newer are fully compatible.  
- **Le format de sortie est-il configurable ?** You can export the combined image as PNG, JPEG, BMP, etc.  

## Qu'est-ce que créer un code QR Java ?

Créer un code QR en Java signifie convertir une chaîne de texte en une matrice bidimensionnelle qui peut être scannée par des smartphones ou des lecteurs de codes-barres. **Aspose.BarCode for Java** gère l'encodage et le rendu, vous permettant de vous concentrer sur la logique métier plutôt que sur le traitement d'image de bas niveau.

## Pourquoi utiliser Aspose.BarCode Java pour générer des codes-barres en Java ?

- **Large prise en charge des symbologies** – from classic linear codes to modern 2‑D matrices.  
- **Rendu haute qualité** – anti‑aliased output that works on any device.  
- **API simple** – create, customize, and combine barcodes with just a few method calls.  
- **Aucune dépendance externe** – everything runs on the JVM without native libraries.  

## Prérequis

Avant de plonger dans le tutoriel, assurez‑vous de disposer des prérequis suivants :

- Compréhension de base de la programmation Java.  
- Kit de développement Java (JDK) installé sur votre système.  
- Bibliothèque Aspose.BarCode for Java téléchargée et configurée. Vous pouvez la télécharger [ici](https://releases.aspose.com/barcode/java/).  
- Un environnement de développement intégré (IDE) tel qu'Eclipse ou IntelliJ IDEA.

## Importer les espaces de noms

Dans votre projet Java, importez les espaces de noms nécessaires pour accéder aux fonctionnalités d'Aspose.BarCode. Ajoutez les déclarations d'importation suivantes au début de votre classe Java :

```java
import java.awt.Color;
import java.awt.Graphics;
import java.awt.image.BufferedImage;
import java.io.File;
import java.util.ArrayList;
import java.util.HashMap;

import javax.imageio.ImageIO;

import com.aspose.barcode.BaseEncodeType;
import com.aspose.barcode.EncodeTypes;


import com.aspose.barcode.generation.BarcodeGenerator;
```

## Étape 1 : Définir le répertoire des ressources

Définissez le chemin du répertoire des ressources où les codes-barres générés seront enregistrés. Ce répertoire est crucial pour organiser et gérer vos images de codes-barres.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Étape 2 : Créer une collection de codes-barres

Initialisez un `HashMap` pour stocker les données des codes-barres. Chaque entrée de la collection représente un code-barres avec son type d'encodage respectif.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Étape 3 : Générer les images de codes-barres

Parcourez la collection et générez les images de codes-barres à l'aide de la bibliothèque Aspose.BarCode. Stockez les images dans un `ArrayList` pour un traitement ultérieur.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Étape 4 : Créer une image combinée

Déterminez la largeur maximale et la hauteur totale des images de codes-barres. Créez un `BufferedImage` pour combiner les images de codes-barres individuelles en une seule image de sortie.

```java
int maxWidth = 0;
int sumHeight = 0;
for (BufferedImage bmp : images) {
    sumHeight += bmp.getHeight();
    if (maxWidth < bmp.getWidth())
        maxWidth = bmp.getWidth();
}

int offset = 10;
BufferedImage resultBitmap = new BufferedImage(maxWidth + offset * 2, sumHeight + offset * images.size(),
        BufferedImage.TYPE_INT_ARGB);
Graphics g = resultBitmap.getGraphics();
g.setColor(Color.white);
g.fillRect(0, 0, resultBitmap.getWidth(), resultBitmap.getHeight());

int yPosition = offset;
for (int i = 0; i < images.size(); ++i) {
    BufferedImage currentBitmap = images.get(i);
    g.drawImage(currentBitmap, offset, yPosition, null);
    yPosition += currentBitmap.getHeight() + offset;
}
```

## Étape 5 : Enregistrer le résultat

Enregistrez l'image combinée finale à l'emplacement de fichier spécifié.

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Cas d'utilisation courants pour la génération de plusieurs codes-barres

- **Étiquettes d'emballage** – combinez les codes produit, lot et expédition sur une seule étiquette.  
- **Billets d'événement** – intégrez des identifiants QR, Data Matrix et Code 128 pour différentes stations de lecture.  
- **Gestion des stocks** – affichez le SKU, les données de puce RFID et les numéros de série ensemble pour un audit rapide.

## Dépannage & conseils

- **Problèmes de taille d'image** – ajustez la variable `offset` pour augmenter ou diminuer l'espacement entre les codes-barres.  
- **Symbologie non prise en charge** – vérifiez que votre version d'Aspose.BarCode supporte le type de code-barres souhaité.  
- **Performance** – réutilisez un seul objet `Graphics` si vous générez de nombreuses images dans une boucle.

## Questions fréquemment posées

**Q1 : Puis-je personnaliser l'apparence des codes-barres individuels dans l'image générée ?**  
R1 : Oui, Aspose.BarCode offre de nombreuses options de personnalisation de l'apparence des codes-barres, vous permettant d'adapter le style de chaque code-barres à vos préférences.

**Q2 : Aspose.BarCode est‑il compatible avec différentes symbologies de codes-barres ?**  
R2 : Absolument ! Aspose.BarCode prend en charge un large éventail de symbologies, y compris CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 et AZTEC, comme le montre ce tutoriel.

**Q3 : Comment puis‑je intégrer Aspose.BarCode dans mon projet Java ?**  
R3 : Il suffit de télécharger la bibliothèque Aspose.BarCode for Java depuis [ici](https://releases.aspose.com/barcode/java/) et de suivre les instructions d'installation fournies dans la documentation.

**Q4 : Puis‑je utiliser Aspose.BarCode pour des applications commerciales ?**  
R4 : Oui, vous pouvez obtenir une licence depuis [ici](https://purchase.aspose.com/buy) pour utiliser Aspose.BarCode à des fins commerciales.

**Q5 : Existe‑t‑il des options d'essai disponibles pour Aspose.BarCode ?**  
R5 : Bien sûr ! Vous pouvez explorer les fonctionnalités d'Aspose.BarCode en obtenant une licence d'essai gratuite [ici](https://releases.aspose.com/).

**Q6 : Comment générer un code QR haute résolution pour l'impression ?**  
R6 : Définissez le DPI souhaité sur le `BarcodeGenerator` avant d'appeler `generateBarCodeImage()`, puis enregistrez l'image dans un format sans perte tel que PNG.

**Q7 : Que faire si l'image combinée apparaît tronquée ?**  
R7 : Vérifiez que les calculs de `offset` et de la taille du canevas tiennent correctement compte de toutes les hauteurs des codes-barres ; augmenter la hauteur du canevas ou réduire la taille des codes-barres individuels résout la plupart des problèmes de troncature.

---

**Dernière mise à jour :** 2026-04-03  
**Testé avec :** Aspose.BarCode for Java 24.11  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}