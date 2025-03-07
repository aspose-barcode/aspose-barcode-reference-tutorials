---
title: Configuration du code unidimensionnel 128
linktitle: Configuration du code unidimensionnel 128
second_title: API Aspose.BarCode .NET
description: Découvrez comment générer des codes-barres Code 128 unidimensionnels dans .NET à l’aide d’Aspose.BarCode. Suivez notre guide étape par étape pour une intégration transparente des codes-barres.
weight: 10
url: /fr/net/one-dimensional-barcode-types/one-dimensional-code-128-configuration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configuration du code unidimensionnel 128


Si vous êtes un développeur .NET à la recherche d'un outil puissant pour générer des codes-barres dans vos applications, Aspose.BarCode for .NET est votre solution incontournable. Ce guide complet vous guidera tout au long du processus d'exploitation des capacités d'Aspose.BarCode for .NET pour créer des codes-barres Code 128 unidimensionnels. Il est conçu pour les développeurs débutants et expérimentés. 

## Conditions préalables

Avant de plonger dans le monde passionnant de la génération de codes-barres avec Aspose.BarCode, assurez-vous d'avoir les conditions préalables suivantes en place :

1. Visual Studio : assurez-vous que Visual Studio est installé sur votre système.

2.  Aspose.BarCode pour .NET : vous devrez télécharger et installer Aspose.BarCode pour .NET. Vous pouvez l'obtenir de[ici](https://releases.aspose.com/barcode/net/).

3. Votre projet .NET : vous devez avoir un projet .NET configuré et prêt à intégrer la génération de codes-barres.

Maintenant, commençons !

## Importer des espaces de noms

La première étape consiste à importer les espaces de noms nécessaires à votre projet. Ces espaces de noms vous donneront accès aux fonctionnalités et fonctions d'Aspose.BarCode.

### Étape 1 : Importer les espaces de noms

```csharp
using Aspose.BarCode.Generation;
```

## Configuration du code unidimensionnel 128

Créons maintenant des codes-barres Code 128 à l'aide d'Aspose.BarCode pour .NET. Nous passerons en revue chaque étape en détail, en veillant à ce que vous ayez une compréhension claire du processus.

### Étape 2 : définir le chemin

Tout d’abord, définissez le chemin d’accès au répertoire dans lequel vous souhaitez enregistrer les images de codes-barres générées.

```csharp
string path = "Your Directory Path";
```

### Étape 3 : Créer un générateur de codes-barres Code 128

 Créer un`BarcodeGenerator` exemple pour générer des codes-barres Code 128. Vous pouvez spécifier le type de code-barres que vous souhaitez générer (dans ce cas, Code128) et la valeur que vous souhaitez encoder.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code128, "CODE");
```

### Étape 4 : Configurer les paramètres du code-barres

Avant de générer le code-barres, vous pouvez configurer différents paramètres. Par exemple, vous pouvez choisir d'afficher ou de masquer la somme de contrôle.

#### Option 1 : ne pas afficher la somme de contrôle

```csharp
gen.Parameters.Barcode.ChecksumAlwaysShow = false;
```

#### Option 2 : Afficher la somme de contrôle

```csharp
gen.Parameters.Barcode.ChecksumAlwaysShow = true;
```

### Étape 5 : Enregistrez l'image du code-barres

Il est maintenant temps d'enregistrer l'image du code-barres générée dans le répertoire spécifié. Vous pouvez enregistrer le code-barres avec ou sans la somme de contrôle, selon la configuration que vous avez choisie à l'étape précédente.

#### Enregistrer le code-barres sans somme de contrôle

```csharp
gen.Save($"{path}OneCSCode128NotShowChecksum.png", BarCodeImageFormat.Png);
```

#### Enregistrer le code-barres avec la somme de contrôle

```csharp
gen.Save($"{path}OneCSCode128ShowChecksum.png", BarCodeImageFormat.Png);
```

C'est ça! Vous avez généré avec succès des codes-barres Code 128 unidimensionnels à l’aide d’Aspose.BarCode pour .NET. Vous pouvez utiliser ces codes-barres dans diverses applications, telles que la gestion des stocks, l'étiquetage des produits, etc.

## Conclusion

Aspose.BarCode for .NET fournit une solution puissante et conviviale pour la génération de codes-barres dans les applications .NET. Grâce à son API intuitive et à sa documentation complète, vous pouvez facilement intégrer la fonctionnalité de codes-barres dans vos projets. Que vous ayez besoin de créer des codes-barres unidimensionnels ou bidimensionnels, Aspose.BarCode est là pour vous.

Intégrez Aspose.BarCode dans vos applications .NET dès aujourd'hui et rationalisez facilement vos processus de génération de codes-barres.

### FAQ

### Aspose.BarCode pour .NET est-il compatible avec .NET Core ?
Oui, Aspose.BarCode pour .NET est compatible avec .NET Framework et .NET Core.

### Puis-je personnaliser l'apparence des codes-barres générés ?
Absolument! Aspose.BarCode vous permet de personnaliser divers aspects du code-barres, notamment la taille, la couleur et l'emplacement du texte.

### Aspose.BarCode est-il adapté à la génération de codes QR ?
Bien qu'Aspose.BarCode se concentre principalement sur les codes-barres unidimensionnels, vous pouvez également utiliser Aspose.BarCode for .NET pour générer des codes QR.

### Existe-t-il un essai gratuit disponible ?
 Oui, vous pouvez essayer Aspose.BarCode pour .NET gratuitement en téléchargeant la version d'essai[ici](https://releases.aspose.com/).

### Où puis-je obtenir de l'aide pour Aspose.BarCode pour .NET ?
 Vous pouvez demander de l'aide et partager vos expériences sur le forum Aspose.BarCode for .NET.[ici](https://forum.aspose.com/c/barcode/13).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
