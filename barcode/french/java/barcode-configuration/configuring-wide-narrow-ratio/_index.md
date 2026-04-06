---
date: 2026-02-12
description: Apprenez à créer un code‑128 avec un rapport large‑étroit personnalisé
  en Java à l’aide d’Aspose.BarCode, et à générer efficacement des images PNG de code‑barres.
  Suivez notre guide étape par étape.
linktitle: Configuring Wide-Narrow Ratio
second_title: Aspose.BarCode Java API
title: Comment créer un code‑barres CODE_128 avec un rapport large‑étroit en Java
url: /fr/java/barcode-configuration/configuring-wide-narrow-ratio/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code-barres CODE_128 avec un rapport Large‑Étroit en Java

## Introduction

Si vous devez **créer un code‑barres code128** avec des proportions visuelles précises, ajuster le rapport large‑étroit est la clé. Dans ce tutoriel, nous parcourrons un processus de création de **code‑barres étape par étape** en utilisant Aspose.BarCode pour Java, vous montrant comment configurer le rapport, **générer des images PNG de code‑barres**, et **enregistrer l’image du code‑barres** sur le disque. Que vous créiez des étiquettes d’inventaire, des tags d’expédition ou toute application nécessitant un code‑barres CODE_128 au style personnalisé, vous trouverez tout ce dont vous avez besoin ici.

## Réponses rapides
- **Qu'est‑ce que le rapport large‑étroit ?** Il contrôle la largeur relative des barres larges par rapport aux barres étroites dans un code‑barres.  
- **Quelle symbologie prend en charge l'ajustement du rapport ?** La plupart des symbologies 1‑D, y compris CODE_128, vous permettent de définir un rapport personnalisé.  
- **Ai‑je besoin d’une licence ?** Un essai gratuit est disponible, mais une licence commerciale est requise pour une utilisation en production.  
- **Puis‑je générer une image de code‑barres au format PNG ?** Oui—utilisez `generator.save(...)` pour générer des images PNG de code‑barres.  
- **Le code est‑il compatible avec Java 8+ ?** Absolument ; Aspose.BarCode fonctionne avec toutes les versions modernes de Java.

## Prérequis

Avant de plonger dans le code, assurez‑vous de disposer de ce qui suit :

- Java Development Kit (JDK) installé sur votre machine.  
- Bibliothèque Aspose.BarCode pour Java. Téléchargez‑la depuis le [download link](https://releases.aspose.com/barcode/java/).

## Importer les packages

Pour commencer, importez la classe essentielle d’Aspose.BarCode dans votre projet.

```java
// Import Aspose.BarCode library
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Qu'est‑ce que le rapport large‑étroit et pourquoi l'ajuster ?

Le rapport large‑étroit détermine l'épaisseur des barres « larges » par rapport aux barres « étroites ». Ajuster ce rapport peut améliorer la lisibilité par le scanner, répondre à des normes d'impression spécifiques, ou simplement correspondre au style visuel d’une marque.

## Comment créer un code‑barres code128 avec un rapport large‑étroit en Java

Ci‑dessous se trouve un guide de **code‑barres étape par étape** qui vous accompagne à chaque étape du processus.

### Étape 1 : Définir le répertoire du document

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Assurez‑vous que le répertoire existe et que vous disposez des permissions d’écriture ; c’est ici que le fichier **save barcode image** sera placé.

### Étape 2 : Instancier l’objet Barcode

```java
// Instantiate barcode object
// Create an instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

Ici nous **créer un code‑barres code128** en passant `EncodeTypes.CODE_128` au constructeur.

### Étape 3 : Définir le rapport Large‑Étroit

```java
// Set the wide to narrow ratio for the barcode
generator.getParameters().getBarcode().setWideNarrowRatio(3.0f);
```

La méthode `setWideNarrowRatio` vous permet d’ajuster finement l’espacement visuel. Une valeur de `3.0f` signifie que la barre large fait trois fois la largeur d’une barre étroite.

### Étape 4 : Enregistrer l’image sur le disque

```java
// Save the image to disk in PNG format
generator.save(dataDir + "wideNarrowRatio.png");
```

L’appel à `save` **générera l’image du code‑barres** et l’enregistrera sous forme de fichier PNG, complétant l’étape **save barcode image**.

## Pourquoi ajuster le rapport large‑étroit ?

- **Compatibilité du scanner :** Certains scanners préfèrent un rapport entre 2,0 et 3,0 pour des taux de lecture optimaux.  
- **Qualité d’impression :** Ajuster le rapport peut compenser les limitations de DPI de l’imprimante, évitant des barres déformées.  
- **Cohérence de la marque :** Certaines entreprises souhaitent que les codes‑barres s’alignent visuellement avec les couleurs corporatives ou les directives de conception.

## Problèmes courants et solutions

| Problème | Raison | Solution |
|----------|--------|----------|
| Le code‑barres apparaît déformé | Rapport trop élevé/bas pour l’imprimante | Ajustez la valeur passée à `setWideNarrowRatio` (p. ex., 2.0‑2.5). |
| Fichier non créé | Chemin `dataDir` invalide ou permissions insuffisantes | Vérifiez le chemin du répertoire et assurez‑vous que l’application dispose des droits d’écriture. |
| Le scanner ne peut pas lire le code‑barres | Rapport hors de la plage recommandée pour la symbologie | Utilisez des rapports standards (2.0‑3.0) ou testez avec le scanner cible. |

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.BarCode avec d’autres frameworks Java ?**  
R : Oui, Aspose.BarCode est conçu pour fonctionner de manière transparente avec Spring, Java EE, Android et d’autres environnements Java.

**Q : Comment puis‑je générer des codes‑barres avec différentes symbologies ?**  
R : Il suffit de changer le type de symbologie dans le constructeur `BarcodeGenerator`, par exemple `EncodeTypes.QR` pour les codes QR.

**Q : Une version d’essai d’Aspose.BarCode est‑elle disponible ?**  
R : Oui, vous pouvez accéder à la version d’essai gratuite [ici](https://releases.aspose.com/).

**Q : Où puis‑je trouver la documentation détaillée d’Aspose.BarCode ?**  
R : Consultez la documentation [ici](https://reference.aspose.com/barcode/java/).

**Q : Comment obtenir du support pour Aspose.BarCode ?**  
R : Visitez le forum Aspose.BarCode [ici](https://forum.aspose.com/c/barcode/13) pour le support et les discussions communautaires.

---

**Dernière mise à jour :** 2026-02-12  
**Testé avec :** Aspose.BarCode for Java 24.11 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}