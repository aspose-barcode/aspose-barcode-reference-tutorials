---
date: 2026-02-25
description: Aprenda a gerar imagens de código de barras usando Aspose.BarCode para
  .NET. Este guia passo a passo mostra como gerar códigos de barras Code 39 com e
  sem soma de verificação.
linktitle: One-Dimensional Code 39 Configuration
second_title: Aspose.BarCode .NET API
title: Como gerar código de barras – Configuração do Code 39 com Aspose.BarCode
url: /pt/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configuração Unidimensional Code 39

## Introdução

Neste tutorial, você aprenderá **como gerar código de barras** imagens, especificamente códigos de barras unidimensionais Code 39, usando Aspose.BarCode para .NET. Os códigos de barras desempenham um papel crucial nos negócios modernos, desde o rastreamento de inventário até a habilitação de recuperação de dados rápida e precisa. Aspose.BarCode para .NET é uma biblioteca poderosa que simplifica a geração e personalização de códigos de barras em aplicações .NET. Este guia passo a passo divide o processo em partes facilmente digeríveis, garantindo que até mesmo desenvolvedores novos na geração de códigos de barras possam acompanhar.

## Respostas Rápidas
- **Qual é a biblioteca principal?** Aspose.BarCode para .NET  
- **Posso criar um código de barras com checksum?** Sim – defina `IsChecksumEnabled = EnableChecksum.Yes`  
- **Um checksum é obrigatório?** Não – você pode gerar um código de barras sem checksum desativando‑o  
- **Qual formato de imagem é usado nos exemplos?** PNG (`BarCodeImageFormat.Png`)  
- **Preciso de licença para desenvolvimento?** Uma licença temporária está disponível para avaliação  

## O que é geração de código de barras com Aspose.BarCode?
A geração de código de barras é o processo de converter texto ou dados numéricos em um padrão visual legível por máquina. Aspose.BarCode para .NET suporta dezenas de simbologias, incluindo Code 39, e permite controlar tudo, desde tamanho e cor até o cálculo de checksum.

## Por que usar Code 39 e opções de checksum?
Code 39 é amplamente adotado em logística e manufatura porque codifica dados alfanuméricos sem caracteres especiais. Adicionar um checksum (ou omiti‑lo) permite equilibrar a detecção de erros com a simplicidade—perfeito para etiquetas de inventário, rótulos de envio ou sistemas simples de ponto de venda.

## Pré-requisitos

Antes de mergulharmos, certifique‑se de que você possui o seguinte:

