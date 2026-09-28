---
category: general
date: 2026-07-18
description: Crie imagens de código de barras GS1 em C# com este guia passo a passo
  sobre como gerar código de barras C# usando Aspose.BarCode – sem enrolação, apenas
  código funcional.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create gs1 barcode images
- how to generate barcode c#
language: pt
lastmod: 2026-07-18
og_description: Crie imagens de código de barras GS1 em C# com este tutorial conciso.
  Aprenda como gerar códigos de barras em C# usando Aspose.BarCode e salvar arquivos
  PNG em segundos.
og_image_alt: Screenshot of a generated GS1‑MicroPDF417 barcode saved as a PNG file
og_title: Crie Imagens de Código de Barras GS1 em C# – Guia Completo Passo a Passo
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create GS1 barcode images in C# with this step‑by‑step guide on how
    to generate barcode C# using Aspose.BarCode – no fluff, just working code.
  headline: Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly
  type: TechArticle
tags:
- barcode
- csharp
- gs1
- aspose
title: Criar imagens de código de barras GS1 em C# – Como gerar código de barras em
  C# rapidamente
url: /pt/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Imagens de Código de Barras GS1 em C# – Como Gerar Código de Barras C#

Já precisou **criar imagens de código de barras gs1** para uma etiqueta de embalagem, mas não sabia por onde começar? Você não está sozinho. Neste tutorial você verá exatamente **como gerar código de barras c#** que produz imagens GS1‑MicroPDF417 em questão de minutos.

Vamos percorrer todo o processo — instalar a biblioteca, configurar o gerador, trocar os dados AI (Application Identifier) e, finalmente, salvar um conjunto de arquivos PNG. Ao final, você terá um aplicativo console pronto‑para‑executar que gera um conjunto de imagens de código de barras GS1, cada uma refletindo uma combinação diferente de AI.

---

## O que você precisará

- **.NET 6+** (ou .NET Framework 4.6+). O runtime mais recente funciona melhor com Aspose.BarCode.
- **Aspose.BarCode for .NET** – instale via NuGet (`Install-Package Aspose.BarCode`).
- Uma pasta no disco onde os arquivos PNG serão gravados (chamaremos de `YOUR_DIRECTORY`).
- Um entendimento básico da sintaxe C# — nada sofisticado é necessário.

Se você já tem isso, ótimo. Caso contrário, obtenha o pacote NuGet primeiro; é uma única linha no Package Manager Console e cuida de todas as dependências.

---

## Etapa 1: Configurar um Projeto Console Minimalista

Abra sua IDE favorita (Visual Studio, Rider ou VS Code) e crie um novo projeto console:

```bash
dotnet new console -n Gs1BarcodeDemo
cd Gs1BarcodeDemo
dotnet add package Aspose.BarCode
```

Substitua o `Program.cs` gerado automaticamente pelo código mostrado nas próximas etapas. Este esqueleto nos dá uma base limpa para **criar imagens de código de barras gs1** sem excessos.

---

## Etapa 2: Como criar imagens de código de barras gs1 – Inicializar o Gerador

O núcleo da operação é `BarcodeGenerator`. Iniciaremos com um valor inicial GS1‑MicroPDF417, por exemplo `(17)991231(10)ABCD`. Essa string codifica dois AIs: data de validade (17) e lote (10).

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with a GS1‑MicroPDF417 barcode type
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.GS1MicroPdf417,
            "(17)991231(10)ABCD");
```

**Por que isso importa:** O `EncodeTypes.GS1MicroPdf417` indica ao Aspose que estamos lidando com um formato GS1 compacto e de alta densidade. Começar com uma string AI válida garante que o primeiro PNG que salvamos já esteja em conformidade com os padrões GS1.

---

## Etapa 3: Ajustar Parâmetros Visuais – Afinar Tamanho e Layout

Um código de barras muito pequeno ou com forma estranha não será lido. Aqui definimos a X‑dimension (largura do módulo) para 2 pixels, limitamos o número de colunas para manter a imagem estreita e habilitamos o linking para que múltiplos códigos de barras possam ser concatenados posteriormente, se necessário.

```csharp
        // Set visual parameters for a crisp, scannable image
        barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;      // module width
        barcodeGen.Parameters.Barcode.Pdf417.Columns = 2;        // column count
        barcodeGen.Parameters.Barcode.Pdf417.IsLinked = true;   // enable linking
```

**Dica:** Se precisar de um código de barras mais alto, aumente `Rows` em vez de colunas. Brinque com `XDimension` para atender ao tamanho mínimo de módulo de 0,33 mm exigido pela maioria dos scanners.

---

## Etapa 4: Salvar o Primeiro Código de Barras – AI 17 + AI 10

Agora realmente gravamos a imagem no disco. O nome do arquivo reflete os AIs usados, facilitando a localização posterior.

```csharp
        // Save the first image (AI 17 + AI 10)
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_17_10.png",
                        BarCodeImageFormat.Png);
