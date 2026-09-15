---
category: general
date: 2026-07-15
description: Como gerar imagem de código QR em Python usando Aspose.Barcode. Aprenda
  passo a passo a criação de código QR com texto estendido, codificação ECI e suporte
  a Unicode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate qr code image
- Aspose.Barcode QR
- Python barcode generation
- extended codetext builder
- ECI encoding in QR
- QR code with Unicode
language: pt
lastmod: 2026-07-15
og_description: Como gerar imagem de código QR em Python com Aspose.Barcode. Este
  guia orienta você na criação de códigos QR usando texto de código estendido, codificação
  ECI e caracteres Unicode.
og_image_alt: Python script generating a QR code image with extended codetext via
  Aspose.Barcode
og_title: Como gerar imagem de código QR em Python – Tutorial completo do Aspose.Barcode
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: How to generate QR code image in Python using Aspose.Barcode. Learn
    step‑by‑step QR code creation with extended codetext, ECI encoding, and Unicode
    support.
  headline: How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide
  type: TechArticle
- description: How to generate QR code image in Python using Aspose.Barcode. Learn
    step‑by‑step QR code creation with extended codetext, ECI encoding, and Unicode
    support.
  name: How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide
  steps:
  - name: 1. *What if I need more than two segments?*
    text: Simply call `add_plain_codetext` or `add_eci_codetext` as many times as
      you like. The builder maintains the correct ordering, so the QR code will contain
      each segment in the sequence you add them.
  - name: 2. *Can I embed emojis?*
    text: "Yes—emojis are just Unicode characters. Use the UTF‑8 ECI (value 26) and
      pass the emoji string, e.g., `builder.add_eci_codetext(26, \"\U0001F680\")`.
      The QR will display the rocket emoji on supporting scanners."
  - name: 3. *What if the QR becomes too dense?*
    text: 'QR codes have version limits. If you exceed the data capacity, Aspose will
      automatically bump the version up to the next size, but the image might become
      larger. To control size, you can lower the error correction level:'
  - name: 4. *Do I need to worry about character sets other than UTF‑8?*
    text: Only if you have legacy systems that require a specific encoding (e.g.,
      ISO‑8859‑1). In that case, replace `26` with the appropriate ECI value (see
      Aspose’s ECI table). For most modern apps, UTF‑8 is the safest bet.
  - name: 5. *How do I add a logo in the center?*
    text: 'Aspose.Barcode supports `barcode.generator.QRCodeParameters.logo_image`.
      Load an image with Pillow (`from PIL import Image`) and assign it:'
  type: HowTo
tags:
- QR code
- Python
- Aspose
title: Como gerar imagem de código QR em Python com Aspose.Barcode – Guia completo
url: /pt/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Gerar Imagem de Código QR em Python com Aspose.Barcode – Guia Completo

Já se perguntou **como gerar imagem de código QR** em Python sem precisar vasculhar dezenas de bibliotecas? Você não está sozinho. Muitos desenvolvedores precisam de uma forma confiável de incorporar texto multilíngue — pense em russo, árabe ou emoji — dentro de um QR code, e as bibliotecas nativas frequentemente ficam aquém.

A verdade é que o Aspose.Barcode para Python torna isso surpreendentemente simples. Neste tutorial vamos percorrer os passos exatos, desde a instalação do pacote até a criação de uma string de codetexto estendido que mistura ASCII puro com Unicode codificado em ECI. Ao final, você terá uma imagem de QR code pronta para uso gravada no disco.

## O Que Este Guia Cobre

- Instalação do **Aspose.Barcode** para Python (compatível com Python 3.8+)
- Construção de um **codetexto estendido** que combina segmentos plain e Unicode
- Uso da **codificação ECI** para renderizar corretamente caracteres russos
- Configuração do `BarcodeGenerator` para produzir um QR code
- Salvamento da imagem de saída em formato PNG
- Dicas, armadilhas comuns e ideias para próximos passos (como adicionar logos ou ajustar a correção de erro)

Nenhuma experiência prévia com Aspose é necessária; basta uma configuração básica de Python e curiosidade sobre QR codes.

---

## Pré‑requisitos

Antes de mergulharmos, certifique‑se de que você tem:

1. **Python 3.8 ou mais recente** instalado na sua máquina.  
2. Um **ambiente virtual** (opcional, mas recomendado) para manter as dependências organizadas.  
3. Acesso ao **pip** para instalar o pacote `aspose-barcode`.  
4. Permissão de escrita em uma pasta onde o PNG gerado será salvo.

