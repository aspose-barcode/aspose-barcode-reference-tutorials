---
date: 2026-09-23
description: Aprenda a usar Aspose.BarCode para gerar um código de barras DataMatrix
  com texto de código estendido em .NET, ideal para aplicações de inventário e logística.
keywords:
- how to use aspose
- create barcode for inventory
- barcode generation .net core
- generate barcode image c#
lastmod: 2026-09-23
linktitle: Configuração de Texto de Código Estendido DataMatrix
og_description: Como usar Aspose.BarCode para gerar um código de barras DataMatrix
  com texto de código estendido em .NET. Siga um guia rápido passo a passo para soluções
  de inventário e logística.
og_image_alt: Screenshot of a DataMatrix barcode generated with Aspose.BarCode in
  a .NET console app
og_title: Como usar Aspose.BarCode para criar texto de código DataMatrix em .NET
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  headline: How to use Aspose.BarCode to create DataMatrix code text in .NET
  type: TechArticle
- description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  name: How to use Aspose.BarCode to create DataMatrix code text in .NET
  steps:
  - name: Define the output folder
    text: Specify where the generated barcode image will be saved. Replace the placeholder
      with a valid path on your machine.
  - name: Build the extended code text
    text: '`DataMatrixExtCodetextBuilder` is a helper class that assembles the extended
      code text according to the DataMatrix specification. It automatically inserts
      the required ECI (Extended Channel Interpretation) markers. This mix demonstrates
      how you can combine Unicode characters, C40 encoding, plain tex'
  - name: Generate the final codetext string
    text: After configuring all parts, retrieve the combined string that Aspose.BarCode
      will embed into the barcode.
  - name: Create the DataMatrix barcode
    text: '`BarcodeGenerator` is the core class that produces barcode images. Instantiate
      it with `EncodeTypes.DataMatrix` and the extended codetext, then set visual
      parameters such as X‑dimension, image format, and optional human‑readable text.
      The above code **creates barcode aspose .net** with the desired e'
  - name: Verify the barcode by reading it back
    text: '`BarCodeReader` validates that the generated symbol can be decoded correctly,
      which is essential for automated test pipelines and quality assurance. If everything
      is set up properly, the console will output the exact extended code text you
      built earlier.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET
    question: What library is needed?
  - answer: DataMatrix with extended code text
    question: Which barcode type?
  - answer: Yes, the API is cross‑platform
    question: Can I use .NET Core / .NET 6?
  - answer: A free trial works for development; a license is required for production
    question: Do I need a license for testing?
  - answer: About 10‑15 minutes for a basic example
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- Aspose.BarCode
- DataMatrix
- .NET barcode
- C# barcode generation
- inventory labeling
title: Como usar Aspose.BarCode para criar texto de código DataMatrix em .NET
url: /pt/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como usar Aspose.BarCode para criar texto de código DataMatrix em .NET

Integrar códigos de barras em aplicações .NET modernas não é mais uma tarefa de nicho — é um requisito central para inventário, logística e soluções de digitalização móvel. Neste guia você **aprenderá como usar Aspose.BarCode** para configurar um código de barras DataMatrix com texto de código estendido, gerar a imagem e verificá‑la programaticamente. Você verá por que essa abordagem é ideal para criar códigos de barras para inventário e como ela se encaixa em projetos .NET Core ou .NET 6.

## Respostas rápidas
- **Qual biblioteca é necessária?** Aspose.BarCode for .NET  
- **Qual tipo de código de barras?** DataMatrix with extended code text  
- **Posso usar .NET Core / .NET 6?** Yes, the API is cross‑platform  
- **Preciso de uma licença para testes?** A free trial works for development; a license is required for production  
- **Quanto tempo leva a implementação?** About 10‑15 minutes for a basic example  

## O que é Aspose.BarCode para .NET?
Aspose.BarCode para .NET é uma biblioteca comercial que permite aos desenvolvedores gerar e reconhecer mais de 30 simbologias de códigos de barras, incluindo DataMatrix, QR e Code 128, e produzir imagens de até 10.000 × 10.000 pixels sem dependências externas. Ela oferece suporte a .NET Framework 4.5+, .NET Core 3.1+ e .NET 5/6/7.

## Por que usar texto de código estendido DataMatrix?
O texto de código estendido DataMatrix permite incorporar vários esquemas de codificação — UTF‑8, C40, Text, X12 — em um único símbolo, permitindo até **3116 codewords** (aproximadamente 155 KB de dados) em um quadrado compacto. Essa capacidade é perfeita para rotulagem de produtos multilíngues, rastreamento de dispositivos médicos e embalagens inteligentes onde é necessário combinar IDs alfanuméricos com cargas binárias.

## Pré‑requisitos

Antes de começar, verifique se você tem o seguinte:

