---
date: 2026-08-02
description: Aprenda a criar código de barras DataMatrix, gerar datamatrix e explorar
  a geração de códigos de barras de alta densidade com Aspose.BarCode para projetos
  .NET.
keywords:
- create datamatrix barcode
- high density barcode
- generate datamatrix barcode
- barcode generation asp.net
- temporary aspose license
lastmod: 2026-08-02
linktitle: Configuração do DataMatrix ECC 200
og_description: Crie código de barras DataMatrix com Aspose.BarCode para .NET. Este
  tutorial mostra a geração de códigos de barras de alta densidade, configuração temporária
  da licença Aspose e código C# passo a passo.
og_image_alt: Guide showing C# code to create a DataMatrix barcode using Aspose.BarCode
og_title: Criar código de barras DataMatrix – guia Aspose.BarCode .NET
schemas:
- author: Aspose
  dateModified: '2026-08-02'
  description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  headline: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  name: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  steps:
  - name: Initialize the Barcode Generator
    text: '`BarcodeGenerator` is Aspose.BarCode''s core class that creates and renders
      barcodes. It accepts the symbology type and the text to encode. Replace `"Your
      Directory Path"` with the folder where you’d like the image saved.'
  - name: Set XDimension and ECC Type
    text: '`XDimension` defines the pixel size of each DataMatrix module, while `DataMatrixEcc`
      selects the error‑correction level. ECC 200 provides the highest correction
      capability for this symbology. Adjust the pixel value if you need larger or
      smaller modules; typical values are 4‑6 px for on‑screen displa'
  - name: Generate and Save the Barcode Image
    text: The `Save` method writes the barcode to a file. You can choose PNG, JPEG,
      or TIFF by passing the corresponding `BarCodeImageFormat` enum value. Switch
      `BarCodeImageFormat.Png` to `BarCodeImageFormat.Jpeg` or `BarCodeImageFormat.Tiff`
      if your workflow requires a different format.
  type: HowTo
- questions:
  - answer: Yes, the same API works in .NET Core, .NET 5, and .NET 6 projects.
    question: Can I use this code in a .NET Core console application?
  - answer: Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg` in the
      `Save` call.
    question: How do I change the output format to JPEG?
  - answer: Yes – generate the image first, then add it to a PDF using Aspose.PDF
      or any PDF library.
    question: Is it possible to embed the barcode directly into a PDF?
  - answer: DataMatrix supports UTF‑8; simply pass the Unicode string to the generator
      as shown.
    question: What if I need to encode Unicode characters?
  - answer: Absolutely – place the generation code inside a loop and change the data/value
      for each iteration.
    question: Does the library support batch generation of multiple barcodes?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- .NET barcode generation
- C# barcode tutorial
title: Como criar código de barras DataMatrix (ECC 200) com Aspose.BarCode para .NET
url: /pt/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar código de barras DataMatrix (ECC 200) com Aspose.BarCode para .NET

## Introdução

Neste guia você **criará código de barras DataMatrix** (ECC 200) usando Aspose.BarCode para .NET. Seja construindo um rastreador de inventário, um sistema ponto‑de‑venda ou automatizando fluxos de trabalho de documentos, um código de barras de alta densidade pode armazenar muitos dados em um espaço pequeno. Percorreremos cada passo de configuração, explicaremos por que cada ajuste importa e forneceremos trechos de C# prontos para execução.

## Respostas rápidas

- **Qual biblioteca é a melhor para DataMatrix em .NET?** Aspose.BarCode for .NET  
- **Qual nível ECC o ECC 200 fornece?** Correção de erro de alta densidade para leitura robusta.  
- **Preciso de uma licença para executar o exemplo?** Uma licença temporária funciona para avaliação; uma licença completa é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Posso gerar PNG, JPEG ou TIFF?** Sim – o método `Save` suporta vários formatos de imagem.

## O que é DataMatrix ECC 200?

DataMatrix ECC 200 é um código de barras bidimensional de alta densidade que pode armazenar até 2.335 caracteres alfanuméricos ou 1.556 bytes de dados binários em um padrão compacto quadrado ou retangular. Ele usa correção de erro Reed‑Solomon para recuperar módulos perdidos ou danificados, tornando‑o ideal para aplicações como marcação de peças aeroespaciais, rotulagem farmacêutica e logística, onde a confiabilidade é crítica.

## Por que usar a geração de código de barras Aspose?

Aspose.BarCode suporta **30+ simbologias**, pode renderizar imagens de até 10.000 × 10.000 px sem carregar o arquivo inteiro na memória, e fornece saída determinística em Windows, Linux e macOS. Sua API permite controlar cada parâmetro de renderização, tornando‑a a escolha mais flexível para cenários de **geração de código de barras ASP.NET**.

## Pré-requisitos

1. **Ambiente de Desenvolvimento** – Visual Studio com o framework .NET apropriado instalado.  
2. **Aspose.BarCode for .NET** – Baixe e instale do site, [aqui](https://releases.aspose.com/barcode/net/).  
3. **Licença** – Obtenha uma licença temporária para teste [aqui](https://purchase.aspose.com/temporary-license/).  
4. **Fundamentos de C#** – Familiaridade com a sintaxe C# e a estrutura de projetos.

Agora que cobrimos o básico, vamos avançar para a configuração do DataMatrix ECC 200.

## Importar Namespaces

O namespace `Aspose.BarCode.Generation` contém todas as classes necessárias para a criação de códigos de barras. Importe-o no início do seu arquivo:

```csharp
using Aspose.BarCode.Generation;
```

## Como criar código de barras DataMatrix (ECC 200) passo a passo

Para gerar um código de barras DataMatrix ECC 200, basta carregar os dados que deseja codificar, configurar alguns parâmetros chave no `BarcodeGenerator` e então chamar `Save` para gravar o arquivo de imagem. Esse fluxo de três etapas lida com codificação, correção de erro e seleção de formato de saída, permitindo integrar a criação de códigos de barras em qualquer aplicação .NET com código mínimo.

### Passo 1: Inicializar o Gerador de Código de Barras

`BarcodeGenerator` é a classe central do Aspose.BarCode que cria e renderiza códigos de barras. Ela aceita o tipo de simbologia e o texto a ser codificado.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixEcc200:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Your code goes here
}
```

