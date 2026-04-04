---
date: 2026-02-25
description: Aprenda a gerar imagem de código de barras e salvar o PNG do código de
  barras usando Aspose.BarCode para .NET – um exemplo completo de código de barras
  Aspose.
linktitle: One-Dimensional Code 93 Configuration
second_title: Aspose.BarCode .NET API
title: Gerar imagem de código de barras – Code 93 com Aspose.BarCode
url: /pt/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/
weight: 12
---

 content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerar imagem de código de barras – Código 93 unidimensional com Aspose.BarCode

## Introdução

Na era digital atual, os códigos de barras se tornaram parte integrante de nossas vidas, simplificando processos como gerenciamento de estoque, rotulagem de produtos e rastreamento no ponto de venda. **Gerar uma imagem de código de barras** costuma ser o primeiro passo para integrar esses identificadores em suas aplicações. O Aspose.BarCode para .NET oferece uma API robusta e fácil de usar que permite criar códigos de barras Code 93 de alta qualidade em apenas algumas linhas de código C#. Seja você quem está desenvolvendo um sistema de armazém, um aplicativo de varejo ou uma ferramenta de relatórios personalizada, este tutorial orienta você através de um **exemplo de barcode aspose** completo que mostra como gerar, personalizar e **salvar arquivos PNG de código de barras**.

## Respostas rápidas
- **O que o tutorial aborda?** Criação e salvamento de uma imagem de código de barras Code 93 com tratamento de checksum.  
- **Qual biblioteca é usada?** Aspose.BarCode para .NET (última versão estável).  
- **Preciso de licença?** Uma versão de avaliação gratuita funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Posso mudar o formato de saída?** Sim – você pode salvar como PNG, JPEG, BMP, etc., alterando o `BarCodeImageFormat`.  
- **Quais são os requisitos mínimos?** .NET Framework 4.6+ ou .NET Core 3.1+ e Visual Studio.

## O que é um código de barras Code 93?
Code 93 é uma simbologia alfanumérica de alta densidade que suporta todo o conjunto de caracteres ASCII. É frequentemente escolhido por seu tamanho compacto e checksum incorporado, que ajuda a garantir a integridade dos dados durante a leitura.

## Por que gerar imagens de código de barras com Aspose.BarCode?
- **Controle total** sobre o tipo de codificação, checksum, tamanho e formato da imagem.  
- **Sem dependências externas** – a biblioteca funciona em qualquer plataforma .NET.  
- **Qualidade de renderização excelente**, adequada tanto para exibição em tela quanto para impressão em alta resolução.  
- **Documentação abrangente** e um grande conjunto de exemplos que aceleram o desenvolvimento.

## Pré‑requisitos

Antes de mergulharmos no código, certifique‑se de que você tem o seguinte:

1. **Visual Studio** (qualquer edição recente).  
2. **Aspose.BarCode para .NET** instalado – você pode obtê‑lo na página oficial de download.  
3. Familiaridade básica com **C#** e a estrutura de projetos .NET.

Agora que está tudo pronto, vamos ao guia passo a passo.

## Importar namespaces

Primeiro, importe os namespaces necessários para acessar as classes de geração de código de barras.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## Etapa 1: Definir o caminho do diretório

Defina onde a imagem de código de barras gerada será salva. Substitua o placeholder por uma pasta válida em sua máquina.

```csharp
string path = "Your Directory Path";
```

## Etapa 2: Criar um código de barras Code 93 unidimensional

Instancie um `BarcodeGenerator` com o tipo `Code93Extended` e os dados que você deseja codificar.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code93Extended, "CODE");
```

## Etapa 3: Habilitar checksum (opcional)

Code 93 inclui checksum por padrão. Você pode ativá‑lo ou desativá‑lo usando a propriedade `IsChecksumEnabled`.

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
```

## Etapa 4: Salvar a imagem do código de barras (Salvar Barcode PNG)

Gere a imagem e salve‑a como um arquivo PNG na pasta especificada anteriormente.

```csharp
gen.Save($"{path}OneCSCode93WithChecksum.png", BarCodeImageFormat.Png);
```

## Etapa 5: Tratamento de exceções – Gerando sem checksum

Se precisar criar um código de barras **sem** checksum, será necessário tratar possíveis exceções que possam ocorrer.

```csharp
try
{
    gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.No;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

### Problemas comuns e soluções
- **Caminho inválido** – verifique se o diretório existe e se a aplicação tem permissão de gravação.  
- **Caracteres não suportados** – Code 93 suporta todo o conjunto ASCII, mas caracteres de controle podem gerar erros.  
- **Licença não definida** – sem uma licença válida, a biblioteca funciona em modo de avaliação e pode adicionar uma marca d'água.

## Perguntas frequentes (FAQs)

### Q: Onde posso encontrar a documentação do Aspose.BarCode para .NET?
A: Você pode encontrar a documentação em [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/).

### Q: Como faço o download do Aspose.BarCode para .NET?
A: Você pode baixar o Aspose.BarCode para .NET no site em [Aspose.BarCode for .NET Download](https://releases.aspose.com/barcode/net/).

### Q: Existe uma versão de avaliação gratuita do Aspose.BarCode para .NET?
A: Sim, você pode obter uma avaliação gratuita do Aspose.BarCode para .NET [aqui](https://releases.aspose.com/).

### Q: Como posso comprar uma licença para o Aspose.BarCode para .NET?
A: Você pode adquirir uma licença na página de compra em [Aspose.BarCode for .NET Purchase](https://purchase.aspose.com/buy).

### Q: Onde posso obter suporte ou fazer perguntas sobre o Aspose.BarCode para .NET?
A: Você pode encontrar um fórum da comunidade para suporte e discussões em [Aspose.BarCode for .NET Support](https://forum.aspose.com/c/barcode/13).

---

**Última atualização:** 2026-02-25  
**Testado com:** Aspose.BarCode 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}