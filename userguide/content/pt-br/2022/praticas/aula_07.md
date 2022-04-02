---
title: "Aula 07 - Visualização e pré-edição de árvores filogenéticas"
linkTitle: "Aula 07 - Visualização e pré-edição de árvores filogenéticas"
weight: 7
description: >
  Softwares utilizados: FigTree ou iTOL (online)
---
<div align="justify">
Uma vez que obtivemos nossas árvores filogenéticas, precisamos avaliá-las e interpretá-las para decidirmos se ainda há modificações necessárias ou se já estão adequadas aos nossos objetivos. Além disso, estando adequadas, precisamos prepará-las esteticamente para compor nossas apresentações e publicações. Nesta atividade, iremos utilizar softwares que nos permitem visualizar nossas árvores e fazer pequenas modificações estéticas que facilitarão a edição final para o padrão exigido em uma publicação ou apresentação.
<br><br>
Para este tutorial, utilizaremos o FigTree. Se você ainda não tem o FigTree instalado, pode encontrar instruções <a href="https://gene7029/2022/download/figtree">aqui</a>. Caso opte por utilizar o iTOL, pode acessá-lo <a href="https://itol.embl.de/">aqui</a>.
<br><br>
Clique nos links abaixo para baixar os arquivos que serão utilizados nesta prática:
<br><br>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_07/aula_07.zip">Link para pasta com todos os arquivos (formato zip)</a></li>
<br>
Para baixar os arquivos individualmente:
<br><br>
<ul>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_07/Aula_07_Arvore_EF_IQTREE.treefile">Arquivo de saída do IQ-Tree com a árvore da região de EF (formato TREEFILE)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_07/Aula_07_Arvore_EFTUB_IQTREE.treefile">Arquivo de saída do IQ-Tree com a árvore do alinhamento concatenado (formato TREEFILE)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_07/Aula_07_Arvore_EF_MrBayes.tre">Arquivo de saída do MrBayes com a árvore da região de EF (formato TRE)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_07/Aula_07_Arvore_EFTUB_MrBayes.tre">Arquivo de saída do MrBayes com a árvore do alinhamento concatenado (formato TRE)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_07/Aula_07_Arvore_EF_IQTREE.svg">Arquivo SVG da árvore da região de EF feita no IQ-TREE (formato SVG)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_07/Aula_07_Arvore_EF_IQTREE.pdf">Arquivo PDF da árvore da região de EF feita no IQ-TREE (formato PDF)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_07/Aula_07_Arvore_EF_MrBayes.svg">Arquivo SVG da árvore da região de EF feita no MrBayes (formato SVG)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_07/Aula_07_Arvore_EF_MrBayes.pdf">Arquivo PDF da árvore da região de EF feita no MrBayes (formato PDF)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_07/Aula_07_Arvore_EFTUB_IQTREE.svg">Arquivo SVG da árvore do alinhamento concatenado feita no IQ-TREE (formato SVG)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_07/Aula_07_Arvore_EFTUB_IQTREE.pdf">Arquivo PDF da árvore do alinhamento concatenado feita no IQ-TREE (formato PDF)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_07/Aula_07_Arvore_EFTUB_MrBayes.svg">Arquivo SVG da árvore do alinhamento concatenado feita no MrBayes (formato SVG)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_07/Aula_07_Arvore_EFTUB_MrBayes.pdf">Arquivo PDF da árvore do alinhamento concatenado feita no MrBayes (formato PDF)</a></li>
</ul>
</div>

## Edição de árvores no FigTree

