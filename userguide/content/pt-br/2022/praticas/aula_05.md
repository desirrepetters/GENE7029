---
title: "Aula 05 - Concatenação e Teste de Modelo Evolutivo em alinhamento concatenado"
linkTitle: "Aula 05 - Concatenação e Teste de Modelo Evolutivo em alinhamento concatenado"
weight: 5
description: >
  Softwares utilizados: ModelFinder e PartitionFinder no PhyloSuite
---
<div align="justify">
Há diversas situações em que se faz necessário utilizar mais de um gene ou região genômica na análise filogenética para que seja possível identificar um organismo ou delimitar espécies com sucesso. Neste exemplo, iremos criar um alinhamento concatenado e estimar o modelo evolutivo mais adequado para sua análise. Esses resultados serão a base para nossa próxima atividade, em que finalmente realizaremos a análise filogenética com o alinhamento concatenado.
<br><br>
Para este tutorial, utilizaremos os plugin do ModelFinder e do PartitionFinder dentro do PhyloSuite. Se você ainda não tem o PhyloSuite instalado com estes plugins configurados, pode encontrar instruções <a href="https://cursodefilogeniaufpr.netlify.app/docs/download/phylosuite">aqui</a>.
<br><br>
Clique nos links abaixo para baixar os arquivos que serão utilizados nesta prática:
<br><br>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_05/aula_05.zip">Link para pasta com todos os arquivos (formato zip)</a></li>
<br>
Para baixar os arquivos individualmente:
<br><br>
<ul>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_05/Aula_05_EF_Consenso.fasta">Sequência Consenso, região EF (formato FASTA)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_05/Aula_05_EF_Referencias.fasta">Sequências de referência da região EF (formato FASTA)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_05/Aula_05_EF_Outgroup.fasta">Sequência do outgroup da região EF (formato FASTA)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_05/Aula_05_EF_Todas.fasta">Arquivo com todas as sequências da região EF (formato FASTA)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_05/Aula_05_TUB_Consenso.fasta">Sequência Consenso, região TUB (formato FASTA)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_05/Aula_05_TUB_Referencias.fasta">Sequências de referência da região TUB (formato FASTA)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_05/Aula_05_TUB_Outgroup.fasta">Sequência do outgroup da região TUB (formato FASTA)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_05/Aula_05_TUB_Todas.fasta">Arquivo com todas as sequências da região TUB (formato FASTA)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_05/Aula_05_Tabela.pdf">Tabela das sequências de referência</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_05/Aula_05_EF_Alinhamento_MAFFT.fasta">Alinhamento bruto do MAFFT da região EF (formato FASTA)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_05/Aula_05_TUB_Alinhamento_MAFFT.fasta">Alinhamento bruto do MAFFT da região TUB (formato FASTA)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_05/Aula_05_EF_Alinhamento_Corrigido.fasta">Alinhamento do MAFFT da região EF já editado (formato FASTA)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_05/Aula_05_TUB_Alinhamento_Corrigido.fasta">Alinhamento do MAFFT da região TUB2 já editado (formato FASTA)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_05/Aula_05_Alinhamento_Concatenado.fas">Alinhamento concatenado (formato FASTA)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_05/Aula_05_Alinhamento_Concatenado.phy">Alinhamento concatenado (formato PHYLIP)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_05/Aula_05_Resultado_ModelFinder.log">Arquivo de saída do ModelFinder com o melhor modelo evolutivo (formato LOG)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_05/Aula_05_ModelFinder_Para_Configurar.nex">Arquivo do ModelFinder com modelo evolutivo para configuração da análise filogenética</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_05/Aula_05_Resultado_PartitionFinder.txt">Arquivo de saída do PartitionFinder com o melhor modelo evolutivo (formato TXT)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_05/Aula_05_PartitionFinder_Para_Configurar.nex">Arquivo do PartitionFinder com modelo evolutivo para configuração da análise filogenética</a></li>
</ul>
</div>

## Concatenando alinhamentos 

