---
title: "Aula 09 - Depósito de alinhamentos e árvores no TreeBASE"
linkTitle: "Aula 09 - Depósito de alinhamentos e árvores no TreeBASE"
weight: 9
description: >
  Softwares utilizados: Notepad ++ e TreeBASE (online)
---

<div align="justify">
Uma árvore esteticamente adequada em uma imagem com boa qualidade faz toda a diferença ao compor uma publicação, atraindo a atenção dos leitores e melhorando a recepção dos nossos trabalhos. Entretanto, é extremamente importante também divulgar e disponibilizar os dados por trás da imagem, para que a comunidade possa conferir e também se beneficiar das nossas análises. Esse processo tem se consolidado cada vez mais como um requisito obrigatório para publicação em muitas revistas, exigindo todas as sequências originais que foram produzidas no trabalho sejam depositadas no GenBank, e também que os alinhamentos e árvores filogenéticas sejam depositados no TreeBASE. 
<br><br>
Nesta atividade, abordaremos o depósito de alinhamentos e árvores no TreeBASE, que pode ser acessado <a href="https://www.treebase.org/treebase-web/home.html">aqui</a>.
<br><br>
Clique nos links abaixo para baixar os arquivos que serão utilizados nesta prática:
<br><br>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_09/aula_09.zip">Link para pasta com todos os arquivos (formato zip)</a></li>
<br>
Para baixar os arquivos individualmente:
<br><br>
<ul>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_09/Aula_09_Alinhamento_EF.nexus">Alinhamento da região de EF (formato NEXUS)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_09/Aula_09_Alinhamento_EFTUB.nexus">Alinhamento concatenado (formato NEXUS)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_09/Aula_09_Arvore_IQTREE.treefile">Arquivo de saída do IQ-Tree com a árvore da região de EF (formato TREEFILE)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_09/Aula_09_Arvore_EF_IQTREE.tre">Arquivo de saída do IQ-Tree com a árvore da região de EF adaptado (formato TRE)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_09/Aula_09_Arvore_EFTUB_IQTREE.treefile">Arquivo de saída do IQ-Tree com a árvore do alinhamento concatenado (formato TREEFILE)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_09/Aula_09_Arvore_EFTUB_IQTREE.tre">Arquivo de saída do IQ-Tree com a árvore do alinhamento concatenado adaptado (formato TRE)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_09/Aula_09_Arvore_EF_MrBayes.tre">Arquivo de saída do MrBayes com a árvore da região de EF (formato TRE)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_09/Aula_09_Arvore_EFTUB_MrBayes.tre">Arquivo de saída do MrBayes com a árvore do alinhamento concatenado (formato TRE)</a></li>
</ul>
</div>

## Criando um cadastro de usuário no TreeBASE

<div align="justify">
O TreeBASE é um repositório online de informações filogenéticas, e aceita os mais diversos tipos de dados, sem restrição a nenhum tipo de organismo. Seu uso é gratuito e não há necessidade de cadastro para utilizar as ferramentas de busca. Entretanto, para depositar um alinhamento ou árvore, o cadastro é obrigatório. Para realizar o cadastro, após acessar o TreeBASE, clique em “<i>Upload Data</i>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_1.png" alt="Página inicial do TreeBASE com destaque para a opção Upload Data" align="center">
</center>
<br><br>
Na página seguinte, clique em “New to Treebase? Click here to Signup” caso ainda não tenha o cadastro:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_2.png" alt="Tela de login do TreeBASE" align="center">
</center>
<br><br>
Preencha seus dados na página seguinte, e clique em “<i>Register</i>” para concluir o cadastro:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_3.png" alt="Página de cadastro de usuário no TreeBASE" align="center">
</center>
<br><br>
Após concluir o cadastro, retorne para a tela de login e utilize seus dados para acessar sua conta.
<br><br>
</div>


## Depositando os alinhamentos e árvores

