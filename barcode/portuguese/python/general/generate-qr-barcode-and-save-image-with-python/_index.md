---
category: general
date: 2026-11-27
description: Gere código de barras QR em Python usando Aspose.Barcode e aprenda como
  salvar a imagem do código de barras no disco rapidamente.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate QR barcode
- save barcode image
- Aspose.Barcode Python
- extended codetext QR
- barcode version information
language: pt
lastmod: 2026-11-27
og_description: Gere código de barras QR em Python com Aspose.Barcode e salve a imagem
  do código de barras instantaneamente. Siga o exemplo completo para criar, personalizar
  e armazenar códigos QR.
og_image_alt: Screenshot of a generated QR barcode created with Python
og_title: Gerar código QR e salvar imagem com Python – guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Generate QR barcode in Python using Aspose.Barcode and learn how to
    save barcode image to disk quickly.
  headline: Generate QR barcode and save image with Python
  type: TechArticle
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: Gerar código QR e salvar imagem com Python
url: /pt/python/general/generate-qr-barcode-and-save-image-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerar código de barras QR e salvar imagem com Python

Se você precisa **gerar código de barras QR** em uma aplicação Python, este guia mostra como fazer isso usando a biblioteca Aspose.Barcode. Você também aprenderá a forma correta de **salvar a imagem do código de barras** em uma pasta local, recuperar detalhes da versão da biblioteca e lidar com segmentos de codetext estendidos.

Criar códigos QR é uma necessidade comum para sistemas de bilhetagem, pagamentos móveis e rastreamento de produtos. Ao final deste tutorial você terá um script pronto‑para‑executar que produz um arquivo de imagem de código de barras QR e imprime informações de versão para depuração ou conformidade.

## Pré-requisitos

* Python 3.8 ou mais recente instalado.
* O pacote `aspose-barcode`. Instale‑o com `pip install aspose-barcode`.
* Permissão de escrita no diretório onde a imagem do código de barras será armazenada.

Nenhum serviço externo adicional é necessário; todo o processo é executado localmente.

## Etapa 1: Construir um codetext estendido com `ExtCodetextBuilder`

O codetext estendido permite misturar texto simples e segmentos ECI (Extended Channel Interpretation) em um único código QR. Isso é útil quando você precisa incorporar caracteres de diferentes conjuntos de caracteres, como o símbolo do Euro.

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# Create the builder instance
ext_builder = ExtCodetextBuilder()

# Add a plain text segment
ext_builder.add_plain_codetext("ABC123")

# Add an ECI segment that uses ISO‑IEC 8859‑1 (code page 3)
ext_builder.add_eci_codetext(3, "€123")
```

**Por que esta etapa é importante:**  
`ExtCodetextBuilder` monta a string final que o codificador QR processará. Sem construir o codetext estendido, o código de barras conteria apenas caracteres ASCII simples e não poderia representar símbolos específicos de locale.

## Etapa 2: Recuperar a string de codetext estendido combinada

```python
# Get the final extended codetext that will be encoded
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

A saída se parece com:

```
Extended codetext: ABC123[ECI3]€123
```

O marcador `[ECI3]` entre colchetes indica ao codificador QR que ele deve mudar para o conjunto de caracteres especificado para os caracteres seguintes.

## Etapa 3: Gerar o código de barras QR usando o codetext estendido

```python
# Create a QR barcode generator with the extended codetext
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)
```

**Explicação:**  
`BarcodeGenerator` recebe dois argumentos: o tipo de código de barras (`QR`) e os dados a codificar (`extended_codetext`). O gerador prepara todas as estruturas internas necessárias para a renderização.

## Etapa 4: Salvar a imagem do código de barras gerado

```python
# Define the output path – adjust the folder as needed
output_path = "output/qr_extended.png"

# Save the image in PNG format
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")
```

**Por que você deve usar esta abordagem:**  
Chamar `save` diretamente grava a imagem no disco usando o formato inferido da extensão do arquivo. O método suporta PNG, JPEG, BMP e TIFF, oferecendo flexibilidade para diferentes consumidores posteriores.

### Verificando a imagem salva

Abra o arquivo `output/qr_extended.png` com qualquer visualizador de imagens. Você deverá ver um código QR que, ao ser escaneado, retorna a string `ABC123€123`. A maioria dos scanners QR móveis modernos lida com o segmento ECI automaticamente.

## Etapa 5: Consultar informações da versão do Aspose.BarCode (opcional, mas útil)

Conhecer a versão exata da biblioteca Aspose.BarCode ajuda quando você precisa relatar bugs ou verificar compatibilidade.

```python
# Retrieve version details
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Saída típica:

```
Aspose.BarCode version:
  Assembly version : 23.9.0.0
  File version     : 23.9.0
  Product          : Aspose.BarCode for Python via .NET
  Release date     : 2023-09-15
```

## Script completo – copie, cole e execute

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# 1️⃣ Build extended codetext
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC123")
ext_builder.add_eci_codetext(3, "€123")
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 2️⃣ Generate QR barcode
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)

# 3️⃣ Save barcode image
output_path = "output/qr_extended.png"
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")

# 4️⃣ Display version information
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Executar o script produz a imagem do código QR e imprime tanto o codetext estendido quanto os detalhes da versão no console.

## Variações comuns e casos de borda

| Situação | Ajuste recomendado |
|-----------|--------------------|
| **Conjunto de caracteres diferente** | Alterar o identificador ECI passado para `add_eci_codetext`. Para UTF‑8 use `5`. |
| **Correção de erro mais alta** | Definir `barcode.parameters.barcode.qr_error_level = bc.QRErrorLevel.H` antes de chamar `save`. |
| **Tamanho de imagem personalizado** | Usar `barcode.parameters.image_width` e `barcode.parameters.image_height` para controlar as dimensões em pixels. |
| **Saída não‑PNG** | Alterar a extensão do arquivo em `output_path` para `.jpg` ou `.bmp`. A biblioteca seleciona automaticamente o codificador correto. |

## Dicas avançadas

* **Crie a pasta de saída** programaticamente se ela puder não existir:

  ```python
  import os
  os.makedirs(os.path.dirname(output_path), exist_ok=True)
  ```

* **Valide o código QR** após a geração lendo‑o novamente com `aspose.barcode.BarcodeReader`. Isso garante que os dados codificados correspondam às expectativas, especialmente ao usar segmentos ECI.

  ```python
  reader = bc.BarcodeReader(output_path, bc.DecodeType.QR)
  for result in reader.read():
      print("Decoded text:", result.code_text)
  ```

* **Dica de desempenho** – reutilize uma única instância de `BarcodeGenerator` se precisar gerar muitos códigos QR em um loop. Redefina a propriedade `code_text` em vez de criar um novo objeto a cada iteração.

## Conclusão

Agora você sabe como **gerar código de barras QR** em Python com Aspose.Barcode, construir um codetext estendido que mistura segmentos simples e ECI, e **salvar a imagem do código de barras** corretamente no disco. O script também mostra como recuperar informações da versão da biblioteca para solução de problemas.

Os próximos passos que você pode explorar incluem:

* Adicionar sobreposição de logotipo ou cores personalizadas ao código QR.
* Incorporar o código de barras QR diretamente em PDFs usando Aspose.PDF.
* Automatizar a geração em lote para grandes conjuntos de dados.

Sinta-se à vontade para experimentar diferentes cargas de dados, níveis de correção de erro e formatos de imagem. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá-lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [How to generate Code 128 barcode and save barcode image with Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [How to generate DataMatrix barcode in Python with Aspose.BarCode](/barcode/english/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}