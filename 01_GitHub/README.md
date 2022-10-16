<h1 align="center"> Git e GitHub </h1>
Primeiramente gostaria de agradecer ao <b>Willian Justen</b> e ao <b>Professor Gustavo Guanabara</b> por terem disponibilizado no youtube videaulas super didáticas para que pessoas assim como eu consigam se desenvolver nessa jornada. Os linkds para os cursos são respecitvamente:


<ol type="i">
<li><a href="https://www.youtube.com/watch?v=IBClN6VpJDw&list=PLlAbYrWSYTiPA2iEiQ2PF_A9j__C4hi0A">Git e GitHub para iniciantes - Willian Justen</a>
<li><a href="https://www.cursoemvideo.com/curso/curso-de-git-e-github/">Curso de Git e GitHub - Gustavo Guanabara</a>
</ol>
<br>


<h2 align="left"><b>Introdução</b></h2>
<b>O que é o controle de versão?</b>

É muito comum quando estamos escrevendo um trabalho muito longo, como uma dissertação de mestrado, ou um projeto extenso criarmos cópias e mais cópias de arquivos só pra poder guardar diferentes versões desse trabalho com pequenas modificações só para podermos guardar pequenas ideias na hipótese de querermos voltar com alguma dessas ideias ou desfazermos alguma modificação caso o cliente decida voltar para a ideia anterior. Isso gera um grande problema de organização e consumo de HD desnecessariamente. Outra aplicação para o controle de versão é conseguirmos recuperar alguma etapa importante do nosso projeto que foi acidentalmente apagada.

O controle de versão é um sistema que tem por finalidade gerenciar as diferentes versões de um documento. É responsável por pegar as diferentes modificações ocorridas no projeto e criar versões desses documentos facilitando com que consiga avançar ou voltar versões sem grandes dificuldades.

O Git é um dos sistemas disponíveis no mercado que realizam essa tarefa de gerenciar as versões de documentos.

<h2 align="left"><b>Configuração</b></h2>

A configuração do git para que as informações possam passar para todos os repositórios do usuário, é feito o config do global. Para tanto, insere-se na linha de comando do terminal:

Configurando o nome:<br>
<font color=#0000FF><i>git config --global user.name "Seu Nome"</i></font>

Configurando o email:<br>
<font color=#0000FF><i>git config --global user.email "seuemail@email.com.br"</i></font>

É possível também configurar o editor principal do git, caso seja necessário digitar alguma mensagem como em um commit.

Configurando o edtiro de texto principal: <br>
<font color=#0000FF><i>git config --global core.editor "comando do editor sem as aspas"</i></font>

Para saber as informações contidas nas configurações do git basta digitar na linha de comando:<br>
<font color=#0000FF><i>git config --list</i></font>

Caso queira saber apenas um parâmetro especifico, digita-se: <br>
<font color=#0000FF><i>git config --"parâmetros sem as aspas"</i></font>

<h2 align="left"><b>Criação de Pastas/Movimentação de caminho pelo Terminal</b></h2>

Para alterar-se a pasta de trabalho através do terminal, usa-se o comando <i>cd</i> seguido do caminho até o qual deseja ir. Por exemplo, ao digitar o comando <i>cd</i> no terminal, o terminal será direcionado para o diretório raiz do usuário a partir do qual é possível entrar nos diferentes discos físicos ou virtuais existentes na máquina.

A partir da raiz é possível ir caminhando diretório por diretório até chegar ao local onde o usuário deseja salvar os arquivos do projeto. No meu caso, criei um diretório no disco da nuvem no Drive e o comando para chegar até ele ficou o seguinte:

<font color=#0000FF><i>cd g:/Meu\ Drive/GitHub/Estudos</i></font>

Perceba que iniciei com o comando <i>cd</i> seguido da letra que nomeia o meu disco na nuvem dentro do meu sistema seguido de ":"  e "/". Nesse momento eu acesso através do terminal meu disco g. Caso não saiba qual o nome do diretório que deseja ir em seguida, é possível usar o comando <i>dir</i> para se descobrir quais as pastas disponíveis dentro do diretório atual.

Em seguida escrevi o nome do diretório para o qual desejo ir em seguida. Nesse ponto, perceba que os diretórios são separados pela símbolo "/". Assim, "Meu\ Drive" é um único diretório a barra invertida é necessária para sinalizar espaço no nome das pastas.

Por questão de organização decidir criar um diretório geral para todos os meus projetos salvos no git, e para este projeto de registro de estudos em específico criei um diretório para servir de repositório do projeto.

A criação de diretórios é feito através do comando <i>mkdir</i>, dentro do diretório que se deseja criar uma nova pasta escreva o comando seguido do nome do diretório:<br>

<font color=#0000FF><i>mkdir GitHub</i></font>

Em seguida para acessar o diretório GitHub que acabei de criar, uso o comando <i>cd</i> novamente com o nome da pasta seguido de "/":

<font color=#0000FF><i>cd GitHub/</i></font>

É possíve ir criando diretórios dentro de diretórios seguindo o mesmo passo a passo.

Para retornar uma pasta utiliza-se o comando <i>cd ..</i>, então caso esteja no diretório /g/Meu\ Drive/GitHub/Estudos e queiramos retornar para o diretório GitHub, na linha de comando do terminal digita-se

<font color=#0000FF><i>cd ..</i></font>

E o resultado no caminho do diretório será: <font color=#0000FF><i>/g/Meu\ Drive/GitHub</i></font>

<h2 align="left"><b>Inicializando um repositório local</b></h2>

