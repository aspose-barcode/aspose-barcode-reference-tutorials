---
date: 2026-02-28
description: Apprenez à créer un générateur de codes‑barres Aspose pour les codes‑barres
  Databar unidimensionnels 2D en .NET. Suivez notre guide pas à pas pour la configuration
  et la personnalisation.
linktitle: One-Dimensional Databar 2D Component Configuration
second_title: Aspose.BarCode .NET API
title: Créer le générateur de codes-barres Aspose – Configuration Databar 2D
url: /fr/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/
weight: 15
---

 not needed.

Make sure to preserve code block placeholders exactly.

Let's construct final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configuration du composant Databar 2D unidimensionnel

## Réponses rapides
- **À quoi sert le drapeau du composant 2D ?** Il indique au générateur s'il doit intégrer un symbole 2D composite à l'intérieur du code‑barres Databar.  
- **Puis-je modifier la X‑dimension ?** Oui, la propriété `XDimension.Pixels` contrôle la largeur du module.  
- **Quel format d'image est utilisé dans l'exemple ?** PNG, via `BarCodeImageFormat.Png`.  
- **Ai‑je besoin d'une licence pour le développement ?** Un essai gratuit suffit pour les tests ; une licence commerciale est requise pour la production.  
- **Le code est‑il compatible avec .NET Core ?** Absolument — Aspose.BarCode prend en charge .NET Framework et .NET Core.

## Qu'est‑ce qu'un composant Databar 2D unidimensionnel ?
Un composant Databar 2D combine un code‑barres linéaire traditionnel avec un petit symbole composite 2D, vous permettant de stocker des informations supplémentaires (comme une URL ou des champs de données additionnels) sans augmenter la taille globale du code‑barres.

## Pourquoi utiliser Aspose.BarCode pour cette tâche ?
- **Intégration .NET complète** – fonctionne sans problème avec les projets C#.  
- **API de configuration riche** – ajustez les dimensions, activez/désactivez le composant 2D, et choisissez parmi de nombreux formats de sortie.  
- **Aucune dépendance externe** – la bibliothèque est autonome, ce qui simplifie le déploiement.

## Prérequis

1. **Installation** – Assurez‑vous qu'Aspose.BarCode pour .NET est installé. Téléchargez‑le depuis le site web [ici](https://releases.aspose.com/barcode/net/).  
2. **Connaissances de base** – Une familiarité avec C# et le développement .NET vous aidera à suivre les étapes.  
3. **Environnement de développement** – Visual Studio, Rider, ou tout éditeur compatible C#.

Une fois ces bases couvertes, commençons à configurer le composant Databar 2D.

## Importer les espaces de noms

La première chose à faire est d'importer l'espace de noms Aspose.BarCode afin de pouvoir accéder à ses classes.

```csharp
using Aspose.BarCode;
```

## Définir le chemin de sortie

Spécifiez où les images de code‑barres générées seront enregistrées sur votre système de fichiers.

```csharp
string path = "Your Directory Path";
```

Remplacez `"Your Directory Path"` par un chemin de dossier réel sur votre machine.

## Créer un générateur de code‑barres

Instanciez le `BarcodeGenerator` avec le type Databar Expanded et fournissez les données que vous souhaitez encoder.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "(01)12345678901231");
```

N'hésitez pas à remplacer les données d'exemple par votre propre identifiant d'application GS1 ou tout autre contenu.

## Comment créer un générateur de code‑barres Aspose pour un Databar 2D unidimensionnel

Configurez maintenant les propriétés visuelles et le drapeau du composant 2D, puis enregistrez les images.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;

// Disable 2D component flag
gen.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
gen.Save($"{path}Databar2DComponentDisabled.png", BarCodeImageFormat.Png);

// Enable 2D component flag
gen.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
gen.Save($"{path}Databar2DComponentEnabled.png", BarCodeImageFormat.Png);
```

- **XDimension** contrôle la largeur de chaque module du code‑barres.  
- Mettre `Is2DCompositeComponent` à **false** génère un Databar purement linéaire.  
- Le mettre à **true** ajoute le symbole 2D composite, utile pour encoder des données supplémentaires.

## Problèmes courants et astuces

- **Chemin invalide** – Assurez‑vous que le dossier existe et que l'application dispose des permissions d'écriture.  
- **Exception de licence** – Si vous voyez un avertissement de licence, appliquez votre licence Aspose avant de générer le code‑barres.  
- **Image non visible** – Vérifiez que le `BarCodeImageFormat` correspond à l'extension de fichier que vous utilisez.

## Conclusion

Vous avez maintenant appris comment **créer un générateur de code‑barres Aspose** pour un composant Databar 2D unidimensionnel, en basculant le drapeau composite 2D et en ajustant la X‑dimension. Cette approche flexible vous permet d'adapter le code‑barres à une large gamme de scénarios métier. Pour une personnalisation plus poussée, explorez la documentation complète d'Aspose.BarCode : [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/).

Si vous avez besoin de plus d'exemples ou rencontrez des difficultés, la communauté Aspose est un excellent endroit pour poser des questions.

## FAQ

### Aspose.BarCode pour .NET est‑il compatible avec différents types de codes‑barres ?
- Oui, Aspose.BarCode pour .NET prend en charge un large éventail de types de codes‑barres, ce qui le rend très polyvalent pour diverses applications.

### Puis‑je personnaliser l'apparence des codes‑barres générés ?
- Absolument ! Vous pouvez ajuster la taille, la couleur et diverses autres propriétés visuelles du code‑barres selon vos besoins.

### Existe‑t‑il des options de licence disponibles pour Aspose.BarCode pour .NET ?
- Oui, Aspose propose des options de licence pour répondre à différents besoins. Vous pouvez les explorer sur le site web.

### Aspose.BarCode convient‑il aux débutants comme aux développeurs expérimentés ?
- Aspose.BarCode est conçu pour être convivial, le rendant adapté tant aux débutants qu'aux développeurs expérimentés.

### Où puis‑je obtenir du support et de l'aide pour Aspose.BarCode pour .NET ?
- Vous pouvez demander de l'aide et interagir avec la communauté sur le [forum de support Aspose.BarCode pour .NET](https://forum.aspose.com/c/barcode/13).

## Questions fréquemment posées

**Q : Puis‑je générer des codes‑barres dans des formats autres que PNG ?**  
A : Oui, la méthode `Save` prend en charge BMP, JPEG, GIF, TIFF, et plus en spécifiant le `BarCodeImageFormat` approprié.

**Q : Comment appliquer une couleur personnalisée au code‑barres ?**  
A : Utilisez `gen.Parameters.Barcode.ForeColor` et `gen.Parameters.Barcode.BackColor` pour définir les couleurs de premier plan et d'arrière‑plan.

**Q : Est‑il possible d'intégrer un logo dans l'image du code‑barres ?**  
A : Aspose.BarCode fournit une propriété `Image` où vous pouvez superposer un logo après la génération du code‑barres.

**Q : Quelles versions de .NET sont prises en charge ?**  
A : La bibliothèque fonctionne avec .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ et .NET 6+.

**Q : Comment améliorer la fiabilité du scan pour des impressions basse résolution ?**  
A : Augmentez la valeur de `XDimension` et assurez un contraste suffisant entre le code‑barres et l'arrière‑plan.

---

**Dernière mise à jour :** 2026-02-28  
**Testé avec :** Aspose.BarCode 24.12 for .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}