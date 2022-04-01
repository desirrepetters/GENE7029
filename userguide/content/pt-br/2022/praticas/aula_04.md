---
title: "Aula 04 - Análise Filogenética"
linkTitle: "Aula 04 - Análise Filogenética"
weight: 4
description: >
  Softwares utilizados: IQ-TREE e MrBayes no PhyloSuite e versões online do IQ-TREE e MrBayes.
---
<div align="justify">
Agora que temos um alinhamento corrigido e determinamos o modelo evolutivo mais adequado a ser implementado, finalmente chegou a hora de realizar a análise filogenética e obter as tão desejadas árvores.
<br><br>
Para este tutorial, utilizaremos os plugin do IQ-TREE e do MrBayes dentro do PhyloSuite. Se você ainda não tem o PhyloSuite instalado com estes plugins configurados, pode encontrar instruções <a href="https://cursodefilogeniaufpr.netlify.app/docs/download/phylosuite">aqui</a>. Para utilizar o IQ-TREE online, clique <a href="http://iqtree.cibiv.univie.ac.at/">aqui</a>. Já para utilizar o MrBayes online, as opções são o <a href="https://ngphylogeny.fr/">NGPhylogeny.fr</a> e o <a href="http://www.phylo.org/">CIPRES</a>.
<br><br>
Clique nos links abaixo para baixar os arquivos que serão utilizados nesta prática:
<br><br>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_04/aula_04.zip">Link para pasta com todos os arquivos (formato zip)</a></li>
<br>
Para baixar os arquivos individualmente:
<br><br>
<ul>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_04/Aula_03_Alinhamento_Corrigido.fasta">Alinhamento do MAFFT já editado (formato FASTA)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_04/Aula_03_Resultado_ModelFinder.iqtree">Arquivo de teste modelo evolutivo do ModelFinder para configurar a análise (formato IQ-TREE)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_04/Aula_04_Arvore_IQTREE_PhyloSuite.treefile">Arquivo de saída do IQ-Tree com a árvore (formato TREEFILE)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_04/Aula_04_Arvore_IQTREE_Online.treefile">Arquivo de saída do IQ-Tree online com a árvore (formato TREEFILE)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_04/Aula_04_Arvore_MrBayes_PhyloSuite.tre">Arquivo de saída do MrBayes com a árvore (formato TRE)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_04/Aula_04_Log_MrBayes_PhyloSuite.txt">Arquivo log de saída do MrBayes (formato TXT)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_04/Aula_04_Arvore_MrBayes_Online.nhx">Arquivo de saída do MrBayes online com a árvore (formato NHX)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_04/Aula_04_Log_MrBayes_Online.txt">Arquivo log de saída do MrBayes online (formato TXT)</a></li>
</ul>
</div>

## Análise Filogenética de Máxima Verossimilhança com o IQ-TREE usando o plugin do PhyloSuite

