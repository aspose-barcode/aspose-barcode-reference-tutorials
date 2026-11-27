---
category: general
date: 2026-11-27
description: Crie códigos de barras postais rapidamente com Python. Aprenda a gerar
  uma imagem de código de barras a partir de uma string usando a simbologia RM4SCC.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode
- create barcode from string
- how to generate barcode image
language: pt
lastmod: 2026-11-27
og_description: Crie código de barras postal em Python. Siga este guia para aprender
  como gerar uma imagem de código de barras a partir de uma string com a simbologia
  RM4SCC.
og_image_alt: Screenshot showing a created postal barcode saved as a PNG file
og_title: Crie código de barras postal em Python – tutorial completo de codificação
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Create postal barcode quickly with Python. Learn how to generate a
    barcode image from a string using the RM4SCC symbology.
  headline: Create postal barcode in Python – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- Python
- RM4SCC
title: Criar código de barras postal em Python – guia passo a passo
url: /pt/python-java/general/create-postal-barcode-in-python-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar código de barras postal em Python – guia passo a passo

Se você precisa **criar código de barras postal** para aplicações de envio, este guia mostra exatamente como fazer isso com Python. Você verá um exemplo conciso e executável que transforma uma string simples em uma imagem PNG de alta qualidade usando a simbologia RM4SCC.  

Gerar um fluxo de **criar código de barras a partir de string** é útil para verificação de endereços, impressão em massa de etiquetas e integração com serviços postais. As etapas abaixo cobrem tudo, desde a instalação da biblioteca até o ajuste da largura das barras para desempenho ideal do scanner.

## O que este tutorial cobre

* Instalar o pacote `barcode` necessário (ou o SDK oficial que fornece `BarcodeGenerator`).
* Inicializar um gerador para o formato RM4SCC com uma string de dados.
* Ajustar a X‑dimension (largura do módulo) para controlar a espessura das barras.
* Salvar o resultado como uma imagem PNG – o formato mais comum quando você se pergunta **como gerar imagem de código de barras** para web ou impressão.
* Dicas para lidar com diretórios ausentes, formatos de imagem alternativos e armadilhas comuns.

Ao final do artigo, você terá um arquivo PNG pronto para uso chamado `PostalRM4SCCFilledBars.png` que pode ser incorporado em faturas, manifestos de envio ou qualquer fluxo de trabalho postal.

## Pré-requisitos

* Python 3.8+ instalado na sua máquina.  
* Acesso a um terminal ou prompt de comando.  
* Familiaridade básica com importações Python e caminhos de arquivos.  

Se você já tem um ambiente virtual, ative-o antes de instalar o pacote.

```bash
pip install python-barcode-sdk   # replace with the actual package name if different
```

> **Dica profissional:** Fixe a versão (`python-barcode-sdk==1.4.2`) para evitar alterações quebradas em lançamentos futuros.

## Etapa 1: Criar código de barras postal com a simbologia RM4SCC

O primeiro passo é instanciar um `BarcodeGenerator` para o formato RM4SCC e fornecer a ele os dados que você deseja codificar.

```python
from barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1 – initialise the generator with the RM4SCC symbology
# "123456" is the example postal code; replace it with any alphanumeric string.
gen = BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
```

**Por que isso importa:**  
`EncodeTypes.RM4SCC` indica ao SDK para usar o *Royal Mail 4‑State Code* (RM4SCC), que é o padrão para códigos de barras postais do Reino Unido. Fornecer os dados como uma string simples (`"123456"`) é a maneira mais simples de **criar código de barras a partir de string** sem lidar com tabelas de codificação de baixo nível.

## Etapa 2: Ajustar dimensões do código de barras para melhor legibilidade

Os scanners geralmente esperam uma largura mínima de barra. Definir a X‑dimension para 4 pixels fornece barras mais finas enquanto permanece dentro da faixa recomendada.

```python
# Step 2 – set the module (X) dimension to 4 pixels
gen.Parameters.Barcode.XDimension.Pixels = 4
```

**Por que você pode mudar isso:**  
Uma X‑dimension maior (por exemplo, 6 px) gera barras mais grossas, o que pode ser útil para impressoras de baixa resolução. Por outro lado, um valor menor torna o código de barras mais compacto — ideal para etiquetas com espaço limitado.

## Etapa 3: Salvar o código de barras como uma imagem PNG

Agora escreva o código de barras gerado no disco. PNG é sem perdas, garantindo que o código de barras permaneça nítido para leitores ópticos.

```python
# Step 3 – export the barcode to a PNG file
output_path = "YOUR_DIRECTORY/PostalRM4SCCFilledBars.png"
gen.Save(output_path, BarCodeImageFormat.Png)
print(f"Barcode saved to {output_path}")
```

