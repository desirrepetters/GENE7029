---
title: "Aula 10 - Depósito de sequências no GenBank"
linkTitle: "Aula 10 - Depósito de sequências no GenBank"
weight: 10
description: >
  Softwares utilizados: Notepad ++, Microsoft Excel (ou outro editor de planilhas e tabelas), NCBI GenBank e Augustus (online)
---

<div align="justify">
Na atividade anterior discutimos a importância de depositar os dados que compõem e dão suporte às nossas análises, com uma demonstração como depositar alinhamentos e árvores no TreeBASE. Em muitos casos, quando trabalhamos apenas com sequências já disponíveis na literatura, apenas depositar estes dois tipos de dados já é suficiente no contexto de uma publicação. Entretanto, caso nosso estudo tenha gerado sequências originais e incluído estas sequências nas análises, também é necessário disponibilizá-las à comunidade científica por meio de um depósito no GenBank. 
<br><br>
Nesta atividade, abordaremos o depósito de sequências de DNA no GenBank, focando em sequências geradas por sequenciamento Sanger. Para acessar o GenBank, clique <a href="https://www.ncbi.nlm.nih.gov/genbank/">aqui</a>.
<br><br>
Clique nos links abaixo para baixar os arquivos que serão utilizados nesta prática:
<br><br>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_10/aula_10.zip">Link para pasta com todos os arquivos (formato zip)</a></li>
<br>
Para baixar os arquivos individualmente:
<br><br>
<ul>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_10/Aula_10_Sequencias_ITS.fasta">Arquivo com sequências ITS (formato FASTA)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_10/Aula_10_Modelo_para_Source_Modifiers_ITS.xlsx">Arquivo “Source Modifiers” das sequências ITS para editar no Excel (formato XLSX)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_10/Aula_10_Source_Modifiers_ITS.txt">Arquivo “Source Modifiders” das sequências ITS para depósito no GenBank (formato TXT separado por tabulações)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_10/Aula_10_Sequencias_EF.fasta">Arquivo com sequências EF (formato FASTA)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_10/Aula_10_Modelo_para_Source_Modifiers_EF.xlsx">Arquivo “Source Modifiers” das sequências EF para editar no Excel (formato XLSX)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_10/Aula_10_Source_Modifiers_EF.txt">Arquivo “Source Modifiers” das sequências EF para depósito no GenBank (formato TXT separado por tabulações)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_10/Aula_10_Modelo_para_Features.xlsx">Arquivo “Features” das sequências EF para editar no Excel (formato XLSX)</a></li>
<li><a href="https://github.com/desirrepetters/cursodefilogenia.ufpr/raw/master/userguide/content/pt-br/docs/praticas/example_files/aula_10/Aula_10_Features_EF.txt">Arquivo “Features” das sequências EF para depósito no GenBank (formato TXT separado por tabulações)</a></li>
</ul>
</div>

## Criando um cadastro de usuário no NCBI

<div align="justify">
Assim como no TreeBASE, vimos durante as aulas que para pesquisar informações e dados no GenBank e em outros sites do NCBI não é necessário possuir um cadastro de usuário. Entretanto, para depositar uma sequência ou outros tipos de dados, o cadastro é obrigatório. Para realizar o cadastro, após acessar o GenBank, clique em “<i>Sigin to NCBI</i>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_1.png" alt="Opção Sign in to NCBI na página inicial do GenBank" align="center">
</center>
<br><br>
Em seguida, clique em “<i>Register for an NCBI account</i>” caso ainda não tenha um cadastro:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_2.png" alt="Opção Register for an NCBI account na página Sign in to NCBI" align="center">
</center>
<br><br>
Preencha seus dados na página seguinte, e clique em “<i>Create account</i>” para concluir o cadastro. Caso sua instituição esteja listada na opção “<i>Skip registration by using a 3rd party sign in option</i>”, é possível fazer o login diretamente com seu e-mail institucional:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_3.png" alt="Opções Create account e Skip registration by using a 3rd party sign in option" align="center">
</center>
<br><br>
Após concluir o cadastro, retorne para a tela de login e utilize seus dados para acessar sua conta. Para depositar sequências no GenBank o primeiro passo será acessar o BankIt. Na página inicial do BankIt é possível selecionar o tipo de sequência a ser depositado e clicar em “<i>Start</i>”. A depender do tipo de material a ser depositado, diferentes arquivos serão necessários. Sendo assim, o tutorial será dividido entre o depósito de sequências que são processadas automaticamente sem necessidade de um arquivo de anotação <b>(a)</b>, e sequências que necessitam um arquivo de anotação <b>(b)</b>:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_4.png" alt="Opção (a) para depósito via Submission Portal e (b) para depósito via BankIt" align="center">
</center>
<br><br>
</div>

