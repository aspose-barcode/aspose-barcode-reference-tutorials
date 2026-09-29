---
category: general
date: 2026-07-30
description: Créez un code‑barres Databar Stacked Omnidirectional en Python. Suivez
  ce guide étape par étape pour configurer le rapport d’aspect, la XDimension et exporter
  le PNG à l’aide d’un générateur de codes‑barres Python.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked omnidirectional
- python barcode generator
- databar aspect ratio
- xdimension pixel size
- barcodeimageformat png
language: fr
lastmod: 2026-07-30
og_description: Créez un code‑barres Databar Stacked Omnidirectional en Python. Ce
  tutoriel montre comment définir XDimension, ajuster le rapport d’aspect du DataBar
  et enregistrer au format PNG avec BarCodeImageFormat.
og_image_alt: Screenshot of a Databar Stacked Omnidirectional barcode saved as a PNG
  file
og_title: Créer un code‑barres omnidirectionnel Databar empilé – Tutoriel Python
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Create Databar Stacked Omnidirectional barcode in Python. Follow this
    step‑by‑step guide to configure aspect ratio, XDimension, and export PNG using
    a python barcode generator.
  headline: Create Databar Stacked Omnidirectional Barcode in Python
  type: TechArticle
tags:
- barcode
- python
- databar
title: Créer un code‑barres Databar empilé omnidirectionnel en Python
url: /fr/python-java/general/create-databar-stacked-omnidirectional-barcode-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code-barres Databar empilé omnidirectional en Python

Vous avez déjà eu besoin de **créer un code-barres databar empilé omnidirectional** en Python mais vous ne saviez pas par où commencer ? Vous n'êtes pas seul—de nombreux développeurs rencontrent ce problème lorsqu'ils utilisent pour la première fois la classe `BarcodeGenerator`. La bonne nouvelle, c'est que le processus complet est assez simple une fois que vous avez compris les propriétés clés.

Dans ce guide, nous parcourrons un exemple complet et exécutable qui utilise un **générateur de code-barres python** pour définir le XDimension, ajuster le ratio d’aspect DataBar, et enfin exporter deux fichiers PNG. À la fin, vous aurez une bonne maîtrise de la génération de symboles empilés omnidirectionnels de haute qualité pour tout projet d’inventaire ou de logistique.

## Ce que vous apprendrez

- Comment instancier un générateur **databar stacked omnidirectional** avec une charge utile GTIN‑14.  
- Pourquoi la **taille en pixels XDimension** est importante pour la fiabilité du scan.  
- L’impact du **ratio d’aspect DataBar** sur la largeur vs. la hauteur des rangées.  
- Comment enregistrer le résultat en tant que fichier **BarCodeImageFormat PNG**.  
- Conseils pour réutiliser le même objet générateur afin de produire plusieurs variantes sans surcharge mémoire supplémentaire.

### Prérequis

- Python 3.8+ (la bibliothèque que nous utilisons est pure‑Python, aucune roue compilée n’est requise).  
- Le package `barcode-generator` (installer via `pip install barcode-generator`).  
- Un dossier dans lequel vous pouvez écrire – le script y déposera deux images PNG.

Si vous êtes à l’aise avec les importations Python de base et le code orienté objet, vous êtes prêt à démarrer.

## Créer un code-barres Databar empilé omnidirectional – Vue d’ensemble des étapes

Ci-dessous, nous décomposons le flux de travail en six étapes faciles. Chaque étape est un bloc de code autonome que vous pouvez copier‑coller dans un REPL ou un fichier script. N’hésitez pas à expérimenter—modifier le ratio d’aspect ou le XDimension vous donnera instantanément un style visuel différent.

---

## Étape 1 : Créer le générateur Databar empilé omnidirectional

