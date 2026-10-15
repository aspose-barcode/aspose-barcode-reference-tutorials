---
category: general
date: 2026-10-15
description: Crie código de barras a partir de uma string com Aspose.Barcode para
  Python. Aprenda como gerar código de barras, definir dimensões e salvar como PNG
  em minutos.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from string
- how to generate barcode
- barcode generator example
- generate postal barcode
- aspose barcode python
language: pt
lastmod: 2026-10-15
og_description: Crie código de barras a partir de uma string com Aspose.Barcode para
  Python. Este tutorial mostra passo a passo como gerar um código de barras postal
  e salvá‑lo como PNG.
og_image_alt: Screenshot of a generated postal barcode saved as PNG
og_title: Criar código de barras a partir de string em Python – Guia Aspose
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode from string with Aspose.Barcode for Python. Learn how
    to generate barcode, set dimensions, and save as PNG in minutes.
  headline: How to create barcode from string in Python using Aspose
  type: TechArticle
tags:
- barcode
- python
- Aspose
title: Como criar código de barras a partir de uma string em Python usando Aspose
url: /pt/python-java/general/how-to-create-barcode-from-string-in-python-using-aspose/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar código de barras a partir de uma string em Python usando Aspose

Se você precisa **criar código de barras a partir de uma string** rapidamente, o Aspose.Barcode para Python torna isso simples. Neste guia você verá exatamente **como gerar imagens de código de barras**, ajustar a dimensão X e salvar o resultado como um arquivo PNG — tudo com apenas algumas linhas de código.

Você também receberá um **exemplo completo de gerador de código de barras** que pode copiar‑colar no seu próprio projeto. Nenhum script externo ou configuração complexa é necessário, e o tutorial funciona com a versão atual do Aspose.Barcode 23.10.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

- Python 3.8+ instalado na sua máquina  
- Uma licença ativa do Aspose.Barcode para Python (a avaliação gratuita funciona para testes)  
- `pip install aspose-barcode` executado no seu ambiente virtual  

Esses itens garantem que o código seja executado sem erros de importação.

## Criar código de barras a partir de string com Aspose.Barcode (Python)

O primeiro passo é instanciar o `BarcodeGenerator` com a simbologia desejada — neste caso o código postal **Planet** — e a string que você deseja codificar.

```python
# Step 1: Import the required classes
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 2: Create a barcode generator for the Planet symbology with data "123456"
# This is the core of the "create barcode from string" operation.
generator = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

**Por que isso importa:**  
`EncodeTypes.Planet` indica ao Aspose que deve usar a simbologia postal Planet, que foi projetada para triagem de correspondência em vários países. O segundo argumento (`"123456"`) é a string bruta que será codificada no código de barras. Alterar esse valor permite que você **crie código de barras a partir de uma string** para qualquer código postal ou número de rastreamento que precisar.

## Como gerar código de barras com dimensões personalizadas

A largura do módulo de um código postal (a dimensão X) costuma precisar corresponder às especificações de impressão. O Aspose permite definir a largura em pixels enquanto calcula automaticamente a altura.

```python
# Step 3: Set the X dimension (module width) in pixels; height is calculated automatically
generator.parameters.barcode.x_dimension.pixels = 4
```

**Por que você pode ajustar isso:**  
Uma dimensão X maior deixa as barras mais espessas, o que pode melhorar a confiabilidade da leitura em impressoras de baixa resolução. Por outro lado, um valor menor reduz o tamanho da imagem para uso na web. Esta linha demonstra **como gerar código de barras** que atendam a requisitos de tamanho exatos.

## Salvar a imagem do código de barras

Depois de configurar o gerador, basta chamar `save`. O método aceita o caminho de saída e o formato de imagem desejado.

```python
# Step 4: Save the generated barcode as a PNG image
output_path = "YOUR_DIRECTORY/PostalPlanetAuto.png"
generator.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_path}")
```

**O que você obtém:**  
Um arquivo PNG chamado `PostalPlanetAuto.png` contendo o código postal Planet que codifica `"123456"`. Você pode abrir o arquivo em qualquer visualizador de imagens para verificar o resultado.

![Screenshot of a generated postal barcode saved as PNG](barcode_example.png){.align-center alt="Screenshot of a generated postal barcode saved as PNG"}

## Exemplo completo de gerador de código de barras

Abaixo está o script completo, pronto para ser executado, que inclui todas as etapas acima. Copie‑o para um arquivo chamado `generate_postal_barcode.py` e execute `python generate_postal_barcode.py`.

```python
# generate_postal_barcode.py
# -------------------------------------------------
# Complete example that shows how to create barcode from string,
# set custom dimensions, and save the result as PNG using Aspose.Barcode for Python.
# -------------------------------------------------