**Por que PNG?**  
`BarCodeImageFormat.Png` preserva os dados de pixel exatos, o que é crítico quando você pergunta **como gerar imagem de código de barras** que devem ser lidas por scanners de alta velocidade. Se precisar de um formato diferente (JPEG, BMP, TIFF), substitua `Png` pelo valor enum apropriado.

### Resultado esperado

Depois de executar o script, você deverá ver um arquivo semelhante à imagem abaixo:

![Exemplo de um código de barras postal criado salvo como arquivo PNG](https://example.com/images/postal-rm4scc.png "Código de barras postal criado em formato PNG")

A imagem contém uma série de barras de quatro estados representando a string `123456`. Escaneando o PNG com um leitor de código de barras retorna os dados originais.

## Lidando com casos de borda comuns

| Situação | O que fazer |
|-----------|------------|
| **Directory does not exist** | Use `os.makedirs(os.path.dirname(output_path), exist_ok=True)` antes de chamar `gen.Save`. |
| **Invalid characters in data** | RM4SCC aceita apenas dígitos (0‑9). Valide a entrada com `str.isdigit()` e levante um erro claro se falhar. |
| **Different image format required** | Substitua `BarCodeImageFormat.Png` por `BarCodeImageFormat.Jpeg` (ou `Bmp`, `Tiff`) e ajuste a extensão do arquivo conforme necessário. |
| **Need higher resolution for print** | Aumente `gen.Parameters.Barcode.XDimension.Pixels` e, opcionalmente, defina `gen.Parameters.Image.Dpi = 300`. |

```python
import os

# Ensure output directory exists
os.makedirs(os.path.dirname(output_path), exist_ok=True)

# Optional: enforce numeric data for RM4SCC
data = "123456"
if not data.isdigit():
    raise ValueError("RM4SCC barcode data must contain only digits.")

# Continue with generator creation as shown earlier...
```

## Script completo para copiar‑colar rápido

Abaixo está o programa completo, pronto para executar, que incorpora todas as dicas de boas práticas discutidas.

```python
import os
from barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def create_postal_barcode(data: str, out_path: str, x_dim: int = 4):
    """
    Generates an RM4SCC postal barcode from a string and saves it as PNG.

    Args:
        data: Numeric string to encode (e.g., "123456").
        out_path: Full file path where the PNG will be written.
        x_dim: Desired X‑dimension in pixels (default 4).
    """
    # Validate input for RM4SCC
    if not data.isdigit():
        raise ValueError("RM4SCC barcode data must contain only digits.")
    
    # Ensure the output directory exists
    os.makedirs(os.path.dirname(out_path), exist_ok=True)

    # Initialise generator
    gen = BarcodeGenerator(EncodeTypes.RM4SCC, data)

    # Set module width
    gen.Parameters.Barcode.XDimension.Pixels = x_dim

    # Save as PNG
    gen.Save(out_path, BarCodeImageFormat.Png)
    print(f"Barcode saved to {out_path}")

if __name__ == "__main__":
    # Example usage
    create_postal_barcode(
        data="123456",
        out_path="output/PostalRM4SCCFilledBars.png",
        x_dim=4
    )
```

Executar este script produz o mesmo arquivo `PostalRM4SCCFilledBars.png` demonstrado anteriormente.

## Conclusão

Agora você sabe como **criar imagens de código de barras postal** em Python usando a simbologia RM4SCC. O tutorial cobriu todo o pipeline — desde **criar código de barras a partir de string** até ajustar dimensões e, finalmente, responder **como gerar imagem de código de barras** em formato PNG.  

Os próximos passos que você pode explorar incluem:

* Gerar códigos de barras para conjuntos de dados em massa (iterar sobre linhas de CSV).  
* Mudar para outras simbologias como `EncodeTypes.Code128` ou `EncodeTypes.QR`.  
* Incorporar o PNG diretamente em faturas PDF com `reportlab`.  

Experimente diferentes valores de X‑dimension e formatos de imagem para adequar às especificações da sua impressora ou scanner. Feliz codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá-lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como criar código de barras postal em Python com Aspose.BarCode](/barcode/english/python-java/general/how-to-create-postal-barcode-in-python-with-aspose-barcode/)
- [Como criar código de barras a partir de string em Python usando Aspose](/barcode/english/python-java/general/how-to-create-barcode-from-string-in-python-using-aspose/)
- [Como criar imagem de código de barras em Python com Aspose.BarCode](/barcode/english/python-java/general/how-to-create-barcode-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}