Se algum desses itens lhe for desconhecido, pause aqui e configure‑os — quando estiverem prontos, o resto será simples como uma torta.

---

## Etapa 1: Instalar Aspose.Barcode para Python

O primeiro obstáculo é obter a biblioteca. Aspose distribui seus pacotes no PyPI, então um único comando `pip` resolve tudo:

```bash
pip install aspose-barcode
```

> **Dica profissional:** Se você estiver dentro de um ambiente virtual, manterá seus site‑packages globais limpos. Se encontrar erros de permissão, adicione `--user` ou execute o comando com `sudo` (embora este último raramente seja necessário em configurações modernas).

Após a instalação terminar, você pode verificá‑la com:

```python
import aspose.barcode as barcode
print(barcode.__version__)   # Should print something like 23.12.0
```

Se a versão for exibida sem reclamações, está tudo pronto.

---

## Etapa 2: Criar uma Instância do **Extended Codetext Builder**

Aspose.Barcode fornece a classe `ExtCodetextBuilder` para compor cargas úteis de QR complexas. Pense nela como um pequeno editor de texto que sabe como prefixar os caracteres de controle corretos para cada segmento.

```python
# Step 2: Initialise the builder
builder = barcode.generation.ExtCodetextBuilder()
```

Por que usar um builder? Concatenar bytes brutos diretamente é propenso a erros; o builder garante as trocas corretas de ECI (Extended Channel Interpretation), de modo que seu scanner de QR decode cada idioma corretamente.

---

## Etapa 3: Começar do Zero (Opcional, mas Limpo)

Se você reutilizar a mesma instância do builder, chamar `clear()` limpa quaisquer dados anteriores. É uma rede de segurança que impede que segmentos residuais vaze para o próximo QR.

```python
# Step 3: Ensure the builder is empty
builder.clear()
```

Você pode pular esta linha na primeira execução do script, mas mantê‑la torna o código idempotente — útil quando você incorpora essa lógica dentro de uma função que pode ser chamada repetidamente.

---

## Etapa 4: Adicionar um Segmento Plain (Não Codificado)

A maioria dos QR codes começa com uma simples string ASCII — talvez um identificador ou uma URL. O método `add_plain_codetext` adiciona exatamente isso, sem nenhum marcador ECI.

```python
# Step 4: Add plain ASCII text
builder.add_plain_codetext("HelloWorld")
```

Neste exemplo usamos `"HelloWorld"` como placeholder. Substitua‑o pelo que precisar — talvez um SKU de produto ou uma mensagem curta.

---

## Etapa 5: Adicionar um Segmento **Codificado em ECI** (UTF‑8 = 26)

Agora vem a parte multilíngue. O valor ECI **26** corresponde ao UTF‑8, o padrão de fato para Unicode. Ao passar `26` junto com uma frase em russo, informamos ao scanner de QR para mudar para UTF‑8 antes de ler os caracteres seguintes.

```python
# Step 5: Append a Russian phrase using UTF‑8 ECI (value 26)
builder.add_eci_codetext(26, "Привет")   # "Privet" means "Hello" in Russian
```

Você pode trocar `26` por outros valores ECI (por exemplo, `27` para ISO‑8859‑1) se precisar de uma codificação diferente. O builder inserirá automaticamente os caracteres de controle adequados.

---

## Etapa 6: Recuperar o Codetexto Estendido Combinado

Depois que todos os segmentos forem adicionados, recupere a string final que o gerador de QR consumirá. Essa string contém sequências de controle invisíveis, mas ainda pode ser impressa para depuração.

