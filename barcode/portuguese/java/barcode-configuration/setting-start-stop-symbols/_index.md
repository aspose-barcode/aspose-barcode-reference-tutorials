---
date: 2025-12-17
description: Aprenda como criar imagem de código de barras em Java e como definir
  símbolos usando Aspose.BarCode. Este guia passo a passo mostra como gerar um código
  de barras Codabar com símbolos de início/fim personalizados.
linktitle: Setting Start and Stop Symbols
second_title: Aspose.BarCode Java API
title: Criar Imagem de Código de Barras em Java – Definindo Símbolos de Início e Fim
url: /pt/java/barcode-configuration/setting-start-stop-symbols/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Imagem de Código de Barras Java – Definindo Símbolos de Início e Fim

## Introdução

Neste tutorial abrangente, você **criará arquivos de create barcode image java** com Aspose.BarCode for Java e aprenderá **como definir símbolos** para códigos de barras Codabar. Seja você quem esteja construindo um sistema de ponto de venda, uma aplicação logística ou qualquer solução que precise de geração confiável de códigos de barras, personalizar os símbolos de início e fim lhe dá controle total sobre o formato do código. Vamos percorrer cada passo, explicar por que cada configuração importa e mostrar como produzir uma imagem PNG pronta para uso.

## Respostas Rápidas
- **Qual biblioteca cria imagens de código de barras em Java?** Aspose.BarCode for Java.  
- **Posso personalizar os símbolos de início/fim?** Sim, usando `setCodabarStartSymbol` e `setCodabarStopSymbol`.  
- **Qual tipo de código de barras é usado neste exemplo?** CODABAR.  
- **Preciso de licença para produção?** Uma licença comercial é necessária para uso não‑trial.  
- **Qual formato de saída é gerado?** Imagem PNG salva em disco.

## O que é “create barcode image java”?

Gerar uma imagem de código de barras em Java significa produzir programaticamente uma representação visual (geralmente PNG, JPG ou BMP) de uma simbologia de código de barras que pode ser lida por leitores padrão. Aspose.BarCode oferece uma API fluente que abstrai os detalhes de codificação de baixo nível, permitindo que você se concentre na lógica de negócios.

## Por que usar Aspose.BarCode para gerar código de barras com Aspose?

Aspose.BarCode oferece:
- **Amplo suporte a simbologias** (incluindo CODABAR, QR, DataMatrix, etc.).
- **Controle granular** sobre aparência, tamanho e opções de codificação.
- **Compatibilidade multiplataforma** com qualquer runtime Java.
- **Nenhuma dependência externa**, facilitando a implantação.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

1. **Java Development Kit (JDK)** – Instale o JDK mais recente a partir da [Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).  
2. **Aspose.BarCode for Java library** – Baixe-a no [download link](https://releases.aspose.com/barcode/java/).

Ter esses itens prontos garante que você possa **generate barcode image java** sem componentes ausentes.

## Importar Pacotes

No seu projeto Java, importe as classes necessárias para trabalhar com Aspose.BarCode:

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.CodabarSymbol;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Guia Passo a Passo

### Etapa 1: Definir o Diretório do Documento

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Substitua `"Your Document Directory"` pelo caminho absoluto ou relativo onde deseja que a imagem do código de barras seja salva.

### Etapa 2: Criar Instância do Gerador de Código de Barras

```java
// Create instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "12345678");
```

Aqui informamos ao Aspose.BarCode para usar a simbologia **CODABAR** e a string de dados `"12345678"`.

### Etapa 3: Definir Símbolo de Início Codabar

```java
// Set the Codabar start symbol to A
generator.getParameters().getBarcode().getCodabar().setCodabarStartSymbol(CodabarSymbol.A);
```

O método `setCodabarStartSymbol` permite **how to set symbols** para o caractere de início. Neste caso, escolhemos `A`.

### Etapa 4: Definir Símbolo de Fim Codabar

```java
// Set the Codabar stop symbol to D
generator.getParameters().getBarcode().getCodabar().setCodabarStopSymbol(CodabarSymbol.D);
```

De forma similar, `setCodabarStopSymbol` define o caractere de parada. Usar `D` completa o formato CODABAR exigido por muitos sistemas legados.

### Etapa 5: Salvar a Imagem Gerada

```java
// Save the image to disk in PNG format
generator.save(dataDir + "startAndStopSymbols.png");
```

A chamada `save` grava o código de barras em um arquivo PNG chamado **startAndStopSymbols.png** no diretório especificado anteriormente.

### Armadilhas Comuns & Dicas

- **Caminho de diretório incorreto** – Garanta que `dataDir` termine com um separador de arquivos (`/` ou `\`) ou concatene usando `Paths.get`.  
- **Símbolos de início/fim não suportados** – CODABAR aceita apenas A, B, C, D como símbolos de início/fim. Qualquer outro valor lançará uma exceção.  
- **Licença não aplicada** – No modo trial a imagem gerada pode conter marca d'água. Aplique sua licença antes de implantar em produção.

## Conclusão

Agora você aprendeu como **create barcode image java** e como **how to set symbols** precisamente para um código de barras Codabar usando Aspose.BarCode. Essa técnica oferece a flexibilidade necessária para atender a especificações de código de barras específicas da indústria, mantendo seu código limpo e fácil de manter.

Explore opções adicionais de personalização — como alterar cores, adicionar texto legível por humanos ou mudar para outras simbologias — consultando a documentação oficial da API em [documentation](https://reference.aspose.com/barcode/java/).

## Perguntas Frequentes

### Posso usar Aspose.BarCode for Java em um projeto comercial?
Sim, você pode. Para uso comercial, considere adquirir uma licença [aqui](https://purchase.aspose.com/buy).

### Existe uma versão de avaliação gratuita disponível?
Sim, você pode experimentar a versão de avaliação gratuita [aqui](https://releases.aspose.com/).

### Como posso obter suporte para Aspose.BarCode for Java?
Visite o fórum Aspose.BarCode [aqui](https://forum.aspose.com/c/barcode/13) para qualquer suporte ou dúvidas.

### Como obtenho uma licença temporária?
Se necessário, você pode adquirir uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

### Existem mais simbologias de código de barras suportadas pelo Aspose.BarCode for Java?
Sim, o Aspose.BarCode suporta uma ampla gama de simbologias de código de barras. Consulte a documentação para a lista completa.

**Perguntas e Respostas Adicionais**

**Q: Quais formatos de imagem posso exportar além de PNG?**  
A: Aspose.BarCode suporta PNG, JPEG, BMP, GIF e TIFF. Use a extensão de arquivo apropriada no método `save`.

**Q: Posso gerar imagens de código de barras na memória sem gravar em disco?**  
A: Sim, chame `generator.save(OutputStream)` para escrever diretamente em um stream, útil para respostas web.

**Q: A biblioteca funciona no Android?**  
A: A versão Java é compatível com Android, mas você deve incluir manualmente as dependências necessárias.

---

**Última atualização:** 2025-12-17  
**Testado com:** Aspose.BarCode for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}