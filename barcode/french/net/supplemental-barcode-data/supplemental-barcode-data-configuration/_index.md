---
date: 2026-03-07
description: Apprenez à créer un code‑barres EAN‑13 avec des données complémentaires
  en C# en utilisant Aspose.BarCode pour .NET – générez rapidement un PNG de code‑barres.
linktitle: Supplemental Barcode Data Configuration
second_title: Aspose.BarCode .NET API
title: Créer un code‑barres EAN‑13 avec données supplémentaires – Aspose.BarCode
url: /fr/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code-barres EAN-13 avec données supplémentaires – Aspose.BarCode pour .NET

Dans ce tutoriel pratique, vous allez **créer un code-barres EAN-13** qui inclut des données supplémentaires EAN‑2 ou EAN‑5, et vous verrez comment **générer des fichiers PNG de code-barres** en quelques lignes de C#. Que vous construisiez un système de caisse pour le commerce de détail, une application logistique ou un simple outil d'inventaire, la capacité d'ajouter des informations supplémentaires rend vos codes-barres beaucoup plus utiles.

## Réponses rapides
- **Que signifie « données supplémentaires » ?** Chiffres supplémentaires (EAN‑2/EAN‑5) imprimés à côté du code-barres principal, souvent utilisés pour le prix ou les numéros d'édition.  
- **Quel type de code-barres est utilisé ?** EAN‑13 comme symbole principal, avec des suppléments optionnels EAN‑2 ou EAN‑5.  
- **Puis-je générer des images PNG ?** Oui – la méthode `Save` vous permet d'exporter directement en PNG.  
- **Ai-je besoin d'une licence pour le développement ?** Un essai gratuit suffit pour les tests ; une licence commerciale est requise pour la production.  
- **Cette fonctionnalité est‑elle compatible avec .NET Core / .NET 6 ?** Absolument – Aspose.BarCode prend en charge tous les runtimes .NET modernes.

## Prérequis

Avant de plonger dans le code, assurez‑vous d'avoir :
- Visual Studio (ou tout IDE compatible .NET).  
- Une copie d'Aspose.BarCode pour .NET – téléchargez‑la **[ici](https://releases.aspose.com/barcode/net/)**.  
- Connaissances de base en C#.  
- Un dossier accessible en écriture où les fichiers PNG générés seront enregistrés.

## Importation des espaces de noms

Tout d'abord, ajoutez l'espace de noms Aspose.BarCode afin de pouvoir accéder aux classes de génération :

```csharp
using Aspose.BarCode.Generation;
```

> **Astuce :** Si vous utilisez .NET Core, ajoutez le package NuGet `Aspose.BarCode` à votre projet au lieu de référencer manuellement le DLL.

## Qu’est‑ce qu’un code‑barres supplémentaire ?

Un code‑barres supplémentaire est une chaîne numérique auxiliaire imprimée à côté du code‑barres principal.  
- **EAN‑2** – supplément à deux chiffres, souvent utilisé pour les numéros d'édition des magazines.  
- **EAN‑5** – supplément à cinq chiffres, couramment utilisé pour les extensions de prix sur les articles de détail.

L'ajout de ces suppléments ne modifie pas les données principales EAN‑13 ; il fournit simplement un contexte supplémentaire que les lecteurs peuvent interpréter.

## Pourquoi utiliser Aspose.BarCode pour les données supplémentaires ?

- **API en une ligne** – configurez à la fois le code‑barres principal et son supplément dans un seul objet.  
- **Contrôle total sur les dimensions** – ajustez la dimension X, l'espacement du supplément et le format d'image.  
- **Cross‑platform** – fonctionne sur .NET Framework, .NET Core et .NET 5/6+.

## Guide étape par étape

### Étape 1 : Configurer le répertoire de sortie

Définissez où les fichiers PNG seront stockés. Remplacez le texte de substitution par un chemin réel sur votre machine.

```csharp
string path = "Your Directory Path";
```

### Étape 2 : Initialiser le générateur de code‑barres (Barcode Generator C#)

Créez une instance de `BarcodeGenerator`, en spécifiant **EAN‑13** comme type principal et en fournissant la charge utile de 13 chiffres.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

### Étape 3 : Ajuster les dimensions du code‑barres

Affinez la taille visuelle du code‑barres ainsi que l'espace réservé au supplément.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

### Étape 4 : Ajouter un supplément EAN‑2

Définissez les données supplémentaires à une valeur à deux chiffres (par ex., « 12 »). Elles apparaîtront à droite du code‑barres principal.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

### Étape 5 : Enregistrer le code‑barres EAN‑2 au format PNG

Exportez l'image. L'argument `BarCodeImageFormat.Png` garantit un fichier PNG de haute qualité.

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

### Étape 6 : Passer à un supplément EAN‑5

Modifiez `SupplementData` en une chaîne à cinq chiffres pour les extensions de prix.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

### Étape 7 : Enregistrer le code‑barres EAN‑5 au format PNG

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

> **Pourquoi cela fonctionne :** La même instance de `BarcodeGenerator` est réutilisée, vous n’avez donc qu’à modifier la propriété `SupplementData` avant chaque appel à `Save`. Cela rend le code concis et évite la création d’objets inutiles.

## Problèmes courants et astuces

- **Chemin de répertoire invalide** – assurez‑vous que le dossier existe et que l’application dispose des permissions d’écriture.  
- **Longueur de supplément incorrecte** – EAN‑2 attend exactement 2 chiffres, EAN‑5 attend 5 ; sinon une exception est levée.  
- **Image non visible** – vérifiez que `BarCodeImageFormat.Png` est utilisé ; d’autres formats (par ex., JPEG) peuvent introduire des artefacts de compression qui affectent la lisibilité par le scanner.  

## Questions fréquemment posées

### Puis‑je utiliser Aspose.BarCode pour .NET dans mon projet .NET Core ?

Oui, Aspose.BarCode pour .NET est entièrement compatible avec .NET Core, .NET 5 et .NET 6.

### Existe‑t‑il un essai gratuit disponible pour Aspose.BarCode pour .NET ?

Oui, vous pouvez l’essayer gratuitement en visitant **[ce lien](https://releases.aspose.com/)**.

### Où puis‑je obtenir une licence temporaire pour Aspose.BarCode pour .NET ?

Vous pouvez obtenir une licence temporaire depuis **[ce lien](https://purchase.aspose.com/temporary-license/)**.

### Aspose.BarCode prend‑il en charge un large éventail de types de code‑barres ?

Absolument – il prend en charge EAN‑13, QR Code, Code 128, DataMatrix, PDF‑417 et bien d’autres.

### Puis‑je personnaliser l’apparence des code‑barres générés ?

Oui, vous pouvez modifier les couleurs, les polices, les marges, et même ajouter des images d’arrière‑plan en utilisant l’API étendue `Parameters`.

## Conclusion

Vous savez maintenant comment **créer un code‑barres EAN‑13** avec des données supplémentaires EAN‑2 ou EAN‑5 et **générer des fichiers PNG de code‑barres** en utilisant Aspose.BarCode pour .NET. Cette approche vous offre un contrôle total sur les dimensions du code‑barres, l’espacement du supplément et le format de sortie, ce qui la rend idéale pour le commerce de détail, la logistique et tout scénario nécessitant des informations numériques supplémentaires.

Pour aller plus loin, consultez le guide de référence complet : **[documentation Aspose.BarCode pour .NET](https://reference.aspose.com/barcode/net/)**.

---

**Dernière mise à jour :** 2026-03-07  
**Testé avec :** Aspose.BarCode 24.11 for .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}