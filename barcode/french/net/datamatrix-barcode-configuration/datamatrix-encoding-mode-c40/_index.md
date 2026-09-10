---
date: 2026-06-09
description: Apprenez à générer des codes-barres DataMatrix et à enregistrer le PNG
  en utilisant le codage C40 avec Aspose.BarCode – guide complet pour la génération
  de codes-barres .NET Core.
keywords:
- how to generate datamatrix
- barcode generation .net core
- datamatrix c40 png
linktitle: Mode d'encodage DataMatrix (C40)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  headline: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  type: TechArticle
- description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  name: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  steps:
  - name: Define the Directory Path
    text: Set the folder where the PNG image will be stored. Replace the placeholder
      with an actual path on your machine.
  - name: Set Up Barcode Generation
    text: Create a `BarcodeGenerator` instance, specify `EncodeTypes.DataMatrix`,
      and provide the data you want to encode.
  - name: Customize Barcode
    text: Configure the X‑dimension (pixel width of the modules) and switch the encoding
      mode to C40.
  - name: Save the Barcode Image
    text: Finally, save the generated barcode as a PNG file. This is the concrete
      answer to **how to save png** with Aspose.BarCode. When you run the program,
      you’ll find `DataMatrixEncodeModeC40.png` in the folder you specified, ready
      to be used in reports, labels, or web pages.
  type: HowTo
