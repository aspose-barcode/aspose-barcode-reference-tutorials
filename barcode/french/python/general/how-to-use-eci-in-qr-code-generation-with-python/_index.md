---
category: general
date: 2026-11-20
description: Apprenez à utiliser l'ECI, à générer un QR à partir du texte, à réinitialiser
  le constructeur et à enregistrer l'image QR en utilisant la bibliothèque Python
  de codes-barres.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use eci
- generate qr from text
- how to clear builder
- save qr image
- clear qr builder
language: fr
lastmod: 2026-11-20
og_description: Comment utiliser l'ECI pour générer un QR à partir du texte, effacer
  le générateur de QR et enregistrer l'image QR – un guide complet étape par étape.
og_image_alt: Diagram illustrating how to use ECI to generate a QR code and save the
  QR image
og_title: Comment utiliser l'ECI dans la génération de QR codes avec Python
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to use ECI, generate QR from text, clear the builder, and
    save QR image using the Python barcode library.
  headline: How to use ECI in QR code generation with Python
  type: TechArticle
tags:
- QR code
- Python
- barcode
- ECI
title: Comment utiliser l’ECI dans la génération de QR codes avec Python
url: /fr/python/general/how-to-use-eci-in-qr-code-generation-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment utiliser l'ECI dans la génération de QR code avec Python

Si vous avez besoin de **comment utiliser eci** lors de la création de QR codes, ce guide montre les étapes exactes. Vous verrez comment générer un QR à partir de texte, réinitialiser le builder, puis enregistrer l'image du QR — le tout en quelques lignes de Python.

Les QR codes contenant des données multilingues nécessitent souvent un segment Extended Channel Interpretation (ECI) afin que les lecteurs sachent quel jeu de caractères appliquer. Ce tutoriel vous explique comment construire un codetext étendu, réinitialiser le builder lorsqu’on le réutilise, et persister le résultat sous forme de fichier PNG.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

- Python 3.8+ installé.
- Le package Aspose.BarCode for Python via .NET (ou toute bibliothèque `barcode` compatible qui fournit `ExtCodetextBuilder` et `BarcodeGenerator`).
- Une connaissance de base des concepts de QR code.

Installez la bibliothèque avec pip :

```bash
pip install aspose-barcode
```

> **Astuce :** Utilisez un environnement virtuel pour éviter les conflits de versions.

## Étape 1 : Importer les classes requises

Les classes principales avec lesquelles vous allez travailler sont `ExtCodetextBuilder` pour construire le codetext étendu et `BarcodeGenerator` pour rendre le QR code.

```python
from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
```

Ces imports vous donnent accès aux méthodes du builder (`add_plain_codetext`, `add_eci_codetext`, etc.) ainsi qu’aux fonctions du générateur `set_code_text`, `set_symbology` et `save`.

## Étape 2 : Créer et configurer le ExtCodetextBuilder

Créer une nouvelle instance du builder est le premier exemple concret de **comment utiliser eci**. Vous pouvez également réinitialiser le builder plus tard si vous devez le réutiliser.

```python
# Create an ExtCodetextBuilder instance
extended_text_builder = ExtCodetextBuilder()

# Optional: clear any previous items (useful when reusing the same builder)
extended_text_builder.clear()   # this demonstrates how to clear builder
```

Appeler `clear()` garantit que le builder démarre dans un état propre, ce qui est essentiel lorsqu’on génère plusieurs QR codes dans une boucle.

## Étape 3 : Ajouter du codetext simple (sans ECI)

Le texte simple ne nécessite pas de segment ECI. Utilisez `add_plain_codetext` pour les chaînes compatibles ASCII.

```python
# Add plain codetext (e.g., an English phrase)
extended_text_builder.add_plain_codetext("HelloWorld")
```

Le builder contient maintenant le segment simple `"HelloWorld"`.

## Étape 4 : Ajouter un segment encodé ECI

Voici le cœur de **comment utiliser eci** : vous spécifiez la valeur ECI (26 pour UTF‑8) et fournissez la chaîne Unicode que vous souhaitez encoder. Cela permet au QR code de contenir du russe, du chinois ou toute autre langue non couverte par le jeu de caractères ISO‑8859‑1 par défaut.

```python
# Add ECI‑encoded codetext (ECI value 26 = UTF‑8, Russian “Hello”)
extended_text_builder.add_eci_codetext(26, "Привет")
```

> **Pourquoi c’est important :** Sans l’indicateur ECI, un lecteur interpréterait les octets avec le jeu de caractères par défaut et afficherait des caractères corrompus pour du texte non‑ASCII.

## Étape 5 : Récupérer la chaîne de codetext étendu combinée

Après avoir ajouté tous les segments requis, récupérez la chaîne finale qui sera transmise au générateur de QR.

```python
combined_extended_text = extended_text_builder.get_extended_codetext()
print("Extended codetext:", combined_extended_text)
```

La valeur affichée ressemble à quelque chose comme :

```
Extended codetext: [ECI26]ПриветHelloWorld
```

Le format exact dépend de la bibliothèque, mais l’élément essentiel est que le marqueur ECI (`[ECI26]`) précède la charge utile UTF‑8.

## Étape 6 : Générer le QR code avec le texte combiné

