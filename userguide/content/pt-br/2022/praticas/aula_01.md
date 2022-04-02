---
title: "Aula 01 - Edição e Análise Inicial de Sequências de DNA"
linkTitle: "Aula 01 - Edição e Análise Inicial de Sequências de DNA"
weight: 1
description: >
  Software utilizado: MEGA7 ou MEGA X.
---
<div align="justify">
A primeira etapa para uma análise filogenética de qualidade e um procedimento de identificação de espécies bem-sucedido envolve um bom processamento de sequências de DNA. Se feito de forma correta, este processo irá garantir que estamos trabalhando com sequências confiáveis e sem informações espúrias.
<br><br>
Para este tutorial, iremos utilizar o software MEGA, seja na versão MEGA 7 ou MEGA X. Se você ainda não tem este software instalado, pode encontrar instruções <a href="https://gene7029.netlify.app/2022/download/mega/">aqui</a>.
<br><br>
Clique nos links abaixo para baixar os arquivos que serão utilizados nesta prática:
<br><br>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_01/aula_01.zip">Link para pasta com todos os arquivos (formato zip)</a></li>
<br>
Para baixar os arquivos individualmente:
<br><br>
<ul>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_01/Aula_01_Exemplo_01F.ab1">Aula_01_Exemplo_01F.abi</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_01/Aula_01_Exemplo_01R.ab1">Aula_01_Exemplo_01R.abi</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_01/Aula_01_Exemplo_02.ab1">Aula_01_Exemplo_02.abi</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_01/Aula_01_Exemplo_03.ab1">Aula_01_Exemplo_03.abi</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_01/Aula_01_Exemplo_04.ab1">Aula_01_Exemplo_04.abi</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_01/Aula_01_Exemplo_01.fasta">Aula_01_Exemplo_01.fasta</a></li>
</ul>
</div>

## Primeiros passos

<div align="justify">
Quando recebemos os resultados de um produto de reação de sequenciamento, em geral temos dois arquivos: um arquivo .FASTA e um arquivo de eletroferograma, em geral no formato .ABI, mas podendo variar dependendo do equipamento. O arquivo .FASTA contém a sequência do material enviado para sequenciamento, mas como é obtido de forma automatizada pelo equipamento, pode conter erros de leitura e não levar em consideração a baixa qualidade de algumas bases, de modo que não é recomendado trabalhar com este arquivo. Nesse sentido, a principal recomendação é analisar os eletroferogramas base à base, para garantir a confiabilidade da sequência.
</div>

## O que é e como analisar um eletroferograma?

