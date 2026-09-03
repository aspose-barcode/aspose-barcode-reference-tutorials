---
category: general
date: 2026-07-18
description: Crie códigos de barras PDF417 rapidamente com C#. Aprenda como gerar
  o código de barras, definir parâmetros e salvar arquivos de imagem – inclui o tratamento
  do AI 10.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate barcode
- how to set parameters
- how to save image
- barcode ai 10
language: pt
lastmod: 2026-07-18
og_description: Crie código de barras PDF417 em C# com um tutorial completo. Descubra
  como gerar o código de barras, ajustar as configurações e salvar imagens enquanto
  lida com AI 10.
og_image_alt: Screenshot illustrating create pdf417 barcode code in C#
og_title: Criar código de barras PDF417 em C# – Rápido, flexível, exemplo completo
  de código
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create PDF417 barcode quickly with C#. Learn how to generate barcode,
    set parameters, and save image files – includes AI 10 handling.
  headline: Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: Create PDF417 barcode quickly with C#. Learn how to generate barcode,
    set parameters, and save image files – includes AI 10 handling.
  name: Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  steps:
  - name: '**X‑dimension** – controls the width of the smallest bar (in pixels)'
    text: '**X‑dimension** – controls the width of the smallest bar (in pixels)'
  - name: '**Column count** – influences the overall shape; fewer columns = taller
      barcode'
    text: '**Column count** – influences the overall shape; fewer columns = taller
      barcode'
  - name: '**IsLinked** – enables the optional link module that ties the barcode to
      the data string'
    text: '**IsLinked** – enables the optional link module that ties the barcode to
      the data string'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspnet
- barcode-generation
title: Criar código de barras PDF417 em C# – Guia completo passo a passo
url: /pt/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Código de Barras PDF417 em C# – Guia Completo Passo a Passo

Já precisou **criar código de barras pdf417** mas não tinha certeza de qual biblioteca ou configuração escolher? Você não está sozinho—muitos desenvolvedores encontram esse obstáculo quando começam a brincar com GS1‑Micro‑PDF417. A boa notícia é que, com algumas linhas de C#, você pode gerar um código de barras perfeitamente formatado, ajustar sua aparência e salvar a imagem diretamente no disco.

Neste tutorial, vamos percorrer **como gerar código de barras** usando a biblioteca Aspose.BarCode, mostrar **como definir parâmetros** como X‑dimension e contagem de colunas, e demonstrar **como salvar imagem** arquivos para as variações AI 10 e AI 21. Ao final, você terá um trecho reutilizável que pode inserir em qualquer projeto .NET.

## Pré-requisitos

- .NET 6+ ou .NET Framework 4.7.2 (qualquer runtime recente funciona)
- Visual Studio 2022 ou seu editor C# favorito
- O pacote NuGet **Aspose.BarCode for .NET** (`Install-Package Aspose.BarCode`)
- Uma pasta gravável no disco onde os arquivos PNG serão salvos

É isso—nenhuma ferramenta extra, nenhuma configuração complexa. Pronto? Vamos lá.

## Etapa 1: Criar Código de Barras PDF417 com Formato GS1‑Micro

A primeira coisa que fazemos é **criar código de barras pdf417** e alimentá‑lo com os dados AI iniciais. No GS1‑Micro‑PDF417, o AI 10 (número de lote) costuma ser o ponto de partida, então o codificaremos imediatamente.

```csharp
using Aspose.BarCode.Generation;

// Define where the PNGs will be saved
string outputDir = @"C:\Barcodes\";

// Instantiate the generator for GS1‑Micro‑PDF417
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.GS1MicroPdf417,
    "(10)ABCD12345(240)ABCD");   // AI 10 + additional data
```

> **Por que isso importa:** O `EncodeTypes.GS1MicroPdf417` indica à biblioteca que siga a especificação GS1‑Micro, que adiciona automaticamente os colchetes do AI. Se você pular isso, acabará com um PDF417 genérico que pode não ser escaneável em ambientes de varejo.

## Etapa 2: Como Definir Parâmetros para o Código de Barras

Agora que temos uma instância de código de barras, precisamos ajustar finamente suas características visuais. É aqui que **como definir parâmetros** entra em ação. Ajustaremos três configurações comuns:

1. **X‑dimension** – controla a largura da barra mais fina (em pixels)
2. **Column count** – influencia a forma geral; menos colunas = código de barras mais alto
3. **IsLinked** – habilita o módulo de link opcional que liga o código de barras à string de dados

```csharp
// X‑dimension: 2 pixels per module (good balance of size vs readability)
barcode.Parameters.Barcode.XDimension.Pixels = 2;

// Columns: 3 columns makes the barcode compact yet readable
barcode.Parameters.Barcode.Pdf417.Columns = 3;

// Enable linking (adds a special pattern that some scanners use)
barcode.Parameters.Barcode.Pdf417.IsLinked = true;
```

> **Dica profissional:** Se você está visando a leitura móvel, aumente a X‑dimension para 3‑4 pixels; módulos maiores sobrevivem melhor a câmeras de baixa resolução.

