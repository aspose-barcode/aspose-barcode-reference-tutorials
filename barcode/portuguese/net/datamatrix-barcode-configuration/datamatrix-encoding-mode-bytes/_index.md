---
date: 2026-05-30
description: Aprenda como gerar código de barras DataMatrix no modo Bytes e ler código
  de barras DataMatrix usando Aspose.BarCode para .NET – um guia passo a passo de
  códigos de barras.
keywords:
- generate datamatrix barcode
- read datamatrix barcode
- barcode generator settings
- step by step barcode
- create barcode asp.net
linktitle: Modo de Codificação DataMatrix (Bytes)
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to generate DataMatrix barcode in Bytes mode and read DataMatrix
    barcode using Aspose.BarCode for .NET – a step‑by‑step barcode guide.
  headline: Generate DataMatrix Barcode in Bytes Mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to generate DataMatrix barcode in Bytes mode and read DataMatrix
    barcode using Aspose.BarCode for .NET – a step‑by‑step barcode guide.
  name: Generate DataMatrix Barcode in Bytes Mode with Aspose.BarCode for .NET
  steps:
  - name: Initialize the BarcodeGenerator
    text: '`BarcodeGenerator` is the main class used to generate barcode images for
      a given symbology and data.'
  - name: Set DataMatrix Encode Mode to Bytes
    text: '`DataMatrixEncodeMode.Bytes` tells the generator to treat the input as
      raw binary bytes rather than text.'
  - name: Set Display Text
    text: '`CodeText` property sets the human‑readable text displayed below the barcode
      symbol.'
  - name: Save the Barcode Image
    text: '`Save` method writes the generated barcode to an image file in the specified
      format.'
  - name: Try to Recognize
    text: '`BarCodeReader` reads barcode images and extracts the encoded data.'
  - name: Iterate and Display Results
    text: Iterate over `reader.ReadBarCodes()` to access each detected barcode and
      its `CodeText`. With these steps, you have successfully **generated a DataMatrix
      barcode** in Bytes mode and verified it using Aspose.BarCode for .NET. The library
      abstracts the low‑level encoding details, so you can focus on b
  type: HowTo
