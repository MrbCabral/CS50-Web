# Git
- Git é um sistema de controle de versão de código;
- Controle de versão é o gerenciamento de mudanças de documentos, programas, web sites, configurações de equipamentos e outros conjuntos de informações;
- Git pode acompanhar as alterações feitas no código, sincronizar o código entre diferentes pessoas, testar alterações no código sem perder o original e reverter para versões antigas do código;
- GitHub é um site que armazena repositórios do Git na Internet para facilitar a colaboração que o Git permite;
- Repositório é um local para acompanhar o código e todas suas alterações;
- Pode-se usar o git pela interface de linha de comandos (CLI) ou por interface gráfica ([GitKraken](https://www.gitkraken.com/), [GitHub Desktop](https://desktop.github.com/), [Web](https://github.com/));

## Alguns Comandos
- `git clone <url>`: pega um repositório armazenado em um servidor (como o GitHub) e salva numa pasta na sua máquina local
    > `git clone git@github.com:MrbCabral/CS50-Web.git`
- `git add <filename(s)>`: adiciona arquivos à área de preparação para serem incluídos no próximo commit
- `git commit -m "message"`: tira um snapshot do repositório (local) e salve-o  com uma mensagem sobre as alterações
- `git commit -am <filename(s)> "message"`: adiciona arquivos e _commita_ as mudanças
- `git status`: mostra o estado atual do repositório
- `git push`: envia quaisquer alterações locais (commits) para um servidor remoto
- `git pull`: pega quaisquer alterações deste repositório no servidor remoto e salva na máquina local
- `git log`: mostra o histórico de todos os commits 
- `git reflog`: mostra uma lista de todas as referências diferentes a commits
- `git reset HEAD~1`: Desfaz o último commit
- `git reset <hash-commit>`: Volta a versão do commit específico
- `git reset --hard <commit>`: redefine o repositório para um determinado commit (_"volta para o código que funcionava"_)
- `git reset --hard origin/master`: redefine o repositório apra o estado original (p.e., a versão clonada no GitHub)
- `git ignore "*.log"`: ignora todos os arquivos .log ao adicionar as mudanças
- `git lock config/database.yml`: configura para que as mudanças em `config/database.yml` não seja _commitadas_
- `git unlock config/database.yml`: desfaz o comando anterior
- `git obliterate secret.yml`: remove todas as referências ao arquivo `secret.yml`

## Mesclagem (Merge)
- Ao combinar diferentes versões de código, p.e. usando o `git pull`, um conflito de mesclagem pode ocorrer se as diferentes versões tiverem dados diferentes no mesmo local. O Git tentará cuidas da mesclagem automaticamente, mas se dois usuários editarem, p.e., a mesma linha, um conflito de mesclagem precisará ser resolvido manualmente.
    - Para resover, remova localmente todas as linhas e códigos que não são desejados e envie os resultados.

## Autenticação
- Ao usar git na CLI, você pode querer registrar uma chave SSH. Para isso, siga os passos:
1. [Gerar chaves SSH](https://help.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
2. [Associar a chave a conta GitHub](https://help.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account)
3. [Autorizar a chave para longon único](https://help.github.com/en/github/authenticating-to-github/authorizing-an-ssh-key-for-use-with-saml-single-sign-on)
4. Para testar, digite:
```bash
ssh -T git@github.com
yes
```
_Senha digitada no passo 1, quando criou a chave SSH. Ou seja, a senha que protege a chave gerada._

## Fluxo (Workflow)
Local Git: Escrever -> git add -> git commit -> git push

## Ramificações (Branching)

```
                +---------+   +---------+   +---------+   +---------+   +---------+
Master Branch   |commit #1|-->|commit #2|-->|commit #3|-->|commit #4|-->|  merge  |
                +---------+   +---------+   +---------+   +---------+   +---------+
                                   :                                         ^
                                   |        +---------+   +---------+        |
Feature Branch                     +------->|commit #1|-->|commit #2|--------+
                                            +---------+   +---------+
```
- `git branch`: mostra em qual ramo está;
- `git branch --list`: lista os ramos existentes;
- `git checkout -b <branchname>`: cria um ramo localmente
- `git push origin <branchname> --set-upstream`: envia o ramo ao servidor
- Mais comandos: [git branch](https://devhints.io/git-branch)

<!-- TODO
Fork
Pull Request
-->

## Ref
- [Git Commands - Wethefoss](https://wethefoss.github.io/Git-Commands/)
- [Git and GitHub for Beginners - Crash Course - freeCodeCamp.org](https://www.youtube.com/watch?v=RGOj5yH7evk)
- [Usando Git](https://help.github.com/pt/github/using-git)
- [Git Crash Course - Traversy Media](https://www.youtube.com/watch?v=SWYqp7iY_Tc)