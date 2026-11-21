---
category: general
date: 2026-11-20
description: Aprenda a usar ECI, gerar QR a partir de texto, limpar o construtor e
  salvar a imagem QR usando a biblioteca de códigos de barras do Python.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use eci
- generate qr from text
- how to clear builder
- save qr image
- clear qr builder
language: pt
lastmod: 2026-11-20
og_description: Como usar ECI para gerar QR a partir de texto, limpar o construtor
  de QR e salvar a imagem QR – um guia completo passo a passo.
og_image_alt: Diagram illustrating how to use ECI to generate a QR code and save the
  QR image
og_title: Como usar ECI na geração de códigos QR com Python
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to use ECI, generate QR from text, clear the builder, and
    save QR image using the Python barcode library.
  headline: How to use ECI in QR code generation with Python
  type: TechArticle
tags:
- QR code
- Python
- barcode
- ECI
title: Como usar ECI na geração de códigos QR com Python
url: /pt/python/general/how-to-use-eci-in-qr-code-generation-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como usar ECI na geração de QR code com Python

Se você precisa **saber como usar eci** ao criar QR codes, este guia mostra os passos exatos. Você verá como gerar QR a partir de texto, limpar o builder e, finalmente, salvar a imagem QR — tudo com algumas linhas de Python.

QR codes que contêm dados multilíngues frequentemente requerem um segmento Extended Channel Interpretation (ECI) para que os leitores saibam qual conjunto de caracteres aplicar. Este tutorial orienta você na construção de um codetext estendido, na limpeza do builder ao reutilizá‑lo e na persistência do resultado como um arquivo PNG.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

- Python 3.8+ instalado.
- O pacote Aspose.BarCode for Python via .NET (ou qualquer biblioteca `barcode` compatível que forneça `ExtCodetextBuilder` e `BarcodeGenerator`).
- Familiaridade básica com conceitos de QR code.

Instale a biblioteca com pip:

```bash
pip install aspose-barcode
```

> **Dica profissional:** Use um ambiente virtual para evitar conflitos de versão.

## Etapa 1: Importar as classes necessárias

As classes principais com as quais você trabalhará são `ExtCodetextBuilder` para construir o codetext estendido e `BarcodeGenerator` para renderizar o QR code.

```python
from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
```

Essas importações dão acesso aos métodos do builder (`add_plain_codetext`, `add_eci_codetext`, etc.) e às funções do gerador `set_code_text`, `set_symbology` e `save`.

## Etapa 2: Criar e configurar o ExtCodetextBuilder

Criar uma nova instância do builder é o primeiro exemplo concreto de **como usar eci**. Você também pode limpar o builder posteriormente se precisar reutilizá‑lo.

```python
# Create an ExtCodetextBuilder instance
extended_text_builder = ExtCodetextBuilder()

# Optional: clear any previous items (useful when reusing the same builder)
extended_text_builder.clear()   # this demonstrates how to clear builder
```

Chamar `clear()` garante que o builder comece em um estado limpo, o que é essencial ao gerar múltiplos QR codes em um loop.

## Etapa 3: Adicionar codetext simples (sem ECI)

Texto simples não precisa de um segmento ECI. Use `add_plain_codetext` para strings compatíveis com ASCII.

```python
# Add plain codetext (e.g., an English phrase)
extended_text_builder.add_plain_codetext("HelloWorld")
```

O builder agora contém o segmento simples `"HelloWorld"`.

## Etapa 4: Adicionar um segmento codificado com ECI

Aqui está o núcleo de **como usar eci**: você especifica o valor ECI (26 para UTF‑8) e fornece a string Unicode que deseja codificar. Isso permite que o QR code carregue russo, chinês ou qualquer outro idioma que não esteja coberto pelo conjunto padrão ISO‑8859‑1.

```python
# Add ECI‑encoded codetext (ECI value 26 = UTF‑8, Russian “Hello”)
extended_text_builder.add_eci_codetext(26, "Привет")
```

> **Por que isso importa:** Sem o indicador ECI, um leitor interpretaria os bytes usando o conjunto de caracteres padrão e exibiria caracteres corrompidos para textos não‑ASCII.

## Etapa 5: Recuperar a string combinada de codetext estendido

Depois de adicionar todos os segmentos necessários, obtenha a string final que será passada ao gerador de QR.

```python
combined_extended_text = extended_text_builder.get_extended_codetext()
print("Extended codetext:", combined_extended_text)
```

O valor impresso se parece com algo assim:

```
Extended codetext: [ECI26]ПриветHelloWorld
```

O formato exato depende da biblioteca, mas a parte importante é que o marcador ECI (`[ECI26]`) precede a carga UTF‑8.

## Etapa 6: Gerar o QR code usando o texto combinado

Agora você pode **gerar QR a partir de texto** passando o codetext estendido para `BarcodeGenerator`.