Para iniciar um repositório e tê-lo como parte do ecosistema do git na máquina, utiliza se o seguinte comando:

<font color=#0000FF><i>git init</i></font>

Esse comando é responsáve por inicilizar o repositório e ficar monitorando todas as mudanças que ocorrerem no projeto. O resultado desse comando é a inicialização de um repositório na pasta selecionada com um diretório chamado <i>.git</i> no qual está inserido algumas pastas responsáveis por guardar a configuração do repositório, qual o branch padrão e os branch existentes, e outras informações do projeto no git.

<h2 align="left"><b>Ciclo de Vida dos Status dos Arquivos</b></h2>

O git separa de maneira em definidos os arquivos do projeto em 4 status:

<ol>
<li><i>untracked</i> - é o momento em que o arquivo acabou de ser adicionado ao repositório, mas ainda não foi visto pelo git. Ou seja, o git ainda não reconhece em nenhuma versão do seu projeto a existência desse arquivo.
<li><i>unmodified</i> - Após a inserção desse novo arquivo no git ele passa a ser considerado como unmodified. Agora o git reconhece ele como um arquivo presente na versão que ele foi adicionado, porém ainda sem modificações.
<li><i>modified</i> - Se houver uma edição desse arquivo após o reconhecimento dele pelo git, ele passa a ser considerado como um arquivo modified.
<li><i>staged</i> - Depois de modificado esse arqvui pode ser jogado para uma área em que será criada a versão (Staged), que é o momento em que o arquivo fica em stanby aguardando a finalização da versão. Nessa área é como se o git estivesse sendo avisado para que no momento em que a versão for fechada os arquivos com modificação devem ser levados para nova versão. Após o fechamento da versão e realizar o commit, todos esses arquivos em staged voltam a ser unmodified para esta nova versão.
</ol>

<h2 align="left"><b>Comandos Git</b></h2>

<font color=#0000FF><i>git status</i></font><br>

Serve para reportar como está o repositório.

<font color=#0000FF><i>git add "nome do arquivo sem as aspas"</i></font><br>

Adiciona ao git o arquivo especifico para serem comitados e posteriormente adicionados a branch. Caso seja um novo arquivo, ainda não reconhecido pelo git, antes do <i>git add</i> ele estará no estado <u>untracked</u>, após o comando ele passará a ser reconhecido pelo git e estará no estado <u>staged</u>, ou seja preparado para ser comitado e ir para a versão final. Se for um arquivo já existente, antes do comando ele poderá estar no estado <u>unmodified</u> ou <u>modified</u>, dependendo se sofreu edição ou não, e após o comando também passará para o estado <u>staged</u>.

<font color=#0000FF><i>git add .</i></font><br>

Faz o mesmo que o comando <i>git add "nome do arquivo"</i> porém com todos os arquivos modificados dentro daquele diretório, mesmo que o arquivo modificado esteja dentro de subdiretório daquela pasta.

<b>obs:</b> Se após o <i>git add</i> houver outra modificação no arquivo ele sairá do estado <u>staged</u> e passará para o estado <u>modified</u> e para que ele seja novamente adicionado a nova versão a ser comitada é preciso realizar o comando <i>git add</i>

<font color=#0000FF><i>git commit -m "Digite seu comentário dentro das aspas"</i></font><br>

O comando <i>git commit</i> é o momento em que é sinalizado para o git pegar todos os arquivos do repositório e criar uma nova versão dele. O parâmetro <u>-m "Mensagem"</u> serve para sinalizar que um comentário será adicionado a esse commit, utilizado para explicar as alterações e observações importantes sobre a versão que está sendo comitada.

<b>obs.:</b> Quando um commit é realizado o git cria uma numeração que chamamos de <i>hash</i> que é a identificação da versão que foi criada. A esta <i>hash</i> está associado um log que é o comentário que foi colocado através do parâmetro <u>-m</u>.

<font color=#0000FF><i>git log</i></font><br>

Permite visualizar o histórico de versões com todos dos commit apresentado a <i>hash</i> do commit, o autor da modificação e a data da modificação e a mensagem do commit. Para sair do comando pressione a tecla "q".

É possível adicionar alguns parâmetros ao <i>git log</i>:

<font color=#0000FF><i>-- decorate</i></font> - que apresenta informações como se o arquivo foi transferido de uma branch para outra, se ocorreu um merge, tags geradas etc.

<font color=#0000FF><i>-- author="nome"</i></font> - filtra todos os commits de um autor que tenha a palavra "nome" no nome do Autor.

<font color=#0000FF><i>git shortlog</i></font><br> - Mostra em ordem alfabética a lista dos autores que fizeram commits, quantos commits foram realizados e quais foram esses commits.

<font color=#0000FF><i>-sn</i></font> - é um parâmetros que pode ser adicionado ao <i>git shortlog</i> que traz um resumo do nome de todos os autores que realizaram commit e a quantidade de cada commit por autor.

<font color=#0000FF><i>-- graph</i></font> - Mostra em forma gráfica o que esta acontecendo com os branchs e versões.

<font color=#0000FF><i>git show "número da hash sem as aspas"</i></font> - mostra o que aconteceu com o commit, o que foi adicionado, o que foi removido.

<font color=#0000FF><i>git diff</i></font><br>

Mostra as mudanças antes de ser feito o commit. Pressione a tecla "q" para sair do comando. Também é possível adicionar parâmetros ao comando.

<font color=#0000FF><i>--name-only</i></font> - mostra apenas o nome dos arquivos que tiveram modificações.



