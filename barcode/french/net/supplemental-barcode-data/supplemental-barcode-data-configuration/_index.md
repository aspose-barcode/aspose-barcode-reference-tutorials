---
title: Création de données de codes-barres supplémentaires avec Aspose.BarCode pour .NET
linktitle: Configuration des données de codes-barres supplémentaires
second_title: API Aspose.BarCode .NET
description: Générez des données de codes-barres supplémentaires avec Aspose.BarCode pour .NET. Personnalisez les codes-barres EAN-2 et EAN-5 sans effort. Guide étape par étape pour les développeurs .NET.
weight: 10
url: /fr/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Création de données de codes-barres supplémentaires avec Aspose.BarCode pour .NET


Dans le monde de la génération et de la personnalisation de codes-barres, Aspose.BarCode for .NET se distingue comme un outil puissant et polyvalent. Que vous soyez un développeur expérimenté ou un débutant, ce guide étape par étape vous guidera tout au long du processus de configuration de données de codes-barres supplémentaires à l'aide d'Aspose.BarCode pour .NET. 

## Conditions préalables

Avant de plonger dans le monde des données supplémentaires sur les codes-barres, assurez-vous que les conditions préalables suivantes sont remplies :

- Un environnement de développement mis en place avec Visual Studio ou tout autre outil de développement .NET.
-  Une copie d'Aspose.BarCode pour .NET. Si ce n'est pas déjà fait, vous pouvez le télécharger[ici](https://releases.aspose.com/barcode/net/).
- Connaissance de base de la programmation C#.
- Un répertoire dans lequel vous pouvez enregistrer les images de codes-barres générées.

## Importation d'espaces de noms

Tout d’abord, assurez-vous que vous disposez des espaces de noms nécessaires inclus dans votre code C# pour fonctionner avec Aspose.BarCode pour .NET. Importez les espaces de noms requis au début de votre fichier C# :

```csharp
using Aspose.BarCode.Generation;
```

Décomposons maintenant le processus de configuration des données de codes-barres supplémentaires en plusieurs étapes.

## Étape 1 : configuration du chemin du répertoire

 Dans votre code C#, définissez le chemin d'accès au répertoire dans lequel vous souhaitez enregistrer les images de codes-barres générées. Remplacer`"Your Directory Path"` avec votre chemin de répertoire réel.

```csharp
string path = "Your Directory Path";
```

## Étape 2 : Création d'un générateur de codes-barres

 Créer une instance de`BarcodeGenerator` en spécifiant le type de code-barres et les données que vous souhaitez encoder. Dans cet exemple, nous utilisons un code-barres EAN-13 avec la donnée « 1234567890128 ».

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

## Étape 3 : Personnalisation des dimensions du code-barres

Définissez les dimensions du code-barres, telles que la dimension X (la largeur du plus petit élément du code-barres) et l'espace supplémentaire. Dans cet exemple, nous définissons la dimension X sur 2 pixels et l'espace supplémentaire sur 20 pixels.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

## Étape 4 : Configuration du supplément EAN-2

Pour configurer un code-barres supplémentaire EAN-2, définissez les données supplémentaires sur la valeur souhaitée. Dans ce cas, nous l'avons mis à "12". 

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

## Étape 5 : enregistrement de l'image du code-barres

Enregistrez l'image de code-barres générée dans votre répertoire spécifié avec un nom significatif. Dans cet exemple, nous enregistrons le code-barres supplémentaire EAN-2 sous le nom "SupplementEAN2.png".

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

## Étape 6 : Configuration du supplément EAN-5

 Pour configurer un code-barres supplémentaire EAN-5, modifiez simplement le`SupplementData` à la valeur souhaitée. Ici, nous l'avons réglé sur "12345".

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

## Étape 7 : Enregistrement de l'image du code-barres (EAN-5)

Enfin, enregistrez l'image du code-barres supplémentaire EAN-5 dans le répertoire spécifié. Dans ce cas, nous l'enregistrons sous le nom "SupplementEAN5.png".

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

Vous avez désormais configuré et généré avec succès des données de codes-barres supplémentaires à l’aide d’Aspose.BarCode for .NET. Vous pouvez utiliser cette approche pour créer une large gamme de types de codes-barres avec diverses données supplémentaires.

## Conclusion

Aspose.BarCode for .NET est un outil puissant pour la génération et la personnalisation de codes-barres. Dans ce guide, nous avons parcouru étape par étape le processus de configuration et de génération de données de codes-barres supplémentaires. Avec les bonnes conditions préalables et un peu de codage, vous pouvez travailler efficacement avec les données de codes-barres et répondre à vos besoins spécifiques.

 Pour plus d'informations et une utilisation avancée, reportez-vous au[Documentation Aspose.BarCode pour .NET](https://reference.aspose.com/barcode/net/).

## Questions fréquemment posées

### Puis-je utiliser Aspose.BarCode pour .NET dans mon projet .NET Core ?
Oui, Aspose.BarCode pour .NET est compatible avec .NET Core.

### Existe-t-il un essai gratuit disponible pour Aspose.BarCode pour .NET ?
 Oui, vous pouvez l'essayer gratuitement en visitant[ce lien](https://releases.aspose.com/).

### Où puis-je obtenir une licence temporaire pour Aspose.BarCode pour .NET ?
 Vous pouvez obtenir une licence temporaire auprès de[ce lien](https://purchase.aspose.com/temporary-license/).

### Aspose.BarCode prend-il en charge un large éventail de types de codes-barres ?
Oui, il prend en charge différents types de codes-barres, notamment EAN-13, QR Code, Code 128, etc.

### Puis-je personnaliser l'apparence des codes-barres générés ?
Absolument, vous pouvez personnaliser les dimensions, les couleurs et d'autres aspects des codes-barres pour répondre à vos besoins.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
