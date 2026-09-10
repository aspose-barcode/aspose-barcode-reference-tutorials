---
category: general
date: 2026-09-10
description: Codifique caracteres não ASCII em um QR code e salve a imagem do QR code
  com um construtor Python simples. Siga um guia passo a passo usando ExtCodetextBuilder
  e BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- encode non ascii characters
- save qr code image
- extended codetext builder
- eci encoding python
- barcode generation python
language: pt
lastmod: 2026-09-10
og_description: Codifique caracteres não ASCII em um QR code e salve a imagem do QR
  code usando Python. Este tutorial mostra como criar um texto de código estendido,
  gerar um QR code e armazenar a imagem.
og_image_alt: Diagram showing encode non ASCII characters in QR code and save QR code
  image workflow
og_title: Codifique caracteres não ASCII em QR code e salve a imagem do QR code –
  guia passo a passo em Python
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
title: Codificar caracteres não ASCII em código QR e salvar a imagem do código QR
url: /pt/python/general/encode-non-ascii-characters-in-qr-code-and-save-qr-code-imag/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Codificar caracteres não ASCII em QR code e salvar a imagem do QR code

Se você precisa **codificar caracteres não ASCII** em um QR code, este guia mostra exatamente como fazer isso e, em seguida, **salvar a imagem do QR code** no disco. Seja manipulando dados em russo, chinês ou emojis, o `ExtCodetextBuilder` permite misturar texto simples e segmentos codificados em ECI sem precisar lidar manualmente com bytes.

Você aprenderá como criar uma string de codetexto estendida, gerar um QR code que entende essa string e, finalmente, gravar a imagem do código de barras em um arquivo. O tutorial assume conhecimento básico de Python e que você tem o SDK `barcode` instalado.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem:

* Python 3.8+ instalado.
* O pacote Python `barcode` (ou o SDK apropriado) que fornece `ExtCodetextBuilder`, `CodetextEncodingType` e `BarcodeGenerator`.
* Permissão de escrita no diretório onde você deseja **salvar a imagem do QR code**.

Você pode instalar o SDK com pip (substitua `barcode-sdk` pelo nome real do pacote):

```bash
pip install barcode-sdk
```

## Etapa 1: Criar um construtor de codetexto estendido

O primeiro passo é instanciar `ExtCodetextBuilder`. Este objeto coleta vários segmentos de texto e produz uma única string que a simbologia QR pode interpretar.

```python
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Initialize the builder that will hold all text parts
ext_builder = ExtCodetextBuilder()
```

*Por que isso importa*: QR codes suportam **codetexto estendido**, o que significa que você pode incorporar vários modos de codificação (plain, ECI, etc.) em um único código de barras. O construtor abstrai a formatação de baixo nível exigida pela especificação QR.

## Etapa 2: Adicionar um segmento de texto simples

Texto simples é o modo padrão e funciona para caracteres ASCII. Adicioná‑lo primeiro fornece um fallback legível para leitores que ignoram ECI.

```python
# Add simple ASCII text
ext_builder.add_plain_codetext("HelloWorld")
```

Se você omitir esta etapa, o QR code conterá apenas o segmento ECI, o que alguns leitores mais antigos podem não decodificar corretamente.

## Etapa 3: Adicionar um segmento codificado em ECI para caracteres não‑ASCII

Para incluir caracteres fora do intervalo ASCII — como cirílico, chinês ou emojis — você deve especificar uma codificação ECI (Extended Channel Interpretation). Aqui usamos UTF‑8 para a palavra russa “Привет”.

```python
# Add a UTF‑8 encoded segment containing non‑ASCII characters
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")  # Russian “Hi”
```

*Por que isso funciona*: A especificação QR define valores ECI que informam ao scanner qual conjunto de caracteres aplicar. Sem o marcador ECI, os bytes brutos seriam interpretados como ISO‑8859‑1, resultando em saída corrompida.

## Etapa 4: Recuperar a string combinada de codetexto estendido

Depois de adicionar todos os segmentos desejados, chame `get_extended_codetext()` para obter a string final que o gerador de códigos de barras espera.

```python
# Combine all parts into one extended codetext string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

O valor impresso parece uma série de caracteres de controle seguidos pelo texto real, mas você nunca precisará analisá‑lo manualmente.

## Etapa 5: Gerar um QR code usando o codetexto estendido

Agora crie um `BarcodeGenerator`, defina a simbologia para QR (a única simbologia 2‑D comum que suporta codetexto estendido) e forneça a string combinada.

```python
# Initialize the QR generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)          # QR supports extended codetext
qr_generator.set_code_text(extended_codetext)
```

*Dica*: Se você tentar o mesmo processo com Code‑128 ou DataMatrix, o SDK lançará uma exceção porque esses formatos não podem interpretar marcadores ECI.

## Etapa 6: Salvar a imagem do QR code

Finalmente, grave o código de barras em um arquivo PNG. É aqui que você **salva a imagem do QR code** para uso posterior.

```python
output_path = "output/qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

Certifique‑se de que a pasta `output` exista ou crie‑a com `os.makedirs('output', exist_ok=True)` antes de chamar `save`.

### Exemplo completo executável

Juntando todas as etapas, você obtém um script autocontido que pode ser executado imediatamente:

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

**Saída esperada** (console):

```
Extended codetext: <binary representation showing ECI markers>
QR code saved to output/qr_extended.png
```

Abrir `qr_extended.png` com qualquer scanner de QR exibirá `HelloWorldПривет`. Scanners que entendem ECI renderizarão os caracteres cirílicos corretamente; outros mostrarão apenas a parte ASCII.

## Perguntas frequentes & casos de borda

| Pergunta | Resposta |
|----------|----------|
| *Posso usar outras codificações como Shift‑JIS?* | Sim. Substitua `CodetextEncodingType.UTF_8` por `CodetextEncodingType.SHIFT_JIS` e forneça o texto apropriado. |
| *E se os dados combinados excederem a capacidade do QR?* | QR codes têm limites de versão (até 177 × 177 módulos). Se o construtor lançar uma exceção de tamanho, aumente o nível de correção de erro ou divida os dados em vários QR codes. |
| *Preciso definir uma versão específica de QR?* | O SDK seleciona automaticamente a menor versão que cabe nos dados. Você pode forçar uma versão com `qr_generator.set_qr_version(10)` se necessário. |
| *A imagem será transparente?* | Por padrão o SDK grava um PNG com fundo branco. Use `qr_generator.set_background_color(Color.Transparent)` antes de `save` se precisar de transparência. |

## Conclusão

Neste tutorial você aprendeu como **codificar caracteres não ASCII** em um QR code usando o `ExtCodetextBuilder` e, em seguida, **salvar a imagem do QR code** com o `BarcodeGenerator`. O processo envolve construir uma string de codetexto estendida, adicionar segmentos simples e codificados em ECI, gerar a simbologia QR e, finalmente, gravar o arquivo de imagem.

A partir daqui, você pode explorar:

* Adicionar mais segmentos ECI (diferentes idiomas ou emojis).
* Ajustar os níveis de correção de erro do QR para maior confiabilidade.
* Incorporar o PNG gerado em PDFs ou páginas web.

Feliz codificação e aproveite a criação de QR codes multilíngues!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Generate Code128 Barcode with Aspose.Barcode Python – Full Guide](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [display product name using Python barcode library – step‑by‑step guide](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}