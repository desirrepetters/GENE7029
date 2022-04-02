---
title: "Aula 06 - Análise Filogenética com Alinhamento Concatenado"
linkTitle: "Aula 06 - Análise Filogenética com Alinhamento Concatenado"
weight: 6
description: >
  Softwares utilizados: IQ-TREE e MrBayes no PhyloSuite e versões online do IQ-TREE e MrBayes
---
<div align="justify">
Nesta atividade, incorporaremos mais uma região genômica à nossa análise filogenética inicial realizada na <a href="https://gene7029.netlify.app/2022/praticas/aula_04/">Aula 04</a>, e avaliaremos a diferença de resolução observada para alguns clados.
<br><br>
Para este tutorial, utilizaremos os plugins IQ-TREE e do MrBayes dentro do PhyloSuite. Se você ainda não tem o PhyloSuite instalado com estes plugins configurados, pode encontrar instruções <a href="https://gene7029.netlify.app/2022/download/phylosuite">aqui</a>. Para utilizar o IQ-TREE online, clique aqui. Já para utilizar o MrBayes online, a principal opção é o <a href="http://www.phylo.org/">CIPRES</a>, visto que no momento o NGPhylogeny.fr é limitado à análises com apenas um gene/alinhamento.
<br><br>
Clique nos links abaixo para baixar os arquivos que serão utilizados nesta prática:
<br><br>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_06/aula_06.zip">Link para pasta com todos os arquivos (formato zip)</a></li>
<br>
Para baixar os arquivos individualmente:
<br><br>
<ul>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_06/Aula_05_Alinhamento_Concatenado.fas">Alinhamento concatenado (formato FASTA)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_06/Aula_05_Alinhamento_Concatenado.phy">Alinhamento concatenado (formato PHYLIP)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_06/Aula_05_Resultado_ModelFinder.log">Arquivo de saída do ModelFinder com o melhor modelo evolutivo (formato LOG)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_06/Aula_05_ModelFinder_Para_Configurar.nex">Arquivo do ModelFinder com modelo evolutivo para configuração da análise filogenética</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_06/Aula_05_Resultado_PartitionFinder.txt">Arquivo de saída do PartitionFinder com o melhor modelo evolutivo (formato TXT)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_06/Aula_05_PartitionFinder_Para_Configurar.nex">Arquivo do PartitionFinder com modelo evolutivo para configuração da análise filogenética</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_06/Aula_06_Arvore_EFTUB_IQTREE_PhyloSuite.treefile">Arquivo de saída do IQ-Tree com a árvore (formato TREEFILE)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_06/Aula_06_Arvore_EFUTB_IQTREE_Online.treefile">Arquivo de saída do IQ-Tree online com a árvore (formato TREEFILE)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_06/Aula_06_Arvore_EFTUB_MrBayes_PhyloSuite.tre">Arquivo de saída do MrBayes com a árvore (formato TRE)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_06/Aula_06_Log_EFTUB_MrBayes_PhyloSuite.txt">Arquivo log de saída do MrBayes (formato TXT)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_06/Aula_06_Arquivo_MrBayes_para_CIPRES.nex">Arquivo do PhyloSuite para configurar o MrBayes no CIPRES (formato NEX)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_06/Aula_06_Arvore_EFTUB_MrBayes_Online.tre">Arquivo de saída do MrBayes online com a árvore (formato TRE)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_06/Aula_06_Log_EFTUB_MrBayes_Online.txt">Arquivo log de saída do MrBayes online (formato TXT)</a></li>
</ul>
</div>

## Análise Filogenética de Máxima Verossimilhança com o IQ-TREE usando o plugin do PhyloSuite

