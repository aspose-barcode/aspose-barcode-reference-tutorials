---
date: 2026-06-09
description: Aprenda como criar código de barras DataMatrix no modo ASCII usando Aspose.BarCode
  para .NET. Este guia mostra como gerar o código de barras em C# rapidamente.
keywords:
- create datamatrix barcode
- generate barcode c#
- how to encode barcode
- barcode generator example
linktitle: Modo de Codificação DataMatrix (ASCII)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  headline: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  name: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  steps:
  - name: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
    text: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
  - name: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
  - name: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
    text: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
  - name: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
    text: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
  type: HowTo
- questions:
  - answer: Yes, a valid Aspose license is required for production use; a free trial
      is available for evaluation.
    question: Can I use this in a commercial application?
  - answer: Absolutely – Aspose.BarCode fully supports .NET Core 3.1+, .NET 5, .NET
      6, and later versions.
    question: Does the library work with .NET Core?
  - answer: Up to 2,335 alphanumeric characters fit in a single DataMatrix symbol
      when using ASCII encoding.
    question: How many characters can I encode in ASCII mode?
  - answer: Yes, adjust `generator.Parameters.Image.ForeColor` and `BackColor` to
      any `System.Drawing.Color` value.
    question: Can I change the barcode’s foreground or background color?
  - answer: The official documentation contains dozens of samples covering custom
      sizes, colors, and error‑correction levels.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Criar código de barras DataMatrix no modo ASCII com Aspose.BarCode para .NET
url: /pt/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar código de barras DataMatrix em modo ASCII com Aspose.BarCode para .NET

## Introdução

Pronto para **criar imagens de código de barras DataMatrix** que utilizam a eficiente codificação ASCII? Neste tutorial você aprenderá como gerar um código de barras DataMatrix em modo ASCII usando Aspose.BarCode para .NET. Vamos percorrer cada passo — desde a configuração do projeto até a gravação da imagem final — para que você possa adicionar a geração de códigos de barras às suas aplicações C# em minutos.

## Respostas rápidas
- **Qual biblioteca é a melhor para DataMatrix em .NET?** Aspose.BarCode for .NET  
- **Quantas linhas de código são necessárias?** Cerca de 5‑7 linhas para um código de barras ASCII básico  
- **Preciso de uma licença?** Uma avaliação gratuita funciona para desenvolvimento; uma licença é necessária para produção  
- **Plataformas suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **Posso alterar tamanho ou cores?** Sim, Aspose.BarCode expõe propriedades para dimensões e cores de primeiro plano/fundo  

## O que é o código de barras DataMatrix?

DataMatrix é um código de barras bidimensional que armazena texto e dados binários em um padrão quadrado compacto.  
Um código de barras DataMatrix codifica informações em uma grade de módulos pretos e brancos, permitindo até 2.335 caracteres alfanuméricos em um único símbolo. É amplamente usado em manufatura, logística e saúde porque pode ser impresso em tamanhos muito pequenos mantendo alta legibilidade.

## Como criar um código de barras DataMatrix em modo ASCII?

Carregue o namespace Aspose.BarCode, instancie um `BarcodeGenerator`, defina o `EncodeMode` para **EncodeMode.ASCII**, atribua sua string de dados e chame `Save` para gravar o arquivo de imagem. Essa abordagem produz um código de barras DataMatrix perfeitamente compatível com codificação apenas ASCII em apenas algumas linhas de código C#.

## Por que usar codificação ASCII para DataMatrix?

O modo ASCII é a codificação padrão e mais eficiente para dados de texto simples, oferecendo o menor tamanho de símbolo possível para cadeias alfanuméricas. Ele suporta todos os 128 caracteres ASCII, processa os dados mais rapidamente que modos estendidos e garante máxima compatibilidade com scanners legados que esperam símbolos ASCII padrão.

## Pré-requisitos

