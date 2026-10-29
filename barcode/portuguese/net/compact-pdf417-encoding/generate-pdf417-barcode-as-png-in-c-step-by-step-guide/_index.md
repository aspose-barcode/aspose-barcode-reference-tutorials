---
category: general
date: 2026-10-28
description: Gere código de barras PDF417 em C# e exporte-o como imagem PNG. Aprenda
  a configurar o layout, definir colunas e linhas e salvar o arquivo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- barcode generator PNG
- how to set PDF417
- how to generate PNG barcode
- how to configure PDF417 barcode
language: pt
lastmod: 2026-10-28
og_description: Gere código de barras PDF417 em C# e salve-o como uma imagem PNG.
  Siga este guia completo para configurar o layout, definir colunas e linhas e produzir
  um arquivo de código de barras de alta qualidade.
og_image_alt: Screenshot of a generated PDF417 barcode saved as a PNG file
og_title: Gerar código de barras PDF417 como PNG – tutorial C#
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Generate PDF417 barcode in C# and export it as a PNG image. Learn how
    to configure layout, set columns and rows, and save the file.
  headline: Generate PDF417 barcode as PNG in C# – step‑by‑step guide
  type: TechArticle
tags:
- C#
- PDF417
- barcode
- image generation
title: Gerar código de barras PDF417 como PNG em C# – guia passo a passo
url: /pt/net/compact-pdf417-encoding/generate-pdf417-barcode-as-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerar código de barras PDF417 como PNG em C# – guia passo a passo

Se você precisa **gerar código de barras PDF417** em uma aplicação .NET, este guia mostra exatamente como criar o código de barras e salvá‑lo como uma imagem PNG. Você aprenderá como configurar o layout do código de barras, definir o número de colunas e linhas, e produzir um arquivo que pode ser usado em inventário, bilhetagem ou cenários de escaneamento móvel.

O tutorial cobre tudo, desde a instalação da biblioteca necessária até o tratamento de casos extremos, como valores de layout inválidos. Nenhuma documentação externa é necessária — basta copiar o código, executá‑lo e você terá uma imagem de código de barras pronta para uso.

## Pré-requisitos

* .NET 6.0 SDK ou posterior instalado  
* Um ambiente de desenvolvimento C# (Visual Studio, VS Code ou Rider)  
* Acesso à internet para baixar o pacote NuGet **Aspose.BarCode for .NET** (a biblioteca usada nos exemplos)  

Esses requisitos garantem que o código compile e execute sem configuração adicional.

## Etapa 1: Instalar a biblioteca de código de barras

A maneira mais direta de obter a capacidade de **gerador de código de barras PNG** é usar o pacote oficial Aspose.BarCode. Abra um terminal na pasta do seu projeto e execute:

```bash
dotnet add package Aspose.BarCode
```

O comando adiciona a biblioteca e suas dependências ao seu arquivo de projeto. Após a instalação ser concluída, você pode referenciar as classes nos seus arquivos fonte C#.

## Etapa 2: Criar um gerador de código de barras PDF417

Criar o objeto do código de barras é a base do processo. O trecho a seguir cria um gerador que codifica o texto `"Sample"` usando a simbologia PDF417.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for PDF417
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");
```

*Por que esta etapa importa* – A classe `BarcodeGenerator` encapsula todas as configurações necessárias para a renderização. Ao especificar `EncodeTypes.Pdf417`, você indica à biblioteca que ela deve produzir um **código de barras PDF417**, que é um código linear empilhado ideal para armazenar grandes quantidades de dados.

## Etapa 3: Como definir colunas e linhas do PDF417

Um código de barras PDF417 pode ser personalizado ajustando sua matriz. Os dois parâmetros mais comuns são **colunas** (módulos horizontais) e **linhas** (módulos verticais). Controlar esses valores influencia o tamanho e a legibilidade do código de barras.

```csharp
        // Step 3: Configure a custom layout – set columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4; // allowed range: 2‑30
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // allowed range: 1‑90
```

### Como configurar o código de barras PDF417 para dimensões específicas

* Use valores dentro dos intervalos documentados; números fora do intervalo geram uma exceção.  
* Um número maior de colunas comprime o código de barras horizontalmente, enquanto mais linhas aumentam a altura vertical.  
* Ajuste o layout para corresponder à superfície de impressão alvo ou à distância de escaneamento.

Se precisar de uma forma diferente, altere os números conforme necessário. A biblioteca recalcula automaticamente o tamanho dos módulos para manter o código de barras legível.

## Etapa 4: Como gerar código de barras PNG

Salvar o código de barras como um arquivo PNG é uma operação de uma única linha assim que o gerador está totalmente configurado. PNG oferece compressão sem perdas, tornando‑o ideal para imagens de código de barras nítidas.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        generator.Save("CustomLayout.png", BarCodeImageFormat.Png);
    }
}
```