<div align="justify">
Ao abrir o FigTree, podemos abrir a árvore para pré-edição com a opção “<i>Open</i>” dentro do menu “<i>File</i>". Escolha o arquivo da árvore de interesse em seu computador e clique para abrir:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_07/aula_07_1.png" alt="Opção Open dentro do menu File do FigTree" align="center">
</center>
<br><br>
Embora tenhamos incluído um outgroup na análise, precisaremos re-enraizar a árvore antes de fazer mais ajustes. Para isso, clique no ramo correspondente ao outgroup (nesse caso, “<b><i>Fusarium oxysporum</i> NRRL 22902</b>” e selecione a opção “<i>Reroot</i>” no menu superior:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_07/aula_07_2.png" alt="Seleção do Outgroup e opção Reroot para re-enraizar a árvore no FigTree" align="center">
</center>
<br><br>
Após re-enraizar a árvore, podemos fazer ajustes para melhorar o espaçamento entre os indivíduos da árvore, bem como diminuir o comprimento da árvore. Para realizar estes ajustes, as opções dentro da aba “<i>Layout</i>” são:
<br><br>
<ul>
<li><b>Expansion:</b> aumenta o espaçamento entre os indivíduos na direção vertical de acordo com a posição da barra lateral. Caso sua árvore contenha muitos indivíduos e apenas utilizar a opção “<i>Expansion</i>” não seja suficiente, você pode também utilizar a opção “<i>Zoom</i>”.</li>
<li><b>Root length:</b> diminui o comprimento da raiz da árvore, e consequentemente reduz o comprimento do restante da árvore.</li>
<li><b>Align Tip Labels:</b> alinha os nomes dos indivíduos no canto direito da imagem.</li>
</ul>
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_07/aula_07_3.png" alt="Opções da aba Layout do FigTree" align="center">
</center>
<br><br>
Na aba “<i>Tip Labels</i>” podemos alterar o tamanho com a opção “<i>Font Size</i>” e tipo de fonte utilizada para o nome dos indivíduos na caixa “<i>Font</i>” dentro da opção “<i>Setup</i>”.
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_07/aula_07_4.png" alt="Opções da aba Tip Label do FigTree" align="center">
</center>
<br><br>
Já na aba “<i>Node Labels</i>” podemos incluir na nossa árvore os valores de suporte para os ramos. Na opção Display selecione “<i>label</i>”, e ajuste o tamanho e tipo de fonte nas opções “<i>Font Size</i>” e “<i>Setup – Font</i>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_07/aula_07_5.png" alt="Opções da aba Node Labels do FigTree" align="center">
</center>
<br><br>
Ao realizar estes primeiros ajustes, veremos que o espaçamento entre os nomes dos indivíduos melhorou, bem como tamanho da fonte deixou as palavras mais legíveis. Por outro lado, veremos que os valores de suporte não estão bem posicionados à esquerda dos clados correspondentes, e em alguns casos acabam sobrepondo alguns nomes de indivíduos. Infelizmente esta é uma limitação do FigTree em termos de edição, mas iremos corrigi-la no momento da edição mais detalhada no Inkscape. 
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_07/aula_07_6.png" alt="Valores de suporte (bootstrap) sobrepondo o nome dos indivíduos na árvore plotada no FigTree" align="center">
</center>
<br><br>
Neste momento, o principal interesse da pré-edição é melhorar um pouco o aspecto visual das letras e números e corrigir possíveis problemas em relação ao tamanho da árvore, para ter uma base melhor para edição no Inkscape. Se estiver satisfeito com esta edição inicial, exporte a árvore para o formato SVG (para edição no Inkscape) ou PDF (para visualização e interpretação prévia) com as opções “<i>Export SVG</i>” e “<i>Export PDF</i>” no menu “<i>File</i>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_07/aula_07_7.png" alt="Opções EXport PDF e Export SVG para exportar imagens no FigTree" align="center">
</center>
<br><br>
</div>

## Edição de árvores no iTOL

<div align="justify">
Outra opção para edição de árvores (e que vai ser obrigatória no caso de edição das árvores geradas pelo MrBayes no NGPhylogeny.fr) consiste no <a href="https://itol.embl.de/">iTOL</a>, realizada no próprio navegador. Para iniciar a edição, basta acessar o iTOL e clicar na opção <a href="https://itol.embl.de/upload.cgi">“Upload”</a>:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_07/aula_07_8.png" alt="Opçoes para upload da árvore no iTOL" align="center">
</center>
<br><br>
Na página seguinte, forneça um nome para a árvore em “<i>Tree name</i>” e faça upload da árvore selecionando o arquivo adequado na opção “<i>Tree file</i>” e clicando em upload. Nesse exemplo, usaremos o arquivo “<b>Aula_07_Arvore_MrBayes_Online.nhx</b>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_07/aula_07_9.png" alt="Configuração do bloco Substitution Model Options no servidor online do IQ-TREE" align="center">
</center>
<br><br>
Após abrir a árvore, é possível re-enraizar ao clicar no indivíduo que representa o outgroup, e dentro da opção “<i>Tree structure</i>”, selecione “<i>Reroot the tree here</i>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_07/aula_07_10.png" alt="Re-enraizamento da árvore no iTOL" align="center">
</center>
<br><br>
Após re-enraizar a árvore, podemos fazer alguns ajustes na aparência do texto e na topologia, e incluir os valores de suporte. Na aba “<i>Controls</i>”, sub-aba “<i>Basic</i>”, podemos alterar:
<br><br>
<ul>
<li><b>Labels:</b> altera o posicionamento do nome dos indivíduos, que podem estar alinhados à direita (“<i>Aligned></i>”) ou próximos aos ramos (“<i>At tips</i>”).</li>
<li><b>Label font:</b> aqui, podemos alterar a fonte a ser utilizada no texto dos nomes dos indivíduos.</li>
<li><b>Font style:</b> nessa opção podemos alterar o tamanho da fonte, cor e o estilo (itálico e negrito, por exemplo).</li>
</ul>
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_07/aula_07_11.png" alt="Opções da sub-aba Basic na aba Controls dentro do iTOL" align="center">
</center>
<br><br>
Já na sub-aba “<i>Advanced</i>” da aba “<i>Controls</i>", podemos controlar aspectos relacionados aos valores de suporte dos clados. Para incluir os valores de suporte, clique em “<i>Display</i>” na opção “<i>Bootstraps / metadata</i>”. Em seguida, selecione o conjunto de dados adequados em “<i>Data source</i>”. No caso do exemplo, o conjunto de dados é “<i>prob</i>”. 
<br><br>
Em seguida, selecione “<i>Text</i>” para apresentar os valores de suporte em forma de texto (ao invés de apresentá-los utilizando um símbolo, ou codificando por cor/largura dos ramos). Por fim, ajuste os parâmetros do texto como tamanho e cor da fonte (na opção “<i>Font</i>”), posição dos valores de suporte nos em relação aos ramos (na popção “<i>Position on branch</i>”), e reduza o número de casas após a vírgula em “<i>Round to: n decimals</i>”. Nesse exemplo, os valores de suporte apresentarão apenas duas casas após a vírgula:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_07/aula_07_12.png" alt="Opções da sub-aba Advanced na aba Controls dentro do iTOL" align="center">
</center>
<br><br>
Por fim, para exportar a imagem para um arquivo SVG, ajuste o zoom para incluir toda a árvore na tela com os ícones de lupa na lateral esquerda: 
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_07/aula_07_13.png" alt="Opções de ajuste de zoom no iTOL" align="center">
</center>
<br><br>
Após realizar o ajuste, selecione “<i>SVG: Scalable Vector Graphics</i>” na opção “<i>Format</i>”, “<i>Export area</i>” como “<i>Screen</i>”, clique em “<i>Export</i>” e selecione a pasta de interesse para salvar o arquivo no computador:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_07/aula_07_14.png" alt="Opções de exportar imagem no formato SVG dentro do iTOL" align="center">
</center>
<br><br>
</div>



## Aula em vídeo

<br>
<div align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/vTXdtja4ojc" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe> 
<br><br>
Clique <a href="https://photos.app.goo.gl/PLPWLKSX9cM9MNKb7">aqui</a> para fazer o download do vídeo.
<br><br>
</div>

