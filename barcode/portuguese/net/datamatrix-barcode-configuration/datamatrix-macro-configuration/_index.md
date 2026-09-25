---
date: 2026-08-17
description: Aprenda a criar código de barras DataMatrix com caracteres macro usando
  Aspose.BarCode para .NET e descubra como usar DataMatrix em suas aplicações.
keywords:
- create datamatrix barcode
- datamatrix barcode error correction
- aspose barcode macro
- .net barcode generation
lastmod: 2026-08-17
linktitle: Configuração de Macro DataMatrix
og_description: Aprenda a criar código de barras DataMatrix com caracteres macro usando
  Aspose.BarCode para .NET. Este guia fornece código passo a passo, opções de personalização
  e dicas de verificação para geração confiável de códigos de barras.
og_image_alt: Guide showing creation of DataMatrix barcode with macro characters in
  .NET using Aspose.BarCode
og_title: Criar código de barras DataMatrix com caracteres macro usando Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-17'
  description: Learn how to create DataMatrix barcode with macro characters using
    Aspose.BarCode for .NET and discover how to use DataMatrix in your applications.
  headline: How to create DataMatrix barcode with macro characters in .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode with macro characters using
    Aspose.BarCode for .NET and discover how to use DataMatrix in your applications.
  name: How to create DataMatrix barcode with macro characters in .NET
  steps:
  - name: setting up your project
    text: Create a new Console Application (or any .NET project) in Visual Studio.
      Add a reference to the Aspose.BarCode DLLs that you obtained from the download.
  - name: DataMatrix macro configuration
    text: The core of the tutorial – here we actually **create DataMatrix barcode**
      with a macro character. > **Pro tip:** Replace `"ASPOSE"` with any string you
      need to encode. The macro character (`Macro05`) tells scanners that this barcode
      is part of a macro sequence.
  - name: customize barcode parameters for error correction
    text: 'Before saving, you can tweak additional settings: - **XDimension** – controls
      the size of each module (pixel). - **Margin**, **ErrorCorrection**, and **EncodingMode**
      – all accessible via `gen.Parameters.Barcode.DataMatrix`.'
  - name: save the barcode
    text: The snippet above saves the image as `DataMatrixMacro.png` in the folder
      you specified. PNG is loss‑less, making it ideal for further processing.
  - name: recognize the barcode
    text: '`BarCodeReader` is Aspose.BarCode''s class for decoding barcodes from images.
      Using `BarCodeReader` we immediately read back the generated image to confirm
      that the macro character and data are correct. This round‑trip validation is
      especially handy during automated testing.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET is a powerful library that allows .NET developers
      to generate and recognize barcodes in various formats, including DataMatrix,
      QR, and more.
    question: What is Aspose.BarCode for .NET?
  - answer: DataMatrix barcodes are compact, highly reliable, and can store large
      amounts of data, making them ideal for manufacturing, logistics, and healthcare.
    question: Why should I use DataMatrix barcodes?
  - answer: You can find the documentation at [the Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).
    question: Where can I find the documentation for Aspose.BarCode for .NET?
  - answer: Yes, you can download a free trial from [the free trial link](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: If you have any questions or need support, you can visit the Aspose.BarCode
      for .NET forum at [the support forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- aspose.barcode
- c# barcode generation
- macro barcode
- barcode error correction
title: Como criar código de barras DataMatrix com caracteres macro no .NET
url: /pt/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar código de barras DataMatrix com caracteres macro em .NET

## Introdução

Gerar um **código de barras DataMatrix** que inclua caracteres macro permite embutir informações de referência adicionais em um pequeno símbolo quadrado. Neste tutorial você aprenderá a **criar código de barras DataMatrix** com caracteres macro usando Aspose.BarCode para .NET, personalizar tamanho e correção de erros e verificar o resultado instantaneamente. Ao final, você estará pronto para incorporar códigos de barras habilitados para macro em rótulos de produtos, documentos ou dispositivos médicos.

## Respostas rápidas
- **Qual é a biblioteca principal?** Aspose.BarCode para .NET  
- **Posso criar um código de barras DataMatrix com caracteres macro?** Sim – defina a propriedade `MacroCharacters`.  
- **Preciso de licença para produção?** É necessária uma licença válida da Aspose para uso em produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Existe uma versão de avaliação gratuita?** Absolutamente – faça o download no site oficial da Aspose.

## Pré‑requisitos

Antes de mergulhar na configuração de macro, certifique‑se de que você tem o seguinte:

1. **Visual Studio** – qualquer edição recente funciona.  
2. **Aspose.BarCode para .NET** – faça o download em [o link de download](https://releases.aspose.com/barcode/net/).  
3. **Conhecimento básico de .NET** – familiaridade com C# e o ecossistema .NET.

## Importar namespaces

Começamos importando os namespaces necessários para geração e reconhecimento de códigos de barras.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

## O que é “gerar código de barras DataMatrix” com caracteres macro?

`MacroCharacters` permite que códigos de barras DataMatrix incluam símbolos macro que referenciam dados adicionais. Usando caracteres macro como Macro05 ou Macro06, um único código de barras pode apontar para um conjunto de dados maior ou para uma sequência de códigos de barras relacionados, o que é valioso em logística, manufatura e rastreamento de documentos, onde a codificação compacta de informações vinculadas é necessária.

## Por que usar Aspose.BarCode para gerar código de barras DataMatrix?

Aspose.BarCode oferece controle preciso sobre o tamanho do DataMatrix, nível de correção de erros e configurações de macro, suportando mais de 30 simbologias de código de barras e manipulando arquivos de até 10 MB sem carregar a imagem inteira na memória. Sua implementação multiplataforma .NET funciona em .NET Framework, .NET Core e .NET 5/6, e inclui reconhecimento embutido para que você possa validar o código de barras instantaneamente.

## Guia passo a passo

### Etapa 1: configurando seu projeto

Crie um novo Console Application (ou qualquer projeto .NET) no Visual Studio. Adicione uma referência às DLLs do Aspose.BarCode que você obteve no download.

### Etapa 2: configuração de macro do DataMatrix

O núcleo do tutorial – aqui realmente **criamos o código de barras DataMatrix** com um caractere macro.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixMacro:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE"))
{
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    // Set the macro character to 05
    gen.Parameters.Barcode.DataMatrix.MacroCharacters = MacroCharacter.Macro05;
    gen.Save($"{path}DataMatrixMacro.png", BarCodeImageFormat.Png);

    // Try to recognize it
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixMacro:" + result.CodeText);
    }
}
```

> **Dica profissional:** Substitua `"ASPOSE"` por qualquer string que você precise codificar. O caractere macro (`Macro05`) informa aos scanners que este código de barras faz parte de uma sequência macro.

### Etapa 3: personalizar parâmetros do código de barras para correção de erros

Antes de salvar, você pode ajustar configurações adicionais:

- **XDimension** – controla o tamanho de cada módulo (pixel).  
- **Margin**, **ErrorCorrection** e **EncodingMode** – todos acessíveis via `gen.Parameters.Barcode.DataMatrix`.

### Etapa 4: salvar o código de barras

O trecho acima salva a imagem como `DataMatrixMacro.png` na pasta especificada. PNG é sem perdas, tornando‑o ideal para processamento posterior.

### Etapa 5: reconhecer o código de barras

`BarCodeReader` é a classe do Aspose.BarCode para decodificar códigos de barras a partir de imagens. Usando `BarCodeReader` lemos imediatamente a imagem gerada para confirmar que o caractere macro e os dados estão corretos. Essa validação de ida e volta é especialmente útil durante **testes automatizados**.

## Como usar DataMatrix em cenários do mundo real?

Você pode aplicar códigos de barras DataMatrix com caracteres macro à rotulagem de produtos, vinculando números de série a um banco de dados central, ao rastreamento de documentos incorporando uma referência a um registro digital, e a etiquetas de equipamentos de saúde que armazenam dados de pacientes ou dispositivos em um símbolo pequeno e escaneável. Esses casos de uso reduzem a entrada manual de dados e melhoram a rastreabilidade.

## Problemas comuns & soluções

| Problema | Motivo | Solução |
|----------|--------|---------|
| Código de barras não reconhecido | `XDimension` incorreto ou baixa resolução da imagem | Aumente `XDimension.Pixels` para 4‑6 e salve como PNG ou TIFF |
| Caractere macro ignorado | Leitor não suporta modo macro | Use um scanner/leitor que suporte explicitamente macro DataMatrix (ex.: versões mais recentes do ZXing) |
| Caminho não encontrado | Variável `path` inválida | Certifique‑se de que o diretório exista ou use `Path.Combine` com `Environment.CurrentDirectory` |

## Perguntas frequentes

**Q: O que é Aspose.BarCode para .NET?**  
A: Aspose.BarCode para .NET é uma biblioteca poderosa que permite a desenvolvedores .NET gerar e reconhecer códigos de barras em vários formatos, incluindo DataMatrix, QR e outros.

**Q: Por que devo usar códigos de barras DataMatrix?**  
A: Códigos de barras DataMatrix são compactos, altamente confiáveis e podem armazenar grandes quantidades de dados, tornando‑os ideais para manufatura, logística e saúde.

**Q: Onde posso encontrar a documentação do Aspose.BarCode para .NET?**  
A: Você pode encontrar a documentação em [a documentação do Aspose.BarCode para .NET](https://reference.aspose.com/barcode/net/).

**Q: Existe uma versão de avaliação gratuita para Aspose.BarCode para .NET?**  
A: Sim, você pode baixar uma avaliação gratuita em [o link de avaliação gratuita](https://releases.aspose.com/).

**Q: Onde posso obter suporte para Aspose.BarCode para .NET?**  
A: Se tiver dúvidas ou precisar de suporte, visite o fórum do Aspose.BarCode para .NET em [o fórum de suporte](https://forum.aspose.com/c/barcode/13).

---

**Última atualização:** 2026-08-17  
**Testado com:** Aspose.BarCode 24.11 para .NET  
**Autor:** Aspose

## Tutoriais relacionados

- [Create barcode aspose .net - Configuring DataMatrix Code Text](/barcode/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [DataMatrix Structured Append Configuration with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}