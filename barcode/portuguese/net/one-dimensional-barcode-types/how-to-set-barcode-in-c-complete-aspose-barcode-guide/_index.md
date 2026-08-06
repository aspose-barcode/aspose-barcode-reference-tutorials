---
category: general
date: 2026-08-06
description: Como definir o código de barras usando Aspose.BarCode em C#. Aprenda
  a alterar caracteres macro e criar imagem de código de barras em C# com código passo
  a passo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- how to change macro
- barcode generator c#
- create barcode image c#
language: pt
lastmod: 2026-08-06
og_description: Como definir código de barras com Aspose.BarCode em C#. Este guia
  mostra como alterar caracteres macro e criar rapidamente uma imagem de código de
  barras em C#.
og_image_alt: Screenshot of a MicroPDF417 barcode generated with C# code
og_title: Como definir código de barras em C# – tutorial Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: How to set barcode using Aspose.BarCode in C#. Learn how to change
    macro characters and create barcode image C# with step‑by‑step code.
  headline: How to set barcode in C# – complete Aspose.BarCode guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Como definir código de barras em C# – guia completo do Aspose.BarCode
url: /pt/net/one-dimensional-barcode-types/how-to-set-barcode-in-c-complete-aspose-barcode-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como definir código de barras em C# – guia completo do Aspose.BarCode

Se você precisa **definir código de barras** em uma aplicação .NET, este tutorial mostra os passos exatos usando Aspose.BarCode. Você verá como alterar caracteres macro, ajustar parâmetros visuais e **criar arquivos de imagem de código de barras C#** que podem ser salvos diretamente no disco.

O guia cobre tudo, desde a instalação da biblioteca até a geração de dois códigos MicroPDF417 com valores macro diferentes. Nenhuma documentação externa é necessária—você pode copiar o código, executá‑lo e verificar a saída PNG imediatamente.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 ou superior (o exemplo usa um projeto de console)
* Visual Studio 2022 ou qualquer IDE C#
* Uma licença ativa do Aspose.BarCode (uma avaliação gratuita funciona para testes)
* Conhecimento básico de sintaxe C#

Você também precisará do pacote NuGet:

```bash
dotnet add package Aspose.BarCode
```

## Como definir parâmetros do código de barras – passo 1: criar o gerador

A primeira ação é instanciar um `BarcodeGenerator` com a simbologia e os dados desejados. Usar `EncodeTypes.MicroPdf417` indica ao Aspose.BarCode que ele deve produzir uma variante compacta do PDF417.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Step 1: Create a MicroPDF417 barcode generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417, // symbology
                "12345ABC");             // data to encode
```

**Por que isso importa:** `BarcodeGenerator` é o objeto central; todas as configurações posteriores modificam sua propriedade `Parameters`. Selecionar o `EncodeTypes` correto garante que o código de barras siga a especificação MicroPDF417.

## Como alterar caracteres macro – passo 2: ajustar parâmetros visuais

Os caracteres macro são códigos de controle opcionais que permitem concatenar vários símbolos PDF417. O exemplo alterna entre `Macro05` e `Macro06`. Você também define a largura do módulo (`XDimension`) e o número de colunas para controlar o tamanho do código de barras.

```csharp
            // Step 2: Adjust visual parameters – set the X‑dimension (module width) and number of columns
            generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width in pixels
            generator.Parameters.Barcode.Pdf417.Columns = 4;           // number of data columns

            // Encode the first macro character (Macro05) and save the image
            generator.Parameters.Barcode.Pdf417.MacroCharacters = MacroCharacter.Macro05;
            generator.Save("MicroPdf417_Macro05.png", BarCodeImageFormat.Png);
```

**Por que você altera o macro:** O caractere macro informa ao scanner que este código de barras faz parte de um conjunto de dados maior. Alterná‑lo demonstra como os mesmos dados podem ser vinculados a diferentes identificadores macro.

## Como definir código de barras – passo 3: gerar um segundo código com macro diferente

Agora reutilizamos a mesma instância `generator`, apenas trocando o valor do macro. Isso evita recriar o objeto e demonstra que **definir código de barras** pode ser feito em tempo de execução.

```csharp
            // Step 3: Switch to the second macro character (Macro06) and save the new image
            generator.Parameters.Barcode.Pdf417.MacroCharacters = MacroCharacter.Macro06;
            generator.Save("MicroPdf417_Macro06.png", BarCodeImageFormat.Png);
        }
    }
}
```

### Saída esperada

Ao executar o programa, são criados dois arquivos PNG na pasta do projeto:

* `MicroPdf417_Macro05.png` – código de barras com Macro05
* `MicroPdf417_Macro06.png` – código de barras com Macro06

Ambas as imagens exibem um símbolo compacto MicroPDF417 que codifica `12345ABC`. Você pode abrir os arquivos PNG com qualquer visualizador de imagens para verificar a qualidade visual.

## Boas práticas para o gerador de código de barras C#

* **Reutilize o gerador:** Alterar `Parameters` em uma instância existente é mais eficiente do que criar um novo gerador para cada código.
* **Defina a X‑dimension cedo:** A largura do módulo influencia o tamanho geral da imagem; ajuste‑a antes de salvar.
* **Valide o uso de macro:** Nem todos os scanners suportam caracteres macro. Teste com o hardware alvo se pretender usá‑los em produção.
* **Libere recursos:** `BarcodeGenerator` implementa `IDisposable`. Em um serviço de longa duração, envolva‑o em um bloco `using` ou chame `Dispose()` quando terminar.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "12345ABC"))
{
    // configure parameters...
}
```

## Criar imagem de código de barras C# – dicas de solução de problemas

| Sintoma                              | Causa provável                              | Solução |
|--------------------------------------|---------------------------------------------|---------|
| Arquivo PNG em branco                | `XDimension` definido como 0 ou valor muito alto | Use uma largura de pixel razoável (1‑5) |
| Código de barras ilegível pelo scanner | Caractere macro incorreto para o scanner   | Verifique a documentação do scanner; use `MacroNone` se não for necessário |
| Exceção `ArgumentOutOfRangeException` | Contagem de colunas fora do intervalo permitido (1‑30) | Mantenha `Columns` entre 1 e 30 |

## Conclusão

Agora você sabe **como definir código de barras**, **como alterar caracteres macro** e como **criar arquivos de imagem de código de barras C#** usando Aspose.BarCode. O exemplo completo e executável demonstra todo o fluxo de trabalho, desde a criação do gerador até a exportação da imagem.

Em seguida, explore outras simbologias (`EncodeTypes.QR`, `EncodeTypes.Code128`) ou incorpore o código de barras diretamente em PDFs com Aspose.PDF. Ambos os tópicos fazem parte do ecossistema mais amplo de **gerador de código de barras c#** e podem ser adicionados a este projeto com alterações mínimas de código.

Boa codificação e sinta‑se à vontade para experimentar diferentes valores macro, dimensões e formatos de saída!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to create barcode quiet zone for Code 16K using Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [How to create dotcode extended codetext with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [How to Set Border for ITF-14 Barcode Customization](/barcode/english/net/itf-14-barcode-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}