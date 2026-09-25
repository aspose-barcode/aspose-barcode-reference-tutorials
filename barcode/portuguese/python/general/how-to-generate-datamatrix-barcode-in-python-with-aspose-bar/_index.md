---
category: general
date: 2026-08-22
description: Aprenda a gerar códigos de barras DataMatrix em Python e codificar texto
  em russo usando Aspose.BarCode – guia passo a passo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate DataMatrix barcode
- encode Russian text
language: pt
lastmod: 2026-08-22
og_description: Gere código de barras DataMatrix em Python e codifique texto em russo
  com Aspose.BarCode. Siga o exemplo completo e execute‑o instantaneamente.
og_image_alt: Python script that generate DataMatrix barcode with encoded Russian
  text
og_title: Gerar código de barras DataMatrix em Python – tutorial completo do Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  headline: How to generate DataMatrix barcode in Python with Aspose.BarCode
  type: TechArticle
- description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  name: How to generate DataMatrix barcode in Python with Aspose.BarCode
  steps:
  - name: '**ABC123** – the plain identifier.'
    text: '**ABC123** – the plain identifier.'
  - name: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
    text: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
  - name: Open the PNG file in an image viewer.
    text: Open the PNG file in an image viewer.
  - name: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
    text: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
  - name: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
    text: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
  type: HowTo
tags:
- Aspose.BarCode
- Python
- barcode generation
title: Como gerar código de barras DataMatrix em Python com Aspose.BarCode
url: /pt/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar código de barras DataMatrix em Python com Aspose.BarCode

Se você precisa **gerar código de barras DataMatrix** em Python enquanto **codifica texto em russo**, este guia mostra os passos exatos. Você verá um exemplo completo e executável que cria um codetext estendido, configura o código de barras e salva a imagem em um único script.

Criar códigos de barras que contêm caracteres não‑ASCII frequentemente levanta questões sobre conjuntos de caracteres e codificação de dados. Usando o `ExtCodetextBuilder` do Aspose.BarCode, você pode incorporar com segurança texto UTF‑8, como caracteres cirílicos, dentro de um símbolo DataMatrix. O resultado funciona com qualquer scanner que suporte o padrão DataMatrix.

Neste tutorial você irá:

* Instalar o pacote Aspose.BarCode necessário.
* Construir um codetext estendido que mistura dados simples e texto em russo.
* **Gerar código de barras DataMatrix** com a string estendida.
* Ajustar parâmetros do código de barras, como o tamanho do módulo.
* Salvar o código de barras como um arquivo PNG.

Nenhum serviço externo é necessário; tudo roda localmente na sua máquina.

## Pré-requisitos

Antes de começar, certifique-se de que você tem:

* Python 3.8 ou mais recente instalado.
* Uma licença ativa do Aspose.BarCode para Python (uma avaliação gratuita funciona para desenvolvimento).
* Familiaridade básica com scripts Python.

Você pode instalar a biblioteca Aspose.BarCode via pip:

```bash
pip install aspose-barcode
```

## Etapa 1: Construir uma string de codetext estendido

A primeira tarefa é criar uma única string que contenha tanto o identificador simples do produto quanto a frase em russo. `ExtCodetextBuilder` permite concatenar diferentes partes de codetext preservando suas informações de codificação.

```python
# Import required Aspose.BarCode classes
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

# Initialize the extended codetext builder
builder = ExtCodetextBuilder()

# Add a plain ASCII identifier – this could be a SKU, part number, etc.
builder.add_plain_codetext("ABC123")

# Add Russian text using ECI (Extended Channel Interpretation) encoding.
# The eci_encoding value 3 corresponds to UTF‑8.
builder.add_eci_codetext(eci_encoding=3, codetext="Привет")

# Retrieve the combined string that Aspose.BarCode will use.
extended_text = builder.get_extended_codetext()
print("Generated extended codetext:", extended_text)
```

**Por que esta etapa é importante** – Os símbolos DataMatrix armazenam bytes brutos. Quando você precisa misturar alfabetos, deve informar ao codificador qual conjunto de caracteres se aplica a cada segmento. O método `add_eci_codetext` insere um indicador ECI antes do texto em russo, garantindo que os scanners interpretem os bytes como UTF‑8. Sem o ECI, os caracteres cirílicos apareceriam como dados corrompidos.

## Etapa 2: Criar um gerador de código de barras DataMatrix

Com o codetext estendido pronto, instancie um `BarcodeGenerator` especificando o tipo `EncodeTypes.DATA_MATRIX`.

```python
# Create a DataMatrix barcode generator using the extended codetext
generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)
```

**Por que DataMatrix?** – DataMatrix é um código de barras bidimensional que pode armazenar até 2.335 caracteres alfanuméricos ou 1.556 bytes. É ideal para itens pequenos, peças industriais e situações onde você precisa incorporar texto multilíngue.

## Etapa 3: (Opcional) Configurar parâmetros do código de barras

Aspose.BarCode expõe muitos parâmetros. Para a maioria dos casos de uso, as configurações padrão produzem um símbolo legível. No entanto, você pode querer controlar o tamanho de cada módulo (o quadrado menor na matriz) para atender aos requisitos de impressão.

