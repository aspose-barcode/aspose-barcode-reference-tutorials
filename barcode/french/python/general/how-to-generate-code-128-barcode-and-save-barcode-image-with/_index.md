---
category: general
date: 2026-09-23
description: Apprenez à générer un code‑barres Code 128 et à enregistrer l’image du
  code‑barres en utilisant Aspose.BarCode en Python – guide étape par étape.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate code 128 barcode
- save barcode image
- Aspose.BarCode Python
- extended codetext builder
- barcode PNG export
language: fr
lastmod: 2026-09-23
og_description: Générez un code‑barres Code 128 et enregistrez l’image du code‑barres
  avec Aspose.BarCode en Python. Suivez cet exemple complet pour créer, personnaliser
  et exporter le code‑barres au format PNG.
og_image_alt: Python-generated Code 128 barcode saved as PNG image
og_title: Générer un code-barres Code 128 et enregistrer l’image du code-barres –
  Guide Python
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to generate Code 128 barcode and save barcode image using
    Aspose.BarCode in Python – step‑by‑step guide.
  headline: How to generate Code 128 barcode and save barcode image with Aspose.BarCode
  type: TechArticle
tags:
- barcode
- Code 128
- Python
- Aspose
title: Comment générer un code‑barres Code 128 et enregistrer l’image du code‑barres
  avec Aspose.BarCode
url: /fr/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer un code‑barres Code 128 et enregistrer l’image du code‑barres avec Aspose.BarCode

Si vous devez **générer un code‑barres Code 128** et **enregistrer l’image du code‑barres** dans un projet Python, ce tutoriel montre les étapes exactes. En utilisant `ExtCodetextBuilder` d’Aspose.BarCode, vous pouvez intégrer du texte brut et des segments Unicode dans une même charge utile, puis rendre le résultat sous forme de fichier PNG.

Vous verrez un script complet et exécutable, une explication de chaque ligne, ainsi que des astuces pour les problèmes courants tels que la gestion du codage ECI ou le choix du bon dossier de sortie. Aucune documentation externe n’est requise — il suffit de copier, coller et exécuter.

## Prérequis

* Python 3.8+ installé.
* Le package `aspose.barcode` (installer avec `pip install aspose-barcode`).
* Permission d’écriture sur le répertoire où le PNG sera enregistré.

Le code fonctionne avec n’importe quelle symbologie prise en charge par Aspose.BarCode, mais l’exemple se concentre sur **Code 128** car il encode efficacement les données alphanumériques et prend en charge les jeux de caractères étendus.

## Étape 1 : Importer les classes requises

```python
import barcode                     # Core Aspose.BarCode namespace
from barcode import BarCodeWriter, BarCodeEncodeMode, BarCodeImageFormat
from barcode import ExtCodetextBuilder, BuildVersionInfo
```

*Pourquoi cette étape ?* L’importation des classes vous donne accès au constructeur de texte étendu, au writer qui crée l’image, et à l’aide de version qui peut être utile pour déboguer les mises à jour de la bibliothèque.

## Étape 2 : Construire le texte codé étendu