Vous pouvez maintenant **générer QR à partir de texte** en passant le codetext étendu à `BarcodeGenerator`.

```python
# Initialize the QR generator
qr_generator = barcode.generation.BarcodeGenerator()

# Assign the combined extended codetext
qr_generator.set_code_text(combined_extended_text)

# Choose QR symbology (the library supports many, QR is the most common)
qr_generator.set_symbology(barcode.Symbology.QR)

# Save the QR image to disk – this demonstrates how to save QR image
output_path = "qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

Lorsque vous ouvrez `qr_extended.png`, un QR code apparaît qui encode à la fois la chaîne anglaise simple et le salut russe. Le scanner moderne affichera correctement “HelloWorld” et “Привет”.

### Pourquoi appeler `clear()` avant de réutiliser le builder

Si vous générez plusieurs QR codes dans une boucle, oublier de nettoyer le builder concaténera les anciens segments avec les nouveaux, produisant un code invalide. Voici un petit modèle :

```python
for text, eci, unicode_str in data_set:
    extended_text_builder.clear()                       # ensures a fresh start
    extended_text_builder.add_plain_codetext(text)
    extended_text_builder.add_eci_codetext(eci, unicode_str)
    qr_generator.set_code_text(extended_text_builder.get_extended_codetext())
    qr_generator.save(f"qr_{text}.png")
```

Cet extrait illustre **comment nettoyer le builder** et **comment générer QR à partir de texte** de façon répétée.

## Cas limites et pièges courants

| Situation | À surveiller | Comment gérer |
|-----------|--------------|---------------|
| **Valeur ECI non prise en charge** | La bibliothèque lève `InvalidArgumentException`. | N’utiliser que les valeurs ECI listées dans la spécification (par ex., 26 pour UTF‑8, 20 pour Shift‑JIS). |
| **Texte combiné très long** | La version QR peut dépasser la capacité maximale. | Augmentez automatiquement la version QR (`qr_generator.set_qr_version(QRVersion.AUTO)`) ou divisez les données sur plusieurs QR codes. |
| **Erreurs de permission du système de fichiers** | `save` échoue avec `IOError`. | Assurez‑vous que le répertoire cible existe et que le processus a les droits d’écriture. |
| **Affichage incorrect du jeu de caractères** | Le scanner montre des caractères illisibles. | Vérifiez que la valeur ECI correcte correspond à l’encodage réel de la chaîne. |

## Exemple complet exécutable

Voici un script autonome que vous pouvez copier, coller et exécuter. Il inclut tous les imports, la gestion des erreurs et des commentaires pour plus de clarté.

```python
# qr_eci_example.py
# Demonstrates how to use ECI, generate QR from text, clear the builder,
# and save QR image using Aspose.BarCode for Python.

from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
import os

def generate_qr(plain_text: str, eci_value: int, unicode_text: str, out_file: str):
    """
    Creates a QR code that contains both plain and ECI‑encoded text.
    Parameters:
        plain_text – ASCII‑compatible string.
        eci_value  – Numeric ECI identifier (e.g., 26 for UTF‑8).
        unicode_text – Text that requires the specified ECI.
        out_file – Destination file path for the PNG image.
    """
    # Step 1: instantiate and clear the builder
    builder = ExtCodetextBuilder()
    builder.clear()                       # how to clear builder

    # Step 2: add segments
    builder.add_plain_codetext(plain_text)
    builder.add_eci_codetext(eci_value, unicode_text)

    # Step 3: retrieve combined text
    combined = builder.get_extended_codetext()
    print("Combined extended codetext:", combined)

    # Step 4: generate QR code
    generator = barcode.generation.BarcodeGenerator()
    generator.set_code_text(combined)
    generator.set_symbology(barcode.Symbology.QR)

    # Ensure output directory exists
    os.makedirs(os.path.dirname(out_file), exist_ok=True)

    # Step 5: save QR image – how to save QR image
    generator.save(out_file)
    print(f"QR code saved as {out_file}")

if __name__ == "__main__":
    # Example usage
    generate_qr(
        plain_text="HelloWorld",
        eci_value=26,               # UTF‑8
        unicode_text="Привет",      # Russian "Hello"
        out_file="output/qr_extended.png"
    )
```

L’exécution de ce script produit `output/qr_extended.png`, un QR code qui encode correctement le texte anglais et russe.

## Conclusion

Vous savez maintenant **comment utiliser eci** lors de la construction de QR codes, comment **réinitialiser le builder QR** avant réutilisation, comment **générer QR à partir de texte**, et les étapes exactes pour **enregistrer l’image QR** avec Python. En suivant ce modèle, vous pouvez intégrer n’importe quelle chaîne Unicode dans un QR code tout en gardant l’état du builder prévisible.

### Et après ?

- Explorez d’autres valeurs ECI pour des langues comme le chinois (ECI 20) ou ISO‑8859‑5.
- Ajustez les niveaux de correction d’erreur (`qr_generator.set_error_correction_level`) pour améliorer la fiabilité du scan.
- Combinez plusieurs segments ECI dans un même QR pour des messages multilingues.

Bon codage, et amusez‑vous à créer des QR codes multilingues !


## Que devez‑vous apprendre ensuite ?


Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to generate barcode with ECI using Aspose.Barcode Python](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [How to generate barcode in Python – complete step‑by‑step guide](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}