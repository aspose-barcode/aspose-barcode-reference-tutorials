---
date: 2026-05-19
description: Aprenda como criar código de barras Aztec usando Aspose.BarCode para
  .NET, personalizar aspect ratios, codificar bytes ou texto e master symbol modes.
keywords:
- create aztec barcode
- aztec barcode encoding
- aspose barcode .net
linktitle: Codificação de Código de Barras Aztec
schemas:
- author: Aspose
  dateModified: '2026-05-19'
  description: Learn how to create Aztec barcode using Aspose.BarCode for .NET, customize
    aspect ratios, encode bytes or text, and master symbol modes.
  headline: How to create Aztec barcode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create Aztec barcode using Aspose.BarCode for .NET, customize
    aspect ratios, encode bytes or text, and master symbol modes.
  name: How to create Aztec barcode with Aspose.BarCode for .NET
  steps:
  - name: '**Create a `BarcodeGenerator` instance** with `EncodeTypes.Aztec`.'
    text: '**Create a `BarcodeGenerator` instance** with `EncodeTypes.Aztec`.'
  - name: '**Assign your data** (text, bytes, or numeric string).'
    text: '**Assign your data** (text, bytes, or numeric string).'
  - name: '**Set `AspectRatio`** – for example, `1.5` for a wider bar.'
    text: '**Set `AspectRatio`** – for example, `1.5` for a wider bar.'
  - name: '**Generate the image** using `Save` or `GetBarCodeImage`.'
    text: '**Generate the image** using `Save` or `GetBarCodeImage`.'
  - name: '**Prepare the byte array** (e.g., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).'
    text: '**Prepare the byte array** (e.g., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).'
  - name: '**Instantiate `BarcodeGenerator`** with `EncodeTypes.Aztec`.'
    text: '**Instantiate `BarcodeGenerator`** with `EncodeTypes.Aztec`.'
  - name: '**Call `EncodeBytes(data)`** to load the binary content.'
    text: '**Call `EncodeBytes(data)`** to load the binary content.'
  - name: '**Render the barcode** with `Save` or `GetBarCodeImage`.'
    text: '**Render the barcode** with `Save` or `GetBarCodeImage`.'
  - name: '**Create the generator** with `EncodeTypes.Aztec`.'
    text: '**Create the generator** with `EncodeTypes.Aztec`.'
  - name: '**Set `CodeText`** to the string you want to encode.'
    text: '**Set `CodeText`** to the string you want to encode.'
  type: HowTo
- questions:
  - answer: The library works with .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET
      6, and later.
    question: Which .NET versions are supported by Aspose.BarCode for Aztec encoding?
  - answer: Yes—set the `Resolution` property (e.g., 300 dpi) before saving the image
      to obtain print‑ready quality.
    question: Can I create a high‑resolution Aztec barcode for printing?
  - answer: Up to 3,000 numeric or 2,300 alphanumeric characters, or roughly 1,800
      bytes of raw data in Compact mode.
    question: How large a data payload can an Aztec barcode hold?
  - answer: Absolutely—Aspose.BarCode’s decoder automatically detects orientation
      and corrects it during the read operation.
    question: Is it possible to read an Aztec barcode that has been rotated?
  - answer: A free evaluation license is available for testing; a commercial license
      is required for production deployments.
    question: Do I need a license for development and testing?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Como criar código de barras Aztec com Aspose.BarCode para .NET
url: /pt/net/aztec-barcode-encoding/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Codificação de Código de Barras Aztec

Você está pronto para mergulhar no mundo da Codificação de Código de Barras Aztec e aprender a **criar código de barras Aztec** imagens com Aspose.BarCode for .NET? Esta biblioteca oferece controle total sobre tamanho, correção de erros e representação de dados, tornando-a ideal para tudo, desde bilhetagem móvel até rastreamento de inventário.

## Respostas Rápidas
- **Qual biblioteca suporta códigos de barras Aztec?** Aspose.BarCode for .NET  
- **Posso mudar a proporção de aspecto?** Sim, via a propriedade `AspectRatio`  
- **É possível codificar em nível de byte?** Absolutamente – use o método `EncodeBytes`  
- **Quais níveis de correção de erro estão disponíveis?** Níveis 0 a 4 (mais alto = mais redundância)  
- **Preciso de uma licença para produção?** Sim, uma licença comercial remove os limites de avaliação  