<div align="justify">
Após realizar o teste de modelo evolutivo tanto com o ModelFinder quanto com o PartitionFinder, podemos redirecionar os resultados para a análise de Máxima Verossimilhança no IQ-TREE com a opção “<i>Import the results to IQ-TREE</i>”. Ao selecionar essa opção, a janela de configuração do IQ-TREE é aberta, e podemos conferir se a configuração foi realizada correta, e alterar parâmetros que julgarmos necessários. Os campos que merecem atenção são:
<br><br>
<ul>
<li><b>Alignment file:</b> aqui deve estar listado o nome do arquivo de alinhamento concatenado que será usado pela análise, no formato FASTA. No exemplo, é o arquivo “<b>Aula_05_Alinhamento_Concatenado.fas</b>”</li>
<li><b>Seq. Type:</b> podemos manter em “<i>Auto detect</i>”, ou especificar o tipo de sequência que estamos utilizando, que neste caso é DNA.</li>
<li><b>Partition mode:</b> aqui devemos selecionar o arquivo produzido pelo ModelFinder ou pelo PartitionFinder que informa como o alinhamento concatenado deve ser ou não particionado. Caso você tenha optado pelos resultados do ModelFinder, o arquivo será “<b>Aula_05_Alinhamento_Concatenado_fas_mrbayes.best_scheme.nex</b>”. Já se você tiver optado pelo resultado do PartitionFinder, o arquivo será “<b>IQ_partition.nex</b>”.</li>
<li><b>Outgroup:</b> aqui devemos selecionar o(s) outgroup(s) a ser utilizado, dentre os todos os indíviduos incluídos na análise. O IQ-TREE suporta a inclusão de mais de um indivíduo como outgroup. Entre parênteses, o IQ-TREE mostra quantos indivíduos foram selecionados (no exemplo, apenas um, <i>Fusarium oxysporum</i>).</li>
</ul>
<br><br>
Já na seção “<i>Branch Support Analysis</i>”, configuraremos parâmetros relacionados ao método de bootstrap para cálculo do suporte dos ramos, de forma similar ao que fizemos na <a href="https://gene7029.netlify.app/2022/praticas/aula_04/#análise-filogenética-de-máxima-verossimilhança-com-o-iq-tree-usando-o-plugin-do-phylosuite">Aula 04</a>:
<br><br>
<ul>
<li><b>Bootstrap:</b> o IQ-TREE fornece uma “aproximação ultra-rápida de bootstrap” (<i>ultrafast bootstrap approximation, UFBoot</i>) para reduzir o tempo total de análise e as altas necessidades computacionais que existem no método tradicional de bootstrap não-paramétrico. É possível selecionar essa opção em “<i>Ultrafast</i>”. Caso deseje utilizar o bootstrap não-paramétrico, selecione “<i>Standard</i>”. Entretanto, optar por esta modalidade fará com que a análise seja extremamente mais demorada..</li>
<li><b>Num of bootstrap: </b> neste campo, informe quantas repetições de bootstrap devem ser realizadas. Sugere-se um mínimo de 1000, e neste exemplo usaremos 5000.</li>
<li><b>Max. iter: </b> Número máximo de iterações a serem realizadas no método de bootstrap ultra-rápido. O padrão é 1000.</li>
<li><b>Minimum cor. coefic.: </b> Valor mínimo para o coeficiente de correlação que indicará a convergência das análises de bootstrap ultrarápido. O padrão é 0.99.</li>
</ul>
<br><br>
Ao usar o bootstrap ultrarápido, também recomenda-se realizar o teste de SH-aLRT (<i>SH-like approximate likelihood ratio test</i>) e comparar os valores de suporte dos ramos obtidos no UFboot e no SH-aLRT. Para realizar esse teste, marque a caixa de seleção “<i>SH-aLRT branch test</i>”, e indique o número de repetições (1000 ou mais).
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_06/aula_06_1.png" alt="Janela de configuração do IQ-TREE dentro do PhyloSuite e configurações específicas para análise concatenada" align="center">
</center>
<br><br>
Por fim, clique em “<i>Start</i>” para iniciar a análise. Como temos um arquivo informando a forma de particionamento da análise, não foi necessário mexer nas opções do bloco “<i>Substitution Model Options</i>”, e antes de iniciar a análise o próprio PhyloSuite informa que qualquer configuração existente neste bloco será ignorada. Agora, basta acompanhar o processo pela barra de progresso e obter a árvore final.
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_06/aula_06_2.png" alt="Aviso informando que o bloco Substitution Model Options será ignorado em função da existência de um arquivo com partições" align="center">
</center>
<br><br>
Em alguns casos o programa pode retornar a mesma janela de erro que vimos em diversas análises, mas apesar disso, a análise filogenética de Máxima Verossimilhança foi concluída. Para encontrar o arquivo de saída, basta acessar a pasta “<i>GenBank file</i>”, em seguida “<i>files</i>”, “<i>IQTree_results</i>” e a pasta com a data e horário em você utilizou o software. Dentro desta pasta teremos diversos arquivos, e árvore final com valores de suporte do UFBoot e do SH-aLRT estão no arquivo com extensão “.treefile”. No nosso exemplo, será o arquivo “<b>Aula_05_Alinhamento_Concatenado_fas_mrbayes.best_scheme.nex.treefile</b>”. Iremos avaliar, interpretar e editar este arquivo da árvore no tutorial seguinte com o FigTree.
<br><br>
</div>

