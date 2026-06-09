---
date: 2026-06-09
description: Aprenda como gerar código de barras datamatrix com Aspose.BarCode para
  .NET, personalize proporções, modos ECC e codificação datamatrix c40 para uma criação
  de código de barras eficiente.
keywords:
- generate datamatrix barcode
- datamatrix c40 encoding
- aspose barcode .net
- datamatrix ecc modes
- barcode aspect ratio
linktitle: Configuração de Código de Barras DataMatrix
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  headline: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  name: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  steps:
  - name: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
    text: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
  - name: '**Adjust** `AspectRatio` to your desired value.'
    text: '**Adjust** `AspectRatio` to your desired value.'
  - name: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
    text: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
  type: HowTo
- questions:
  - answer: Choose ECC 000‑140 for small data sets with limited error correction,
      or ECC 200 for larger data and higher reliability. Macro mode adds an extra
      data layer for linking.
    question: How do I decide which ECC mode to use?
  - answer: Yes, set the `CodeText` property to your custom string, then select the
      appropriate encoding mode (ASCII, C40, etc.) to control size.
    question: Can I embed custom text in a DataMatrix barcode?
  - answer: Set `EncodeMode` to `Auto`; Aspose.BarCode evaluates the payload and picks
      the most space‑efficient mode automatically.
    question: Is there a way to automatically select the best encoding mode?
  - answer: Reuse a single `BarCodeGenerator` instance, enable multi‑threading, and
      generate PNG images for lossless quality or JPEG for smaller file size. Processing
      10 000 symbols typically completes in under 30 seconds on a standard 8‑core
      server.
    question: What are the performance considerations for large barcode batches?
  - answer: Absolutely – the library is fully compatible with .NET Framework, .NET
      Core, and the latest .NET releases, offering the same feature set across all
      platforms.
    question: Does Aspose.BarCode support .NET Core and .NET 5/6?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Gerar Código de Barras DataMatrix – Guia Profissional com Aspose.BarCode
url: /pt/net/datamatrix-barcode-configuration/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerar Código de Barras DataMatrix – Guia Profissional com Aspose.BarCode

Welcome to our comprehensive tutorial series on **generate datamatrix barcode** using Aspose.BarCode for .NET. Whether you're a seasoned developer fine‑tuning barcode output or a newcomer eager to understand the fundamentals, this guide walks you through every step—from basic configuration to advanced encoding techniques—so you can deliver reliable, scan‑ready barcodes in any .NET application.

## Respostas Rápidas
- **Qual é o objetivo principal?** Para criar e personalizar códigos de barras DataMatrix programaticamente.  
- **Qual biblioteca é usada?** Aspose.BarCode for .NET.  
- **Preciso de uma licença?** Um teste gratuito está disponível; uma licença comercial é necessária para produção.  
- **Versões .NET suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Posso personalizar a proporção de aspecto?** Sim – veja a seção “How to customize DataMatrix aspect ratio”.

## O que é generate datamatrix barcode?
Um DataMatrix barcode é uma matriz bidimensional de células pretas e brancas que pode armazenar até 2 300 caracteres alfanuméricos. Usando Aspose.BarCode, você pode **generate datamatrix barcode** imagens, PDFs ou SVGs diretamente do seu código .NET, controlando tamanho, nível de correção de erro e modo de codificação para atender a qualquer padrão da indústria.

## Por que usar Aspose.BarCode para DataMatrix?
Aspose.BarCode renderiza símbolos DataMatrix em até **600 dpi** sem pixelização, garantindo leituras nítidas em impressoras de alta resolução. Ele suporta **todos os mais de 50 modos ECC e macro** — incluindo ECC 000‑140, ECC 200 e Macro 05/06 — para que você possa escolher o nível de correção de erro ideal para o tamanho dos seus dados. A API oferece opções de codificação **ASCII, C40, Text, X12 e Bytes**, permitindo compactar os dados de forma eficiente. A integração requer apenas um único pacote NuGet e nenhuma biblioteca nativa externa.

## Como personalizar a proporção de aspecto do DataMatrix
A propriedade `AspectRatio` de `BarCodeGenerator` controla a proporção largura‑altura do símbolo DataMatrix gerado. `BarCodeGenerator` é a classe principal no Aspose.BarCode usada para criar imagens de códigos de barras.  

**Resposta direta:** Set `generator.Parameters.Barcode.DataMatrix.AspectRatio = 1.2` (or any value between 0.5 and 2.0) before calling `GenerateBarCodeImage()`. The library automatically recalculates module size to preserve scan reliability while respecting the requested ratio.

### Passo a passo
1. **Instanciar** `BarCodeGenerator` com `EncodeTypes.DataMatrix`.  
2. **Ajustar** `AspectRatio` ao valor desejado.  
3. **Gerar** a imagem e verificar com um scanner ou o leitor interno da Aspose.

