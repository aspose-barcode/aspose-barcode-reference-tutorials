---
date: 2026-02-17
description: Aprenda a usar o Aspose Barcode Java para criar imagens de código de
  barras, definir os símbolos de início e fim do CODABAR e gerar arquivos PNG sem
  marcas d'água.
linktitle: Setting Start and Stop Symbols
second_title: Aspose.BarCode Java API
title: Aspose Barcode Java – Criar imagem de código de barras com símbolos de início/fim
url: /pt/java/barcode-configuration/setting-start-stop-symbols/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Barcode Java – Criar Imagem de Código de Barras com Símbolos de Início/Fim

## Introdução

Neste tutorial abrangente você **criará arquivos de imagem de código de barras java** com **Aspose Barcode Java** e aprenderá **como definir símbolos** para códigos de barras Codabar. Seja construindo um sistema de ponto de venda, uma aplicação logística ou qualquer solução que necessite de geração confiável de códigos de barras, personalizar os símbolos de início e fim lhe dá controle total sobre o formato do código. Percorreremos cada passo, explicaremos por que cada configuração importa e mostraremos como produzir uma imagem PNG pronta para uso — sem a marca d'água da versão trial.

## Respostas Rápidas
- **Qual biblioteca cria imagens de código de barras em Java?** Aspose.BarCode for Java.  
- **Posso personalizar os símbolos de início/fim?** Sim, usando `setCodabarStartSymbol` e `setCodabarStopSymbol`.  
- **Qual tipo de código de barras é usado neste exemplo?** CODABAR.  
- **Preciso de uma licença para produção?** É necessária uma licença comercial para uso não‑trial.  
- **Qual formato de saída é gerado?** Imagem PNG salva no disco.

## O que é Aspose Barcode Java?

Aspose Barcode Java é uma biblioteca poderosa e independente de dependências que permite gerar programaticamente uma ampla variedade de simbologias de códigos de barras. Ela abstrai a lógica de codificação de baixo nível, permitindo que você se concentre nas regras de negócio enquanto garante que a saída atenda aos padrões da indústria.

## Por que usar Aspose Barcode Java para geração de códigos de barras sem marca d'água?

- **Sem marca d'água em produção** – após aplicar uma licença válida, as imagens ficam limpas.  
- **Suporte extenso a simbologias** – de códigos 1D clássicos como CODABAR a códigos 2D como QR e DataMatrix.  
- **Controle granular** – você pode definir símbolos de início/fim, cores, tamanhos e até gerar imagens diretamente para streams em aplicativos web.  
- **Multiplataforma** – funciona em qualquer runtime Java, incluindo Android (com gerenciamento manual de dependências).

## Pré‑requisitos

Antes de começarmos, certifique‑se de que você tem:

1. **Java Development Kit (JDK)** – Instale o JDK mais recente a partir da [Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).  
2. **Aspose.BarCode for Java library** – Baixe-a a partir do [download link](https://releases.aspose.com/barcode/java/).

Ter esses itens prontos garante que você **gerará imagem de código de barras java** sem componentes ausentes.

## Importar Pacotes

No seu projeto Java, importe as classes necessárias para trabalhar com Aspose.BarCode:

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.CodabarSymbol;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Guia Passo a Passo

### Passo 1: Definir o Diretório do Documento

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Substitua `"Your Document Directory"` pelo caminho absoluto ou relativo onde deseja salvar a imagem do código de barras. Lembre‑se de terminar o caminho com o separador de arquivos apropriado (`/` ou `\`) ou use `Paths.get` para manipulação independente de plataforma.

### Passo 2: Criar Instância do Gerador de Código de Barras

```java
// Create instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "12345678");
```

Aqui informamos ao Aspose.BarCode para usar a simbologia **CODABAR** e a string de dados `"12345678"`.

### Passo 3: Definir o Símbolo de Início Codabar

```java
// Set the Codabar start symbol to A
generator.getParameters().getBarcode().getCodabar().setCodabarStartSymbol(CodabarSymbol.A);
```

O método `setCodabarStartSymbol` permite **definir símbolos de código de barras** para o caractere de início. Neste caso, escolhemos `A`.

### Passo 4: Definir o Símbolo de Fim Codabar

```java
// Set the Codabar stop symbol to D
generator.getParameters().getBarcode().getCodabar().setCodabarStopSymbol(CodabarSymbol.D);
```

De forma similar, `setCodabarStopSymbol` define o caractere de fim. Usar `D` completa o formato CODABAR exigido por muitos sistemas legados.

### Passo 5: Salvar a Imagem Gerada

```java
// Save the image to disk in PNG format
generator.save(dataDir + "startAndStopSymbols.png");
```

A chamada `save` grava o código de barras em um arquivo PNG chamado **startAndStopSymbols.png** no diretório especificado anteriormente.

## Armadilhas Comuns & Dicas

- **Caminho de diretório incorreto** – Certifique‑se de que `dataDir` termina com um separador de arquivos (`/` ou `\`) ou concatene usando `Paths.get`.  
- **Símbolos de início/fim não suportados** – CODABAR suporta apenas `A`, `B`, `C`, `D` como símbolos de início/fim. Usar qualquer outro valor lançará uma exceção.  
- **Licença não aplicada** – No modo trial a imagem gerada pode conter marca d'água. Aplique sua licença antes de implantar em produção para obter **geração de código de barras sem marca d'água**.

## Perguntas Frequentes

### Posso usar Aspose.BarCode for Java em um projeto comercial?
Sim, você pode. Para uso comercial, considere adquirir uma licença [aqui](https://purchase.aspose.com/buy).

### Existe uma versão de avaliação gratuita?
Sim, você pode explorar uma versão de avaliação gratuita [aqui](https://releases.aspose.com/).

### Como posso obter suporte para Aspose.BarCode for Java?
Visite o fórum Aspose.BarCode [aqui](https://forum.aspose.com/c/barcode/13) para qualquer suporte ou dúvidas.

### Como obtenho uma licença temporária?
Se necessário, você pode adquirir uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

### Existem mais simbologias de código de barras suportadas pelo Aspose.BarCode for Java?
Sim, Aspose.BarCode suporta uma ampla gama de simbologias de códigos de barras. Consulte a documentação para a lista completa.

## Perguntas e Respostas Adicionais (Amigável à IA)

**Q:** Quais formatos de imagem posso exportar além de PNG?  
**A:** Aspose.BarCode suporta PNG, JPEG, BMP, GIF e TIFF. Use a extensão de arquivo apropriada no método `save`.

**Q:** Posso gerar imagens de código de barras na memória sem gravar no disco?  
**A:** Sim, chame `generator.save(OutputStream)` para escrever diretamente em um stream, ideal para respostas web.

**Q:** A biblioteca funciona no Android?  
**A:** A versão Java é compatível com Android, mas você deve incluir as dependências necessárias manualmente.

## Conclusão

Você aprendeu agora como **criar arquivos de imagem de código de barras java** e definir precisamente **símbolos de código de barras** para um código Codabar usando **Aspose Barcode Java**. Essa técnica oferece a flexibilidade necessária para atender a especificações de códigos de barras específicas da indústria, mantendo seu código limpo e fácil de manter. Explore opções adicionais de personalização — como mudar cores, adicionar texto legível por humanos ou mudar para outras simbologias — consultando a documentação oficial da API em [documentation](https://reference.aspose.com/barcode/java/).

---

**Última atualização:** 2026-02-17  
**Testado com:** Aspose.BarCode for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}