<div align="justify">
Após abrir o PhyloSuite e definir sua pasta de trabalho, podemos iniciar a configuração da análise de máxima verossimilhança clicando na opção “<i>IQ-TREE</i>” dentro do menu “<i>Phylogeny</i>":
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_04/aula_04_1.png" alt="Opção do IQ-TREE no menu Phylogeny dentro do PhyloSuite" align="center">
</center>
<br><br>
Nesse momento podemos perceber uma funcionalidade interessante do PhyloSuite relacionada à pasta de trabalho: ao utilizarmos a mesma pasta de trabalho para fazer todas as análises relacionadas a um mesmo alinhamento, o PhyloSuite é capaz de configurar automaticamente as opções das análises filogenéticas. Nesse caso, quando usamos o mesmo diretório de trabalho utilizado para realizar os testes de modelos evolutivos com o ModelFinder, a janela “<i>Choose inputs</i>” é aberta, mostrando que há arquivos prévios que podem ser aproveitados. Observe a lista para conferir os detalhes, principalmente em termos da data e hora, e se for a pasta correta, clique em OK:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_04/aula_04_2.png" alt="Janela Choose Inputs para escolha de resultados do ModelFinder dentro do PhyloSuite" align="center">
</center>
<br><br>
Na janela seguinte poderemos confirmar se os parâmetros foram configurados automaticamente de forma correta, e também fazer modificações que julgarmos necessárias. Os campos que merecem atenção são:
<br><br>
<ul>
<li><b>Alignment file:</b> aqui deve estar listado o nome do arquivo de alinhamento que será usado pela análise</li>
<li><b>Seq. Type:</b> podemos manter em “<i>Auto detect</i>”, ou especificar o tipo de sequência que estamos utilizando, que neste caso é DNA.</li>
<li><b>Outgroup:</b> aqui devemos selecionar o(s) outgroup(s) a ser utilizado, dentre os todos os indíviduos incluídos na análise. O IQ-TREE suporta a inclusão de mais de um indivíduo como outgroup. Entre parênteses, o IQ-TREE mostra quantos indivíduos foram selecionados (no exemplo, apenas um, <i>Fusarium oxysporum</i>).</li>
</ul>
<br><br>
Dentro da seção “<i>Substitution Model Options</i>” o software configurará automaticamente os parâmetros de acordo com os resultados do ModelFinder. Caso você esteja trabalhando em uma pasta diferente ou o PhyloSuite não tenha configurado automaticamente, os campos devem ser configurados como segue:
<br><br>
<ul>
<li><b>Models:</b> aqui, selecione o modelo evolutivo a ser utilizado (no exemplo, SYM).</li>
<li><b>Rate heterogeneity:</b> caso o modelo mais adequado inclua +G ou +I, marque as caixas de seleção correspondentes.</li>
</ul>
<br><br>
Já na seção “<i>Branch Support Analysis</i>”, configuraremos parâmetros relacionados ao método de bootstrap para cálculo do suporte dos ramos:
<br><br>
<ul>
<li><b>Bootstrap:</b> o IQ-TREE fornece uma “aproximação ultra-rápida de bootstrap” (<i>ultrafast bootstrap approximation, UFBoot</i>) para reduzir o tempo total de análise e as altas necessidades computacionais que existem no método tradicional de bootstrap não-paramétrico. É possível selecionar essa opção em “<i>Ultrafast</i>”. Caso deseje utilizar o bootstrap não-paramétrico, selecione “<i>Standard</i>”. Entretanto, optar por esta modalidade fará com que a análise seja extremamente mais demorada.</li>
<li><b>Num of bootstrap: </b> neste campo, informe quantas repetições de bootstrap devem ser realizadas. Sugere-se um mínimo de 1000, e neste exemplo usaremos 5000.</li>
<li><b>Max. iter: </b> Número máximo de iterações a serem realizadas no método de bootstrap ultra-rápido. O padrão é 1000.</li>
<li><b>Minimum cor. coefic.: </b> Valor mínimo para o coeficiente de correlação que indicará a convergência das análises de bootstrap ultrarápido. O padrão é 0.99.</li>
</ul>
<br><br>
Ao usar o bootstrap ultrarápido, também recomenda-se realizar o teste de SH-aLRT (<i>SH-like approximate likelihood ratio test</i>) e comparar os valores de suporte dos ramos obtidos no UFboot e no SH-aLRT. Para realizar esse teste, marque a caixa de seleção “<i>SH-aLRT branch test</i>”, e indique o número de repetições (1000 ou mais). Por fim, clique em “<i>Start</i>” para iniciar a análise e acompanhe o processo pela barra de progresso:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_04/aula_04_3.png" alt="Janela de Configurações do IQ-TREE no PhyloSuite" align="center">
</center>
<br><br>
Em alguns casos o programa pode retornar a mesma janela de erro que vimos ao produzir alinhamentos com o MAFFT e ao testar o modelo evolutivo com o ModelFinder, mas apesar disso, a análise filogenética de Máxima Verossimilhança foi concluída. Para encontrar o arquivo de saída, basta acessar a pasta “<i>GenBank file</i>”, em seguida “<i>files</i>”, “<i>IQTree_results</i>” e a pasta com a data e horário em você utilizou o software. Dentro desta pasta teremos diversos arquivos, e árvore final com valores de suporte do UFBoot e do SH-aLRT estão no arquivo com extensão “.treefile”. No nosso exemplo, será o arquivo “<b>Aula_03_Alinhamento_Corrigido.treefile</b>”. Iremos avaliar, interpretar e editar este arquivo da árvore em um tutorial futuro com o FigTree.
<br><br>
</div>

