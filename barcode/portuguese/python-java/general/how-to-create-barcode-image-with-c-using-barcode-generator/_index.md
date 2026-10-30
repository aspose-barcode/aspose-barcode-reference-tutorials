---
category: general
date: 2026-10-28
description: Crie imagem de código de barras em C# rapidamente. Aprenda a usar o gerador
  de código de barras em C#, como definir o tamanho dos pixels e como alterar a proporção
  para DataBar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- how to set pixel size
- how to change aspect ratio
- how to generate databar
language: pt
lastmod: 2026-10-28
og_description: Crie uma imagem de código de barras em C# com um Gerador de Código
  de Barras. Siga este guia para definir o tamanho dos pixels, alterar a proporção
  e gerar códigos de barras DataBar.
og_image_alt: Screenshot of a generated barcode image created with C#
og_title: Criar imagem de código de barras em C# – guia passo a passo
schemas:
- author: GroupDocs
  dateModified: '2026-10-28'
  description: Create barcode image in C# quickly. Learn barcode generator c# usage,
    how to set pixel size, and how to change aspect ratio for DataBar.
  headline: How to create barcode image with C# using Barcode Generator
  type: TechArticle
tags:
- barcode
- C#
- imaging
title: Como criar imagem de código de barras com C# usando o Gerador de Código de
  Barras
url: /pt/python-java/general/how-to-create-barcode-image-with-c-using-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar imagem de código de barras com C# usando o Barcode Generator

Se você precisa **criar imagem de código de barras** em uma aplicação .NET, este guia mostra exatamente como fazer. Você verá um exemplo completo e executável que usa a biblioteca Barcode Generator C# para gerar um código de barras DataBar stacked omnidirectional, definir o tamanho em pixels e alterar a proporção.

Gerar códigos de barras programaticamente elimina a necessidade de ferramentas externas e permite incorporar a imagem diretamente em PDFs, relatórios ou controles de UI. Nas etapas abaixo também abordamos **como definir o tamanho em pixels** e **como alterar a proporção**, duas exigências comuns quando se precisa de um código de barras nítido e dimensionado corretamente.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 SDK ou posterior instalado  
* Uma IDE compatível com C# (Visual Studio, Rider ou VS Code)  
* O pacote NuGet `BarcodeGenerator` (por exemplo, `GroupDocs.Barcode` ou `Aspose.Barcode`) instalado no seu projeto  

Você pode adicionar o pacote com o seguinte comando:

```bash
dotnet add package GroupDocs.Barcode
```

> **Dica profissional:** Verifique se a versão do pacote corresponde ao seu framework de destino para evitar incompatibilidades em tempo de execução.

## Criar imagem de código de barras com Barcode Generator C#

A primeira etapa é instanciar o gerador com o tipo de código de barras e os dados desejados. O exemplo abaixo cria um código de barras **DataBar stacked omnidirectional**, ideal para cenários de leitura no varejo.

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // Step 1: Create a BarcodeGenerator for DataBar stacked omnidirectional
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example data

        // Step 2: Set the pixel size of the X‑dimension (how to set pixel size)
        barcode.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 3: Save an image with the first aspect ratio (how to generate databar)
        barcode.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcode.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // Step 4: Change the aspect ratio (how to change aspect ratio) and save a second image
        barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcode.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### Por que cada linha importa

* **Instanciar `BarcodeGenerator`** – O construtor recebe uma simbologia de código de barras (`EncodeTypes.DatabarStackedOmniDirectional`) e a string de dados bruta. Escolher a simbologia correta garante que o scanner consiga ler o código.  
* **Definir `XDimension.Pixels`** – Esta propriedade controla a largura do menor elemento de barra. Um valor de `2` produz uma imagem de alta granularidade que permanece legível na maioria das telas. Aumente se precisar de um código de barras maior para impressoras de baixa resolução.  
* **Configurar `AspectRatio`** – A família DataBar suporta várias proporções que afetam a relação altura‑largura. Os valores `15` e `30` são comuns; `15` gera um código mais curto, enquanto `30` produz um mais alto.  
* **Método `Save`** – Salva o código de barras gerado em um arquivo PNG. Você pode substituir `BarCodeImageFormat.Png` por `Jpeg` ou `Bmp` se o seu sistema downstream exigir outro formato.

## Como definir o tamanho em pixels para diferentes contextos de renderização

O tamanho em pixels determina a densidade visual do código de barras. Se o código será exibido em um monitor de alta DPI, pode‑se aumentar o tamanho para `3` ou `4`. Por outro lado, para impressoras térmicas de baixa resolução, um tamanho menor (por exemplo, `1`) reduz o consumo de tinta.