```

Depois de executar o programa, você deverá ver um PNG nítido em `YOUR_DIRECTORY`. Abra‑o — você verá as barras pequenas e o texto legível abaixo. Essa é a primeira de muitas **imagens de código de barras gs1** que vamos gerar.

---

## Etapa 5: Alterar os Dados Codificados – Reutilizar o Mesmo Gerador

Em vez de criar um novo `BarcodeGenerator` para cada par de AI, simplesmente trocamos a propriedade `CodeText` e chamamos `Save` novamente. Essa abordagem é a maneira mais eficiente de **criar imagens de código de barras gs1** em massa.

```csharp
        // AI 15 (best before) + AI 10 (batch)
        barcodeGen.CodeText = "(15)991231(10)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_15_10.png",
                        BarCodeImageFormat.Png);

        // AI 13 (production date) + AI 21 (serial)
        barcodeGen.CodeText = "(13)991231(21)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_13_21.png",
                        BarCodeImageFormat.Png);

        // AI 11 (manufacture date) + AI 21 (serial)
        barcodeGen.CodeText = "(11)991231(21)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_11_21.png",
                        BarCodeImageFormat.Png);

        // Only AI 17 (expiration) – no batch number
        barcodeGen.CodeText = "(17)991231";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_17.png",
                        BarCodeImageFormat.Png);
```

**Por que reutilizar?** Alterar `CodeText` evita a sobrecarga de reinstanciar o gerador e garante configurações visuais consistentes em todas as imagens.

---

## Etapa 6: Executar, Verificar e Ajustar

Compile e execute:

```bash
dotnet run
```

Agora você deve ter cinco arquivos PNG, cada um nomeado de acordo com o par de AI que contém. Abra qualquer um deles com um visualizador de imagens; você verá o código de barras e o texto codificado abaixo. Para confirmar que os dados estão corretos, use um aplicativo gratuito de scanner GS1 no seu telefone — aponte para o PNG na tela e veja os valores de AI aparecerem.

**Problemas comuns & como evitá‑los**

| Problema | Causa | Solução |
|----------|-------|--------|
| Código de barras ilegível | `XDimension` muito baixo (ex.: 1 pixel) | Aumente para 2 ou 3 pixels |
| Colchetes AI ausentes | Formato incorreto de `CodeText` | Sempre envolva cada AI entre parênteses |
| Imagem muito grande | Muitas colunas/linhas | Reduza `Columns` ou deixe o Aspose dimensionar automaticamente |
| Erro de tempo de execução `EncodeTypes` não encontrado | Falta `using Aspose.BarCode.Generation` | Adicione a diretiva `using` ausente |

---

## Etapa 7: Estendendo o Exemplo – Gerando Mais Combinações de AI

Se precisar **criar imagens de código de barras gs1** para dezenas de variantes de produto, considere carregar pares de AI a partir de um arquivo CSV:

```csharp
using System.IO;

string[] lines = File.ReadAllLines(@"ai_pairs.csv"); // format: "(17)991231,(10)ABCD"
foreach (var line in lines)
{
    barcodeGen.CodeText = line.Replace(',', ' ');
    string fileName = $"GS1MicroPdf417_{line.Replace("(", "").Replace(")", "").Replace(",", "_")}.png";
    barcodeGen.Save(Path.Combine(@"YOUR_DIRECTORY", fileName), BarCodeImageFormat.Png);
}
```

Este pequeno loop lê cada linha, troca os dados e salva um PNG com um nome descritivo — perfeito para pipelines de impressão de etiquetas em grande escala.

---

## Conclusão

Agora você tem um programa C# completo e pronto‑para‑executar que **cria imagens de código de barras gs1** para múltiplos cenários de AI, demonstrando a forma mais direta de **como gerar código de barras c#** usando Aspose.BarCode. Reutilizando uma única instância de `BarcodeGenerator`, ajustando parâmetros visuais e trocando `CodeText`, você pode gerar quantos PNGs compatíveis GS1‑MicroPDF417 seu projeto precisar.

Qual o próximo passo? Experimente adicionar cores (`barcodeGen.Parameters.Barcode.ForeColor`), incorporar o código de barras em um PDF ou mudar para outra simbologia GS1 como DataMatrix. O mesmo padrão se aplica — inicializar, configurar, definir `CodeText` e salvar.

Sinta‑se à vontade para deixar um comentário se encontrar algum problema, ou compartilhar suas próprias variações. Boa codificação, e que seus scans estejam sempre limpos!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como criar zona silenciosa de código de barras para Code 16K usando Aspose.BarCode para .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Como criar zona silenciosa de código de barras para ITF-14 usando Aspose.BarCode para .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Como gerar código de barras – Configuração Code 39 com Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}