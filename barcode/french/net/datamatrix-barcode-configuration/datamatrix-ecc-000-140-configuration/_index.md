---
date: 2026-08-17
description: Apprenez comment créer un code‑barres datamatrix aspose en utilisant
  Aspose.BarCode pour .NET – idéal pour la génération de codes‑barres, la gestion
  des stocks et les projets de générateur de codes‑barres C#.
keywords:
- create datamatrix barcode aspose
- datamatrix barcode error correction
- barcode generation with visual studio
lastmod: 2026-08-17
linktitle: Configuration DataMatrix ECC 000-140
og_description: Créer un code‑barres datamatrix aspose en utilisant Aspose.BarCode
  pour .NET – une solution rapide et haute performance pour la gestion des stocks
  et les projets de codes‑barres C#.
og_image_alt: Guide showing C# code to generate DataMatrix ECC 000-140 barcode with
  Aspose.BarCode
og_title: Créer un code‑barres datamatrix aspose avec Aspose.BarCode pour .NET
schemas:
- author: Aspose
  dateModified: '2026-08-17'
  description: Learn how to create datamatrix barcode aspose using Aspose.BarCode
    for .NET – ideal for barcode generation inventory management and C# barcode generator
    projects.
  headline: How to create datamatrix barcode aspose with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Yes. The library is fully cross‑platform and runs on .NET 5+, .NET 6+,
      and .NET Core on Linux without additional dependencies.
    question: Can I use Aspose.BarCode for .NET on Linux servers?
  - answer: You can reuse a single `BarcodeGenerator` instance in a loop; each call
      to `Save` re‑renders the image in roughly 40‑60 ms, making it suitable for generating
      thousands of labels per minute.
    question: How does the library handle large batches of barcodes?
  - answer: No. Setting `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc140`
      automatically applies the correct error‑correction algorithm.
    question: Do I need to encode the data manually for ECC 140?
  - answer: The free trial provides full feature access, including ECC 140, but adds
      a watermark to the generated images. Apply a license for production to remove
      the watermark.
    question: Is a trial version sufficient for development?
  - answer: Absolutely. Use `generator.Parameters.Barcode.Color` and `generator.Parameters.Barcode.BackColor`
      to match your branding.
    question: Can I customize the barcode’s colors?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- C# barcode generation
- inventory management
title: Comment créer un code‑barres datamatrix aspose avec Aspose.BarCode
url: /fr/net/datamatrix-barcode-configuration/datamatrix-ecc-000-140-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code-barres datamatrix aspose avec Aspose.BarCode

Dans les logiciels modernes de chaîne d'approvisionnement, vous avez souvent besoin de **create datamatrix barcode aspose** rapidement et de manière fiable. Ce tutoriel vous guide dans la génération d'un symbole DataMatrix ECC 000‑140 avec Aspose.BarCode pour .NET, une bibliothèque qui gère le travail lourd d'encodage, de correction d'erreurs et de rendu d'image. À la fin du guide, vous disposerez d'un extrait C# prêt à l'emploi qui peut être intégré à n'importe quel projet de gestion d'inventaire .NET.

## Réponses rapides
- **Quelle est la bibliothèque principale ?** Aspose.BarCode for .NET  
- **Quel type de code-barres est couvert ?** DataMatrix ECC 000‑140  
- **Quel langage est utilisé ?** C# (C Sharp)  
- **Ai‑je besoin d'une licence ?** Un essai gratuit est disponible ; une licence est requise pour la production  
- **Temps d'implémentation typique ?** Environ 10‑15 minutes pour un générateur de base  

## Qu'est‑ce que DataMatrix ECC 000‑140 ?
DataMatrix est un code‑barres bidimensionnel qui stocke de grands volumes de données dans un carré compact. Le niveau de correction d'erreurs **ECC 000‑140** peut récupérer jusqu'à 140 % des mots de code endommagés, ce qui le rend parfait pour les environnements d'entrepôt difficiles où les étiquettes peuvent être rayées ou tachées.

## Pourquoi choisir Aspose.BarCode pour .NET ?
Aspose.BarCode pour .NET fournit une API complète et haute performance qui simplifie la création de codes‑barres pour de nombreuses symbologies, offrant une correction d'erreurs intégrée, un dimensionnement automatique et un large support de plateformes, ce qui le rend idéal pour les solutions d'inventaire et d'étiquetage de niveau entreprise.

- **API robuste :** Gère plus de 30 symbologies de codes‑barres et applique automatiquement les règles d'encodage.  
- **Cross‑platform :** Fonctionne sous Windows, macOS et Linux sans dépendances natives.  
- **Haute performance :** Génère un DataMatrix de 200 × 200 pixels en moins de 50 ms sur un CPU typique de 2,5 GHz, permettant des lignes d'étiquetage à haut débit.  

