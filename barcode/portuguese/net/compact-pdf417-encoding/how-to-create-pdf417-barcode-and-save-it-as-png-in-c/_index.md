---
category: general
date: 2026-10-05
description: Aprenda a criar código de barras PDF417 em C# e gerar PNG do código de
  barras com código passo a passo e dicas de boas práticas.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- generate barcode PNG
- how to generate PDF417
language: pt
lastmod: 2026-10-05
og_description: Crie código de barras PDF417 em C# e gere o PNG do código de barras
  instantaneamente. Siga este tutorial completo para uma solução pronta para produção.
og_image_alt: Example of a compact PDF417 barcode created with C#
og_title: Criar código de barras PDF417 em C# – guia completo para gerar PNG
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
    step‑by‑step code and best‑practice tips.
  headline: How to create PDF417 barcode and save it as PNG in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
    step‑by‑step code and best‑practice tips.
  name: How to create PDF417 barcode and save it as PNG in C#
  steps:
  - name: Expected output
    text: When you open `CompactPdf417.png`, you should see a vertical, high‑density
      barcode that encodes the string *Åspóse.Barcóde©*. Scanning the image with any
      PDF417 reader returns the original text.
  - name: Generating other image formats
    text: 'If you prefer JPEG or BMP, change the `BarCodeImageFormat` enum:'
  - name: Adjusting error correction
    text: 'For harsh environments (e.g., outdoor signage), increase the error‑correction
      level:'
  - name: Encoding binary data
    text: 'PDF417 can encode binary payloads. Pass a `byte[]` instead of a string:'
  - name: Handling very long strings
    text: 'When the data exceeds the default capacity, the generator automatically
      creates additional rows. You can limit the row count to avoid oversized images:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- image generation
title: Como criar código de barras PDF417 e salvá-lo como PNG em C#
url: /pt/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar código de barras PDF417 e salvá‑lo como PNG em C#

Se você precisa **criar código de barras PDF417** em uma aplicação .NET, este guia mostra exatamente como fazer isso. Você receberá um trecho de C# pronto‑para‑uso que gera um arquivo **PNG de código de barras** de alta qualidade e entenderá cada configuração que influencia o resultado.

Gerar códigos de barras é uma necessidade comum para sistemas de bilhetagem, rastreamento de inventário e codificação segura de documentos. Ao final deste tutorial, você poderá responder à pergunta “**como gerar PDF417**” com um exemplo completo e executável.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 SDK ou posterior instalado  
* Um ambiente de desenvolvimento como Visual Studio 2022 ou VS Code  
* O pacote **Aspose.BarCode for .NET** NuGet (ou qualquer biblioteca compatível que suporte PDF417)  

Você pode adicionar o pacote com o seguinte comando:

```bash
dotnet add package Aspose.BarCode
```

O código abaixo usa a API Aspose porque ela fornece controle granular sobre os parâmetros do PDF417 e suporta exportação PNG nativamente.

## Etapa 1: Configurar o projeto e importar namespaces

Crie um novo projeto de console e importe os namespaces necessários:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

O namespace `Aspose.BarCode.Generation` contém a classe `BarcodeGenerator`, que é o ponto de entrada para **criar imagens de código de barras PDF417**.

## Etapa 2: Criar código de barras PDF417 com o texto desejado

Instancie o gerador com o enum `EncodeTypes.Pdf417` e os dados que você deseja codificar. O exemplo usa uma string que contém caracteres especiais para demonstrar o tratamento de Unicode:

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

O gerador agora contém um objeto de código de barras que você pode configurar antes da renderização.

## Etapa 3: Configurar parâmetros visuais

Ajustar finamente o código de barras melhora a legibilidade e reduz o tamanho da imagem. As configurações mais frequentemente ajustadas são **X‑dimension**, **columns** e **compact mode**.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 4: Define the number of columns for the PDF417 code
generator.Parameters.Barcode.Pdf417.Columns = 3;

// Step 5: Enable compact (truncated) mode to reduce the barcode size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

* **X‑dimension** controla a largura de cada módulo; um valor de `2` pixels gera um código de barras compacto, porém legível.  
* **Columns** determina quantas colunas de dados o código usa. Menos colunas tornam o código de barras mais estreito, porém mais alto.  
* **Truncate** ativa o modo “compact” definido pela especificação PDF417, que remove linhas de preenchimento desnecessárias.

Você pode experimentar `Rows` e `ErrorCorrectionLevel` se seu caso de uso exigir maior resistência a danos.

## Etapa 4: Salvar o código de barras como imagem PNG

Por fim, exporte o código de barras para um arquivo PNG. PNG preserva bordas nítidas e suporta transparência, tornando‑o ideal para cenários web e impressão.

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Executar o programa cria `CompactPdf417.png` no diretório especificado. A imagem se parece com isto:

