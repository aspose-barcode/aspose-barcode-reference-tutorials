---
category: general
date: 2026-09-10
description: Encodez des caractères non ASCII dans un code QR et enregistrez l'image
  du code QR avec un constructeur Python simple. Suivez un guide étape par étape en
  utilisant ExtCodetextBuilder et BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- encode non ascii characters
- save qr code image
- extended codetext builder
- eci encoding python
- barcode generation python
language: fr
lastmod: 2026-09-10
og_description: Encodez des caractères non ASCII dans un QR code et enregistrez l'image
  du QR code avec Python. Ce tutoriel montre comment créer un texte codé étendu, générer
  un QR code et enregistrer l'image.
og_image_alt: Diagram showing encode non ASCII characters in QR code and save QR code
  image workflow
og_title: Encoder des caractères non ASCII dans un QR code et enregistrer l'image
  du QR code – guide Python étape par étape
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Encode non ASCII characters in a QR code and save QR code image with
    a simple Python builder. Follow a step‑by‑step guide using ExtCodetextBuilder
    and BarcodeGenerator.
  headline: Encode non ASCII characters in QR code and save QR code image
  type: TechArticle
tags:
- barcode
- QR code
- Python
title: Encoder les caractères non ASCII dans le code QR et enregistrer l'image du
  code QR
url: /fr/python/general/encode-non-ascii-characters-in-qr-code-and-save-qr-code-imag/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Encoder des caractères non ASCII dans un code QR et enregistrer l'image du code QR

Si vous devez **encoder des caractères non ASCII** dans un code QR, ce guide vous montre exactement comment le faire puis **enregistrer l'image du code QR** sur le disque. Que vous manipuliez des données en russe, chinois ou des emojis, l'ExtCodetextBuilder vous permet de mélanger du texte brut et des segments encodés ECI sans manipuler manuellement les octets.

Vous apprendrez comment créer une chaîne de codetext étendue, générer un code QR qui comprend cette chaîne, et enfin écrire l'image du code-barres dans un fichier. Le tutoriel suppose des connaissances de base en Python et que vous avez le SDK `barcode` installé.

## Prérequis

* Python 3.8+ installé.
* Le paquet Python `barcode` (ou le SDK approprié) qui fournit `ExtCodetextBuilder`, `CodetextEncodingType` et `BarcodeGenerator`.
* Permission d'écriture sur le répertoire où vous souhaitez **enregistrer l'image du code QR**.

Vous pouvez installer le SDK avec pip (remplacez `barcode-sdk` par le nom réel du paquet) :

```bash
pip install barcode-sdk
```

## Étape 1 : Créer un constructeur de codetext étendu

La première étape consiste à instancier `ExtCodetextBuilder`. Cet objet collecte plusieurs segments de texte et produit une chaîne unique que la symbologie du code QR peut interpréter.

```python
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Initialize the builder that will hold all text parts
ext_builder = ExtCodetextBuilder()
```

*Pourquoi c'est important* : les codes QR prennent en charge le **codetext étendu**, ce qui signifie que vous pouvez intégrer plusieurs modes d'encodage (plain, ECI, etc.) dans un même code-barres. Le constructeur abstrait le formatage de bas niveau requis par la spécification QR.

## Étape 2 : Ajouter un segment texte brut

Le texte brut est le mode par défaut et fonctionne pour les caractères ASCII. L'ajouter en premier fournit une solution de repli lisible pour les scanners qui ignorent l'ECI.

```python
# Add simple ASCII text
ext_builder.add_plain_codetext("HelloWorld")
```

Si vous omettez cette étape, le code QR ne contiendra que le segment ECI, ce que certains lecteurs plus anciens pourraient ne pas décoder correctement.

## Étape 3 : Ajouter un segment encodé ECI pour les caractères non ASCII

Pour inclure des caractères hors de la plage ASCII — tels que le cyrillique, le chinois ou les emojis — vous devez spécifier un encodage ECI (Extended Channel Interpretation). Ici nous utilisons UTF‑8 pour le mot russe « Привет ».

```python
# Add a UTF‑8 encoded segment containing non‑ASCII characters
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")  # Russian “Hi”
```

*Pourquoi cela fonctionne* : la spécification QR définit des valeurs ECI qui indiquent au scanner quel jeu de caractères appliquer. Sans le marqueur ECI, les octets bruts seraient interprétés comme ISO‑8859‑1, ce qui entraînerait une sortie illisible.

## Étape 4 : Récupérer la chaîne de codetext étendue combinée

