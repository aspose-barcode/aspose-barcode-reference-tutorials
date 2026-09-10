---
date: 2026-06-09
description: Aprenda como gerar códigos de barras DataMatrix e salvar PNG usando codificação
  C40 com Aspose.BarCode – guia completo para geração de códigos de barras em .NET
  Core.
keywords:
- how to generate datamatrix
- barcode generation .net core
- datamatrix c40 png
linktitle: Modo de Codificação DataMatrix (C40)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  headline: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  type: TechArticle
- description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  name: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  steps:
  - name: Define the Directory Path
    text: Set the folder where the PNG image will be stored. Replace the placeholder
      with an actual path on your machine.
  - name: Set Up Barcode Generation
    text: Create a `BarcodeGenerator` instance, specify `EncodeTypes.DataMatrix`,
      and provide the data you want to encode.
  - name: Customize Barcode
    text: Configure the X‑dimension (pixel width of the modules) and switch the encoding
      mode to C40.
  - name: Save the Barcode Image
    text: Finally, save the generated barcode as a PNG file. This is the concrete
      answer to **how to save png** with Aspose.BarCode. When you run the program,
      you’ll find `DataMatrixEncodeModeC40.png` in the folder you specified, ready
      to be used in reports, labels, or web pages.
  type: HowTo