## Análise Filogenética de Máxima Verossimilhança no IQ-TREE com o servidor online

<div align="justify">
O <a href="http://iqtree.cibiv.univie.ac.at/">servidor online do IQ-TREE</a> apresenta funções similares ao plugin do IQ-TREE no PhyloSuite e pode ser configurado de forma bastante simples. A única desvantagem é que os campos de configuração não serão preenchidos de forma automática como no PhyloSuite. Nesse sentido, uma possibilidade é abrir o PhyloSuite como referência das opções enquanto realiza o preenchimento dos campos na página do servidor. 
<br><br>
No primeiro bloco intitulado “<i>Input Data</i>”, iremos fazer o upload do arquivo de alinhamento concatenado (nesse caso, o arquivo “<b>Aula_05_Alinhamento_Concatenado.fas</b>” e informar ao IQ-TREE que se trata de uma sequência de DNA. Além disso, diferentemente da configuração que fizemos na Aula 04, precisamos fornecer o arquivo com informações sobre o particionamento da análise. Caso você tenha optado pelo resultado do ModelFinder, utilize o arquivo “<b>Aula_05_Alinhamento_Concatenado_fas_mrbayes.best_scheme.nex</b>”. Caso sua opção seja pelo PartitionFinder, o arquivo a ser utilizado é o “<b>IQ_partition.nex</b>”. Como tanto o ModelFinder quanto o PartitionFinder sugeriram que o conjunto de alinhamentos fosse analisado sob apenas um modelo evolutivo, devemos selecionar “<i>Edge-linked</i>” na opção “<i>Partition type</i>”. Do contrário, caso os alinhamentos devessem ser analisados com modelos diferentes, selecionaríamos “<i>Edge-unliked</i>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_06/aula_06_3.png" alt="Configuração do bloco Input Data no servidor online do IQ-TREE" align="center">
</center>
<br><br>
Em seguida, no bloco intitulado “<i>Substitution Model Options</i>”, selecionamos o modelo evolutivo e as opções adicionais quando necessário. Nesse caso, configuraremos de acordo com o modelo proposto tanto pelo ModelFinder quanto pelo PartitionFinder:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_06/aula_06_4.png" alt="Configuração do bloco Substitution Model Options no servidor online do IQ-TREE" align="center">
</center>
<br><br>
No bloco “<i>Branch Support Analysis</i>” também podemos escolher entre bootstrap ultra-rápido e bootstrap não-paramétrico. Configuraremos de forma similar à configuração do PhyloSuite, selecionando bootstrap ultra-rápido e realização do teste SH-aLRT. O restante das opções pode ser mantido com as configurações padrão. Podemos adicionar nosso e-mail para recebermos uma notificação quando a análise for concluída e iniciar a análise em “<i>Submit Job</i>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_06/aula_06_5.png" alt="Configuração dos blocos Branch Support Analysis e e-mail no servidor online do IQ-TREE" align="center">
</center>
<br><br>
Na página seguinte podemos observar em qual link os resultados poderão ser acessados após o término da análise. Após receber a notificação por e-mail ou após clicar neste link e o Status da análise for “<i>Success</i>”, podemos clicar em “<i>Download Selected Jobs</i>” e baixar os arquivos, que virão numa pasta compactada, tal como fizemos na Aula 04. Assim como no plugin do IQ-TREE do PhyloSuite, o arquivo com a árvore será o “<b>Aula_05_Alinhamento_Concatenado_fas_mrbayes.best_scheme.nex.treefile</b>”, e poderá ser aberto e analisado futuramente no FigTree.
<br><br>
</div>

## Análise Filogenética de Inferência Bayesiana com o MrBayes usando o plugin do PhyloSuite

<div align="justify">
Após realizar o teste de modelo evolutivo tanto com o ModelFinder quanto com o PartitionFinder, podemos redirecionar os resultados para a análise de Inferência no MrBayes com a opção “<i>Import the results to MrBayes</i>”. Ao selecionar essa opção, a janela de configuração do MrBayes é aberta, e podemos conferir se a configuração foi realizada correta, e alterar parâmetros que julgarmos necessários. Os campos que merecem atenção são:
<br><br>
<ul>
<li><b>Alignment file:</b> aqui deve estar listado o nome do arquivo de alinhamento concatenado que será usado pela análise (nesse caso, será o arquivo “<b>Aula_05_Alinhamento_Concatenado_interleave.nex</b>”</li>
<li><b>Outgroup: </b> aqui devemos selecionar o(s) outgroup(s) a ser utilizado, dentre os todos os indíviduos incluídos na análise. O MrBayes também suporta a inclusão de mais de um indivíduo como outgroup. Entre parênteses, o MrBayes mostra quantos indivíduos foram selecionados (no exemplo, apenas um, <i>Fusarium oxysporum</i>).</li>
</ul>
<br>
Dentro da seção “<i>Parameters</i>” o software configurará automaticamente os parâmetros de acordo com os resultados do ModelFinder ou do PartitionFinder. O PhyloSuite terá feito a configuração automática corretamente caso todos os campos como “<i>Models</i>” ou “<i>Rate Var</i>” estejam acinzentados e sem possibilidade de modificação, e a opção “Partition Models” esteja colorida. Caso a opção “<i>Partition Models</i>” esteja acinzentada, clique sobre ela para ativar a configuração. 
<br><br>
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
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_06/aula_06_6.png" alt="Janela de configuração do MrBayes dentro do PhyloSuite" align="center">
</center>
<br><br>
Ao clicarmos na opção “<i>Show MrBayes Data Block</i>” podemos conferir se a configuração do particionamento foi realizada corretamente. Em “<i>charset</i>” podemos ver que os dois alinhamentos (posições 1-687 e 688-1240) foram reunidos em só um conjunto (“<i>subset1</i>”). E que a este conjunto foi atribuída uma partição (“<i>Names</i>”), e que à partição “<i>Names</i>” foi atribuído o modelo evolutivo GTR (“<i>nst=6</i>”) +I + G (“<i>rates=invgamma</i>”):
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_06/aula_06_7.png" alt="Bloco de configuração do modelo evolutivo dentro do script do MrBayes no PhyloSuite" align="center">
</center>
<br><br>
Por fim, clique em “<i>Start</i>” para iniciar a análise e acompanhe o processo pela barra de progresso. Diferentemente da análise de máxima verossimilhança, podemos verificar se as cadeias das duas análises (parâmetro “<i>Number of runs</i>”) atingiram convergência de acordo com o valor de “<i>Average standard deviation of split frequencies</i>”. Se o valor for igual ou inferior a 0.01, a convergência foi atingida e a análise não precisa ser continuada, mesmo que o número total de gerações ainda não tenha sido atingido: 
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_06/aula_06_8.png" alt="Valor de Average standard deviation of split frequencies inferior a 0.01" align="center">
</center>
<br><br>
Em alguns casos o programa pode retornar a mesma janela de erro que vimos nas análises anteriores, mas apesar disso, a análise filogenética de Inferência Bayesiana foi concluída. Para encontrar o arquivo de saída, basta acessar a pasta “<i>GenBank file</i>”, em seguida “<i>files</i>”, “<i>MrBayes_results</i>” e a pasta com a data e horário em você utilizou o software. Dentro desta pasta teremos diversos arquivos, e árvore consenso final estará no arquivo “<b>input.nex.con.tre</b>”, de extensão .TRE. O arquivo de registro da análise será o arquivo “log”. Iremos avaliar, interpretar e editar o arquivo da árvore em um tutorial futuro com o FigTree.
<br><br>
</div>

## Análise Filogenética de Inferência Bayesiana com o MrBayes com o CIPRES

<div align="justify">
Visto que o NGPhylogeny.fr é limitado às análises com apenas um gene, utilizaremos o <a href="http://www.phylo.org/">CIPRES</a> para realizar a análise filogenética de inferência bayesiana em alinhamentos concatenados. A configuração é bastante simples, e o PhyloSuite pode ajudar neste processo. A única desvantagem é a limitação de utilizar apenas um outgroup, ao invés de múltiplos outgroups conforme permitido pelo PhyloSuite.
<br><br>
Antes de realizar a configuração no <a href="http://www.phylo.org/">CIPRES</a>, iremos baixar o arquivo necessário para a análise na janela de configuração do MrBayes no PhyloSuite. Podemos seguir todas as etapas de concatenação do alinhamento, teste de modelo evolutivo e configuração da análise do MrBayes, lembrando de especificar somente um outgroup. Por fim, ao invés de clicar para iniciar a análise em start, clicaremos em “<i>Show MrBayes Data Block</i>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_06/aula_06_9.png" alt="Opção Show MrBayes Data Block na janela de configuração do MrBayes no PhyloSuite" align="center">
</center>
<br><br>
Ao clicar nesta opção uma nova janela será aberta, apresentando um arquivo NEXUS que contém tanto o alinhamento quanto os comandos utilizados pelo MrBayes. Clique na opção “<i>Save to File</i>” para salvar o arquivo, ou copie todo o conteúdo da janela e salve em um novo arquivo no Notepad++ com as extensões “.NEX” ou “.BAY”.
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_06/aula_06_10.png" alt="Opção Save to File na janela da opção Show MrBayes Data Block no PhyloSuite" align="center">
</center>
<br><br>
Em seguida, acesse o CIPRES e faça o upload deste arquivo na opção “<i>Data</i>” dentro da pasta de interesse (caso tenha dúvidas sobre este processo, confira instruções mais detalhadas <a href="https://gene7029.netlify.app/2022/cadastros/cipres">aqui</a>). Neste tutorial usaremos o arquivo “<b>Aula_06_Arquivo_MrBayes_para_CIPRES</b>.nex”. Após realizar o upload do arquivo, crie uma nova tarefa em “<i>Create New Task</i>”. Atribua um nome para a análise no campo “<i>Description</i>” e clique em “<i>Select Input Data</i>" para selecionar o arquivo de entrada:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_06/aula_06_11.png" alt="Página de configuração de nova tarefa no CIPRES" align="center">
</center>
<br><br>
Selecione o arquivo desejado (nesse caso, “<b>Aula_06_Arquivo_MrBayes_para_CIPRES.nex</b>”) e clique em “<i>Select Data</i>”):
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_06/aula_06_12.png" alt="Opção Select Data para selecionar o arquivo a ser utilizado na nova tarefa no CIPRES" align="center">
</center>
<br><br>
Em seguida, clique em “<i>Select Tool</i>” para selecionar o software a ser utilizado. Nesse exemplo, utilizaremos o MrBayes, então clique na opção “<i>MrBayes on XSEDE</i>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_06/aula_06_13.png" alt="Lista de softwares do CIPRES com destaque para o software MrBayes" align="center">
</center>
<br><br>
Após selecionar o software, clique em “<i>Set parameters</i>” para configurar os parâmetros da análise. Como o arquivo que foi obtido no PhyloSuite possuía o alinhamento e os comandos utilizados pelo MrBayes, marque a caixa de seleção “<i>My Data Contains a MrBayes Data Block (CHECK THIS OR MrBayes BLOCK ENTRIES WILL BE OVERWRITTEN!!!)</i>”, para que o CIPRES leve em conta os comandos presentes no arquivo e não seja necessário fazer todas as configurações manualmente na página do CIPRES. 
<br><br>
Em seguida, informe o número de sub-análises e número de cadeias de Markov de forma semelhante ao que foi configurado no PhyloSuite nas opções “<i>My MrBayes Block specifies nruns=</i>” e “<i>My MrBayes Block specifies nchains=</i>”, respectivamente. Em seguida, informe o número máximo de horas computacionais em que a análise deve ser mantida em execução. Como o limite do CIPRES é 168, sugerimos preencher com este valor para garantir que haja tempo suficiente para a conclusão da análise, ou ela será cancelada antes do final. Além disso, caso a análise dure menos de 168 horas computacionais, o valor correto será contabilizado na cota de utilização gratuita de 1000 horas, então não há problemas em estabelecer um valor maior neste momento.  
<br><br>
Por fim, é possível optar por utilizar ou não o BEAGLE. Utilizar o BEAGLE pode acelerar em até 20% a execução das análises. Entretanto, para alguns grupos de difícil resolução, utilizar o BEAGLE pode levar ao surgimento de topologias anômalas na árvore final. O recomendado é utilizá-lo, e desabilitar esta opção somente caso as árvores resultantes estejam muito estranhas, apresentando problemas sérios na topologia (por exemplo, desaparecimento de grupos bem suportados na análise de máxima verossimilhança, ou agrupamentos muito diferentes de filogenias previamente publicadas disponíveis na literatura). Após configurar todas as opções, clique em “<i>Save Parameters</i>” para confirmar. O CIPRES mostrará uma notificação sobre o tempo computacional e o uso do BEAGLE, e basta clicar em “<i>OK</i>” para ambas:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_06/aula_06_14.png" alt="Opções de configuração do MrBayes no CIPRES" align="center">
</center>
<br><br>
Por fim, clique em “<i>Save and Run Task</i>” para prosseguir. O CIPRES novamente apresentará uma notificação informando que as análises podem ser demoradas e que atualizar constantemente a página não irá acelerar o processo e pode até corromper os dados. Basta clicar em “<i>OK</i>” para iniciar a análise:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_06/aula_06_15.png" alt="Opções Save and Run Task para iniciar a análise no MrBayes no CIPRES" align="center">
</center>
<br><br>
Após confirmar, seremos redirecionados para a página da lista de tarefas dentro da pasta. Podemos atualizar a página clicando em “<i>Refresh Tasks</i>”. O campo “<i>Current CPU Hr Usage</i>” apresenta um cálculo provisório de horas computacionais que serão utilizadas caso a análise dure as 168 solicitadas nos vários processadores utilizados. Ao final da análise este valor será atualizado para o valor real (e provavelmente será bem inferior que 4032). 
<br><br>
Em “<i>Running Tasks</i>” podemos acompanhar quantas análises simultâneas estão em andamento (é possível rodar várias análises distintas ao mesmo tempo). Quando a caixa “<i>View Status</i>” mudar para “<i>View Output</i>”, a análise estará concluída. Além de acompanhar o progresso nessa página, o CIPRES enviará um aviso por e-mail quando a análise for terminada:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_06/aula_06_16.png" alt="Aba de Tarefas no CIPRES com informações sobre o progresso da análise do MrBayes" align="center">
</center>
<br><br>
Após terminar a análise, podemos clicar em “<i>View Output</i>” para baixar a árvore final e o arquivo LOG da análise. Independentemente da análise, o nome do arquivo da árvore será sempre “<b>input.nex.con.tre</b>”. Já o arquivo LOG será o “<b>log.txt</b>”. Clique em na opção “<i>Download</i>” para baixar ambos os arquivos para o computador.
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_06/aula_06_17.png" alt="Lista de arquivos de saída do MrBayes no CIPRES" align="center">
</center>
<br><br>
O arquivo da árvore será interpretado e editado em um tutorial futuro com o FigTree. Entretanto, é necessário avaliar se as análises atingiram convergência de acordo com informação de “<i>Average standard deviation of split frequencies</i>”, de forma semelhante ao que foi feito ao utilizar o MrBayes no PhyloSuite. Para isso, abra o arquivo no Notepad ++ e utilize a ferramenta “<i>Localizar</i>” (Ctrl + F) e procure pelo número total de gerações utilizadas (nesse caso, 10000000). Na linha logo abaixo da segunda ocorrência deste valor no documento será possível encontrar o valor final de “<i>Average standard deviation of split frequencies</i>” para a análise. Neste caso podemos observar que o valor final foi de 0.009188, que é inferior a 0.01 e permitindo que a árvore seja utilizada:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_06/aula_06_18.png" alt="Valor de Average standard deviation of split frequecies obtido na análise" align="center">
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