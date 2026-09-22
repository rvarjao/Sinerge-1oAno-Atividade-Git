# Site da Turma — Atividade Prática de Git e GitHub

## O desafio

A turma inteira vai trabalhar **no mesmo repositório**. Cada aluno deverá
criar sua própria página dentro do site da turma, **sem alterar a página
dos colegas**.

No final, o site terá uma página inicial (`index.html`) com o nome de
todos os alunos. Ao clicar no seu nome, cada um deve chegar até a página
que você mesmo criou.

Essa atividade não é sobre HTML bonito — é sobre aprender, na prática, como
um time usa Git e GitHub para trabalhar no mesmo projeto sem bagunçar o
trabalho dos outros.

---

## Passo a passo

### 1. Clonar o projeto

```bash
git clone URL_DO_REPOSITORIO
```

`git clone` faz uma cópia completa do repositório (com todo o histórico)
do GitHub para o seu computador. É a partir dessa cópia local que você vai
trabalhar.

### 2. Entrar na pasta

```bash
cd NOME_DO_REPOSITORIO
```

### 3. Criar sua própria branch

Uma branch é como uma "linha do tempo paralela" do projeto, onde você pode
fazer alterações sem afetar o trabalho dos outros. Crie uma com o seu nome:

```bash
git switch -c seu-nome-sobrenome
```

Exemplo:

```bash
git switch -c joao-silva
```

Use o **mesmo nome/sobrenome** que você vai usar no arquivo da sua página.

> ⚠️ **Nunca faça alterações diretamente na branch `main`.**
> A `main` é a versão oficial do site. Todo trabalho começa em uma branch
> própria.

### 4. Criar sua página

Dentro da pasta `alunos/`, crie um arquivo HTML com o seu nome, por exemplo:

```text
alunos/joao-silva.html
```

⚠️ O nome do arquivo precisa ser **exatamente igual** ao endereço que já
está configurado no link do seu nome em `index.html`. Se o link aponta
para `alunos/joao-silva.html`, o arquivo criado precisa ter esse nome
exato (letras minúsculas, sem espaços e sem acentos).

Veja mais abaixo um exemplo de estrutura para a sua página.

### 5. Conferir o que foi alterado

```bash
git status
```

Esse comando mostra quais arquivos foram criados, modificados ou
removidos desde o último commit. Use-o sempre que quiser conferir o que
está prestes a enviar.

### 6. Adicionar o arquivo ao commit

```bash
git add alunos/joao-silva.html
```

O `git add` seleciona o arquivo que você quer incluir no próximo commit.

### 7. Criar o commit

```bash
git commit -m "Adiciona página do João Silva"
```

Um commit é um "registro" (uma foto) de uma alteração no projeto, com uma
mensagem explicando o que foi feito. Ele fica guardado no histórico do
Git para sempre.

### 8. Enviar sua branch para o GitHub

```bash
git push -u origin joao-silva
```

Esse comando envia a sua branch (com o seu commit) para o repositório no
GitHub, deixando-a disponível para o professor revisar e, depois, juntar
o seu trabalho à `main`.

---

## Regras da atividade

1. ❌ Não altere a página de outro aluno.
2. ❌ Não trabalhe diretamente na branch `main`.
3. ✅ Cada aluno deve criar sua própria branch.
4. ✅ Cada aluno deve criar **apenas** o seu próprio arquivo dentro da pasta `alunos/`.
5. ❌ Não altere o `index.html` sem autorização do professor.
6. ✅ A sua página precisa abrir corretamente ao clicar no seu nome na página inicial.
7. ✅ Nesta primeira atividade, tente entregar seu trabalho em **apenas um commit**.

---

## Checklist de entrega

- [ ] Clonei o repositório
- [ ] Criei minha branch
- [ ] Criei minha página
- [ ] Testei minha página no navegador
- [ ] Usei `git status`
- [ ] Usei `git add`
- [ ] Fiz meu commit
- [ ] Fiz push da minha branch

---

## Exemplo de estrutura da página do aluno

Você pode usar o modelo abaixo como ponto de partida e personalizar como
quiser (cores, textos, layout). A página deve conter, no mínimo:

* seu nome;
* uma pequena apresentação;
* três interesses;
* uma imagem;
* um link para voltar para o `index.html`.

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>João Silva</title>
  <link rel="stylesheet" href="../style.css" />
</head>
<body>
  <div class="pagina-aluno">
    <h1>João Silva</h1>

    <img src="https://via.placeholder.com/300" alt="Foto de João Silva" />

    <p>
      Olá! Sou aluno do curso de Desenvolvimento de Sistemas e esta é a
      minha primeira página criada usando Git e GitHub.
    </p>

    <h2>Meus interesses</h2>
    <ul>
      <li>Programação</li>
      <li>Jogos</li>
      <li>Música</li>
    </ul>

    <a class="voltar" href="../index.html">&larr; Voltar para a página inicial</a>
  </div>
</body>
</html>
```

---

## Como o trabalho da turma se organiza

Cada aluno trabalha na sua própria branch, sem interferir no trabalho dos
colegas. Mais adiante, o professor vai revisar e juntar (merge) cada
branch à `main`, formando o site completo da turma.

```text
main
│
├── arthur-goncalves
├── brayan-paula
├── brendha-duarte
├── caue-souza
├── davi-niedzievski
├── ...
└── rebecca-mroczko
```

---

## O que ainda não vamos ver

Esta atividade tem um foco bem específico. Ainda **não** vamos falar sobre:

* conflitos de merge;
* rebase;
* cherry-pick;
* Git Flow;
* comandos avançados de Git.

Por enquanto, o fluxo que importa é só este:

```text
clone
  ↓
branch
  ↓
editar/criar arquivo
  ↓
status
  ↓
add
  ↓
commit
  ↓
push
```

Bom trabalho e boa prática! 🚀