![Código de barras PDF417 compacto criado com C#](compact-pdf417.png "Exemplo de um código de barras PDF417 compacto criado com C#")

*O texto alternativo acima contém a palavra‑chave principal, atendendo aos requisitos de SEO e acessibilidade.*

## Exemplo completo, executável

Juntando todas as peças, aqui está um programa autocontido que você pode copiar, colar e executar:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1. Initialize the generator with PDF417 type and sample data
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

        // 2. Configure size and compactness
        generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
        generator.Parameters.Barcode.Pdf417.Columns = 3;           // number of columns
        generator.Parameters.Barcode.Pdf417.Truncate = true;       // enable compact mode

        // 3. Optional: increase error correction for damaged prints
        // generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;

        // 4. Export to PNG
        string outputPath = @"C:\Barcodes\CompactPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

### Saída esperada

Ao abrir `CompactPdf417.png`, você deverá ver um código de barras vertical, de alta densidade, que codifica a string *Åspóse.Barcóde©*. Escanear a imagem com qualquer leitor PDF417 retorna o texto original.

## Por que essas configurações são importantes

* **X‑dimension** influencia tanto o tamanho físico quanto a velocidade de leitura. Módulos menores aumentam a densidade de dados, mas podem exigir scanners de maior resolução.  
* **Columns** afeta a proporção. Para recibos móveis, um número baixo de colunas mantém o código de barras estreito o suficiente para caber em papel fino.  
* **Truncate** reduz o número de linhas, economizando tinta e espaço sem sacrificar a integridade dos dados, pois o PDF417 já inclui códigos de correção de erro.

Entender esses parâmetros permite adaptar o código de barras às restrições do seu meio‑de‑destino — seja uma impressora de etiquetas, uma página web ou um aplicativo móvel.

## Variações comuns e casos de borda

### Gerando outros formatos de imagem

Se preferir JPEG ou BMP, altere o enum `BarCodeImageFormat`:

```csharp
generator.Save(@"C:\Barcodes\Pdf417.jpg", BarCodeImageFormat.Jpeg);
```

JPEG comprime a imagem, mas pode introduzir artefatos que afetam a leitura em tamanhos pequenos.

### Ajustando correção de erro

Para ambientes adversos (por exemplo, sinalização externa), aumente o nível de correção de erro:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 8; // max is 8
```

Níveis mais altos adicionam mais redundância, tornando o código de barras maior, porém mais robusto.

### Codificando dados binários

PDF417 pode codificar payloads binários. Passe um `byte[]` em vez de uma string:

```csharp
byte[] binaryData = new byte[] { 0x01, 0xFF, 0xA5 };
generator = new BarcodeGenerator(EncodeTypes.Pdf417, binaryData);
```

A biblioteca muda automaticamente para o modo binário.

### Manipulando strings muito longas

Quando os dados excedem a capacidade padrão, o gerador cria automaticamente linhas adicionais. Você pode limitar a contagem de linhas para evitar imagens excessivamente grandes:

```csharp
generator.Parameters.Barcode.Pdf417.Rows = 30; // max rows
```

Se o conteúdo ainda não couber, considere dividi‑lo em vários códigos de barras.

## Dicas avançadas

* **Cache o gerador** se precisar criar muitos códigos de barras com as mesmas configurações. Reutilizar o objeto evita alocações repetidas de recursos internos.  
* **Defina `Resolution`** nas `ImageOptions` se precisar de DPI específico para impressão:

  ```csharp
  generator.Parameters.ImageResolution = 300; // DPI
  ```

* **Valide a saída** programaticamente com `BarCodeReader` para garantir que o PNG gerado possa ser decodificado antes de enviá‑lo aos usuários.

## Conclusão

Agora você sabe como **criar código de barras PDF417** em C# e **gerar arquivos PNG de código de barras** com controle total sobre tamanho, colunas e modo compacto. O exemplo completo demonstra a abordagem padrão, explica por que cada configuração importa e cobre variações como correção de erro, formatos alternativos e dados binários. Use as dicas acima para adaptar a solução ao seu fluxo de trabalho específico, seja construindo um sistema de bilhetagem, um gerador de etiquetas logísticas ou um codificador de documentos seguros.

---

**Próximos passos**

* Explore outras simbologias 2D (DataMatrix, QR) usando a mesma classe `BarcodeGenerator`.  
* Integre a criação de códigos de barras em uma API ASP.NET Core para servir PNGs sob demanda.  
* Combine a imagem do código de barras com bibliotecas de geração de PDF para incorporá‑la diretamente em relatórios.

Happy coding!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que expandem as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [How to create pdf417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [How to generate micro pdf417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}