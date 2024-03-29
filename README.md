# Git
Comandos Git

`git config --local user.name "Seu nome aqui"`
- para criar o usuario que irá mexer no código, apenas localmente no msm repositorio 
-----------------------------------------------------------------------------------------------------------------------------------------------
`git config --local user.email "seu@email.aqui"` 
- Para criar o email de quem irá mexer no código, apenas localmente no msm repositorio
-----------------------------------------------------------------------------------------------------------------------------------------------

`git config --global user.name "Seu nome aqui"`  
- Para criar o usuario de quem irá mexer no código, em todos os repositorios
-----------------------------------------------------------------------------------------------------------------------------------------------

`git config --global user.email "Seu email aqui"`
- Para criar o email de quem irá mexer no código, em todos os repositorios
-----------------------------------------------------------------------------------------------------------------------------------------------

`git status`
- Verifica quais os estados que os arquivos estão
-----------------------------------------------------------------------------------------------------------------------------------------------

`git add "nome do seu arquivo"` 
- adiciona um arquivo
-----------------------------------------------------------------------------------------------------------------------------------------------

`git add .`
- Adiciona todos os arquivos de uma vez
-----------------------------------------------------------------------------------------------------------------------------------------------

`git commit -m "uma mensagem"` 
- para fzer um commit e deixar uma mensagem
-----------------------------------------------------------------------------------------------------------------------------------------------
`git log`
- Mostra o historico das modificações, pressione q para sair do git log
-----------------------------------------------------------------------------------------------------------------------------------------------

`git log --oneline`
- Para mostrar todos os commits resumidamente em apenas uma linha
-----------------------------------------------------------------------------------------------------------------------------------------------

`git log -p` 
- Para mostrar todas as alterações detalhadamente
-----------------------------------------------------------------------------------------------------------------------------------------------

`git log --pretty="%H %s`
- Para mostrar a hash e a mensagem do commit
-----------------------------------------------------------------------------------------------------------------------------------------------
Observação:

- para que o git não monitore alguma pasta ou arquivo, você deve criar um arquivo chamado ".gitignore", e dentro do .gitignore adicionar o nome dos arquivos ou pastas que vc não quer que o git monitore.

Por exemplo:

`*.sqlite3` ou por exemplo `*.py`
- Para ignorar por extensão utilize apenas um * antes da extensão

`**__pycache__`
- Para ignorar um diretório utilize dois ** antes do nome do diretório
								
-----------------------------------------------------------------------------------------------------------------------------------------------

## Compartilhando trabalho - Repositórios Remotos

1-) cd.. (para voltar para pasta GitHub)

2-) criar um diretório dentro da pasta GitHub com o comando, `mkdir "servidor"`

3-) entrar dentro da pasta criada, `cd servidor/`

4-) agora dentro da pasta criada basta executar o camando, `git init --bare` 
- Para informar que, nessa pasta que você está, irá receber apenas as alterações do código. vc irá receber uma mensagem que inicializou um repositório vazio no caminho C:/Users/renan/Documents/GitHub/servidor/

5-) agora temos que entrar na pasta Renan onde estão os codigos para serem enviados para o repositorio "nome da pasta" cd ../Renan/

6-) agora vamos adicionar o endereço, `git remote add local C:/Users/renan/Documents/GitHub/servidor/`  
- podemos dar um nome pro nosso repositorio que se chamará de "local" acompanhado do endereço do repositório

7-) `git remote`
- este comando retornará o nome do endereço do repositório o nome é "local" 

8-) `git remote -v`
- Mostra o caminho

9-) `cd ..` para voltar para pasta GitHub, e criar uma pasta chamada "ana" que também vai fazer parte do projeto, para criar a pasta: `mkdir ana`

10-) `cd ana`
- para entrar na pasta ana

11-) Agora a ana irá baixar para ela do nosso repositório, todo o conteúdo ja feito ate agora no nosso projeto, com o seguinte comando: `git clone  C:/Users/renan/Documents/GitHub/servidor/`
- ela irá baixar tudo que tem nessa pasta servidor Porém quando ela baixar, o repositório estará vazio. por que na pasta Renan, ainda não subiu pro Repositório o projeto. 

-----------------------------------------------------------------------------------------------------------------------------------------------

`git init --bare` 
- Para informar que nessa pasta que vc está, irá receber apenas as alterações do código
-----------------------------------------------------------------------------------------------------------------------------------------------

`git remote add local C:/Users/renan/Documents/GitHub/servidor/` 
- para adicionar um servidor chamado no caso desse exemplo de "local"
-----------------------------------------------------------------------------------------------------------------------------------------------

`git remote`  
- para listar os servidores que tem
-----------------------------------------------------------------------------------------------------------------------------------------------

`git remote -v`  
- Mostra o caminho
-----------------------------------------------------------------------------------------------------------------------------------------------

`git clone C:/Users/renan/Documents/GitHub/servidor/projeto` 
- para baixar algum dado do repositório servidor
-----------------------------------------------------------------------------------------------------------------------------------------------

`git push local master`
- git push para enviar, local para indicar que será no repositorio chamado servidor, e master que é a branch que estamos
-----------------------------------------------------------------------------------------------------------------------------------------------

`git pull local master` 
- git pull para pegar, este comando irá pegar no repositorio a nova atualização do projeto
-----------------------------------------------------------------------------------------------------------------------------------------------

`git remote rename origin local`
- Para renomear
1-) O nome atual do seu controle remoto (origin)
2-) O nome para o qual você deseja alterar o controle remoto (local)

-----------------------------------------------------------------------------------------------------------------------------------------------

## Para Subir um código pro GitHub:

1-) ir até seu GitHub e criar um repositorio e pegar o caminho dele que esta em "CODE"

2-) ir até o terminal e colocar o seguinte comando Passando o nome do repositório: `git remote add origin https://github.com/iRnx/Django.git`

3-) Depois basta enviar na branch que você quer, que nesse caso será a branch master: `git push origin master`

Observação:

- Caso queira excluir uma pasta remota: `git remote remove origin`

Prontoooo !!! 

-----------------------------------------------------------------------------------------------------------------------------------------------

## Usar branch:

1-) criar uma nova branch, `git branch titulo`, uma forma rápida tbm de criar branch: `git checkout -b titulo`, você criaria a branch titulo e ja estaria nela

2-) `git branch`
- para ver em qual branch você está

3-) `git checkout titulo`
- para você mudar de branch

-----------------------------------------------------------------------------------------------------------------------------------------------

## para usar o merge:

1-) O merge junta uma branch: `git merge titulo`
- este comando iria juntar a branch titulo na sua branch master. Porém para juntar, atualmente vc tem q estar na branch master por exemplo e dps fazer o merge

-----------------------------------------------------------------------------------------------------------------------------------------------

## Rebase:

1-) `git rebase titulo` 
- Serve para atualizar a master com outra branch, por exemplo: todas as atualizações que estiver na branch titulo, nós queremos trazer para a branch master. então basta estar na branch master e fazer um rebase 

-----------------------------------------------------------------------------------------------------------------------------------------------

Resolvendo conflitos:

branch renan:
`git pull origin master --rebase`


branch master:
`git merge renan`
`git push origin master`


branch renan:
`git pull origin renan --rebase`
`git push origin renan`



