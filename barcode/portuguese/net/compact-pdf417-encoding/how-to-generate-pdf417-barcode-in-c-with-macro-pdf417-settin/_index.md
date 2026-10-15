---
category: general
date: 2026-10-15
description: Aprenda como gerar código de barras PDF417 em C# usando parâmetros Macro‑PDF417,
  definir as dimensões do código de barras e salvar como PNG. Exemplo de código completo
  incluído.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417 barcode
- C# PDF417 barcode
- Macro PDF417 parameters
- set barcode dimensions
- barcode image format
- barcode checksum
language: pt
lastmod: 2026-10-15
og_description: Como gerar código de barras PDF417 em C# com configuração completa
  de Macro‑PDF417, controle de dimensões e saída PNG. Siga o exemplo completo.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Como gerar código de barras PDF417 em C# – guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to generate PDF417 barcode in C# using Macro‑PDF417 parameters,
    set barcode dimensions, and save as PNG. Complete code example included.
  headline: How to generate PDF417 barcode in C# with Macro‑PDF417 settings
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- Aspose.Barcode
title: Como gerar código de barras PDF417 em C# com configurações Macro‑PDF417
url: /pt/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-macro-pdf417-settin/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar código de barras PDF417 em C# com configurações Macro‑PDF417

Se você precisa **gerar código de barras PDF417** para um fluxo de trabalho de documentos, este guia mostra os passos exatos. Você verá como configurar os parâmetros Macro‑PDF417, definir as dimensões do código de barras e exportar o resultado como uma imagem PNG — tudo em um único programa C# executável.

Gerar um código de barras PDF417 não requer múltiplas bibliotecas ou pós‑processamento complexo. Usando o Aspose.Barcode para .NET, você pode controlar cada aspecto do código de barras, desde a largura do módulo até o checksum, e produzir uma imagem de alta qualidade pronta para impressão ou leitura.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* SDK .NET 6.0 (ou superior) instalado  
* Visual Studio 2022 ou qualquer IDE C# de sua preferência  
* Pacote NuGet Aspose.Barcode para .NET (`Install-Package Aspose.Barcode`)  

Esses pré‑requisitos garantem que o código compile sem configurações adicionais.

## Etapa 1: Criar um gerador de código de barras para um código Macro‑PDF417

A primeira operação cria uma instância `BarcodeGenerator` que tem como alvo o formato `EncodeTypes.MacroPdf417`. O construtor recebe os dados que você deseja codificar — neste caso, a string `"Sample text"`.

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

// Step 1: Initialize the generator with Macro‑PDF417 and data to encode
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent steps configure the barcode
```

Criar o gerador configura o objeto interno `Parameters`, que será usado para ajustar as propriedades do **código de barras C# PDF417**.

## Etapa 2: Definir a aparência básica – definir dimensões do código de barras

Controlar o tamanho visual de um código de barras melhora a confiabilidade da leitura. A propriedade `XDimension.Pixels` define a largura do módulo (ponto), enquanto `Pdf417.Columns` determina quantas colunas o código de barras terá.

```csharp
    // Step 2: Define module width and column count
    generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width in pixels
    generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

Definir essas dimensões garante que o código de barras caiba em tamanhos típicos de etiquetas e atenda às especificações dos leitores.

## Etapa 3: Fornecer identificação de arquivo Macro‑PDF417

Macro‑PDF417 estende o código de barras PDF417 padrão com metadados a nível de arquivo. Você deve atribuir um ID de arquivo único, ID de segmento, contagem total de segmentos e um nome de arquivo legível.

```csharp
    // Step 3: Assign macro file identification
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";
```

Esses **parâmetros Macro PDF417** permitem que sistemas downstream reconstruam o arquivo original a partir de múltiplos segmentos de código de barras.

## Etapa 4: Adicionar metadados macro adicionais – incluir checksum do código de barras

Além da identificação, Macro‑PDF417 pode armazenar checksum, tamanho do arquivo, timestamp, destinatário, remetente e uma bandeira de terminação. Fornecer um checksum melhora as verificações de integridade dos dados durante a decodificação.

