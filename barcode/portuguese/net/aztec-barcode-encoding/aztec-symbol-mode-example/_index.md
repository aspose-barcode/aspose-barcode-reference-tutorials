---
date: 2026-05-24
description: Aprenda como criar código de barras aztec .net usando Aspose.BarCode
  para .NET, cobrindo os modos de símbolo Auto, FullRange, Compact e Rune com orientação
  passo a passo.
keywords:
- create aztec barcode .net
- aztec symbol mode
- aspose barcode .net
linktitle: Exemplo de Modo de Símbolo Aztec
schemas:
- author: Aspose
  dateModified: '2026-05-24'
  description: Learn how to create aztec barcode .net using Aspose.BarCode for .NET,
    covering Auto, FullRange, Compact, and Rune symbol modes with step‑by‑step guidance.
  headline: Create Aztec Barcode .NET with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Aztec Symbol Mode determines how the library packs data into layers, affecting
      size, capacity, and readability.
    question: What is the purpose of Aztec Symbol Mode in barcode generation?
  - answer: Yes, simply assign a new string to the `CodeText` property before calling
      `Save`.
    question: Can I change the code text for Aztec barcodes in Aspose.BarCode for
      .NET?
  - answer: Yes, you can download a free trial version of Aspose.BarCode for .NET
      [here](https://releases.aspose.com/).
    question: Is there a free trial version of Aspose.BarCode for .NET available?
  - answer: You can refer to the complete documentation for Aspose.BarCode for .NET
      [here](https://reference.aspose.com/barcode/net/).
    question: Where can I find the full documentation for Aspose.BarCode for .NET?
  - answer: You can acquire a temporary license for Aspose.BarCode for .NET by visiting
      [this link](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Criar código de barras Aztec .NET com Aspose.BarCode
url: /pt/net/aztec-barcode-encoding/aztec-symbol-mode-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dominar o Modo de Símbolo Aztec com Aspose.BarCode para .NET

Se você está procurando **criar código de barras aztec .net** de forma rápida e confiável, o Aspose.BarCode para .NET oferece uma API completa que funciona no .NET Framework, .NET Core e .NET 5/6+. Neste tutorial vamos explorar os quatro Modos de Símbolo Aztec — Auto, FullRange, Compact e Rune — mostrando exatamente como alternar entre eles e salvar o resultado como imagem. Ao final, você poderá incorporar códigos de barras Aztec em qualquer aplicação .NET com apenas algumas linhas de código.

## Respostas Rápidas
- **Qual biblioteca gera códigos de barras Aztec em .NET?** Aspose.BarCode for .NET.  
- **Quantos modos de símbolo o Aztec suporta?** Quatro: Auto, FullRange, Compact e Rune.  
- **Preciso de licença para desenvolvimento?** Uma versão de avaliação funciona para avaliação; uma licença comercial é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ e .NET 6+.  
- **Posso gerar PNG, JPEG ou SVG?** Sim—qualquer formato de imagem padrão é suportado.

## O que é criar código de barras aztec .net?
`create aztec barcode .net` refere‑se ao processo de gerar um código de barras bidimensional Aztec usando a API Aspose.BarCode em um ambiente .NET. A API lida com a codificação, seleção do modo de símbolo e renderização da imagem automaticamente, permitindo que desenvolvedores produzam códigos de alta qualidade sem precisar lidar com detalhes de baixo nível, como cálculos de correção de erros ou manipulação de pixels.

## Por que usar Aspose.BarCode para códigos de barras Aztec?
Aspose.BarCode suporta **30+ simbologias de código de barras** e pode renderizar imagens de até **10.000 × 10.000 px** sem carregar todo o arquivo na memória. Ele processa um documento de 500 páginas em menos de **2 segundos** em um servidor típico, tornando‑o ideal para cenários empresariais de alto volume.

## Pré-requisitos

Antes de começarmos, certifique‑se de que você tem os seguintes pré‑requisitos:

- Um conhecimento prático de desenvolvimento .NET.  
- Visual Studio instalado na sua máquina.  
- Uma cópia do Aspose.BarCode para .NET. Você pode baixá‑lo [aqui](https://releases.aspose.com/barcode/net/). Você também pode explorar outros produtos Aspose [aqui](https://releases.aspose.com/).

Agora que tudo está pronto, vamos mergulhar nos exemplos de Modo de Símbolo Aztec.

## Importando Namespaces

Primeiro, você precisará importar os namespaces necessários para trabalhar com Aspose.BarCode para .NET. Abra seu projeto no Visual Studio e adicione as seguintes instruções `using` no topo do seu arquivo de código:

```csharp
using Aspose.BarCode.Generation;
```

Com os namespaces em vigor, você já pode começar a usar o Aspose.BarCode para .NET.

## Como configurar o Barcode Generator para códigos de barras Aztec?

A classe `BarcodeGenerator` é o componente central que cria imagens de código de barras com base na simbologia selecionada e nas opções de configuração. Ela fornece uma API simples para especificar o tipo de código de barras, os dados a codificar e vários parâmetros de renderização antes de salvar o resultado em um arquivo de imagem.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecSymbolModeExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

Nesta etapa, configuramos o gerador e fornecemos o texto do código para codificação.

## Como definir o Modo de Símbolo Aztec para Auto?

A enumeração `AztecSymbolMode` define os quatro modos de símbolo possíveis para códigos de barras Aztec, e a opção **Auto** permite que a biblioteca escolha automaticamente o tamanho mais compacto, preservando todos os requisitos de dados e correção de erros. Esse modo é ideal para a maioria dos cenários em que você deseja o menor código de barras possível sem ajustes manuais.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Auto;
gen.Save($"{path}AztecSymbolModeAuto.png", BarCodeImageFormat.Png);
```

Esta etapa garante que o Modo de Símbolo Aztec seja determinado automaticamente, e a imagem resultante do código de barras é salva.

## Como forçar o Modo de Símbolo FullRange?

Quando você precisa da capacidade máxima de dados, pode selecionar o valor **FullRange** da enumeração `AztecSymbolMode`. Esse modo desativa a redução automática de tamanho, permitindo que o código de barras armazene toda a gama de caracteres e alcance a maior densidade de informação possível, o que é útil para conjuntos de dados extensos.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
gen.Save($"{path}AztecSymbolModeFullRange.png", BarCodeImageFormat.Png);
```

Isso criará um código de barras com o Modo de Símbolo Aztec FullRange.

## Como gerar um código de barras Aztec Compacto?

O valor **Compact** da enumeração `AztecSymbolMode` produz um código de barras menor ao reduzir o número de camadas usadas na matriz. Isso resulta em uma imagem mais eficiente em termos de espaço, sendo adequado para aplicações com área de exibição limitada, como telas móveis ou etiquetas pequenas.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Compact;
gen.Save($"{path}AztecSymbolModeCompact.png", BarCodeImageFormat.Png);
```

Esta etapa configura o código de barras para ser gerado com o Modo de Símbolo Aztec Compacto.

## Como criar um código de barras Aztec Rune?

O modo **Rune** é uma variante especializada da simbologia Aztec que codifica dados numéricos usando um conjunto de caracteres personalizado, oferecendo um estilo visual distinto enquanto mantém a mesma força de correção de erros dos outros modos. É útil quando você precisa de um código de barras que enfatize informações numéricas.

```csharp
gen.CodeText = "123"; // Change the code text if needed
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Rune;
gen.Save($"{path}AztecSymbolModeRune.png", BarCodeImageFormat.Png);
```

Esta etapa altera o texto do código para "123" e gera um código de barras com o Modo de Símbolo Aztec Rune.

## Problemas Comuns e Soluções

- **Imagem não salva** – Certifique‑se de que a pasta de saída existe e que a aplicação tem permissões de gravação.  
- **Tamanho de símbolo inesperado** – Verifique se você não sobrescreveu `EncodeMode` em outro lugar no seu código.  
- **Exceção de licença** – Uma versão de avaliação adiciona uma marca d'água; aplique uma licença válida para removê‑la.

## Perguntas Frequentes

**P: Qual é o objetivo do Modo de Símbolo Aztec na geração de códigos de barras?**  
R: O Modo de Símbolo Aztec determina como a biblioteca empacota os dados em camadas, afetando tamanho, capacidade e legibilidade.

**P: Posso alterar o texto do código para códigos de barras Aztec no Aspose.BarCode para .NET?**  
R: Sim, basta atribuir uma nova string à propriedade `CodeText` antes de chamar `Save`.

**P: Existe uma versão de avaliação gratuita do Aspose.BarCode para .NET disponível?**  
R: Sim, você pode baixar uma versão de avaliação gratuita do Aspose.BarCode para .NET [aqui](https://releases.aspose.com/).

**P: Onde posso encontrar a documentação completa do Aspose.BarCode para .NET?**  
R: Você pode consultar a documentação completa do Aspose.BarCode para .NET [aqui](https://reference.aspose.com/barcode/net/).

**P: Como posso obter uma licença temporária para Aspose.BarCode para .NET?**  
R: Você pode adquirir uma licença temporária para Aspose.BarCode para .NET visitando [este link](https://purchase.aspose.com/temporary-license/).

## Conclusão

Neste tutorial exploramos como **criar código de barras aztec .net** usando o Aspose.BarCode, cobrindo os modos de símbolo Auto, FullRange, Compact e Rune. Agora você tem uma base sólida para incorporar códigos de barras Aztec versáteis em qualquer aplicação .NET, seja ela desktop, servidor web ou serviço em nuvem.

Se você tiver dúvidas ou precisar de mais assistência, não hesite em contatar a comunidade Aspose.BarCode no seu [forum de suporte](https://forum.aspose.com/c/barcode/13).

---

**Last Updated:** 2026-05-24  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Codificação de Texto do Código Aztec com Aspose.BarCode para .NET](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)
- [Codificação de Bytes Aztec usando barcode generator .net](/barcode/net/aztec-barcode-encoding/aztec-bytes-encoding/)
- [Como criar código de barras Aztec com correção de erro em .NET](/barcode/net/aztec-barcode-encoding/aztec-error-level-example/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}