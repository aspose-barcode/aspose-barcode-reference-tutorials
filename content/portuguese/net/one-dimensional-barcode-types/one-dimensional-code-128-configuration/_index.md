---
title: Configuração do Código Unidimensional 128
linktitle: Configuração do Código Unidimensional 128
second_title: API Aspose.BarCode .NET
description: Aprenda como gerar códigos de barras Code 128 unidimensionais em .NET usando Aspose.BarCode. Siga nosso guia passo a passo para integração perfeita de código de barras.
type: docs
weight: 10
url: /pt/net/one-dimensional-barcode-types/one-dimensional-code-128-configuration/
---

Se você é um desenvolvedor .NET em busca de uma ferramenta poderosa para gerar códigos de barras em seus aplicativos, o Aspose.BarCode for .NET é a solução ideal. Este guia abrangente orientará você no processo de aproveitar os recursos do Aspose.BarCode for .NET para criar códigos de barras Code 128 unidimensionais e foi projetado para iniciantes e desenvolvedores experientes. 

## Pré-requisitos

Antes de mergulharmos no emocionante mundo da geração de código de barras com Aspose.BarCode, certifique-se de ter os seguintes pré-requisitos em vigor:

1. Visual Studio: certifique-se de ter o Visual Studio instalado em seu sistema.

2.  Aspose.BarCode para .NET: Você precisará baixar e instalar o Aspose.BarCode para .NET. Você pode obtê-lo de[aqui](https://releases.aspose.com/barcode/net/).

3. Seu projeto .NET: você deve ter um projeto .NET configurado e pronto para integrar a geração de código de barras.

Agora vamos começar!

## Importar namespaces

primeiro passo é importar os namespaces necessários para o seu projeto. Esses namespaces fornecerão acesso aos recursos e funções do Aspose.BarCode.

### Etapa 1: importar os namespaces

```csharp
using Aspose.BarCode.Generation;
```

## Configuração do Código Unidimensional 128

Agora, vamos criar códigos de barras Code 128 usando Aspose.BarCode for .NET. Analisaremos cada etapa detalhadamente, garantindo que você tenha uma compreensão clara do processo.

### Etapa 2: definir o caminho

Primeiro, defina o caminho para o diretório onde deseja salvar as imagens de código de barras geradas.

```csharp
string path = "Your Directory Path";
```

### Etapa 3: Crie um gerador de código de barras Code 128

 Criar uma`BarcodeGenerator` instância para gerar códigos de barras Code 128. Você pode especificar o tipo de código de barras que deseja gerar (neste caso, Code128) e o valor que deseja codificar.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code128, "CODE");
```

### Etapa 4: configurar os parâmetros do código de barras

Antes de gerar o código de barras, você pode configurar vários parâmetros. Por exemplo, você pode optar por mostrar ou ocultar a soma de verificação.

#### Opção 1: não mostrar soma de verificação

```csharp
gen.Parameters.Barcode.ChecksumAlwaysShow = false;
```

#### Opção 2: Mostrar soma de verificação

```csharp
gen.Parameters.Barcode.ChecksumAlwaysShow = true;
```

### Etapa 5: salve a imagem do código de barras

Agora é hora de salvar a imagem do código de barras gerada no diretório especificado. Você pode salvar o código de barras com ou sem checksum, dependendo da configuração escolhida na etapa anterior.

#### Salvar código de barras sem soma de verificação

```csharp
gen.Save($"{path}OneCSCode128NotShowChecksum.png", BarCodeImageFormat.Png);
```

#### Salvar código de barras com soma de verificação

```csharp
gen.Save($"{path}OneCSCode128ShowChecksum.png", BarCodeImageFormat.Png);
```

É isso! Você gerou com sucesso códigos de barras Code 128 unidimensionais usando Aspose.BarCode for .NET. Você pode usar esses códigos de barras em diversas aplicações, como gerenciamento de estoque, etiquetagem de produtos e muito mais.

## Conclusão

Aspose.BarCode for .NET fornece uma solução poderosa e fácil de usar para geração de código de barras em aplicativos .NET. Com sua API intuitiva e extensa documentação, você pode integrar facilmente a funcionalidade de código de barras em seus projetos. Se você precisa criar códigos de barras unidimensionais ou bidimensionais, Aspose.BarCode tem o que você precisa.

Incorpore Aspose.BarCode em seus aplicativos .NET hoje mesmo e simplifique seus processos de geração de código de barras com facilidade.

### Perguntas frequentes

### Aspose.BarCode para .NET é compatível com .NET Core?
Sim, Aspose.BarCode for .NET é compatível com .NET Framework e .NET Core.

### Posso personalizar a aparência dos códigos de barras gerados?
Absolutamente! Aspose.BarCode permite personalizar vários aspectos do código de barras, incluindo tamanho, cor e posicionamento do texto.

### O Aspose.BarCode é adequado para gerar códigos QR?
Embora o Aspose.BarCode se concentre principalmente em códigos de barras unidimensionais, você também pode usar o Aspose.BarCode for .NET para gerar códigos QR.

### Existe um teste gratuito disponível?
 Sim, você pode experimentar o Aspose.BarCode for .NET gratuitamente baixando a versão de teste[aqui](https://releases.aspose.com/).

### Onde posso obter suporte para Aspose.BarCode for .NET?
 Você pode procurar ajuda e compartilhar suas experiências no fórum Aspose.BarCode for .NET[aqui](https://forum.aspose.com/c/barcode/13).
