---
date: 2025-12-17
description: Apprenez à générer des codes-barres en Java avec Aspose.BarCode, couvrant
  la génération dynamique de codes-barres, la création de codes-barres EAN‑13 et l’enregistrement
  d’images de codes-barres avec des données supplémentaires.
linktitle: Supplementing Data
second_title: Aspose.BarCode Java API
title: Comment générer un code‑barres avec des données supplémentaires en Java
url: /fr/java/barcode-configuration/supplementing-data/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer un code-barres avec des données supplémentaires en Java

## Introduction

Dans l'écosystème numérique actuel, en constante évolution, la question de **comment générer un code-barres** efficacement se pose à de nombreux développeurs Java. Aspose.BarCode for Java propose une API puissante et facile à utiliser qui prend en charge la **génération dynamique de codes-barres**, y compris la création de **codes-barres EAN‑13** avec des données supplémentaires. Que vous construisiez des systèmes d'inventaire, des applications POS de détail ou des solutions de suivi logistique, ce tutoriel vous guide à travers un **exemple de générateur de code-barres Java** qui enregistre l'image du code-barres sur le disque et vous permet de personnaliser la partie supplément.

## Réponses rapides
- **Quelle bibliothèque est la meilleure pour générer des codes-barres en Java ?** Aspose.BarCode for Java.  
- **Quelle symbologie crée un code-barres numérique de 13 chiffres ?** EAN‑13.  
- **Puis-je ajouter des données supplémentaires à un code-barres EAN‑13 ?** Oui, en utilisant l'API `Supplement`.  
- **Comment enregistrer le code-barres généré en tant qu'image ?** Appelez `generator.save("path/filename.jpg")`.  
- **Une licence est‑elle requise pour une utilisation en production ?** Oui, une licence commerciale est nécessaire ; une version d'essai gratuite est disponible.  

## Qu'est-ce que la génération de code-barres en Java ?

La génération de code-barres consiste à convertir des données — chiffres, lettres ou un mélange des deux — en un motif visuel lisible par les scanners. Avec Aspose.BarCode, vous pouvez produire des **images de code-barres haute résolution** à la volée, ce qui la rend idéale pour les scénarios de **génération dynamique de code-barres** tels que la billetterie en temps réel ou l'exécution de commandes.

## Pourquoi utiliser Aspose.BarCode pour la génération dynamique de code-barres ?

- **Contrôle total** sur la symbologie, la taille, les couleurs et les données supplémentaires.  
- **Aucune dépendance externe** – Java pur, fonctionne sur n'importe quelle plateforme.  
- **Support intégré** pour des dizaines de types de code-barres, y compris **create ean13 barcode**.  
- **API simple** qui vous permet de **save barcode image** en une seule ligne de code.  

## Prérequis

- **Java Development Kit (JDK)** – toute version récente (8 ou supérieure).  
- **IDE** – IntelliJ IDEA, Eclipse ou votre éditeur préféré.  
- **Aspose.BarCode for Java** – téléchargez la bibliothèque depuis le site officiel **[here](https://releases.aspose.com/barcode/java/)** et ajoutez le JAR au classpath de votre projet.  

## Importer les packages

Une fois la bibliothèque référencée, importez la classe principale qui pilote la création de code-barres.

```java
// Import Aspose.BarCode for Java
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Guide étape par étape

### Étape 1 : Définir le répertoire de votre document

Définissez le dossier où l'image générée sera stockée.

```java
String dataDir = "Your Document Directory";
```

### Étape 2 : Créer une instance du générateur de code-barres

Instanciez `BarcodeGenerator` avec le **codetext** et la **symbologie** souhaités. Ici, nous **create ean13 barcode** en utilisant la chaîne numérique "123456789123".

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.EAN_13, "123456789123");
```

### Étape 3 : Définir les données supplémentaires

Ajoutez une chaîne supplémentaire de 5 chiffres. Cela est utile pour les magazines, les périodiques ou tout cas où des informations supplémentaires suivent le code-barres principal.

```java
generator.getParameters().getBarcode().getSupplement().setSupplementData("12345");
```

### Étape 4 : Définir l'espace du supplément

Ajustez l'écart entre le code-barres principal et son supplément. La valeur est exprimée en points.

```java
generator.getParameters().getBarcode().getSupplement().getSupplementSpace().setPoint(2.0f);
```

### Étape 5 : Enregistrer l'image du code-barres

Enfin, écrivez l'image sur le disque. Le format est déduit de l'extension du fichier (JPEG dans cet exemple).

```java
generator.save(dataDir + "supplementData.jpg");
```

> **Astuce :** Vous pouvez changer l'extension du fichier en `.png` ou `.bmp` pour obtenir un format d'image différent sans code supplémentaire.

## Problèmes courants et solutions

| Problème | Cause | Solution |
|----------|-------|----------|
| **Image non enregistrée** | `dataDir` pointe vers un dossier inexistant | Assurez‑vous que le répertoire existe ou créez‑le programmatique­ment (`new File(dataDir).mkdirs();`). |
| **Longueur du supplément invalide** | Les suppléments EAN‑13 doivent comporter 2 ou 5 chiffres | Fournissez exactement 2 ou 5 caractères ; sinon une exception est levée. |
| **Caractères non pris en charge** | Caractères non numériques dans le codetext EAN‑13 | Utilisez uniquement les chiffres 0‑9 pour EAN‑13 ; passez à une autre symbologie pour les alphanumériques. |

## Questions fréquemment posées

### Aspose.BarCode est‑il compatible avec toutes les versions de Java ?

Aspose.BarCode for Java est conçu pour être compatible avec un large éventail de versions de Java. Consultez la **[documentation](https://reference.aspose.com/barcode/java/)** pour plus de détails.

### Puis‑je personnaliser l'apparence des codes‑barres générés ?

Oui, Aspose.BarCode offre divers paramètres et réglages pour personnaliser l'apparence des codes‑barres. Explorez la documentation pour plus d'informations détaillées.

### Une version d'essai est‑elle disponible ?

Oui, vous pouvez accéder à une version d'essai gratuite **[here](https://releases.aspose.com/)**.

### Comment obtenir du support pour Aspose.BarCode ?

Visitez le **[forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13)** pour obtenir de l'aide de la communauté et des experts.

### Où puis‑je acheter Aspose.BarCode pour Java ?

Vous pouvez acheter Aspose.BarCode pour Java **[here](https://purchase.aspose.com/buy)**.

---

**Last Updated:** 2025-12-17  
**Tested With:** Aspose.BarCode for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}