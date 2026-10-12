# workshop-git-treino

Exercício do workshop de Git e GitHub do **n.inf**.

O objetivo é acrescentares o teu nome a `CONTRIBUTORS.md` através de um Pull Request. No fim terás usado fork, clone, branch, commit, push e Pull Request.

## Passos

1. **Fork.** Clica em **Fork** no topo desta página para criares a tua cópia.

2. **Cria um token (PAT).** Em GitHub, vai a Settings, Developer settings, Personal access tokens, Fine-grained tokens, Generate new token.
   - Repository access: *Only select repositories*, e escolhe só o teu fork.
   - Permissions: Contents com *Read and write*.
   - Validade curta (por exemplo 7 dias). Copia o token, só aparece uma vez.

3. **Clona o teu fork.**
   ```bash
   git clone https://github.com/<o-teu-utilizador>/workshop-git-treino.git
   cd workshop-git-treino
   ```

4. **Cria uma branch.**
   ```bash
   git switch -c <o-teu-nome>/adiciona-nome
   ```

5. **Edita `CONTRIBUTORS.md`.** Acrescenta o teu nome numa nova linha **no fim** da lista.

6. **Guarda a alteração.**
   ```bash
   git status
   git add CONTRIBUTORS.md
   git commit -m "Adiciona <o-teu-nome> aos contribuidores"
   ```

7. **Envia para o teu fork.**
   ```bash
   git push -u origin <o-teu-nome>/adiciona-nome
   ```
   O Git pede o username e a palavra-passe: usa o teu username e **o token** como palavra-passe.

8. **Abre um Pull Request** para este repositório. No GitHub aparece um botão *Compare & pull request*.

## Desafio: resolver um conflito

Se vários Pull Requests mexerem no fim do mesmo ficheiro, o GitHub avisa que há conflitos. Para os resolver:

```bash
git remote add upstream https://github.com/<dono>/workshop-git-treino.git
git pull upstream main
```

Abre `CONTRIBUTORS.md`, mantém todos os nomes e apaga as marcas `<<<<<<<`, `=======` e `>>>>>>>`. Depois:

```bash
git add CONTRIBUTORS.md
git commit
git push
```

Regras e convenções em [CONTRIBUTING.md](CONTRIBUTING.md).
