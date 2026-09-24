---
category: general
date: 2026-07-18
description: Use extcodetextbuilder aspose para criar códigos QR que combinam texto
  ASCII simples e texto russo em UTF‑8. Aprenda a geração de códigos QR com Aspose.Barcode
  em Python.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- use extcodetextbuilder aspose
- Aspose.Barcode
- ECI encoding
- QR Code generation
- mixed codetext
language: pt
lastmod: 2026-07-18
og_description: Use o ExtCodeTextBuilder da Aspose permite que você misture fragmentos
  simples e codificados em UTF‑8 em um QR Code. Siga este guia passo a passo para
  Aspose.Barcode em Python.
og_image_alt: use extcodetextbuilder aspose QR code example showing mixed ECI text
og_title: usar extcodetextbuilder aspose – Crie códigos QR com texto ECI misto
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  headline: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  type: TechArticle
- description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  name: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  steps:
  - name: What if my scanner doesn’t recognize the Cyrillic part?
    text: Make sure the scanning app advertises ECI support. Older hardware may ignore
      the ECI segment and treat the bytes as ISO‑8859‑1, resulting in garbled characters.
  - name: Can I add more than two fragments?
    text: Absolutely. Call `add_plain_codetext` or `add_eci_codetext` as many times
      as you need. The builder will concatenate them in the order you invoke the methods.
  - name: How do I change the QR Code size or foreground color?
    text: 'Use the `qr_generator.parameters` object:'
  - name: Is there a way to embed binary data (e.g., a small file) alongside text?
    text: Yes. Use `add_binary_codetext` with a byte array, and pair it with an appropriate
      ECI if the binary represents a specific character set. The builder will handle
      the necessary mode switches.
  type: HowTo
tags:
- barcode
- Aspose
- Python
- QR Code
- ECI
title: 'use extcodetextbuilder aspose: Gerar códigos QR com texto ECI misto'
url: /pt/python/general/use-extcodetextbuilder-aspose-generate-qr-codes-with-mixed-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# use extcodetextbuilder aspose – Build QR Codes with Mixed ECI Text

Já se perguntou como **usar extcodetextbuilder aspose** para incorporar caracteres em inglês e cirílico em um único QR Code? Você não está sozinho. Muitos desenvolvedores encontram dificuldades ao precisar misturar dados ASCII e não‑ASCII, especialmente quando o scanner de destino espera marcadores ECI (Extended Channel Interpretation) corretos.  

Neste tutorial vamos percorrer passo a passo as etapas exatas para criar um QR Code que contém “HELLO123” **e** a palavra russa “Привет”, tudo com a API Python do Aspose.Barcode. Ao final você terá um script pronto‑para‑executar, entenderá por que cada chamada é importante e saberá como ajustar o processo para outras línguas ou formatos de dados.

## O que você aprenderá

- Como **inicializar ExtCodetextBuilder** e adicionar fragmentos simples e codificados em ECI.  
- Por que o valor de codificação **ECI** `3` corresponde ao UTF‑8 e como isso afeta a leitura.  
- A sequência exata para configurar um **gerador de QR Code** com Aspose.Barcode.  
- Como salvar a imagem resultante e verificar o conteúdo misto.  

**Pré‑requisitos** – você precisa do Python 3.8+, do pacote `aspose-barcode` instalado (`pip install aspose-barcode`), e de uma pasta onde possa gravar imagens. Nada mais.

---

## usar extcodetextbuilder aspose para construir codetext misto

A primeira coisa que precisamos é de uma instância `ExtCodetextBuilder`. Pense nele como um padrão builder que concatena diferentes trechos de texto enquanto insere automaticamente os marcadores ECI corretos nos bastidores.

```python
# Step 1: Build an extended codetext that mixes plain and ECI‑encoded fragments
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

# Create the builder object
ext_builder = ExtCodetextBuilder()

# Add plain ASCII text – this part needs no special handling
ext_builder.add_plain_codetext("HELLO123")                     # Plain ASCII text

# Add UTF‑8 encoded Russian text – ECI value 3 signals UTF‑8 to the scanner
ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")  # UTF‑8 encoded Russian text

# Retrieve the combined string that Aspose.Barcode will consume
extended_codetext = ext_builder.get_extended_codetext()
```

**Por que isso importa:**  
- `add_plain_codetext` mantém os dados como‑estão, o que é perfeito para números ou letras em inglês.  
- `add_eci_codetext` insere um segmento ECI (`[ECI:3]`) antes da string fornecida, informando a qualquer leitor compatível que os bytes seguintes são UTF‑8. Sem isso, o scanner interpretaria os bytes cirílicos como lixo.

> **Dica profissional:** Se precisar de um conjunto de caracteres diferente, altere o valor `eci_encoding` de acordo com a tabela ECI (por exemplo, `26` para ISO‑8859‑1).  

---

## Inicializar geração de QR Code com Aspose.Barcode

Agora que temos um `extended_codetext` formatado corretamente, podemos passá‑lo ao gerador de QR Code. Aspose.Barcode abstrai a criação de baixa‑nível da matriz QR, permitindo que você se concentre nos dados.

```python
# Step 2: Initialise a QR Code generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)   # Choose QR as the symbology
```

**O que está acontecendo aqui?**  
- `BarcodeGenerator()` cria um novo objeto gerador com configurações padrão (tamanho, resolução, etc.).  
- `set_symbology` informa ao motor que queremos um QR Code em vez, por exemplo, de um Code128.  

