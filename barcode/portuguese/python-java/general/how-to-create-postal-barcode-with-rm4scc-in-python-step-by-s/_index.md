---
category: general
date: 2026-11-27
description: Aprenda a criar código de barras postal em Python usando o formato RM4SCC.
  Este tutorial cobre a dimensão X, a altura da barra e a gravação da imagem como
  PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode
- RM4SCC barcode
- barcode X dimension
- barcode bar height
- save barcode as PNG
language: pt
lastmod: 2026-11-27
og_description: Crie código de barras postal em Python usando RM4SCC. Ajuste a dimensão
  X, a altura da barra e exporte para PNG com um script completo e executável.
og_image_alt: Screenshot of a generated RM4SCC postal barcode saved as a PNG file
og_title: Criar código de barras postal em Python – exemplo completo de RM4SCC
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Learn how to create postal barcode in Python using the RM4SCC format.
    This tutorial covers X dimension, bar height, and saving the image as PNG.
  headline: How to create postal barcode with RM4SCC in Python – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- Python
- Aspose
title: Como criar código de barras postal com RM4SCC em Python – guia passo a passo
url: /pt/python-java/general/how-to-create-postal-barcode-with-rm4scc-in-python-step-by-s/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar código de barras postal com RM4SCC em Python – guia passo a passo

Se você precisa **criar código de barras postal** para um sistema de correspondência, este guia mostra exatamente como gerar um código de barras RM4SCC em Python. Você verá como configurar a dimensão X, definir uma altura de barra personalizada e salvar o resultado como uma imagem PNG — tudo com um único script autônomo.

Gerar um **código de barras postal** é uma necessidade comum para logística, e‑commerce e soluções de envio em massa. O código abaixo usa a biblioteca Aspose.BarCode for Python, que implementa a simbologia RM4SCC exigida por muitos serviços postais. Ao final deste tutorial você terá um arquivo PNG pronto para uso que pode ser impresso em envelopes ou anexado a pacotes.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* Python 3.8 ou mais recente instalado.
* Uma licença ativa do Aspose.BarCode for Python (ou uma chave de avaliação gratuita).  
  Instale o pacote com `pip install aspose-barcode`.
* Permissão de gravação no diretório onde o PNG será salvo.

Nenhuma biblioteca de sistema adicional é necessária; a biblioteca lida com todo o processamento de imagem internamente.

## Etapa 1: Importar as classes do Aspose.BarCode e criar o gerador

A primeira tarefa é importar as classes necessárias e instanciar um `BarcodeGenerator` para o formato RM4SCC. O **código de barras RM4SCC** codifica uma string numérica de 6 dígitos que representa um código de roteamento postal.

```python
# Step 1: Import and create a barcode generator for RM4SCC
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# The data "123456" is a sample postal routing number.
barcode_generator = BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
```

**Por que isso importa:**  
`EncodeTypes.RM4SCC` informa à biblioteca para aplicar as regras exatas da simbologia definidas pelo Royal Mail 4‑State Customer Code. Usar o tipo correto garante que o código de barras seja legível pelos equipamentos postais.

## Etapa 2: Configurar a dimensão X (largura do módulo)

A **dimensão X do código de barras** controla a largura do menor elemento de barra. Definir 4 pixels produz um código de barras que equilibra legibilidade e compacidade para a maioria das impressoras de etiquetas.

```python
# Step 2: Set the X dimension (module width) to 4 pixels
barcode_generator.parameters.barcode.x_dimension.pixels = 4
```

**Por que isso importa:**  
Uma dimensão X menor reduz a largura total do código de barras, enquanto um valor maior melhora a tolerância a imperfeições de impressão. Ajuste esse valor com base no DPI da sua impressora e no espaço disponível na etiqueta.

## Etapa 3: Definir a altura da barra

A **altura da barra do código de barras** determina quão alta cada barra aparece. Uma altura de 100 pixels fornece contraste suficiente para scanners ópticos sem consumir espaço excessivo na etiqueta.

```python
# Step 3: Set the bar height to 100 pixels
barcode_generator.parameters.barcode.bar_height.pixels = 100
```

**Por que isso importa:**  
Scanners postais esperam uma altura mínima de barra para detectar de forma confiável os padrões de quatro estados. Se você reduzir demais a altura, o scanner pode não perceber as sutis diferenças entre barras e espaços.

## Etapa 4: Salvar o código de barras como imagem PNG

Por fim, **salve o código de barras como PNG** para obter uma imagem sem perdas adequada para impressão. PNG preserva as dimensões exatas dos pixels que você configurou, o que é crítico para a precisão do código de barras.

```python
# Step 4: Save the generated barcode as a PNG image
output_path = "YOUR_DIRECTORY/PostalRM4SCCBarHeight100Pixels.png"
barcode_generator.save(output_path, BarCodeImageFormat.Png)

print(f"Barcode saved to {output_path}")
```

**Por que isso importa:**  
PNG é amplamente suportado por softwares de design de etiquetas e impressoras. O arquivo pode ser incorporado diretamente em PDFs, documentos Word ou impresso usando ferramentas padrão de impressão de imagens.

### Saída esperada

