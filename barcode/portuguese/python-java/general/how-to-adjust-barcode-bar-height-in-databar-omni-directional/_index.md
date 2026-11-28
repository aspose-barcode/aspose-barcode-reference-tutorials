---
category: general
date: 2026-11-27
description: Aprenda como ajustar a altura das barras do código de barras em um gerador
  de código de barras DataBar Omni‑Directional. Código passo a passo mostra como definir
  alturas de 30 px e 60 px.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- adjust barcode bar height
- DataBar Omni‑Directional barcode
- set XDimension
- barcode image format
- BarCodeImageFormat
- barcode generator python
language: pt
lastmod: 2026-11-27
og_description: Ajuste a altura das barras do código de barras em um gerador de código
  de barras DataBar Omni‑Directional com Python. Siga o guia completo para definir
  alturas, dimensão X e salvar imagens PNG.
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode with adjusted bar height
og_title: Ajustar a altura da barra do código de barras no gerador DataBar Omni‑Directional
schemas:
- author: GroupDocs
  dateModified: '2026-11-27'
  description: Learn how to adjust barcode bar height in a DataBar Omni‑Directional
    barcode generator. Step‑by‑step code shows setting heights to 30 px and 60 px.
  headline: How to adjust barcode bar height in DataBar Omni‑Directional generator
  type: TechArticle
tags:
- barcode
- python
- DataBar
- imaging
title: Como ajustar a altura das barras do código de barras no gerador DataBar Omni‑Directional
url: /pt/python-java/general/how-to-adjust-barcode-bar-height-in-databar-omni-directional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como ajustar a altura das barras do código de barras no gerador DataBar Omni‑Directional

Se você precisar **ajustar a altura das barras do código de barras** para um código de barras DataBar Omni‑Directional, este guia mostra exatamente como fazer. Você verá um exemplo completo e executável em Python que altera a altura das barras de 30 px para 60 px mantendo a X‑dimension e o formato da imagem consistentes.

Alterar as dimensões visuais de um código de barras é uma necessidade comum quando o código precisa se ajustar a um tamanho específico de etiqueta ou diretriz de design. Além da altura das barras, você também pode querer ajustar a **X‑dimension** (tamanho do módulo) ou escolher um **formato de imagem do código de barras** diferente, como PNG ou JPEG.

Neste tutorial você irá:

* Instalar a biblioteca necessária (GroupDocs.Barcode for Python)
* Criar um gerador de código de barras DataBar Omni‑Directional
* Definir o tamanho do módulo com `XDimension`
* Ajustar a propriedade de altura da barra duas vezes
* Salvar as imagens resultantes no **BarCodeImageFormat** desejado

Nenhuma experiência prévia com a API do GroupDocs é necessária — apenas conhecimentos básicos de Python.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem:

* Python 3.8 ou mais recente instalado
* `groupdocs.barcode` package (`pip install groupdocs-barcode`)  
* Permissão de escrita em uma pasta onde os arquivos PNG serão salvos

Se você não está familiarizado com o **código de barras DataBar Omni‑Directional**, ele codifica um GTIN de 14 dígitos e é amplamente usado no varejo para leitura em qualquer orientação.

## Etapa 1: Configurar o gerador de código de barras DataBar Omni‑Directional

Primeiro, importe as classes necessárias e instancie o gerador com os dados GTIN que você deseja codificar.

```python
from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a DataBar Omni‑Directional barcode
# The string "(01)12345678901231" follows the GS1 Application Identifier syntax
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")
```

*Por que isso importa:* A constante `EncodeTypes.DatabarOmniDirectional` indica à biblioteca que deve produzir a simbologia Omni‑Directional. A string de dados inclui o AI `(01)` que marca um valor GTIN‑14.

## Etapa 2: Definir a X‑dimension (tamanho do módulo)

A X‑dimension controla a largura da barra mais estreita. Um valor comum para renderização na tela é **2 px por módulo**.

```python
# Set the module (X‑dimension) size – 2 px per module
gen.parameters.barcode.x_dimension.pixels = 2
```

Usar um **set XDimension** consistente garante que o código de barras escale corretamente em diferentes impressoras e scanners.

## Etapa 3: Ajustar a altura da barra para 30 px e salvar a imagem

Agora alteramos a propriedade de altura da barra. A primeira altura que usaremos é **30 px**, que é adequada para etiquetas pequenas.

```python
# Define the first bar height (30 px)
gen.parameters.barcode.bar_height.pixels = 30

# Save the barcode as a PNG image
gen.save("output/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png)
```

A constante `BarCodeImageFormat.Png` seleciona o **formato de imagem do código de barras** PNG, que preserva qualidade sem perdas.

### Resultado esperado

O arquivo `DatabarBarHeight30Pixels.png` contém um código de barras DataBar Omni‑Directional cujas barras têm 30 px de altura. Abaixo está uma pré‑visualização de placeholder:

![Código de barras DataBar com altura de barra de 30 px](images/databar_30px.png "Código de barras DataBar com altura de barra de 30 px")

> **Dica:** Se você abrir o PNG em um editor de imagens, verá a altura exata da barra. As barras estreitas têm 2 px de largura, conforme definido anteriormente.

## Etapa 4: Alterar a altura da barra para 60 px para um código de barras mais alto

Para aplicações que exigem uma pegada visual maior — como uma etiqueta de frete — você pode aumentar a altura da barra para **60 px**.

```python
# Change the bar height to 60 px for a taller barcode
gen.parameters.barcode.bar_height.pixels = 60
```

Apenas a propriedade `BarHeight` é alterada; a X‑dimension e a codificação permanecem as mesmas, portanto o código de barras continua legível.

## Etapa 5: Salvar a imagem do código de barras atualizado

Finalmente, grave o código de barras mais alto em um segundo arquivo PNG.

```python
# Save the updated barcode image
gen.save("output/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png)
```

### Resultado esperado

O arquivo `DatabarBarHeight60Pixels.png` mostra os mesmos dados codificados, mas cada barra agora tem 60 px de altura. A diferença visual é ilustrada abaixo:

![Código de barras DataBar com altura de barra de 60 px](images/databar_60px.png "Código de barras DataBar com altura de barra de 60 px")

## Exemplo completo e executável

Juntando tudo, aqui está o script completo que você pode copiar‑colar em um arquivo chamado `adjust_barcode_height.py` e executar diretamente.

```python
# adjust_barcode_height.py
# Demonstrates how to adjust barcode bar height for a DataBar Omni‑Directional barcode

from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# 1️⃣ Create the generator with GTIN data
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")

# 2️⃣ Set module size (X‑dimension) to 2 px
gen.parameters.barcode.x_dimension.pixels = 2

# 3️⃣ First bar height: 30 px
gen.parameters.barcode.bar_height.pixels = 30
gen.save(os.path.join(output_dir, "DatabarBarHeight30Pixels.png"), BarCodeImageFormat.Png)

# 4️⃣ Second bar height: 60 px
gen.parameters.barcode.bar_height.pixels = 60
gen.save(os.path.join(output_dir, "DatabarBarHeight60Pixels.png"), BarCodeImageFormat.Png)

print(f"Barcodes saved to '{output_dir}'")
```

Execute o script:

```bash
python adjust_barcode_height.py
```

Você deverá ver dois arquivos PNG na pasta `output`, cada um refletindo a altura da barra que você definiu.

## Perguntas comuns e casos de borda

| Pergunta | Resposta |
|----------|----------|
| **Posso usar JPEG em vez de PNG?** | Sim. Substitua `BarCodeImageFormat.Png` por `BarCodeImageFormat.Jpeg`. JPEG é com perdas, portanto prefira PNG para leitura precisa. |
| **E se eu precisar de uma altura de barra que não seja múltiplo de 10?** | A propriedade `BarHeight.Pixels` aceita qualquer valor inteiro. Basta atribuir a contagem de pixels desejada (por exemplo, `45`). |
| **Alterar a altura da barra afeta os dados codificados?** | Não. Apenas a representação visual muda; a string de dados subjacente permanece idêntica. |
| **Como mudar a X‑dimension após salvar a primeira imagem?** | Você pode modificar `gen.parameters.barcode.x_dimension.pixels` a qualquer momento antes de chamar `save()`. A alteração será aplicada às imagens subsequentes. |
| **O gerador é thread‑safe?** | A instância `BarcodeGenerator` não tem garantia de ser thread‑safe. Crie uma instância separada por thread se você gerar códigos de barras simultaneamente. |

## Conclusão

Agora você sabe como **ajustar a altura das barras do código de barras** em um gerador de código de barras DataBar Omni‑Directional usando Python. O tutorial abordou a criação do gerador, a definição da **X‑dimension**, a modificação da propriedade **barcode bar height** e a gravação de imagens no **formato de imagem do código de barras** desejado.

A partir daqui, você pode experimentar outras alturas, diferentes tamanhos de módulo, ou mudar para formatos de imagem alternativos como JPEG ou BMP. Você também pode explorar recursos adicionais do **barcode generator python**, como adicionar texto legível por humanos ou alterar esquemas de cores.

Feliz codificação, e mantenha seus códigos de barras nítidos e perfeitamente dimensionados!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como definir largura e ajustar altura para um código de barras GS1 DataBar Omni‑Directional](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [Criar databar omni‑directional e imagem de código de barras em Python](/barcode/english/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/)
- [.net barcode generator – alterar altura do código de barras](/barcode/english/python-java/general/net-barcode-generator-change-barcode-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}