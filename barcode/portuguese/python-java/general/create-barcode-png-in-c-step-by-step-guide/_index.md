---
category: general
date: 2026-08-03
description: Crie PNG de código de barras em C# e aprenda como alterar a proporção
  de aspecto para imagens DataBar. Siga este exemplo completo com código e dicas.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode PNG
- how to change aspect ratio
- Aspose.BarCode C#
- DataBar stacked omnidirectional
- barcode image format PNG
language: pt
lastmod: 2026-08-03
og_description: Crie PNG de código de barras em C# e veja como alterar a proporção
  para códigos de barras DataBar. Este guia fornece código pronto‑para‑usar e dicas
  práticas.
og_image_alt: Sample barcode PNG generated with aspect ratio 15
og_title: Criar código de barras PNG em C# – exemplo completo com controle de proporção
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  headline: Create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  name: Create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: How to change other visual properties?
    text: 'You can adjust foreground color, background color, or add human‑readable
      text through the `generator.Parameters.Barcode` object. For example:'
  - name: What if I need a different image format?
    text: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as needed.
      PNG remains the best choice for lossless barcode images.
  - name: Does the aspect ratio affect scanning speed?
    text: Higher aspect ratios increase the barcode’s height, which can improve scan
      reliability on devices that struggle with short stacked symbols. However, extremely
      tall barcodes may not fit on small labels, so test with your target hardware.
  - name: Can I generate multiple barcodes in a loop?
    text: Yes. Create a new `BarcodeGenerator` instance for each data string or reuse
      the same instance while updating `CodeText` and `DataBar.AspectRatio`. This
      approach reduces object allocation overhead.
  type: HowTo
tags:
- barcode
- C#
- PNG
- Aspose
title: Criar PNG de código de barras em C# – guia passo a passo
url: /pt/python-java/general/create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar PNG de código de barras em C# – guia passo a passo

Se você precisa **criar PNG de código de barras** em C#, este tutorial mostra exatamente como fazer. Você irá gerar um código de barras DataBar omnidirecional empilhado, salvá‑lo como um arquivo PNG e aprender **como alterar a proporção** para se adequar a diferentes ambientes de leitura.

O guia cobre tudo o que você precisa: pacotes necessários, um programa completo e executável, e explicações sobre por que cada configuração importa. Ao final, você terá dois arquivos PNG — um com proporção 15 e outro com 30 — prontos para teste ou uso em produção.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

