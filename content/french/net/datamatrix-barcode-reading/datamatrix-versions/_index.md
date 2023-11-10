---
title: Générez des codes-barres DataMatrix avec Aspose.BarCode pour .NET
linktitle: Versions DataMatrix
second_title: API Aspose.BarCode .NET
description: Découvrez comment générer des codes-barres DataMatrix dans .NET à l'aide d'Aspose.BarCode pour .NET. Dimensions personnalisées, prise en charge ECC et bien plus encore.
type: docs
weight: 12
url: /fr/net/datamatrix-barcode-reading/datamatrix-versions/
---
Si vous recherchez une solution fiable pour générer des codes-barres DataMatrix dans vos applications .NET, Aspose.BarCode for .NET est la voie à suivre. Dans ce guide étape par étape, nous vous guiderons tout au long du processus d'utilisation d'Aspose.BarCode for .NET pour créer des codes-barres DataMatrix. Nous décomposerons chaque exemple en plusieurs étapes, afin que vous puissiez suivre facilement.

## Conditions préalables

Avant de plonger dans le code, assurez-vous que les conditions préalables suivantes sont en place :
- Un environnement de développement avec support .NET.
- Une copie d'Aspose.BarCode pour .NET, que vous pouvez télécharger à partir de[ce lien](https://releases.aspose.com/barcode/net/).
- Connaissance de base de C# et du framework .NET.

Explorons maintenant les versions DataMatrix et comment les générer à l'aide d'Aspose.BarCode pour .NET.

## Importer des espaces de noms

Dans tout projet C#, il est essentiel d'importer les espaces de noms nécessaires. Dans le cas d'Aspose.BarCode, vous devrez inclure les éléments suivants :

```csharp
using Aspose.BarCode.Generation;
```

 Cet espace de noms donne accès au`BarcodeGenerator` classe, ce qui est crucial pour générer des codes-barres.

Maintenant, décomposons l'exemple en plusieurs étapes.

## Étape 1 : Configurez le chemin de votre répertoire

Commencez par définir le chemin du répertoire dans lequel vous souhaitez enregistrer les codes-barres DataMatrix générés.

```csharp
string path = "Your Directory Path";
```

 Remplacer`"Your Directory Path"` avec le chemin réel où vous souhaitez enregistrer les images de codes-barres.

## Étape 2 : initialiser le générateur de codes-barres

 Créez une instance du`BarcodeGenerator` classe et spécifiez le type de code-barres comme`DataMatrix`. Vous pouvez également fournir les données que vous souhaitez encoder dans le code-barres.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Le code pour générer des codes-barres va ici
}
```

## Étape 3 : Configurer les propriétés du code-barres

Vous pouvez personnaliser diverses propriétés du code-barres DataMatrix, telles que ses dimensions et son type ECC (Error Correction Code). Voici un exemple de définition de la dimension X sur 4 pixels et de choix d'ECC200 :

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4;
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

## Étape 4 : Définir la version DataMatrix et enregistrer

Vous pouvez spécifier la version DataMatrix en définissant le nombre de lignes et de colonnes. Après avoir configuré la version, enregistrez l'image du code-barres.

Par exemple, pour créer un code-barres DataMatrix avec 22 lignes et 22 colonnes à l'aide d'ECC200 :

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC200_22x22;
generator.Save($"{path}DataMatrixRows22Columns22Ecc200.png", BarCodeImageFormat.Png);
```

De même, vous pouvez générer un code-barres avec différents paramètres en modifiant la version et le type ECC selon vos besoins.

## Étape 5 : répétez l'opération pour d'autres versions

Vous pouvez répéter l'étape 4 pour d'autres versions de DataMatrix. Par exemple, pour créer un code-barres de 12 lignes et 64 colonnes à l'aide d'ECC200 :

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.DMRE_12x64;
generator.Save($"{path}DataMatrixRows12Columns64Ecc200.png", BarCodeImageFormat.Png);
```

## Étape 6 : Changer de type ECC

Si vous souhaitez modifier le type ECC en Ecc140, vous pouvez le faire en mettant à jour la propriété ECC :

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;
```

## Étape 7 : Générer des codes-barres avec différentes versions et ECC

Répétez l'étape 4 pour les autres versions de DataMatrix et types ECC, en enregistrant chaque code-barres avec un nom de fichier unique.

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC000_140_29x29;
generator.Save($"{path}DataMatrixRows29Columns29Ecc140.png", BarCodeImageFormat.Png);
```

Maintenant que vous avez appris à générer des codes-barres DataMatrix à l'aide d'Aspose.BarCode for .NET, vous pouvez facilement intégrer cette fonctionnalité dans vos applications .NET.

## Conclusion

Aspose.BarCode for .NET simplifie le processus de génération de codes-barres DataMatrix dans vos applications .NET. Avec ce guide étape par étape, vous pouvez créer des codes-barres avec différentes versions et types ECC, offrant flexibilité et personnalisation pour répondre à vos besoins spécifiques.

 Si vous avez des questions ou besoin d'aide, n'hésitez pas à visiter le[Documentation Aspose.BarCode pour .NET](https://reference.aspose.com/barcode/net/) ou consultez le[Forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13) pour le soutien.

## FAQ

### Q1 : Qu'est-ce que l'ECC dans les codes-barres DataMatrix ?

A1 : ECC (Error Correction Code) est un composant essentiel des codes-barres DataMatrix qui contribue à garantir l'intégrité des données. Différents niveaux ECC fournissent différents degrés de correction d'erreur.

### Q2 : Puis-je générer des codes-barres DataMatrix avec des dimensions personnalisées à l'aide d'Aspose.BarCode pour .NET ?

A2 : Oui, vous pouvez personnaliser les dimensions des codes-barres DataMatrix en définissant le nombre de lignes et de colonnes comme démontré dans le didacticiel.

### Q3 : Où puis-je télécharger Aspose.BarCode pour .NET ?

 A3 : Vous pouvez télécharger Aspose.BarCode pour .NET à partir de[ce lien](https://releases.aspose.com/barcode/net/).

### Q4 : Existe-t-il un essai gratuit disponible pour Aspose.BarCode pour .NET ?

 A4 : Oui, vous pouvez accéder à un essai gratuit d'Aspose.BarCode pour .NET[ici](https://releases.aspose.com/).

### Q5 : Comment puis-je obtenir une licence temporaire pour Aspose.BarCode pour .NET ?

 A5 : Pour obtenir une licence temporaire pour Aspose.BarCode pour .NET, visitez[ce lien](https://purchase.aspose.com/temporary-license/).