---
date: 2025-12-27
description: Apprenez comment ajouter une légende aux images de code‑barres en Java
  en utilisant Aspose.BarCode. Cet exemple de générateur de code‑barres Java montre
  comment créer facilement une image de code‑barres en Java.
linktitle: Adding Caption to Barcode
second_title: Aspose.BarCode Java API
title: Comment ajouter une légende à un code‑barres en Java avec Aspose.BarCode
url: /fr/java/text-and-styling/adding-caption-barcode/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter une légende à un code-barres en Java avec Aspose.BarCode

## Introduction

Si vous avez besoin de **comment ajouter une légende** à un code-barres pour une meilleure lisibilité et un meilleur branding, vous êtes au bon endroit. Dans ce tutoriel, nous passerons en revue les étapes exactes pour ajouter des légendes au-dessus et en dessous d’une image de code‑barres en utilisant Aspose.BarCode pour Java. À la fin, vous disposerez d’un code‑barres entièrement stylisé qui non seulement encode les données mais affiche également un texte utile — parfait pour les étiquettes de produits, les systèmes d’inventaire ou tout scénario où les utilisateurs bénéficient d’un contexte supplémentaire.

## Quick Answers
- **Quelle bibliothèque est requise ?** Aspose.BarCode for Java.  
- **Puis-je changer la police et la couleur ?** Oui — la famille de police de la légende et la couleur du texte sont personnalisables.  
- **Quels types de code‑barres fonctionnent ?** Toutes les symbologies prises en charge par Aspose.BarCode (par ex., CODE_128, QR, DataMatrix).  
- **Ai‑je besoin d’une licence pour les tests ?** Un essai gratuit est disponible ; une licence commerciale est requise pour la production.  
- **Combien de temps prend l’implémentation ?** Généralement moins de 10 minutes une fois la bibliothèque ajoutée.

## What is a caption in a barcode?
Une légende est un texte simple qui apparaît soit au-dessus, soit en dessous du graphique du code‑barres. Elle peut indiquer le nom du produit, le prix ou toute autre information qui complète les données encodées.

## Why add captions with Aspose.BarCode?
- **Expérience utilisateur améliorée :** Les utilisateurs peuvent lire instantanément la signification d’un code‑barres sans le scanner.  
- **Cohérence de la marque :** Vous pouvez appliquer vos propres polices, couleurs et alignements pour correspondre aux guides de style de l’entreprise.  
- **Contrôle total :** L’API d’Aspose.BarCode vous permet de basculer la visibilité, de définir l’alignement et de styliser chaque légende indépendamment.

## Prerequisites

Avant de commencer, assurez‑vous d’avoir :

- Le Java Development Kit (JDK) installé.
- La bibliothèque Aspose.BarCode for Java téléchargée et ajoutée à votre projet. Vous pouvez trouver le lien de téléchargement [ici](https://releases.aspose.com/barcode/java/).
- Un IDE tel qu’IntelliJ IDEA ou Eclipse.

## Import Packages

Dans votre fichier source Java, importez les classes Aspose.BarCode requises ainsi que la classe AWT `Color` :

```java
import com.aspose.barcode.*;
import java.awt.*;
```

## Step 1: Set Up Document and Resource Directories

Spécifiez où vous souhaitez stocker l’image du code‑barres générée. Ajustez les chemins pour qu’ils correspondent à votre environnement.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

## Step 2: Create Barcode Generator Instance

Instanciez `BarcodeGenerator` avec la symbologie souhaitée (par ex., CODE_128) et le texte du code que vous voulez encoder.

```java
BarcodeGenerator bb = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

## Step 3: Configure Caption Above the Barcode

Définissez la légende qui apparaît au-dessus du code‑barres. Vous pouvez contrôler l’alignement, le texte, la visibilité, la famille de police, la taille et la couleur.

```java
bb.getParameters().getCaptionAbove().setAlignment(TextAlignment.LEFT);
bb.getParameters().getCaptionAbove().setText("Aspose.Demo");
bb.getParameters().getCaptionAbove().setVisible(true);
bb.getParameters().getCaptionAbove().getFont().setFamilyName("Pristina");
bb.getParameters().getCaptionAbove().getFont().getSize().setPoint(14);
bb.getParameters().getCaptionAbove().setTextColor(Color.RED);
```

## Step 4: Configure Caption Below the Barcode

De même, définissez la légende en dessous du code‑barres. N’hésitez pas à utiliser un alignement ou un style différent si besoin.

```java
bb.getParameters().getCaptionBelow().setAlignment(TextAlignment.RIGHT);
bb.getParameters().getCaptionBelow().setText("Aspose.Demo");
bb.getParameters().getCaptionBelow().setVisible(true);
bb.getParameters().getCaptionBelow().getFont().setFamilyName("Pristina");
bb.getParameters().getCaptionBelow().getFont().getSize().setPoint(14);
bb.getParameters().getCaptionBelow().setTextColor(Color.RED);
```

## Step 5: Save the Barcode Image

Enfin, écrivez le code‑barres (avec les légendes) dans un fichier image. Le format est déduit de l’extension du fichier.

```java
bb.save(dataDir + "barcodeCaption.jpg");
```

Vous pouvez répéter les étapes ci‑dessus pour expérimenter différentes polices, couleurs ou alignements, ou pour générer plusieurs images de code‑barres dans une boucle.

## Common Issues & Tips

- **Légende non visible ?** Assurez‑vous que `setVisible(true)` est appelé pour la légende que vous souhaitez afficher.  
- **Couleurs incorrectes ?** Utilisez les constantes `java.awt.Color` ou créez des couleurs personnalisées avec `new Color(r, g, b)`.  
- **Problèmes de chemin ?** Vérifiez que `dataDir` pointe vers un dossier existant et accessible en écriture ; sinon, `bb.save()` lèvera une `IOException`.  
- **Conseil de performance :** Réutilisez une seule instance de `BarcodeGenerator` lors de la génération de nombreux codes‑barres ; changez uniquement les `EncodeTypes` ou le `codetext` selon les besoins.

## Frequently Asked Questions (FAQs)

### Can I customize the font style of the barcode captions?
Oui, vous pouvez personnaliser la famille de police, la taille et la couleur de la légende au-dessus et en dessous du code‑barres.

### Is Aspose.BarCode compatible with different barcode symbologies?
Absolument ! Aspose.BarCode prend en charge un large éventail de symbologies, garantissant une flexibilité dans la génération de codes‑barres.

### How can I integrate Aspose.BarCode into my Java project?
Vous pouvez suivre le guide d’intégration détaillé disponible [ici](https://reference.aspose.com/barcode/java/) pour des instructions étape par étape.

### Is there a free trial available for Aspose.BarCode for Java?
Oui, vous pouvez accéder à l’essai gratuit [ici](https://releases.aspose.com/) pour explorer toutes les fonctionnalités avant d’acheter.

### Where can I get help if I run into issues?
Où puis‑je obtenir de l’aide en cas de problème ? Le forum communautaire d’Aspose.BarCode est un excellent endroit pour le support et les discussions. Visitez le forum [ici](https://forum.aspose.com/c/barcode/13).

---

**Dernière mise à jour :** 2025-12-27  
**Testé avec :** Aspose.BarCode for Java 24.11  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}