<div align="justify">
Um eletroferograma é um gráfico representativo do material que foi sequenciado, contendo não apenas as bases de DNA que foram sequenciadas, mas também informações sobre a qualidade do sequenciamento e da amostra. Se bem interpretado, pode fornecer informações muito valiosas sobre seu material e facilitar a resolução de problemas, bem como garantir uma maior confiabilidade às suas futuras análises.
<br><br>
Neste guia, vamos avaliar alguns dos principais tipos eletroferogramas que podem ser encontrados, e quais atitudes tomar em relação à cada situação.
<br><br>
Para abrir um eletroferograma no MEGA, devemos utilizar a opção “<i>View/Edit Sequencer Files (Trace)</i>” dentro do menu “<i>Align</i>”. 
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_01/aula_01_1.png" alt="Janela da Opção Edit/View Sequencer Files (Trace)" align="center">
</center>
<br><br>
Procure em seu computador o Arquivo “<b>Aula_01_Exemplo_01F.abi</b>”, e clique em "<i>Abrir</i>". Este é um típico exemplo de um eletroferograma de boa qualidade, em que não ocorreram problemas durante o preparo da amostra, e nem durante o processo de sequenciamento. Vamos agora discutir alguns dos principais detalhes a serem levados em consideração.
<br><br>
Em geral, no início e no final do eletroferograma podemos ver bases mal resolvidas, com picos largos, de altura e espaçamento irregular, sobrepostos ou até mesmo duplos. Apesar de ser um evento frequente e normal, a informação destas bases deve ser desconsiderada, pois não há como garantir sua confiabilidade e falta precisão. Dessa forma, a primeira etapa do processamento de uma sequência deve ser cortar estas regiões mal resolvidas das pontas. Para isso, devemos clicar na última base da região a ser desconsiderada no início da sequência (que no exemplo é uma base C perto da posição 20) e em seguida na opção “<i>Mask upstream of the cursor</i>”. Isso fará com que esta região seja marcada para ser desconsiderada posteriormente. Se tudo der certo, ela ficará sombreada em cinza, diferente do restante da sequência. Neste exemplo não precisaremos cortar a sequência na região final, mas caso fosse necessário, bastaria selecionar a primeira base a ser desconsiderada no final da sequência, e usar a opção “<i>Mask downstream of the cursor</i>”.
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_01/aula_01_2.png" alt="Janela da Opção Mask upstream of the cursor" align="center">
</center>
<br><br>
Após marcar as regiões de corte, precisamos avaliar o restante da sequência. Um bom cromatograma como o do exemplo apresenta bases regularmente espaçadas, de picos únicos e de alturas (intensidades) semelhantes. Neste momento de avaliação, é importante observar se a sequência na parte superior da tela corresponde aos picos que estão na parte inferior, pois em alguns momentos o software pode adicionar ou remover bases por engano, principalmente em regiões em que há bases repetidas. Se for necessário adicionar bases que foram removidas, podemos clicar na sequência e digitar a letra correspondente à base inexistente. Se for necessário remover, basta clicar na letra correspondente à base extra e deletar. Para facilitar essa visualização, o software utiliza cores diferentes para os picos de cada base: vermelho para timinas, azul para citosinas, verde para adeninas e preto para guaninas.
<br><br>
Se tudo estiver de acordo com a sequência, podemos transferi-la para outra janela do MEGA clicando na opção “<i>Add unmasked sequence to Alignment Explorer</i>” ou utilizando o atalho “<i>Ctrl + A</i>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_01/aula_01_3.png" alt="Janela da Opção Add unmasked sequence to Alignment Explorer, apresentando eletroferograma de boa qualidade" align="center">
</center>
<br><br>
Ao utilizarmos esta opção, a sequência é adicionada à aba de Exploração de Alinhamentos. A partir desta aba, podemos renomear a sequência para outro nome de interesse (em geral, a sequência tem um nome relacionado ao equipamento, que não corresponde ao nome da amostra). Neste caso, iremos renomear esta sequência de “<b>46175</b>” para “<b>Exemplo_01F</b>”, dando dois cliques sobre o nome dela e digitando o novo nome:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_01/aula_01_4.png" alt="Instrução para Renomear as Sequências" align="center">
</center>
<br><br>
A partir deste ponto, podemos fazer diferentes análises com esta sequência, desde submetê-la ao BLAST no NCBI GenBank, quanto alinhá-las à outras sequências. Neste momento, entretanto, vamos analisar outro arquivo. Você deve ter notado que o nome do arquivo contém a letra F no final, e que há outro arquivo com a letra R. “F” e “R” são abreviações comumente utilizadas para “Forward” e “Reverse”, que se referem à orientação direta ou reversa de uma sequência de DNA. Ao sequenciar um fragmento, é muito comum fazê-lo em ambas as direções, tanto para obter um fragmento final maior, quanto para obter maior confiabilidade ao observar a sobreposição de ambas as sequências, combinando as duas numa sequência consenso. 
<br><br>
Vamos então produzir uma sequência consenso para o “<b>Exemplo_01</b>”. Por hora, deixaremos de lado a primeira sequência que analisamos. Minimize a aba de exploração de alinhamentos, e volte para a tela inicial do MEGA, e clique novamente na opção “<i>View/Edit Sequencer Files (Trace)</i>” dentro do menu “<i>Align</i>”. Agora, procure em seu computador o Arquivo “<b>Aula_01_Exemplo_01R.abi</b>”, e clique em Abrir. Faremos os mesmos procedimentos de corte que foram feitos na sequência anterior (desta vez, na base G da posição 20), exportaremos para a aba de exploração de alinhamentos, e a renomearemos como “<b>Exemplo_01R</b>”. 
<br><br>
Para criar a sequência consenso final, precisamos encontrar as regiões de sobreposição entre as duas sequências, e ver quais regiões foram sequenciadas em ambas as fitas. Para isso, vamos alinhar as duas sequências com o MUSCLE, que é um software de alinhamento incluído dentro do MEGA. Como não estamos trabalhando com sequências de DNA codificante, selecionaremos a opção “<i>Align DNA</i>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_01/aula_01_5.png" alt="Instruções para alinhamento das sequências com o MUSCLE" align="center">
</center>
<br><br>
Em seguida, clique em OK para que o MUSCLE selecione as duas sequências disponíveis, e peça aceite os parâmetros sugeridos por padrão, clicando em “<i>Compute</i>”. O MUSCLE iniciará o alinhamento, que tende a ser rápido por se tratarem de apenas duas sequências. 
<br><br>
Agora, vamos analisar o resultado. Observe que as sequências praticamente não estão alinhadas, com vários gaps (regiões presentes em apenas uma das sequências) e posições discordantes ao longo do alinhamento. As posições idênticas nas duas sequências são sinalizadas com asteriscos:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_01/aula_01_6.png" alt="Instruções para alinhamento das sequências com o MUSCLE" align="center">
</center>
<br><br>
Por que isto aconteceu, considerando que se tratam de duas sequências do mesmo organismo, e da mesma região genômica? A resposta está em um ponto já mencionado anteriormente: a orientação das fitas. Uma das sequências está na orientação direta, mas as outra está na orientação reversa, sendo reversamente complementar à fita direta. Para corrigir e produzir a sequência consenso, precisamos artificialmente inverter esta sequência, clicando sobre ela com o botão direito do mouse e em seguida em “<i>Reverse complement</i>”. Depois de inverter a sequência, repita o procedimento de alinhamento no MUSCLE e compare o resultado com o do alinhamento anterior. Desta vez, temos várias posições idênticas, e nas pontas temos regiões que estavam presentes em apenas uma das fitas. 
<br><br>
Para produzir a sequência consenso final, podemos adotar um critério mais conservador e utilizar apenas as regiões que apresentam sobreposição, deletando as pontas. Para excluir estas bases das pontas, basta selecioná-las e deletar. Entretanto, dependendo da qualidade do sequenciamento, podemos optar por não excluir estas bases e utilizá-las mesmo assim, quando o eletroferograma apresentava uma boa qualidade. 
<br><br>
Para isso, teremos que copiar a informação extra de uma das fitas para a outra. Sugerimos selecionar e copiar a sequência da fita direta para a fita reversa, selecionando a região que está presente apenas na fita direta, e colar na fita reversa. Em seguida, delete a sequência da fita direta, clicando sobre ela e selecionando “<i>Delete</i>”.
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_01/aula_01_7.png" alt="Instruções para deletar sequência extra durante a criação da consenso" align="center">
</center>
<br><br>
Agora é hora de exportar a sequência consenso final para um arquivo .FASTA que será utilizado em análises futuras. Para isso, renomeie a sequência para “<b>Exemplo_01</b>” e dentro do menu superior “<i>Data</i>”, selecione a opção “<i>FASTA format</i>” dentro de “<i>Export alignment</i>”. Escolha a pasta do computador e o nome de sua preferência para salvar o arquivo. 
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_01/aula_01_8.png" alt="Instruções para exportar a sequência no formato .FASTA" align="center">
</center>
<br><br>
</div>

