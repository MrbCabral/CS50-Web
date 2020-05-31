## Git and GitHub
- Git é um sistema de controle de versão de código;
- Controle de versão é o gerenciamento de mudanças de documentos, programas, web sites, configurações de equipamentos e outros conjuntos de informações;
- Git pode acompanhar as alterações feitas no código, sincronizar o código entre diferentes pessoas, testar alterações no código sem perder o original e reverter para versões antigas do código;
- GitHub é um site que armazena repositórios do Git na Internet para facilitar a colaboração que o Git permite;
- Repositório é um local para acompanhar o código e todas suas alterações;
- Pode-se usar o git pela interface de linha de comandos (CLI) ou por interface gráfica ([GitKraken](https://www.gitkraken.com/), [GitHub Desktop](https://desktop.github.com/), [Web](https://desktop.github.com/));
- Comandos Git:
    - `git clone <url>` : pega um repositório armazenado em um servidor (como o GitHub) e salva numa pasta na sua máquina local
        > `git clone https://github.com/MrbCabral/CS50-Web.git`
    - `git add <filename(s)>` : adiciona arquivos à área de preparação para serem incluídos no próximo commit
    - `git commit -m "message"` : tira um snapshot do repositório (local) e salve-o  com uma mensagem sobre as alterações
    - `git commit -am <filename(s)> "message"` : adiciona arquivos e _comita_ as mudanças
    - `git status` : mostra o estado atual do repositório
    - `git push` : envia quaisquer alterações locais (commits) para um servidor remoto
    - `git pull` : pega quaisquer alterações deste repositório no servidor remoto e salva na máquina local
    - `git log` : mostra o histórico de todos os commits 
    - `git reflog` : mostra uma lista de todas as referências diferentes a commits
    - `git reset --hard <commit>` : redefine o repositório para um determinado commit (_"volta para o código que funcionava"_)
    - `git reset --hard origin/master` : redefine o repositório apra o estado original (p.e., a versão clonada no GitHub)
- Ao combinar diferentes versões de código, p.e. usando o `git pull`, um conflito de mesclagem pode ocorrer se as diferentes versões tiverem dados diferentes no mesmo local. O Git tentará cuidas da mesclagem automaticamente, mas se dois usuários editarem, p.e., a mesma linha, um conflito de mesclagem precisará ser resolvido manualmente.
    - Para resover, remova localmente todas as linhas e códigos que não são desejados e envie os resultados.

## Ref
- [https://wethefoss.github.io/Git-Commands/]
- [Git and GitHub for Beginners - Crash Course - freeCodeCamp.org](https://www.youtube.com/watch?v=RGOj5yH7evk)