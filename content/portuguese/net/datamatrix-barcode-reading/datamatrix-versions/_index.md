---
title: Gere códigos de barras DataMatrix com Aspose.BarCode para .NET
linktitle: Versões DataMatrix
second_title: API Aspose.BarCode .NET
description: Aprenda como gerar códigos de barras DataMatrix em .NET usando Aspose.BarCode for .NET. Dimensões personalizadas, suporte ECC e muito mais.
type: docs
weight: 12
url: /pt/net/datamatrix-barcode-reading/datamatrix-versions/
---
Se você está procurando uma solução confiável para gerar códigos de barras DataMatrix em seus aplicativos .NET, o Aspose.BarCode for .NET é o caminho a percorrer. Neste guia passo a passo, orientaremos você no processo de uso do Aspose.BarCode for .NET para criar códigos de barras DataMatrix. Dividiremos cada exemplo em várias etapas, garantindo que você possa acompanhar com facilidade.

## Pré-requisitos

Antes de mergulharmos no código, certifique-se de ter os seguintes pré-requisitos em vigor:
- Um ambiente de desenvolvimento com suporte .NET.
-  Uma cópia do Aspose.BarCode for .NET, que você pode baixar em[esse link](https://releases.aspose.com/barcode/net/).
- Conhecimento básico de C# e do framework .NET.

Agora, vamos explorar as versões do DataMatrix e como gerá-las usando Aspose.BarCode for .NET.

## Importar namespaces

Em qualquer projeto C#, é essencial importar os namespaces necessários. No caso de Aspose.BarCode, você precisará incluir o seguinte:

```csharp
using Aspose.BarCode.Generation;
```

 Este namespace fornece acesso ao`BarcodeGenerator` classe, que é crucial para gerar códigos de barras.

Agora, vamos dividir o exemplo em várias etapas.

## Etapa 1: configure o caminho do seu diretório

Comece definindo o caminho do diretório onde deseja salvar os códigos de barras DataMatrix gerados.

```csharp
string path = "Your Directory Path";
```

 Substituir`"Your Directory Path"` com o caminho real onde você deseja salvar as imagens de código de barras.

## Etapa 2: inicializar o gerador de código de barras

 Crie uma instância do`BarcodeGenerator` class e especifique o tipo de código de barras como`DataMatrix`. Você também pode fornecer os dados que deseja codificar no código de barras.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // O código para geração de códigos de barras vai aqui
}
```

## Etapa 3: configurar propriedades do código de barras

Você pode personalizar diversas propriedades do código de barras DataMatrix, como suas dimensões e tipo ECC (Error Correction Code). Aqui está um exemplo de configuração da dimensão X para 4 pixels e escolha ECC200:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4;
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

## Etapa 4: definir a versão do DataMatrix e salvar

Você pode especificar a versão do DataMatrix definindo o número de linhas e colunas. Após configurar a versão, salve a imagem do código de barras.

Por exemplo, para criar um código de barras DataMatrix com 22 linhas e 22 colunas usando ECC200:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC200_22x22;
generator.Save($"{path}DataMatrixRows22Columns22Ecc200.png", BarCodeImageFormat.Png);
```

Da mesma forma, você pode gerar um código de barras com parâmetros diferentes alterando a versão e o tipo de ECC conforme necessário.

## Etapa 5: Repita para outras versões

Você pode repetir a Etapa 4 para outras versões do DataMatrix. Por exemplo, para criar um código de barras com 12 linhas e 64 colunas usando ECC200:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.DMRE_12x64;
generator.Save($"{path}DataMatrixRows12Columns64Ecc200.png", BarCodeImageFormat.Png);
```

## Etapa 6: mudar os tipos de ECC

Se quiser alterar o tipo ECC para Ecc140, você pode fazer isso atualizando a propriedade ECC:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;
```

## Etapa 7: gerar códigos de barras com diferentes versões e ECC

Repita a Etapa 4 para outras versões do DataMatrix e tipos de ECC, salvando cada código de barras com um nome de arquivo exclusivo.

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC000_140_29x29;
generator.Save($"{path}DataMatrixRows29Columns29Ecc140.png", BarCodeImageFormat.Png);
```

Agora que você aprendeu como gerar códigos de barras DataMatrix usando Aspose.BarCode for .NET, você pode integrar facilmente essa funcionalidade em seus aplicativos .NET.

## Conclusão

Aspose.BarCode for .NET simplifica o processo de geração de códigos de barras DataMatrix em seus aplicativos .NET. Com este guia passo a passo, você pode criar códigos de barras com diferentes versões e tipos de ECC, oferecendo flexibilidade e customização para atender às suas necessidades específicas.

 Se você tiver alguma dúvida ou precisar de ajuda, não hesite em visitar o[Documentação do Aspose.BarCode para .NET](https://reference.aspose.com/barcode/net/) ou confira o[Fórum Aspose.BarCode](https://forum.aspose.com/c/barcode/13) para suporte.

## Perguntas frequentes

### Q1: O que é ECC em códigos de barras DataMatrix?

A1: ECC (Código de Correção de Erros) é um componente vital dos códigos de barras DataMatrix que ajuda a garantir a integridade dos dados. Diferentes níveis de ECC fornecem vários graus de correção de erros.

### Q2: Posso gerar códigos de barras DataMatrix com dimensões personalizadas usando Aspose.BarCode for .NET?

A2: Sim, você pode personalizar as dimensões dos códigos de barras DataMatrix definindo o número de linhas e colunas conforme demonstrado no tutorial.

### Q3: Onde posso baixar o Aspose.BarCode para .NET?

 A3: Você pode baixar Aspose.BarCode para .NET em[esse link](https://releases.aspose.com/barcode/net/).

### Q4: Existe uma avaliação gratuita disponível para Aspose.BarCode for .NET?

 A4: Sim, você pode acessar uma avaliação gratuita do Aspose.BarCode for .NET[aqui](https://releases.aspose.com/).

### Q5: Como posso obter uma licença temporária para Aspose.BarCode for .NET?

 A5: Para obter uma licença temporária para Aspose.BarCode for .NET, visite[esse link](https://purchase.aspose.com/temporary-license/).