Executar o script gera um arquivo chamado `PostalRM4SCCBarHeight100Pixels.png`. Ao abrir a imagem, você verá um código de barras RM4SCC limpo com módulos de 4 pixels e altura de barra de 100 pixels, pronto para inclusão em uma etiqueta de correspondência.

## Código‑fonte completo – pronto para copiar e executar

Abaixo está o exemplo completo e executável que combina todas as etapas. Substitua `YOUR_DIRECTORY` por um caminho absoluto ou relativo onde você deseja salvar o PNG.

```python
"""
Complete example: create postal barcode (RM4SCC) in Python,
configure X dimension and bar height, and save as PNG.
"""

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def generate_postal_barcode(data: str,
                            x_dim_pixels: int = 4,
                            bar_height_pixels: int = 100,
                            output_file: str = "PostalRM4SCC.png") -> None:
    """
    Generates an RM4SCC postal barcode with custom dimensions.

    Args:
        data: Six‑digit numeric string for the postal routing code.
        x_dim_pixels: Width of the smallest bar element (default 4).
        bar_height_pixels: Height of the bars in pixels (default 100).
        output_file: Path where the PNG image will be saved.
    """
    # Create generator for RM4SCC
    generator = BarcodeGenerator(EncodeTypes.RM4SCC, data)

    # Apply custom dimensions
    generator.parameters.barcode.x_dimension.pixels = x_dim_pixels
    generator.parameters.barcode.bar_height.pixels = bar_height_pixels

    # Save as PNG
    generator.save(output_file, BarCodeImageFormat.Png)

    print(f"Barcode saved to {output_file}")

if __name__ == "__main__":
    # Example usage
    generate_postal_barcode(
        data="123456",
        x_dim_pixels=4,
        bar_height_pixels=100,
        output_file="YOUR_DIRECTORY/PostalRM4SCCBarHeight100Pixels.png"
    )
```

**Explicação da função:**

* `generate_postal_barcode` isola a lógica de criação do código de barras, tornando‑a reutilizável em diferentes projetos.
* Os parâmetros padrão correspondem aos valores demonstrados na seção passo a passo, mas você pode passar números diferentes para adaptar a outros formatos de etiqueta.
* A função imprime uma mensagem de confirmação, útil para processamento em lote onde você gera muitos códigos de barras em um loop.

## Variações comuns e casos de borda

| Situação | Alteração recomendada |
|-----------|--------------------|
| **Comprimento diferente do número de roteamento** | RM4SCC espera exatamente 6 dígitos. Se você receber uma string mais curta, preencha com zeros à esquerda (`data.zfill(6)`). |
| **Impressora de alta resolução** | Aumente `x_dim_pixels` para 6 ou 8 para manter a largura da barra proporcional ao DPI da impressora. |
| **Necessidade de fundo transparente** | Substitua `BarCodeImageFormat.Png` por `BarCodeImageFormat.PngTransparent` (se suportado) ou defina `generator.parameters.image.transparent_background = True`. |
| **Geração em lote** | Percorra uma lista de números de roteamento e chame `generate_postal_barcode` para cada um, armazenando os resultados em uma pasta dedicada. |
| **Dados não numéricos** | RM4SCC não aceita caracteres alfabéticos. Valide a entrada antes de chamar o gerador para evitar erros em tempo de execução. |

## Dicas profissionais para impressão confiável de códigos de barras postais

* **Valide o comprimento dos dados** antes de criar o código de barras; uma exceção será lançada se a string não tiver seis dígitos.
* **Teste o código de barras impresso** com um scanner físico antes de colocar em produção. Pequenas variações na densidade da tinta da impressora podem afetar a legibilidade.
* **Mantenha o arquivo PNG sem compressão** (a compressão padrão do PNG é sem perdas). Re‑compactar para JPEG introduzirá artefatos que quebram o código de barras.
* **Use um diretório de saída consistente** para simplificar a integração com ferramentas de design de etiquetas que esperam uma estrutura de pastas específica.

## Conclusão

Agora você sabe como **criar código de barras postal** em Python usando a simbologia RM4SCC, ajustar a **dimensão X do código de barras**, definir a **altura da barra do código de barras** e **salvar o código de barras como PNG**. O script completo pode ser integrado a qualquer fluxo de trabalho de etiquetas de envio, e a função modular facilita a geração automática de centenas de códigos de barras.

Em seguida, explore tópicos relacionados como **gerar códigos QR para URLs de rastreamento**, **incorporar códigos de barras em faturas PDF** ou **usar outras simbologias postais como POSTNET**. Cada um desses se baseia nos mesmos princípios demonstrados aqui: escolher o tipo de codificação correto, configurar parâmetros visuais e exportar uma imagem de alta qualidade.

Sinta‑se à vontade para experimentar diferentes dimensões, cores ou formatos de arquivo para adequar ao seu ambiente de impressão específico. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Como criar código de barras postal em Python com Aspose.BarCode](/barcode/english/python-java/general/how-to-create-postal-barcode-in-python-with-aspose-barcode/)
- [Criar código de barras PNG em Python – Guia completo](/barcode/english/python-java/general/create-barcode-png-in-python-complete-guide/)
- [Como criar código de barras planetário PNG com Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}