La première chose que nous faisons est d'**instancier le générateur databar stacked omnidirectional**, en passant l'énumération `EncodeTypes` appropriée et la chaîne de données.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1 – initialize the generator with a GTIN‑14 payload
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)
```

> **Pourquoi c’est important :** Le drapeau `EncodeTypes.DatabarStackedOmniDirectional` indique à la bibliothèque de produire un symbole empilé omnidirectional, qui est la seule variante DataBar capable d’encoder jusqu’à 14 chiffres tout en restant lisible sous n’importe quel angle.

---

## Configurer la taille en pixels XDimension

La **taille en pixels XDimension** contrôle le plus petit module (la barre noire la plus fine). Une valeur de `2` pixels fonctionne bien pour la plupart des scénarios d’affichage à l’écran.

```python
# Step 2 – set the smallest module to 2 pixels
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2
```

> **Astuce :** Si vous prévoyez d’imprimer le code-barres à haute résolution DPI, augmentez cette valeur à 3 ou 4 pour éviter les bords flous.

---

## Ajuster le ratio d’aspect DataBar (15)

Le **ratio d’aspect DataBar** détermine la largeur de chaque rangée par rapport à sa hauteur. Un ratio d’aspect de `15` produit des rangées plus larges, ce que de nombreux lecteurs préfèrent pour une capture rapide en mouvement.

```python
# Step 3 – make rows wider (aspect ratio = 15)
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
```

> **Pourquoi 15 ?** La spécification officielle GS1 recommande un ratio compris entre 10 et 20 pour les symboles empilés omnidirectionnels. Nous choisissons `15` comme valeur par défaut équilibrée.

---

## Exporter le code-barres en PNG avec BarCodeImageFormat

Maintenant que le générateur est configuré, nous sauvegardons l’image. L’énumération `BarCodeImageFormat.Png` garantit une sortie sans perte, parfaite pour le traitement en aval.

```python
# Step 4 – save the first PNG with the 15 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR15.png",
    BarCodeImageFormat.Png
)
```

> **Ce que vous verrez :** Ouvrez le PNG généré ; vous devriez remarquer un code-barres net, à fort contraste, avec des rangées relativement larges.

---

## Modifier le ratio d’aspect DataBar à 30

Parfois, vous avez besoin de rangées plus hautes plutôt que plus larges—peut-être pour s’adapter à une étiquette étroite. Passer le **ratio d’aspect DataBar** à `30` rend chaque rangée plus haute.

```python
# Step 5 – increase the aspect ratio to make rows taller
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
```

> **Cas limite :** Des ratios très élevés (par ex., >40) peuvent faire dépasser le code-barres les hauteurs d’étiquette typiques, il faut donc tester sur une vraie imprimante avant de valider.

---

## Exporter à nouveau le code-barres avec le nouveau ratio d’aspect

Enfin, nous réutilisons le même objet `barcode_generator` pour écrire un deuxième PNG. Pas besoin de recréer le générateur—il suffit de modifier la propriété et d’appeler `Save` à nouveau.

```python
# Step 6 – save the second PNG with the 30 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR30.png",
    BarCodeImageFormat.Png
)
```

> **Résultat :** Vous avez maintenant deux fichiers PNG—un avec des rangées larges (`AR15`) et un autre avec des rangées hautes (`AR30`). Comparez-les côte à côte pour décider lequel convient le mieux à votre configuration de lecteur.

---

## Exemple complet fonctionnel

En rassemblant le tout, voici le script complet que vous pouvez exécuter immédiatement. Remplacez `YOUR_DIRECTORY` par un chemin absolu sur votre machine.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1️⃣ Initialize generator
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)

# 2️⃣ Set smallest module (XDimension)
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2

# 3️⃣ First aspect ratio – wider rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR15.png", BarCodeImageFormat.Png)

# 4️⃣ Second aspect ratio – taller rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR30.png", BarCodeImageFormat.Png)

print("✅ Two PNG files created – AR15 and AR30")
```

**Sortie attendue** (dans votre console) :

```
✅ Two PNG files created – AR15 and AR30
```

Et deux fichiers image apparaissent dans le dossier cible, prêts pour les tests de lecture.

---

## Conclusion

Nous venons d’**créer des codes-barres databar stacked omnidirectional** en Python, d’ajuster la **taille en pixels XDimension**, d’expérimenter deux réglages différents du **ratio d’aspect DataBar**, et d’exporter les résultats en fichiers **BarCodeImageFormat PNG**. L’ensemble du flux de travail tient en quelques lignes, tout en vous offrant un contrôle complet sur les caractéristiques visuelles les plus importantes pour les lecteurs.

Et ensuite ? Essayez de remplacer la charge utile par un autre GTIN, jouez avec les couleurs en convertissant le PNG en image à palette, ou générez un rapport PDF qui intègre les deux PNG côte à côte. La classe `BarcodeGenerator` est suffisamment flexible pour gérer tous ces scénarios, alors n’hésitez pas à expérimenter.

Des questions sur un cas d’utilisation particulier ou une erreur rencontrée ? Laissez un commentaire ci‑dessous, et je serai heureux d’aider. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}