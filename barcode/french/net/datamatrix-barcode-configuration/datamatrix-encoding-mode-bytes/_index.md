---
date: 2026-05-30
description: Apprenez à générer un code-barres DataMatrix en mode Octets et à lire
  un code-barres DataMatrix en utilisant Aspose.BarCode pour .NET – un guide pas à
  pas sur les codes-barres.
keywords:
- generate datamatrix barcode
- read datamatrix barcode
- barcode generator settings
- step by step barcode
- create barcode asp.net
linktitle: Mode d'encodage DataMatrix (Octets)
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to generate DataMatrix barcode in Bytes mode and read DataMatrix
    barcode using Aspose.BarCode for .NET – a step‑by‑step barcode guide.
  headline: Generate DataMatrix Barcode in Bytes Mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to generate DataMatrix barcode in Bytes mode and read DataMatrix
    barcode using Aspose.BarCode for .NET – a step‑by‑step barcode guide.
  name: Generate DataMatrix Barcode in Bytes Mode with Aspose.BarCode for .NET
  steps:
  - name: Initialize the BarcodeGenerator
    text: '`BarcodeGenerator` is the main class used to generate barcode images for
      a given symbology and data.'
  - name: Set DataMatrix Encode Mode to Bytes
    text: '`DataMatrixEncodeMode.Bytes` tells the generator to treat the input as
      raw binary bytes rather than text.'
  - name: Set Display Text
    text: '`CodeText` property sets the human‑readable text displayed below the barcode
      symbol.'
  - name: Save the Barcode Image
    text: '`Save` method writes the generated barcode to an image file in the specified
      format.'
  - name: Try to Recognize
    text: '`BarCodeReader` reads barcode images and extracts the encoded data.'
  - name: Iterate and Display Results
    text: Iterate over `reader.ReadBarCodes()` to access each detected barcode and
      its `CodeText`. With these steps, you have successfully **generated a DataMatrix
      barcode** in Bytes mode and verified it using Aspose.BarCode for .NET. The library
      abstracts the low‑level encoding details, so you can focus on b
  type: HowTo