Après avoir ajouté tous les segments souhaités, appelez `get_extended_codetext()` pour obtenir la chaîne finale attendue par le générateur de code-barres.

```python
# Combine all parts into one extended codetext string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

La valeur imprimée ressemble à une série de caractères de contrôle suivis du texte réel, mais vous n'avez jamais besoin de l'analyser manuellement.

## Étape 5 : Générer un code QR en utilisant le codetext étendu

Créez maintenant un `BarcodeGenerator`, définissez la symbologie sur QR (la seule symbologie 2‑D courante qui prend en charge le codetext étendu), et fournissez la chaîne combinée.

```python
# Initialize the QR generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)          # QR supports extended codetext
qr_generator.set_code_text(extended_codetext)
```

*Astuce* : si vous essayez le même processus avec Code‑128 ou DataMatrix, le SDK lèvera une exception car ces formats ne peuvent pas interpréter les marqueurs ECI.

## Étape 6 : Enregistrer l'image du code QR

Enfin, écrivez le code-barres dans un fichier PNG. C'est ici que vous **enregistrez l'image du code QR** pour une utilisation ultérieure.

```python
output_path = "output/qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

Assurez-vous que le dossier `output` existe ou créez-le avec `os.makedirs('output', exist_ok=True)` avant d'appeler `save`.

### Exemple complet exécutable

Assembler toutes les étapes vous donne un script autonome que vous pouvez exécuter immédiatement :

```python
import os
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Ensure the output directory exists
os.makedirs("output", exist_ok=True)

# 1️⃣ Create the builder
ext_builder = ExtCodetextBuilder()

# 2️⃣ Add plain ASCII text
ext_builder.add_plain_codetext("HelloWorld")

# 3️⃣ Add UTF‑8 encoded non‑ASCII text (Russian)
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")

# 4️⃣ Retrieve the combined string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 5️⃣ Generate QR code
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)
qr_generator.set_code_text(extended_codetext)

# 6️⃣ Save the image
output_file = "output/qr_extended.png"
qr_generator.save(output_file)
print(f"QR code saved to {output_file}")
```

**Sortie attendue** (console) :

```
Extended codetext: <binary representation showing ECI markers>
QR code saved to output/qr_extended.png
```

Ouvrir `qr_extended.png` avec n'importe quel scanner QR affichera `HelloWorldПривет`. Les scanners qui comprennent l'ECI rendront correctement les caractères cyrilliques ; les autres ne montreront que la partie ASCII.

## Questions fréquentes & cas limites

| Question | Réponse |
|----------|--------|
| *Puis-je utiliser d'autres encodages comme Shift‑JIS ?* | Oui. Remplacez `CodetextEncodingType.UTF_8` par `CodetextEncodingType.SHIFT_JIS` et fournissez le texte approprié. |
| *Que se passe-t-il si les données combinées dépassent la capacité du QR ?* | Les codes QR ont des limites de version (jusqu'à 177 × 177 modules). Si le constructeur lève une exception de taille, augmentez le niveau de correction d'erreur ou divisez les données sur plusieurs codes QR. |
| *Dois-je définir une version QR spécifique ?* | Le SDK sélectionne automatiquement la plus petite version qui convient aux données. Vous pouvez forcer une version avec `qr_generator.set_qr_version(10)` si nécessaire. |
| *L'image sera-t-elle transparente ?* | Par défaut le SDK écrit un PNG avec un fond blanc. Utilisez `qr_generator.set_background_color(Color.Transparent)` avant `save` si vous avez besoin de transparence. |

## Conclusion

Dans ce tutoriel, vous avez appris comment **encoder des caractères non ASCII** dans un code QR en utilisant `ExtCodetextBuilder` puis **enregistrer l'image du code QR** avec `BarcodeGenerator`. Le processus consiste à construire une chaîne de codetext étendue, ajouter des segments texte brut et encodés ECI, générer la symbologie QR, et enfin écrire le fichier image.

À partir d'ici, vous pouvez explorer :

* Ajouter d'autres segments ECI (différentes langues ou emojis).
* Ajuster les niveaux de correction d'erreur du QR pour une plus grande fiabilité.
* Intégrer le PNG généré dans des PDF ou des pages web.

Bon codage, et amusez‑vous à créer des codes QR multilingues !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités d'API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment générer une image de code QR en Python avec Aspose.Barcode – Guide complet](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Générer un code-barres Code128 avec Aspose.Barcode Python – Guide complet](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [afficher le nom du produit avec la bibliothèque de code-barres Python – guide étape par étape](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}