```python
# Initialize the QR generator
qr_generator = barcode.generation.BarcodeGenerator()

# Assign the combined extended codetext
qr_generator.set_code_text(combined_extended_text)

# Choose QR symbology (the library supports many, QR is the most common)
qr_generator.set_symbology(barcode.Symbology.QR)

# Save the QR image to disk – this demonstrates how to save QR image
output_path = "qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

Ao abrir `qr_extended.png`, aparecerá um QR code que codifica tanto a string em inglês simples quanto a saudação em russo. Escaneando-o com um leitor QR moderno, será exibido corretamente “HelloWorld” e “Привет”.

### Por que você deve chamar `clear()` antes de reutilizar o builder

Se você gerar múltiplos QR codes em um loop, esquecer de limpar o builder concatenará segmentos antigos com os novos, produzindo um código inválido. Veja um padrão rápido:

```python
for text, eci, unicode_str in data_set:
    extended_text_builder.clear()                       # ensures a fresh start
    extended_text_builder.add_plain_codetext(text)
    extended_text_builder.add_eci_codetext(eci, unicode_str)
    qr_generator.set_code_text(extended_text_builder.get_extended_codetext())
    qr_generator.save(f"qr_{text}.png")
```

Este trecho ilustra **como limpar o builder** e **como gerar QR a partir de texto** repetidamente.

## Casos de borda e armadilhas comuns

| Situação | O que observar | Como lidar |
|-----------|-------------------|---------------|
| **Valor ECI não suportado** | A biblioteca lança `InvalidArgumentException`. | Use apenas valores ECI listados na especificação (ex.: 26 para UTF‑8, 20 para Shift‑JIS). |
| **Texto combinado muito longo** | A versão do QR pode exceder a capacidade máxima. | Aumente a versão do QR automaticamente (`qr_generator.set_qr_version(QRVersion.AUTO)`) ou divida os dados em vários QR codes. |
| **Erros de permissão no sistema de arquivos** | `save` falha com `IOError`. | Garanta que o diretório de destino exista e que o processo tenha permissão de escrita. |
| **Exibição incorreta de charset** | O leitor mostra caracteres corrompidos. | Verifique se o valor ECI correto corresponde à codificação real da string. |

## Exemplo completo executável

Abaixo está um script autocontido que você pode copiar, colar e executar. Ele inclui todas as importações, tratamento de erros e comentários para clareza.

```python
# qr_eci_example.py
# Demonstrates how to use ECI, generate QR from text, clear the builder,
# and save QR image using Aspose.BarCode for Python.

from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
import os

def generate_qr(plain_text: str, eci_value: int, unicode_text: str, out_file: str):
    """
    Creates a QR code that contains both plain and ECI‑encoded text.
    Parameters:
        plain_text – ASCII‑compatible string.
        eci_value  – Numeric ECI identifier (e.g., 26 for UTF‑8).
        unicode_text – Text that requires the specified ECI.
        out_file – Destination file path for the PNG image.
    """
    # Step 1: instantiate and clear the builder
    builder = ExtCodetextBuilder()
    builder.clear()                       # how to clear builder

    # Step 2: add segments
    builder.add_plain_codetext(plain_text)
    builder.add_eci_codetext(eci_value, unicode_text)

    # Step 3: retrieve combined text
    combined = builder.get_extended_codetext()
    print("Combined extended codetext:", combined)

    # Step 4: generate QR code
    generator = barcode.generation.BarcodeGenerator()
    generator.set_code_text(combined)
    generator.set_symbology(barcode.Symbology.QR)

    # Ensure output directory exists
    os.makedirs(os.path.dirname(out_file), exist_ok=True)

    # Step 5: save QR image – how to save QR image
    generator.save(out_file)
    print(f"QR code saved as {out_file}")

if __name__ == "__main__":
    # Example usage
    generate_qr(
        plain_text="HelloWorld",
        eci_value=26,               # UTF‑8
        unicode_text="Привет",      # Russian "Hello"
        out_file="output/qr_extended.png"
    )
```

Executar este script gera `output/qr_extended.png`, um QR code que codifica corretamente texto em inglês e russo.

## Conclusão

Agora você sabe **como usar eci** ao construir QR codes, como **limpar o builder de QR** antes de reutilizá‑lo, como **gerar QR a partir de texto** e os passos exatos para **salvar a imagem QR** com Python. Seguindo o padrão acima, você pode incorporar qualquer string Unicode em um QR code mantendo o estado do builder previsível.

### O que vem a seguir?

- Explore outros valores ECI para idiomas como chinês (ECI 20) ou ISO‑8859‑5.
- Ajuste os níveis de correção de erro (`qr_generator.set_error_correction_level`) para melhorar a confiabilidade da leitura.
- Combine múltiplos segmentos ECI em um único QR para mensagens multilíngues.

Feliz codificação e aproveite a criação de QR codes multilíngues!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to generate barcode with ECI using Aspose.Barcode Python](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [How to generate barcode in Python – complete step‑by‑step guide](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}