```csharp
// Example: increase pixel size for a high‑resolution display
barcode.Parameters.Barcode.XDimension.Pixels = 4;
```

**Caso extremo:** Definir o tamanho em pixels muito baixo (< 1) lança uma `ArgumentOutOfRangeException`. Sempre valide o valor antes de atribuí‑lo.

## Como alterar a proporção sem recriar o gerador

Alterar a proporção é uma simples atualização de propriedade; você **não** precisa recriar a instância `BarcodeGenerator`. Isso economiza memória e melhora o desempenho quando for necessário gerar várias imagens com formas diferentes.

```csharp
// Switch from a short to a tall barcode
barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
barcode.Save("TallDatabar.png", BarCodeImageFormat.Png);
```

Se precisar de mais de duas proporções, pode percorrer um array:

```csharp
int[] ratios = { 15, 20, 25, 30 };
foreach (int ratio in ratios)
{
    barcode.Parameters.Barcode.DataBar.AspectRatio = ratio;
    string fileName = $"DatabarAspectRatio{ratio}.png";
    barcode.Save(fileName, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {fileName}");
}
```

## Saída esperada

Ao executar o programa, são criados dois arquivos PNG (ou mais, se usar o loop). Abra‑os em qualquer visualizador de imagens; você deverá ver um código DataBar limpo:

* **DatabarAspectRatio15.png** – código curto e largo, adequado para espaços de etiqueta estreitos.  
* **DatabarAspectRatio30.png** – código mais alto, que melhora a confiabilidade da leitura em scanners angulados.

Ambas as imagens compartilham o mesmo tamanho em pixels (2 px por módulo) mas diferem apenas na altura, demonstrando **como alterar a proporção** mantendo os demais parâmetros constantes.

## Armadilhas comuns e como evitá‑las

| Sintoma | Causa | Solução |
|---------|-------|-----|
| O código de barras aparece borrado | `XDimension.Pixels` definido muito baixo para a resolução de saída | Aumente o tamanho em pixels para pelo menos `2` para exibição em tela, `3` para impressão |
| O scanner não consegue ler o código | `EncodeTypes` incorreto para o formato dos dados | Verifique se os dados GTIN‑14 correspondem à simbologia escolhida |
| `ArgumentOutOfRangeException` na proporção | Valor da proporção não suportado pela biblioteca (faixa válida: 15‑30) | Use apenas valores documentados pela biblioteca, ou capture a exceção e recorra a um padrão |
| Arquivo não encontrado após `Save` | Caminho relativo aponta para um diretório inexistente | Use um caminho absoluto ou garanta que `Directory.CreateDirectory` seja chamado antes |

```csharp
// Ensure the output folder exists
string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputDir);
barcode.Save(Path.Combine(outputDir, "DatabarAspectRatio15.png"), BarCodeImageFormat.Png);
```

## Próximos passos – estendendo o fluxo de trabalho do código de barras

Agora que você pode **criar imagem de código de barras**, talvez queira:

* **Incorporar o PNG em um PDF** usando uma biblioteca como `PdfSharp` ou `iTextSharp`.  
* **Gerar outras simbologias** (QR, Code128, PDF417) alterando o enum `EncodeTypes`.  
* **Aplicar transformações de cor** acessando `barcode.Parameters.Barcode.Image.Color`.  
* **Servir a imagem via um endpoint ASP.NET Core** para geração sob demanda em aplicações web.

Cada um desses tópicos se baseia nos mesmos conceitos centrais abordados neste tutorial, como o uso de **barcode generator c#**, controle de tamanho em pixels e manipulação de proporção.

## Conclusão

Agora você sabe como **criar imagem de código de barras** em C# com um Barcode Generator, como definir o tamanho em pixels, como alterar a proporção e como gerar códigos DataBar de forma eficiente. O exemplo completo e executável pode ser copiado para qualquer projeto .NET, adaptado para outras simbologias e ampliado para atender fluxos de trabalho reais.

Sinta‑se à vontade para experimentar diferentes valores de `XDimension`, proporções e formatos de saída. Se encontrar problemas, consulte a tabela “Armadilhas comuns” ou a documentação oficial da biblioteca para opções de configuração mais avançadas. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Como criar imagem de código de barras e ajustar sua proporção em C#](/barcode/english/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/)
- [Como gerar conjunto de códigos de barras com tamanho personalizado e salvar a imagem em C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [Como usar um gerador de código de barras C# para criar códigos DataBar](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}