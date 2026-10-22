---
category: general
date: 2026-10-21
description: Aprenda como gerar código de barras PDF417 em C# usando Aspose.BarCode.
  Etapas detalhadas cobrem as configurações do código de barras PDF417, a criação
  de código de barras macro PDF417 e a gravação como PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate PDF417 barcode
- PDF417 barcode settings
- Macro PDF417 barcode
- barcode generator C#
- BarCodeImageFormat PNG
- EncodeTypes.MacroPdf417
language: pt
lastmod: 2026-10-21
og_description: Como gerar código de barras PDF417 em C# usando Aspose.BarCode. Siga
  este tutorial passo a passo para configurar as definições do código de barras PDF417,
  criar um código de barras PDF417 macro e exportar para PNG.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C# code
og_title: Como gerar código de barras PDF417 em C# – guia completo
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Detailed
    steps cover PDF417 barcode settings, macro PDF417 barcode creation, and saving
    as PNG.
  headline: How to generate PDF417 barcode in C# with macro support
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Detailed
    steps cover PDF417 barcode settings, macro PDF417 barcode creation, and saving
    as PNG.
  name: How to generate PDF417 barcode in C# with macro support
  steps:
  - name: '**Create a `BarcodeGenerator` instance** using `EncodeTypes.MacroPdf417`.'
    text: '**Create a `BarcodeGenerator` instance** using `EncodeTypes.MacroPdf417`.'
  - name: '**Adjust basic barcode appearance** (module size, colors, etc.).'
    text: '**Adjust basic barcode appearance** (module size, colors, etc.).'
  - name: '**Configure PDF417‑specific settings**, including macro‑related fields.'
    text: '**Configure PDF417‑specific settings**, including macro‑related fields.'
  - name: '**Save the generated barcode image** with `BarCodeImageFormat PNG`.'
    text: '**Save the generated barcode image** with `BarCodeImageFormat PNG`.'
  type: HowTo
tags:
- PDF417
- barcode
- C#
- Aspose.BarCode
title: Como gerar código de barras PDF417 em C# com suporte a macro
url: /pt/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-macro-support/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar código de barras PDF417 em C# com suporte a macro

Se você precisa gerar código de barras PDF417 em C#, este guia mostra uma solução completa, pronta‑para‑executar. Seja construindo um sistema de etiquetas logísticas ou codificando blocos de dados grandes, você verá como configurar as definições do código de barras PDF417, criar um código de barras Macro PDF417 e salvar o resultado como imagem PNG.

Gerar um código de barras PDF417 não requer manipulação de bits de baixo nível. Ao usar a **barcode generator C#** da Aspose.BarCode, você pode focar na lógica de negócio enquanto a biblioteca cuida da codificação, correção de erros e renderização da imagem.

## O que você precisará

Antes de começar, certifique‑se de que tem:

- **.NET 6.0** ou superior (o código também funciona com .NET Framework 4.6+)
- Pacote NuGet **Aspose.BarCode for .NET** (`Install-Package Aspose.BarCode`)
- Um ambiente de desenvolvimento como Visual Studio 2022 ou Visual Studio Code
- Permissão de escrita em uma pasta onde a imagem PNG será salva

Esses pré‑requisitos garantem que o exemplo compile e execute sem configuração adicional.

## Como gerar código de barras PDF417 – visão geral passo a passo

Abaixo está um roteiro conciso do processo:

1. **Criar uma instância de `BarcodeGenerator`** usando `EncodeTypes.MacroPdf417`.
2. **Ajustar a aparência básica do código de barras** (tamanho do módulo, cores, etc.).
3. **Configurar as definições específicas do PDF417**, incluindo campos relacionados a macro.
4. **Salvar a imagem do código de barras gerado** com `BarCodeImageFormat PNG`.

Cada etapa é explicada em detalhe, com trechos de código completos que você pode copiar diretamente para um aplicativo console.

## Etapa 1: Configurar o ambiente de desenvolvimento

Crie um novo projeto console e adicione a referência ao Aspose.BarCode:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Abra `Program.cs` e adicione os namespaces necessários:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Essas importações dão acesso a `BarcodeGenerator`, `EncodeTypes` e `BarCodeImageFormat`.

## Etapa 2: Criar o gerador de código de barras Macro PDF417

A primeira linha da implementação cria o objeto **Macro PDF417 barcode**. O enum `EncodeTypes.MacroPdf417` indica à biblioteca que deve usar a variante macro do PDF417.

```csharp
// Step 1: Create a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample Text"))
{
    // Subsequent configuration goes here
}
```

> **Por que isso importa:** Usar `EncodeTypes.MacroPdf417` habilita os campos macro (`FileID`, `SegmentID`, etc.) que permitem dividir uma carga útil grande em várias imagens de código de barras mantendo a ordem.

## Etapa 3: Ajustar a aparência básica do código de barras

Antes de ajustar os parâmetros específicos do PDF417, defina a largura do módulo (pixel). Um valor de `2` fornece uma imagem clara e escaneável sem tamanho de arquivo excessivo.

```csharp
// Step 2: Adjust basic barcode appearance
generator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel width of a single module
```

Você também pode mudar as cores de primeiro plano/fundo aqui se a sua UI exigir uma paleta diferente.

## Etapa 4: Configurar as definições específicas do PDF417