from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def create_postal_barcode(data: str, output_file: str, x_dim_pixels: int = 4):
    """
    Generates a Planet postal barcode from the supplied string.

    Args:
        data: The raw string to encode (e.g., "123456").
        output_file: Full path where the PNG image will be saved.
        x_dim_pixels: Desired X dimension in pixels (default = 4).

    Returns:
        None. The PNG file is written to disk.
    """
    # Validate data length for Planet symbology (6‑digit numeric is standard)
    if not data.isdigit() or len(data) != 6:
        raise ValueError("Planet barcode requires a 6‑digit numeric string.")

    # Create the generator (this is the core of create barcode from string)
    generator = BarcodeGenerator(EncodeTypes.Planet, data)

    # Adjust module width; height is calculated automatically
    generator.parameters.barcode.x_dimension.pixels = x_dim_pixels

    # Save as PNG
    generator.save(output_file, BarCodeImageFormat.PNG)
    print(f"Barcode saved to {output_file}")

if __name__ == "__main__":
    # Example usage – you can change the values to test other strings
    try:
        create_postal_barcode(
            data="123456",
            output_file="PostalPlanetAuto.png",
            x_dim_pixels=4
        )
    except Exception as e:
        print(f"Error generating barcode: {e}")
```

### Saída esperada

A execução do script produz:

```
Barcode saved to PostalPlanetAuto.png
```

…e cria um arquivo `PostalPlanetAuto.png` que se parece com isto:

![Generated Planet barcode](barcode_example.png){.align-center alt="Generated Planet barcode saved as PNG"}

## Variações comuns e casos de borda

| Situação | O que mudar | Por quê |
|-----------|----------------|-----|
| **Simbologia diferente** (ex.: Code128) | Substitua `EncodeTypes.Planet` por `EncodeTypes.Code128` | Permite **gerar código de barras** para etiquetas de inventário, não apenas códigos postais. |
| **Strings de dados mais longas** | Garanta que a simbologia escolhida suporte o comprimento; para Planet você deve manter 6 dígitos. | Evita `ValueError` em tempo de execução. |
| **Resolução maior** | Aumente `x_dimension.pixels` para 6 ou 8. | Produz barras mais espessas para impressão em alta DPI. |
| **Outros formatos de imagem** | Use `BarCodeImageFormat.JPEG` ou `BarCodeImageFormat.GIF`. | Útil quando PNG não é adequado ao seu fluxo de trabalho. |
| **Execução em um serviço web** | Substitua a chamada `save` do sistema de arquivos por um fluxo `BytesIO` e retorne os bytes. | Habilita a geração de código de barras sob demanda em Flask ou Django. |

**Dica profissional:** Sempre valide a string de entrada antes de chamar `BarcodeGenerator`. Dados inválidos (comprimento errado, caracteres não numéricos para Planet) gerarão uma exceção e interromperão sua aplicação.

## Como gerar código de barras em um endpoint Flask (passo opcional)

Se você quiser expor o **exemplo de gerador de código de barras** como uma API REST, pode envolver a função `create_postal_barcode`:

```python
from flask import Flask, send_file, request, abort
import io

app = Flask(__name__)

@app.route("/barcode", methods=["GET"])
def barcode_endpoint():
    data = request.args.get("data", "123456")
    try:
        # Generate barcode into an in‑memory stream
        stream = io.BytesIO()
        generator = BarcodeGenerator(EncodeTypes.Planet, data)
        generator.parameters.barcode.x_dimension.pixels = 4
        generator.save(stream, BarCodeImageFormat.PNG)
        stream.seek(0)
        return send_file(stream, mimetype="image/png", as_attachment=False)
    except Exception as exc:
        abort(400, str(exc))

if __name__ == "__main__":
    app.run(debug=True)
```

Este trecho mostra como **gerar código de barras** sob demanda sem gravar em disco, o que é útil para microsserviços.

## Conclusão

Agora você sabe como **criar código de barras a partir de uma string** em Python usando Aspose.Barcode, como **gerar código de barras** com dimensões personalizadas e como **salvar** o resultado como um arquivo PNG. O **exemplo completo de gerador de código de barras** inclui validação de entrada, tratamento de erros e uma função reutilizável que pode ser integrada a aplicações maiores.

Em seguida, explore outras simbologias (`EncodeTypes.Code128`, `EncodeTypes.QR`) ou incorpore o gerador em um framework web como Flask ou Django. Ambas as etapas aprofundarão seu entendimento da biblioteca **aspose barcode python** e ampliarão as formas como você pode **gerar imagens de código de barras postal** para projetos do mundo real.

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to generate barcode in Python – complete step‑by‑step guide](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Create barcode png in Python – Full Aspose.Barcode Guide](/barcode/english/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/)
- [How to generate barcode with ECI using Aspose.Barcode Python](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}