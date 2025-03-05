---
title: Configuração de relação ampla-estreita unidimensional
linktitle: Configuração de relação ampla-estreita unidimensional
second_title: API Aspose.BarCode .NET
description: Gere códigos de barras personalizados facilmente com Aspose.BarCode for .NET. Guia passo a passo para configuração unidimensional de proporção larga-estreita.
type: docs
weight: 22
url: /pt/net/one-dimensional-barcode-types/one-dimensional-wide-narrow-ratio-configuration/
---

Você deseja gerar e personalizar códigos de barras sem esforço em seus aplicativos .NET? Não procure mais! Aspose.BarCode for .NET é uma biblioteca robusta que facilita a geração e personalização de códigos de barras. Neste guia passo a passo, nos aprofundaremos em como aproveitar o poder do Aspose.BarCode for .NET para criar códigos de barras com uma configuração de proporção larga-estreita.

## Pré-requisitos

Antes de mergulharmos no mundo dos códigos de barras com Aspose.BarCode for .NET, você precisa ter os seguintes pré-requisitos:

### 1. Ambiente do Visual Studio
   - Certifique-se de ter o Visual Studio instalado em seu sistema para trabalhar com aplicativos .NET.
   
### 2. Biblioteca Aspose.BarCode para .NET
   -  Você deve ter a biblioteca Aspose.BarCode for .NET instalada. Você pode baixá-lo no[local na rede Internet](https://releases.aspose.com/barcode/net/).

### 3. Chave de licença (opcional)
   -  Se você tiver uma chave de licença, ela poderá ser usada para desbloquear recursos adicionais da biblioteca. Você pode obter uma licença temporária em[aqui](https://purchase.aspose.com/temporary-license/).

Agora que você tem os pré-requisitos definidos, vamos começar a criar códigos de barras unidimensionais com configuração de proporção ampla-estreita usando Aspose.BarCode para .NET.

## Importar namespaces

Primeiro, você precisa incluir os namespaces necessários em seu projeto para acessar os recursos do Aspose.BarCode for .NET. Você pode fazer isso adicionando as seguintes instruções using na parte superior do seu código:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## Etapa 1: Defina o caminho do seu diretório

Comece definindo o caminho onde deseja salvar as imagens de código de barras geradas. Você pode fazer isso com o seguinte código:

```csharp
string path = "Your Directory Path";
```

 Substituir`"Your Directory Path"` com o caminho real do diretório onde você deseja salvar as imagens de código de barras.

## Etapa 2: Criar um código de barras unidimensional de proporção ampla e estreita

Agora, vamos criar um código de barras unidimensional com uma configuração de proporção ampla-estreita usando Aspose.BarCode for .NET. Neste exemplo, usaremos o tipo de codificação Code39Extended e definiremos os dados como “ASPOSE”.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code39Extended, "ASPOSE");
```

Esta linha de código inicializa um gerador de código de barras com o tipo de codificação e dados especificados.

## Etapa 3: definir a proporção ampla/estreita

A proporção largo-estreito determina a proporção entre elementos largos e estreitos no código de barras. Nesta etapa, definiremos a proporção amplo-estreito como 2:

```csharp
gen.Parameters.Barcode.WideNarrowRatio = 2;
```

E então, salvaremos a imagem do código de barras gerada no caminho especificado:

```csharp
gen.Save($"{path}WideNarrow2Code39.png", BarCodeImageFormat.Png);
```

## Etapa 4: ajustar a proporção amplo-estreito

Você pode experimentar diferentes proporções largo-estreito para obter a aparência desejada do código de barras. Por exemplo, se você quiser um código de barras mais largo, defina a proporção largo-estreito como 5:

```csharp
gen.Parameters.Barcode.WideNarrowRatio = 5;
```

E salve a imagem do código de barras:

```csharp
gen.Save($"{path}WideNarrow5Code39.png", BarCodeImageFormat.Png);
```

Agora você criou com sucesso códigos de barras unidimensionais com diferentes proporções largas e estreitas usando Aspose.BarCode for .NET. Esta biblioteca oferece flexibilidade para gerar códigos de barras adaptados às suas necessidades específicas.

## Conclusão

Aspose.BarCode for .NET é uma biblioteca versátil que simplifica a geração e personalização de códigos de barras em seus aplicativos .NET. Neste tutorial, cobrimos os fundamentos da criação de códigos de barras unidimensionais com configuração de proporção larga-estreita. Com a capacidade de ajustar vários parâmetros, você pode criar códigos de barras que atendem perfeitamente às suas necessidades.

## perguntas frequentes

### 1. Como posso obter uma licença do Aspose.BarCode for .NET?
 Você pode comprar uma licença no[Aspor site](https://purchase.aspose.com/buy).

### 2. Posso usar Aspose.BarCode for .NET sem licença?
Sim, você pode usá-lo com uma licença temporária, que oferece funcionalidade limitada.

### 3. O Aspose.BarCode for .NET é compatível com .NET Core?
Sim, Aspose.BarCode for .NET é compatível com .NET Core e .NET Framework.

### 4. Há alguma limitação quanto aos tipos de códigos de barras que posso gerar?
Aspose.BarCode for .NET oferece suporte a uma ampla variedade de simbologias de código de barras, incluindo QR Code, Code 39 e muito mais.

### 5. Como posso obter suporte ou tirar dúvidas sobre o Aspose.BarCode for .NET?
 Você pode visitar o[Fórum Aspose.BarCode](https://forum.aspose.com/c/barcode/13) para apoio e discussões.