- questions:
  - answer: DataMatrix encoding mode defines how input data is transformed into the
      two‑dimensional pattern; Bytes mode stores raw binary bytes directly.
    question: What is DataMatrix encoding mode?
  - answer: You can obtain a free trial of Aspose.BarCode for .NET from [here](https://releases.aspose.com/).
    question: How can I get a free trial of Aspose.BarCode for .NET?
  - answer: The documentation for Aspose.BarCode for .NET is available [here](https://reference.aspose.com/barcode/net/).
    question: Where can I find documentation for Aspose.BarCode for .NET?
  - answer: Yes, Aspose.BarCode for .NET is suitable for commercial use. You can purchase
      a license from [here](https://purchase.aspose.com/buy).
    question: Is Aspose.BarCode for .NET suitable for commercial use?
  - answer: Yes, you can obtain a temporary license for Aspose.BarCode for .NET from
      [here](https://purchase.aspose.com/temporary-license/).
    question: Can I use a temporary license for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Générer un code-barres DataMatrix en mode Octets avec Aspose.BarCode pour .NET
url: /fr/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Générer un code-barres DataMatrix en mode Octets avec Aspose.BarCode pour .NET

Dans ce tutoriel, vous apprendrez comment **générer un code-barres DataMatrix** en utilisant le mode d’encodage Octets, puis **lire le code-barres DataMatrix** avec Aspose.BarCode pour .NET. Que vous construisiez un système de gestion d’entrepôt ou une application de billetterie mobile, le guide pas à pas ci‑dessous vous montre exactement comment configurer les paramètres du générateur de code-barres, produire une image de haute qualité et le décoder à nouveau — le tout en quelques lignes de C#.

## Réponses rapides
- **Puis-je générer un code-barres DataMatrix en .NET ?** Oui, utilisez `BarcodeGenerator` avec `EncodeTypes.DataMatrix` et définissez `DataMatrixEncodeMode.Bytes`.
- **Quelle méthode lit le code-barres ?** `BarCodeReader` lit l’image et renvoie le texte encodé.
- **Ai‑je besoin d’une licence pour la production ?** Une licence commerciale est requise ; un essai gratuit est disponible.
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Combien d’octets puis‑je encoder ?** Jusqu’à 1 555 octets dans un seul symbole DataMatrix.

## Qu’est‑ce que la génération d’un code-barres DataMatrix ?
**Générer un code-barres DataMatrix** signifie créer un code-barres bidimensionnel, de forme carrée, capable de stocker des données binaires. Aspose.BarCode rend le symbole sous forme d’image PNG, JPG ou SVG que tout scanner peut décoder. Il est largement utilisé pour le suivi d’inventaire, la gestion de documents et l’authentification car il offre une haute densité de données et des capacités de correction d’erreurs, le rendant fiable même sur des impressions de mauvaise qualité.

## Pourquoi utiliser le mode d’encodage Octets ?
Le mode Octets vous permet d’intégrer des données binaires brutes (jusqu’à 1 555 octets) sans les convertir en texte, ce qui est idéal pour les numéros de série, GUID ou charges utiles chiffrées. Aspose.BarCode prend en charge **plus de 30 symbologies de code‑barres** et peut traiter **des documents de plusieurs centaines de pages** sans charger le fichier complet en mémoire, garantissant des performances rapides même dans des scénarios à haut débit.

## Prérequis
Avant de plonger dans le processus d’encodage, vous devez disposer des prérequis suivants :

1. Aspose.BarCode for .NET : Pour commencer, vous devez disposer de la bibliothèque Aspose.BarCode for .NET installée. Vous pouvez la télécharger depuis [ici](https://releases.aspose.com/barcode/net/). Vous pouvez également trouver d’autres produits Aspose à [ici](https://releases.aspose.com/).
2. Votre environnement de développement : Assurez‑vous d’avoir un environnement de développement configuré, incluant Visual Studio ou tout autre IDE de votre choix.
3. Connaissances de base en C# : Ce tutoriel suppose que vous avez une compréhension de base de la programmation en C#.

Pour obtenir de l’aide, consultez [Support Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

Avec ces prérequis en place, vous êtes prêt à commencer à encoder des données au format DataMatrix en utilisant le mode Octets.

## Importer les espaces de noms
Pour utiliser Aspose.BarCode pour .NET, importez les espaces de noms requis en haut de votre fichier C# :

```csharp
using System;
using System.Text;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

Maintenant que l’environnement est prêt, parcourons les étapes exactes pour **générer un code-barres DataMatrix** puis le lire.

## Comment générer un code-barres DataMatrix en mode Octets ?
Chargez le `BarcodeGenerator`, définissez le mode d’encodage sur Octets, configurez le texte d’affichage optionnel, enregistrez l’image, puis utilisez `BarCodeReader` pour vérifier le résultat — le tout en six étapes concises. Cette approche garantit un code‑barres fiable conforme à la norme ISO/IEC 16022.

### Étape 1 : Initialiser le BarcodeGenerator
`BarcodeGenerator` est la classe principale utilisée pour générer des images de code‑barres pour une symbologie et des données données.

```csharp
string path = "Your Directory Path";
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, strBld.ToString()))
{
    // Set the XDimension in Pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
```

### Étape 2 : Définir le mode d’encodage DataMatrix sur Octets
`DataMatrixEncodeMode.Bytes` indique au générateur de traiter l’entrée comme des octets binaires bruts plutôt que comme du texte.

```csharp
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Bytes;
```

### Étape 3 : Définir le texte d’affichage
La propriété `CodeText` définit le texte lisible par l’homme affiché sous le symbole du code‑barres.

```csharp
    gen.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Bytes mode";
```

### Étape 4 : Enregistrer l’image du code‑barres
La méthode `Save` écrit le code‑barres généré dans un fichier image au format spécifié.

```csharp
    gen.Save($"{path}DataMatrixEncodeModeBytes.png", BarCodeImageFormat.Png);
```

### Étape 5 : Tenter de reconnaître
`BarCodeReader` lit les images de code‑barres et extrait les données encodées.

```csharp
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
```

### Étape 6 : Itérer et afficher les résultats
Itérez sur `reader.ReadBarCodes()` pour accéder à chaque code‑barres détecté et à son `CodeText`.

```csharp
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixEncodeModeBytes:" + BitConverter.ToString(result.CodeBytes));
    }
}
```

Avec ces étapes, vous avez réussi à **générer un code‑barres DataMatrix** en mode Octets et à le vérifier à l’aide d’Aspose.BarCode pour .NET. La bibliothèque abstrait les détails d’encodage de bas niveau, vous permettant de vous concentrer sur la logique métier plutôt que sur les mathématiques du code‑barres.

## Problèmes courants et solutions
- **Les données encodées sont tronquées** – Assurez‑vous que le tableau d’octets ne dépasse pas 1 555 octets ; sinon la bibliothèque passera automatiquement à une taille de symbole plus grande ou lèvera une exception.
- **L’image apparaît floue** – Enregistrez l’image à une résolution plus élevée (par ex., 300 dpi) en définissant `generator.Parameters.ImageResolution` avant d’appeler `Save`.
- **Le lecteur renvoie null** – Vérifiez que le chemin de l’image est correct et que le fichier n’est pas corrompu ; confirmez également que `BarCodeReader` est instancié avec `DecodeType.DataMatrix`.

## Questions fréquemment posées
**Q : Qu’est‑ce que le mode d’encodage DataMatrix ?**  
R : Le mode d’encodage DataMatrix définit comment les données d’entrée sont transformées en motif bidimensionnel ; le mode Octets stocke directement les octets binaires bruts.

**Q : Comment obtenir un essai gratuit d’Aspose.BarCode pour .NET ?**  
R : Vous pouvez obtenir un essai gratuit d’Aspose.BarCode pour .NET depuis [ici](https://releases.aspose.com/).

**Q : Où puis‑je trouver la documentation d’Aspose.BarCode pour .NET ?**  
R : La documentation d’Aspose.BarCode pour .NET est disponible [ici](https://reference.aspose.com/barcode/net/).

**Q : Aspose.BarCode pour .NET convient‑il à un usage commercial ?**  
R : Oui, Aspose.BarCode pour .NET convient à un usage commercial. Vous pouvez acheter une licence depuis [ici](https://purchase.aspose.com/buy).

**Q : Puis‑je utiliser une licence temporaire pour Aspose.BarCode pour .NET ?**  
R : Oui, vous pouvez obtenir une licence temporaire pour Aspose.BarCode pour .NET depuis [ici](https://purchase.aspose.com/temporary-license/).

---

**Dernière mise à jour :** 2026-05-30  
**Testé avec :** Aspose.BarCode 24.12 for .NET  
**Auteur :** Aspose

## Tutoriels associés
- [Maîtriser l’encodage DataMatrix en ASCII avec Aspose.BarCode pour .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Lire le code‑barres DataMatrix C# – Générer le mode DataMatrix (Auto)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Comment générer des codes‑barres DataMatrix (ECC 200) avec Aspose.BarCode pour .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}