Substitua `"Your Directory Path"` pela pasta onde deseja salvar a imagem.

### Passo 2: Definir XDimension e Tipo ECC

`XDimension` define o tamanho em pixels de cada módulo DataMatrix, enquanto `DataMatrixEcc` seleciona o nível de correção de erro. ECC 200 oferece a maior capacidade de correção para esta simbologia.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 4;
gen.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

Ajuste o valor em pixels se precisar de módulos maiores ou menores; valores típicos são 4‑6 px para exibição na tela e 8‑10 px para rótulos impressos.

### Passo 3: Gerar e Salvar a Imagem do Código de Barras

O método `Save` grava o código de barras em um arquivo. Você pode escolher PNG, JPEG ou TIFF passando o valor enum correspondente `BarCodeImageFormat`.

```csharp
gen.Save($"{path}DataMatrixEcc200.png", BarCodeImageFormat.Png);
```

Altere `BarCodeImageFormat.Png` para `BarCodeImageFormat.Jpeg` ou `BarCodeImageFormat.Tiff` se seu fluxo de trabalho exigir um formato diferente.

## Problemas comuns e solução de problemas

| Sintoma | Causa provável | Correção |
|---------|----------------|----------|
| Código de barras aparece borrado | XDimension muito baixa | Aumente `XDimension.Pixels` para 6‑8 |
| Leitura falha em dispositivos móveis | Nível ECC incorreto | Garanta que `DataMatrixEcc = DataMatrixEccType.Ecc200` |
| Arquivo não criado | Cadeia de caminho inválida | Use um caminho absoluto ou verifique se a pasta existe |

## Perguntas Frequentes

**Q: Posso usar este código em uma aplicação console .NET Core?**  
A: Sim, a mesma API funciona em projetos .NET Core, .NET 5 e .NET 6.

**Q: Como altero o formato de saída para JPEG?**  
A: Substitua `BarCodeImageFormat.Png` por `BarCodeImageFormat.Jpeg` na chamada `Save`.

**Q: É possível incorporar o código de barras diretamente em um PDF?**  
A: Sim – gere a imagem primeiro, depois adicione-a a um PDF usando Aspose.PDF ou qualquer biblioteca PDF.

**Q: E se eu precisar codificar caracteres Unicode?**  
A: DataMatrix suporta UTF‑8; basta passar a string Unicode para o gerador conforme mostrado.

**Q: A biblioteca suporta geração em lote de múltiplos códigos de barras?**  
A: Absolutamente – coloque o código de geração dentro de um loop e altere os dados/valor a cada iteração.

## Conclusão

Cobrimos tudo o que você precisa para **criar código de barras DataMatrix** (ECC 200) com Aspose.BarCode para .NET: desde os pré-requisitos e importação de namespaces até a configuração da X‑dimension, seleção do nível ECC e salvamento da imagem no formato desejado. Experimente as diversas propriedades adicionais — como margem, cor de fundo e rotação — para ajustar a saída ao seu caso de uso específico.

Se você encontrar algum desafio, a comunidade está pronta para ajudar no [fórum Aspose.BarCode](https://forum.aspose.com/c/barcode/13). Boa codificação!

---

**Última atualização:** 2026-08-02  
**Testado com:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Como gerar códigos de barras DataMatrix ECC 000-140 com Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-000-140-configuration/)
- [Como ler códigos de barras DataMatrix com Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-reading/)
- [Criar Barcode PNG – Proporção de Aspecto DataMatrix – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}