As **PDF417 barcode settings** são expostas através de `generator.Parameters.Barcode.Pdf417`. Os campos macro mais importantes são mostrados abaixo:

```csharp
// Step 3: Configure PDF417‑specific settings
generator.Parameters.Barcode.Pdf417.Columns = 5;                     // number of columns (affects width)
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;     // unique file identifier
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // segment number within the file
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;  // total number of segments
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";  // optional human‑readable name
```

### Entendendo cada propriedade

| Propriedade | Finalidade | Faixa típica |
|-------------|------------|--------------|
| `Columns` | Controla quantas colunas de dados cada linha contém. Mais colunas reduzem o número de linhas, mas aumentam a largura. | 1 – 30 |
| `MacroPdf417FileID` | Identificador de 32 bits que agrupa todos os segmentos do mesmo arquivo lógico. Deve ser o mesmo para cada segmento. | Qualquer inteiro positivo |
| `MacroPdf417SegmentID` | Índice baseado em zero do segmento atual. Incrementar para cada código de barras subsequente. | 0 – `SegmentsCount`‑1 |
| `MacroPdf417SegmentsCount` | Número total de segmentos que compõem o arquivo completo. Todos os segmentos devem ser gerados. | ≥ 1 |
| `MacroPdf417FileName` | Nome descritivo opcional (máx. 255 caracteres). Útil para depuração. | Cadeia alfanumérica |

> **Dica profissional:** Mantenha `Columns` entre 3 e 7 para a maioria das impressoras de etiquetas. Valores maiores podem exceder a largura imprimível em dispositivos de baixa resolução.

## Etapa 5: Salvar o código de barras como imagem PNG

Por fim, escreva o código de barras no disco usando `BarCodeImageFormat PNG`. PNG preserva qualidade sem perdas, essencial para uma leitura confiável.

```csharp
// Step 4: Save the generated barcode image
string outputPath = Path.Combine(Environment.CurrentDirectory, "MacroPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Quando o programa terminar, você encontrará `MacroPdf417.png` na pasta do projeto. Abrir o arquivo mostra um código de barras Macro PDF417 limpo, pronto para impressão.

### Saída esperada

A imagem gerada se parece com o exemplo abaixo (apenas ilustrativo):

![Macro PDF417 barcode example](macro-pdf417-barcode.png "Macro PDF417 barcode generated by C# code")

*O texto alternativo da imagem é “Macro PDF417 barcode generated with C# code”, atendendo aos requisitos de acessibilidade e SEO.*

## Problemas comuns e solução de problemas

| Problema | Sintoma | Correção |
|----------|---------|----------|
| **EncodeTypes incorreto** | O código de barras é renderizado como QR code ou texto simples. | Certifique‑se de usar `EncodeTypes.MacroPdf417` (não `EncodeTypes.Pdf417`). |
| **IDs de segmento incompatíveis** | O scanner relata “segmento ausente”. | Incrementar `MacroPdf417SegmentID` sequencialmente e manter `SegmentsCount` consistente em todos os arquivos. |
| **Tamanho de módulo muito grande** | O código de barras fica muito largo para a etiqueta. | Reduzir `XDimension.Pixels` ou diminuir `Columns`. |
| **Erros de caminho de arquivo** | `UnauthorizedAccessException` ao salvar. | Salvar em uma pasta que você possua, por exemplo, `Environment.CurrentDirectory`. |
| **Pacote NuGet ausente** | Erro de compilação: `BarcodeGenerator` não encontrado. | Executar `dotnet add package Aspose.BarCode` antes de compilar. |

Resolver esses problemas cedo economiza tempo ao integrar a geração de códigos de barras em fluxos de trabalho maiores.

## Estendendo o exemplo

Agora que você pode gerar um único código de barras Macro PDF417, considere os próximos passos:

- **Geração em lote**: Percorra uma coleção de blocos de dados, atualizando `MacroPdf417SegmentID` a cada iteração.
- **Formatos de imagem diferentes**: Substitua `BarCodeImageFormat.Png` por `Jpeg` ou `Bmp` se seu sistema downstream preferir esses formatos.
- **Incorporar em PDFs**: Use Aspose.PDF para colocar o PNG em um relatório PDF para distribuição.
- **Verificação de leitura**: Teste os códigos de barras gerados com um scanner de hardware ou um aplicativo móvel que suporte Macro PDF417.

Essas variações mantêm as **PDF417 barcode settings** principais intactas enquanto adaptam a saída às necessidades do seu projeto.

## Conclusão

Agora você sabe **como gerar código de barras PDF417** em C# usando Aspose.BarCode, desde a criação de um `BarcodeGenerator` com `EncodeTypes.MacroPdf417` até a configuração dos campos macro e a gravação do resultado como `BarCodeImageFormat PNG`. O código completo e executável demonstra a abordagem recomendada, explica por que cada configuração importa e destaca armadilhas comuns que você pode encontrar.

Sinta‑se à vontade para experimentar diferentes contagens de colunas, cores ou formatos de saída e integrar o gerador em suas próprias aplicações para codificação de dados de alta densidade e confiável.

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Como gerar códigos de barras PDF417 em C# com Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/)
- [Como criar código de barras macro PDF417 em C# usando Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Como salvar código de barras e gerar PDF417 com Aspose em C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}