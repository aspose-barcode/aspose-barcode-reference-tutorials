---
category: general
date: 2026-10-28
description: Apprenez à créer du texte de code étendu en Python avec ExtCodetextBuilder.
  Comprend des données en clair et encodées en ECI, du code pas à pas et des conseils
  de bonnes pratiques.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create extended codetext
- ExtCodetextBuilder Python
- add plain codetext
- add eci codetext
- extended‑codetext example
language: fr
lastmod: 2026-10-28
og_description: Créez du texte de code étendu en Python avec ExtCodetextBuilder. Ce
  tutoriel montre la gestion des données en clair et encodées en ECI, le code complet
  exécutable et les pièges courants.
og_image_alt: Diagram showing how to create extended codetext using ExtCodetextBuilder
  in Python
og_title: Créer un texte de code étendu en Python – guide complet
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Learn how to create extended codetext in Python using ExtCodetextBuilder.
    Includes plain and ECI‑encoded data, step‑by‑step code and best‑practice tips.
  headline: How to create extended codetext in Python with ExtCodetextBuilder
  type: TechArticle
- description: Learn how to create extended codetext in Python using ExtCodetextBuilder.
    Includes plain and ECI‑encoded data, step‑by‑step code and best‑practice tips.
  name: How to create extended codetext in Python with ExtCodetextBuilder
  steps:
  - name: Prerequisites
    text: '* Python 3.8 or newer. * The `extcodetext` package (or a similar library
      that provides `ExtCodetextBuilder`). Install it with:'
  - name: Handling other encodings
    text: 'If you need ISO‑8859‑1 (Western European) you would use `add_eci_codetext(4,
      "¡Hola!")`. For Shift‑JIS (Japanese) the ECI value is 20:'
  - name: 'Edge case: Empty strings'
    text: Calling `add_plain_codetext("")` or `add_eci_codetext(3, "")` is harmless;
      the builder simply ignores the empty fragment. However, repeated empty calls
      can lead to unnecessary ECI markers. Guard against this by checking string length
      before adding.
  type: HowTo
tags:
- Python
- encoding
- data‑serialization
title: Comment créer du texte de code étendu en Python avec ExtCodetextBuilder
url: /fr/python/general/how-to-create-extended-codetext-in-python-with-extcodetextbu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer du codetext étendu en Python avec ExtCodetextBuilder

Si vous devez **créer du codetext étendu** pour des applications de code‑barres ou de data‑matrix, ce guide vous montre exactement comment le faire en Python. Vous verrez comment combiner du texte brut, ajouter des sections ECI (Extended Channel Interpretation) pour les caractères Unicode, et récupérer une chaîne unique correctement formatée prête pour l’encodage.

Le tutoriel couvre tout, de l’installation de la bibliothèque requise à la gestion des cas limites tels que les valeurs ECI non prises en charge. À la fin, vous disposerez d’un modèle réutilisable que vous pourrez intégrer à n’importe quel projet nécessitant de **créer du codetext étendu**.

## Ce que vous apprendrez

* Le rôle de `ExtCodetextBuilder` lors de la construction de chaînes à encodage mixte.  
* Comment **add plain codetext** et **add ECI codetext** dans une même instance du builder.  
* Comment vérifier la sortie finale et dépanner les problèmes courants.  
* Variantes pour d’autres jeux de caractères (par ex., ISO‑8859‑1, Shift‑JIS).  

### Prérequis

* Python 3.8 ou plus récent.  
* Le paquet `extcodetext` (ou une bibliothèque similaire qui fournit `ExtCodetextBuilder`). Installez‑le avec :

```bash
pip install extcodetext
```

* Familiarité de base avec Unicode et les valeurs ECI – ECI 3 correspond à UTF‑8, ECI 4 à ISO‑8859‑1, etc.

> **Astuce :** Gardez à portée de main un tableau de référence des numéros ECI. Cela évite les incompatibilités accidentelles entre l’encodage déclaré et la séquence d’octets réelle.

## Comprendre ExtCodetextBuilder

`ExtCodetextBuilder` est un petit utilitaire qui concatène plusieurs fragments de texte tout en insérant automatiquement les marqueurs ECI requis. Un marqueur ECI indique à l’encodeur de code‑barres en aval quel jeu de caractères utiliser pour les octets suivants. Sans ce marqueur, les caractères non‑ASCII seraient mal interprétés.

Le builder fonctionne en trois phases simples :

1. **Create** l’instance du builder.  
2. **Append** les fragments en texte brut ou encodés ECI.  
3. **Retrieve** la chaîne de codetext étendu combinée.

Ci‑dessous, nous parcourons chaque phase avec du code concret.

## Étape 1 : Créer une instance d’ExtCodetextBuilder

La première ligne construit l’objet qui contiendra tous les fragments. Aucune configuration n’est requise à ce stade.

```python
from extcodetext import ExtCodetextBuilder