## Etapa 3: Como Salvar Imagem – Primeira Versão (AI 10)

Com o gerador configurado, finalmente podemos **como salvar imagem**. O método `Save` grava o código de barras em um arquivo no formato que você especificar. Aqui usamos PNG porque preserva bordas nítidas sem artefatos de compressão.

```csharp
// Save the barcode that encodes AI 10
barcode.Save($"{outputDir}GS1MicroPdf417_AI10.png", BarCodeImageFormat.Png);
```

Neste ponto, você deve ver um arquivo chamado `GS1MicroPdf417_AI10.png` em seu `outputDir`. Abra‑o com qualquer visualizador de imagens—você verá um PDF417 limpo e de alto contraste pronto para impressão.

## Etapa 4: Trocar para um AI Diferente (AI 21) e Salvar Novamente

Frequentemente você precisa codificar um identificador de aplicação diferente, como AI 21 (número de série). Alterar a propriedade `CodeText` é tudo o que é necessário. Isso demonstra o tratamento de **código de barras ai 10** versus **código de barras ai 21** em uma única operação.

```csharp
// Change the encoded data – now using AI 21
barcode.CodeText = "(21)ABCD12345(240)ABCD";

// Save the new variant
barcode.Save($"{outputDir}GS1MicroPdf417_AI21.png", BarCodeImageFormat.Png);
```

> **E se precisar de mais AIs?** Basta concatená‑los na mesma string, por exemplo, `"(10)ABCD(21)12345(240)XYZ"`. A biblioteca analisa os colchetes automaticamente.

## Exemplo Completo Funcional

Juntando tudo, aqui está um programa autônomo que você pode copiar e colar em um aplicativo console:

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Output folder – change to suit your environment
        string outputDir = @"C:\Barcodes\";

        // 2️⃣ Create generator with initial AI 10 data
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.GS1MicroPdf417,
            "(10)ABCD12345(240)ABCD");

        // 3️⃣ Set visual parameters
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // how to set parameters
        barcode.Parameters.Barcode.Pdf417.Columns = 3;
        barcode.Parameters.Barcode.Pdf417.IsLinked = true;

        // 4️⃣ Save first image (AI 10)
        barcode.Save($"{outputDir}GS1MicroPdf417_AI10.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved AI 10 barcode.");

        // 5️⃣ Switch to AI 21 and save second image
        barcode.CodeText = "(21)ABCD12345(240)ABCD";
        barcode.Save($"{outputDir}GS1MicroPdf417_AI21.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved AI 21 barcode.");
    }
}
```

**Saída esperada:** Dois arquivos PNG aparecem em `C:\Barcodes\`—`GS1MicroPdf417_AI10.png` e `GS1MicroPdf417_AI21.png`. Ambos contêm um PDF417 escaneável; o primeiro codifica AI 10, o segundo AI 21.

## Armadilhas Comuns & Como Evitá‑las

- **Permissões de pasta ausentes:** Se o `Save` lançar uma `UnauthorizedAccessException`, verifique novamente se o caminho existe e se seu aplicativo tem permissões de escrita.
- **Formatação de AI incorreta:** Esquecer os parênteses (`(10)`) fará com que o código de barras seja tratado como dados simples, quebrando a validação GS1.
- **X‑dimension muito pequena:** Barras mais finas que 1 pixel podem desaparecer quando a imagem for redimensionada. Mantenha pelo menos 2 pixels para exibição em tela.

## Próximos Passos & Tópicos Relacionados

Agora que você sabe **como gerar código de barras**, **como definir parâmetros** e **como salvar imagem**, talvez queira explorar:

- Adicionar **human‑readable text** abaixo do código de barras (`barcode.Parameters.Barcode.CodeTextLocation = CodeLocation.BelowBarcode`)
- Exportar para **PDF** em vez de PNG (`BarCodeImageFormat.Pdf`)
- Integrar a geração de código de barras em uma **ASP.NET Core API** para criação de imagens sob demanda

Cada um desses tópicos se baseia diretamente na fundação que apresentamos neste guia.

---

### Resumo Rápido

- **Criar código de barras pdf417** usando `BarcodeGenerator` com `EncodeTypes.GS1MicroPdf417`
- **Como definir parâmetros** como X‑dimension, colunas e linking
- **Como salvar imagem** como PNG para as variantes AI 10 e AI 21
- Manipulado **código de barras ai 10** e trocado para **código de barras ai 21** com uma única alteração de propriedade

Experimente, ajuste as configurações, e você terá um motor de código de barras robusto pronto para produção. Tem perguntas ou precisa de um mergulho mais profundo? Deixe um comentário abaixo—bom código!

## O Que Você Deve Aprender a Seguir?

Os tutoriais a seguir cobrem tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como Criar Código de Barras – PDF417 Compacto com Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Como Criar Zona Silenciosa de Código de Barras para ITF-14 Usando Aspose.BarCode para .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Como criar código de barras Aztec com correção de erro em .NET](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}