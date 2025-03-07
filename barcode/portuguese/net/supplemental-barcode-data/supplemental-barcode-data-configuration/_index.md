---
title: Criando dados de código de barras suplementares com Aspose.BarCode para .NET
linktitle: Configuração de dados de código de barras suplementar
second_title: API Aspose.BarCode .NET
description: Gere dados de código de barras suplementares com Aspose.BarCode for .NET. Personalize códigos de barras EAN-2 e EAN-5 sem esforço. Guia passo a passo para desenvolvedores .NET.
weight: 10
url: /pt/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criando dados de código de barras suplementares com Aspose.BarCode para .NET


No mundo da geração e customização de códigos de barras, Aspose.BarCode for .NET se destaca como uma ferramenta poderosa e versátil. Quer você seja um desenvolvedor experiente ou esteja apenas começando, este guia passo a passo irá orientá-lo no processo de configuração de dados de código de barras suplementares usando Aspose.BarCode for .NET. 

## Pré-requisitos

Antes de mergulharmos no mundo dos dados suplementares de código de barras, certifique-se de ter os seguintes pré-requisitos em vigor:

- Um ambiente de desenvolvimento configurado com Visual Studio ou qualquer outra ferramenta de desenvolvimento .NET.
-  Uma cópia do Aspose.BarCode para .NET. Se ainda não o fez, você pode baixá-lo[aqui](https://releases.aspose.com/barcode/net/).
- Conhecimento básico de programação C#.
- Um diretório onde você pode salvar as imagens de código de barras geradas.

## Importando Namespaces

Primeiro, certifique-se de ter os namespaces necessários incluídos em seu código C# para trabalhar com Aspose.BarCode for .NET. Importe os namespaces necessários no início do seu arquivo C#:

```csharp
using Aspose.BarCode.Generation;
```

Agora, vamos dividir o processo de configuração de dados de código de barras suplementares em várias etapas.

## Etapa 1: configurando o caminho do diretório

 Em seu código C#, defina o caminho para o diretório onde deseja salvar as imagens de código de barras geradas. Substituir`"Your Directory Path"` com o caminho real do diretório.

```csharp
string path = "Your Directory Path";
```

## Etapa 2: Criando um Gerador de Código de Barras

 Crie uma instância de`BarcodeGenerator` especificando o tipo de código de barras e os dados que deseja codificar. Neste exemplo, estamos usando um código de barras EAN-13 com os dados “1234567890128”.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

## Etapa 3: Personalização das dimensões do código de barras

Defina as dimensões do código de barras, como a dimensão X (a largura do menor elemento do código de barras) e o espaço suplementar. Neste exemplo, definimos a dimensão X para 2 pixels e o espaço suplementar para 20 pixels.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

## Passo 4: Configurando o Suplemento EAN-2

Para configurar um código de barras suplementar EAN-2, defina os dados suplementares para o valor desejado. Neste caso, definimos como "12". 

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

## Etapa 5: salvando a imagem do código de barras

Salve a imagem do código de barras gerada no diretório especificado com um nome significativo. Neste exemplo, salvamos o código de barras suplementar EAN-2 como "SupplementEAN2.png".

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

## Etapa 6: Configurando o Suplemento EAN-5

 Para configurar um código de barras suplementar EAN-5, basta alterar o`SupplementData` ao valor desejado. Aqui, definimos como “12345”.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

## Etapa 7: Salvando a imagem do código de barras (EAN-5)

Por fim, salve a imagem do código de barras suplementar EAN-5 no diretório especificado. Neste caso, salvamos como "SupplementEAN5.png".

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

Agora, você configurou e gerou com êxito dados de código de barras suplementares usando Aspose.BarCode for .NET. Você pode usar essa abordagem para criar uma ampla variedade de tipos de códigos de barras com dados complementares variados.

## Conclusão

Aspose.BarCode for .NET é uma ferramenta poderosa para geração e personalização de código de barras. Neste guia, percorremos passo a passo o processo de configuração e geração de dados complementares de código de barras. Com os pré-requisitos certos e um pouco de codificação, você pode trabalhar de forma eficiente com dados de código de barras e atender às suas necessidades específicas.

 Para obter mais informações e uso avançado, consulte o[Documentação do Aspose.BarCode para .NET](https://reference.aspose.com/barcode/net/).

## perguntas frequentes

### Posso usar Aspose.BarCode for .NET em meu projeto .NET Core?
Sim, Aspose.BarCode for .NET é compatível com .NET Core.

### Existe uma avaliação gratuita disponível para Aspose.BarCode for .NET?
 Sim, você pode experimentá-lo gratuitamente visitando[esse link](https://releases.aspose.com/).

### Onde posso obter uma licença temporária do Aspose.BarCode for .NET?
 Você pode obter uma licença temporária em[esse link](https://purchase.aspose.com/temporary-license/).

### O Aspose.BarCode oferece suporte a uma ampla variedade de tipos de códigos de barras?
Sim, suporta vários tipos de códigos de barras, incluindo EAN-13, QR Code, Code 128 e muito mais.

### Posso personalizar a aparência dos códigos de barras gerados?
Com certeza, você pode personalizar dimensões, cores e outros aspectos dos códigos de barras para atender às suas necessidades.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
