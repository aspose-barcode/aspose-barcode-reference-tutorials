---
category: general
date: 2026-09-29
description: Exibir o nome do produto em Python ao imprimir a data de lançamento e
  recuperar os detalhes da versão da biblioteca de código de barras.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- display product name
- print release date
- how to get version
- how to print product
- show minor version
language: pt
lastmod: 2026-09-29
og_description: Exiba o nome do produto em Python e aprenda como imprimir a data de
  lançamento, obter a versão e mostrar a versão menor com algumas linhas de código.
og_image_alt: Screenshot of terminal output showing product name, version, and release
  date
og_title: Exibir nome do produto e informações da versão no Python
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Display product name in Python while printing release date and retrieving
    version details from the barcode library.
  headline: Display product name and version info in Python
  type: TechArticle
tags:
- Python
- barcode library
- version information
title: Exibir nome do produto e informações de versão em Python
url: /pt/python/general/display-product-name-and-version-info-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exibir nome do produto e informações de versão em Python

Se você precisa **exibir o nome do produto** de uma biblioteca, este guia mostra exatamente como fazer. Você também aprenderá a **imprimir a data de lançamento**, **como obter a versão** e **exibir a versão menor** usando código Python conciso.

Muitos desenvolvedores integram recursos de leitura ou geração de códigos de barras e precisam expor os metadados da biblioteca para usuários ou logs. Este tutorial cobre tudo o que é necessário para recuperar e apresentar essas informações de forma confiável.

## O que você aprenderá

* Recuperar informações de versão da biblioteca `barcode`.  
* **Exibir nome do produto** juntamente com os números de versão principal e menor.  
* **Imprimir a data de lançamento** em um formato legível por humanos.  
* Lidar com atributos ausentes de forma elegante.  

**Pré‑requisitos**  
* Python 3.8 ou superior.  
* Acesso ao pacote `barcode` (instale com `pip install python-barcode` ou a biblioteca que fornece `BuildVersionInfo`).  

---

## Como exibir nome do produto e informações de versão em Python

O primeiro passo é importar a biblioteca e chamar o método que retorna um objeto de informações de versão. O objeto contém atributos como `PRODUCT`, `PRODUCT_MAJOR`, `PRODUCT_MINOR` e `RELEASE_DATE`.

```python
import barcode

def main():
    # Step 1: Retrieve version information from the barcode library
    info = barcode.BuildVersionInfo()

    # Step 2: Display product name
    print(f"Product: {info.PRODUCT}")

    # Step 3: Show major and minor version numbers
    print(f"Version: {info.PRODUCT_MAJOR}.{info.PRODUCT_MINOR}")

    # Step 4: Print release date
    print(f"Release date: {info.RELEASE_DATE}")

if __name__ == "__main__":
    main()
```

**Por que isso funciona**  
`BuildVersionInfo()` retorna um objeto leve cujos atributos são preenchidos no momento da importação. Acessar os atributos diretamente evita I/O extra e garante que os dados exibidos correspondam à versão da biblioteca que seu código está realmente usando.

### Saída esperada

```
Product: BarcodeLib
Version: 2.5
Release date: 2024-03-15
```

Os valores exatos dependem da versão instalada da biblioteca de código de barras.

---

## Como obter a versão da biblioteca barcode

Se você precisa apenas dos números de versão, pode pular a impressão do nome do produto e focar nos campos numéricos.

```python
import barcode

info = barcode.BuildVersionInfo()
major = info.PRODUCT_MAJOR
minor = info.PRODUCT_MINOR

print(f"Current version: {major}.{minor}")
```

*Os atributos `PRODUCT_MAJOR` e `PRODUCT_MINOR` seguem o versionamento semântico, permitindo comparar versões programaticamente.*

---

## Como imprimir a data de lançamento

A data de lançamento é armazenada como uma string no formato `YYYY‑MM‑DD`. Para apresentá‑la em um locale diferente, converta‑a primeiro para um objeto `datetime`.

```python
import barcode
from datetime import datetime

info = barcode.BuildVersionInfo()
raw_date = info.RELEASE_DATE          # e.g., "2024-03-15"
date_obj = datetime.strptime(raw_date, "%Y-%m-%d")
formatted = date_obj.strftime("%B %d, %Y")  # "March 15, 2024"

print(f"Release date: {formatted}")
```

