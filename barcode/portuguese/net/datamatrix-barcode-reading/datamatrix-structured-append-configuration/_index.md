---
date: 2026-06-14
description: Aprenda a ler datamatrix e gerar códigos de barras structured append
  no .NET usando Aspose.BarCode, a biblioteca de códigos de barras rápida e confiável.
keywords:
- how to read datamatrix
- DataMatrix structured append
- Aspose.BarCode .NET
linktitle: Configuração de DataMatrix Structured Append
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to read datamatrix and generate structured append barcodes
    in .NET using Aspose.BarCode, the fast and reliable barcode library.
  headline: How to Read DataMatrix Append with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to read datamatrix and generate structured append barcodes
    in .NET using Aspose.BarCode, the fast and reliable barcode library.
  name: How to Read DataMatrix Append with Aspose.BarCode for .NET
  steps:
  - name: Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
    text: Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
  - name: You can also browse other Aspose products [here](https://releases.aspose.com/).
    text: You can also browse other Aspose products [here](https://releases.aspose.com/).
  - name: A .NET development environment such as Visual Studio 2022 or Visual Studio
      Code with the C# extension.
    text: A .NET development environment such as Visual Studio 2022 or Visual Studio
      Code with the C# extension.
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET.
    question: What library handles DataMatrix structured append?
  - answer: Up to 16 DataMatrix symbols.
    question: How many symbols can a single structured append sequence contain?
  - answer: A free trial works for development and testing.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes, you can decode from a byte array or stream.
    question: Can I read the barcode without an image file?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Como ler DataMatrix Append com Aspose.BarCode para .NET
url: /pt/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configuração de Append Estruturado DataMatrix com Aspose.BarCode para .NET

Se você é um desenvolvedor procurando **how to read datamatrix** usando append estruturado em suas aplicações .NET, Aspose.BarCode para .NET é a sua solução ideal. Neste guia passo a passo, vamos percorrer a geração e decodificação de códigos de barras DataMatrix que são divididos em vários símbolos. Ao final deste tutorial, você estará confortável em criar, configurar e ler códigos de barras DataMatrix com append estruturado usando Aspose.BarCode para .NET.

## Respostas Rápidas
- **Qual biblioteca lida com o append estruturado DataMatrix?** Aspose.BarCode for .NET.
- **Quantos símbolos pode conter uma única sequência de append estruturado?** Até 16 símbolos DataMatrix.
- **Preciso de uma licença para desenvolvimento?** Uma versão de avaliação gratuita funciona para desenvolvimento e testes.
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Posso ler o código de barras sem um arquivo de imagem?** Sim, você pode decodificar a partir de um array de bytes ou stream.

## O que é how to read datamatrix?
**how to read datamatrix** refere-se ao processo de decodificar símbolos DataMatrix e, quando aplicável, juntar as partes de uma sequência de append estruturado para recuperar a carga de dados original. Aspose.BarCode fornece suporte embutido para esse fluxo de trabalho, lidando automaticamente com a ordem dos símbolos e a concatenação dos dados.

## Por que usar Aspose.BarCode para append estruturado DataMatrix?
Aspose.BarCode suporta **30+ simbologias de código de barras** e pode decodificar imagens de até **10.000 × 10.000 px** em menos de **200 ms** em hardware de servidor típico. A biblioteca também oferece **implantação sem dependências**, o que significa que você não precisa de DLLs nativas adicionais, e funciona em runtimes .NET para Windows, Linux e macOS.

## Pré-requisitos

Antes de mergulhar no tutorial, você precisará:

1. Aspose.BarCode for .NET Library – faça o download a partir de [here](https://releases.aspose.com/barcode/net/).
2. Você também pode navegar por outros produtos Aspose [here](https://releases.aspose.com/).
3. Um ambiente de desenvolvimento .NET como Visual Studio 2022 ou Visual Studio Code com a extensão C#.

Agora, vamos começar a criar e ler códigos de barras DataMatrix com append estruturado.

## Importar Namespaces

O primeiro passo é importar os namespaces que expõem a API de código de barras.

A classe `BarCodeWriter` é o ponto de entrada do Aspose.BarCode para criar códigos de barras, enquanto `BarCodeReader` lida com a decodificação.

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

Agora que você importou os namespaces necessários, vamos gerar um código de barras de append estruturado.

## Como ler códigos de barras DataMatrix com append estruturado?

Carregue a imagem gerada (ou stream) em um `BarCodeReader`, habilite a opção `ReadStructuredAppend` e chame `ReadBarcode`. O leitor retornará automaticamente os dados combinados e exporá detalhes da sequência, como `StructuredAppendFileId`, `StructuredAppendTotalCount` e `StructuredAppendSegmentId`. O resultado combinado é retornado como uma única string, e você também pode recuperar os identificadores de segmento individuais através da propriedade `StructuredAppendSegmentId` do leitor para processamento personalizado.

```csharp
    using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
    {
        reader.ReadBarCodes();

        Console.WriteLine("Barcode ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodeId);
        Console.WriteLine("Barcodes count: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodesCount);
        Console.WriteLine("File ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendFileId);
    }
}
```

Nesta etapa, usamos o leitor para extrair o ID do código de barras, a contagem total e o ID do arquivo, confirmando que a configuração de append estruturado foi interpretada corretamente.

## Etapa 1: Configurar Append Estruturado DataMatrix

Para criar um código de barras DataMatrix com append estruturado, você precisa configurar sua configuração. Isso inclui definir o caminho do diretório, o ID do código de barras, o número de códigos de barras e o ID do arquivo.

```csharp
string path = "Your Directory Path";

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;

    // Set DataMatrix structured append mode
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodeId = 3;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodesCount = 5;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendFileId = 150;

    // Generate the barcode image
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

Nesta etapa, configuramos o código de barras DataMatrix com os parâmetros desejados.

## Problemas Comuns e Soluções

- **Ordenação de segmento incorreta:** Certifique-se de que os valores de `StructuredAppendSegmentId` sejam sequenciais a partir de 0; caso contrário, o leitor não poderá remontar os dados corretamente.
- **Contagem total incompatível:** O `StructuredAppendTotalCount` deve ser o mesmo em todos os símbolos; uma incompatibilidade fará com que o leitor trate a sequência como incompleta.
- **Qualidade da imagem:** Imagens de baixa resolução podem causar falhas na decodificação. Procure ter pelo menos **300 dpi** ao renderizar o código de barras em um bitmap.

## Perguntas Frequentes

### Q1: O que é append estruturado DataMatrix e por que é usado?
R1: O append estruturado DataMatrix é um recurso que permite dividir uma grande quantidade de dados em vários códigos de barras menores. Isso é particularmente útil quando você tem espaço limitado para um único código de barras ou precisa organizar os dados de forma eficiente. É comumente usado em logística, saúde e manufatura.

### Q2: Posso usar Aspose.BarCode para .NET no meu projeto de código aberto?
R2: Sim, Aspose.BarCode para .NET oferece uma versão de avaliação gratuita que você pode usar em projetos de código aberto. Você pode encontrar a versão de avaliação [here](https://releases.aspose.com/).

### Q3: Existe suporte da comunidade disponível para Aspose.BarCode para .NET?
R3: Sim, você pode buscar suporte da comunidade e interagir com outros usuários no fórum Aspose.BarCode [here](https://forum.aspose.com/c/barcode/13).

### Q4: Como posso obter uma licença temporária para Aspose.BarCode para .NET?
R4: Se você precisar de uma licença temporária para avaliação ou testes, pode obter uma em [here](https://purchase.aspose.com/temporary-license/).

### Q5: O Aspose.BarCode para .NET suporta outros tipos de código de barras?
R5: Sim, Aspose.BarCode para .NET suporta uma ampla variedade de tipos de códigos de barras, incluindo QR codes, Code 128, EAN‑13 e muitos outros. Você pode explorar a documentação completa [here](https://reference.aspose.com/barcode/net/) para ver a lista completa de tipos de código de barras suportados.

---

**Última atualização:** 2026-06-14  
**Testado com:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose

## Tutoriais Relacionados

- [Programação do Leitor DataMatrix com Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-reader-programming/)
- [Gerar códigos de barras DataMatrix com Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-versions/)
- [Configuração Mestre de Macro DataMatrix com Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}