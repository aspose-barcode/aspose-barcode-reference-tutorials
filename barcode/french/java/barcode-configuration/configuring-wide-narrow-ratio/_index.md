---
date: 2025-12-10
description: Apprenez à générer un code‑barres avec un rapport large‑étroit personnalisé
  en Java en utilisant Aspose.BarCode et à créer efficacement une image de code‑barres.
  Suivez notre guide étape par étape.
linktitle: Configuring Wide-Narrow Ratio
second_title: Aspose.BarCode Java API
title: Comment générer un code‑barres avec un rapport large‑étroit en Java
url: /fr/java/barcode-configuration/configuring-wide-narrow-ratio/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer un code-barres avec un rapport large-étroit en Java

## Introduction

Si vous devez **how to generate barcode** avec des proportions visuelles précises, ajuster le rapport large‑étroit est la clé. Dans ce tutoriel, nous parcourrons un processus de création **step by step barcode** en utilisant Aspose.BarCode for Java, vous montrant comment configurer le rapport, générer l'image du code-barres et **save barcode png** sur le disque. Que vous créiez des étiquettes d'inventaire, des tags d'expédition ou toute application nécessitant un code-barres CODE_128 au style personnalisé, vous trouverez tout ce dont vous avez besoin ici.

## Réponses rapides
- **What is the wide‑narrow ratio?** Il contrôle la largeur relative des barres larges par rapport aux barres étroites dans un code-barres.  
- **Which symbology supports ratio adjustment?** La plupart des symbologies 1‑D, y compris CODE_128, vous permettent de définir un rapport personnalisé.  
- **Do I need a license?** Un essai gratuit est disponible, mais une licence commerciale est requise pour une utilisation en production.  
- **Can I generate a barcode image in PNG format?** Oui—utilisez `generator.save(...)` pour générer l'image du code-barres au format PNG.  
- **Is the code compatible with Java 8+?** Absolument ; Aspose.BarCode fonctionne avec toutes les versions modernes de Java.

## Prérequis

Avant de plonger dans le code, assurez-vous de disposer de ce qui suit :

- Java Development Kit (JDK) installé sur votre machine.  
- Bibliothèque Aspose.BarCode for Java. Téléchargez-la depuis le [download link](https://releases.aspose.com/barcode/java/).

## Importer les packages

Pour commencer, importez la classe essentielle Aspose.BarCode dans votre projet.

```java
// Import Aspose.BarCode library
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Qu'est-ce que le rapport large‑étroit et pourquoi l'ajuster ?

Le rapport large‑étroit détermine l'épaisseur des barres « large » par rapport aux barres « étroite ». Ajuster ce rapport peut améliorer la lisibilité par le scanner, répondre à des normes d'impression spécifiques, ou simplement correspondre au style visuel d'une marque.

## Comment générer un code-barres avec un rapport large‑étroit en Java

Ci-dessous, un guide **step by step barcode** qui vous accompagne à chaque étape du processus.

### Étape 1 : Définir le répertoire du document

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Assurez-vous que le répertoire existe et que vous disposez des permissions d'écriture ; c'est ici que le fichier **save barcode png** sera placé.

### Étape 2 : Instancier l'objet Barcode

```java
// Instantiate barcode object
// Create an instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

Ici, nous **create code_128 barcode** en passant `EncodeTypes.CODE_128` au constructeur.

### Étape 3 : Définir le rapport large‑étroit

```java
// Set the wide to narrow ratio for the barcode
generator.getParameters().getBarcode().setWideNarrowRatio(3.0f);
```

La méthode `setWideNarrowRatio` vous permet d'ajuster finement l'espacement visuel. Une valeur de `3.0f` signifie que la barre large fait trois fois la largeur d'une barre étroite.

### Étape 4 : Enregistrer l'image sur le disque

```java
// Save the image to disk in PNG format
generator.save(dataDir + "wideNarrowRatio.png");
```

Appeler `save` **generate barcode image** et l'enregistrera sous forme de fichier PNG, complétant l'étape **save barcode png**.

## Problèmes courants et solutions

| Problème | Raison | Solution |
|----------|--------|----------|
| Le code-barres apparaît déformé | Rapport trop élevé/faible pour l'imprimante | Ajustez la valeur passée à `setWideNarrowRatio` (par ex., 2.0‑2.5). |
| Fichier non créé | Chemin `dataDir` invalide ou permissions insuffisantes | Vérifiez le chemin du répertoire et assurez-vous que l'application a les droits d'écriture. |
| Le scanner ne peut pas lire le code-barres | Rapport hors de la plage recommandée pour la symbologie | Utilisez des rapports standards (2.0‑3.0) ou testez avec le scanner cible. |

## Questions fréquentes

**Q: Puis-je utiliser Aspose.BarCode avec d'autres frameworks Java ?**  
A: Oui, Aspose.BarCode est conçu pour fonctionner de manière transparente avec Spring, Java EE, Android et d'autres environnements Java.

**Q: Comment générer des codes-barres avec différentes symbologies ?**  
A: Il suffit de changer le type de symbologie dans le constructeur `BarcodeGenerator`, par exemple `EncodeTypes.QR` pour les codes QR.

**Q: Existe-t-il une version d'essai disponible pour Aspose.BarCode ?**  
A: Oui, vous pouvez accéder à la version d'essai gratuite [here](https://releases.aspose.com/).

**Q: Où puis-je trouver la documentation détaillée d'Aspose.BarCode ?**  
A: Référez-vous à la documentation [here](https://reference.aspose.com/barcode/java/).

**Q: Comment obtenir du support pour Aspose.BarCode ?**  
A: Visitez le forum Aspose.BarCode [here](https://forum.aspose.com/c/barcode/13) pour le support et les discussions communautaires.

**Dernière mise à jour :** 2025-12-10  
**Testé avec :** Aspose.BarCode for Java 24.11 (latest at time of writing)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}