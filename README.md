# Aprendendo Git

## Criando um novo repositório

- Para se criar um novo repositório no GitHub vamos clicar no “+” e clicar em “New repository”, ou também podemos acessar a url “repo.new”.
- Agora é preciso digitar as informações do repositório desejadas. O nome do repositório, a descrição, se vai ser publico ou privado, se vai ter README ou não.
- Para o exemplo desse repositório será colocado como nome do repositório “aprendendo-git”, ficará sem descrição, será publico e sem o README.
- Para criar um novo arquivo clicaremos na opção “creating a new file”.
- Criaremos um arquivo com o nome de README.md, que será nosso arquivo README.
    - README é o arquivo que terá as informações do projeto.
- E para salvar esse arquivo README após ter editado ele clicar no botão “commit new file”.
    - Commit seria um rótulo do estado do nosso projeto naquela momento
 
 ## Editando arquivos
- Além de criar também podemos editar os arquivos, para isso basta clicar no lápis que fica no arquivo.
- Porém esse método de editar arquivo não é muito bom, pois esse editor do github não é muito bom. Podemos utilizar o VScode dentro do github, o que acaba sendo uma forma melhor de editar os arquivos. Para isso basta clicar na tecla ponto que abrirá uma ferrando do VScode no navegador para editar os arquivos do repositório.
- Nesse editor iremos criar um arquivo “app.py” com um print para exibir uma mensagem na tela.
```
print("Aprendendo github")
```
- Porém ainda precisamos dar o commit das alterações feita, para isso podemos ver na esquerda em “controle do código-fonte” os arquivos que foram alterados. Para dar o commit basta escrever o título do commit e clicar no check.

## Adicionando um colaborador
- Para adicionar um colaborador, alguém que poderá editar os códigos é preciso ir nas configurações do repositório.
- Agora em “collkaborators” clicar em “Add people” e adicionar a pessoa desejada.
    - Agora essa pessoa adicionada pode commitar, editar arquivos.
    
## Git
- Agora usaremos o git, que é a mesmas coisas que fizemos pelo github só que por linha de comando.
- Primeiro iremos clonar o repositório. Para isso temos que ter o git instalado na nossa máquina. Acessar: [https://git-scm.com/book/en/v2/Getting-Started-Installing-Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
- Após a instalação, no repositório do github clicar em code e depois copiar o link para clonar o repositório.
- Agora para clonar basta ir para o diretório que você deseja clonar o repositório e digitar o comando “git clone URL_repositório_github”.
    - Exemplo: Clonar para o diretório Documents.
        ```bash
        cd Documents
        git clone https://github.com/guilherme-nagal/aprendendo-git.git
        ```
- Agora que clonamos o repositório podemos altera-lo localmente na nossa máquina.
- Podemos verificar o histórico de todos os commits com o seguinte comando:
    ```bash
    git log
    ```
- Ou podemos pegar de uma forma mais resumida com o seguinte comand
    ```bash
    git log --oneline
    ```
    
## Commit
- Para atualizar o repositório da maquina local teremos que usar o comando pull:
    ```bash
    git pull https://github.com/guilherme-nagal/aprendendo-git.git
    ```   
- Agora alterando, localmente, o arquivo app.py para:   
    ```python
    print("Aprendendo github, alteração")
    ```    
- Para verificar quais foram as alterações podemos digitar o seguinte comando.    
    ```bash
    git status
    ```    
- Agora para commitar esse arquivo vamos digitar:    
    ```bash
    git commit app.py -m "Alterando o arquivo app.py"
    ```    
    - Caso essa seja a primeira vez commitando um arquivo aparecerá para adicionar nas configurações seu username e seu nome. Para isso basta digitar    
    ```bash
    git config --global user.email "you@example.com"
    git config --global user.name "Your Name"
    ```    
- Agora vamos upar esse commit no github, para isso vamos utilizar o seguinte comando:   
    ```bash
    git push origin main
    ```
    - Enviando do nosso repositório local para o main, do github.
    - Alterando já no repositório do github.
- Outra sequência de comandos para fazer o push é:   
    ```bash
    git add .
    git commit -m "Comentário"
    git push origin main
    ```
    
## Retoamdno para uma versão antiga
- Podemos ver o histórico de commits no github clicando no ícone de histórioco.
    - Ou como visto anteriormente podemos digitar o comando `git log`.
- Para voltar para uma versão anterior do repositório devemos pegar o código da versão desejada e digitar o comando:
    ```bash
    git restore --source código_da_versão .
    ```
- Agora temos que dar o commit:
    ```bash
    git commit . -m "voltando a vesão"
    git push
    ```

## Branch
- Branch são ramificações para separa alguns códigos, como por exemplo o código que está em desenvolvimento e o que está sendo rodado.
- Para criar uma branch de desenvolvimento devemos utilizar o seguinte código:
    ```bash
    git checkout -b desenvolvimento
    ```
    - Dessa forma criamos a branch de desenvolvimento e já estamos nela.
- Caso queira voltar para a branch main digitar o seguinte código:
    ```bash
    git switch main
    ```
- Na branch de desenvolvimento podemos alterar o código sem alterar na branch main. Como exemplo vamos alterar o arquivo app.py
    ```bash
    print("Desenvolvimento")
    ```
- Agora faremos o push com essa branch.
    ```bash
    git add .
    git commit -m "Desenvolvimento"
    git push origin desenvolvimento
    ```
- Se compararmos a duas branch no github podemos ver que elas são diferentes.
    - Para alterar a branch deve-se clicar aqui:
- Após termos feitas todas as validações da branch de desenvolvimento teremos que mandar para main, para isso teremos que fazer um merge no principal.
- Primeiro veremos as branchs e a branch em que estamos:
    ```bash
    git branch
    ```
- Então voltaremos para a branch principal.
    ```bash
    git swith main
    ```
- Agora vamos ver o histórico de commits e pegar o código do último commit.
    ```bash
    git log --oneline
    ```
- Para dar o merge deve-se digitar o seguinte comando:
    ```bash
    git merge desenvolvimento
    ```
- Se visualizarmos novamente o histórico é possível ver que o último push recebeu um id que juntará a branch de desenvolvimento com a main.
- Por último basta dar um push.
    ```bash
    git push origin main
    ```

> Status do projeto: Em desenvolvimento