<div align="justify">
Ao fazer o login, seremos redirecionados para a página inicial de usuário em que consta uma lista de todos depósitos que criamos. Em uma conta recém-criada a lista estará vazia, visto que nenhum depósito foi criado ainda. Para começar um novo depósito, clique em “<i>New Submission</i>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_4.png" alt="Opção New Submission na tela inicial do TreeBASE" align="center">
</center>
<br><br>
Na página “<i>Create New Submission</i>”, informe um nome para o seu depósito no campo “<i>Name of study</i>”, e caso queira fornecer informações adicionais, é possível preenchê-las no campo “<i>Notes for study</i>”. Não é necessário que o nome do depósito corresponda ao título da publicação, e existirão outros campos para adicionar informações relativas à publicação. Após preencher as informações, clique em "<i>Submit</i>" para prosseguir:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_5.png" alt="Página Create New Submission dentro do TreeBASE" align="center">
</center>
<br><br> 
Após clicar em “<i>Submit</i>” você será redirecionado à página de gerenciamento do depósito. Em “<i>Summary</i>”, podemos observar qual é o código permanente do depósito em “<i>Submission</i>” (nesse caso, 27921) e o status (“<i>In Progress</i>”). Em “<i>Study Accession URL</i>” podemos encontrar o link permanente que pode ser incluído na publicação para que os leitores possam acessar o depósito. Além deste link, temos um link secreto em “<i>Reviewer access URL</i>”, que podemos enviar aos revisores da publicação ou divulgar de forma mais restrita enquanto o depósito estiver privado.
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_6.png" alt="Página de gerenciamento da submissão no TreeBASE com links para divulgar o depósito" align="center">
</center>
<br><br>
Nas abas da lateral direita (“<i>Tool Box</i>”), podemos encontrar opções para complementar as informações sobre o depósito (abas “Citation” e “Authors”) incluir arquivos no depósito (aba “<i>Upload</i>”), validar os indivíduos com base em dados taxonômicos (aba “<i>Taxa</i>”), gerenciar os alinhamentos (“<i>Matrices</i>”), gerenciar as árvores (“<i>Trees</i>”), criar e organizar as análises (“<i>Analyses</i>”) e obter o histórico de todos os arquivos que em algum momento fizeram parte do depósito (“<i>Files</i>”). Vamos discorrer sobre cada uma das opções:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_7.png" alt="Opções disponíveis na aba lateral Tool Box" align="center">
</center>
<br><br>
Na opção "<i>Citation</i>", podemos incluir informações sobre a publicação, como título, palavras-chave e resumo, e também informações sobre a revista. No campo “<i>Status</i>” é possível informar em qual estágio a publicação se encontra, de modo que o TreeBASE saiba se é um manuscrito em preparação, ou se já se trata de um trabalho já publicado. Como muitas vezes iniciamos os depósitos na fase de preparação de um manuscrito, não é obrigatório fornecer dados sobre a revista (ou até mesmo o DOI!). Esses dados só serão obrigatórios no momento de tornar o depósito público e aberto para toda a comunidade, uma vez que, diferentemente do GenBank, o TreeBASE só libera depósitos que estejam associados a uma publicação. Após inserir as informações que julgar necessárias, clique em “<i>Submit</i>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_8.png" alt="Preenchimento da aba Citation dentro do TreeBASE" align="center">
</center>
<br><br>
Na aba “<i>Authors</i>” podemos informar os autores associados à publicação. Em alguns casos, quando os autores já estão associados a outros depósitos, é possível encontrá-los ao digitar seu último nome na ferramenta de busca e clicando em “<i>Search</i>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_9.png" alt="Campo de busca por sobrenome de autores na aba Authors do TreeBASE" align="center">
</center>
<br><br>
Caso a busca não retorne nenhum autor, é possível adicionar as informações no campo “<i>New Author Information</i>”. Informe o nome completo e o endereço de e-mail e clique em “<i>Submit</i>”. Por outro lado, caso o sistema encontre alguma correspondência, esta estará listada em “<i>Matched Authors</i>”. Confira as informações e caso correspondam ao autor de interesse, clique em “<i>Insert</i>”. É comum o surgimento de registros redundantes ao longo dos depósitos (principalmente pelo fato de que as mesmas pessoas são cadastradas inúmeras vezes por pesquisadores diferentes). Nesse exemplo, podemos ver que há 3 registros diferentes para a mesma pessoa:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_10.png" alt="Campo New Author Information e campo Matched Authors mostrando três registros redundantes para autor no TreeBASE" align="center">
</center>
<br><br>
Após adicionar todos os autores à lista, é possível mudar a ordem com as opções “Up” e “Down” em “Author Order”. Além disso, também é possível excluir um autor utilizando o ícone “X” ao lado de seu nome:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_11.png" alt="Opções UP e DOWN para mudar a ordem de listagem de autores e opção X para exclusão de autor na aba Authors do TreeBASE" align="center">
</center>
<br><br>
Na aba “<i>Upload</i>” podemos enviar os arquivos que irão compor o depósito (alinhamentos e árvores). Uma vez que o depósito se refere ao estudo como um todo (e não a análises específicas dentro de um estudo), podemos enviar todos os alinhamentos e árvores que foram produzidos e apresentados no estudo (inclusive se foram apresentados somente no material suplementar). Nesse momento não é necessário nos preocuparmos em organizar os dados por análise, pois esta configuração será feita em outra aba.
<br><br>
No campo “<i>Nexus Files Upload</i>” selecione os arquivos a serem enviados para o depósito. Os alinhamentos devem estar no formato NEXUS (caso não estejam, utilize a opção “<i>Convert sequence format</i>” do PhyloSuite para adequar o formato) e as árvores devem estar neste formato também.
<br><br>
A árvore do MrBayes produzida no PhyloSuite já está automaticamente neste formato, mas a árvore produzida no IQ-TREE precisará ser editada, pois o formato “.TREEFILE” não é interpretado adequadamente pelo TreeBASE. Para adequar o formato, abra o arquivo da árvore do IQ-TREE no Notepad ++, e abra também o arquivo da árvore do MrBayes. No arquivo da árvore do MrBayes, copie todas as linhas entre a primeira linha “#NEXUS” e a linha “<i>begin trees;</i>” e cole no começo do arquivo da árvore do IQ-TREE. Em seguida, antes da árvore do IQ-TREE, adicione o termo “<i>tree=</i>”.
<br><br> 
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_12.png" alt="Inclusão dos termos begin trees e tree= no arquivo de árvore obtido no IQ-TREE" align="center">
</center>
<br><br>
Por fim, adicione uma linha com o termo “<i>end;</i>” no final do arquivo. 
<br><br> 
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_13.png" alt="Inclusão do termo end no final do arquivo de árvore obtido no IQ-TREE" align="center">
</center>
<br><br>
Seguindo estas instruções teremos criado um bloco de táxon no arquivo com a lista de todos os indivíduos incluídos na análise. Além disso, teremos criado um bloco com a árvore, possibilitando de o TEEBASE consiga ler e interpretar o arquivo futuramente. Caso tenha alguma dúvida sobre as alterações necessárias, confira os arquivos de modelo listados no início desta prática e use-os como exemplos.
<br><br>
Adicione os arquivos na aba “<i>Nexus Files Upload</i>” e use a opção “<i>Attach another file</i>” para adicionar quantos arquivos forem necessários. Após selecionar todos os arquivos de interesse, clique em “<i>Upload</i>”.
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_14.png" alt="Campo File Upload no TreeBASE" align="center">
</center>
<br><br>
Após realizar o Upload, os arquivos estarão listados na aba “Files”. Esta aba manterá um registro permanente dos arquivos que forem enviados, por mais que futuramente sejam excluídos ou substituídos no depósito. Confira se os arquivos enviados constam na lista, e se tudo estiver certo, siga para as próximas etapas.
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_15.png" alt="Aba Files com a lista de arquivos enviados para o depósito no TreeBASE" align="center">
</center>
<br><br>
Após enviar os arquivos é necessário realizar alguns ajustes e fornecer informações sobre os conjuntos de dados. Na aba “<i>Taxa</i>” o TreeBASE tentará vincular os organismos presentes nos alinhamentos e árvores à organismos que estejam listados no NCBI e no uBIO. Ao carregar a página pela primeira vez, um aviso é mostrado, informando que os organismos ainda não foram vinculados à uma base de dados taxonômicos externa:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_16.png" alt="Campo Taxon Labels mostrando os indivíduos que ainda não foram validados contra uma base de dados taxonômicos" align="center">
</center>
<br><br>
Para vincular os indivíduos automaticamente clique na opção “<i>Validate Taxon Labels</i>” no final da página:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_17.png" alt="Opção Validate Taxon Labels no TreeBASE" align="center">
</center>
<br><br>
Ao recarregar a página o TreeBASE novamente mostrará um aviso caso não tenha sido encontrada uma correspondência na base de dados taxonômicos externa:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_18.png" alt="Lista de indivíduos que mesmo após o uso da opção Validate Taxon Labels ainda não possuem correspondência em um banco de dados taxonômico" align="center">
</center>
<br><br>
Para os indivíduos em que a validação foi bem sucedida, será adicionado um identificador às colunas “<i>NCBI taxid</i>” e “<i>uBIO namebankID</i>”, correspondente ao registro das respectivas espécies nestas duas bases de dados. Para alguns grupos de organismos não é incomum que a validação não seja bem sucedida em algumas espécies, principalmente quando as duas bases de dados não estão devidamente atualizadas com os nomes científicos das espécies recentemente descritas. Caso você deseje conferir se os registros da espécie realmente não existe, é possível pesquisar pelo nome da espécie no NCBI e no uBIO. Se existir um registro, é possível editar as informações do depósito clicando no ícone de lápis e adicionar o código do registro manualmente. 
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_19.png" alt="Lista de indivíduos mostrando exemplos de taxon validado vs. não validado e ícone de lápis para validação manual" align="center">
</center>
<br><br>
Embora exista este problema com as bases de dados, erros no processo de validação podem acontecer em função de como organizamos os dados no alinhamento e na árvore. Para que o TreeBASE possa ler e interpretar o nome de um organismo adequadamente, este nome precisa estar no formato “[Gênero]_[epíteto_específico]_[código_identificador_do_indivíduo]”, tal como em “<b>Fusarium_fujikuroi_NRRL13998</b>”. Nomes de gênero abreviados (tal como “F_” ao invés de “Fusarium_”), quaisquer caracteres extras, espaços ao longo do nome da sequência ou espaços no meio do código identificador do indivíduo (por exemplo, “NRRL 13998” ao invés “NRRL 13998”) impedem que o TreeBASE consiga identificar o nome correto da espécie. Nesse contexto, reforça-se ainda mais a importância de organizar os arquivos de alinhamentos e sequências de forma correta desde o começo para evitar problemas numa etapa tão avançada do processo. 
<br><br>
Após revisar todos os indivíduos e adicionar os códigos do NCBI ou uBIO quando possível, podemos prosseguir para a aba “<i>Matrices</i>”. Aqui devemos editar o nome da matriz em “<i>Matrix Title</i>” (em geral com o nome do(s) gene(s) presente(s) no alinhamento), adicionar informações descritivas em “<i>Description</i>” e selecionar o tipo de dados em “<i>Matrix Kind</i>”. Aqui como se trata de um alinhamento de sequências de DNA deve-se selecionar “<i>Nucleic Acid</i>”, mas é possível depositar sequências de aminoácidos e inclusive matrizes de caracteres morfológicos e comportamentais. Caso deseje excluir uma matriz, use o ícone de “X”. O ícone de círculo vermelho é importante pois sinaliza que esta matriz ainda não foi vinculada à nenhuma análise (configuração que faremos nas próximas etapas). Após configurar as análises, é importante voltar a esta aba e conferir se o ícone passou de vermelho para uma seta verde, garantindo que o TreeBASE reconheceu o vínculo. Ao finalizar de incluir as informações, clique em “<i>Update</i>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_20.png" alt="Edição e gerenciamento dos alinhamentos na aba Matrices do TreeBASE" align="center">
</center>
<br><br>
Na aba “<i>Trees</i>”, devemos editar o nome das árvores em “<i>Block Title</i>” (em geral com o nome do(s) gene(s) presente(s) no alinhamento e o software utilizado na análise e/ou método filogenético). Caso deseje excluir uma árvore, use o ícone de “X”. O ícone de círculo vermelho também é importante aqui, e nesse caso sinaliza que a árvore ainda não foi vinculada à nenhuma análise (configuração que faremos nas próximas etapas). Após configurar as análises, é importante voltar a esta aba e conferir se o ícone passou de vermelho para uma seta verde, garantindo que o TreeBASE reconheceu o vínculo entre a árvore e análise. Ao finalizar de incluir as informações, clique em “<i>Update</i>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_21.png" alt="Edição e gerenciamento dos arquivos de árvores na aba Trees do TreeBASE" align="center">
</center>
<br><br>
Na aba “<i>Analyses</i>” iremos estabelecer os vínculos entre alinhamentos e árvores, e informar quais softwares foram utilizados e quais métodos filogenéticos foram empregados nas análises. Clique no ícone de “+” para criar uma nova análise:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_22.png" alt="Criação de uma nova análise na aba Analyses do TreeBASE" align="center">
</center>
<br><br>
Clique no ícone de lápis e adicione um nome e detalhes para a análise nos campos “<i>Name</i>” e “<i>Notes</i>” respectivamente. Em geral as análises são divididas por alinhamento. Sendo assim, para cada alinhamento, crie uma nova análise, e inclua todas as árvores produzidas com este mesmo alinhamento na mesma análise. Ao terminar de editar as informações, clique em “<i>Update</i>” para salvar, e depois no ícone de “+” para adicionar a primeira etapa da análise:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_23.png" alt="Edição dos detalhes da análise como título e notas e criação da primeira etapa da análise" align="center">
</center>
<br><br>
Na primeira etapa, vamos configurar a análise de máxima verossimilhança. Escolha “<i>Matrices</i>” como “<i>Input data</i>” e “<i>Tree blocks</i>” como "<i>Output data</i>". Ao selecionar estas opções, o TreeBASE retornará os possíveis arquivos de entrada no formato “<i>Matrices</i>” (os alinhamentos), e possíveis arquivos de saída no formato “<i>Tree Blocks</i>” (as árvores). Selecione o alinhamento de EF como “<i>Input Data</i>” e a árvore de máxima verossimilhança do IQ-TREE como “Output Data”. No campo “<i>Analysis step</i>”, preencha o campo “<i>Name</i>” com o nome que deseja designar para a análise (em geral, o método utilizado). No campo “<i>Software used</i>”, informe o nome do software (nesse caso, “<i>IQ-TREE</i>”), e na opção “<i>Algorithm</i>”, selecione o tipo de método filogenético utilizado (nesse caso, “<i>maximum likelihood</i>”). Insira informações complementares como versão do software e comandos se julgar necessário, clique em “<i>"Update</i>” para salvar e depois no ícone de “+” para criar a segunda etapa da análise:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_24.png" alt="Configuração da primeira etapa da análise com os dados da máxima verossimilhança" align="center">
</center>
<br><br>
Na segunda etapa, vamos configurar a análise de inferência bayesiana. Escolha “<i>Matrices</i>” como “<i>Input data</i>” e “<i>Tree blocks</i>” como "<i>Output data</i>". Ao selecionar estas opções, o TreeBASE retornará os possíveis arquivos de entrada no formato “<i>Matrices</i>” (os alinhamentos), e possíveis arquivos de saída no formato “<i>Tree Blocks</i>” (as árvores). Selecione o alinhamento de EF como “<i>Input Data</i>” e a árvore de inferência bayesiana do MrBayes como “<i>Output Data</i>”. No campo “<i>Analysis step</i>”, preencha o campo “<i>Name</i>” com o nome que deseja designar para a análise (em geral, o método utilizado). No campo “<i>Software used</i>”, informe o nome do software (nesse caso, “<i>MrBayes</i>”), e na opção “<i>Algorithm</i>”, selecione o tipo de método filogenético utilizado (nesse caso, “<i>bayesian inference</i>”). Insira informações complementares como versão do software e comandos se julgar necessário, clique em “<i>Update</i>” para salvar.
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_25.png" alt="Configuração da primeira etapa da análise com os dados da inferência bayesiana" align="center">
</center>
<br><br>
Após configurar as análises, volte às abas “<i>Matrices</i>” e “<i>Trees</i>” e confira se os alinhamentos e árvores do depósito agora possuem uma seta verde, indicando que o TreeBASE reconheceu os vínculos entre todos os arquivos:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_26.png" alt="Aba Matrices mostrando um alinhamento vinculado à uma análise, indicado pela seta verde" align="center">
</center>
<br><br>
Se os arquivos tiverem sido reconhecidos e vinculados, a configuração do depósito foi efetuada com sucesso. Enquanto o status do depósito for “<i>In Progress</i>”, os arquivos podem ser modificados, excluídos ou substituídos à vontade. Quando todas as alterações e configurações necessárias forem realizadas e o depósito estiver pronto para ser liberado ao público e a publicação foi aceita, clique na aba “<i>Submissions</i>” e na opção “<i>Change to Ready Status</i>” dentro do menu “<i>Change Status</i>” para finalizar o depósito:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_27.png" alt="Opção Change to Ready Status na aba Submissions para finalizar o depósito no TreeBASE" align="center">
</center>
<br><br>
</div>