<div align="justify">
Para realizar uma análise filogenética concatenada é necessário possuir um arquivo único em que os alinhamentos individuais das diferentes regiões de interesse estejam reunidos, como se representassem um único alinhamento. Existem diversas formas de produzir este arquivo, e muitos o fazem de forma manual copiando e colando as sequências num único arquivo final. Embora seja possível, não recomendamos fazê-lo de forma manual por ser um processo demorado, e também pela possibilidade de erros. 
<br><br>
Para realizar este processo de forma automatizada, existe a possibilidade de utilizar softwares como o SequenceMatrix, o MEGA X e o próprio PhyloSuite. Neste tutorial, focaremos no PhyloSuite pela facilidade em produzir o arquivo concatenado e já direcioná-lo para as análises seguintes (teste de modelo evolutivo e análise filogenética), simplificando o processo como um todo.
<br><br>
Nesta atividade, vamos utilizar o alinhamento da região EF que produzimos na Aula 02, e concatená-lo a um alinhamento da região TUB2. Para simplificar, já partiremos dos alinhamentos prontos nos arquivos “<b>Aula_05_EF_Alinhamento_Corrigido.fasta</b>” e “<b>Aula_05_TUB_Alinhamento_Corrigido.fasta</b>”, e não descreveremos novamente todo o processo para obter o alinhamento da região TUB2. Caso tenha dúvidas ou queira produzir o alinhamento da região TUB2 desde o começo, utilize os arquivos “<b>Aula_05_TUB_Consenso.fasta</b>”, “<b>Aula_05_TUB_Referencias.fasta</b>” e “<b>Aula_05_TUB_Outgroup.fasta</b>” ou diretamente o arquivo “<b>Aula_05_TUB_Todas.fasta</b>” e siga os passos do tutorial da Aula 02.
<br><br>
Observando os arquivos “<b>Aula_05_EF_Alinhamento_Corrigido.fasta</b>” e “<b>Aula_05_TUB_Alinhamento_Corrigido.fasta</b>” você irá notar que em ambos os arquivos as sequências de um mesmo organismo têm nomes idênticos. Este detalhe é crucial para que a concatenação seja realizada corretamente pelos softwares. Caso exista alguma diferença nos nomes, mesmo que seja de apenas um único caractere, os softwares não serão capazes de estabelecer a correspondência entre os arquivos sendo concatenados e tratarão as sequências como pertencentes à organismos diferentes. Tenha sempre isto em mente ao produzir os alinhamentos do seu material de estudo, para evitar problemas futuros. 
<br><br>
Para iniciar a atividade, iremos abrir o PhyloSuite e definir a pasta de trabalho para a pasta que contiver os alinhamentos a serem concatenados (neste exemplo, “aula_05”). Podemos iniciar o processo de concatenação de sequências clicando na opção “<i>Concatenate Sequence</i>” dentro do menu “<i>Alignment</i>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_05/aula_05_1.png" alt="Opção Concatenate Sequence no menu Alignment dentro do PhyloSuite" align="center">
</center>
<br><br>
Na janela seguinte precisamos selecionar os arquivos a serem concatenados na opção “<i>Input</i>”. No bloco “<i>Parameter</i>”, podemos selecionar os formatos de arquivos de saída que nos interessam. Nesse caso, deixaremos todas as opções selecionadas. Na opção “<i>Export file name</i>”, digite o nome desejado para o arquivo de saída (neste caso “<b>Aula_05_Alinhamento_Concatenado</b>”). Não é necessário selecionar a opção “<i>Linear figure</i>”. Podemos iniciar a concatenação clicando em “<i>Start</i>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_05/aula_05_2.png" alt="Janela de configuração da função Concatenate Sequence dentro do PhyloSuite" align="center">
</center>
<br><br>
É muito comum que nem todos os indivíduos tenham sequências para todas as regiões sendo analisadas e concatenadas. Mesmo que nem todas as sequências estejam disponíveis, ainda é possível incluir estes indivíduos na análise sem maiores problemas. Quando isso acontecer, a janela “<i>Concatenation Warning</i>” será aberta. Ela informará que o PhyloSuite detectou a ausência de algumas sequências (“<i>missing genes</i>”, genes faltantes), e que adicionará “?” à região que seria preenchida por tais sequências no alinhamento concatenado. Clicando em “<i>Show details</i>”, ele abrirá a lista das sequências faltantes, com o nome do organismo e o alinhamento em que a sequência não existia. Para consultar a lista completa também é possível abrir o arquivo “<i>missing_genes.txt</i>”. Clique em OK para prosseguir:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_05/aula_05_3.png" alt="Janela Concatenation Warning mostrando as sequências faltantes nos alinhamentos" align="center">
</center>
<br><br>
Ao concluir a concatenação, o PhyloSuite fornecerá opções para transferir o arquivo concatenado para análises subsequentes. Nos próximos passos iremos explorar a possibilidade de transferir o arquivo concatenado diretamente para as análises de teste de modelo evolutivo.
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_05/aula_05_4.png" alt="Opções de redirecionamento dos resultados do concatenamento no PhyloSuite" align="center">
</center>
<br><br>
</div>