## Que outros tipos de eletroferograma posso encontrar?

<div align="justify">
Procure em seu computador o Arquivo “<b>Aula_01_Exemplo_02.abi</b>”, e clique em "<i>Abrir</i>". Observe que neste caso, apesar de muitos dos picos estarem regularmente espaçados, há diversos picos duplos ao longo da sequência. 
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_01/aula_01_9.png" alt="Eletroferograma com Picos Duplos" align="center">
</center>
<br><br>
Este tipo de fenômeno pode ser oriundo de contaminação ao longo do processo, em diversas etapas, tais como:
<br><br>
<ul>
<li>Contaminação da amostra ou dos reagentes de extração de DNA</li>
<li>Contaminação do produto ou dos reagentes de PCR</li>
<li>Contaminação do produto ou dos materiais utilizados para a corrida de sequenciamento</li>
</ul>
<br>
Neste tipo de situação não é possível distinguir quais bases correspondem à sequência da sua amostra, e quais bases são oriundas de contaminação. Sendo assim, é necessário encontrar a fonte de contaminação, e realizar um novo sequenciamento.
<br><br>
Para o próximo exemplo, procure em seu computador o Arquivo “<b>Aula_01_Exemplo_03.abi</b>”, e clique em Abrir. Neste caso, ocorreu uma queda brusca e permanente no sinal do eletroferograma. Isso pode ocorrer tanto em fragmentos curtos, indicando que a reação atingiu o fragmento, ou em casos em que a quantidade de reagentes para a reação de sequenciamento foi insuficiente. Nesses casos, é importante avaliar se uma sequência mais longa seria ou não necessária, para determinar se será necessário repetir o sequenciamento. Na situação do exemplo, em que foram sequenciados 70 pares de base, seria necessário repetir o sequenciamento, principalmente considerando que o fragmento esperado tinha em torno de ~600 pares de bases.
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_01/aula_01_10.png" alt="Eletroferograma com Queda Repentina do Sinal" align="center">
</center>
<br><br>
Para o último exemplo, procure em seu computador o Arquivo “<b>Aula_01_Exemplo_04.abi</b>”, e clique em "<i>Abrir</i>". Este é um dos piores resultados que podem ser encontrados, e em que obrigatoriamente deve-se repetir a reação de sequenciamento. A ausência de sinal num eletroferograma pode ter diversos motivos, desde falhas no equipamento e na corrida, bem como perda da amostra durante os procedimentos de purificação. Nesses casos, costuma-se observar alguns poucos picos altos no início do eletroferograma, que correspondem aos dideoxinucleotídeos que não foram incorporados durante a reação.
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_01/aula_01_11.png" alt="Eletroferograma sem nenhum pico" align="center">
</center>
<br><br>

</div>

## Aula em vídeo

<br>
<div align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/DeN0ePRtjVc" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe> 
<br><br>
Clique <a href="https://photos.app.goo.gl/3LBgHgLsCDLef2TU8">aqui</a> para fazer o download do vídeo.
<br><br>
</div>

## Slides

<div align="center">
<br>
Clique <a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/slides/aula_01.pdf">aqui</a>!
</div>