- questions:
  - answer: C40 is a compact alphanumeric encoding scheme for DataMatrix symbols,
      ideal for text that includes letters, numbers, and a limited set of special
      characters.
    question: What is DataMatrix Encoding Mode (C40)?
  - answer: You can find the documentation [here](https://reference.aspose.com/barcode/net/).
      It provides detailed guidance on all barcode types and encoding options.
    question: Where can I find the Aspose.BarCode for .NET documentation?
  - answer: Yes, the library supports a wide range of .NET versions, from .NET Framework
      4.5+ to .NET 6 and later.
    question: Is Aspose.BarCode for .NET compatible with all .NET versions?
  - answer: Yes, you can explore a free trial of Aspose.BarCode for .NET by visiting
      [this link](https://releases.aspose.com/). It allows you to test the library’s
      features and capabilities.
    question: Can I try Aspose.BarCode for .NET before purchasing?
  - answer: You can find a supportive community and access support for Aspose.BarCode
      for .NET on the [Aspose forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Como gerar DataMatrix PNG com C40 usando Aspose.BarCode
url: /pt/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Modo de Codificação Master DataMatrix (C40) com Aspose.BarCode para .NET

## Introdução

Neste tutorial você aprenderá **como gerar datamatrix** códigos de barras e salvá-los como arquivos PNG usando o modo de codificação C40 com Aspose.BarCode para .NET. Seja construindo um sistema de inventário, um gerador de etiquetas de envio ou qualquer solução que exija símbolos compactos e de alta densidade, dominar o C40 fornece símbolos menores sem sacrificar a legibilidade. Percorreremos cada passo — desde a configuração do ambiente até a produção do PNG final — para que você possa integrar o código instantaneamente ao seu projeto.

## Respostas Rápidas
- **O que significa “how to generate datamatrix”?** Criar uma imagem de código de barras DataMatrix programaticamente.  
- **Qual modo de codificação é abordado?** DataMatrix C40, um esquema alfanumérico eficiente.  
- **Preciso de uma licença?** Um teste gratuito funciona para testes; uma licença comercial é necessária para produção.  
- **Posso executar isso no .NET Core?** Sim, Aspose.BarCode suporta totalmente .NET Core, .NET 5, .NET 6 e versões posteriores.  
- **Qual formato de arquivo é produzido?** PNG – um formato de imagem sem perdas e amigável para a web.

## Como Gerar DataMatrix com Codificação C40

Carregue seus dados, configure o gerador e chame `Save` – esse é o fluxo de trabalho completo em três etapas concisas. A classe `BarcodeGenerator` lida com a criação do símbolo, enquanto o enum `BarCodeImageFormat.Png` indica ao Aspose.BarCode que escreva o resultado como um arquivo PNG. `Save` grava a imagem do código de barras gerado no caminho de arquivo especificado no formato escolhido. Este parágrafo de resposta direta fornece a solução de ponta a ponta antes de mergulharmos em cada linha de código.

## O que é o Modo de Codificação DataMatrix (C40)?

`DataMatrixEncodeMode` é uma enumeração que especifica qual esquema de codificação o Aspose.BarCode deve usar para símbolos DataMatrix. A opção `DataMatrixEncodeMode.C40` seleciona a codificação alfanumérica C40, que agrupa letras, dígitos e um conjunto limitado de pontuação em menos módulos, reduzindo o tamanho geral do símbolo enquanto mantém a legibilidade para textos típicos de inventário. Esse esquema eficiente é ideal quando você precisa codificar dados alfanuméricos de forma compacta.

## Por que Usar Aspose.BarCode para .NET?

Aspose.BarCode oferece **mais de 30 parâmetros configuráveis** para dimensões, níveis de correção de erro e modos de codificação, e suporta **mais de 50 formatos de imagem e código de barras**. A biblioteca funciona em **.NET Framework 4.5+, .NET Core 2.0+, .NET 5/6+**, proporcionando geração sem dependências que funciona em servidores, desktops e dispositivos móveis.

## Pré‑requisitos

Antes de mergulharmos no código, certifique-se de que você tem o seguinte:

1. **Ambiente de Desenvolvimento .NET** – Visual Studio, Rider ou qualquer IDE que suporte C#.  
2. **Aspose.BarCode para .NET** – instalado via NuGet ou o instalador oficial. Consulte a [documentation](https://reference.aspose.com/barcode/net/) para detalhes.  
3. **Conhecimento básico de C#** – você deve estar confortável com namespaces, classes e instruções using.  
4. **Pasta com permissão de gravação** – um diretório na sua máquina onde o PNG será salvo.

## Importando Namespaces Necessários

A classe `BarcodeGenerator` é o ponto de entrada para criar qualquer código de barras. Adicione o namespace necessário no topo do seu arquivo fonte C# para que você possa acessar a API de geração:

```csharp
using Aspose.BarCode.Generation;
```

## Geração de Código de Barras Passo a Passo

A seguir está um walkthrough **passo a passo do código de barras**. Cada etapa é explicada em linguagem simples, e os placeholders originais são mantidos inalterados para conveniência de copiar e colar.

### Etapa 1: Definir o Caminho do Diretório
Defina a pasta onde a imagem PNG será armazenada. Substitua o placeholder por um caminho real na sua máquina.

```csharp
string path = "Your Directory Path";
```

### Etapa 2: Configurar a Geração do Código de Barras
Crie uma instância de `BarcodeGenerator`, especifique `EncodeTypes.DataMatrix` e forneça os dados que deseja codificar.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE.BARCODE"))
{
    // Additional steps go here
}
```

### Etapa 3: Personalizar o Código de Barras
Configure a X‑dimension (largura em pixels dos módulos) e altere o modo de codificação para C40.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 6;
gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.C40;
```

### Etapa 4: Salvar a Imagem do Código de Barras
Finalmente, salve o código de barras gerado como um arquivo PNG. Esta é a resposta concreta para **how to save png** com Aspose.BarCode.

```csharp
gen.Save($"{path}DataMatrixEncodeModeC40.png", BarCodeImageFormat.Png);
```

Ao executar o programa, você encontrará `DataMatrixEncodeModeC40.png` na pasta que especificou, pronto para ser usado em relatórios, etiquetas ou páginas web.

## Problemas Comuns & Dicas

- **Caminho Inválido** – Certifique-se de que o diretório exista e que você tenha permissões de gravação; caso contrário, `gen.Save` lançará uma exceção.  
- **Modo de Codificação Incorreto** – Se precisar codificar caracteres fora do conjunto C40, altere para `DataMatrixEncodeMode.Auto` ou outro modo apropriado.  
- **Tamanho da Imagem** – Ajuste `XDimension.Pixels` para aumentar ou diminuir o tamanho geral do código de barras sem afetar a legibilidade.

## Perguntas Frequentes

**Q: O que é o Modo de Codificação DataMatrix (C40)?**  
A: C40 é um esquema de codificação alfanumérica compacta para símbolos DataMatrix, ideal para textos que incluem letras, números e um conjunto limitado de caracteres especiais.

**Q: Onde posso encontrar a documentação do Aspose.BarCode para .NET?**  
A: Você pode encontrar a documentação [here](https://reference.aspose.com/barcode/net/). Ela fornece orientações detalhadas sobre todos os tipos de código de barras e opções de codificação.

**Q: O Aspose.BarCode para .NET é compatível com todas as versões do .NET?**  
A: Sim, a biblioteca suporta uma ampla gama de versões do .NET, desde .NET Framework 4.5+ até .NET 6 e posteriores.

**Q: Posso experimentar o Aspose.BarCode para .NET antes de comprar?**  
A: Sim, você pode explorar um teste gratuito do Aspose.BarCode para .NET visitando [this link](https://releases.aspose.com/). Ele permite que você teste os recursos e capacidades da biblioteca.

**Q: Onde posso obter suporte para o Aspose.BarCode para .NET?**  
A: Você pode encontrar uma comunidade de apoio e acessar suporte para Aspose.BarCode para .NET no [Aspose forum](https://forum.aspose.com/c/barcode/13).

## Conclusão

Seguindo este guia **passo a passo do código de barras**, você agora sabe exatamente **como gerar datamatrix** códigos de barras e salvá-los como arquivos PNG usando o modo de codificação C40 com Aspose.BarCode para .NET. Esta abordagem lhe dá controle total sobre a aparência, tamanho e representação dos dados do código de barras, facilitando a incorporação de códigos de alta qualidade em qualquer aplicação .NET.

---

**Última atualização:** 2026-06-09  
**Testado com:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Codificação DataMatrix em Bytes com Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [Codificação Master DataMatrix em ASCII com Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Como Gerar Códigos de Barras DataMatrix (ECC 200) com Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}