# Step 1: Create an ExtCodetextBuilder instance
codetext_builder = ExtCodetextBuilder()
```

*Pourquoi c’est important* : Instancier le builder alloue un tampon interne. Tous les appels `add_*` suivants opèrent sur ce tampon, garantissant l’ordre que vous spécifiez.

## Étape 2 : Ajouter des données brutes (non‑encodées)

Les données brutes sont composées de caractères appartenant au jeu de caractères par défaut (généralement ASCII). Utilisez `add_plain_codetext` pour ces fragments.

```python
# Step 2: Append plain (un‑encoded) data to the builder
codetext_builder.add_plain_codetext("ABC123")
```

*Explication* : La chaîne `"ABC123"` ne contient que des caractères ASCII, donc aucun marqueur ECI n’est nécessaire. La méthode ajoute simplement les octets bruts au tampon interne.

## Étape 3 : Ajouter des données qui doivent être précédées d’un ECI

Lorsque vous devez intégrer des caractères Unicode – comme le cyrillique, le japonais ou des emoji – vous devez indiquer à l’encodeur quel jeu de caractères utiliser. Cela se fait avec `add_eci_codetext(eci, text)`. Le premier argument est la valeur numérique ECI ; le second est le texte réel.

```python
# Step 3: Append data that must be preceded by an ECI (e.g., 3 for UTF‑8)
# This ensures the text "Привет" is correctly interpreted as UTF‑8
codetext_builder.add_eci_codetext(3, "Привет")
```

*Pourquoi ECI 3* : Selon la spécification ISO/IEC 18004, ECI 3 correspond à UTF‑8. En insérant ce marqueur, le lecteur de code‑barres sait décoder les octets suivants en UTF‑8, préservant ainsi les caractères cyrilliques.

### Gestion d’autres encodages

Si vous avez besoin d’ISO‑8859‑1 (Europe de l’Ouest), vous utiliseriez `add_eci_codetext(4, "¡Hola!")`. Pour Shift‑JIS (japonais), la valeur ECI est 20 :

```python
codetext_builder.add_eci_codetext(20, "こんにちは")
```

Vérifiez toujours que la bibliothèque de code‑barres cible prend en charge la valeur ECI choisie ; les ECI non supportés entraîneront des échecs d’encodage.

## Étape 4 : Récupérer la chaîne de codetext étendu combinée

Après avoir ajouté tous les fragments, appelez `get_extended_codetext()` pour obtenir la chaîne finale. Cette chaîne inclut toutes les séquences d’échappement ECI nécessaires.

```python
# Step 4: Retrieve the combined extended‑codetext string
extended_codetext = codetext_builder.get_extended_codetext()

print("Extended codetext:", extended_codetext)
```

**Résultat attendu** (affiché sous forme de `repr` Python pour plus de clarté) :

```
Extended codetext: 'ABC123\x1B\x1D\x03Привет'
```

*Décomposition* :

* `ABC123` – segment ASCII brut.  
* `\x1B\x1D\x03` – séquence d’échappement ECI pour UTF‑8 (ESC GS 0x03).  
* `Привет` – le mot cyrillique encodé en UTF‑8.

Les octets d’échappement exacts peuvent varier selon l’implémentation de la bibliothèque, mais l’ordre logique sera toujours *brut → marqueur ECI → texte Unicode*.

## Exemple complet exécutable

En rassemblant le tout, voici un script autonome que vous pouvez copier‑coller dans un fichier nommé `create_extended_codetext.py` et exécuter immédiatement.

```python
#!/usr/bin/env python3
"""
Create extended codetext in Python using ExtCodetextBuilder.
Demonstrates plain text, UTF‑8 ECI, and how to retrieve the final string.
"""

from extcodetext import ExtCodetextBuilder

def main() -> None:
    # 1️⃣ Create the builder
    builder = ExtCodetextBuilder()

    # 2️⃣ Add a plain ASCII segment
    builder.add_plain_codetext("ABC123")

    # 3️⃣ Add a UTF‑8 segment (ECI 3) containing Cyrillic characters
    builder.add_eci_codetext(3, "Привет")

    # 4️⃣ Retrieve and display the extended codetext
    result = builder.get_extended_codetext()
    print("Extended codetext:", result)

if __name__ == "__main__":
    main()