```python
# Step 6: Get the full extended codetext
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

A saída no console aparecerá embaralhada (por causa dos bytes de controle embutidos), o que é perfeitamente normal. O importante é que o builder juntou as partes plain e Unicode corretamente.

---

## Etapa 7: Configurar o Barcode Generator

Agora entregamos o codetexto estendido ao `BarcodeGenerator` da Aspose. Defina a simbologia para `QR` e atribua a string combinada a `code_text`.

```python
# Step 7: Initialise the QR code generator
generator = barcode.generation.BarcodeGenerator()
generator.symbology = barcode.Symbology.QR          # Choose QR symbology
generator.code_text = extended_codetext           # Use the extended codetext
```

Você pode ajustar propriedades adicionais aqui — como `resolution`, `error_correction_level` ou `foreground_color`. Essas opções estão cobertas na documentação da Aspose, mas para uma imagem básica os padrões funcionam bem.

---

## Etapa 8: Salvar a Imagem do QR Code Gerada

Por fim, grave o QR code no disco. O método `save` aceita um caminho de arquivo e um formato opcional; PNG é um padrão seguro.

```python
# Step 8: Persist the QR code as a PNG file
output_path = "qr_extended.png"   # Adjust path as needed
generator.save(output_path)
print(f"QR code saved to {output_path}")
```

Abra o `qr_extended.png` resultante com qualquer visualizador de imagens. Escaneá‑lo com um smartphone deve revelar duas mensagens separadas: “HelloWorld” e “Привет”. A maioria dos leitores modernos de QR lida automaticamente com a troca de ECI.

---

## Exemplo Completo em Funcionamento

Juntando tudo, aqui está o script completo que você pode copiar‑colar e executar:

```python
import aspose.barcode as barcode

# Initialise the extended codetext builder
builder = barcode.generation.ExtCodetextBuilder()
builder.clear()                                   # Ensure a clean start
builder.add_plain_codetext("HelloWorld")          # Plain ASCII segment
builder.add_eci_codetext(26, "Привет")            # Russian UTF‑8 segment
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# Configure the QR generator
generator = barcode.generation.BarcodeGenerator()
generator.symbology = barcode.Symbology.QR
generator.code_text = extended_codetext

# Save the image
output_file = "qr_extended.png"
generator.save(output_file)
print(f"QR code image saved as {output_file}")
```

**Saída esperada** (console):

```
Extended codetext: <binary data>   # appears garbled due to ECI markers
QR code image saved as qr_extended.png
```

Abra `qr_extended.png` → escaneie → você verá “HelloWorld” seguido de “Привет”.

---

## Perguntas Frequentes & Casos de Borda

### 1. *E se eu precisar de mais de dois segmentos?*  
Basta chamar `add_plain_codetext` ou `add_eci_codetext` quantas vezes quiser. O builder mantém a ordem correta, então o QR code conterá cada segmento na sequência em que foram adicionados.

### 2. *Posso incorporar emojis?*  
Sim — emojis são apenas caracteres Unicode. Use o ECI UTF‑8 (valor 26) e passe a string do emoji, por exemplo `builder.add_eci_codetext(26, "🚀")`. O QR exibirá o emoji de foguete em scanners que o suportem.

### 3. *E se o QR ficar muito denso?*  
QR codes têm limites de versão. Se você ultrapassar a capacidade de dados, Aspose aumentará automaticamente a versão para o próximo tamanho, mas a imagem pode ficar maior. Para controlar o tamanho, você pode reduzir o nível de correção de erro:

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorCorrectionLevel.L
```

### 4. *Preciso me preocupar com conjuntos de caracteres diferentes de UTF‑8?*  
Só se você tiver sistemas legados que exijam uma codificação específica (por exemplo, ISO‑8859‑1). Nesse caso, substitua `26` pelo valor ECI apropriado (veja a tabela de ECI da Aspose). Para a maioria das aplicações modernas, UTF‑8 é a escolha mais segura.

### 5. *Como adiciono um logo no centro?*  
Aspose.Barcode suporta `barcode.generator.QRCodeParameters.logo_image`. Carregue uma imagem com Pillow (`from PIL import Image`) e atribua‑a:

```python
from PIL import Image
logo = Image.open("logo.png")
generator.parameters.qr.logo_image = logo
```

O logo será sobreposto preservando a escaneabilidade (Aspose ajusta automaticamente as zonas silenciosas).

---

## Dicas Profissionais para Uso em Produção

- **Cache o builder** se você gerar o mesmo QR repetidamente; isso evita reconstruir a string estendida a cada vez.
- **Valide a saída** com um teste unitário que decodifique o QR (por exemplo, usando `zxing` ou `pyzbar`) para garantir que as trocas de ECI estejam corretas.
- **Defina um nome de arquivo determinístico** (talvez incluindo um hash da carga) para evitar sobrescrever imagens existentes.
- **Fique atento à licença**: Aspose.Barcode é software comercial. A avaliação gratuita funciona para desenvolvimento, mas uma licença é necessária para implantação em produção.

---

## Próximos Passos & Tópicos Relacionados

Agora que você sabe **como gerar QR code**


## O Que Você Deve Aprender a Seguir?


Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to create dotcode extended codetext with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}