**Dica:** Sempre valide a string de data antes de analisá‑la para evitar `ValueError` quando a biblioteca mudar seu formato.

---

## Exibir versão menor ao lado da versão principal

Às vezes é necessário exibir a versão menor separadamente, por exemplo ao registrar avisos de compatibilidade.

```python
import barcode

info = barcode.BuildVersionInfo()
print(f"Major version: {info.PRODUCT_MAJOR}")
print(f"Minor version: {info.PRODUCT_MINOR}")
```

**Pro dica:** Use a versão menor para acionar flags de recursos:

```python
if info.PRODUCT_MINOR >= 5:
    enable_new_feature()
```

---

## Tratamento de atributos ausentes (casos de borda)

Versões mais antigas da biblioteca barcode podem não expor todos os atributos. Envolva o acesso aos atributos em `getattr` com valores padrão sensatos.

```python
import barcode

info = barcode.BuildVersionInfo()

product = getattr(info, "PRODUCT", "Unknown Product")
major = getattr(info, "PRODUCT_MAJOR", 0)
minor = getattr(info, "PRODUCT_MINOR", 0)
release = getattr(info, "RELEASE_DATE", "N/A")

print(f"Product: {product}")
print(f"Version: {major}.{minor}")
print(f"Release date: {release}")
```

Esse padrão garante que seu script nunca falhe por causa de um campo ausente, tornando‑o robusto para pipelines de CI que podem ser executados contra múltiplas versões da biblioteca.

---

## Exemplo completo e executável

Abaixo está o script completo que combina todas as boas práticas: validação de atributos, formatação de data e saída clara.

```python
import barcode
from datetime import datetime

def fetch_info():
    """Retrieve version info safely, providing defaults for missing attributes."""
    raw = barcode.BuildVersionInfo()
    return {
        "product": getattr(raw, "PRODUCT", "Unknown Product"),
        "major": getattr(raw, "PRODUCT_MAJOR", 0),
        "minor": getattr(raw, "PRODUCT_MINOR", 0),
        "release_raw": getattr(raw, "RELEASE_DATE", "N/A")
    }

def format_release(date_str):
    """Convert YYYY‑MM‑DD to a friendly format; fall back to the original string."""
    try:
        dt = datetime.strptime(date_str, "%Y-%m-%d")
        return dt.strftime("%B %d, %Y")
    except (ValueError, TypeError):
        return date_str

def main():
    info = fetch_info()

    # Display product name
    print(f"Product: {info['product']}")

    # Show major and minor version numbers
    print(f"Version: {info['major']}.{info['minor']}")

    # Print release date in a readable form
    print(f"Release date: {format_release(info['release_raw'])}")

if __name__ == "__main__":
    main()
```

Executar este script em um sistema com a biblioteca barcode instalada gera uma saída semelhante ao exemplo anterior, mas agora protege contra campos ausentes e formata a data de maneira agradável.

---

## Conclusão

Agora você sabe como **exibir nome do produto**, **imprimir a data de lançamento**, **obter a versão**, **imprimir o produto** e **exibir a versão menor** usando um fluxo de trabalho Python simples. O exemplo completo demonstra acesso confiável a atributos, manipulação de datas e comparação de versões — habilidades que você pode reutilizar para qualquer biblioteca de terceiros que exponha objetos de metadados.

**Próximos passos**

* Explore outros métodos de metadados da biblioteca barcode, como `BuildCommitInfo()`.  
* Integre a saída a um framework de logging (ex.: `logging.info`).  
* Compare versões programaticamente para impor versões mínimas necessárias em sua aplicação.

Sinta‑se à vontade para experimentar diferentes formatos de saída ou estender o script para gravar as informações em um arquivo para fins de auditoria. Feliz codificação!  

![Saída do terminal mostrando nome do produto e detalhes da versão](image.png "Saída do terminal")

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [exibir nome do produto usando a biblioteca Python barcode – guia passo a passo](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)
- [Como imprimir a versão do Aspose.Barcode (Python)](/barcode/english/python/general/how-to-print-version-of-aspose-barcode-python/)
- [Como gerar código de barras com Aspose.BarCode em Python](/barcode/english/python-java/general/how-to-generate-barcode-with-aspose-barcode-in-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}