1. **Aspose.BarCode for .NET** – faça o download no site oficial **[Aspose.BarCode .NET download page](https://releases.aspose.com/barcode/net/)**.  
2. **Um ambiente de desenvolvimento .NET** – Visual Studio, Rider ou VS Code com o .NET SDK.  
3. **Conhecimento básico de C#** – você deve estar confortável com classes, namespaces e a diretiva `using`.

## Importar namespaces

Adicione os namespaces necessários no início do seu arquivo C# para que o compilador saiba onde encontrar as classes de código de barras.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

Esses namespaces dão acesso tanto aos recursos de geração quanto de reconhecimento de códigos de barras.

## Como configurar texto de código estendido DataMatrix?

Carregue o builder, adicione os segmentos desejados e deixe o Aspose.BarCode lidar com os marcadores ECI automaticamente. Este parágrafo de resposta direta indica os passos exatos: criar um `DataMatrixExtCodetextBuilder`, adicionar segmentos Unicode, C40, texto simples e modo Text, e então recuperar a string combinada para o gerador.

### Etapa 1: Definir a pasta de saída

Especifique onde a imagem do código de barras gerado será salva. Substitua o placeholder por um caminho válido na sua máquina.

```csharp
string path = "Your Directory Path";
```

### Etapa 2: Construir o texto de código estendido

`DataMatrixExtCodetextBuilder` é uma classe auxiliar que monta o texto de código estendido de acordo com a especificação DataMatrix. Ela insere automaticamente os marcadores ECI (Extended Channel Interpretation) necessários.

```csharp
DataMatrixExtCodetextBuilder codetextBuilder = new DataMatrixExtCodetextBuilder();
codetextBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
codetextBuilder.AddECICodetextWithEncodeMode(ECIEncodings.UTF8, DataMatrixEncodeMode.C40, "ABCDE");
codetextBuilder.AddPlainCodetext("test");
codetextBuilder.AddCodetextWithEncodeMode(DataMatrixEncodeMode.Text, "abcde");
```

Esta combinação demonstra como você pode combinar caracteres Unicode, codificação C40, texto simples e modo Text em um único símbolo DataMatrix.

### Etapa 3: Gerar a string final de codetext

Após configurar todas as partes, recupere a string combinada que o Aspose.BarCode incorporará ao código de barras.

```csharp
string codetext = codetextBuilder.GetExtendedCodetext();
```

### Etapa 4: Criar o código de barras DataMatrix

`BarcodeGenerator` é a classe principal que produz imagens de códigos de barras. Instancie‑a com `EncodeTypes.DataMatrix` e o codetext estendido, depois defina parâmetros visuais como X‑dimension, formato da imagem e texto legível opcional.

```csharp
using (var generator = new BarcodeGenerator(EncodeTypes.DataMatrix, codetext))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended Codetext";
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ExtendedCodetext;

    generator.Save($"{path}DataMatrixExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

O código acima **cria barcode aspose .net** com o texto de código estendido desejado e o salva como um arquivo PNG.

### Etapa 5: Verificar o código de barras lendo‑o novamente

`BarCodeReader` valida que o símbolo gerado pode ser decodificado corretamente, o que é essencial para pipelines de teste automatizados e garantia de qualidade.

```csharp
using (var reader = new BarCodeReader(generator.GenerateBarCodeImage(), DecodeType.DataMatrix))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
        Console.WriteLine("DataMatrixExtendedCodetext:" + result.CodeText);
}
```

Se tudo estiver configurado corretamente, o console exibirá o texto de código estendido exato que você construiu anteriormente.

## Armadilhas comuns e solução de problemas

| Problema | Razão | Correção |
|----------|-------|----------|
| Código de barras ilegível | X‑dimension muito baixa | Aumente `XDimension.Pixels` (ex.: 4 → 6) |
| Caracteres corrompidos | Codificação ECI incorreta | Garanta que `ECIEncodings.UTF8` corresponda ao conjunto de caracteres |
| Arquivo não salvo | Caminho inválido | Use um caminho absoluto ou verifique se a pasta existe |
| Exceção de licença | Teste expirado | Aplique uma licença temporária ou completa (veja FAQ) |

## Perguntas frequentes

### Q1: O que é Aspose.BarCode para .NET?
A1: Aspose.BarCode para .NET é uma biblioteca poderosa que permite aos desenvolvedores gerar e reconhecer uma ampla variedade de simbologias de códigos de barras, incluindo DataMatrix, QR, Code128 e mais.

### Q2: Onde posso encontrar a documentação do Aspose.BarCode para .NET?
A2: Você pode acessar a referência completa da API **[Aspose.BarCode .NET API reference](https://reference.aspose.com/barcode/net/)**.

### Q3: Existe uma versão de teste gratuita disponível para Aspose.BarCode para .NET?
A3: Sim, uma versão de teste gratuita pode ser baixada em **[Aspose.BarCode free trial download](https://releases.aspose.com/)**.

### Q4: Como obtenho uma licença temporária para teste?
A4: Licenças temporárias são fornecidas para fins de avaliação e podem ser solicitadas em **[Aspose temporary license request page](https://purchase.aspose.com/temporary-license/)**.

### Q5: Onde posso obter suporte ou fazer perguntas sobre Aspose.BarCode para .NET?
A5: O fórum oficial do Aspose.BarCode é o melhor lugar para buscar ajuda: **[Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)**.

---

**Última atualização:** 2026-09-23  
**Testado com:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose

## Tutoriais Relacionados

- [Como gerar códigos de barras DataMatrix usando Aspose.BarCode para .NET – Guia passo a passo](/barcode/net/datamatrix-barcode-configuration/)
- [Gerar um código de barras DataMatrix em modo ASCII com Aspose.BarCode para .NET (C#)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Gerar código de barras Aztec com codificação de texto usando Aspose.BarCode para .NET](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}