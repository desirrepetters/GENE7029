---
title: "Aula 03 - Teste de Modelos Evolutivos"
linkTitle: "Aula 03 - Teste de Modelos Evolutivos"
weight: 3
description: >
  Softwares utilizados: ModelFinder no PhyloSuite ou jModelTest
---
<div align="justify">
Com o nosso alinhamento devidamente inspecionado e corrigido, a próxima etapa é descobrir qual o modelo evolutivo mais se ajusta ao nosso alinhamento, para que possamos implementá-lo em nossa análise filogenética. 
<br><br>
Para este tutorial, utilizaremos o plugin do ModelFinder dentro do PhyloSuite, e como possibilidade extra, podemos utilizar o jModelTest (em sua versão instalada ou no portal <a href="https://www.phylo.org/">CIPRES</a>). Se você ainda não tem o PhyloSuite instalado com os plugins do ModelFinder e do IQ-TREE configurados, pode encontrar instruções <a href="https://gene7029.netlify.app/2022/download/phylosuite">aqui</a>. Caso prefira utilizar o jModelTest, pode encontrar instruções de instalação <a href="https://gene7029.netlify.app/2022/download/jmodeltest">aqui</a>.
<br><br>
Clique nos links abaixo para baixar os arquivos que serão utilizados nesta prática:
<br><br>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_03/aula_03.zip">Link para pasta com todos os arquivos (formato zip)</a></li>
<br>
Para baixar os arquivos individualmente:
<br><br>
<ul>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_03/Aula_03_Alinhamento_Corrigido.fasta">Alinhamento do MAFFT já editado (formato FASTA)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_03/Aula_03_Alinhamento_Corrigido_fasta_mrbayes.log">Arquivo de saída do ModelFinder (formato LOG)</a></li>
</ul>
</div>

## Teste de modelo evolutivo com o plugin do ModelFinder no PhyloSuite

<div align="justify">
Após abrir o PhyloSuite e definir sua pasta de trabalho, podemos realizar o teste do modelo evolutivo clicando na opção “<i>ModelFinder</i>” dentro do menu “<i>Phylogeny</i>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_03/aula_03_1.png" alt="Opção do ModelFinder dentro do menu Phylogeny do PhyloSuite" align="center">
</center>
<br><br>
Em seguida, procure o arquivo “<b>Aula_03_Alinhamento_Corrigido.fasta</b>” em seu computador. Na opção “<i>Sequence Type</i>” selecione DNA, em “<i>Criterion</i>” selecione “<i>Corrected AIC (AICc)</i>” (no arquivo final todos estarão apresentados, mas selecionar esta opção dará um destaque a este critério). Em “<i>Model</i>”, é possível selecionar “<i>Mrbayes</i>” para testar apenas os modelos que podem ser implementados no MrBayes. As outras opções não precisam ser modificadas. Em seguida, aperte em “<i>Start</i>” e acompanhe o processo por meio da barra de progresso:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_03/aula_03_2.png" alt="Opções para configuração do ModelFinder dentro do PhyloSuite" align="center">
</center>
<br><br>
Em alguns casos o programa pode retornar a mesma janela de erro que vimos ao produzir alinhamentos com o MAFFT, mas apesar disso, o teste de modelos evolutivos foi concluído. Para encontrar o arquivo de saída, basta acessar a pasta “<i>GenBank file</i>”, em seguida “<i>files</i>”, “<i>ModelFinder_results</i>” e a pasta com a data e horário em você utilizou o software. Dentro desta pasta teremos diversos arquivos, e as informações mais importantes estarão no arquivo com a extensão “.log”. No nosso exemplo, será o arquivo “<b>Aula_03_Alinhamento_Corrigido_fasta_mrbayes.log</b>”.
<br><br>
Ao abrir este arquivo, observaremos algumas informações relativas ao teste e ao software, lista das sequências analisadas, entre outras. Devemos procurar pelas linhas que informem os modelos evolutivos mais adequados de acordo com os três diferentes critérios adotados pelo ModelFinder: “<i>Bayesian Information Criterion</i>”, “<i>Akaike Information Criterion</i>” e “<i>Corrected Akaike Information Criterion</i>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_03/aula_03_3.png" alt="Lista dos melhores modelos evolutivos de acordo com os critérios AIC, AICc e BIC no arquivo de saída do ModelFinder" align="center">
</center>
<br><br>
Como informamos ao ModelFinder que gostaríamos de escolher o modelo com base no critério AICc antes de rodar a análise, a linha “<i>Best-fit model</i>” mostra o modelo mais adequado com base neste critério. Entretanto, o software ainda apresenta os outros modelos mais adequados com base nos outros critérios, permitindo a comparação entre eles.
<br><br>
</div>