## Prérequis
1. **Visual Studio** – toute édition récente (Community, Professional ou Enterprise).  
2. **Aspose.BarCode for .NET** – téléchargez‑le depuis le [lien de téléchargement](https://releases.aspose.com/barcode/net/). Vous pouvez également visiter [ce lien](https://releases.aspose.com/) pour des ressources supplémentaires.  
3. **Un projet .NET** – prêt à référencer l'assembly Aspose.BarCode.  

## Importer les espaces de noms
Dans votre fichier C#, ajoutez la directive using requise afin de pouvoir accéder aux classes de code‑barres.

```csharp
using Aspose.BarCode.Generation;
```

**La classe `BarcodeGenerator` est le moteur central d'Aspose.BarCode pour créer des images de code‑barres.**  
**La classe `BarcodeGenerator` est le moteur central d'Aspose.BarCode qui crée et configure les images de code‑barres.**  
```csharp
using Aspose.BarCode.Generation;
```

## Cas d'utilisation de génération de code‑barres pour la gestion d'inventaire
Imaginez que vous devez étiqueter des milliers de palettes dans un centre de distribution. En générant des codes‑barres DataMatrix ECC 000‑140, vous pouvez intégrer les ID produit, les numéros de lot et les dates d'expiration dans un seul symbole résistant aux erreurs que les scanners portables lisent instantanément, réduisant les erreurs de saisie manuelle jusqu'à 95 %.

## Comment créer un code‑barres datamatrix aspose en C#
Chargez les données, configurez le générateur et enregistrez l'image – le tout en trois étapes concises. Le `BarcodeGenerator` sélectionne automatiquement la taille de module optimale et applique le niveau de correction ECC 140, vous n'avez donc pas à calculer vous‑même les valeurs de somme de contrôle, rapidement et efficacement.

### Étape 1 : définir le répertoire de sortie
Choisissez un dossier où le fichier PNG sera écrit. Le chemin doit exister avant d'appeler `Save`.

```csharp
string path = "Your Directory Path";
```

### Étape 2 : créer le générateur de code‑barres
Instanciez `BarcodeGenerator`, définissez la symbologie sur DataMatrix, fournissez la charge utile, et sélectionnez le niveau de correction d'erreurs le plus élevé.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Set the XDimension in Pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set DataMatrix ECC to 140
    gen.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;

    // Save the generated barcode image
    gen.Save($"{path}DataMatrixEcc000140.png", BarCodeImageFormat.Png);
}
```

Dans cet extrait, nous :
* Choisir **DataMatrix** comme type de code‑barres.  
* Fournir une valeur d'exemple (`"Åspóse.Barcóde©"`).  
* Définir **XDimension** pour contrôler la taille du module (4 pixels ici).  
* Sélectionner le niveau de correction d'erreurs le plus élevé (**ECC 140**).  
* Enregistrer la sortie en fichier PNG.  

## Problèmes courants et solutions
| Problème | Solution |
|----------|----------|
| **Chemin invalide** | Assurez‑vous que `path` se termine par un séparateur de répertoire (`\` ou `/`) et que le dossier existe. |
| **Caractères non pris en charge** | DataMatrix prend en charge UTF‑8 ; évitez les caractères de contrôle et utilisez le bon encodage. |
| **Licence non appliquée** | La classe `Aspose.BarCode.License` applique une licence commerciale pour débloquer toutes les fonctionnalités. Appelez‑la avant de générer tout code‑barres. |

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.BarCode pour .NET sur des serveurs Linux ?**  
R : Oui. La bibliothèque est entièrement cross‑platform et fonctionne sur .NET 5+, .NET 6+ et .NET Core sous Linux sans dépendances supplémentaires.

**Q : Comment la bibliothèque gère‑t‑elle de gros lots de codes‑barres ?**  
R : Vous pouvez réutiliser une seule instance de `BarcodeGenerator` dans une boucle ; chaque appel à `Save` re‑rend l'image en environ 40‑60 ms, ce qui la rend adaptée à la génération de milliers d'étiquettes par minute.

**Q : Dois‑je encoder les données manuellement pour ECC 140 ?**  
R : Non. Le réglage `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc140` applique automatiquement l'algorithme de correction d'erreurs approprié.

**Q : Une version d'essai suffit‑elle pour le développement ?**  
R : L'essai gratuit donne un accès complet aux fonctionnalités, y compris ECC 140, mais ajoute un filigrane aux images générées. Appliquez une licence pour la production afin de supprimer le filigrane.

**Q : Puis‑je personnaliser les couleurs du code‑barres ?**  
R : Absolument. Utilisez `generator.Parameters.Barcode.Color` et `generator.Parameters.Barcode.BackColor` pour correspondre à votre identité visuelle.

---

**Dernière mise à jour :** 2026-08-17  
**Testé avec :** Aspose.BarCode 24.11 pour .NET  
**Auteur :** Aspose

## Tutoriels associés

- [Comment générer des codes‑barres DataMatrix (ECC 200) avec Aspose.BarCode pour .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Maîtriser l'encodage DataMatrix en ASCII avec Aspose.BarCode pour .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Comment lire les codes‑barres DataMatrix avec Aspose.BarCode pour .NET](/barcode/net/datamatrix-barcode-reading/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}