## Teste de modelo evolutivo com o ModelFinder

<div align="justify">
Para testar o modelo evolutivo no alinhamento concatenado usando o ModelFinder, clique na opção “<i>Import the results to ModelFinder</i>” na janela mostrada anteriormente. A janela de configuração do ModelFinder será aberta e boa parte das opções já estará preenchida automaticamente. No campo “<i>Input</i>”, na opção “<i>Alignment File</i>”, devemos conferir se o arquivo concatenado foi selecionado corretamente (nesse caso, “<b>Aula_05_Alinhamento_Concatenado.fas</b>”). No bloco “<i>Parameters</i>”, selecionaremos como “<i>Sequence Type</i>” a opção DNA, “<i>Corrected AIC (AICc)</i>” como Criterion e em “Model for”, a opção MrBayes. 
<br><br>
Como agora estamos trabalhando com um alinhamento concatenado, existem diferentes possibilidades para testar o modelo: podemos testar os genes separadamente, bem como testar o conjunto inteiro sob um mesmo modelo. No campo “<i>Partition Mode</i>”, selecionaremos as opções “<i>Edge-unlinked</i>” para testar os genes separadamente, e “<i>Merge</i>” para também testar os dois genes sob o mesmo modelo. Dessa forma, podemos comparar os resultados e decidir se trabalharemos com modelos distintos para os genes ou não. Após configurar estas opções, clique em “<i>Start</i>” e acompanhe o processo pela barra de progresso:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_05/aula_05_5.png" alt="Janela de configuração do ModelFinder dentro do PhyloSuite" align="center">
</center>
<br><br>
Ao concluir o teste, é possível implementar os resultados no IQ-TREE ou MrBayes. Neste momento, vamos selecionar “<i>Open the results folder</i>” para interpretar os resultados e entender qual critério o PhyloSuite utiliza para implementar o modelo evolutivo automaticamente:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_05/aula_05_6.png" alt="Opções de redirecionamento dos resultados do ModelFinder dentro do PhyloSuite" align="center">
</center>
<br><br>
Na pasta de resultados, procure pelo arquivo “<b>PhyloSuite_ModelFinder</b>” e abra no Bloco de Notas ou Notepad ++. Ao longo do arquivo estarão presentes várias informações sobre a análise. Neste arquivo do exemplo, nas linhas 117 e 118 teremos o valor de Score segundo o critério de AICc para os alinhamentos separadamente e a soma destes valores representa o score segundo o critério de AICc para uma análise incorporando modelos distintos para cada um dos alinhamentos. Ou seja, foi calculado um valor de 9044,823 para o alinhamento da região EF sob o modelo evolutivo SYM+I+G e um valor de 5245,662 para o alinhamento da região TUB sob o modelo evolutivo SYM+G, totalizando um score de 14288,398 para a análise usando os modelos evolutivos distintos para cada alinhamento.Por outro lado, ao juntar os dois alinhamentos num mesmo conjunto e aplicar um único modelo evolutivo, foi obtido um score de 14090,163 sob o modelo GTR+F+I+G. Uma vez que o melhor modelo evolutivo segundo o critério AICc será aquele que apresentar o menor score, a análise nos sugere que seria melhor analisar os dois alinhamentos sob o modelo GTR+F+I+G (score 14090,163, foi o menor) ao invés de analisar os alinhamentos separadamente com diferentes modelos (score 14288,398, foi o maior). 
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_05/aula_05_7.png" alt="Resultado do teste de modelo evolutivo do alinhamento concatenado, visualizado no Notepad ++" align="center">
</center>
<br><br>
Levando isto em consideração, percebemos que este foi o critério do PhyloSuite para informar GTR+F+I+G como o “<i>BEST-FIT PARTITION MODEL</i>” nas linhas 123 e 124 do exemplo. Se seguirmos com estes resultados para o IQ-TREE ou MrBayes, veremos que a opção automática do PhyloSuite irá sugerir analisar os dois alinhamentos sob o mesmo modelo evolutivo.
<br><br>
</div>

