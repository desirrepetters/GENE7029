---
title: "Aula 08 - Edição de Árvores para Publicações Científicas"
linkTitle: "Aula 08 - Edição de Árvores para Publicações Científicas"
weight: 8
description: >
  Softwares utilizados: Inkscape
---
<div align="justify">
Na atividade anterior pudemos perceber que o uso do FigTree é importante e necessário para incluir os valores de suporte na árvore e também pode auxiliar a realizar uma pré-edição e customização simples da imagem. Essa customização nos permite produzir imagens simples e razoáveis para interpretação e discussão de uma árvore, e podem atender bem às necessidades durante o período em que uma análise está sendo refinada e diversas árvores parciais são construídas. Entretanto, as limitações do FigTree não nos permitem produzir uma imagem final que atenda às exigências das publicações e apresentações científicas. Nessa atividade, vamos terminar a edição das árvores filogenéticas e preparar imagens com qualidade suficiente para compor uma publicação. 
<br><br>
Para este tutorial, utilizaremos o Inkscape. Se você ainda não tem o Inkscape instalado, pode encontrar instruções <a href="https://gene7029.netlify.app/2022/download/inkscape">aqui</a>.
<br><br>
Clique nos links abaixo para baixar os arquivos que serão utilizados nesta prática:
<br><br>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_08/aula_08.zip">Link para pasta com todos os arquivos (formato zip)</a></li>
<br>
Para baixar os arquivos individualmente:
<br><br>
<ul>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_08/Aula_08_Arvore_EF_IQTREE.svg">Arquivo SVG da árvore da região de EF feita no IQ-TREE (formato SVG)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_08/Aula_08_Arvore_EF_MrBayes.svg">Arquivo SVG da árvore da região de EF feita no MrBayes (formato SVG)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_08/Aula_08_Arvore_EFTUB_IQTREE.svg">Arquivo SVG da árvore do alinhamento concatenado feita no IQ-TREE (formato SVG)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_08/Aula_08_Arvore_EFTUB_MrBayes.svg">Arquivo SVG da árvore do alinhamento concatenado feita no MrBayes (formato SVG)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_08/Aula_08_Arvore_EF_Inkscape.png">Arquivo final da árvore da região EF editada no Inkscape, unindo as árvores de Máxima Verossimilhança e Inferência Bayesiana (formato PNG)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_08/Aula_08_Arvore_EF_Inkscape.svg">Arquivo final da árvore da região EF editada no Inkscape, unindo as árvores de Máxima Verossimilhança e Inferência Bayesiana (formato SVG)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_08/Aula_08_Arvore_EFTUB_Inkscape.png">Arquivo final da árvore do alinhamento concatenado editada no Inkscape, unindo as árvores de Máxima Verossimilhança e Inferência Bayesiana (formato PNG)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_08/Aula_08_Arvore_EFTUB_Inkscape.svg">Arquivo final da árvore do alinhamento concatenado editada no Inkscape, unindo as árvores de Máxima Verossimilhança e Inferência Bayesiana (formato SVG)</a></li>
</ul>
</div>

## Edição de árvores no Inkscape