- questions:
  - answer: DataMatrix encoding mode defines how input data is transformed into the
      two‑dimensional pattern; Bytes mode stores raw binary bytes directly.
    question: What is DataMatrix encoding mode?
  - answer: You can obtain a free trial of Aspose.BarCode for .NET from [here](https://releases.aspose.com/).
    question: How can I get a free trial of Aspose.BarCode for .NET?
  - answer: The documentation for Aspose.BarCode for .NET is available [here](https://reference.aspose.com/barcode/net/).
    question: Where can I find documentation for Aspose.BarCode for .NET?
  - answer: Yes, Aspose.BarCode for .NET is suitable for commercial use. You can purchase
      a license from [here](https://purchase.aspose.com/buy).
    question: Is Aspose.BarCode for .NET suitable for commercial use?
  - answer: Yes, you can obtain a temporary license for Aspose.BarCode for .NET from
      [here](https://purchase.aspose.com/temporary-license/).
    question: Can I use a temporary license for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Gerar código de barras DataMatrix no modo Bytes com Aspose.BarCode para .NET
url: /pt/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerar Código de Barras DataMatrix no Modo Bytes com Aspose.BarCode para .NET

Neste tutorial você aprenderá como **gerar código de barras DataMatrix** usando o modo de codificação Bytes e então **ler o código de barras DataMatrix** novamente com Aspose.BarCode para .NET. Seja construindo um sistema de gerenciamento de armazém ou um aplicativo móvel de bilhetagem, o guia passo a passo de código de barras abaixo mostra exatamente como configurar as definições do gerador de código de barras, produzir uma imagem de alta qualidade e decodificá‑la novamente — tudo em apenas algumas linhas de C#.

## Respostas Rápidas
- **Posso gerar um código de barras DataMatrix em .NET?** Sim, use `BarcodeGenerator` com `EncodeTypes.DataMatrix` e defina `DataMatrixEncodeMode.Bytes`.
- **Qual método lê o código de barras?** `BarCodeReader` lê a imagem e retorna o texto codificado.
- **Preciso de uma licença para produção?** É necessária uma licença comercial; uma versão de avaliação gratuita está disponível.
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Quantos bytes posso codificar?** Até 1.555 bytes em um único símbolo DataMatrix.

## O que é gerar código de barras DataMatrix?
**Gerar código de barras DataMatrix** significa criar um código de barras bidimensional, em forma quadrada, que pode armazenar dados binários. Aspose.BarCode renderiza o símbolo como uma imagem PNG, JPG ou SVG que qualquer scanner pode decodificar. É amplamente usado para rastreamento de inventário, gerenciamento de documentos e autenticação porque fornece alta densidade de dados e recursos de correção de erros, tornando‑o confiável mesmo em impressões de baixa qualidade.

## Por que usar o modo de codificação Bytes?
O modo Bytes permite incorporar dados binários brutos (até 1.555 bytes) sem convertê‑los em texto, o que é ideal para números de série, GUIDs ou cargas úteis criptografadas. Aspose.BarCode suporta **30+ simbologias de código de barras** e pode processar **documentos com centenas de páginas** sem carregar o arquivo inteiro na memória, garantindo desempenho rápido mesmo em cenários de alto volume.

## Pré‑requisitos

Antes de mergulharmos no processo de codificação, você precisará ter os seguintes pré‑requisitos em vigor:

1. Aspose.BarCode for .NET: Para começar, você deve ter a biblioteca Aspose.BarCode for .NET instalada. Você pode baixá‑la em [aqui](https://releases.aspose.com/barcode/net/). Você também pode encontrar outros produtos Aspose em [aqui](https://releases.aspose.com/).
2. Seu Ambiente de Desenvolvimento: Certifique‑se de que você tem um ambiente de desenvolvimento configurado, incluindo Visual Studio ou qualquer outra IDE de sua escolha.
3. Conhecimento Básico de C#: Este tutorial assume que você tem uma compreensão básica da programação em C#.

Para obter ajuda, visite [Suporte Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

Com esses pré‑requisitos em vigor, você está pronto para começar a codificar dados no formato DataMatrix usando o modo Bytes.

## Importar Namespaces

Para usar Aspose.BarCode para .NET, importe os namespaces necessários no topo do seu arquivo C#:

```csharp
using System;
using System.Text;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

Agora que o ambiente está pronto, vamos percorrer os passos exatos para **gerar código de barras DataMatrix** e então lê‑lo novamente.

## Como gerar código de barras DataMatrix no modo Bytes?

Carregue o `BarcodeGenerator`, defina o modo de codificação para Bytes, configure o texto de exibição opcional, salve a imagem e, finalmente, use `BarCodeReader` para verificar o resultado — tudo em seis passos concisos. Esta abordagem garante um código de barras confiável que segue o padrão ISO/IEC 16022.

### Etapa 1: Inicializar o BarcodeGenerator

`BarcodeGenerator` é a classe principal usada para gerar imagens de código de barras para uma determinada simbologia e dados.

```csharp
string path = "Your Directory Path";
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, strBld.ToString()))
{
    // Set the XDimension in Pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
```

### Etapa 2: Definir o Modo de Codificação DataMatrix para Bytes

`DataMatrixEncodeMode.Bytes` indica ao gerador que trate a entrada como bytes binários brutos em vez de texto.

```csharp
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Bytes;
```

### Etapa 3: Definir o Texto de Exibição

A propriedade `CodeText` define o texto legível por humanos exibido abaixo do símbolo do código de barras.

```csharp
    gen.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Bytes mode";
```

### Etapa 4: Salvar a Imagem do Código de Barras

O método `Save` grava o código de barras gerado em um arquivo de imagem no formato especificado.

```csharp
    gen.Save($"{path}DataMatrixEncodeModeBytes.png", BarCodeImageFormat.Png);
```

### Etapa 5: Tentar Reconhecer

`BarCodeReader` lê imagens de código de barras e extrai os dados codificados.

```csharp
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
```

### Etapa 6: Iterar e Exibir Resultados

Itere sobre `reader.ReadBarCodes()` para acessar cada código de barras detectado e seu `CodeText`.

```csharp
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixEncodeModeBytes:" + BitConverter.ToString(result.CodeBytes));
    }
}
```

Com esses passos, você gerou com sucesso **um código de barras DataMatrix** no modo Bytes e o verificou usando Aspose.BarCode para .NET. A biblioteca abstrai os detalhes de codificação de baixo nível, permitindo que você se concentre na lógica de negócios em vez da matemática do código de barras.

## Problemas Comuns e Soluções

- **Dados codificados são truncados** – Certifique‑se de que o array de bytes não exceda 1.555 bytes; caso contrário, a biblioteca mudará automaticamente para um tamanho de símbolo maior ou lançará uma exceção.
- **A imagem aparece borrada** – Salve a imagem em uma resolução mais alta (por exemplo, 300 dpi) definindo `generator.Parameters.ImageResolution` antes de chamar `Save`.
- **O leitor retorna null** – Verifique se o caminho da imagem está correto e se o arquivo não está corrompido; também confirme que `BarCodeReader` foi instanciado com `DecodeType.DataMatrix`.

## Perguntas Frequentes

**Q: O que é o modo de codificação DataMatrix?**  
A: O modo de codificação DataMatrix define como os dados de entrada são transformados no padrão bidimensional; o modo Bytes armazena bytes binários brutos diretamente.

**Q: Como posso obter uma avaliação gratuita do Aspose.BarCode para .NET?**  
A: Você pode obter uma avaliação gratuita do Aspose.BarCode para .NET em [aqui](https://releases.aspose.com/).

**Q: Onde posso encontrar a documentação do Aspose.BarCode para .NET?**  
A: A documentação do Aspose.BarCode para .NET está disponível [aqui](https://reference.aspose.com/barcode/net/).

**Q: O Aspose.BarCode para .NET é adequado para uso comercial?**  
A: Sim, o Aspose.BarCode para .NET é adequado para uso comercial. Você pode comprar uma licença em [aqui](https://purchase.aspose.com/buy).

**Q: Posso usar uma licença temporária para o Aspose.BarCode para .NET?**  
A: Sim, você pode obter uma licença temporária para o Aspose.BarCode para .NET em [aqui](https://purchase.aspose.com/temporary-license/).

---

**Última Atualização:** 2026-05-30  
**Testado com:** Aspose.BarCode 24.12 for .NET  
**Autor:** Aspose

## Tutoriais Relacionados

- [Dominar a Codificação DataMatrix em ASCII com Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Ler código de barras DataMatrix C# – Gerar Modo DataMatrix (Auto)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Como Gerar Códigos de Barras DataMatrix (ECC 200) com Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}