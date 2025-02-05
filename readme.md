
## Resumo de comandos GIT e GITHUB


**UBUNTU - Configuração do GIT**

**Acesso total de adm:**
'sudo add-apt-repository ppa:git-core/ppa'

**Atualizar os pacotes:**
'sudo apt update'

**instalação do git:**
'sudo apt install git'

**verificar versão:**
'git --version'

**Referência: https://git-scm.com/book/pt-br/v2/Come%C3%A7ando-Instalando-o-Git*

=================================================

**GIT BASH**

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
==================================================

**Criar Repositório**

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

=======================================================

**Desfazendo Alterações no Repositório local**
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

'''
git log</br>
git reset --soft PEGAR O HASH DO ÚLTIMO COMMIT NO GIT LOG</br>
'''

**Opção02. Outra maneira de retornar com commit anterior*</br>
'''
git log</br>
git reset --hard PEGAR O HASH DO ÚLTIMO COMMIT NO GIT LOG</br>
'''
**O hard ignora o commit anterior e apaga os arquivos.*

**Opção03. Apagar o arquivo.*</br>
'''
git log</br>
git reset PASSAR O NOME DO ARQUIVO</br>
git reset resumos/aula01.md</br>
git status</br>
'''

**Opção04. Apagar o arquivo.*</br>
'''
'git log'</br>
'git reset --staged PASSAR O NOME DO ARQUIVO'</br>
'git reset --staged resumos/aula01.md'</br>
'git status'</br>
'''
</br></br>
**Histórico mais detalhado:**
git reflog

=======================================================

***TRABALHANDO COM BRANCHES - CRIANDO, MESCLANDO, DELETANDO E TRATANDO CONFLITOS***

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

=======================================================

**Para verificar as alterações da branch main:**
'git fecth origin main'

**Para verificar as diferenças das branchs:**
'git diff'

**Para verificar as diferenças das branchs do remoto e da local:**
'git merge origin/main'
 
**Para clonar um repositório, que tenha várias branchs, mas apenas uma 
uma branch será clonada:**
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