## Como gerar códigos de barras DataMatrix ECC 000‑140
ECC 000‑140 é ideal para cadeias curtas de dados onde um símbolo compacto é necessário, oferecendo até 140 palavras‑código de correção de erro. `DataMatrixEccMode.Ecc000140` seleciona o esquema de correção de erro ECC 000‑140 para DataMatrix.  

**Resposta direta:** Use `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc000140` before rendering. Isso troca o codificador para o algoritmo ECC 000‑140, produzindo a menor matriz possível para os dados fornecidos, mantendo ainda uma correção de erro robusta.

### Dica prática
Ao codificar dados numéricos com menos de 20 caracteres, o ECC 000‑140 costuma gerar uma matriz 10 × 10, economizando espaço valioso na etiqueta.

## Como gerar códigos de barras DataMatrix ECC 200
ECC 200 é o modo DataMatrix mais amplamente adotado, suportando até 2 335 caracteres alfanuméricos e oferecendo correção de erro superior. `DataMatrixEccMode.Ecc200` seleciona o esquema de correção de erro ECC 200 para DataMatrix.  

**Resposta direta:** Defina `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc200` e forneça sua carga útil via `CodeText`. A biblioteca então seleciona automaticamente o tamanho de matriz ideal.

### Quando preferir ECC 200
Use ECC 200 para cadeias mais longas, dados de tipo misto ou quando precisar da maior resistência a danos — até **30 %** do símbolo pode ser restaurado.

## Como dominar a codificação DataMatrix em ASCII
O modo ASCII codifica caracteres usando um byte único por caractere, tornando‑o o mais eficiente em espaço para texto simples. `DataMatrixEncodeMode.Ascii` indica ao gerador para usar a codificação ASCII para o símbolo DataMatrix.  

**Resposta direta:** Atribua `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Ascii` e defina `CodeText` para sua string ASCII. O motor compacta os dados sem sobrecarga extra, produzindo a menor matriz possível para conteúdo puro em ASCII.

### Cenário de exemplo
Um SKU de armazém composto por letras maiúsculas e dígitos (por exemplo, “AB1234”) encaixa perfeitamente no modo ASCII, frequentemente resultando em uma matriz 12 × 12.

## Como gerar DataMatrix Modo (Auto)
O modo Auto permite que Aspose.BarCode analise a entrada e escolha automaticamente a codificação mais eficiente (ASCII, C40, Text, X12 ou Bytes). `DataMatrixEncodeMode.Auto` habilita esse recurso de seleção automática.  

**Resposta direta:** Defina `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Auto`. A biblioteca avalia a carga útil, seleciona o modo ideal e renderiza o código de barras em um único passo.

### Benefícios
O modo Auto reduz o esforço de desenvolvimento e garante o menor símbolo possível para dados de tipo misto, melhorando a velocidade de leitura.

## Como usar o modo de codificação DataMatrix (Bytes)
O modo Bytes é projetado para dados binários, como cargas criptografadas ou arquivos compactados. `DataMatrixEncodeMode.Bytes` instrui o gerador a tratar cada byte como dados brutos.  

**Resposta direta:** Use `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Bytes` e forneça uma string codificada em Base64 como `CodeText`. O codificador trata cada byte como dado bruto, preservando a representação binária exata.

### Caso de uso
Incorporar um GUID de 128 bits ou um pequeno token criptografado diretamente em um símbolo DataMatrix.

## Como dominar o modo de codificação DataMatrix (C40)
O modo C40 comprime dados alfanuméricos em maiúsculas, alcançando até **40 %** de redução de tamanho comparado ao ASCII. `DataMatrixEncodeMode.C40` ativa este algoritmo de compressão.  

**Resposta direta:** Defina `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.C40` e forneça uma string em maiúsculas (por exemplo, “HELLO WORLD”). O motor compacta três caracteres em dois codewords, reduzindo a matriz final.

### Dica profissional
C40 funciona melhor quando a carga útil consiste principalmente de letras maiúsculas, números e espaços. Para caso misto, considere o modo Auto.

## Como configurar o texto do código DataMatrix
A propriedade `CodeText` define os dados exatos armazenados no código de barras. Ela pode incluir texto simples, cadeias numéricas ou até cargas XML. `CodeText` é a principal propriedade string de `BarCodeGenerator` que contém a carga do código de barras.  

**Resposta direta:** Atribua `generator.Parameters.Barcode.CodeText = "YourDataHere"` antes de renderizar. A propriedade aceita qualquer string UTF‑8 até o comprimento máximo suportado pelo modo ECC escolhido.

### Dica avançada
Combine `CodeText` com `ExtendedDataMatrix` para incorporar metadados adicionais sem aumentar o tamanho da matriz visível.

## Como dominar a configuração macro do DataMatrix
Os modos macro (Macro 05 e Macro 06) permitem incorporar um símbolo DataMatrix secundário dentro do principal, útil para vincular a fontes de dados externas. `DataMatrixMacroMode.Macro05` e `DataMatrixMacroMode.Macro06` habilitam esses recursos macro.  