```

L’exécution du script affiche la chaîne combinée, prête pour tout encodeur de code‑barres acceptant une entrée de codetext étendu.

## Pièges courants et comment les éviter

| Symptôme | Cause probable | Solution |
|---|---|---|
| `UnicodeEncodeError` lors de l’appel à `add_eci_codetext` | Fournir une chaîne contenant des caractères non représentables dans l’ECI choisi | Vérifier que l’ECI correspond à l’encodage réel de la chaîne (par ex., utiliser ECI 3 pour tout texte UTF‑8). |
| Marqueur ECI manquant dans la sortie finale | Utilisation accidentelle de `add_plain_codetext` pour des données non‑ASCII | Passer à `add_eci_codetext` pour tout caractère hors du domaine ASCII. |
| Le lecteur de code‑barres affiche des caractères illisibles | Le lecteur ne prend pas en charge la valeur ECI sélectionnée | Choisir un ECI universellement supporté (UTF‑8 est largement supporté) ou revenir à ISO‑8859‑1 si la langue cible le permet. |
| `get_extended_codetext` renvoie une chaîne vide | Aucun fragment n’a été ajouté avant l’appel de la méthode | S’assurer qu’au moins un appel `add_*` est exécuté. |

### Cas particulier : Chaînes vides

Appeler `add_plain_codetext("")` ou `add_eci_codetext(3, "")` est sans danger ; le builder ignore simplement le fragment vide. Cependant, des appels vides répétés peuvent entraîner des marqueurs ECI inutiles. Évitez cela en vérifiant la longueur de la chaîne avant d’ajouter.

```python
text = "data"
if text:
    builder.add_plain_codetext(text)
```

## Étendre le modèle pour des données dynamiques

Dans les applications réelles, vous construisez souvent le codetext étendu à partir d’entrées utilisateur ou d’un enregistrement de base de données. Le fragment suivant montre une boucle qui traite une liste de tuples `(type, value)`, où `type` vaut soit `"plain"` soit `"eci"`.

```python
fragments = [
    ("plain", "Order#"),
    ("plain", "98765"),
    ("eci", (3, "商品")),   # Japanese word "商品" (product) encoded as UTF‑8
]

for kind, payload in fragments:
    if kind == "plain":
        builder.add_plain_codetext(payload)
    elif kind == "eci":
        eci_val, text = payload
        builder.add_eci_codetext(eci_val, text)
    else:
        raise ValueError(f"Unsupported fragment type: {kind}")

print(builder.get_extended_codetext())
```

Cette approche se met à l’échelle facilement : vous pouvez lire les définitions de fragments depuis JSON, CSV ou une API sans modifier la logique de construction principale.

## Tester la sortie

Un test unitaire rapide garantit que le builder se comporte comme attendu. En utilisant `pytest` :

```python
def test_extended_codetext():
    b = ExtCodetextBuilder()
    b.add_plain_codetext("X")
    b.add_eci_codetext(3, "✓")   # Check mark in UTF‑8
    result = b.get_extended_codetext()
    assert result.startswith("X")
    assert "\x1B\x1D\x03".encode() in result.encode()
```

L’exécution de `pytest` doit réussir, confirmant que le marqueur ECI apparaît exactement où il doit être.

## Concepts associés que vous pourriez explorer ensuite

* **Bibliothèques d’encodage de code‑barres** – par ex., `python-barcode`, liaisons `zxing`, qui acceptent directement la chaîne de codetext étendu.  
* **Référence du tableau ECI** – une liste complète des valeurs numériques ECI est publiée par ISO/IEC 18004 et peut être stockée sous forme de dictionnaire Python pour la recherche.  
* **Niveaux de correction d’erreur** – lors de la génération de QR codes, combinez le codetext étendu avec le niveau de correction d’erreur approprié (L, M, Q, H) pour un scan robuste.

## Conclusion

Vous savez maintenant comment **créer du codetext étendu** en Python avec `ExtCodetextBuilder`. Le processus est simple :

1. Instancier le builder.  
2. Ajouter les fragments en texte brut et encodés ECI selon les besoins.  
3. Récupérer la chaîne finale et la fournir à votre générateur de code‑barres.

En suivant le modèle ci‑dessus, vous pouvez gérer n’importe quel mélange d’ASCII et d’Unicode, éviter les erreurs d’encodage courantes et produire des chaînes prêtes pour les scanners de code‑barres, compatibles avec une large gamme de lecteurs. Expérimentez avec différents ECI, intégrez le builder dans votre pipeline de données, et vous disposerez d’une base solide pour tous vos besoins en codetext étendu.

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}