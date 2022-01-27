# COMANDOS: GIT

### Inicializar um repositório: ```git init``` 



### Exibe o estado do repositório: ```git status```. 

- Esse comando exibe algumas informações sobre a *branch* em que você se encontra, como seu nome, se ela está atualizada em relação à master e quais arquivos foram alterados.



### Salvar alterações: ```git add```

- Quando criamos, modificamos ou excluímos um arquivo, essas alterações ocorrerão em nosso ambiente local e não serão incluídas no próximo *commit* (a menos que alteremos as configurações).



### "Checkpoint": ```git commit -m "mensagem curta (geralmente só uma frase)"```

- Para mostrar para o Git que houve uma alteração em seu código precisamos avisar, para fazer isso é necessário escrever uma mensagem, que chamamos de _commit_ (Criamos este "checkpoint" somente depois de adicionarmos as alterações no código).



### Histórico de alterações: ```git log```

- Esse comando apresenta todas as alterações realizadas na branch, além disso, ele exibirá algumas informações como:
  - O Hash do commit; O Hash é um código identificador único de cada commit, ou seja, não existem commits com  o mesmo Hash o que permitem algumas manipulações;
  - A Branch em que o commit se encontra;
  - O autor do commit;
  - A data da realização do commit;
  - E  a mensagem.



### Exibir alterações realizadas no commit: `git show (hash do commit)`



### Histórico curto de alterações: ```git log --online```

- Como deve suspeitar este comando apresenta o log de alterações em somente uma linha.  Neste formato algumas informações são omitidas como, autor, data, além do hash do commit ser apresentado de forma resumida.



### Histórico longo de alterações: ```git log --p```

- Assim como há a versão resumida do log há a detalhada que além de mostrar todas as informações do `git log` ele exibe as alterações realizadas no código.



### Histórico gráfico de alterações: `git log --graph `



### Alterar as configurações: ```git config```

- ​	Com esse comando, uma série de configurações tanto localmente (o projeto atual) quanto para a máquina como um todo. Para definirmos isso usamos `--local` ou `--global`, respectivamente. Geralmente esse comando é usado para definir o autor dos commits.
  - `git config --global user.name`;
  - `git config --global user.email`.



### Ignorando arquivos

- Para fazermos o Git ignorar arquivos e pastas precisamos criar um arquivo chamado **.gitignore**, ao adicionarmos arquivos e pastas neste arquivo especialo git passa a ignorá-los.
- Não há nenhum comando git ignore explícito: é preciso editar e fazer commit do arquivo `.gitignore` à mão quando você tiver novos arquivos que quer ignorar. Os arquivos `.gitignore` contêm padrões que são comparados com nomes de arquivos em seu repositório para determinar se devem ou não ser ignorados.



### Criar repositório de alterações:  `git init --bare`

- ​	Para criar um repositório onde se possa armazenar somente as alterações usamos o comando `git init --bare`.



### Criar um repositório remoto: `git remote add`

- Para adicionar um repositório remoto onde possa ser armazenada as alterações usamos o comando `git remote add (nome que deseja dar ao repositório) (caminho para este repositório que pode ser local ou um link para um servidor externo)`.
- Renomear repositório: `git remote rename (nome antigo) (novo nome)`



### Listar repositórios remotos: `git remote`

- `git remote -v` exibe o caminho deste repositório;



### Clonar repositório: `git clone (endereço do repositório)`



### Enviar alterações para o seu repositório: `git push (repositório) (branch)`



### Trazer os dados de algum repositório: `git pull (repositório) (branch)`



### Criar uma branch: `git branch (nome)`



### Deletar uma branch: `git branch -d (nome da branch)`



### Mudar para uma branch: `git checkout (nome da branch)`



### Unir branchs: `git merge (nome da branch)`

- Gera um commit a mais

  

### Atualizar branch: `git rebase (nome da branch)`

- Com esse comando todas as alterações da branch criada serão atualizadas para a branch que você se encontra sem gerar um commit de merge.

  

### Desfazer alterações antes de adicionar: `git checkout --(nome do arquivo)`



### Desfazer alterações depois de adicionar: `git reset HEAD (nome do arquivo)`



### Desfazer alterações após o commit: `git revert (hash do commit)`



### Salvar  temporariamente: `git stash`



### Listar as alterações salvas: `git stash list`



### Trazer arquivo salvo

1.  `git stash apply (numero do stash list)`
2. `git stash drop`

- Uma outra opção é usar o comando `git stash pop` com este comando o Git tira a última alteração salva.

  

### Navegar até um commit: `git checkout (hash do commit)`

- Ao "navegar" para o commit desejado todas as alterações realizadas serão ignoradas, a menos que se crie uma nova branch a partir deste commit.



### Ver a diferença entre commits: `git diff (hash do primeiro)..(hash do segundo)`



### Definir  "checkpoits" (release): `git tag -a (nome da tag) -m (mensagem se desejar)`



### Enviar tags: `git push (nome do repositório remoto) (nome da tag)`



### Unir commits: `git rebase -i HEAD~(a quantidade de commits que você quer unir)` ou `git rebase -i (commit imediatamente anterior ao que deseja unir)`

- Ao executar o comando uma tela do VIM será aberta, nela terá os commits que deseja-se unir, para uni-los trocamos a palavra "pick", dos que irão ser unidos, na frente dos commits por "s". Após isso, basta digitar ":X" + ENTER.



### Pegando um commit específico: `git cherry-pick (hash do commit)`



### Viajando entre commits: `git bisect `

- Esse comando permite que o usuário procure alterações em determinados pontos da aplicação.
  1. Para iniciar usamos o comando: `git bisect start`
  2. Precisamos informar qual parte do código não está adequada usando o comando: `git bisect bad (hash do commit)`
  3. Também precisamos informar um estado do código que estava bom, usando: `git bisect good (hash do commit)`
  4. Dentro deste intervalo de commits informado ele irá apresentar as alterações realizadas.
- Se a alteração exibida é a correta basta digitar `git bisect good`, mas caso ainda não seja a alteração que esteja procurando digite `git bisect bad` para continuar a busca.



### Exibir altores dos commits: `git blame (arquivo)`

# Ferramenta de vizualização Git: 

- [Visualizing Git](https://git-school.github.io/visualizing-git/)
- [Git Cola](https://git-cola.github.io/)
- [GitHub Desktop](https://desktop.github.com/)
- [GitKraken](https://www.gitkraken.com/)

# Mais comandos: [Git log cheatsheet](https://devhints.io/git-log)

# Salvar no VIM: `:X`

