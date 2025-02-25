
## Resumo de comandos GIT e GITHUB  :computer:

:pushpin:**UBUNTU - Configuração do GIT**

**Acesso total de adm:**
'sudo add-apt-repository ppa:git-core/ppa'

**Atualizar os pacotes:**
'sudo apt update'

**instalação do git:**
'sudo apt install git'

**verificar versão:**
'git --version'

**Referência: https://git-scm.com/book/pt-br/v2/Come%C3%A7ando-Instalando-o-Git*

=================================================================================================================

:pushpin:**GIT BASH**

**Para nomear o git:**
'git config --global user.name "Alegria"'

**Para cadastrar email:**
'git config --global user.email alegria@hotmail.com'

**Verificar o nome configurado:**
'git config user.nome'

**Verificar email configurado:**
'git config user.email'

**Verificar a branch configurada:**
'git config init.defaultBranch'

**Configurar a branch:**
'git config --global init.defaultBranch main'

**Exibe a configuração:**
'git config --global --list'

**Referência: https://git-scm.com/docs/git-init*

=============================================================================================================

:pushpin:**Criar Repositório**

**Criar pasta:**
'mkdir dio-resumos-git-e-github'

**Entrar na pasta:**
'cd dio-resumos-git-e-github'

**Iniciar o repositório git:**
'git init'

**Verificar a área de preparação do repositório:**
'git status'

**Criar um arquivo vazio:**
'touch README.md'

https://readme.so/pt*
</br></br>

![image](https://github.com/user-attachments/assets/78538653-d6b2-458a-ac62-c77db5d71933)
</br> ![image](https://github.com/user-attachments/assets/8d565e28-e62e-4690-83c1-2b7ed7bb7ce6)
</br>
Copiar e colar as alterações no bloco de nota dentro do readme e salvar. 
</br></br>

**Adicionar o arquivo no ambiente de preparção:**
'git add README.md'

**Verificar a área de preparação do repositório:**
'git status'

**Preparar o commit:**
'git commit -m"commit inicial"'

**Verificar o(s) commit(s):**
'git log'

**Criar um arquivo vazio dentro de uma pasta:**
'touch resumos/resumo-aula1.md'

**Arquivos que o gitignore deve ignorar no commit:** 
'echo resumo/ > .gitignore'

**Retirar arquivos do gitignore:**
'echo > .gitignore'

**Para que o gitignore reconheça um arquivo vazio:**
'touch aulas/.gitkeep'

**Para adicionar os arquivos ignorados no commit:**
'git add.'

**Subir a alteração do commit:**
'git commit -m"colocar o resumo da alteração"'

Exemplo

git commit -m"adicionar arquivo git ignore e diretórios de aula e resumos"

 
**Caso o tenha uma alteração do README.md LOCAL (online) e atualizar no remoto**
Após as alterações do readme serem efetuadas localmente, usar o comando 'git pull'. 

========================================================================================================

:pushpin:**Desfazendo Alterações no Repositório local**
Para alterar o nome e o versionamento da pasta

**Iniciar o repositório git:**
'git init'

**Remover a força todo repositório git:**
'rm -rf .git'

**Verificar a área de preparação do repositório:**
'git status'

###Restauração do repositório git

**Verificar a área de preparação do repositório:**
'git status'

**Para voltar ao estado anterior do repositório:**
'git restore README.md'

**Alterar a mensagem do último commit:**
'git commit --amend -m"mensagem de alteração"'

Exemplo:

'git commit --amend -m"adicionar gitignore e diretórios aulas e resumos"'

**Opção01. Outra maneira de retornar com commit anterior:*</br>

'''</br>
git log</br>
git reset --soft PEGAR O HASH DO ÚLTIMO COMMIT NO GIT LOG</br>
'''
</br>
:paperclip:**Opção02. Outra maneira de retornar com commit anterior*</br>
'''</br>
git log</br>
git reset --hard PEGAR O HASH DO ÚLTIMO COMMIT NO GIT LOG</br>
'''
</br>
**O hard ignora o commit anterior e apaga os arquivos.*
</br>
:paperclip:**Opção03. Apagar o arquivo.*</br>
'''</br>
git log</br>
git reset PASSAR O NOME DO ARQUIVO</br>
git reset resumos/aula01.md</br>
git status</br>
'''
</br>
:paperclip:**Opção04. Apagar o arquivo.*</br>
'''</br>
'git log'</br>
'git reset --staged PASSAR O NOME DO ARQUIVO'</br>
'git reset --staged resumos/aula01.md'</br>
'git status'</br>
'''
</br></br>
:ledger:**Histórico mais detalhado:**
git reflog

===============================================================================================================

:pushpin:***TRABALHANDO COM BRANCHES - CRIANDO, MESCLANDO, DELETANDO E TRATANDO CONFLITOS***

Branch(tradução:ramo) : é uma ramificação do projeto</br>
*é um ponteiro móvel para um commit no histórico do repositório;</br>
*quando uma nova branch é criada a partir de outra existente, anova se inicia
apontando para o mesmo commit da branch que estava quando foi criada.

**Verificar o(s) commit(s):**
'git log'

**Criar um novo arquivo:**
'echo "#commit-1-branch-main" > commit-1-branch-main.txt'

**Para adicionar os arquivos no commit:**
'git add.'

**Preparar o commit:**
'git commit -m"commit l"'


**Criar uma nova Branch**
'git checkout -b teste'

**Verificar o(s) commit(s), estará no mesmo commit:**
'git log'

**Criar um novo arquivo:**
'echo "#commit-2-branch-main" > commit-2-branch-main.txt'

**Para adicionar os arquivos no commit:**
'git add.'

**Verificar a última branch:**
'git branch -v'

**Verificar os commits das branch é preciso mesclar elas:**
'git merge teste'

**Deletar uma branch:**
'git branch -d teste'

=====================================================================================================

:small_red_triangle_down:</br>
**Para verificar as alterações da branch main:**
'git fecth origin main'

**Para verificar as diferenças das branchs:**
'git diff'

**Para verificar as diferenças das branchs do remoto e da local:**
'git merge origin/main'
 
**Para clonar um repositório, que tenha várias branchs, mas apenas uma branch será clonada:**
git clone https://github.com/elidiana/repo-remoto.git --branch teste --single-b

**Para caso de algum arquivo for deletado:**
'''
git status</br>
git stash
'''
</br>
**Listar as modificações arquivadas:**
'git stash list'

**Criar uma nova branch:**
'git checkout -b teste-2'

**Para retornar para branch principal:**
'git checkout teste'

**Para exibir as alterações mais recentes e excluir a última alteração da pilha:**
'git stash pop'

**Para manter a alteração da list e utilizar depois:**
'git stash apply'

============================================================================================

:pushpin::notebook_with_decorative_cover:**Resumo geral dos comandos mais utilizados**
</br></br>
:black_square_button: git status: verifica quais arquivos foram modificados.</br>
:black_square_button: git add: adiciona as mudanças.</br>
:black_square_button: git commit: registra as mudanças no repositório.</br>
:black_square_button: git clone: realiza automaticamente essa conexão entre o repositório remoto e o repositório local.</br>
:red_circle: Caso quiser alterar o nome  do arquivo: git clone https://github.com/rodrigoalura87/numero-secreto.git repo-clonado, por exemplo.</br>
:black_square_button: git remote add: adicionar no repositório local um link com o repositório remoto.</br>
:black_square_button: git push: passar o git push e em sequência precisamos informar para onde enviaremos o commit. Escrevemos origin que é o apelido do repositório remoto, seguido de main que é a branch. git push origin main.