## Análise Filogenética de Máxima Verossimilhança no IQ-TREE com o servidor online

<div align="justify">
O <a href="http://iqtree.cibiv.univie.ac.at/">servidor online do IQ-TREE</a> apresenta funções similares ao plugin do IQ-TREE no PhyloSuite e pode ser configurado de forma bastante simples. A única desvantagem é que os campos de configuração não serão preenchidos de forma automática como no PhyloSuite. Nesse sentido, uma possibilidade é abrir o PhyloSuite como referência das opções enquanto realiza o preenchimento dos campos na página do servidor. 
<br><br>
No primeiro bloco intitulado “<i>Input Data</i>”, iremos fazer o upload do arquivo de alinhamento (nesse caso, o arquivo “<b>Aula_03_Alinhamento_Corrigido.fasta</b>” e informar ao IQ-TREE que se trata de uma sequência de DNA:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_04/aula_04_4.png" alt="Campo Input Data no servidor online do IQ-TREE" align="center">
</center>
<br><br>
Em seguida, no bloco intitulado “<i>Substitution Model Options</i>”, selecionamos o modelo evolutivo e as opções adicionais quando necessário. Nesse caso, configuraremos de forma similar à configuração apresenta no PhyloSuite:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_04/aula_04_5.png" alt="Campo Substituion Model Options no servidor online do IQ-TREE" align="center">
</center>
<br><br>
No bloco “<i>Branch Support Analysis</i>” também podemos escolher entre bootstrap ultra-rápido e bootstrap não-paramétrico. Configuraremos de forma similar à configuração do PhyloSuite, selecionando bootstrap ultra-rápido e realização do teste SH-aLRT:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_04/aula_04_6.png" alt="Campo Branch Support Analysis no servidor online do IQ-TREE" align="center">
</center>
<br><br>
O restante das opções pode ser mantido com as configurações padrão. Podemos adicionar nosso e-mail para recebermos uma notificação quando a análise for concluída e iniciar a análise em “<i>Submit Job</i>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_04/aula_04_7.png" alt="Inclusão de e-mail e opção Submit Job no servidor online do IQ-TREE" align="center">
</center>
<br><br>
Na página seguinte podemos observar em qual link os resultados poderão ser acessados após o término da análise. Após receber a notificação por e-mail ou após clicar neste link e o Status da análise for “<i>Success</i>”, podemos clicar em “<i>Download Selected Jobs</i>” e baixar os arquivos, que virão numa pasta compactada. 
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_04/aula_04_8.png" alt="Opção para download dos arquivos de saída no servidor online do IQ-TREE" align="center">
</center>
<br><br>
Assim como no plugin do IQ-TREE do PhyloSuite, o arquivo com a árvore será o “<b>Aula_03_Alinhamento_Corrigido.fasta.treefile</b>”, e poderá ser aberto e analisado futuramente no FigTree.
<br><br>
</div>

## Análise Filogenética de Inferência Bayesiana com o MrBayes com o plugin do PhyloSuite

<div align="justify">
Também podemos produzir árvores de inferência bayesiana no PhyloSuite seguindo configurações simples similares ao do IQ-Tree. Após abrir o PhyloSuite e definir a pasta de trabalho, podemos iniciar a configuração da análise de máxima verossimilhança clicando na opção “<i>MrBayes</i>” dentro do menu “<i>Phylogeny</i>":
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_04/aula_04_9.png" alt="Opção MrBayes dentro do menu Phylogeny no PhyloSuite" align="center">
</center>
<br><br>
O plugin do MrBayes também apresenta a funcionalidade de configuração automática à partir da pasta de trabalho. Nesse caso, quando usamos o mesmo diretório de trabalho utilizado para realizar os testes de modelos evolutivos com o ModelFinder, a janela “<i>Choose inputs</i>” também é aberta, mostrando que há arquivos prévios que podem ser aproveitados. 
<br><br>
Observe a lista para conferir os detalhes, principalmente em termos da data e hora, e se for a pasta correta, clique em OK:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_04/aula_04_10.png" alt="Janela Choose Inputs para escolha de resultados do ModelFinder dentro do PhyloSuite" align="center">
</center>
<br><br>
Na janela seguinte poderemos confirmar se os parâmetros foram configurados automaticamente de forma correta, e também fazer modificações que julgarmos necessárias. Os campos que merecem atenção são: 
<br><br>
<ul>
<li><b>Alignment file:</b> aqui deve estar listado o nome do arquivo de alinhamento que será usado pela análise</li>
<li><b>Outgroup: </b> aqui devemos selecionar o(s) outgroup(s) a ser utilizado, dentre os todos os indíviduos incluídos na análise. O MrBayes também suporta a inclusão de mais de um indivíduo como outgroup. Entre parênteses, o MrBayes mostra quantos indivíduos foram selecionados (no exemplo, apenas um, <i>Fusarium oxysporum</i>).</li>
</ul>
<br>
Dentro da seção “<i>Parameters</i>” o software configurará automaticamente os parâmetros de acordo com os resultados do ModelFinder. Caso você esteja trabalhando em uma pasta diferente ou o PhyloSuite não tenha configurado automaticamente, os campos devem ser configurados como segue:
<br><br>
<ul>
<li><b>Models:</b> aqui, selecione o modelo evolutivo a ser utilizado (no exemplo, SYM).</li>
<li><b>Rate Var.: </b> caso o modelo mais adequado inclua +G ou +I, escolha a opção correspondente.</li>
</ul>
<br>
Já na seção “<i>MCMC Settings</i>”, configuraremos parâmetros relacionados ao método de Markov-Chain Monte Carlo:
<br><br>
<ul>
<li><b>Generations:</b> número total de gerações da análise em que novos estados para as cadeias são propostos e aceitos/rejeitados.  O número necessário varia de acordo com o alinhamento analisado e muitas vezes necessitará otimização. Ao final da análise saberemos se utilizamos uma quantidade adequada se as cadeias atingirem a convergência. Neste exemplo, usaremos 10.000.000.</li>
<li><b>Sampling freq.: </b> neste campo, informe a cada quantas gerações uma árvore deve ser amostrada para a geração da árvore consenso final. Este valor deve levar em consideração a quantidade de total de gerações (para não amostrar poucas ou muitas árvores). No exemplo usaremos 10.000.</li>
<li><b>Number of runs:</b> Quantas análises serão realizadas simultaneamente e comparadas para definir se a convergência foi atingida. Aqui usaremos 2, mas pode ser utilizado um valor maior.</li>
<li><b>Number of chains:</b> quantidade de cadeias de Markov independentes que serão testadas ao longo das gerações. Se o valor for 1, não serão utilizadas cadeias aquecidas (análise MCMC). Se for utilizado um valor maior que 1, o método MCMCMC será implementado, com cadeias aquecidas. Dentre o número total de cadeias (n), “n-1” serão cadeias quentes e 1 será fria. A cadeia fria é a “prioritária”, mas ao longo das gerações há troca de informações entre as cadeias para que a análise não estacione em uma topologia ótima local que não seja a topologia ótima global. Em geral, alinhamentos com 50 sequências ou mais tendem a necessitar do uso de cadeias aquecidas para serem resolvidos. Aqui usaremos 4 cadeias (3 quentes e 1 fria), mas alinhamentos mais complexos podem se beneficiar do uso de mais cadeias (6 ou 8 cadeias por exemplo). Entretanto, quanto maior o número de cadeias, mais demorada a análise.</li>
<li><b>Contype:</b> este parâmetro especifica o tipo de árvore consenso que será produzida. contype especifica o tipo de árvore consenso. "<i>Halfcompat</i>" resulta numa árvore em que só serão mostrados grupos/clados que apresentem mais que 0.5 de suporte em probabilidade posterior. Quando o suporte é inferior, são mostradas politomias. "<i>Allcompat</i>" mostrará todos os grupos, independentemente do valor de probabilidade posterior, causando problemas de interpretação ao exibir grupos com valor de suporte muito baixo. Utilizaremos “<i>Halfcompat</i>”</li>
<li><b>Conformat:</b> especifica o formato do arquivo da árvore, que será lido por outros softwares como o FigTree. "<i>Simple</i>" resulta numa árvore que pode ser lida por diversos programas diferentes. "<i>FigTree</i>" resulta numa árvore formatada para o FigTree. Utilizaremos “<i>Simple</i>” para maximizar a compatibilidade entre diferentes programas.</li>
<li><b>Burnin Fraction ou Burnin:</b> especifica quantas árvores iniciais serao descartadas para gerar a arvore consenso. No início da análise as cadeias tendem a divergir rapidamente, de modo que as primeiras árvores amostradas tendem a ser de péssima qualidade e com topologias distintas em relação às topologias observadas na fase estacionária, gerando ruídos no resultado final. Em geral 25 por cento do total de árvores amostradas como Burnin é um valor adequado adequado (0.25, especificado como valor relativo para o “<i>Burnin Fraction</i>”, mas também pode ser especificado como valor absoluto no campo “<i>Burnin</i>”). Há softwares (como o Tracer) que podem estimar valores de burnin mais específicos, se necessário.</li>
</ul>
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_04/aula_04_11.png" alt="Janela de configuração das opções do MrBayes no PhyloSuite" align="center">
</center>
<br><br>
Por fim, clique em “<i>Start</i>” para iniciar a análise e acompanhe o processo pela barra de progresso. Diferentemente da análise de máxima verossimilhança, podemos verificar se as cadeias das duas análises (parâmetro “<i>Number of runs</i>”) atingiram convergência de acordo com o valor de “<i>Average standard deviation of split frequencies</i>”. Se o valor for igual ou inferior a 0.01, a convergência foi atingida e a análise não precisa ser continuada, mesmo que o número total de gerações ainda não tenha sido atingido: 
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_04/aula_04_12.png" alt="Valor de Average standard deviation of split frequencies inferior a 0.01" align="center">
</center>
<br><br>
Em alguns casos o programa pode retornar a mesma janela de erro que vimos ao produzir alinhamentos com o MAFFT e ao testar o modelo evolutivo com o ModelFinder, mas apesar disso, a análise filogenética de Inferência Bayesiana foi concluída. Para encontrar o arquivo de saída, basta acessar a pasta “<i>GenBank file</i>”, em seguida “<i>files</i>”, “<i>MrBayes_results</i>” e a pasta com a data e horário em você utilizou o software. Dentro desta pasta teremos diversos arquivos, e árvore consenso final estará no arquivo “<b>input.nex.con.tre</b>”, de extensão .TRE. O arquivo de registro da análise será o arquivo “<i>log</i>”. Iremos avaliar, interpretar e editar o arquivo da árvore no tutorial seguinte com o FigTree.
<br><br>
</div>

## Análise Filogenética de Inferência Bayesiana no MrBayes com o NGPhylogeny.fr

<div align="justify">
O servidor online do <a href="https://ngphylogeny.fr/tools/tool/281/form">MrBayes no NGPhylogeny.fr</a> apresenta funções similares ao plugin do MrBayes no PhyloSuite e pode ser configurado de forma bastante simples. A única desvantagem é que os campos de configuração não serão preenchidos de forma automática como no PhyloSuite. Nesse sentido, uma possibilidade é abrir o PhyloSuite como referência das opções enquanto realiza o preenchimento dos campos na página do servidor.
<br><br>
Inicialmente fazemos o upload do arquivo de alinhamento a ser utilizado (nesse caso, o arquivo “<b>Aula_03_Alinhamento_Corrigido.fasta</b>”) no campo “<i>Nexus/Fasta/Phylip input file</i>”. Os próximos campos precisam ser preenchidos como segue:
<br><br>
<ul>
<li><b>Number of generations:</b> número total de gerações (aqui usaremos 10.000.000)</li>
<li><b>Number of chains:</b> número de cadeias de Markov (aqui usaremos 4)</li>
<li><b>Number of runs:</b> número de análises simultâneas para o cálculo da convergência (aqui usaremos 2)</li>
<li><b>Outgroup:</b> posição do outgroup no arquivo de alinhamento (no nosso exemplo, o isolado de <i>Fusarium oxysporum</i> é o 40ª sequência da lista, então podemos preencher este campo com 40). Outra possibilidade é preencher este campo com o nome da sequência do outgroup, nesse caso “<b>Fusarium_oxysporum_NRRL_22902</b>”, sem o símbolo de “>” que está presente em todos os cabeçalhos de sequências FASTA.</li>
<li><b>Choose model:</b> modelo evolutivo a ser implementado (aqui usaremos SYM)</li>
<li><b>Sample frequency:</b> informar a cada quantas gerações uma árvore deve ser amostrada para a geração da árvore consenso final. Este valor deve levar em consideração a quantidade de total de gerações (para não amostrar poucas ou muitas árvores). No exemplo usaremos 10.000</li>
<li><b>Print frequency:</b> informar a cada quantas gerações o estado das cadeias será salvo no arquivo log para referência posterior. Também deve levar em consideração a quantidade total de gerações, mas como serve somente de referência, não precisa ser tão frequente quanto o “<i>Sample frequency</i>”. Aqui usaremos 100.000</li>
<li><b>Burn in fraction:</b> especifica quantas árvores iniciais serao descartadas para gerar a arvore consenso. Assim como no PhyloSuite, podemos estimar em 25%.</li>
<li><b>Checkpoint frequency:</b> informar a cada quantas gerações um arquivo “checkpoint” será criado, que permitirá a retomada da análise a partir deste ponto de parada em caso de problemas. Podemos utilizar também 100.000</li>
</ul>
O restante das opções pode ser mantido nas configurações padrão, e podemos iniciar a análise clicando em “<i>Submit</i>”. Ao clicar nessa opção, a análise será redirecionada para uma página que atualizará de tempos em tempos, informando o progresso das diferentes etapas. A análise estará concluída quando setas verdes surgirem na coluna de “<i>Status</i>”. O arquivo log da análise pode ser baixado no ícone da etapa 2 “<i>Mr Bayes on data 1</i>”, no formato TXT. A árvore final pode ser baixada no formato NHX clicando no ícone da etapa 8 “<i>Mr Bayes Consensus tree</i>”, ou aberta no iTol para ser customizada e pré-editada para o Inkscape (pulando a etapa do FigTree) clicando no ícone laranja. Esta customização será descrita em mais detalhes no tutorial da atividade seguinte.
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_04/aula_04_13.png" alt="Janela de resultados do MrBayes no NGPhylogeny.fr" align="center">
</center>
<br><br>
</div>


## Aula em vídeo

<br>
<div align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/FXLjccys9ow" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe> 
<br><br>
Clique <a href="https://photos.app.goo.gl/ucX8jaFma9uJvEJ19">aqui</a> para fazer o download do vídeo.
<br><br>
</div>