- .NET 6.0 SDK ou posterior instalado
- Visual Studio 2022 (ou qualquer IDE para C#)
- Uma referência NuGet ao **Aspose.BarCode** (a biblioteca que fornece `BarcodeGenerator`)
- Permissão de gravação no diretório onde os arquivos PNG serão salvos

Você pode adicionar o pacote Aspose.BarCode com o seguinte comando:

```bash
dotnet add package Aspose.BarCode
```

## Etapa 1: Configurar o projeto e importar namespaces

Crie um novo aplicativo de console e importe os namespaces necessários para a geração de códigos de barras e I/O de arquivos.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodePngDemo
{
    class Program
    {
        static void Main()
        {
            // All subsequent steps are inside Main
```

**Por que isso importa:** Importar `Aspose.BarCode.Generation` lhe dá acesso ao `BarcodeGenerator`. Manter o código dentro de `Main` torna o exemplo autocontido e fácil de executar.

## Etapa 2: Criar um gerador de código de barras para um DataBar omnidirecional empilhado

Instancie `BarcodeGenerator` com o tipo `EncodeTypes.DatabarStackedOmniDirectional` e uma string de dados GS1‑128 de exemplo.

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");
```

**Por que isso importa:** O tipo de codificação escolhido produz um DataBar de alta densidade que pode ser lido pela maioria dos scanners modernos. A string de dados segue o formato do Identificador de Aplicação GS1 (01), que é comum para identificadores de produto.

## Etapa 3: Definir a X‑dimension (largura do módulo) em pixels

Defina a largura do módulo para controlar o tamanho geral do código de barras sem afetar sua legibilidade.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Por que isso importa:** Uma X‑dimension de 2 pixels gera um código de barras que não é nem pequeno demais para os scanners nem grande demais para os espaços típicos de etiquetas.

## Etapa 4: Salvar o primeiro PNG com proporção 15

Ajuste a proporção do DataBar e, em seguida, salve a imagem como um arquivo PNG.

```csharp
            // Step 4: Set the DataBar aspect ratio to 15 and save the image
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;
            string outputPath15 = @"YOUR_DIRECTORY\DatabarAspectRatio15.png";
            generator.Save(outputPath15, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath15} (aspect ratio 15).");
```

**Por que isso importa:** A proporção controla a relação altura‑largura do DataBar empilhado. Uma proporção de 15 é um padrão comum que equilibra legibilidade e altura da etiqueta.

## Etapa 5: Alterar a proporção para 30 e salvar um segundo PNG

Modifique a mesma instância do gerador para usar uma proporção maior e, então, salve a segunda imagem.

```csharp
            // Step 5: Change the aspect ratio to 30 and save another image
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string outputPath30 = @"YOUR_DIRECTORY\DatabarAspectRatio30.png";
            generator.Save(outputPath30, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath30} (aspect ratio 30).");
        }
    }
}
```

**Por que isso importa:** Aumentar a proporção estica o código de barras verticalmente, o que pode melhorar a confiabilidade da leitura em dispositivos de baixa resolução ou quando a etiqueta é impressa em mídia estreita.

## Saída esperada

A execução do programa cria dois arquivos PNG:

| Arquivo                              | Proporção | Dimensões aproximadas (pixels) |
|--------------------------------------|-----------|--------------------------------|
| `DatabarAspectRatio15.png`           | 15        | 200 × 300 (largura × altura)    |
| `DatabarAspectRatio30.png`           | 30        | 200 × 600 (largura × altura)    |

Ambas as imagens contêm um código de barras DataBar claro e legível que codifica o identificador GS1 `(01)12345678901231`.

## Perguntas comuns e casos de borda

### Como alterar outras propriedades visuais?

Você pode ajustar a cor de primeiro plano, cor de fundo ou adicionar texto legível por humanos através do objeto `generator.Parameters.Barcode`. Por exemplo:

```csharp
generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
generator.Parameters.Barcode.CodeTextParameters.ShowCodeText = true;
```

### E se eu precisar de um formato de imagem diferente?

Substitua `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` ou `Gif`, conforme necessário. PNG continua sendo a melhor escolha para imagens de código de barras sem perdas.

### A proporção afeta a velocidade de leitura?

Proporções maiores aumentam a altura do código de barras, o que pode melhorar a confiabilidade da leitura em dispositivos que têm dificuldade com símbolos empilhados curtos. Contudo, códigos de barras extremamente altos podem não caber em etiquetas pequenas, portanto teste com o hardware alvo.

### Posso gerar vários códigos de barras em um loop?

Sim. Crie uma nova instância de `BarcodeGenerator` para cada string de dados ou reutilize a mesma instância atualizando `CodeText` e `DataBar.AspectRatio`. Essa abordagem reduz a sobrecarga de alocação de objetos.

## Dicas profissionais

- **Reutilize o gerador**: Alterar apenas `CodeText` ou `AspectRatio` evita reinstanciar o objeto, o que acelera o processamento em lote.
- **Valide a saída**: Use um scanner portátil ou um aplicativo móvel para confirmar que o PNG gerado é lido corretamente antes de colocar em produção.
- **Nomeação de arquivos**: Inclua a proporção no nome do arquivo (conforme mostrado) para acompanhar as variações durante os testes.

## Conclusão

Agora você sabe como **criar arquivos PNG de código de barras** em C# e, precisamente, **como alterar a proporção** para símbolos DataBar omnidirecionais empilhados. O exemplo completo demonstra inicialização, definição da X‑dimension, manipulação da proporção e salvamento da imagem — tudo em um único programa executável.

A partir daqui, você pode explorar outros tipos de códigos de barras, experimentar cores ou integrar o gerador a um sistema maior de relatórios ou inventário. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Criar PNG de código de barras – Proporção do DataMatrix – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [Como gerar código de barras Aztec com proporção personalizada usando Aspose.BarCode para .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Como personalizar a proporção do código de barras Codablock F com Aspose.BarCode para .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}