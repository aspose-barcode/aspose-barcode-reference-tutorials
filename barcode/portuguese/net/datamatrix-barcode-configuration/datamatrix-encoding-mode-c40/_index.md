---
date: 2026-01-15
description: Aprenda a salvar arquivos PNG enquanto usa o Modo de Codificação DataMatrix
  (C40) com Aspose.BarCode para .NET – um tutorial passo a passo de código de barras.
linktitle: DataMatrix Encoding Mode (C40)
second_title: Aspose.BarCode .NET API
title: Como salvar PNG usando DataMatrix C40 com Aspose.BarCode
url: /pt/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Modo de Codificação DataMatrix (C40) com Aspose.BarCode para .NET

## Introdução

Se você está procurando um guia claro e prático sobre **como salvar PNG** enquanto gera códigos de barras DataMatrix, você está no lugar certo. Seja construindo um sistema de inventário, um gerador de etiquetas de envio ou qualquer solução que precise de códigos de barras compactos e de alta densidade, dominar o modo de codificação C40 lhe proporcionará eficiência de tamanho e representação confiável dos dados. Neste tutorial, percorreremos um processo de criação de **código de barras passo a passo**, desde os pré‑requisitos até a saída final em PNG, usando Aspose.BarCode para .NET.

## Respostas Rápidas
- **O que significa “how to save png”?** Salvar o código de barras gerado como um arquivo de imagem PNG.  
- **Qual modo de codificação é abordado?** Codificação DataMatrix C40.  
- **Preciso de uma licença?** Uma avaliação gratuita funciona para testes; uma licença é necessária para produção.  
- **Posso executar isso no .NET Core?** Sim, o Aspose.BarCode suporta .NET Framework e .NET Core.  
- **Qual formato de arquivo é produzido?** Imagem PNG (Portable Network Graphics).

## Como Salvar PNG com Codificação DataMatrix C40
Salvar o código de barras como PNG é a etapa final depois de configurar o gerador. O método `Save` recebe o caminho do arquivo, o nome desejado e o formato de imagem (`BarCodeImageFormat.Png`). Isso garante que o código de barras seja armazenado em um formato sem perdas que funciona em navegadores, impressoras e dispositivos móveis.

## O que é o Modo de Codificação DataMatrix (C40)?
C40 é um conjunto de caracteres eficiente para dados alfanuméricos, permitindo que você compacte mais informações em um símbolo DataMatrix menor. É especialmente útil quando você precisa codificar texto que contém letras, números e um conjunto limitado de caracteres especiais.

## Por que Usar Aspose.BarCode para .NET?
- **Controle total** sobre dimensões do código de barras, correção de erros e modos de codificação.  
- **Geração sem dependências** – nenhum serviço externo necessário.  
- **Suporte multiplataforma** para .NET Framework, .NET Core e .NET 5/6+.  

## Pré‑requisitos

Antes de mergulharmos no código, certifique‑se de que você tem o seguinte:

1. **Ambiente de Desenvolvimento .NET** – Visual Studio, Rider ou qualquer IDE que suporte C#.  
2. **Aspose.BarCode para .NET** – instalado via NuGet ou o instalador oficial. Veja a [documentação](https://reference.aspose.com/barcode/net/) para detalhes.  
3. **Conhecimento básico de C#** – você deve estar confortável com namespaces, classes e instruções using.  
4. **Pasta com permissão de escrita** – um diretório na sua máquina onde o PNG será salvo.

## Importando Namespaces Necessários

Adicione o namespace necessário no topo do seu arquivo fonte C# para que você possa acessar as classes de geração de código de barras:

```csharp
using Aspose.BarCode.Generation;
```

## Geração de Código de Barras Passo a Passo

Abaixo está um walkthrough de **código de barras passo a passo**. Cada etapa é explicada em linguagem simples, e os blocos de código originais são mantidos inalterados para conveniência de copiar‑e‑colar.

### Passo 1: Definir o Caminho do Diretório
Defina a pasta onde a imagem PNG será armazenada. Substitua o placeholder por um caminho real na sua máquina.

```csharp
string path = "Your Directory Path";
```

### Passo 2: Configurar a Geração do Código de Barras
Crie uma instância `BarcodeGenerator`, especifique `EncodeTypes.DataMatrix` e forneça os dados que deseja codificar.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE.BARCODE"))
{
    // Additional steps go here
}
```

### Passo 3: Personalizar o Código de Barras
Configure a X‑dimension (largura em pixels dos módulos) e altere o modo de codificação para C40.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 6;
gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.C40;
```

### Passo 4: Salvar a Imagem do Código de Barras
Finalmente, salve o código de barras gerado como um arquivo PNG. Esta é a resposta concreta para **como salvar png** com Aspose.BarCode.

```csharp
gen.Save($"{path}DataMatrixEncodeModeC40.png", BarCodeImageFormat.Png);
```

Ao executar o programa, você encontrará `DataMatrixEncodeModeC40.png` na pasta especificada, pronto para ser usado em relatórios, etiquetas ou páginas web.

## Problemas Comuns & Dicas

- **Caminho Inválido** – Certifique-se de que o diretório existe e que você tem permissões de escrita; caso contrário, `gen.Save` lançará uma exceção.  
- **Modo de Codificação Incorreto** – Se precisar codificar caracteres fora do conjunto C40, altere para `DataMatrixEncodeMode.Auto` ou outro modo apropriado.  
- **Tamanho da Imagem** – Ajuste `XDimension.Pixels` para aumentar ou diminuir o tamanho geral do código de barras sem afetar a legibilidade.

## Perguntas Frequentes

**Q: O que é o Modo de Codificação DataMatrix (C40)?**  
A: C40 é um esquema de codificação alfanumérico compacto para símbolos DataMatrix, ideal para textos que incluem letras, números e um conjunto limitado de caracteres especiais.

**Q: Onde posso encontrar a documentação do Aspose.BarCode para .NET?**  
A: Você pode encontrar a documentação [aqui](https://reference.aspose.com/barcode/net/). Ela fornece orientações detalhadas sobre todos os tipos de códigos de barras e opções de codificação.

**Q: O Aspose.BarCode para .NET é compatível com todas as versões do .NET?**  
A: Sim, a biblioteca suporta uma ampla gama de versões do .NET, desde .NET Framework 4.5+ até .NET 6 e posteriores.

**Q: Posso experimentar o Aspose.BarCode para .NET antes de comprar?**  
A: Sim, você pode explorar uma avaliação gratuita do Aspose.BarCode para .NET visitando [este link](https://releases.aspose.com/). Ela permite testar os recursos e capacidades da biblioteca.

**Q: Onde posso obter suporte para o Aspose.BarCode para .NET?**  
A: Você pode encontrar uma comunidade de apoio e acessar suporte para Aspose.BarCode para .NET no [fórum da Aspose](https://forum.aspose.com/c/barcode/13).

## Conclusão

Seguindo este guia **código de barras passo a passo**, você agora sabe exatamente **como salvar PNG** gerados com codificação DataMatrix C40 usando Aspose.BarCode para .NET. Essa abordagem lhe dá controle total sobre a aparência, tamanho e representação dos dados do código de barras, facilitando a integração de códigos de alta qualidade em qualquer aplicação .NET.

---

**Última atualização:** 2026-01-15  
**Testado com:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}