```python
# Set the module (pixel) size to 2.5 points – adjust as needed for your printer DPI
generator.parameters.barcode.x_dimension = 2.5
```

Outros parâmetros úteis incluem nível de correção de erro, margem e cor de fundo. Ajuste-os somente se o ambiente de escaneamento alvo exigir tolerâncias específicas.

## Etapa 4: Salvar a imagem do código de barras

Finalmente, grave o código de barras em um arquivo. O método `save` suporta PNG, JPEG, BMP e vários formatos vetoriais.

```python
# Save the barcode image to the desired folder
output_path = "YOUR_DIRECTORY/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

Ao abrir `extended_codetext.png`, você verá um símbolo DataMatrix nítido. Escaneá-lo com um leitor padrão de DataMatrix retorna as duas partes:

1. **ABC123** – o identificador simples.
2. **Привет** – a saudação em russo, decodificada corretamente como UTF‑8.

## Exemplo completo e executável

Abaixo está o script completo que você pode copiar‑colar em um arquivo chamado `generate_datamatrix.py`. Substitua `YOUR_DIRECTORY` por uma pasta existente no seu sistema.

```python
# generate_datamatrix.py
# -------------------------------------------------
# Complete example: generate DataMatrix barcode and encode Russian text
# -------------------------------------------------

import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

def main():
    # Step 1: Build extended codetext
    builder = ExtCodetextBuilder()
    builder.add_plain_codetext("ABC123")
    builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_text = builder.get_extended_codetext()
    print("Generated extended codetext:", extended_text)

    # Step 2: Create DataMatrix generator
    generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)

    # Step 3: Optional parameters (adjust module size if needed)
    generator.parameters.barcode.x_dimension = 2.5

    # Step 4: Save the image
    output_path = "YOUR_DIRECTORY/extended_codetext.png"
    generator.save(output_path)
    print(f"Barcode saved as {output_path}")

if __name__ == "__main__":
    main()
```

Execute o script a partir da linha de comando:

```bash
python generate_datamatrix.py
```

Você deverá ver uma saída no console semelhante a:

```
Generated extended codetext: (ECI:3)ПриветABC123
Barcode saved as YOUR_DIRECTORY/extended_codetext.png
```

## Verificando o resultado

Para confirmar que o código de barras codifica corretamente a frase em russo:

1. Abra o arquivo PNG em um visualizador de imagens.
2. Use qualquer aplicativo de escaneamento DataMatrix (muitos apps móveis suportam) ou um scanner de hardware.
3. A string decodificada deve exibir `ABC123Привет` (ou as duas partes separadas, dependendo da interface do scanner).

Se os caracteres russos aparecerem como lixo, verifique novamente se o scanner suporta ECI UTF‑8. A maioria dos leitores modernos suporta, mas dispositivos legados podem precisar de configuração explícita.

## Armadilhas comuns e como evitá‑las

| Problema | Causa | Solução |
|----------|-------|---------|
| Saída cirílica corrompida | Indicador ECI ausente | Use `add_eci_codetext` com `eci_encoding=3`. |
| Código de barras muito pequeno para a impressora | Tamanho de módulo padrão muito pequeno para baixa DPI | Aumente `x_dimension` (ex.: `3.0` ou `4.0`). |
| Arquivo não salvo | Caminho de diretório inválido | Certifique-se de que `YOUR_DIRECTORY` exista e seja gravável. |
| Scanner não consegue ler | Densidade de dados excessiva | Reduza a quantidade de dados codificados ou aumente o nível de correção de erro (`generator.parameters.barcode.error_correction_level`). |

## Estendendo o exemplo

Você pode adaptar este padrão para outros idiomas ou tipos de dados:

* **Codificar texto em japonês ou árabe** – altere `eci_encoding` para o valor apropriado (ex.: 5 para ISO‑8859‑5, 6 para ISO‑8859‑7).  
* **Adicionar múltiplos segmentos ECI** – chame `add_eci_codetext` várias vezes, cada um com sua própria codificação.  
* **Criar um código QR em vez disso** – substitua `EncodeTypes.DATA_MATRIX` por `EncodeTypes.QR`.  

Todas as demais etapas permanecem idênticas porque o `ExtCodetextBuilder` abstrai o manuseio de bytes de baixo nível.

## Conclusão

Agora você sabe como **gerar código de barras DataMatrix** em Python e **codificar texto em russo** usando o recurso de codetext estendido do Aspose.BarCode. O script completo lida com a negociação de conjunto de caracteres, criação do código de barras e geração da imagem com apenas algumas linhas de código.

Em seguida, explore outras simbologias de códigos de barras (PDF417, Aztec) ou integre o gerador a um serviço web que devolve imagens PNG sob demanda. Os mesmos princípios — construir um codetext estendido e selecionar o `EncodeTypes` apropriado — se aplicam a toda a suíte Aspose.BarCode.

Boa codificação e aproveite o poder da geração de códigos de barras multilíngues!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como gerar códigos de barras DataMatrix usando Aspose.BarCode para .NET – Guia passo a passo](/barcode/english/net/datamatrix-barcode-configuration/)
- [Gerar um código de barras DataMatrix em modo ASCII com Aspose.BarCode para .NET (C#)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Como gerar códigos de barras DataMatrix (ECC 200) com Aspose.BarCode para .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}