**Resposta direta:** Habilite o modo macro com `generator.Parameters.Barcode.DataMatrix.MacroMode = DataMatrixMacroMode.Macro05` (ou `Macro06`) e defina as propriedades `MacroPdf417` para a carga secundária. O gerador cria um símbolo composto que os scanners podem interpretar como dois códigos vinculados.

### Exemplo do mundo real
Incorporar uma URL na parte macro enquanto mantém os identificadores de produto na matriz principal, permitindo integração web‑para‑código de barras sem interrupções.

*Usando Listagem de Tutoriais Aspose.BarCode para .NET*

## Tutoriais de Configuração de Código de Barras DataMatrix
### [Personalizando a Proporção de Aspecto DataMatrix](./datamatrix-aspect-ratio-customization/)
Aprenda como personalizar as proporções de aspecto do código de barras DataMatrix usando Aspose.BarCode para .NET. Guia passo a passo para geração de códigos de barras.
### [Gerar Códigos de Barras DataMatrix ECC 000-140](./datamatrix-ecc-000-140-configuration/)
Crie códigos de barras DataMatrix ECC 000-140 com facilidade usando Aspose.BarCode para .NET. Aumente a eficiência na gestão de inventário e mais.
### [Gerar Códigos de Barras DataMatrix ECC 200](./datamatrix-ecc-200-configuration/)
Aprenda como gerar códigos de barras DataMatrix ECC 200 em .NET usando Aspose.BarCode. Otimize operações com criação eficiente de códigos de barras.
### [Dominar a Codificação DataMatrix em ASCII](./datamatrix-encoding-mode-ascii/)
Aprenda a criar códigos de barras DataMatrix no modo ASCII usando Aspose.BarCode para .NET. Guia passo a passo para desenvolvedores.
### [Gerar Modo DataMatrix (Auto)](./datamatrix-encoding-mode-auto/)
Aprenda como gerar o Modo DataMatrix (Auto) com Aspose.BarCode para .NET. Este guia passo a passo cobre tudo, desde pré-requisitos até a leitura de códigos de barras.
### [Modo de Codificação DataMatrix (Bytes)](./datamatrix-encoding-mode-bytes/)
Aprenda como codificar dados no formato DataMatrix usando o modo Bytes com Aspose.BarCode para .NET. Siga nosso guia passo a passo para geração e reconhecimento de códigos de barras.
### [Dominar o Modo de Codificação DataMatrix (C40)](./datamatrix-encoding-mode-c40/)
Aprenda o Modo de Codificação DataMatrix (C40) com Aspose.BarCode para .NET. Crie códigos de barras personalizados de forma eficiente. Explore o guia passo a passo.
### [Configurando o Texto do Código DataMatrix](./datamatrix-extended-code-text-configuration/)
Aprenda a configurar o texto de código estendido DataMatrix usando Aspose.BarCode para .NET. Gere, reconheça e integre códigos de barras em suas aplicações .NET.
### [Dominar a Configuração Macro DataMatrix](./datamatrix-macro-configuration/)
Aprenda como configurar códigos de barras DataMatrix Macro com Aspose.BarCode para .NET. Gere, personalize e reconheça códigos de barras DataMatrix em suas aplicações .NET.

## Perguntas Frequentes

**Q: Como decido qual modo ECC usar?**  
A: Escolha ECC 000‑140 para conjuntos de dados pequenos com correção de erro limitada, ou ECC 200 para dados maiores e maior confiabilidade. O modo macro adiciona uma camada extra de dados para vinculação.

**Q: Posso incorporar texto personalizado em um código de barras DataMatrix?**  
A: Sim, defina a propriedade `CodeText` para sua string personalizada, então selecione o modo de codificação apropriado (ASCII, C40, etc.) para controlar o tamanho.

**Q: Existe uma maneira de selecionar automaticamente o melhor modo de codificação?**  
A: Defina `EncodeMode` para `Auto`; Aspose.BarCode avalia a carga útil e escolhe automaticamente o modo mais eficiente em espaço.

**Q: Quais são as considerações de desempenho para lotes grandes de códigos de barras?**  
A: Reutilize uma única instância de `BarCodeGenerator`, habilite multithreading e gere imagens PNG para qualidade sem perdas ou JPEG para tamanho de arquivo menor. Processar 10 000 símbolos normalmente é concluído em menos de 30 segundos em um servidor padrão de 8 núcleos.

**Q: O Aspose.BarCode suporta .NET Core e .NET 5/6?**  
A: Absolutamente – a biblioteca é totalmente compatível com .NET Framework, .NET Core e as versões mais recentes do .NET, oferecendo o mesmo conjunto de recursos em todas as plataformas.

**Última atualização:** 2026-06-09  
**Testado com:** Aspose.BarCode 24.12 for .NET  
**Autor:** Aspose

## Tutoriais Relacionados

- [Como gerar códigos de barras DataMatrix (ECC 200) com Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Dominar a codificação DataMatrix em ASCII com Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Criar PNG de código de barras – Proporção de aspecto DataMatrix – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}