Se precisar de um nível de correção de erro mais alto, pode chamar `qr_generator.parameters.barcode.qr_error_level = ...` antes de atribuir o codetext.

---

## Atribuir o codetext estendido ao gerador de QR

Com o gerador pronto, o próximo passo é simplesmente alimentar a string mista que construímos anteriormente.

```python
# Step 3: Assign the extended codetext to the generator
qr_generator.set_extended_codetext(extended_codetext)
```

**Por que não usar `set_codetext`?**  
`set_codetext` trata a entrada como texto simples, removendo quaisquer marcadores ECI. `set_extended_codetext` preserva os bytes brutos, incluindo o segmento ECI, garantindo que o scanner veja a mudança de idioma correta.

---

## Salvar a imagem do QR Code e verificar o resultado

Por fim, gravamos o QR Code no disco. Aspose.Barcode suporta PNG, JPEG, BMP e mais; PNG é uma escolha segura porque preserva os dados sem perdas.

```python
# Step 4: Save the generated QR Code image
qr_generator.save("YOUR_DIRECTORY/qr_extended.png")
```

Agora você deve ter um arquivo PNG no local especificado. Abra‑o com qualquer aplicativo de leitura de QR que suporte ECI (a maioria dos smartphones modernos suporta). Escaneie uma vez – você verá “HELLO123”. Escaneie novamente (ou use um scanner que mostre os dados brutos) – você também obterá “Привет”. As duas partes aparecem como um único payload, exatamente como construímos.

![exemplo de código QR use extcodetextbuilder aspose mostrando texto ECI misto](YOUR_DIRECTORY/qr_extended.png)

*Texto alternativo da imagem: exemplo de código QR use extcodetextbuilder aspose mostrando texto ECI misto*

---

## Script completo, pronto‑para‑executar

Juntando tudo, aqui está o programa completo que você pode copiar‑colar em um arquivo chamado `qr_mixed_eci.py`:

```python
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

def generate_mixed_eci_qr(output_path: str):
    # Build mixed codetext
    ext_builder = ExtCodetextBuilder()
    ext_builder.add_plain_codetext("HELLO123")
    ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_codetext = ext_builder.get_extended_codetext()

    # Initialise QR generator
    qr_generator = BarcodeGenerator()
    qr_generator.set_symbology(Symbology.QR)

    # Assign extended codetext
    qr_generator.set_extended_codetext(extended_codetext)

    # Save image
    qr_generator.save(output_path)
    print(f"QR Code saved to {output_path}")

if __name__ == "__main__":
    generate_mixed_eci_qr("qr_extended.png")
```

Execute-o com:

```bash
python qr_mixed_eci.py
```

Você verá uma mensagem no console confirmando o local de salvamento, e o PNG aparecerá exatamente onde você indicou.

---

## Perguntas frequentes e casos de borda

### E se o meu scanner não reconhecer a parte em cirílico?
Certifique‑se de que o aplicativo de escaneamento anuncia suporte a ECI. Hardware mais antigo pode ignorar o segmento ECI e tratar os bytes como ISO‑8859‑1, resultando em caracteres corrompidos.

### Posso adicionar mais de dois fragmentos?
Com certeza. Chame `add_plain_codetext` ou `add_eci_codetext` quantas vezes precisar. O builder concatenará na ordem em que os métodos forem invocados.

### Como mudar o tamanho do QR Code ou a cor de primeiro plano?
Use o objeto `qr_generator.parameters`:

```python
qr_generator.parameters.barcode.x_dimension = 4   # module size in points
qr_generator.parameters.barcode.qr_error_level = qr_generator.parameters.barcode.QrErrorLevel.QR_ECLEVEL_Q
qr_generator.save("qr_custom.png", BarCodeImageFormat.PNG, 300)  # 300 DPI
```

### Existe uma forma de incorporar dados binários (por exemplo, um pequeno arquivo) junto ao texto?
Sim. Use `add_binary_codetext` com um array de bytes e combine‑o com um ECI apropriado se o binário representar um conjunto de caracteres específico. O builder cuidará das mudanças de modo necessárias.

---

## Conclusão

Agora você sabe **como usar extcodetextbuilder aspose** para criar QR Codes que mesclam perfeitamente texto ASCII simples e texto russo codificado em UTF‑8. Ao aproveitar o `ExtCodetextBuilder`, definir a codificação **ECI** correta e alimentar o resultado em um **gerador de QR Code Aspose.Barcode**, obtém‑se uma única imagem compatível com padrões que funciona em scanners modernos.  

A partir daqui, experimente trocar `eci_encoding=3` por outros identificadores de idioma, ou teste fragmentos simples adicionais para montar payloads multilíngues. Você também pode explorar as opções `BarCodeImageFormat` para gerar SVG ou PDF caso precise de gráficos vetoriais.  

Feliz codificação, e sinta‑se à vontade para deixar um comentário se encontrar algum obstáculo — seu feedback ajuda a melhorar ainda mais estes guias!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código totalmente funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [Gerar código de barras Java – Definir texto do código usando Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)
- [Criar código de barras aspose .net – Configurando texto do DataMatrix](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Codificação de texto de código Aztec com Aspose.BarCode para .NET](/barcode/english/net/aztec-barcode-encoding/aztec-code-text-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}