- questions:
  - answer: C40 is a compact alphanumeric encoding scheme for DataMatrix symbols,
      ideal for text that includes letters, numbers, and a limited set of special
      characters.
    question: What is DataMatrix Encoding Mode (C40)?
  - answer: You can find the documentation [here](https://reference.aspose.com/barcode/net/).
      It provides detailed guidance on all barcode types and encoding options.
    question: Where can I find the Aspose.BarCode for .NET documentation?
  - answer: Yes, the library supports a wide range of .NET versions, from .NET Framework
      4.5+ to .NET 6 and later.
    question: Is Aspose.BarCode for .NET compatible with all .NET versions?
  - answer: Yes, you can explore a free trial of Aspose.BarCode for .NET by visiting
      [this link](https://releases.aspose.com/). It allows you to test the library’s
      features and capabilities.
    question: Can I try Aspose.BarCode for .NET before purchasing?
  - answer: You can find a supportive community and access support for Aspose.BarCode
      for .NET on the [Aspose forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Comment générer un PNG DataMatrix avec C40 en utilisant Aspose.BarCode
url: /fr/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mode d'encodage DataMatrix principal (C40) avec Aspose.BarCode pour .NET

## Introduction

Dans ce tutoriel, vous apprendrez **comment générer des datamatrix** barcodes et les enregistrer au format PNG en utilisant le mode d'encodage C40 avec Aspose.BarCode pour .NET. Que vous construisiez un système d'inventaire, un générateur d'étiquettes d'expédition ou toute solution nécessitant des symboles compacts et à haute densité, maîtriser le C40 vous permet d'obtenir des symboles plus petits sans sacrifier la lisibilité. Nous parcourrons chaque étape — de la configuration de l'environnement à la production du PNG final — afin que vous puissiez intégrer le code immédiatement dans votre projet.

## Réponses rapides
- **À quoi fait référence « how to generate datamatrix » ?** Création d'une image de code-barres DataMatrix par programmation.  
- **Quel mode d'encodage est couvert ?** DataMatrix C40, un schéma alphanumérique efficace.  
- **Ai-je besoin d'une licence ?** Un essai gratuit suffit pour les tests ; une licence commerciale est requise pour la production.  
- **Puis-je exécuter cela sur .NET Core ?** Oui, Aspose.BarCode prend pleinement en charge .NET Core, .NET 5, .NET 6 et les versions ultérieures.  
- **Quel format de fichier est produit ?** PNG – un format d'image sans perte et adapté au web.

## Comment générer un DataMatrix avec l'encodage C40

Chargez vos données, configurez le générateur et appelez `Save` – c’est le flux de travail complet en trois étapes concises. La classe `BarcodeGenerator` gère la création du symbole, tandis que l'énumération `BarCodeImageFormat.Png` indique à Aspose.BarCode d'écrire le résultat sous forme de fichier PNG. `Save` écrit l'image du code-barres généré dans le chemin de fichier spécifié au format choisi. Ce paragraphe de réponse directe vous fournit la solution de bout en bout avant que nous n'examinions chaque ligne de code.

## Qu'est-ce que le mode d'encodage DataMatrix (C40) ?

`DataMatrixEncodeMode` est une énumération qui indique quel schéma d'encodage Aspose.BarCode doit utiliser pour les symboles DataMatrix. L'option `DataMatrixEncodeMode.C40` sélectionne l'encodage alphanumérique C40, qui regroupe lettres, chiffres et un ensemble limité de ponctuation dans moins de modules, réduisant ainsi la taille globale du symbole tout en conservant la lisibilité pour le texte d'inventaire typique. Ce schéma efficace est idéal lorsque vous devez encoder des données alphanumériques de façon compacte.

## Pourquoi utiliser Aspose.BarCode pour .NET ?

Aspose.BarCode offre **plus de 30 paramètres configurables** pour les dimensions, les niveaux de correction d'erreurs et les modes d'encodage, et il prend en charge **plus de 50 formats d'images et de codes-barres**. La bibliothèque fonctionne sur **.NET Framework 4.5+, .NET Core 2.0+, .NET 5/6+**, offrant une génération sans dépendance qui fonctionne sur les serveurs, les postes de travail et les appareils mobiles.

## Prérequis

Avant de plonger dans le code, assurez-vous de disposer des éléments suivants :

1. **Environnement de développement .NET** – Visual Studio, Rider ou tout IDE supportant C#.  
2. **Aspose.BarCode pour .NET** – installé via NuGet ou l'installateur officiel. Consultez la [documentation](https://reference.aspose.com/barcode/net/) pour plus de détails.  
3. **Connaissances de base en C#** – vous devez être à l'aise avec les espaces de noms, les classes et les instructions using.  
4. **Dossier avec accès en écriture** – un répertoire sur votre machine où le PNG sera enregistré.

## Importation des espaces de noms nécessaires

La classe `BarcodeGenerator` est le point d'entrée pour créer n'importe quel code-barres. Ajoutez l'espace de noms requis en haut de votre fichier source C# afin de pouvoir accéder à l'API de génération :

```csharp
using Aspose.BarCode.Generation;
```

## Génération de code-barres étape par étape

Ci-dessous se trouve un guide **étape par étape** du code-barres. Chaque étape est expliquée en termes simples, et les espaces réservés originaux sont conservés inchangés pour faciliter le copier‑coller.

### Étape 1 : Définir le chemin du répertoire
Définissez le dossier où l'image PNG sera stockée. Remplacez l'espace réservé par un chemin réel sur votre machine.

```csharp
string path = "Your Directory Path";
```

### Étape 2 : Configurer la génération du code-barres
Créez une instance de `BarcodeGenerator`, spécifiez `EncodeTypes.DataMatrix` et fournissez les données que vous souhaitez encoder.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE.BARCODE"))
{
    // Additional steps go here
}
```

### Étape 3 : Personnaliser le code-barres
Configurez la X‑dimension (largeur en pixels des modules) et passez le mode d'encodage à C40.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 6;
gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.C40;
```

### Étape 4 : Enregistrer l'image du code-barres
Enfin, enregistrez le code-barres généré sous forme de fichier PNG. C’est la réponse concrète à **how to save png** avec Aspose.BarCode.

```csharp
gen.Save($"{path}DataMatrixEncodeModeC40.png", BarCodeImageFormat.Png);
```

Lorsque vous exécuterez le programme, vous trouverez `DataMatrixEncodeModeC40.png` dans le dossier que vous avez spécifié, prêt à être utilisé dans les rapports, les étiquettes ou les pages web.

## Problèmes courants et astuces

- **Chemin invalide** – Assurez-vous que le répertoire existe et que vous avez les permissions d'écriture ; sinon `gen.Save` lèvera une exception.  
- **Mode d'encodage incorrect** – Si vous devez encoder des caractères hors du jeu C40, passez à `DataMatrixEncodeMode.Auto` ou à un autre mode approprié.  
- **Taille de l'image** – Ajustez `XDimension.Pixels` pour augmenter ou diminuer la taille globale du code-barres sans affecter la lisibilité.

## Foire aux questions

**Q : Qu'est-ce que le mode d'encodage DataMatrix (C40) ?**  
R : C40 est un schéma d'encodage alphanumérique compact pour les symboles DataMatrix, idéal pour le texte incluant des lettres, des chiffres et un ensemble limité de caractères spéciaux.

**Q : Où puis‑je trouver la documentation d'Aspose.BarCode pour .NET ?**  
R : Vous pouvez trouver la documentation [ici](https://reference.aspose.com/barcode/net/). Elle fournit des instructions détaillées sur tous les types de codes‑barres et les options d'encodage.

**Q : Aspose.BarCode pour .NET est‑il compatible avec toutes les versions de .NET ?**  
R : Oui, la bibliothèque prend en charge un large éventail de versions .NET, du .NET Framework 4.5+ au .NET 6 et ultérieur.

**Q : Puis‑je essayer Aspose.BarCode pour .NET avant d'acheter ?**  
R : Oui, vous pouvez explorer un essai gratuit d'Aspose.BarCode pour .NET en visitant [ce lien](https://releases.aspose.com/). Cela vous permet de tester les fonctionnalités et les capacités de la bibliothèque.

**Q : Où puis‑je obtenir du support pour Aspose.BarCode pour .NET ?**  
R : Vous pouvez trouver une communauté de soutien et accéder au support d'Aspose.BarCode pour .NET sur le [forum Aspose](https://forum.aspose.com/c/barcode/13).

## Conclusion

En suivant ce guide **étape par étape du code‑barres**, vous savez maintenant exactement **comment générer des datamatrix** et les enregistrer au format PNG en utilisant le mode d'encodage C40 avec Aspose.BarCode pour .NET. Cette approche vous donne un contrôle total sur l'apparence, la taille et la représentation des données du code‑barres, facilitant l'intégration de codes‑barres de haute qualité dans toute application .NET.

---

**Dernière mise à jour :** 2026-06-09  
**Testé avec :** Aspose.BarCode 24.11 for .NET  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Encodage DataMatrix en octets avec Aspose.BarCode pour .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [Encodage DataMatrix principal en ASCII avec Aspose.BarCode pour .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Comment générer des codes-barres DataMatrix (ECC 200) avec Aspose.BarCode pour .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}