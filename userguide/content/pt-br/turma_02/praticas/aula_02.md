---
title: "Aula 02 - Obtenção de Sequências no GenBank e Alinhamento Múltiplo"
linkTitle: "Aula 02 - Obtenção de Sequências no GenBank e Alinhamento Múltiplo"
weight: 2
description: >
  Softwares utilizados: MEGA7 ou MEGA X, Notepad ++ e PhyloSuite ou MAFFT online.
---
<div align="justify">
Após realizar a análise dos eletroferogramas da nossa sequência interesse e atestar sua qualidade e confiabilidade, podemos aprofundar nossas análises filogenéticas. Seja para identificar o indivíduo analisado ou entender como ele se relaciona à outras espécies próximas, precisamos de sequências de referência adicionais para comparação. Depois de definir o conjunto de sequências que serão utilizadas, é necessário construir o alinhamento que será submetido à análise filogenética.
<br><br>
Para este tutorial, acessaremos o <a href="https://www.ncbi.nlm.nih.gov/genbank/">NCBI GenBank</a> e utilizaremos os softwares Notepad ++, MEGA (na versão MEGA7 ou MEGA X) e MAFFT (na versão <a href="https://mafft.cbrc.jp/alignment/server/">online</a> ou como plugin do PhyloSuite). Se você ainda não tem estes softwares instalados, pode encontrar instruções <a href="https://cursodefilogeniaufpr.netlify.app/docs/download/">aqui</a>.
<br><br>
Clique nos links abaixo para baixar os arquivos que serão utilizados nesta prática:
<br><br>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_02/aula_02.zip">Link para pasta com todos os arquivos (formato zip)</a></li>
<br>
Para baixar os arquivos individualmente:
<br><br>
<ul>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_02/Aula_02_Consenso.fasta">Sequência Consenso (formato FASTA)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_02/Aula_02_Referencias.fasta">Sequências de referência (formato FASTA)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_02/Aula_02_Outgroup.fasta">Sequência do outgroup (formato FASTA)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_02/Aula_02_Todas.fasta">Arquivo FASTA com todas as sequências</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_02/Aula_02_Tabela.pdf">Tabela das sequências de referência</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_02/Aula_02_Alinhamento_MAFFT.fasta">Alinhamento bruto do MAFFT online (formato FASTA)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_02/Aula_02_Alinhamento_PhyloSuite_MAFFT.fasta">Alinhamento bruto do MAFFT no PhyloSuite (formato FASTA)</a></li>
</ul>
</div>

## Utilizando o BLASTn para definir quais sequências devem ser incluídas em um alinhamento