<div align="justify">
Após abrir o Inkscape, abra o arquivo da árvore no formato SVG para iniciar a edição, clicando na opção “<i>Abrir</i>” do menu “<i>Arquivo</i>” e procurando o arquivo em seu computador (para esse exemplo, editaremos a árvore “<b>Aula_07_Arvore_EFTUB_IQTREE.svg</b>”, mas pode ser utilizada qualquer árvore listada no início do tutorial, ou até mesmo uma árvore que você tenha produzido):
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_08/aula_08_1.png" alt="Opção Abrir dentro do menu Arquivo do Inkscape" align="center">
</center>
<br><br>
Ao abrir a imagem, você verá que não será possível modificar os elementos da imagem individualmente. Como nosso interesse é justamente realizar os ajustes nesses elementos, precisamos habilitar essa opção. Para isso, clique sobre a árvore fazendo com que apareça uma caixa de seleção ao redor de toda a imagem. Em seguida, clique na opção “<i>Desagrupar</i>” dentro do menu “<i>Objeto</i>”. Isso fará com que os elementos individuais da imagem sejam desvinculados uns dos outros, e possam ser editados individualmente:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_08/aula_08_2.png" alt="Opção Desagrupar dentro do menu Objeto do Inkscape" align="center">
</center>
<br><br>
Vamos editar regiões específicas da árvore para com auxílio da ferramenta de zoom. O zoom pode ser ajustado com as teclas “+” ou “-” do teclado numérico, ou segurando a tecla “Ctrl” ao girar a barra de rolagem do mouse. A primeira edição que faremos é remover os underlines presentes nos nomes dos indivíduos e substituí-los por espaços, com a opção “<i>Encontrar/Substituir</i>” do menu superior “<i>Editar</i>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_08/aula_08_3.png" alt="Opção Encontrar/Substitutir dentro do menu Editar do Inkscape" align="center">
</center>
<br><br>
A aba “<i>Encontrar/Substituir</i>” será aberta na lateral direita da janela. Digite os caracteres que deseja substituir no campo “<i>Encontrar</i>” e o caractere a ser utilizado para substituição no campo “<i>Substituir</i>”. Selecione as opções “<i>Procurar em - Texto</i>” e “<i>Escopo – Tudo</i>”, e em seguida “<i>Substituir Tudo</i>” para alterar todas as ocorrências do caractere no texto. Uma sugestão é inicialmente substituir “Fusarium_sp_” por “Fusarium sp. ” (com um espaço após o “sp.”) para garantir que o ponto após “sp” seja adicionado, e em seguida substituir underlines por espaços:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_08/aula_08_4.png" alt="Configurações da opção Encontrar/Substitutir dentro do menu Editar do Inkscape" align="center">
</center>
<br><br>
Em seguida, vamos melhorar o posicionamento dos valores de suporte para que não fiquem sobre o texto. Dessa forma, já iremos posicioná-los nos locais corretos à esquerda dos nós da árvore, e facilitar a edição dos nomes dos indivíduos posteriormente. Para isso, clique sobre os valores e, segurando o botão do mouse, arraste-os para a posição de interesse. Quando estiver satisfeito com o posicionamento, solte o botão. O ajuste do posicionamento também pode ser feito com as teclas direcionais do teclado: clique sobre o elemento a ser movido, ajuste sua posição com as teclas, e quando estiver satisfeito, clique em algum local vazio da imagem para remover a seleção. Outro ajuste importante envolve editar os valores de suporte em si e removê-los se for o necessário: em alguns casos, os valores de suporte são muito baixos e provavelmente indicam que o clado não apresenta suporte suficiente. Remover estes valores da imagem pode ajudar a deixar a árvore menos poluída.
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_08/aula_08_5.png" alt="Ajuste de posicionamento dos valores de suporte na árvore, durante edição no Inkscape" align="center">
</center>
<br><br> 
Além de editar a informação sobre o bootstrap e remover valores baixos, podemos adicionar os valores de probabilidade posterior obtidos em uma análise de inferência bayesiana (se o clado apresentar a mesma topologia em ambas as análises). Em alguns casos, é possível que um clado só possua um bom valor de suporte em uma das análises (por exemplo, na árvore proveniente da inferência bayesiana), e tenha um valor muito baixo na outra (por exemplo, na árvore de máxima verossimilhança). É possível apresentar o bom valor de suporte que apareceu, mas ainda assim informar ao leitor que aqueles clados não possuem suporte suficiente na outra análise. Para isso, pode-se adotar algum símbolo que represente esta ideia. É muito comum que autores utilizem um traço ou hífen (-) para clados que apresentem valor de suporte abaixo de um valor de corte previamente definido (por exemplo, valores de bootstrap abaixo de 70%, ou de bootstrap ultra rápido do IQ-TREE abaixo de 90 ou 95%, ou SH-aLRT acima de 80%, e de probabilidade posterior abaixo de 0.9). Nesse exemplo, adicionamos valores de suporte de probabilidade posterior, de modo que os nós apresentam, em ordem, à sua esquerda, valores de SH-aLRT, bootstrap ultra rápido e probabilidade posterior:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_08/aula_08_6.png" alt="Remoção dos baixos valores de suporte presentes na árvore, durante edição no Inkscape" align="center">
</center>
<br><br>
Para isso, clique na ferramenta “<i>Texto</i>” do menu lateral, e clique sobre o valor a ser editado. Em seguida, faça as edições que julgar necessárias, e ao terminar, clique na ferramenta “<i>Seletor</i>” para sair do modo de texto. 
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_08/aula_08_7.png" alt="Ferramentas Seletor e Texto no menu lateral do Inkscape" align="center">
</center>
<br><br>
Além de editar os valores de suporte dos clados, podemos utilizar a ferramenta texto para editar o nome dos indivíduos na árvore. Podemos deixar os nomes científicos destacados com itálico ou sublinhado, destacar linhagens-tipo em negrito, bem como adicionar outras informações que julgarmos necessárias. Também é possível alterar o tamanho, o alinhamento horizontal, e criar textos sobre ou sub escritos.
<br><br>
Ao selecionar o texto de interesse, as ferramentas de edição aparecerão em caixas de seleção no menu superior. Além disso, é possível alterar a cor do texto utilizando as cores apresentadas no menu inferior. Neste exemplo, colocaremos todos os nomes científicos em itálico, destacaremos a linhagem tipo com negrito e um (T) sobrescrito. Também destacaremos as linhagens que haviam sido erroneamente identificadas com a cor vermelha, e destacaremos o nome do isolado que tínhamos interesse em identificar em azul. Outra alteração será mudar o nome de “Consenso” para “Fusarium awaxy LGMF1661”, ou seja, nome da espécie e código de coleção:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_08/aula_08_8.png" alt="Menus de Edição de Texto e troca de cores Inkscape, e edição de cores e fonte dos nomes dos indivíduos presentes na árvore" align="center">
</center>
<br><br>
Uma outra customização interessante consiste em criar formas e caixas de destaque ao redor dos clados que mereçam maior atenção dos leitores. Podemos criar uma caixa de destaque ao redor do clado “<i>Fusarium awaxy</i>”, sinalizando que o isolado que tínhamos interesse em identificar faz parte desse clado. Para isso, primeiro selecionamos a ferramenta “Retângulo no menu lateral:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_08/aula_08_9.png" alt="Ferramenta Retângulo no menu lateral do Inkscape">
</center>
<br><br>
Em seguida, podemos escolher a cor de interesse para o retângulo clicando na lista de cores na parte inferior da janela. É possível também escolher uma cor diferente para o contorno do retângulo, segurando Shift ao clicar na cor. No menu superior, nas opções “<i>Rx</i>” e “<i>Ry</i>” podemos deixar os cantos mais arredondados (aqui usaremos o valor “8” para as duas opções). Por fim, podemos alterar a opacidade do retângulo para facilitar a leitura do texto (nesse exemplo utilizamos opacidade “26”). Por fim, também foi inserido o texto “<i>Fusarium awaxy</i>” para sinalizar que todos os indivíduos destacados pelo retângulo pertencem à esta espécie (mesmo os que haviam sido erroneamente identificados como <i>Fusarium subglutinans</i>):
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_08/aula_08_10.png" alt="Criação de retângulo ao redor do clado de Fusarium awaxy durante edição da árvore no Inkscape">
</center>
<br><br>
De forma geral, estas são as edições mais importantes a se fazer para melhorar a qualidade e a apresentação visual de uma árvore filogenética. Agora que editamos o clado da espécie “<i>Fusarium awaxy</i>”, basta continuar as edições para o restante da árvore seguindo as mesmas instruções. No momento em que estiver satisfeito com o aspecto da imagem e não for mais necessário editar nenhum dos elementos, podemos exportar a imagem no formato PNG. Para isso, clique na ferramenta “<i>Seletor</i>” do menu lateral, selecione toda a imagem e clique na opção “<i>Exportar imagem PNG</i>” dentro do menu “<i>Arquivo</i>” na parte superior da janela. Na aba lateral que será aberta, podemos personalizar à vontade as dimensões do arquivo PNG sem perda de qualidade e sem criar imagens pixeladas. Esta é uma das grandes vantagens de se trabalhar com arquivos vetoriais no formato SVG para edição das árvores: podemos ajustar o tamanho de acordo com o espaço disponível em uma página de artigo, em uma apresentação de slides ou em um poster, por exemplo. Além disso, também é possível ajustar o tamanho de acordo com outras unidades como centímetros e polegadas, não apenas pixels. Após configurar o tamanho e unidade de interesse, basta clicar em “<i>Exportar Como</i>” e escolher a pasta em que a imagem deverá ser salva para concluir o processo:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_08/aula_08_11.png" alt="Exportando árvore final para formato PNG no Inkscape" align="center">
</center>
<br><br>
</div>


## Aula em vídeo

<br>
<div align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/TgdZRSBTdpE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe> 
<br><br>
Clique <a href="https://photos.app.goo.gl/sKeNARSjMUdkW7Wu6">aqui</a> para fazer o download do vídeo.
<br><br>
</div>