1. **Ambiente de desenvolvimento** – Visual Studio, Rider ou qualquer IDE compatível com C#.  
2. **Aspose.BarCode for .NET** – Baixe o pacote mais recente de [aqui](https://releases.aspose.com/barcode/net/).  
   - Documentação: [documentação do Aspose.BarCode para .NET](https://reference.aspose.com/barcode/net/)  
   - Ajuda da comunidade: [fórum do Aspose.BarCode](https://forum.aspose.com/c/barcode/13)  
3. **Conhecimento básico de C#** – Familiaridade com a estrutura de projetos .NET ajudará a seguir os passos rapidamente.  
4. **Outros produtos Aspose** podem ser encontrados [aqui](https://releases.aspose.com/).

## Importar namespaces

Para começar, adicione as diretivas `using` necessárias no topo do seu arquivo C#:

```csharp
using Aspose.BarCode.Generation;
using System.Drawing;
```

Esses namespaces dão acesso à classe `BarcodeGenerator` e aos tipos relacionados a imagens necessários para salvar a saída.

## Etapa 1: Criar um diretório

Escolha uma pasta onde as imagens de código de barras geradas serão armazenadas. Substitua `"Your Directory Path"` por um caminho absoluto ou relativo que exista na sua máquina.

```csharp
string outputDir = @"C:\Barcodes";
if (!System.IO.Directory.Exists(outputDir))
{
    System.IO.Directory.CreateDirectory(outputDir);
}
```

O código garante que o diretório exista antes de tentar gravar quaisquer arquivos, evitando erros em tempo de execução.

## Etapa 2: Codificar dados em modo ASCII

A classe `BarcodeGenerator` cria e configura imagens de código de barras. A enumeração `DataMatrixEncodeMode` seleciona o algoritmo de codificação para símbolos DataMatrix.

```csharp
// Initialise the generator with the data you want to encode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "1234567890");

// Set the encoding mode to ASCII for optimal size
generator.Parameters.Barcode.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;

// Optional: adjust image dimensions or colors here
generator.Parameters.Image.Width = 200;
generator.Parameters.Image.Height = 200;

// Save the barcode as a PNG file
string filePath = System.IO.Path.Combine(outputDir, "datamatrix_ascii.png");
generator.Save(filePath, BarCodeImageFormat.Png);
```

Após executar o código, você encontrará `datamatrix_ascii.png` na pasta especificada. A imagem contém um código de barras DataMatrix que codifica a string `"1234567890"` usando o modo ASCII compacto.

## Problemas comuns e soluções

- **Erros de acesso a arquivos** – Certifique-se de que a aplicação tem permissão de gravação na pasta de destino. Executar o Visual Studio como Administrador pode resolver problemas de permissão no Windows.  
- **Tamanho do símbolo incorreto** – Se o código de barras aparecer muito grande ou muito pequeno, ajuste `generator.Parameters.Image.Width` e `Height` ou deixe o Aspose calcular automaticamente o tamanho ideal omitindo essas propriedades.  
- **Caracteres não suportados** – O modo ASCII aceita apenas caracteres no intervalo 0‑127. Para dados Unicode, altere para `DataMatrixEncodeMode.Base256` ou outro modo adequado.

## Perguntas Frequentes

**Q: Posso usar isso em uma aplicação comercial?**  
A: Sim, uma licença válida da Aspose é necessária para uso em produção; uma avaliação gratuita está disponível para avaliação.

**Q: A biblioteca funciona com .NET Core?**  
A: Absolutamente – Aspose.BarCode oferece suporte total ao .NET Core 3.1+, .NET 5, .NET 6 e versões posteriores.

**Q: Quantos caracteres posso codificar no modo ASCII?**  
A: Até 2.335 caracteres alfanuméricos cabem em um único símbolo DataMatrix ao usar codificação ASCII.

**Q: Posso alterar a cor de primeiro plano ou de fundo do código de barras?**  
A: Sim, ajuste `generator.Parameters.Image.ForeColor` e `BackColor` para qualquer valor `System.Drawing.Color`.

**Q: Onde posso encontrar exemplos mais avançados?**  
A: A documentação oficial contém dezenas de amostras que cobrem tamanhos personalizados, cores e níveis de correção de erro.

## Perguntas Frequentes

### Q1: Posso usar Aspose.BarCode para .NET com outras linguagens de programação além de C#?

A1: Aspose.BarCode suporta várias linguagens de programação, mas este tutorial foca em C#.

### Q2: Quais são os diferentes modos de codificação disponíveis em códigos de barras DataMatrix?

A2: Os códigos de barras DataMatrix suportam vários modos de codificação, incluindo ASCII, C40, Text e Base256. Cada modo é adequado para diferentes tipos de dados.

### Q3: Posso personalizar a aparência do código de barras gerado, como tamanho e cor?

A3: Sim, Aspose.BarCode oferece uma ampla gama de parâmetros para personalizar a aparência do código de barras, incluindo tamanho, cor e muito mais.

### Q4: Existe uma versão de avaliação gratuita do Aspose.BarCode para .NET?

A4: Sim, você pode explorar o Aspose.BarCode para .NET com uma avaliação gratuita de [aqui](https://releases.aspose.com/).

### Q5: Onde posso comprar uma licença para Aspose.BarCode para .NET?

A5: Você pode adquirir uma licença no site da Aspose [aqui](https://purchase.aspose.com/buy).

---

**Última atualização:** 2026-06-09  
**Testado com:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose

## Tutoriais Relacionados

- [Codificação DataMatrix em Bytes com Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [Ler código de barras DataMatrix C# – Gerar modo DataMatrix (Auto)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Como gerar códigos de barras DataMatrix (ECC 200) com Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.BarCode.Generation;
```

```csharp
string path = "Your Directory Path";
```

```csharp
System.Console.WriteLine("DataMatrixEncodeModeASCII:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    // Set the X-dimension (size) of the barcode in pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set the encoding mode to ASCII
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;
    
    // Save the barcode as a PNG image
    gen.Save($"{path}DataMatrixEncodeModeASCII.png", BarCodeImageFormat.Png);
}
```

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}