## Teste de modelo evolutivo com o jModelTest

<div align="justify">
Também é possível realizar o teste de modelos evolutivos no jModelTest. Após abrir o programa, clique na opção “<i>Load DNA alignment</i>” dentro do menu “File”, escolha o arquivo de alinhamento e clique em Abrir. Para este exemplo também utilizaremos o arquivo “<b>Aula_03_Alinhamento_Corrigido.fasta</b>”. O jModelTest aceita arquivos no formato FASTA ou no formato PHYLIP:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_03/aula_03_4.png" alt="Opção "Load DNA alignment" no menu "File" do jModelTest" align="center">
</center>
<br><br>
Se o arquivo for carregado adequadamente, veremos uma mensagem com informações sobre o número total de sequências e tamanho do alinhamento na janela inicial:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_03/aula_03_5.png" alt="Informações sobre o alinhamento no jModelTest: 81 sequências no total e 687 sítios" align="center">
</center>
<br><br>
Há duas etapas distintas para determinar o modelo evolutivo mais adequado. Primeiro, clique em “<i>Compute likelihood scores</i>” no menu “<i>Analysis</i>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_03/aula_03_6.png" alt="Opção "Compute likelihood scores" no menu Analysis do jModelTest" align="center">
</center>
<br><br>
Em seguida, vamos configurar os parâmetros necessários. Na opção “<i>Number of substitution schemes</i>” selecione “3”. Esta opção irá testar apenas os modelos que podem ser implementados no MrBayes: isso será importante para simplificar o arquivo de saída e não testar uma extensa lista de modelos que nem podem ser utilizados. No campo “<i>Rate variation</i>” selecione as opções “+I” e “G” para incluir as taxas de variação entre sítios de uma sequência: “+I” para levar em consideração a proporção de sítios invariáveis e “+G” para a distribuição gamma. Em “<i>Base tree search</i>”, a opção NNI fará uma estimativa mais rápida, e a opção SPR será mais lenta. O restante dos campos pode ser mantido sem modificações:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_03/aula_03_7.png" alt="Opções para configuração do jModelTest" align="center">
</center>
<br><br>
O progresso da análise pode ser acompanhado na próxima janela, em que o software informa quantos modelos já foram testados, o tempo decorrido, e a porcentagem já concluída da análise:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_03/aula_03_8.png" alt="Janela de Progresso do jModelTest" align="center">
</center>
<br><br>
Após a conclusão desta etapa, podemos calcular o melhor modelo segundo diferentes critérios. Caso deseje utilizar o critério AIC, selecione a opção “<i>Do AIC calculations...</i>” dentro do menu “<i>Analysis</i>”. Marque a opção “<i>Use AICc correction</i>” caso deseje utilizar o critério AICc:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_03/aula_03_9.png" alt="Opções para determinar o modelo segundo o critério AIC ou AICc" align="center">
</center>
<br><br>
Já para utilizar o critério BIC, basta selecionar a opção “<i>Do BIC calculations...</i>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_03/aula_03_10.png" alt="Opções para determinar o modelo segundo o critério BIC" align="center">
</center>
<br><br>
Para exibir a tabela com os resultados, clique na opção “<i>Show results table</i>” no menu “<i>Results</i>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_03/aula_03_11.png" alt="Opção Show results table no menu Results do jModelTest" align="center">
</center>
<br><br>
Na janela “<i>Results</i>”, escolha o critério de interesse (nesse caso, vamos escolher AICc), e para ordenar a tabela de acordo com o melhor critério, clique em “<I>AICc</i>” no cabeçalho (ou em “<i>BIC</i>” caso escolha o critério BIC). O modelo evolutivo mais adequado estará destacado em vermelho (com valor de deltaAICc igual a 0.0), e, neste caso, é o GTR +I +G.
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_03/aula_03_12.png" alt="Janela com os melhores modelos evolutivos para o critério AICc, com destaque para o modelo GTR+I+G em vermelho" align="center">
</center>
<br><br>
</div>

## Aula em vídeo

<br>
<div align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/Az74lshErkE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe> 
<br><br>
Clique <a href="https://photos.app.goo.gl/8KZEPZ4SfGgkcQrY9">aqui</a> para fazer o download do vídeo.
<br><br>
</div>