## Obtendo alinhamentos e árvores no TreeBASE

<div align="justify">
Visto que o TreeBASE é um repositório de alinhamentos e árvores filogenéticas, além de enviarmos os nossos próprios dados, também é possível fazer buscas e obter acesso aos dados presentes em artigos de outros pesquisadores. Esse recurso é bastante útil para obter alinhamentos e árvores de referência que podem vir a servir como base para nossas próprias análises.
<br><br>
Para começar a pesquisa, clique na opção “<i>Search Data</i>” na página inicial do TreeBASE:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_28.png" alt="Opção Search Data na página inicial TreeBASE" align="center">
</center>
<br><br>
Na página de busca será possível procurar por estudos completos (“<i>Studies</i>”), alinhamentos ou matrizes (“<i>Matrices</i>”), árvores (“<i>Trees</i>”), espécies de organismos (“<i>Taxa</i>”) ou por topologias de árvores (“<i>Tree Topologies</i>”). Também é possível alterar o tipo de busca na caixa de seleção, optando por ID do estudo (“<i>Study ID</i>” ou “<i>Legacy Study ID</i>”), autores (“<i>Author</i>”), título (“<i>Title</i>”), palavras do resumo (“<i>Abstract</i>”), citação (“<i>Entire citation</i>”), presença da palavra em qualquer lugar do texto (“<i>All text</i>”) ou pelo Digital Object Identifier/DOI do artigo (“<i>DOI</i>”). Dentre todas, “<i>All text</i>” é a opção mais flexível. 
<br><br>
Para iniciarmos nossa busca, digite o termo “<b>fusarium</b>” na caixa de pesquisa, selecione a opção “<i>All text</i>” e clique em “<i>Search</i>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_29.png" alt="Opções de busca no TreeBASE" align="center">
</center>
<br><br>
Na página seguinte podemos observar que a busca retornou 92 depósitos de diferentes estudos. No cabeçalho da tabela é possível filtrar e ordenar os dados de acordo com a ID do estudo, ordem alfabética de autores (“<i>Authors</i>”), título (“<i>Title</i>”) e revista em que o trabalho foi publicado (“<i>Journal/Publisher</i>”), e também em ordem cronológica de ano. Clique duas vezes em “<i>Year</i>” para ordenar os resultados dos mais recentes para os mais antigos. É importante ter em mente que visto que nem todas as revistas exigem o depósito no TreeBASE antes de uma publicação, não encontraremos dados referentes a todos os artigos já publicados que estejam relacionados à filogenia de <i>Fusarium</i>.
<br><br>
Dentre os resultados disponíveis, iremos baixar os dados do estudo intitulado “<b>Epitypification of <i>Fusarium oxysporum</i> – clearing the taxonomic chaos</b>” clicando na ID de número <b>S23815</b>:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_29.png" alt="Lista de resultados obtidos com a busca do termo fusarium, com destaque para o estudo S23815" align="center">
</center>
<br><br>
Na página do estudo, podemos verificar informações sobre o estado do trabalho, que neste caso está publicado, bem como a citação, lista de autores e e-mails para contato. Para acessar os arquivos, devemos utilizar as abas na área superior. Em “<i>Taxa</i>” encontraremos a lista de espécies que foram avaliadas no estudo. Já em “<i>Matrices</i>", é possível obter os alinhamentos produzidos no estudo, enquanto em “<i>Trees</i>” será possível realizar o download das árvores. Em ambas as abas “<i>Matrices</i>” e “<i>Trees</i>” poderemos fazer o download dos arquivos no formato “<i>NexML</i>”, “<i>Reconstructed Nexus</i>” ou obter o arquivo original que os autores enviaram ao TreeBASE na opção “<i>Download Original File</i>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_30.png" alt="Opções de download de arquivos no depósito S23815 no TreeBASE" align="center">
</center>
<br><br>
Por fim, na aba “<i>Analyses</i>” é possível obter mais informações sobre as análises realizadas no estudo, e identificar quais árvores foram obtidas a partir de quais alinhamentos. Neste exemplo, em “<i>Input data</i>” está listado o alinhamento de entrada, em “<i>Analysis step</i>” está a informação de que foi realizada uma análise filogenética de Inferência Bayesiana, e em “<i>Output data</i>" está listada a árvore obtida:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_09/aula_09_31.png" alt="Aba Analyses do depósito S23815 no TreeBASE" align="center">
</center>
<br><br>
</div>

## Aula em vídeo

<br>
<div align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/DpjuwRD_1vY" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe> 
<br><br>
Clique <a href="https://photos.app.goo.gl/tVdKKafLdas3Mki78">aqui</a> para fazer o download do vídeo.
<br><br>
</div>