*Por que PNG* – O enum `BarCodeImageFormat.Png` indica à biblioteca que o código de barras deve ser renderizado no formato PNG. Esse formato preserva bordas nítidas, o que é essencial para leitores de código de barras que dependem de bordas de alto contraste.

### Saída esperada

Executar o programa cria um arquivo chamado **CustomLayout.png** no diretório de trabalho da aplicação. Ao abrir o arquivo, você verá um código de barras PDF417 retangular com quatro colunas e nove linhas, codificando a string `"Sample"`.

![Gerar código de barras PDF417 como PNG](https://example.com/images/pdf417-custom.png "Gerar código de barras PDF417 como PNG")

*Texto alternativo da imagem*: **Gerar código de barras PDF417 como PNG** – uma imagem de código de barras produzida pelo código do tutorial.

## Etapa 5: Verificar o código de barras e solucionar problemas comuns

Depois de gerar a imagem, você deve verificar se um scanner ou uma ferramenta de validação conseguem lê‑la. Aqui estão algumas verificações rápidas:

| Problema | Causa | Correção |
|----------|-------|----------|
| Código de barras está borrado | Imagem foi redimensionada após a geração | Mantenha o tamanho original do PNG; evite redimensionamento nos controles de UI |
| Leitor relata “dados inválidos” | Colunas/linhas fora do intervalo ou dados muito longos para o layout escolhido | Reduza a quantidade de texto codificado ou aumente linhas/colunas |
| Arquivo PNG está vazio | `generator.Save` aponta para um diretório inexistente | Garanta que o diretório exista ou use um caminho absoluto |

**Dica profissional:** Quando precisar de fundo transparente (por exemplo, sobrepor o código de barras a um elemento de UI), defina `generator.Parameters.Image.TransparentBackground = true;` antes de chamar `Save`.

## Exemplo completo em funcionamento

Abaixo está o programa completo que você pode copiar, colar e executar sem modificações (exceto o caminho de saída, se desejar).

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the generator for PDF417 with sample data
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");

        // Configure custom layout – set columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4; // 2‑30
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // 1‑90

        // Optional: make background transparent
        generator.Parameters.Image.TransparentBackground = true;

        // Save the barcode as a PNG file
        string outputPath = "CustomLayout.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode saved to {outputPath}");
    }
}
```

Executar o programa exibe uma mensagem de confirmação e produz `CustomLayout.png` na mesma pasta do executável.

## Conclusão

Agora você sabe como **gerar código de barras PDF417** em C#, configurar seu layout com colunas e linhas específicas e exportar o resultado como uma imagem **código de barras PNG**. As etapas cobriram a instalação da biblioteca Aspose.BarCode, a inicialização do gerador, a aplicação de dimensões personalizadas, a gravação do arquivo e a verificação da saída.

A partir daqui, você pode explorar configurações adicionais, como nível de correção de erro, margens do código de barras ou incorporação da imagem diretamente em um relatório PDF. Cada um desses tópicos se baseia no padrão central demonstrado neste guia, de modo que você está pronto para adaptar a solução a qualquer cenário de geração de código de barras .NET.

---

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como gerar código de barras PDF417 – Guia completo de programação](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)
- [Como gerar código de barras PDF417 em C# e definir o tamanho do código de barras](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/)
- [Como gerar código de barras PDF417 com Aspose – Guia completo](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}