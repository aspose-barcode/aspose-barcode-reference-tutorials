---
date: 2025-12-08
description: Apprenez à créer un code‑barres Code128 en Java et à générer une image
  de code‑barres en Java avec Aspose.BarCode. Définissez des unités de taille précises
  pour les images de code‑barres avec un code simple et réutilisable.
language: fr
linktitle: Setting Size Unit for Barcode Image
second_title: Aspose.BarCode Java API
title: Créer un code‑barres Code128 en Java avec Aspose.BarCode
url: /java/advanced-settings-and-optimization/setting-size-unit-barcode-image/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code‑128 barcode java et définir l’unité de taille avec Aspose.BarCode

## Introduction

Dans ce guide pas à pas, vous **créerez un code‑128 barcode java** qui génère une image de code‑barres et vous permet de contrôler l’unité de taille du résultat. Que vous construisiez un système d’inventaire, un générateur d’étiquettes d’expédition ou toute application Java nécessitant un code‑barres fiable, Aspose.BarCode pour Java rend le processus simple et hautement personnalisable.

## Réponses rapides
- **Quelle bibliothèque faut‑il ?** Aspose.BarCode pour Java.  
- **Quel type de code‑barres est couvert ?** CODE_128 (create code128 barcode java).  
- **Comment définir l’unité de taille ?** Utilisez la propriété `BarHeight` avec `.setPoint()`.  
- **Puis‑je générer une image de code‑barres java dans d’autres formats ?** Oui – PNG, JPEG, BMP, etc.  
- **Quelles sont les prérequis ?** JDK installé, bibliothèque Aspose.BarCode, et un IDE Java.

## Qu’est‑ce que **create code128 barcode java** ?

Créer un code‑barres CODE_128 en Java signifie instancier la classe `BarcodeGenerator` avec l’énumération `EncodeTypes.CODE_128` et fournir la chaîne de données que vous souhaitez encoder. Cette symbologie est largement utilisée en logistique car elle prend en charge l’ensemble complet du jeu de caractères ASCII et offre une haute densité de données.

## Pourquoi utiliser Aspose.BarCode pour **generate barcode image java** ?

- **Contrôle total des dimensions** – vous pouvez définir la hauteur des barres, la taille du module et la résolution de l’image.  
- **Aucune dépendance externe** – pur Java, fonctionne sur toute plateforme supportant le JDK.  
- **Personnalisation riche** – couleurs, polices, marges, et même les QR codes sont pris en charge.  
- **Haute performance** – génère les images en millisecondes, adapté au traitement par lots.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

1. **Java Development Kit (JDK)** – version 8 ou supérieure installée sur votre machine.  
2. **Aspose.BarCode pour Java** – téléchargez le JAR le plus récent depuis le site Aspose (version d’évaluation ou sous licence).  
3. **Un IDE Java** – tel que IntelliJ IDEA, Eclipse ou VS Code avec les extensions Java.  

## Importer les espaces de noms

Ajoutez les importations requises en haut de votre classe Java afin d’accéder à l’API d’Aspose.BarCode :

```java
import java.io.IOException;

import com.aspose.barcode.*;

import com.aspose.barcode.generation.BarcodeGenerator;
```

## Comment **generate barcode image java** avec Aspose.BarCode ?

Voici le flux de travail complet. Chaque étape est expliquée en termes simples, et les blocs de code originaux sont conservés exactement tels quels.

### Étape 1 : Définir le répertoire des ressources

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Remplacez `"Your Document Directory"` par le chemin absolu où vous souhaitez enregistrer l’image du code‑barres.

### Étape 2 : Instancier l’objet Barcode

```java
// Instantiate barcode object, Set the symbology type to code128 and Set the
// Code text for the barcode
BarcodeGenerator bb = new BarcodeGenerator(EncodeTypes.CODE_128, "1234567");
```

Ici nous **create code128 barcode java** en passant `EncodeTypes.CODE_128` et la chaîne de données `"1234567"`.

### Étape 3 : Définir la hauteur des barres (unité de taille)

```java
// Set the bar height to 3 points
bb.getParameters().getBarcode().getBarHeight().setPoint(3.0f);
```

La méthode `setPoint()` définit la hauteur en points (1 point = 1/72 pouce). Ajustez cette valeur selon les exigences de votre mise en page.

### Étape 4 : Enregistrer l’image

```java
// Save the image
bb.save(dataDir + "barcode-size-unit.jpg");
```

L’appel `save()` écrit le code‑barres généré dans le dossier que vous avez spécifié. Le format de l’image est déduit de l’extension du fichier (JPEG dans ce cas).

## Problèmes courants et solutions

| Problème | Raison | Solution |
|----------|--------|----------|
| **Image non créée** | Le chemin `dataDir` est incorrect ou les permissions d’écriture manquent. | Vérifiez que le dossier existe et que votre application dispose des droits d’écriture. |
| **Le code‑barres apparaît trop petit** | La hauteur des barres définie en points est trop faible pour le DPI choisi. | Augmentez la valeur passée à `setPoint()` ou ajustez le DPI de l’image via `bb.getParameters().getImage().setResolution()`. |
| **Caractères non pris en charge** | CODE_128 ne supporte que l’ASCII ; vous avez fourni du Unicode. | Utilisez une autre symbologie (par ex., QR_CODE) pour des données non‑ASCII. |

## Questions fréquemment posées

**Q : Aspose.BarCode pour Java convient‑il à la fois à la génération et à la reconnaissance de codes‑barres ?**  
R : Oui, la bibliothèque prend en charge à la fois la génération et la reconnaissance d’un large éventail de symbologies.

**Q : Puis‑je personnaliser l’apparence des images de code‑barres générées ?**  
R : Absolument. Vous pouvez modifier les couleurs, ajouter des légendes, ajuster les marges et même incorporer des logos grâce à l’API `Parameters` très complète.

**Q : Comment obtenir une licence temporaire pour Aspose.BarCode pour Java ?**  
R : Rendez‑vous [ici](https://purchase.aspose.com/temporary-license/) pour demander une licence temporaire d’évaluation.

**Q : Où puis‑je trouver du support pour Aspose.BarCode pour Java ?**  
R : Le forum communautaire Aspose.BarCode est le meilleur endroit pour obtenir de l’aide. Consultez le [forum](https://forum.aspose.com/c/barcode/13) pour des réponses et pour poser de nouvelles questions.

**Q : Quelles sont les symbologies de code‑barres prises en charge par Aspose.BarCode pour Java ?**  
R : La bibliothèque supporte des dizaines de symbologies, dont CODE_128, QR_CODE, UPC_A, DataMatrix, PDF417, et bien d’autres.

---

**Dernière mise à jour :** 2025-12-08  
**Testé avec :** Aspose.BarCode pour Java 24.12 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}