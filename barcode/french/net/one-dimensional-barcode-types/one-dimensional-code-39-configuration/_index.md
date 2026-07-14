---
date: 2026-02-25
description: Apprenez à générer des images de code‑barres en utilisant Aspose.BarCode
  pour .NET. Ce guide étape par étape montre comment générer des codes‑barres Code 39
  avec et sans somme de contrôle.
linktitle: One-Dimensional Code 39 Configuration
second_title: Aspose.BarCode .NET API
title: Comment générer un code‑barres – Configuration du Code 39 avec Aspose.BarCode
url: /fr/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/
weight: 11
---

 final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configuration du Code 39 unidimensionnel

## Introduction

Dans ce tutoriel, vous apprendrez **comment générer des images de code‑barres**, en particulier des codes‑barres Code 39 unidimensionnels, en utilisant Aspose.BarCode for .NET. Les codes‑barres jouent un rôle crucial dans les entreprises modernes, du suivi des stocks à la récupération rapide et précise des données. Aspose.BarCode for .NET est une bibliothèque puissante qui simplifie la génération et la personnalisation des codes‑barres dans les applications .NET. Ce guide étape par étape découpe le processus en morceaux faciles à digérer, garantissant que même les développeurs novices en génération de codes‑barres puissent suivre.

## Réponses rapides
- **Quelle est la bibliothèque principale ?** Aspose.BarCode for .NET  
- **Puis-je créer un code‑barres avec somme de contrôle ?** Oui – définissez `IsChecksumEnabled = EnableChecksum.Yes`  
- **La somme de contrôle est‑elle obligatoire ?** Non – vous pouvez générer un code‑barres sans somme de contrôle en la désactivant  
- **Quel format d'image est utilisé dans les exemples ?** PNG (`BarCodeImageFormat.Png`)  
- **Ai‑je besoin d'une licence pour le développement ?** Une licence temporaire est disponible pour l'évaluation  

## Qu'est‑ce que la génération de code‑barres avec Aspose.BarCode ?

La génération de code‑barres consiste à convertir du texte ou des données numériques en un motif visuel lisible par machine. Aspose.BarCode for .NET prend en charge des dizaines de symbologies, dont le Code 39, et vous permet de contrôler tout, de la taille et la couleur au calcul de la somme de contrôle.

## Pourquoi utiliser le Code 39 et les options de somme de contrôle ?

Le Code 39 est largement adopté dans la logistique et la fabrication car il encode des données alphanumériques sans caractères spéciaux. Ajouter une somme de contrôle (ou la laisser de côté) vous permet d'équilibrer la détection d'erreurs avec la simplicité—parfait pour les étiquettes d'inventaire, les étiquettes d'expédition ou les systèmes de point de vente simples.

## Prérequis

Avant de commencer, assurez‑vous de disposer de ce qui suit :

