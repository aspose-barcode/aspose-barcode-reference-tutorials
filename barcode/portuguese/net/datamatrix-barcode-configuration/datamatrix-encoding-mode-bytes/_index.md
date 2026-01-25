---
date: 2026-01-25
description: Aprenda a criar arquivos PNG de código de barras com Aspose.BarCode para
  .NET codificando DataMatrix no modo Bytes. Siga este guia de geração de códigos
  de barras para uma implementação fácil.
linktitle: DataMatrix Encoding Mode (Bytes)
second_title: Aspose.BarCode .NET API
title: Criar PNG de código de barras usando Aspose.BarCode para .NET – Bytes DataMatrix
url: /pt/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar PNG de Código de Barras – Codificação DataMatrix em Bytes com Aspose.BarCode para .NET

## Respostas Rápidas
- **O que significa “criar PNG de código de barras”?** Refere‑se à geração de uma imagem raster PNG que contém um código de barras.
- **Qual biblioteca é a melhor para isso?** Aspose.BarCode para .NET fornece uma API completa para criação e reconhecimento de códigos de barras.
- **Preciso de uma licença?** Um teste gratuito funciona para desenvolvimento; uma licença comercial é necessária para produção.
- **Posso ler o código de barras novamente?** Sim, a mesma biblioteca inclui um BarCodeReader para **ler dados de código de barras DataMatrix**.
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Como criar PNG de código de barras com Aspose.BarCode para .NET
A seguir você encontrará tudo o que precisa — desde pré‑requisitos até um walkthrough de código passo a passo — que permitirá **gerar um código de barras PNG**, definir o texto de exibição e verificar o resultado com o leitor embutido.

## Pré‑requisitos

Antes de mergulharmos no processo de codificação, você precisará ter os seguintes pré‑requisitos em vigor:

1. Aspose.BarCode para .NET: Para começar, você deve ter a biblioteca Aspose.BarCode para .NET instalada. Você pode baixá‑la a partir de [here](https://releases.aspose.com/barcode/net/).

2. Seu Ambiente de Desenvolvimento: Certifique‑se de que você tem um ambiente de desenvolvimento configurado, incluindo Visual Studio ou qualquer outra IDE de sua escolha.

3. Conhecimento Básico de C#: Este tutorial assume que você tem uma compreensão básica da programação em C#.

Com esses pré‑requisitos em vigor, você está pronto para iniciar a codificação de dados no formato DataMatrix usando o modo Bytes.

## Importar Namespaces

Para usar Aspose.BarCode para .NET, você precisará importar os namespaces necessários ao seu código C#. Adicione as linhas a seguir ao topo do seu arquivo de código:

```csharp
using System;
using System.Text;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

Agora, vamos dividir o processo de codificação de dados no formato DataMatrix usando o modo Bytes em várias etapas.

## Etapa 1: Inicializar o BarcodeGenerator

Crie um objeto BarcodeGenerator, especificando o EncodeType como DataMatrix e os dados que você deseja codificar. Você pode substituir `"Your Directory Path"` pelo caminho real onde deseja salvar a imagem do código de barras.

```csharp
string path = "Your Directory Path";
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, strBld.ToString()))
{
    // Set the XDimension in Pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
```

## Etapa 2: Definir o modo de codificação DataMatrix para Bytes

Defina o modo de codificação DataMatrix para Bytes usando o código a seguir:

```csharp
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Bytes;
```

## Etapa 3: Definir o texto de exibição

Você pode definir o texto de exibição para o seu código de barras. Neste exemplo, definimos como "Bytes mode."

```csharp
    gen.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Bytes mode";
```

## Etapa 4: Salvar a imagem do código de barras

Salve a imagem do código de barras gerada no caminho especificado. Neste caso, ela é salva como "DataMatrixEncodeModeBytes.png."

```csharp
    gen.Save($"{path}DataMatrixEncodeModeBytes.png", BarCodeImageFormat.Png);
```

## Etapa 5: Tentar reconhecer

Agora, vamos tentar reconhecer o código de barras DataMatrix codificado. Usaremos o BarCodeReader para isso.

```csharp
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
```

## Etapa 6: Iterar e exibir resultados

Itere pelos resultados e exiba os dados codificados.

```csharp
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixEncodeModeBytes:" + BitConverter.ToString(result.CodeBytes));
    }
}
```

Com essas etapas, você criou com sucesso **um PNG de código de barras** no modo DataMatrix Bytes com Aspose.BarCode para .NET. Esta poderosa biblioteca simplifica a geração e o reconhecimento de códigos de barras, tornando‑se uma ferramenta essencial para desenvolvedores.

Agora, você está pronto para integrar a codificação e decodificação de códigos de barras em suas aplicações .NET com facilidade, graças ao Aspose.BarCode.

## Conclusão

Neste tutorial, exploramos como usar Aspose.BarCode para .NET para **criar arquivos PNG de código de barras** no formato DataMatrix usando o modo Bytes. Seguindo estas etapas simples, você pode aprimorar suas aplicações com recursos robustos de geração e reconhecimento de códigos de barras. Se encontrar algum problema, a comunidade Aspose.BarCode está pronta para ajudar.

Se você tiver dúvidas ou enfrentar algum problema, não hesite em buscar assistência na comunidade Aspose.BarCode em [Aspose.BarCode Support](https://forum.aspose.com/c/barcode/13).

## Perguntas Frequentes

### Q1: O que é o modo de codificação DataMatrix?

A1: O modo de codificação DataMatrix é um método usado para codificar dados em um formato de código de barras 2D. Ele oferece várias opções de codificação, incluindo o modo Bytes, que é adequado para codificar dados binários.

### Q2: Como posso obter um teste gratuito do Aspose.BarCode para .NET?

A2: Você pode obter um teste gratuito do Aspose.BarCode para .NET a partir de [here](https://releases.aspose.com/).

### Q3: Onde posso encontrar documentação para Aspose.BarCode para .NET?

A3: A documentação para Aspose.BarCode para .NET está disponível [here](https://reference.aspose.com/barcode/net/).

### Q4: O Aspose.BarCode para .NET é adequado para uso comercial?

A4: Sim, Aspose.BarCode para .NET é adequado para uso comercial. Você pode comprar uma licença a partir de [here](https://purchase.aspose.com/buy).

### Q5: Posso usar uma licença temporária para Aspose.BarCode para .NET?

A5: Sim, você pode obter uma licença temporária para Aspose.BarCode para .NET a partir de [here](https://purchase.aspose.com/temporary-license/).

## Perguntas Frequentes

**Q: Como faço para **ler oDecodeType.DataMatrix` conforme mostrado na Etapa 5 e.

**Q: Pos legível por humanos no código de barras?**  
A: Defina `gen.Parameters.Barcode.CodeTextParameters.ShowCodeText = false` para ocultar o texto de exibição.

**Q: O Aspose.BarCode suporta .NET Core?**  
A: Absolutamente — a biblioteca funciona com .NET Core, .NET 5, .NET 6 e versões posteriores.

---

**Última atualização:** 2026-01-25  
**Testado com:** Aspose.BarCode 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}