## O que é um código de barras Aztec?
Um código de barras Aztec é um código matricial bidimensional que pode codificar até 3.000 caracteres numéricos ou 2.300 alfanuméricos. Ele apresenta um padrão central de localização, permitindo a leitura rápida mesmo quando o símbolo é impresso em baixa resolução. Como o padrão está localizado no centro, o código pode ser lido de qualquer direção, tornando-o altamente confiável para aplicações móveis e industriais.

## Como personalizar a proporção de aspecto de um código de barras Aztec?
`BarcodeGenerator` é a classe principal usada para criar códigos de barras no Aspose.BarCode. Defina a propriedade `AspectRatio` no objeto `BarcodeGenerator` para a proporção largura‑para‑altura desejada e, em seguida, gere a imagem. Ajustar a proporção de aspecto ajuda a encaixar o código de barras em espaços de UI restritos ou layouts de etiquetas sem sacrificar a confiabilidade da leitura, e também permite que você corresponda às diretrizes de branding ou requisitos específicos da impressora.

### Etapas para personalizar a proporção de aspecto
1. **Crie uma instância de `BarcodeGenerator`** com `EncodeTypes.Aztec`.  
2. **Atribua seus dados** (texto, bytes ou string numérica).  
3. **Defina `AspectRatio`** – por exemplo, `1.5` para uma barra mais larga.  
4. **Gere a imagem** usando `Save` ou `GetBarCodeImage`.  

## Como codificar bytes brutos em um código de barras Aztec?
`EncodeBytes` é um método que aceita um array de bytes e o converte em uma matriz Aztec. Passe um array de bytes para o método `EncodeBytes` do `BarcodeGenerator`. A API converte automaticamente os dados binários em uma matriz Aztec compacta, preservando cada bit. Isso é perfeito para incorporar cargas úteis criptografadas, identificadores binários ou arquivos compactados diretamente em um código de barras.

### Etapas para codificar bytes
1. **Prepare o array de bytes** (por exemplo, `byte[] data = Encoding.UTF8.GetBytes("Hello")`).  
2. **Instancie `BarcodeGenerator`** com `EncodeTypes.Aztec`.  
3. **Chame `EncodeBytes(data)`** para carregar o conteúdo binário.  
4. **Renderize o código de barras** com `Save` ou `GetBarCodeImage`.  

## Como codificar texto em um código de barras Aztec?
`CodeText` é uma propriedade que contém os dados em texto simples a serem codificados. Use a propriedade `CodeText` do `BarcodeGenerator` para fornecer dados em texto simples. A biblioteca seleciona automaticamente o modo de codificação ideal (numérico, alfanumérico ou byte) e aplica o nível de correção de erro apropriado. Isso facilita a incorporação de URLs, IDs de produtos ou qualquer string legível.

### Etapas para codificar texto
1. **Crie o gerador** com `EncodeTypes.Aztec`.  
2. **Defina `CodeText`** para a string que você deseja codificar.  
3. **Opcionalmente ajuste `ErrorLevel`** para maior resiliência.  
4. **Gere a imagem** usando `Save` ou `GetBarCodeImage`.  

## Como gerar códigos de barras Aztec com diferentes níveis de correção de erro?
`ErrorLevel` é uma propriedade que controla a quantidade de dados redundantes adicionados ao código de barras. Ajuste a propriedade `ErrorLevel` (0‑4) antes de renderizar. Níveis mais altos aumentam a quantidade de dados redundantes, permitindo que o código de barras seja lido mesmo quando até 30 % do símbolo está danificado. Isso é crucial para ambientes adversos, como rotulagem industrial ou sinalização externa.

### Etapas para definir a correção de erro
1. **Instancie `BarcodeGenerator`** para Aztec.  
2. **Atribua seus dados** (texto ou bytes).  
3. **Defina `ErrorLevel`** – por exemplo, `generator.Parameters.Barcode.Aztec.ErrorLevel = 3`.  
4. **Renderize o código de barras** com o formato de saída de sua preferência.  