```csharp
    // Step 4: Populate extra macro metadata
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;               // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 850_000;             // file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = DateTime.UtcNow;   // UTC timestamp
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "Acme Corp";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "John Doe";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

Incluir um **checksum de código de barras** e outros metadados torna o código de barras auto‑descritivo, o que é valioso para pipelines automatizados de processamento de documentos.

## Etapa 5: Salvar o código de barras gerado como imagem PNG – escolher o formato da imagem

A etapa final grava o código de barras em um arquivo. O método `Save` aceita um caminho de arquivo e um enum `BarCodeImageFormat`. PNG fornece compressão sem perdas, preservando bordas nítidas para leitura confiável.

```csharp
    // Step 5: Export the barcode to PNG
    generator.Save("C:/Barcodes/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

Após a execução, o arquivo `MacroPdf417.png` contém um código de barras PDF417 nítido, pronto para ser incorporado em PDFs, impresso em etiquetas ou exibido em telas.

## Saída esperada

Abrir `C:/Barcodes/MacroPdf417.png` mostra um código de barras retangular com o texto codificado “Sample text”. O código de barras inclui os metadados macro que você definiu, os quais podem ser verificados com qualquer leitor PDF417 que suporte Macro‑PDF417. As dimensões da imagem refletem a largura do módulo (2 px) e a contagem de colunas (5), resultando em um código de barras compacto, porém legível.

## Variações comuns e casos de borda

| Situação | Ajuste |
|-----------|------------|
| **Comprimento de dados diferente** | Substitua `"Sample text"` por qualquer string UTF‑8; o gerador ajusta automaticamente o tamanho do código de barras. |
| **Resolução mais alta** | Aumente `XDimension.Pixels` para 3 ou 4 para módulos maiores, útil em impressoras de baixa resolução. |
| **Mais segmentos** | Altere `MacroPdf417SegmentsCount` para corresponder ao número total de partes de código de barras que você planeja gerar. |
| **Formato de imagem alternativo** | Use `BarCodeImageFormat.Jpeg` ou `BarCodeImageFormat.Bmp` se seu sistema downstream preferir esses formatos. |
| **Correção de erro personalizada** | Modifique `generator.Parameters.Barcode.Pdf417.ErrorLevel` (faixa 0‑8) para equilibrar densidade de dados e tolerância a erros. |

**Dica profissional:** Sempre valide o código de barras gerado com um scanner físico antes de colocá‑lo em produção. Scanners podem ter limites específicos de firmware quanto à largura do módulo ou contagem de colunas.

## Código-fonte completo

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace Pdf417MacroDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator for Macro‑PDF417 with sample data
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
            {
                // Set visual dimensions
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // column count

                // Provide macro file identification
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";

                // Add macro metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;               // CCITT‑16 checksum
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 850_000;             // file size in bytes
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = DateTime.UtcNow;   // timestamp
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "Acme Corp";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "John Doe";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Export as PNG
                generator.Save("C:/Barcodes/MacroPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("PDF417 barcode generated successfully.");
        }
    }
}
```

Executar este programa cria `MacroPdf417.png` na pasta `C:/Barcodes`. O console confirma a geração bem‑sucedida.

## Conclusão

Agora você sabe **como gerar código de barras PDF417** em C# com controle total do Macro‑PDF417, como **definir dimensões do código de barras**, como incorporar **checksum de código de barras** e outros metadados macro, e como exportar o resultado usando um **formato de imagem de código de barras** escolhido. O exemplo completo pode ser copiado para qualquer projeto .NET, modificado para diferentes cargas de dados e integrado a pipelines maiores de automação de documentos.

### Próximos passos

* Explore os níveis de **correção de erro do código de barras C# PDF417** para melhorar a confiabilidade da leitura.  
* Combine múltiplos segmentos Macro‑PDF417 para codificar arquivos grandes, como PDFs ou imagens.  
* Troque o **formato de imagem do código de barras** para SVG, obtendo gráficos vetoriais escaláveis em aplicações web.  

Sinta‑se à vontade para experimentar os parâmetros e compartilhar seus resultados nos comentários ou em fóruns da comunidade. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Generate barcode C# with Macro PDF417 – full example](/barcode/english/net/compact-pdf417-encoding/generate-barcode-c-with-macro-pdf417-full-example/)
- [How to Generate PDF417 Barcode – Complete Programming Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)
- [How to generate PDF417 barcode in C# with custom dimensions](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}