## Teste de modelo evolutivo com o PartitionFinder

<div align="justify">
Para testar o modelo evolutivo no alinhamento concatenado usando o ModelFinder, clique na opção “<i>Import the results to PartitionFinder</i>” na janela mostrada anteriormente. 	A janela de configuração do PartitionFinder será aberta e boa parte das opções já estará preenchida automaticamente. No campo “<i>Input</i>”, na opção “<i>Alignment File</i>”, devemos conferir se o arquivo concatenado foi selecionado corretamente (nesse caso, “<b>Aula_05_Alinhamento_Concatenado.phy</b>”). Diferentemente do ModelFinder, mesmo sem uma configuração específica prévia, o PartitionFinder já avaliará o alinhamento concatenado testando modelos diferentes para os genes separadamente, e testando o conjunto inteiro sob um mesmo modelo. No bloco “<i>Configuration</i>”, selecionaremos como “<i>branchlengths</i>” a opção “<i>unlinked</i>”, nos campos “<i>model</i>” e "<i>search</i>” selecionaremos a opção “<i>all</i>” e em “<i>model_selection</i>” selecionaremos o critério “AICc”. Após configurar estas opções, clique em “<i>Start</i>” e acompanhe o processo pela barra de progresso:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_05/aula_05_8.png" alt="Janela de configuração do PartitionFinder dentro do PhyloSuite" align="center">
</center>
<br><br>
Ao concluir o teste, o PhyloSuite fornecerá opções para utilizar os resultados em análises filogenéticas com o IQ-TREE ou o MrBayes. Neste momento, vamos selecionar “<i>Open the results folder</i>” para interpretar os resultados e entender qual critério o PhyloSuite utilizará para implementar o modelo evolutivo automaticamente se seguirmos com as análises filogenéticas. 
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_05/aula_05_9.png" alt="Janela de redirecionamento dos resultados do PartitionFinder dentro do PhyloSuite" align="center">
</center>
<br><br>
Na pasta de resultados, procure pela pasta “<i>analysis</i>” e dentro dela, pelo arquivo “<i>best_scheme</i>” e abra no Bloco de Notas ou Notepad ++. Ao longo do arquivo estarão presentes várias informações sobre a análise. Neste arquivo do exemplo, entre as linhas 10 e 20 teremos a descrição do melhor particionamento que o PartitionFinder encontrou para o alinhamento. A linha “<i>Number of subsets</i>” informa que foi melhor analisar todo o conjunto como apenas uma partição, com o modelo GTR+I+G, conforme observado na linha 20. Diferentemente do ModelFinder, embora tenham sido testadas várias formas de dividir o conjunto de alinhamentos, o arquivo “<i>best_scheme</i>” só mostrará a melhor opção. Se seguirmos com estes resultados para o IQ-TREE ou MrBayes, veremos que a opção automática do PhyloSuite irá sugerir analisar os dois alinhamentos sob o mesmo modelo evolutivo. 
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_05/aula_05_10.png" alt="Resultado do teste de modelo evolutivo do alinhamento concatenado, visualizado no Notepad ++" align="center">
</center>
<br><br>
</div>

## Aula em vídeo

<br>
<div align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/YF2itEHw9YI" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe> 
<br><br>
Clique <a href="https://photos.app.goo.gl/r6CrAHnBY7D6d6yr6">aqui</a> para fazer o download do vídeo.
<br><br>
</div>