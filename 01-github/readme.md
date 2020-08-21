# Github

![arquitetura](./imagem.png)

## GIT E GITHUB:

> git é um site

repositório = pasta
github = host = hospedagem
hospedagem é onde fica salvo fisicamente

quando faz qualquer alteração no código vai no '+' no ícone do git, depois vai no terminal dá um git commit -m '', e depois um git push origin master.


dúvida, achou mais legal, difícil.
prints, anotações, 

fazer um git clone, abrir no visual studio clone.
e colocar as anotações. 
salva como jpeg - imagem

> Adiciona o arquivo em stage
```bash
git add ./01-github/readme.md 
```
> Comita os arquivos em stage
```bash
git commit -m 'primeiro commit
```
> Submete os commits não enviados para o remote origin
```bash
git push origin master
```
> Puxa os commits remotos para o repositório local
```bash
git pull origin master
```
---
20/08/2020

---
O modo como você reúne, administra e usa a informação determina se vencerá ou perderá.

![bill gates](./bill.jpg)

---

> comando para adicionar imagem
```bash
![arquitetura](./imagem.png) (entre os parênteses põe o caminho onde está a imagem)
```

> comando para criar uma branch
```bash
git checkout -b NOME DA BRANCH  
-b siginifica criar a branch. Se não colocar o -b quer dizer que está modificando-a. 
```

 > comando para voltar para branch master
 ```bah
 git checkout master
 ```
 
 > comando para ver o que foi alterado
 ```bash
 git status
 ```

 > criando e mantendo oculta uma pasta que precisa ficar somente local
 ``` bash
Usar arquivo secreto(com senhas, etc): cria pasta .env (nela vai inserir o que não pode ser enviado para o repositório). Depois criamos a pasta .gitignore. 
Na pasta gitgore insere o nome da pasta que deve ficar somente local.
```

> comando que armazena temporariamente na memoria os arquivos modificados
```bash
git stash push
```

> comando para voltar ao trabalho anterior. 
```bash
git stash pop
```

> semantic version (exemplo> 1.0.0)
1º número - mudança grande
2º número - funcionalidade nova
3º número - bug fixo