## Quais são os diferentes modos de símbolo Aztec e como usá-los?
`SymbolMode` é uma configuração que determina o tamanho da matriz e a capacidade de dados do código Aztec gerado. O modo de símbolo Aztec determina o tamanho da matriz e a capacidade de dados. A biblioteca oferece quatro modos: **Auto**, **FullRange**, **Compact** e **Rune**.

- **Auto** – o gerador seleciona o menor tamanho possível.  
- **FullRange** – permite o tamanho máximo da matriz para conjuntos de dados muito grandes.  
- **Compact** – cria um símbolo menor e mais denso, ideal para espaço limitado.  
- **Rune** – um modo especializado para codificar runas Unicode.

Selecione o modo via `Generator.Parameters.Barcode.Aztec.SymbolMode`. Cada modo equilibra tamanho, legibilidade e capacidade de dados, permitindo que você ajuste o código de barras às restrições da sua aplicação.

## Tutoriais de Codificação de Código de Barras Aztec
Abaixo estão os guias passo a passo dedicados que aprofundam cada um dos tópicos abordados acima. Clique em qualquer link para explorar exemplos de código completos, pré‑requisitos e dicas de boas práticas.

### [Personalizar a Proporção de Aspecto do Código de Barras Aztec](./aztec-aspect-ratio-customization/)
Aprenda como personalizar as proporções de aspecto dos códigos de barras Aztec usando Aspose.BarCode for .NET. Crie códigos de barras únicos e flexíveis para suas aplicações .NET.

### [Codificação de Bytes Aztec](./aztec-bytes-encoding/)
Aprenda como realizar a Codificação de Bytes Aztec com Aspose.BarCode for .NET. Guia passo a passo, pré‑requisitos e exemplos de código incluídos.

### [Codificação de Texto do Código Aztec](./aztec-code-text-encoding/)
Descubra o poder da Codificação de Texto do Código Aztec com Aspose.BarCode for .NET. Aprenda como criar e reconhecer códigos Aztec em suas aplicações .NET.

### [Gerando Códigos de Barras Aztec com Níveis de Erro](./aztec-error-level-example/)
Aprenda como gerar códigos de barras Aztec com diferentes níveis de erro usando Aspose.BarCode for .NET. Guia abrangente para criação de códigos de barras.

### [Dominando o Modo de Símbolo Aztec](./aztec-symbol-mode-example/)
Explore o Modo de Símbolo Aztec no Aspose.BarCode for .NET e aprenda como gerar códigos de barras versáteis com facilidade. Experimente os modos Auto, FullRange, Compact e Rune neste tutorial abrangente.

## Perguntas Frequentes

**Q: Quais versões do .NET são suportadas pelo Aspose.BarCode para codificação Aztec?**  
A: A biblioteca funciona com .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6 e posteriores.

**Q: Posso criar um código de barras Aztec de alta resolução para impressão?**  
A: Sim—defina a propriedade `Resolution` (por exemplo, 300 dpi) antes de salvar a imagem para obter qualidade pronta para impressão.

**Q: Qual o tamanho máximo de carga de dados que um código de barras Aztec pode conter?**  
A: Até 3.000 caracteres numéricos ou 2.300 alfanuméricos, ou aproximadamente 1.800 bytes de dados brutos no modo Compact.

**Q: É possível ler um código de barras Aztec que foi rotacionado?**  
A: Absolutamente—o decodificador do Aspose.BarCode detecta automaticamente a orientação e a corrige durante a operação de leitura.

**Q: Preciso de uma licença para desenvolvimento e testes?**  
A: Uma licença de avaliação gratuita está disponível para testes; uma licença comercial é necessária para implantações em produção.

---

**Última atualização:** 2026-05-19  
**Testado com:** Aspose.BarCode 24.12 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Como gerar código de barras Aztec com proporção de aspecto personalizada usando Aspose.BarCode for .NET](/barcode/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Codificação de Bytes Aztec usando gerador de código de barras .net](/barcode/net/aztec-barcode-encoding/aztec-bytes-encoding/)
- [Como criar código de barras Aztec com correção de erro em .NET](/barcode/net/aztec-barcode-encoding/aztec-error-level-example/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}