```python
# Create a builder for extended codetext
builder = ExtCodetextBuilder()

# Add plain text (no ECI) – this part is simple ASCII
builder.add_plain_codetext("ABC123")

# Add a Unicode segment with ECI 0x03 (UTF‑8). The word “Пример” means “Example” in Russian.
builder.add_eci_codetext(0x03, "Пример")

# Retrieve the full extended codetext string
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

Le `ExtCodetextBuilder` vous permet de mélanger des données ASCII simples et Unicode dans une seule charge utile de code‑barres. Le octet ECI (Extended Channel Interpretation) `0x03` indique au scanner que les octets suivants sont encodés en UTF‑8, ce qui est essentiel pour des langues comme le russe, le chinois ou l’arabe.

## Étape 3 : Configurer le writer de code‑barres pour Code 128

```python
writer = BarCodeWriter()
writer.encode_type = BarCodeEncodeMode.CODE_128   # Choose Code 128 symbology
writer.code_text = extended_codetext
```

Définir `encode_type` sur `CODE_128` indique au writer de rendre un **code‑barres Code 128**. La propriété `code_text` reçoit la chaîne étendue construite à l’étape précédente.

## Étape 4 : Enregistrer l’image du code‑barres au format PNG

```python
output_path = "YOUR_DIRECTORY/extended_codetext.png"
writer.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode image saved to {output_path}")
```

La méthode `save` écrit le code‑barres dans un fichier. Utiliser `BarCodeImageFormat.PNG` garantit une compression sans perte et une large compatibilité avec les applications web et mobiles.

## Étape 5 (facultatif) : Vérifier la version de la bibliothèque Aspose.BarCode

```python
version_info = BuildVersionInfo()
print("Assembly version :", version_info.ASSEMBLY_VERSION)
print("Product version   :", f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR}")
print("Release date      :", version_info.RELEASE_DATE)
```

Connaître la version exacte de la bibliothèque aide lorsqu’il faut signaler des bugs ou comparer le comportement entre différentes versions.

## Résultat attendu

L’exécution du script produit une sortie console similaire à :

```
Extended codetext: ABC123[ECI=03]Пример
Assembly version : 23.12.0.0
Product version   : 23.12
Release date      : 2023-12-01
Barcode image saved to YOUR_DIRECTORY/extended_codetext.png
```

Le PNG généré (`extended_codetext.png`) ressemble à ceci :

![Code‑barres Code 128 généré par Python enregistré en image PNG](images/code128_extended.png)

*L’image montre un code‑barres Code 128 qui encode à la fois la chaîne ASCII `ABC123` et le mot russe « Пример ».*

## Questions fréquentes et gestion des cas limites

| Question | Answer |
|----------|--------|
| **Puis-je utiliser une symbologie différente ?** | Oui. Remplacez `BarCodeEncodeMode.CODE_128` par tout autre mode pris en charge tel que `QR`, `EAN_13` ou `PDF_417`. |
| **Et si mon texte Unicode contient des emojis ?** | Les emojis sont également des caractères UTF‑8, donc le même appel `add_eci_codetext` fonctionne. Assurez‑vous que le scanner cible prend en charge l’ECI que vous utilisez. |
| **Comment modifier la taille de l’image ?** | Définissez `writer.x_dimension` et `writer.bar_height` avant d’appeler `save`. |
| **Quel dossier dois‑je utiliser pour `output_path` ?** | Tout dossier dans lequel le processus Python peut écrire. Utilisez `os.makedirs` avec `exist_ok=True` pour le créer automatiquement. |

## Astuces professionnelles

* **Évitez de coder en dur les chemins.** Utilisez `os.path.join` et `Path` du module `pathlib` pour une compatibilité multiplateforme.
* **Validez le code‑barres.** Après l’enregistrement, vous pouvez relire l’image avec `barcode.BarCodeReader` pour confirmer que le texte encodé correspond à `extended_codetext`.
* **Astuce de performance.** Si vous générez de nombreux codes‑barres dans une boucle, réutilisez une seule instance de `BarCodeWriter` et ne mettez à jour que `code_text` à chaque itération.

## Conclusion

Vous savez maintenant comment **générer un code‑barres Code 128** avec des données ASCII et Unicode mixtes et **enregistrer l’image du code‑barres** au format PNG en utilisant Aspose.BarCode avec Python. Le script complet couvre la construction du texte codé étendu, la configuration du writer, l’exportation de l’image et la vérification des versions de la bibliothèque.

À partir d’ici, vous pouvez explorer :

* Ajouter des couleurs de premier plan/arrière‑plan (`writer.back_color`, `writer.fore_color`).
* Intégrer le code‑barres dans des PDF avec `Aspose.PDF`.
* Utiliser la classe `BarCodeReader` pour décoder l’image enregistrée et vérifier le contenu automatiquement.

Bon codage, et n’hésitez pas à expérimenter d’autres symbologies et formats d’image !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Générer un code‑barres Code128 avec Aspose.Barcode Python – Guide complet](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [Comment générer un code‑barres en Python – guide complet étape par étape](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Comment générer une image de code QR en Python avec Aspose.Barcode – Guide complet](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}