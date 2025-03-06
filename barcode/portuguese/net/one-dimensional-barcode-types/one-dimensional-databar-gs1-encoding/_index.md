---
title: Codificação GS1 da barra de dados unidimensional
linktitle: Codificação GS1 da barra de dados unidimensional
second_title: API Aspose.BarCode .NET
description: Aprenda a criar códigos de barras codificados Databar GS1 em .NET usando Aspose.BarCode. Gere códigos de barras com facilidade. Siga nosso guia passo a passo.
weight: 18
url: /pt/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Codificação GS1 da barra de dados unidimensional


Neste tutorial, orientaremos você no processo de criação de códigos de barras codificados unidimensionais Databar GS1 usando a biblioteca Aspose.BarCode for .NET. Esteja você procurando gerar códigos de barras com ou sem codificação GS1, nós temos o que você precisa. Este guia passo a passo ajudará você a entender os pré-requisitos, importar namespaces e demonstrar cada exemplo para criar códigos de barras codificados GS1 do Databar com facilidade.

## Pré-requisitos

Antes de mergulharmos no código, certifique-se de ter os seguintes pré-requisitos em vigor:

1.  Aspose.BarCode para .NET: Você deve ter o Aspose.BarCode para .NET instalado. Se ainda não o fez, você pode baixá-lo em[aqui](https://releases.aspose.com/barcode/net/).

2.  Seu caminho de diretório: substituir`"Your Directory Path"` nos exemplos de código com o caminho real onde você deseja salvar as imagens de código de barras geradas.

Agora que você tem os pré-requisitos necessários prontos, vamos prosseguir para a parte de codificação.

## Importando Namespaces

Para começar, você precisa importar os namespaces relevantes para Aspose.BarCode. Adicione as seguintes linhas de código no início do seu projeto .NET:

```csharp
using Aspose.BarCode;
using System;
```

## Etapa 1: inicializar o gerador de código de barras

A primeira etapa é inicializar o objeto BarcodeGenerator com o tipo de codificação desejado. Neste caso, estamos usando a codificação Databar Expanded. 

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## Etapa 2: gerar um código de barras com codificação GS1

Agora, definiremos o codetexto com verificação GS1Encoding e salvaremos a imagem do código de barras gerada. 

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## Etapa 3: gerar um código de barras de codificação variável

Nesta etapa, iremos gerar um código de barras com codetexto variável sem verificação GS1Encoding.

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## Etapa 4: Lidar com exceção para verificação de codificação GS1

Se você tentar gerar um código de barras com codetext variável com a verificação GS1Encoding habilitada, uma exceção será lançada. Veja como você pode lidar com isso:

```csharp
try
{
    gen.CodeText = "ASPOSE";
    gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

Agora você criou com sucesso códigos de barras codificados Databar GS1 unidimensionais com Aspose.BarCode para .NET. Você pode explorar e personalizar ainda mais a geração de seu código de barras com base em seus requisitos específicos.

## Conclusão

Neste tutorial, cobrimos o processo de geração de códigos de barras codificados unidimensionais do Databar GS1 usando Aspose.BarCode para .NET. Discutimos os pré-requisitos, importamos os namespaces necessários e fornecemos orientação passo a passo para a criação de códigos de barras codificados GS1 e de codificação variável.

 Com Aspose.BarCode for .NET, a geração de código de barras se torna uma tarefa perfeita, oferecendo flexibilidade e controle sobre suas necessidades de criação de código de barras. Se você encontrar algum problema ou tiver dúvidas, não hesite em visitar o[Documentação Aspose.BarCode](https://reference.aspose.com/barcode/net/) ou procure ajuda no[Fórum de suporte Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

## perguntas frequentes

### 1. O que é a codificação GS1 em códigos de barras?
A codificação GS1 é um padrão usado em código de barras para garantir estrutura e identificação de dados adequadas. É comumente usado para itens de varejo, saúde e logística para facilitar o rastreamento preciso e a troca de informações.

### 2. Posso personalizar a aparência dos códigos de barras gerados?
Sim, você pode personalizar a aparência dos códigos de barras gerados com Aspose.BarCode for .NET. Você tem controle sobre vários parâmetros como tamanho, cor e estilo.

### 3. Onde posso encontrar recursos e documentação adicionais para Aspose.BarCode?
 Você pode encontrar documentação e exemplos abrangentes em[Documentação Aspose.BarCode](https://reference.aspose.com/barcode/net/). É um recurso valioso para aprendizado e solução de problemas.

### 4. Existe uma versão de teste disponível para Aspose.BarCode?
 Sim, você pode obter uma versão de avaliação gratuita do Aspose.BarCode for .NET em[aqui](https://releases.aspose.com/).

### 5. Como posso adquirir uma licença do Aspose.BarCode for .NET?
 Para adquirir uma licença do Aspose.BarCode for .NET, visite o[página de compra](https://purchase.aspose.com/buy) no site da Aspose.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
