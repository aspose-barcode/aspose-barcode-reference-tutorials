---
category: general
date: 2026-08-09
description: Crie código de barras QR em Python usando Aspose.BarCode. Aprenda como
  construir texto de código estendido, ajustar a aparência e salvar a imagem — tudo
  em um único tutorial.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create QR barcode
- Aspose.BarCode Python
- extended codetext QR
- QR code generation Python
- barcode visual customization
language: pt
lastmod: 2026-08-09
og_description: Crie código de barras QR em Python com Aspose.BarCode. Este guia mostra
  como construir um codetexto estendido, definir parâmetros visuais e exportar a imagem.
og_image_alt: Screenshot of a generated QR barcode created with Aspose.BarCode in
  Python
og_title: Criar código de barras QR com Aspose.BarCode em Python – exemplo completo
  de código
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  headline: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  type: TechArticle
- description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  name: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  steps:
  - name: Common variations
    text: '- **Multiple ECI segments:** Call `add_eci_codetext` multiple times to
      mix several languages. - **Different ECI identifiers:** Use `27` for ISO‑8859‑1,
      `28` for ISO‑8859‑2, etc., depending on your target encoding.'
  - name: Edge case handling
    text: '- **High‑density data:** If the encoded data is large, you may need to
      increase `x_dimension` or choose a higher error‑correction level (via `qr_generator.parameters.qr.error_correction_level`).
      - **Transparent background:** Set `qr_generator.parameters.barcode.bg_color
      = Color.Transparent` for PNGs'
  - name: Verifying the result
    text: 'Open the saved file in any image viewer. You should see a QR code that,
      when scanned, returns the combined string:'
  type: HowTo
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: Criar código de barras QR com Aspose.BarCode em Python – guia passo a passo
url: /pt/python/general/create-qr-barcode-with-aspose-barcode-in-python-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crie código de barras QR com Aspose.BarCode em Python – guia passo a passo

Se você precisa **criar código de barras QR** em Python, este tutorial o conduz por todo o processo usando a biblioteca Aspose.BarCode. Seja codificando IDs de produtos, texto multilíngue ou dados personalizados, você verá como montar um codetext estendido, ajustar configurações visuais e salvar a imagem final em um único script executável.

O exemplo também demonstra como exibir a versão da biblioteca, o que ajuda a verificar se você está usando uma versão compatível. Ao final deste guia você terá uma imagem de código de barras QR pronta para uso e uma compreensão clara de cada opção de configuração.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

- Python 3.8+ instalado.
- O pacote `aspose-barcode` (instale via `pip install aspose-barcode`).
- Familiaridade básica com a sintaxe Python.
- Permissão de escrita no diretório de saída onde o arquivo PNG será salvo.

> **Dica profissional:** Use um ambiente virtual para evitar conflitos de versão com outros projetos.

## Etapa 1: Verificar a versão da biblioteca Aspose.BarCode

Exibir a versão da biblioteca garante que você está usando uma versão que suporta codetext estendido e codificação QR.

```python
from asposebarcode import BuildVersionInfo

# Show the current Aspose.BarCode version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)
```

**Por que isso importa:**  
Versões mais antigas podem não conter a classe `ExtCodetextBuilder` necessária para segmentos mistos de texto simples e ECI. Confirmar a versão evita erros em tempo de execução mais adiante no fluxo de trabalho.

## Etapa 2: Construir uma string de codetext estendido

Um codetext estendido permite combinar dados ASCII simples com segmentos Unicode (ECI), o que é essencial para códigos QR multilíngues.

```python
from asposebarcode import ExtCodetextBuilder

# Initialize the builder
ext_builder = ExtCodetextBuilder()

# Add a plain segment – typically a product ID or numeric code
ext_builder.add_plain_codetext("ABC12345")

# Add an ECI segment – here we embed Japanese greeting "こんにちは"
# 26 is the ECI identifier for UTF‑8 encoding
ext_builder.add_eci_codetext(26, "こんにちは")

# Retrieve the full extended codetext that the QR generator will use
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")
```

**Por que isso importa:**  
O método `add_plain_codetext` armazena os dados como ASCII padrão, enquanto `add_eci_codetext` prefixa um bloco Unicode com o designador ECI apropriado. Essa abordagem garante que os scanners QR interpretem o texto em japonês corretamente, evitando caracteres corrompidos.

### Variações comuns

- **Múltiplos segmentos ECI:** Chame `add_eci_codetext` várias vezes para misturar vários idiomas.
- **Identificadores ECI diferentes:** Use `27` para ISO‑8859‑1, `28` para ISO‑8859‑2, etc., dependendo da codificação alvo.

## Etapa 3: Gerar o código de barras QR usando o codetext estendido

Agora que temos uma string formatada corretamente, podemos criar o código QR.