1. **Ambiente de Desenvolvimento .NET** – conhecimento prático do framework .NET e uma IDE como o Visual Studio. Se você é novo no .NET, comece com a documentação oficial: [Microsoft .NET Documentation](https://docs.microsoft.com/en-us/dotnet/).  
2. **Aspose.BarCode para .NET** – faça o download e instale a biblioteca. Documentação e downloads estão disponíveis aqui: [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/) e [Download Aspose.BarCode for .NET](https://releases.aspose.com/barcode/net/).

Agora que cobrimos os pré‑requisitos, vamos avançar para as etapas principais de criação de códigos de barras unidimensionais Code 39.

## Como Gerar Código de Barras: Importar Namespaces
Para começar a trabalhar com Aspose.BarCode para .NET, importe os namespaces necessários ao seu projeto. Adicionar essas instruções `using` fornece acesso às classes de geração de código de barras.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## Como Gerar Código de Barras Code 39 (com e sem checksum)

A seguir criaremos dois códigos de barras: um **sem checksum** e outro **com checksum**. O código é idêntico, exceto pela flag `IsChecksumEnabled`.

```csharp
// The path to the documents directory.
string path = "Your Directory Path";
System.Console.WriteLine("OneCSCode39:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code39Extended, "CODE");

// Example 1: Create a Code 39 barcode without checksum
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.No;
gen.Save($"{path}OneCSCode39WithoutChecksum.png", BarCodeImageFormat.Png);

// Example 2: Create a Code 39 barcode with checksum
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Save($"{path}OneCSCode39WithChecksum.png", BarCodeImageFormat.Png);
```

**O que o código faz**

1. **Instanciar** `BarcodeGenerator` com `EncodeTypes.Code39Extended` e a string de dados `"CODE"`.  
2. **Alternar** `IsChecksumEnabled` para controlar se um dígito de checksum será acrescentado.  
3. **Salvar** cada código de barras como um arquivo PNG na pasta especificada.

Agora você tem duas imagens de código de barras prontas para uso: `OneCSCode39WithoutChecksum.png` e `OneCSCode39WithChecksum.png`.

## Problemas Comuns e Soluções
| Problema | Por que acontece | Solução |
|----------|------------------|---------|
| **Caminho do arquivo não encontrado** | A variável `path` aponta para uma pasta inexistente. | Certifique‑se de que o diretório exista ou use `Directory.CreateDirectory(path)`. |
| **Caracteres inválidos nos dados** | Code 39 suporta apenas alfanuméricos e alguns símbolos especiais. | Use o Code 39 estendido (`Code39Extended`) que suporta o conjunto completo ASCII, como mostrado acima. |
| **Erro de checksum** | Esquecer de definir `IsChecksumEnabled` quando necessário. | Defina explicitamente a flag para `EnableChecksum.Yes` ou `No` conforme seu cenário. |

## Perguntas Frequentes (FAQs):

### Q: Posso usar Aspose.BarCode para .NET com outras linguagens de programação?
A: Aspose.BarCode foi projetado principalmente para .NET, mas a Aspose oferece bibliotecas de código de barras para outras plataformas também.

### Q: Existem opções de licenciamento disponíveis para Aspose.BarCode para .NET?
A: Sim, você pode explorar as opções de licenciamento e solicitar uma licença temporária no site da Aspose: [Aspose.BarCode Licensing](https://purchase.aspose.com/temporary-license/).

### Q: Aspose.BarCode para .NET é adequado para aplicações web?
A: Sim, Aspose.BarCode para .NET pode ser usado em aplicações web, sendo adequado para uma ampla gama de projetos de desenvolvimento.

### Q: Posso personalizar a aparência dos códigos de barras gerados?
A: Absolutamente, você pode personalizar vários aspectos do código de barras, incluindo tamanho, cores e fontes.

### Q: Onde posso obter suporte ou fazer perguntas sobre Aspose.BarCode para .NET?
A: Você pode encontrar respostas e buscar suporte no fórum do Aspose.BarCode: [Aspose.BarCode Forum](https://forum.aspose.com/c/barcode/13).

## Perguntas Frequentes Adicionais

**Q: Qual a diferença entre um código de barras com checksum e um sem checksum?**  
A: Um checksum adiciona um dígito extra que ajuda a detectar erros de transcrição. Use‑o quando a integridade dos dados for crítica.

**Q: Quão grande pode ser o PNG gerado?**  
A: O tamanho é controlado via `gen.Parameters.ImageWidth/Height`. Ajuste essas propriedades antes de chamar `Save`.

**Q: Posso gerar códigos de barras em outros formatos de imagem?**  
A: Sim, Aspose.BarCode suporta JPEG, BMP, GIF, TIFF e mais—basta alterar o enum `BarCodeImageFormat`.

**Q: Existe uma forma de gerar códigos de barras em uma aplicação web sem gravar no disco?**  
A: Você pode salvar em um `MemoryStream` e retornar o array de bytes diretamente ao cliente.

## Conclusão
Seguindo estas etapas simples, você pode **gerar código de barras** imagens em .NET com controle total sobre o manejo de checksum, formato de imagem e estilo visual. Seja gerenciando inventário, processando pedidos ou construindo um portal web habilitado para códigos de barras, Aspose.BarCode para .NET oferece uma solução confiável e amigável ao desenvolvedor.

---

**Última atualização:** 2026-02-25  
**Testado com:** Aspose.BarCode 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}