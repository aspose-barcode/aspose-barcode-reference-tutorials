---
title: Configurando o texto do código DataMatrix com Aspose.BarCode para .NET
linktitle: Configuração de texto de código estendido DataMatrix
second_title: API Aspose.BarCode .NET
description: Aprenda a configurar o texto do código estendido DataMatrix usando Aspose.BarCode para .NET. Gere, reconheça e integre códigos de barras em seus aplicativos .NET.
type: docs
weight: 17
url: /pt/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/
---
No mundo do desenvolvimento de software, a integração de códigos de barras tornou-se uma necessidade fundamental para diversas aplicações. Com a ajuda de bibliotecas como Aspose.BarCode for .NET, você pode gerar e reconhecer facilmente códigos de barras em seus aplicativos .NET. Este tutorial orientará você no processo de configuração do texto de código estendido DataMatrix usando Aspose.BarCode for .NET. Antes de nos aprofundarmos nos detalhes, vamos dar uma olhada nos pré-requisitos deste guia.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte em vigor:

1. Biblioteca Aspose.BarCode para .NET
Você precisará ter o Aspose.BarCode for .NET instalado. Se ainda não o fez, você pode baixá-lo no site[aqui](https://releases.aspose.com/barcode/net/).

2. Um ambiente de desenvolvimento .NET
Para acompanhar este tutorial, você deve ter um ambiente de desenvolvimento .NET configurado em seu sistema. Você pode usar o Visual Studio ou qualquer outro IDE preferido.

3. Conhecimento básico de C#
Uma compreensão básica da programação C# é essencial para este tutorial.

Agora que você tem as ferramentas e o conhecimento necessários, vamos dividir o processo de configuração do texto de código estendido do DataMatrix usando Aspose.BarCode for .NET em instruções simples e passo a passo.

## Importar namespaces

A primeira etapa para trabalhar com Aspose.BarCode for .NET é importar os namespaces necessários. Adicione os seguintes namespaces ao seu código:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

Esses namespaces fornecem as classes e métodos necessários para trabalhar com códigos de barras.

## Etapa 1: Configuração de texto de código estendido DataMatrix

Nesta etapa, orientaremos você no processo de configuração do texto de código estendido do DataMatrix.

## Etapa 2: definir o caminho do diretório

 Você precisa especificar o caminho do diretório onde deseja salvar o código de barras DataMatrix gerado. Substituir`"Your Directory Path"` com o caminho real em seu sistema.

```csharp
string path = "Your Directory Path";
```

## Etapa 3: crie o codetexto

 Para criar o codetexto para o código de barras DataMatrix, você usará o`DataMatrixExtCodetextBuilder`. Este construtor permite adicionar vários tipos de codetexto com codificações diferentes.

```csharp
DataMatrixExtCodetextBuilder codetextBuilder = new DataMatrixExtCodetextBuilder();
codetextBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
codetextBuilder.AddECICodetextWithEncodeMode(ECIEncodings.UTF8, DataMatrixEncodeMode.C40, "ABCDE");
codetextBuilder.AddPlainCodetext("test");
codetextBuilder.AddCodetextWithEncodeMode(DataMatrixEncodeMode.Text, "abcde");
```

Este código configura o codetexto com uma mistura de diferentes codificações.

## Etapa 4: gerar codetexto

Após configurar o codetexto, gere a string de codetexto DataMatrix.

```csharp
string codetext = codetextBuilder.GetExtendedCodetext();
```

## Etapa 5: gerar código de barras DataMatrix

Agora, crie o código de barras DataMatrix usando o codetexto gerado. Você também pode definir vários parâmetros para o código de barras, como dimensão X e exibição de texto do código.

```csharp
using (var generator = new BarcodeGenerator(EncodeTypes.DataMatrix, codetext))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended Codetext";
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ExtendedCodetext;

    generator.Save($"{path}DataMatrixExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Este código gera e salva a imagem do código de barras DataMatrix com as configurações especificadas.

## Etapa 6: tente reconhecer

 Para garantir que o código de barras possa ser reconhecido, você pode usar o`BarCodeReader`classe para ler o código de barras.

```csharp
using (var reader = new BarCodeReader(generator.GenerateBarCodeImage(), DecodeType.DataMatrix))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
        Console.WriteLine("DataMatrixExtendedCodetext:" + result.CodeText);
}
```

Esta etapa valida o código de barras gerado tentando reconhecê-lo.

Parabéns! Você configurou com êxito o texto do código estendido do DataMatrix usando Aspose.BarCode para .NET. Agora você pode integrar essa funcionalidade aos seus aplicativos .NET.

## Conclusão

Neste tutorial, exploramos o processo de configuração de texto de código estendido DataMatrix usando Aspose.BarCode para .NET. Abordamos os pré-requisitos, instruções passo a passo e demonstramos como gerar e reconhecer o código de barras. Com esse conhecimento, você pode aprimorar seus aplicativos .NET adicionando recursos de geração e reconhecimento de código de barras.

## Perguntas frequentes

### Q1: O que é Aspose.BarCode para .NET?

A1: Aspose.BarCode for .NET é uma biblioteca poderosa que permite aos desenvolvedores gerar e reconhecer códigos de barras em aplicativos .NET. Suporta uma ampla gama de simbologias de códigos de barras e oferece diversas opções de personalização.

### Q2: Onde posso encontrar a documentação do Aspose.BarCode for .NET?

A2: Você pode acessar a documentação do Aspose.BarCode for .NET[aqui](https://reference.aspose.com/barcode/net/).

### Q3: Existe uma avaliação gratuita disponível para Aspose.BarCode for .NET?

 A3: Sim, você pode obter uma versão de avaliação gratuita do Aspose.BarCode for .NET[aqui](https://releases.aspose.com/).

### Q4: Como posso obter uma licença temporária para Aspose.BarCode for .NET?

 R4: Se precisar de uma licença temporária para fins de teste ou avaliação, você poderá obter uma[aqui](https://purchase.aspose.com/temporary-license/).

### Q5: Onde posso obter suporte ou fazer perguntas sobre o Aspose.BarCode for .NET?

 A5: Para qualquer suporte ou dúvidas relacionadas ao Aspose.BarCode for .NET, você pode visitar o fórum Aspose.BarCode[aqui](https://forum.aspose.com/c/barcode/13).