```python
from asposebarcode import BarCodeGenerator, EncodeTypes, BarCodeImageFormat

# Create the QR generator with the extended codetext
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)
```

**Por que isso importa:**  
`EncodeTypes.QR` indica ao Aspose.BarCode que deve usar a simbologia QR. Passar o `extended_codetext` diretamente vincula os dados mistos à matriz QR, preservando tanto as partes simples quanto as Unicode.

## Etapa 4: Ajustar a aparência visual (opcional, mas recomendado)

Ajustar finamente os parâmetros visuais do código de barras melhora a confiabilidade da leitura e adequa‑se às diretrizes de branding.

```python
# Set module (pixel) size – larger values increase overall image size
qr_generator.parameters.barcode.x_dimension = 4      # each module = 4 pixels

# Set border thickness – a thin white border helps scanners isolate the QR code
qr_generator.parameters.barcode.border_width = 2    # 2-pixel border
```

**Por que isso importa:**  
- **`x_dimension`** controla o tamanho de cada módulo QR; muito pequeno pode causar erros de leitura em dispositivos de baixa resolução.
- **`border_width`** adiciona uma zona silenciosa. Alguns scanners exigem ao menos uma zona silenciosa de 4 módulos; a biblioteca adiciona isso automaticamente, mas você pode aumentá‑la para maior segurança.

### Tratamento de casos extremos

- **Dados de alta densidade:** Se os dados codificados forem extensos, pode ser necessário aumentar `x_dimension` ou escolher um nível de correção de erro maior (via `qr_generator.parameters.qr.error_correction_level`).
- **Fundo transparente:** Defina `qr_generator.parameters.barcode.bg_color = Color.Transparent` para PNGs com canal alfa.

## Etapa 5: Salvar a imagem do código de barras QR

Por fim, grave a imagem no disco no formato desejado.

```python
# Define output path – replace YOUR_DIRECTORY with an actual folder
output_file = "YOUR_DIRECTORY/extended_qr.png"

# Save as PNG; other formats include JPEG, BMP, GIF, TIFF
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

**Por que isso importa:**  
Salvar como PNG preserva qualidade sem perdas, o que é ideal para códigos QR que precisam de bordas nítidas. Se precisar de outro formato para uma aplicação web, basta alterar a enumeração `BarCodeImageFormat`.

### Verificando o resultado

Abra o arquivo salvo em qualquer visualizador de imagens. Você deverá ver um código QR que, ao ser escaneado, retorna a string combinada:

```
ABC12345
こんにちは
```

A maioria dos aplicativos modernos de leitura de QR exibe primeiro o segmento simples e depois renderiza a saudação em japonês corretamente.

---

## Script completo executável

Copie todo o bloco abaixo para um arquivo chamado `create_qr_barcode.py` e execute-o com `python create_qr_barcode.py`. Ajuste `YOUR_DIRECTORY` para uma pasta gravável em sua máquina.

```python
# create_qr_barcode.py
from asposebarcode import (
    BuildVersionInfo,
    ExtCodetextBuilder,
    BarCodeGenerator,
    EncodeTypes,
    BarCodeImageFormat,
)

# 1️⃣ Display library version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)

# 2️⃣ Build extended codetext (plain + Japanese Unicode)
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC12345")
ext_builder.add_eci_codetext(26, "こんにちは")
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")

# 3️⃣ Create QR generator
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)

# 4️⃣ Optional visual tweaks
qr_generator.parameters.barcode.x_dimension = 4
qr_generator.parameters.barcode.border_width = 2

# 5️⃣ Save image
output_file = "YOUR_DIRECTORY/extended_qr.png"
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

Executar este script imprime a versão, o codetext estendido e uma confirmação de que o arquivo PNG foi criado.

---

## Conclusão

Agora você sabe como **criar imagens de código de barras QR** em Python usando Aspose.BarCode. O tutorial abordou:

1. Verificar a versão da biblioteca.
2. Construir codetext estendido com segmentos simples e ECI (Unicode).
3. Gerar o código QR.
4. Personalizar parâmetros visuais como tamanho do módulo e largura da borda.
5. Salvar a imagem final em formato PNG.

A partir daqui, você pode explorar:

- Alterar níveis de correção de erro (`qr_generator.parameters.qr.error_correction_level`).
- Adicionar um logotipo ou imagem de fundo (`qr_generator.parameters.qr.logo`).
- Exportar para outros formatos como SVG para gráficos web escaláveis.
- Integrar o gerador em um endpoint Flask ou Django para criação de QR sob demanda.

Experimente diferentes cargas de dados e configurações visuais para adequar‑se ao branding e aos requisitos de leitura da sua aplicação. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [How to create dotcode extended codetext with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Create barcode aspose .net - Configuring DataMatrix Code Text](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}