1. **Environnement de développement .NET** – une connaissance pratique du framework .NET et d'un IDE tel que Visual Studio. Si vous êtes nouveau sur .NET, commencez par la documentation officielle : [Microsoft .NET Documentation](https://docs.microsoft.com/en-us/dotnet/).  
2. **Aspose.BarCode for .NET** – téléchargez et installez la bibliothèque. La documentation et les téléchargements sont disponibles ici : [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/) et [Download Aspose.BarCode for .NET](https://releases.aspose.com/barcode/net/).

Maintenant que nous avons couvert les prérequis, passons aux étapes principales de création de codes‑barres Code 39 unidimensionnels.

## Comment générer un code‑barres : importer les espaces de noms

Pour commencer à travailler avec Aspose.BarCode for .NET, importez les espaces de noms nécessaires dans votre projet. Ajouter ces instructions `using` vous donne accès aux classes de génération de code‑barres.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## Comment générer un code‑barres Code 39 (avec et sans somme de contrôle)

Ci‑dessous, nous créerons deux codes‑barres : un **sans somme de contrôle** et un **avec somme de contrôle**. Le code est identique sauf pour le drapeau `IsChecksumEnabled`.

```csharp
// The path to the documents directory.
string path = "Your Directory Path";
System.Console.WriteLine("OneCSCode39:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code39Extended, "CODE");

// Example 1: Create a Code 39 barcode without checksum
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.No;
gen.Save($"{path}OneCSCode39WithoutChecksum.png", BarCodeImageFormat.Png);

// Example 2: Create a Code 39 barcode with checksum
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Save($"{path}OneCSCode39WithChecksum.png", BarCodeImageFormat.Png);
```

**Ce que fait le code**

1. **Instancier** `BarcodeGenerator` avec `EncodeTypes.Code39Extended` et la chaîne de données `"CODE"`.  
2. **Basculer** `IsChecksumEnabled` pour contrôler si un chiffre de somme de contrôle est ajouté.  
3. **Enregistrer** chaque code‑barres sous forme de fichier PNG dans le dossier spécifié.

Vous avez maintenant deux images de code‑barres prêtes à l'emploi : `OneCSCode39WithoutChecksum.png` et `OneCSCode39WithChecksum.png`.

## Problèmes courants et solutions
| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| **Chemin d'accès introuvable** | La variable `path` pointe vers un dossier inexistant. | Assurez‑vous que le répertoire existe ou utilisez `Directory.CreateDirectory(path)`. |
| **Caractères invalides dans les données** | Code 39 ne prend en charge que les alphanumériques et quelques symboles spéciaux. | Utilisez le Code 39 étendu (`Code39Extended`) qui prend en charge l'ensemble complet ASCII, comme montré ci‑dessus. |
| **Erreur de somme de contrôle** | Oubli de définir `IsChecksumEnabled` lorsque requis. | Définissez explicitement le drapeau sur `EnableChecksum.Yes` ou `No` selon votre scénario. |

## Questions fréquemment posées (FAQ) :

### Q : Puis‑je utiliser Aspose.BarCode for .NET avec d'autres langages de programmation ?
A : Aspose.BarCode est principalement conçu pour .NET, mais Aspose propose également des bibliothèques de code‑barres pour d'autres plateformes.

### Q : Existe‑t‑il des options de licence disponibles pour Aspose.BarCode for .NET ?
A : Oui, vous pouvez explorer les options de licence et demander une licence temporaire sur le site Aspose : [Aspose.BarCode Licensing](https://purchase.aspose.com/temporary-license/).

### Q : Aspose.BarCode for .NET convient‑il aux applications web ?
A : Oui, Aspose.BarCode for .NET peut être utilisé dans les applications web, ce qui le rend adapté à un large éventail de projets de développement.

### Q : Puis‑je personnaliser l'apparence des codes‑barres générés ?
A : Absolument, vous pouvez personnaliser divers aspects du code‑barres, y compris la taille, les couleurs et les polices.

### Q : Où puis‑je obtenir du support ou poser des questions sur Aspose.BarCode for .NET ?
A : Vous pouvez trouver des réponses à vos questions et demander de l'aide sur le forum Aspose.BarCode : [Aspose.BarCode Forum](https://forum.aspose.com/c/barcode/13).

## Questions supplémentaires fréquemment posées

**Q : Quelle est la différence entre un code‑barres avec somme de contrôle et un sans ?**  
A : Une somme de contrôle ajoute un chiffre supplémentaire qui aide à détecter les erreurs de transcription. Utilisez‑la lorsque l'intégrité des données est cruciale.

**Q : Quelle taille peut avoir le PNG généré ?**  
A : La taille est contrôlée via `gen.Parameters.ImageWidth/Height`. Ajustez ces propriétés avant d'appeler `Save`.

**Q : Puis‑je générer des codes‑barres dans d'autres formats d'image ?**  
A : Oui, Aspose.BarCode prend en charge JPEG, BMP, GIF, TIFF, et plus—il suffit de changer l'énumération `BarCodeImageFormat`.

**Q : Existe‑t‑il une façon de générer des codes‑barres dans une application web sans écrire sur le disque ?**  
A : Vous pouvez enregistrer dans un `MemoryStream` et renvoyer le tableau d'octets directement au client.

## Conclusion
En suivant ces étapes simples, vous pouvez **générer des images de code‑barres** en .NET avec un contrôle complet sur la gestion de la somme de contrôle, le format d'image et le style visuel. Que vous gériez des stocks, traitiez des commandes ou construisiez un portail web compatible code‑barres, Aspose.BarCode for .NET offre une solution fiable et conviviale pour les développeurs.

---

**Dernière mise à jour :** 2026-02-25  
**Testé avec :** Aspose.BarCode 24.11 for .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}