## Depositando sequências no GenBank via Submission Portal

<div align="justify">
O “Submission Portal” é um sistema unificado para diversos tipos de submissão, tais como sequências de RNA ribossomal (rRNA), rRNA-ITS, COX1 mitocondrial, vírus Influenza, Norovirus, Dengue ou SARS-CoV-2. Para estes tipos de sequências, o sistema é capaz de realizar o depósito de forma bastante automatizada, sem que seja necessário que o usuário forneça um arquivo de anotação da sequência. Dessa forma, o processo de depósito é bastante simplificado.
<br><br>
Ao acessar o “<i>Submission Portal</i>”, clique em “<i>New submission</i>” para começar o depósito, e certifique-se de que realmente vai depositar as sequências que o sistema é capaz de processar. Do contrário, <a href="https://cursodefilogeniaufpr.netlify.app/docs/praticas/aula_10/#depositando-sequências-no-genbank-via-bankit">siga as instruções para depósito no BankIt</a>.
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_5.png" alt="Opção New submission na página inicial do Submission Portal" align="center">
</center>
<br><br>
Em seguida, na janela “<i>Submission Type</i>”, escolha o tipo de sequência a ser depositada no campo “<i>What do your sequences contain?</i>”. Neste exemplo simularemos o depósito de sequências de ITS de isolados de <i>Fusarium</i>, então selecionaremos “<i>Eukaryotic Nuclear rRNA/ITS</i>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_6.png" alt="Opção Eukaryotic Nuclear rRNA/ITS na aba Submission Type do Submission Portal" align="center">
</center>
<br><br>
Como selecionamos esta opção, o Submission Portal solicita mais informações sobre as informações contidas na sequência a ser depositada. Para sequências de ITS, o sistema busca saber se a sequência apresenta apenas algum dos espaçadores (“<i>ITS1 only</i>” ou “<i>ITS2 only</i>”), se apresenta apenas algum dos genes das subunidades do rRNA (“<i>18S rRNA only</i>” ou “<i>28S rRNA only</i>”), ou se contém várias das regiões mencionadas (“<i>contains rRNA-ITS region</i>”). A sequência do nosso exemplo contém as regiões ITS 1, 5.8S e ITS2, de modo que selecionaremos então a primeira opção:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_7.png" alt="Opção cointains rRNA-ITS region na aba Submission Type" align="center">
</center>
<br><br>
Também podemos criar um título interno para nossa submissão. Ele será um título pessoal, que não será disponibilizado publicamente no GenBank, mas que auxilia no controle interno ao consultar sua lista de submissões futuramente. Neste exemplo utilizaremos o título “<i>ITS_Fusarium_awaxy</i>”, e clicaremos em “<i>Continue</i>” para prosseguir:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_8.png" alt="ITS_Fusarium_awaxy como Submission title" align="center">
</center>
<br><br>
Na janela seguinte, na aba “<i>Submitter</i>” forneceremos informações sobre os autores da sequência, como nome, departamento ou instituição de vínculo (em que as sequências foram produzidas), endereço e dados de contato (para que o GenBank possa entrar em contato sobre situações relacionadas ao depósito). Nesse exemplo, utilizaremos informações sobre o Laboratório de Bioprospecção e Genética Molecular de Microrganismos para o campo “<i>Affiliation</i>”. Ao preencher as informações, é importante não utilizar acentos ou caracteres especiais, pois não são reconhecidos pelo sistema:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_9.png" alt="Campo Affiliation na aba Submitter" align="center">
</center>
<br><br>
No campo “<i>Contact information</i>” utilizaremos como exemplo os dados do curso. Lembre-se que para os telefones é necessário inserir os códigos de área correspondentes:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_10.png" alt="Campo Contact information na aba Submitter" align="center">
</center>
<br><br>
Na janela seguinte, na aba “<i>Sequencing Technology</i>” e no campo “<i>Method</i>”, informe o método utilizado para obter as sequências. Neste exemplo, as sequências foram obtidas pelo método de Sanger, então selecionaremos “<i>Sanger dideoxy sequencing</i>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_11.png" alt="Campo Method na aba Sequencing Technology do Submission Portal" align="center">
</center>
<br><br>
Como é possível montar sequências a partir de outras sequências, no campo "<i>Assembly State</i>" podemos informar se a sequência é composta por um único read/sequência, ou se é um consenso a partir de duas ou mais sequências. Nesse exemplo as sequências foram obtidas a partir de uma sequência só, sem produção de consenso, então selecionaremos “<i>Unassembled sequence reads</i>” e clicaremos em “<i>Continue</i>” para prosseguir:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_12.png" alt="Campo Assembly state na aba Sequencing Technology do Submission Portal" align="center">
</center>
<br><br>
Na aba “<i>Sequences</i>” da janela seguinte, no campo “<i>Release date</i>” podemos informar a data em que as sequências serão liberadas para o público. Se quiser que as sequências se tornem públicas imediatamente, utilize a opção “<i>Release immediately upon processing</i>”. Caso queira definir uma data futura, mantendo as sequências privadas e fechadas, utilize a opção “<i>Release on specified date or upon publication, whichever is first</i>”. Nesse segundo caso, o NCBI GenBank irá liberar as sequências na data determinada ou quando forem citadas em uma publicação, dependendo do que ocorrer antes. Nesse momento é importante ter em mente quais são nossas perspectivas em relação à publicação, para que não seja definido um prazo muito curto e as sequências não se tornem públicas num momento inadequado. Uma boa estratégia é tentar utilizar sempre o prazo máximo disponível de 4 anos, para garantir um bom prazo. Neste exemplo utilizaremos a segunda opção, com o prazo de 18 de Janeiro de 2024:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_13.png" alt="Campo Release date na aba Sequences do Submission Portal" align="center">
</center>
<br><br>
A seguir, no campo “<i>Sequences</i>”, forneça o arquivo com as sequências no formato FASTA. Clique em “<i>Choose file</i>” para fazer o upload do arquivo. É recomendável que os cabeçalhos das sequências possuam uma nomenclatura simples e curta, como os do exemplo (“<b>Seq1</b>”, “<b>Seq2</b>”). Informações sobre o nome da espécie e do isolado serão fornecidas em outro momento, a partir de outro arquivo. Após fazer o upload do arquivo (neste exemplo, utilizaremos o arquivo “<b>Aula_10_Sequencias_ITS.FASTA</b>”), clique em “<i>Continue</i>” para prosseguir. Caso seja necessário modificar, adicionar ou excluir alguma sequência antes de finalizar a submissão, deve-se fazer um upload de um novo arquivo com as modificações necessárias:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_14.png" alt="Campo de Upload na aba Sequences do Submission Portal" align="center">
</center>
<br><br>
Na janela seguinte, na aba “<i>Source Information</i>” e no campo “<i>Distinguishing Identifier for Source</i>”, começaremos a fornecer informações adicionais sobre os indivíduos de origem de cada sequência, tais como substrato de isolamento, origem geográfica, entre outras. Essas informações podem ser adicionadas uma a uma, ou através de uma tabela, facilitando o processo. Para cada uma das sequências o GenBank exige um identificador único, e aqui você deve selecionar qual campo será utilizado para individualizar as sequências, e que estará relacionado ao restante da tabela. Neste exemplo, utilizaremos o identificador “<i>Strain</i>”, e clicaremos em “<i>Continue</i>” para prosseguir:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_15.png" alt="Campo Distinguishing Identifier for Source na aba Source Information do Submission Portal" align="center">
</center>
<br><br>
Na janela seguinte, na aba “<i>Source Modifiers</i>”, o GenBank informa que os requisitos mínimos para cada sequência são o nome científico do organismo, e a linhagem que foi sequenciada, mas que podemos incluir outras informações adicionais. Para a inclusão destas informações podemos editar e incluir diretamente pelo navegador (“<i>Use an editable table</i>”), ou fazer o upload de um arquivo de texto simples separado por tabulações (“<i>Upload a tab-delimited file (template file provided</i>”). Para poucas sequências pode ser relativamente prático informar os dados diretamente no navegador, mas para conjuntos de muitas sequências este tipo de prática se torna inviável, sendo muito mais fácil realizar o upload do arquivo. 
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_16.png" alt="Aba Source Modifiers do Submission Portal" align="center">
</center>
<br><br>
Mas como devemos preparar este arquivo? Quais informações podem ser incluídas além dos requisitos obrigatórios? Na planilha do Excel intitulada “<b>Aula_10_Modelo_para_Source_Modifiers.xlsx</b>” podemos encontrar um exemplo com informações relacionadas às sequências para as quais estamos simulando o depósito: 
<br><br>
<ul>
<li><b>Sequence_ID”:</b> aqui devemos colocar os cabeçalhos das sequências no arquivo FASTA, para que o GenBank possa estabelecer a correspondência entre as sequências e o restante das informações. É importante inserir as sequências na tabela na mesma ordem que o arquivo FASTA.</li>
<li><b>“Organism”:</b> aqui devemos inserir o nome científico da espécie à qual os organismos pertencem, quando foi possível realizar a identificação. Caso a identificação não tenha sido possível, deve-se inserir a nomenclatura de forma indeterminada, no nível taxonômico mais restrito possível. Por exemplo, “<i>Fusarium</i> sp.”</li>
<li><b>“Strain”:</b> neste campo podemos inserir algum código pessoal que identifique os isolados dentro do nosso estudo ou publicação. Neste exemplo, foram inseridos os códigos que os organismos receberam ao serem depositados na coleção de culturas do Laboratório de Bioprospecção e Genética Molecular de Microrganismos (LGMF).</li>
<li><b>Coluna vermelha:</b> esta é uma coluna que serve somente para referência pessoal (para saber de que espécie o organismo se trata e/ou outras informações pessoais) e deve ser removida antes de exportar o arquivo para o depósito.</li>
<li><b>“Collected_by”:</b> aqui devemos inserir o sobrenome e iniciais do pesquisador responsável por coletar o indivíduo no ambiente.</li>
<li><b>“Collection_date”:</b> aqui devemos inserir a data em que o indivíduo foi coletado do ambiente.</li>
<li><b>“Country”:</b>aqui devemos inserir o país em que o indivíduo foi coletado.</li>
<li><b>“Identified_by”:</b> nesse campo indicamos o sobrenome e iniciais do pesquisador responsável por identificar o indivíduo.</li>
<li><b>“Host”:</b> aqui inserimos o nome científico hospedeiro em que o indivíduo foi coletado, caso essa informação faça sentido. Nesse caso em que se tratam de fungos fitopatogênicos em milho, o hospedeiro foi informado como “<i>Zea mays</i>”.</li>
<li><b>“Isolation_source”:</b> aqui podemos fornecer informações mais específicas sobre o substrato de isolamento, caso isso faça sentido. Nesse caso foram informados os órgãos da planta de onde cada indivíduo foi obtido, espiga (“<i>Maize ear</i>” e colmo (“<i>Maize stalk</i>”).</li>
<li><b>“Culture_collection”:</b>aqui podemos inserir códigos de coleções em que o indivíduo esteja depositado, caso isso tenha ocorrido. Nesse exemplo também foi utilizado o código da coleção de culturas do Laboratório de Bioprospecção e Genética Molecular de Microrganismos (LGMF).</li>
<li><b>“Note”:</b> neste campo podemos inserir observações que julgamos relevantes sobre questões taxonômicas ou outros tópicos. Neste exemplo foi inserida uma nota indicando que os isolados pertencem ao “<i>Fusarium fujikuroi species complex</i>”, para que esta informação esteja acessível a quem for buscar pela sequência.</li>
</ul>
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_17.png" alt="Planilha Modelo para Source Modifiers no Excel" align="center">
</center>
<br><br>
Após preencher todas as informações e excluir a coluna vermelha, o arquivo deve ser salvo no formato “<i>Texto (separado por tabulações</i>”) e enviado para o GenBank utilizando a opção “<i>Choose file</i>” para upload e “<i>Continue</i>” para prosseguir e realizar a validação. Neste exemplo, o arquivo editado está intitulado como “<b>Aula_10_Source_Modifiers_ITS.txt</b>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_18.png" alt="Campo de upload na aba Source Modifiers no Submission Portal" align="center">
</center>
<br><br>
Se o processamento da tabela tiver ocorrido sem problemas ou erros, será possível prosseguir para a janela da aba de “<i>References</i>”, em que são incluídas informações sobre as referências da publicação e referências da sequência. No campo “<i>Sequence authors</i>” devem ser informados os autores da publicação que foram responsáveis por gerar as sequências (que nem sempre correspondem a todos os autores envolvidos numa publicação, atenção!), clicando na opção “<i>Add another sequence author</i>”. Neste exemplo iremos inserir apenas duas autoras para a sequência:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_19.png" alt="Campo Sequence authors na aba References do Submission Portal" align="center">
</center>
<br><br>
No campo “<i>Reference</i>” iremos incluir informações sobre a publicação, como seu status (“<i>unpublished</i>” para não-publicado, “<i>in-press</i>” para um artigo que esteja no prelo e “<i>published</i>” para artigos publicados). Como em muitos casos ainda não há certeza sobre em qual revista o artigo será submetido, a opção “<i>Unpublished</i>” solicita apenas um título provisório (“<i>Reference title</i>”) e pergunta se os autores são exatamente os mesmos das sequências (“<i>Same as sequence authors</i>”) ou se há autores diferentes (“<i>Specify authors</i>”). Caso o trabalho esteja no prelo ou já esteja publicado, além do título e dos autores também será necessário informar os dados referentes à revista:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_20.png" alt="Campo Reference authors na aba References do Submission Portal para dados publicados" align="center">
</center>
<br><br>
Neste exemplo simularemos um trabalho ainda não publicado e com autores idênticos aos autores da sequência, clicando em “<i>Continue</i>” para prosseguir:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_21.png" alt="Campo Reference authors na aba References do Submission Portal para dados não-publicados" align="center">
</center>
<br><br>
Após o processamento, o sistema redicionará para a última página (“<i>Review & Submit</i>”), para que a submissão seja revisada e finalizada. Neste momento é importante revisar todas as informações fornecidas para evitar erros. Caso algum erro seja detectado, use as abas superiores para retornar às seções anteriores e realizar as correções necessárias. No campo “<i>GenBank Record Preview</i>” podemos visualizar uma prévia do nosso depósito. Se tudo estiver correto, clicamos em “<i>Submit</i>” para finalizar. Neste exemplo não clicaremos para evitar que este depósito de treinamento seja feito, visto que não se trata de um depósito real. 
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_22.png" alt="Campo GenBank Record Preview na aba Review & Submit do Submission Portal" align="center">
</center>
<br><br>
Em geral as sequências enviadas recebem seus códigos em até dois úteis, salvo em casos em que correções sejam necessárias e sejam solicitadas pela equipe do GenBank. Caso nenhum contato seja recebido neste prazo e os códigos não tenham sido liberados, há a possibilidade de entrar em contato com a equipe do GenBank no e-mail 
<b>gb-admin@ncbi.nlm.nih.gov</b> com o código da submissão no título (nesse caso “<i>GenBank Submission SUB8564846</i>”) para solucionar o problema:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_23.png" alt="Opção Submit no Submission Portal" align="center">
</center>
<br><br>
</div>

## Depositando sequências no GenBank via BankIt

<div align="justify">
Caso as sequências não estejam na lista de sequências que podem ser processadas pelo Submission Portal, deveremos fazer uma submissão pelo BankIt, clicando na opção “<i>Sequence data not listed above (through BankIt)</i>” e em “<i>Start</i>” para começar:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_24.png" alt="Opção Sequence data not listed above (through BankIt) no BankIt" align="center">
</center>
<br><br>
Na próxima página clique em “<i>Start BankIt Submission</i>” para começar:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_25.png" alt="Opção Start BankIt Submission no BankIt" align="center">
</center>
<br><br>
De forma similar ao Submission Portal, será necessário preencher as informações de contato na aba “<i>Contact Information</i>”. Neste exemplo usaremos alguns dados do Laboratório de Bioprospecção e Genética Molecular de Microrganismos da UFPR para simulação e clicar em “<i>Continue</i>” para prosseguir:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_26.png" alt="Aba Contact Information no BankIt" align="center">
</center>
<br><br>
Na aba seguinte (“<i>Reference</i>”) devemos inserir informações sobre os autores da sequência e da publicação, da mesma forma que se inserem estas informações no Submission Portal. Neste exemplo iremos inserir duas autoras de sequência, trabalho não publicado (“<i>Unpublished</i>”) e autoras da publicação idênticas às autoras da sequência, clicando em “<i>Continue</i>” para prosseguir:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_27.png" alt="Aba References no BankIt" align="center">
</center>
<br><br>
Na aba seguinte (“<i>Sequencing Technology</i>”) devemos inserir informações sobre o método de sequenciamento e se são sequenciadas montadas a partir de duas ou mais sequências, de forma similar ao Submission Portal. Nesse exemplo selecionaremos “<i>Sanger dideoxy sequencing</i>” e “<i>unassembled sequence reads</i>” e clicar em “<i>Continue</i>” para prosseguir:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_28.png" alt="Aba Sequencing Technology no BankIt" align="center">
</center>
<br><br>
Na aba “<i>Nucleotide</i>” e no campo “<i>Submission Release Date</i>” devemos informar a data de liberação do depósito, seguindo a mesma lógica do Submission Portal. Neste exemplo também utilizaremos a data de 18 de Janeiro de 2024. 
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_29.png" alt="Campo Submission Release Data na Aba Nucleotide no BankIt" align="center">
</center>
<br><br>
Em seguida, no campo “<i>Sequence(s) and Definition Lines(s)</i>” informaremos o tipo de molécula sequenciada (“<i>Molecule Type</i>”, nesse caso “<i>genomic DNA</i>”), a topologia (“<i>Topology</i>”, nesse caso “<i>Linear</i>”), e se é uma sequência completa de genoma completo de alguma organela ou vírus (nesse caso, “<i>no</i>”):
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_30.png" alt="Campo Sequence(s) and Definition Line(s) Data na Aba Nucleotide no BankIt" align="center">
</center>
<br><br>
No campo “<i>Nucleotide Sequence Format</i>” informamos se estamos depositando sequências no formato FASTA (“<i>FASTA sequences (not an alignment)</i>”) ou um alinhamento (“<i>Alignment (FASTA+GAP, NEXUS, PHYLIP, CLUSTAL(W)</i>”). Nesse exemplo selecionaremos a primeira opção: 
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_31.png" alt="Campo Nucleotide Sequence Format na Aba Nucleotide no BankIt" align="center">
</center>
<br><br>
Por fim, no campo “<i>Nucleotide sequences</i>” é possível colar as sequências diretamente no campo em branco, ou fazer o upload do arquivo no campo “<i>Upload file</i>”. Faremos o upload do arquivo “<b>Aula_10_Sequencias_EF.FASTA</b>” e clicaremos em “<i>Continue</i>” para prosseguir:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_32.png" alt="Campo Nucleotide Sequences na Aba Nucleotide no BankIt" align="center">
</center>
<br><br>
Na aba seguinte (“<i>Submission Set/Batch</i>”) o BankIt fornece algumas opções para agrupar sequências (quando duas ou mais sequências estão sendo submetidas):
<br><br>
<ul>
<li><b>Pop set (Population study):</b> as sequências pertencem ao mesmo gene, de diferentes indivíduos de uma mesma espécie</li>
<li><b>Phy set (Phylogenetic study):</b> as sequências pertencem ao mesmo gene, de diferentes indivíduos e de espécies distintas</li>
<li><b>Mut set (Mutation study):</b> as sequências foram obtidas a partir do sequenciamento de diferentes mutações de um mesmo gene</li>
<li><b>Env set (Environmental study):</b> as sequências foram obtidas ao sequenciar o mesmo gene a partir de uma população de organismos não identificados ou desconhecidos (muito comum em estudos de metagenômica)</li>
<li><b>Batch:</b> sequências não relacionadas, que não pertencem ao mesmo gene, mas podem fazer parte de um mesmo estudo ou do mesmo organismo</li>
</ul>
Neste exemplo, como são várias sequências do gene EF de diferentes isolados de <i>Fusarium awaxy</i>, iremos selecionar a opção “<i>Pop set</i>” e clicar em “<i>Continue</i>” para prosseguir:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_33.png" alt="Aba Submission Set/Batch no BankIt" align="center">
</center>
<br><br>
Na página seguinte (“<i>Submission Category</i>”) podemos informar se os dados são originais (“<i>Original</i>”), produzidos pelos autores que estão submetendo), ou se são anotações a partir de sequências que já existem e foram produzidas por outras pessoas (“<i>Third Party Annotation</i>”), como uma anotação e curadoria manual de um genoma publicado, por exemplo. Nesse caso, como são dados originais, selecionamos “<i>Original</i>” e clicamos em “<i>Continue</i>” para prosseguir:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_34.png" alt="Aba Submission Category no BankIt" align="center">
</center>
<br><br>
Na aba seguinte, de “<i>Source Modifiers</i>”, podemos enviar um arquivo de texto separado por tabulações, similar ao Submission Portal. Caso tenha dúvidas em como preparar a tabela, clique aqui. Com a tabela finalizada, selecione a localização celular das sequências em “<i>Organelle/Location</i>” se aplicável (nesse caso deixaremos em branco pois se trata de um gene nuclear), e faça o upload da tabela no campo “<i>Source Modifiers</i>”, selecionando a opção “<i>Upload source modifiers Table File</i>” e clicando em “<i>Continue</i>” para validar a tabela e prosseguir:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_34.png" alt="Aba Source Modifiers no BankIt" align="center">
</center>
<br><br>
Na aba seguinte (“<i>Features</i>”) encontraremos a parte mais “<i>complicada</i>” dos depósitos de sequências que não são processadas a partir do Submission Portal. Aqui, precisaremos fornecer uma anotação básica da sequência, informando dados sobre o gene, presença de regiões codificantes e íntrons, entre outras coisas. De forma similar à aba de <i>Source Modifiers</i>, podemos informar manualmente no navegador, ou realizar o upload de uma tabela de 5 colunas, delimitada por tabulações. No arquivo do Excel intitulado “<b>Aula_10_Modelo_para_Features.xlsx</b>” temos um exemplo e base para montagem desta planilha.
<br><br>
A planilha é dividida de acordo com os genes, e em cinco colunas. Para cada gene:
<br><br>
<ul>
<li><b>Linha 01:</b> informamos o texto <i>">Feature Seq”</i> e o número da sequência correspondente. </li>
<li><b>Linha 02:</b> informamos a posição de início e de fim do gene nas colunas 01 e 02, e o texto “<i>gene</i>” na coluna 03. Caso o gene se inicie antes da sequência devemos adicionar o símbolo de <i>“<”</i> antes do número da coluna 01 e caso o gene continue para além da sequência devemos adicionar o símbolo de <i>“>”</i> depois do número da coluna 02.</li>
<li><b>Linha 03:</b> adicionamos o texto “<i>gene</i>” na coluna 04 e a abreviação do gene na coluna 05 (neste exemplo, “<i>tef1</i>”)</li>
<li><b>Linha 04:</b> adicionamos o texto “<i>note</i>” na coluna 04 e o nome do gene na coluna 05 (neste exemplo, “<i>translation elongation fator 1-alpha</i>”)</li>
<li><b>Linhas 05 até 08:</b> informamos as posições de início e fim das regiões codificantes nas colunas 01 e 02, respectivamente, e o texto “<i>CDS</i>” na coluna 03 da linha 05. Cada CDS deve estar em uma linha. Caso a CDS inicie antes da sequência devemos adicionar o símbolo de <i>“<”</i> antes do número da coluna 01 da linha 05, e caso continue para além da sequência devemos adicionar o símbolo de <i>“>”</i> depois do número da coluna 02 da linha 05.</li>
<li><b>Linha 09:</b> na linha seguinte após as CDS, devemos inserir o texto “<i>product</i>” na coluna 04 e a abreviação do gene na coluna 05 (neste caso, “<i>tef1</i>”)</li>
<li><b>Linha 10:</b> adicionamos o texto “<i>note</i>” na coluna 04 e o nome do gene na coluna 05 (neste exemplo, “<i>translation elongation fator 1-alpha</i>”)</li>
<li><b>Linha 11:</b> adicionamos o texto “<i>codon_start</i>” na coluna 04 e indicamos o início da fase aberta de leitura na coluna 05 (neste caso, 1)</li>
<li><b>Linha 12:</b> adicionamos o texto “<i>transl_table</i>” na coluna 04 e indicamos a tabela de código genético a ser utilizada para a tradução da sequência de nucleotídeos para aminoácidos (nesse caso, utilizaremos a tabela padrão, 1)</li>
<li><b>Linhas 13-18:</b> repetimos o conteúdo das linhas 05-10, substituindo CDS por mRNA.</li>
</ul>
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_35.png" alt="Modelo de Tabela do Excel para Arquivo Features" align="center">
</center>
<br><br>
Mas como descobrir quais são as regiões codificantes em cada uma das sequências? Uma das possibilidades mais simples é utilizando o software “<i>Augustus</i>”, que realiza predição gênica e pode ser utilizado de forma on-line, sem necessidade de instalação e pode ser acessado <a href="http://bioinf.uni-greifswald.de/augustus/submission.php">aqui</a>.
<br><br>
Em sua página podemos colar as sequências no campo em branco ou fazer upload de um arquivo com todas as sequências no formato FASTA. Em seguida, precisamos escolher um organismo modelo para basear as predições. É importante tentar escolher o organismo mais filogeneticamente próximo possível, visto que cada grupo de organismos apresenta particularidades na forma como seus genes são organizados (por exemplo, diferentes tamanhos e quantidades médias de íntrons, diferentes junções de éxons e íntrons, entre outros fatores). Selecionando um organismo próximo, maior a chance de que nosso organismo de interesse e o organismo modelo compartilhem características evolutivamente. Neste exemplo utilizaremos “<i>Fusarium graminearum</i>”, que pertence ao mesmo gênero de “<i>Fusarium awaxy</i>”. Em seguida, selecionamos a opção “<i>both strands</i>” para que o software procure por genes na orientação direta e na orientação reversa, e selecionamos a opção “<i>few</i>” em “<i>Alternative transcripts</i>” para que genes não existentes não sejam criados artificialmente, atrapalhando nossa análise. Por fim, clicamos em “<i>Run AUGUSTUS</i>” na página seguinte:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_36.png" alt="Opções para submissão de sequência no Augustus" align="center">
</center>
<br><br>
O Augustus irá redirecionar para a página de resultados, informando os genes preditos para cada sequência, com as respectivas posições de exons e íntrons. Observe que os valores para a linha “<i>transcript</i>” e para as linhas “<i>CDS</i>” são os mesmos presentes no arquivo Excel, e que devem ser buscados para todas as sequências a serem depositadas, e inseridos na tabela:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_37.png" alt="Janela de Resultado do Augustus" align="center">
</center>
<br><br>
Após finalizar as buscas no Augustus e preenchimento da tabela, devemos exportar o arquivo no formato “<i>Texto (separado por tabulações”</i>) e fazer o upload na aba “<i>Features</i>” do BankIt, selecionando a opção “<i>Add features by uploading five column feature table file</i>” e clicando em “<i>Continue</i>” para processar e validar a tabela. Neste exemplo utilizaremos o arquivo “<b>Aula_10_Features_EF.txt</b>”:
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_38.png" alt="Aba Features no BankIt" align="center">
</center>
<br><br>
Por fim, se a validação tiver ocorrido corretamente, na aba “<i>Review and Correct</i>” será possível revisar os detalhes da submissão e finalizar o envio. No campo “<i>Additional Email Addresses</i>” é possível informar e-mails adicionais para contato por parte do GenBank. Também é possível realizar o download dos arquivos para manter um backup. Caso todos os detalhes estejam corretos, basta então finalizar a submissão clicando em “<i>Finish Submission</i>”. Visto que esta é apenas uma simulação, não iremos utilizar esta opção.
<br><br>
<center>
<img src="https://raw.githubusercontent.com/desirrepetters/cursodefilogenia.ufpr/master/userguide/content/pt-br/docs/praticas/img/aula_10/aula_10_39.png" alt="Aba Review Submission no BankIt" align="center">
</center>
<br><br>
De forma similar ao Submission Portal, em geral as sequências enviadas recebem seus códigos em até dois úteis, salvo em casos em que correções sejam necessárias e sejam solicitadas pela equipe do GenBank. Caso nenhum contato seja recebido neste prazo e os códigos não tenham sido liberados, também há a possibilidade de entrar em contato com a equipe do GenBank no e-mail 
<b>gb-admin@ncbi.nlm.nih.gov</b> com o código da submissão no título para solucionar o problema.

</div>

## Aula em vídeo

<br>
<div align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/-4OuspI8tI8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe> 
<br><br>
Clique <a href="https://photos.app.goo.gl/opTEPt2UNS8hUzD97">aqui</a> para fazer o download do vídeo.
<br><br>
</div>