<div align="justify">
Para a nossa atividade prática, vamos utilizar a sequência consenso que produzimos na atividade passada como sequência candidata à identificação. Para identificar o indivíduo da sequência consenso, precisamos de sequências adequadas para comparação, de acordo com o nível taxonômico de interesse. 
<br><br>
Em geral, a decisão do nível taxonômico de interesse é realizada no momento de planejamento de um projeto, visto que diferentes genes são adequados para diferentes níveis de identificação. No caso do nosso exemplo, identificaremos a espécie do indivíduo, de modo que precisaremos de sequências de todas as espécies do gênero à que ele pertence.
<br><br>
Especialmente tratando de microrganismos, é muito comum que ao observar características morfológicas e fisiológicas não sejamos capazes nem ao menos de determinar a ordem ou família de um indivíduo, de modo que não teremos nem uma vaga ideia de qual o seu gênero. Em casos como esse, é possível chegar a uma “identificação preliminar” utilizando a ferramenta BLAST do NCBI.
<br><br>
O BLAST (<i>Basic Local Alignment Search Tool</i>) encontra regiões de similaridade entre sequências biológicas (como sequências de nucleotídeos ou proteínas). Ele pode ser utilizado de forma local e até para realizar alinhamentos entre um par de sequências, mas no nosso caso utilizaremos para buscar sequências semelhantes à nossa sequência consenso no banco de dados do NCBI (falaremos mais sobre ele depois) e tentar descobrir à que gênero o indivíduo da sequência consenso pertence, e assim, definir quais sequências de referência precisamos buscar nos bancos de dados. 
<br><br>
A primeira etapa é acessar diretamente a página do <a href="https://blast.ncbi.nlm.nih.gov/Blast.cgi">BLAST</a> e escolher a opção “<a href="https://blast.ncbi.nlm.nih.gov/Blast.cgi?PROGRAM=blastn&PAGE_TYPE=BlastSearch&LINK_LOC=blasthome"><i>Nucleotide BLAST</i></a>”, em que compararemos uma sequência de nucleotídeos contra um banco de dados de nucleotídeos:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_02/aula_02_1.png" alt="Página Inicial do BLAST apresentando as diferentes ferramentas: Nucleotide BLAST, tblastx, tblastn, Protein BLAST" align="center">
</center>
<br><br>
Na página do BLASTn serão fornecidas várias opções para análise da nossa sequência. Na primeira porção da página, devemos colar nossa sequência na primeira caixa (“<i>Enter accession number(s), gi(s), or FASTA sequence(s)”</i>). Não é obrigatório que a sequência esteja no formato FASTA contendo o cabeçalho – se inserirmos apenas a sequência em si, o BLASTn irá funcionar. Apenas devemos estar atentos para não inserir nenhuma informação extra ou caracteres especiais que não sejam reconhecidos. 
<br><br>
Também é possível analisar mais de uma sequência por vez: o BLASTn irá comparar as sequências individualmente e gerar uma aba de resultados que permite navegar entre as sequências. Além da possibilidade colar as sequências a serem analisadas diretamente na caixa em branco, é possível escolher um arquivo do computador em que as sequências estejam salvas, e fazer diretamente o upload deste arquivo:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_02/aula_02_2.png" alt="Campo para inserir a sequência ou arquivo a ser analisado pelo blastn" align="center">
</center>
<br><br>
No próximo campo, podemos escolher contra qual banco de dados ou organismos específicos a sequência consenso será comparada. É possível excluir organismos da comparação, escolher bancos de dados específicos (como por exemplo, apenas comparar com sequências de linhagens-tipo na opção “<i>Sequences from type material</i>”, e agora até mesmo realizar diretamente comparações com sequências de betacoronavírus!). Para nosso exemplo, iremos manter a opção padrão de comparação com a base de dados padrão, que é a coleção não redundante de nucleotídeos:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_02/aula_02_3.png" alt="Opções ~Standard databases (nr etc)~e ~Sequences from type material~ na configuração do blastn" align="center">
</center>
<br><br>
Na última seção, faremos uma escolha em relação ao algoritmo que será utilizado. Podemos restringir os resultados às sequências altamente similares (<i>“Highly similar sequences”</i>, usando o megablast), mais dissimilares (<i>“More dissimilar sequences”</i> usando o discontinguous megablast) ou moderamente similares (<i>“Somewhat similar sequences”</i> com o blastn padrão). Em geral, quando não temos muita ideia do agrupamento taxonômico do organismo de interesse, o ideal é utilizar o blastn padrão para não restringir as buscas excessivamente.
<br><br>
Por fim, conferimos se o tipo de busca que selecionamos está correto (no exemplo, “Search <b>database Nucleotide collection (nr/nt)</b> using <b>Blastn (Optimize for somewhat similar sequences)</b> e clicamos no botão BLAST. Nesse momento não iremos mexer em opções avançadas presentes na aba “<i>Algorithm parameters</i>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_02/aula_02_4.png" alt="Opções ~Somewhat similar sequences (blastn)~ e ~Search database Nucleotide collection (nt/nr) using Blastn (Optimize for somewhat similar sequences)" align="center">
</center>
<br><br>
Em seguida, aguardamos que o BLASTn realize a comparação da sequência consenso com as demais sequências do banco de dados. Na tela seguinte ele fornecerá algumas informações sobre o andamento da busca, como o tempo decorrido. Basta aguardar até que seja carregada a página de resultados.
<br><br>
Na parte superior esquerda, são sumarizadas algumas informações sobre a busca, como o tipo de programa usado (BLASTN), qual banco de dados (nt), qual o tipo de molécula (dna) e o tamanho da sequência:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_02/aula_02_5.png" alt="Campo superior esquerdo dos resultados de blastn" align="center">
</center>
<br><br>
Para nós, as informações mais relevantes estão presentes na seção seguinte: “<i>Sequences producing significant alignments</i>”, em que são listadas as sequências mais similares à sequência consenso que foram encontradas pelo BLASTn. Ao lado da lista de sequências, há algumas colunas com informações adicionais. Vamos discorrer brevemente sobre seu significado.
<br><br>
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_02/aula_02_6.png" alt="Campo ~Sequences producing significant alignments~ na página de resultados de blastn, com diversas sequências de Fusarium" align="center">
</center>
<br><br>
Dentre as colunas descritivas, podemos ver duas colunas que se referem ao “<i>score</i>”. Este score depende do tamanho do alinhamento, do número de matches, mismatches, gaps e da matriz de comparação de sequências utilizada e é normalizado através de variáveis estatísticas. 
<br><br>
Como vimos na aula teórica, ao alinhar duas sequências há vários alinhamentos possíveis, dependendo da combinação de gaps, matches e mismatches existentes. Além disso, diferentes matrizes de substituição ou penalidades de gaps podem gerar diferentes scores. Resumidamente, o score se refere à qualidade geral daquele alinhamento entre as duas sequências, mas não deve ser interpretado no sentido de que a sequência analisada é mais similar às sequências de maior score.
<br><br>
“<i>Query coverage</i>” se refere à porcentagem da sequência que foi utilizada na busca está presente em cada um dos alinhamentos. Em muitos casos, a sequência que estamos analisando pode ser mais longa ou mais curta que as sequências dos bancos de dados, de modo que parte dela pode ficar de fora do alinhamento e reduzir a porcentagem de cobertura. 
<br><br>
Já o E-value nos dá uma noção estatística sobre a qualidade do alinhamento entre as sequências: ele representa a quantidade de alinhamentos como scores iguais ou maiores ao score apresentado espera-se que ocorram ao acaso em uma base de dados de mesmo tamanho que a base de dados utilizada. Se o E-value é baixo, significa que é altamente improvável que um alinhamento de score igual aconteça ao acaso, sugerindo que de fato as sequências são similares. Já se o E-value é muito alto, significa que provavelmente as sequências não são similares, já que um alinhamento de mesmo score é altamente provável, e, portanto, pode ter acontecido por mera coincidência (e não tem real significado biológico). 
<br><br>
A coluna “<i>Percentage of identity (Per. Ident)</i>” se refere à porcentagem de similaridade entre as duas sequências alinhadas, exclusivamente para as regiões alinhadas (representadas na porcentagem de “<i>Query coverage</i>”. Isso significa que é possível que sequências diferentes apresentem a mesma porcentagem de cobertura, mas porcentagens de identidade diferente (uma é mais semelhante à sequência analisada do que a outra), ou uma sequência apresentam menor porcentagem de cobertura, mas porcentagem de identidade maior (provavelmente um pedaço da sequência ficou de fora do alinhamento pela diferença entre o comprimento da sequência analisada e a sequência no banco de dados, mas a porção que foi incluída no alinhamento tem maior similaridade do que a outra que apresenta maior porcentagem de cobertura).
<br><br>
E, por fim, a coluna Accession se refere ao código de acesso com que cada uma das sequências foi registrada ao ser depositada na base de dados, e que pode ser utilizado para buscar diretamente cada uma das sequências, bem como obter informações mais detalhadas sobre elas (tais como dados do indivíduo sequenciado, autores que realizaram o depósito da sequência, entre outras).
<br><br>
De forma geral, os valores das colunas descritivas não devem ser interpretados como valores que dão suporte ou não à identificação de um indivíduo num nível taxonômico tão preciso como espécie. O mais adequado é utilizá-los para avaliar a qualidade daqueles alinhamentos e avaliar se sequenciamos de fato o gene correto, e qual a identificação taxonômica de uma forma mais abrangente (por exemplo, em termos de família ou gênero).
<br><br>
No nosso exemplo, é possível ver que em todas as sequências aparece “<i>translation elongation fator 1-alpha (tef1) gene</i>” ao lado da espécie e do isolado, indicando que a região sequenciada na sequência consenso corresponde a um fragmento do fator de elongamento da tradução 1-alpha, bastante utilizado em alguns grupos taxonômicos. Como a intenção ao sequenciar este indivíduo era de fato sequenciar este fragmento, sabemos então que fomos bem sucedidos em termos de sequenciar a região correta.
<br><br>
Por outro lado, vemos diversas espécies listadas: “<i>Fusarium awaxy</i>”, “<i>Fusarium cf. fujikuroi</i>”, “<i>Fusarium</i> sp.”, “<i>Fusarium culmorum</i>”, “<i>Fusarium subglutinans</i>”, “<i>Fusarium guttiforme</i>”, “<i>Fusarium antophilum</i>”. Este tipo de ocorrência é bastante comum e não é um exemplo isolado: aqui demonstramos o quão problemático é realizar a identificação de espécies apenas via BLASTn, sem análises mais refinadas. Neste caso, a única informação relevante para nossa atividade é de que provavelmente o indivíduo da sequência consenso pertence ao gênero “<i>Fusarium</i>”, mas uma identificação definitiva só poderá ser realizada por meio de análise filogenética utilizando sequências de referência do gênero Fusarium. Não há informações que nos permitam escolher uma das espécies da lista e definir a identificação do indivíduo da sequência consenso. 
<br><br>
Agora que definimos que é necessário obter sequências das espécies descritas e aceitas de <i>Fusarium</i> para realizar a identificação do indivíduo da sequência consenso, seguiremos para a etapa de busca e obtenção de sequências no NCBI GenBank.
<br><br>
</div>

## Obtendo sequências no NCBI GenBank

<div align="justify">
O NCBI GenBank é a base de dados do National Center for Biotechnology Information, contendo dados genéticos disponíveis publicamente. Lá é possível encontrar diversos tipos de dados, desde sequências de DNA de diferentes regiões genômicas, montagens de genomas completos, transcriptomas, entre outros. A existência de bases de dados como o GenBank é extremamente importante, seja para lidar com o crescente volume de dados biológicos gerados, como para fornecer acesso e ferramentas de trabalho adequadas aos pesquisadores que trabalham com estes dados, e garantir que as informações estejam amplamente e permanentemente disponíveis.
<br><br>
Apesar da grande variedade de dados disponíveis no GenBank, no contexto do curso nosso foco será nas páginas e ferramentas destinadas à obtenção de sequências de DNA.
<br><br>
No topo página inicial do GenBank existe uma ferramenta de busca para encontrarmos os dados de interesse. Ao clicar na caixa de seleção suspensa, são listadas várias opções. Para sequências de DNA, escolheremos “<i>Nucleotide</i>”. Em seguida, digitamos os termos de interesse no campo em branco e clicamos em Search para pesquisar. Podemos procurar pelo nome dos organismos de interesse, por nomes de genes, ou também realizar combinações de palavras como nome do organismo e interesse e nomes de genes: 
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_02/aula_02_7.png" alt="Campo superior de buscas no NCBI GenBank com a opção ~Nucleotide~ selecionada e ~fusarium tef1~ como termo de busca" align="center">
</center>
<br><br>
Na próxima página podemos ver o número de resultados da nossa busca (neste caso, 7070), navegar por diferentes páginas de resultados (neste caso, 354 páginas) ou abrir resultados específicos. Vamos abrir o primeiro resultado para avaliar algumas das informações principais e descobrir como obter sua sequência FASTA:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_02/aula_02_8.png" alt="Resultado da busca pelo termo ~fusarium tef1~no NCBI GenBank, com 7070 resultados no total e 354 páginas de resultados." align="center">
</center>
<br><br>
Ao abrir o primeiro resultado, é possível descobrir qual é o código de acesso com o qual a sequência foi registrada (neste caso, <b>MG183712.1</b>), avaliar seu tamanho (714 bp), data em que foi depositada (15 de abril de 2018), qual a identificação segundo o depositante, quem são os autores e se a sequência faz parte de algum trabalho publicado ou não. Neste caso, a sequência consta como “Não publicada”.
<br><br>
Para baixar a sequência há duas possibilidades. A primeira consiste em clicar em “<i>Send to</i>” na parte superior direita, selecionar “<i>Complete record</i>”, “<i>File</i>”, formato “<i>FASTA</i>” e “<i>Create file</i>” para fazer download da sequência no formato FASTA. 
<br><br>
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_02/aula_02_9.png" alt="Página da sequência de código MG183712.1 de Fusarium solani" align="center">
</center>
<br><br>
A segunda possibilidade é clicar em FASTA logo abaixo do código GenBank da sequência e abrir uma nova janela em que a sequência no formato FASTA poderá ser copiada:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_02/aula_02_10.png" alt="Página da sequência de código MG183712.1 de Fusarium solani, em formato FASTA" align="center">
</center>
<br><br>
Para organizar as sequências, seja baixando os arquivos ou copiando cada uma, nossa sugestão é criar um documento no Notepad ++, e editar os cabeçalhos para remover informações extras, caracteres especiais e espaços. Uma boa abordagem é manter os cabeçalhos das sequências sempre como “>[Gênero]_[epíteto específico]_[código do isolado]”, para facilitar a compatibilidade entre diferentes softwares. No caso do exemplo, editaríamos a sequência de <b>“>MG183712.1 Fusarium solani strain FJAT-31354 TEF1 (TEF1) gene, partial cds”</b> para <b>“>Fusarium_solani_FJAT_31354”</b>. É importante sempre usar underlines ao invés de espaços. 
<br><br>
Como você já deve ter percebido pela quantidade de resultados que aparecem na busca, pelo status de “<i>Unpublished</i>” de muitas sequências, e pelo fato da identificação da sequência ser dependente do depositante (e sem curadoria posterior), muitas vezes buscar diretamente pelos genes ou nome dos organismos não é a estratégia mais fácil para filtrar e selecionar as sequências adequadas a serem incluídas na análise filogenética. 
<br><br>
Em geral, uma abordagem mais acertada é buscar por artigos ou outros bancos de dados que informem quais são as espécies aceitas, quais são as linhagens-tipo e os respectivos códigos GenBank para suas sequências, e aí utilizando estes códigos, fazer a busca e baixar as sequências conforme demonstramos anteriormente. 
<br><br>
No caso da sequência consenso, pertencente ao gênero <i>Fusarium</i>, a informação está dispersa em diversos materiais na literatura, e no contexto do curso não seria produtivo que todos gastássemos tempo reunindo essas informações. Além disso, como o gênero <i>Fusarium</i> apresenta muitas espécies descritas, muitas vezes se torna mais fácil realizar análises separando o gênero em diversos complexos de espécies. Como as espécies listadas nos primeiros alinhamentos no nosso resultado de BLASTn pertencem ao mesmo complexo, focaremos a análise no complexo “<i>Fusarium fujikuroi</i>”. Vamos trabalhar com um conjunto de sequências de referência do complexo <i>Fusarium fujikuroi</i> que já foi reunido e curado manualmente, cujos códigos e informações sobre os isolados (origem geográfica, substrato de isolamento, coleção em que foram depositados e referências dos estudos que descreveram cada espécie) estão <a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_02/Aula_02_Tabela.pdf">nesta tabela</a>. 
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_02/aula_02_11.png" alt="Cabeçalho da Tabela das Sequências de Referência" align="center">
</center>
<br><br>
Este tipo de tabela é extremamente útil não só para a nossa própria organização em relação ao nosso material de estudo, mas também para auxiliar outros pesquisadores a terem um acesso mais fácil a estas informações. Nesse sentido, aconselhamos que no momento de pesquisa na literatura, procurem por este tipo de tabela (que facilitará imensamente seu trabalho futuro). Caso este tipo de tabela não exista e as informações estejam muito dispersas em vários bancos de dados e artigos, talvez você inicialmente passe por um processo trabalhoso de reunião e curadoria de informação. Nesse caso, que tal contribuir com outros pesquisadores e facilitar o acesso deles à esta informação ao incluir a tabela em seu trabalho? Com certeza você auxiliará diversas pessoas e esse esforço será reconhecido com diversas citações à sua tabela!
<br><br>
</div>

## Escolhendo o outgroup e organizando o arquivo de entrada

<div align="justify">
Vamos então produzir o alinhamento múltiplo unindo a sequência consenso ainda não identificada, as sequências de referência, e um outgroup adequado. Como já discutimos durante a aula teórica, o outgroup adequado consiste em um indivíduo externo ao grupo que está sendo analisado, mas que compartilhe um ancestral comum. Neste caso, há algumas possibilidades:
<br><br>
<ul>
<li>Algum representante de um gênero que pertença à família Nectriaceae (mesma família do gênero <i>Fusarium</i>);</li>
<li>Algum indivíduo do gênero <i>Fusarium</i>, mas que pertença a um complexo de espécies distinto do complexo <i>Fusarium fujikuroi</i></li>
</ul>
<br><br>
Na nossa atividade prática seguiremos a segunda opção, utilizando um indivíduo da espécie <i>Fusarium oxysporum</i>, que pertence ao complexo de espécies <i>Fusarium oxysporum</i>.
<br><br>
Para produzir o alinhamento múltiplo, utilizaremos o software MAFFT. Podemos utilizar tanto a <a href="https://mafft.cbrc.jp/alignment/server/">versão online</a> quanto o plugin do PhyloSuite, e demonstraremos como realizar o alinhamento das duas formas. Primeiro, devemos criar um único arquivo FASTA contendo todas as sequências que queremos alinhar. Podemos fazer isso abrindo todos os arquivos no Notepad ++, copiar e colar todas as sequências num novo documento e salvar com a extensão FASTA.
<br><br>
</div>

## Alinhamento múltiplo com o MAFFT online

<div align="justify">
Usando o <a href="https://mafft.cbrc.jp/alignment/server/">MAFFT online</a>, no primeiro campo podemos colar diretamente as sequências de DNA a serem alinhadas ou selecionar o arquivo FASTA que acabamos de criar:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_02/aula_02_12.png" alt="Campo para inserir ou escolher o arquivo de sequências no MAFFT online" align="center">
</center>
<br><br>
Em seguida, podemos configurar algumas opções referente ao arquivo de saída. Para evitar problemas de sequências em orientações opostas no meio do alinhamento, podemos selecionar a opção “<i>Adjust direction according to the first sequence</i>”, em que a orientação das sequências será ajustada para seguir a mesma orientação da primeira sequência do alinhamento. Também é possível pedir que o MAFFT ordene as sequências no arquivo de saída de acordo com a sua similaridade com a opção “<i>Aligned</i>” dentro de “<i>Output order</i>”. Ao selecionar essa opção, as sequências mais similares estarão mais próximas no arquivo final, o que é bastante conveniente para a inspeção visual do alinhamento.
<br><br>
Também é possível dar um nome à tarefa em “<i>Job name</i>” e inserir seu e-mail para ser notificado quando o alinhamento ficar pronto, visto que o procedimento pode ser demorado para arquivos muito grandes com muitas sequências longas.
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_02/aula_02_13.png" alt="Opções para o alinhamento com o MAFFT online" align="center">
</center>
<br><br>
O MAFFT também fornece algumas opções avançadas para otimização dos alinhamentos em caso de muitas sequências ou regiões problemáticas, e também a possibilidade de utilizar diferentes matrizes de substituição e alterar a penalidade de gaps. Para este exemplo, utilizaremos as opções já definidas por padrão e clicaremos em “<i>Submit</i>”.
<br><br>
Ao finalizar o alinhamento, o MAFFT redireciona para uma página de resultados. É possível avaliar se havia sequências em orientação reversa no arquivo original na opção “<i>Open all plots</i>”. Se houverem somente linhas vermelhas nos gráficos, todas as sequências estavam em orientação direta (quando comparadas à primeira sequência do alinhamento). Se houver alguma linha azul, esta sequência estava em orientação reversa quando comparada à primeira sequência do alinhamento. Para baixar o alinhamento em formato FASTA, basta clicar em “<i>Fasta format</i>” no menu superior. Neste caso, salvaremos o alinhamento como “<b>Aula_02_Alinhamento_MAFFT.fasta</b>”.
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_02/aula_02_14.png" alt="Instruções para download do alinhamento produzido pelo MAFFT online" align="center">
</center>
<br><br>
</div>

## Alinhamento múltiplo com o plugin do MAFFT no PhyloSuite

<div align="justify">
Também é possível produzir o alinhamento pelo plugin do MAFFT no PhyloSuite. Caso ainda não tenha o PhyloSuite instalado e o plugin do MAFFT configurado, siga estas instruções <a href="https://cursodefilogeniaufpr.netlify.app/docs/phylosuite">aqui</a>. Após a instalação e configuração, para fazer os alinhamentos primeiramente iremos definir uma pasta de trabalho ao abrir o programa. Clicando no ícone amarelo, escolha a pasta que contiver o arquivo com as sequências. Lembre-se de <b>NÃO</b> selecionar a opção “<i>Use this as the default and do not ask again</i>” para que você sempre seja capaz de escolher qualquer pasta de seu interesse e não ficar restrito à uma única pasta:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_02/aula_02_15.png" alt="Janela de seleção do workplace no PhyloSuite" align="center">
</center>
<br><br>
Em seguida, clique na opção “<i>MAFFT</i>” dentro do menu “<i>Alignment</i>":
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_02/aula_02_16.png" alt="Opção MAFFT dentro do menu Alignment do PhyloSuite" align="center">
</center>
<br><br>
Na janela de opções, escolha o arquivo com todas as sequências, modo de alinhamento “<i>Normal</i>”, estratégia “<i>1. –auto</i>” e Export Format “<i>3. FASTA Format / Sorted</i>” para exportar o arquivo final para o formato FASTA com as sequências ordenadas por similaridade. Em “<i>Additional parameters</i>” geralmente a opção “--adjustdirection” para ajustar a orientação das sequências para a mesma da primeira sequência já está selecionada, mas se não estiver, deve ser selecionada. As outras opções não precisam ser selecionadas. Em seguida, aperte em “<i>Start</i>” e acompanhe o processo por meio da barra de progresso:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_02/aula_02_17.png" alt="Janela de configurações do MAFFT dentro do PhyloSuite" align="center">
</center>
<br><br>
Em alguns casos o programa pode retornar uma janela de erro, mas apesar disso, o alinhamento foi concluído. Para encontrar o arquivo de saída, basta acessar a pasta “<i>GenBank file</i>”, em seguida “<i>files</i>”, “<i>mafft_results</i>” e a pasta com a data e horário em você utilizou o software. Dentro desta pasta estará o arquivo FASTA alinhado pelo MAFFT e um arquivo log da tarefa.
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_02/aula_02_18.png" alt="Possível bug inofensivo ao utilizar o MAFFT no PhyloSuite" align="center">
</center>
<br><br>
</div>

## Inspeção visual e edição do alinhamento no MEGA

<div align="justify">
Para inspeção visual e edição, abriremos o alinhamento no software MEGA 7 ou MEGA X. Para abrir o alinhamento seleciona a opção “<i>Edit/Build Aligment</i>” dentro do menu “<i>Align</i>”. Escolha a opção “<i>Retrieve sequences from a file</i>", clique em OK e escolha o arquivo do alinhamento no seu computador (seja o produzido pelo MAFFT online ou pelo plugin do MAFFT no PhyloSuite) para abrir:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_02/aula_02_19.png" alt="Instruções para abrir um arquivo de alinhamento no MEGA" align="center">
</center>
<br><br>
Ao abrir o alinhamento na aba do Explorador de Alinhamentos, vemos que nem todas as sequências tem o mesmo comprimento: algumas são mais longas que outras, de modo que as mais curtas acabam possuindo vários “gaps” no começo e no final. Nesse sentido, é importante cortar um pouco do início e do final do alinhamento para que o alinhamento consista de regiões representadas pela maioria das sequências. Podemos selecionar e deletar estas bases do começo e do final da mesma forma que fizemos ao produzir a sequência consenso na <a href="https://cursodefilogeniaufpr.netlify.app/docs/praticas/aula_02/#o-que-%C3%A9-e-como-analisar-um-eletroferograma">Aula 01</a>.
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_02/aula_02_20.png" alt="Corte nas porções inicial e final do alinhamento" align="center">
</center>
<br><br>
Para a inspeção visual e edição ao longo de um alinhamento, observe principalmente se:
<br><br>
<b>Há um excesso de transversões?</b> Em geral, transições são mais prováveis e frequentes, de modo que isso deve se refletir no alinhamento. Se ao longo de um alinhamento você encontrar um excesso de transversões, avalie estas regiões com mais cuidado para ver se não seria possível incluir alguns gaps ou deslocar algumas bases para que se alinhem à outras.
<br><br>
<b>Há bases que estão deslocadas, e uma região próxima à qual claramente elas deveriam estar alinhadas?</b> Nesse caso, desloque as bases e corrija o alinhamento. No exemplo a seguir, o gap existente nas sequências 15 a 20 provavelmente não existe, visto que nas sequências logo abaixo ou logo acima a região deslocada existe. Nesse caso, selecione as bases deslocadas e mova para a posição correta com a opção “<i>Move selected block left</i>” do menu superior:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_02/aula_02_21.png" alt="Opção ~Move selected block left~ no MEGA 7" align="center">
</center>
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_02/aula_02_22.png" alt="Exemplo de bases deslocadas em um alinhamento" align="center">
</center>
<br><br>
No contexto deste tutorial não iremos discutir exaustivamente todos os pontos do alinhamento que poderiam ou não ser editados. A edição dos alinhamentos exigirá um pouco de prática e tempo, e à medida que você trabalhar com frequência com as mesmas sequências, e olhar com atenção o alinhamento, este processo se tornará cada vez mais fácil e você terá mais confiança nas edições. Lembre-se: sempre é possível desfazer as mudanças (Ctrl + Z), ou exportar várias opções de edição, testá-las em sua análise filogenética e perceber as mudanças, ou mesmo não fazer nenhuma edição enquanto não sentir confiança o suficiente para isso.
<br><br>
Após inspecionar e estar satisfeito com sua edição, exporte o alinhamento no formato FASTA. Dentro do menu superior “<i>Data</i>”, selecione a opção “<i>FASTA format</i>” dentro de “<i>Export alignment</i>”. Escolha a pasta do computador e o nome de sua preferência para salvar o arquivo. Na próxima atividade, faremos o teste de modelo evolutivo e produziremos nossas primeiras árvores filogenéticas.
<br><br>
</div>

## Aula em vídeo

<br>
<div align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/yz0njYN0oIw" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe> 
<br><br>
Clique <a href="https://photos.app.goo.gl/pukRgyGobNrkH3Un7">aqui</a> para fazer o download do vídeo.
<br><br>
</div>