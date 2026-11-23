# Versionamento de Dados e Modelos com Git e DVC (`aula-ml`)

Repositório da **Atividade Prática 07** de **Engenharia de Sistemas Inteligentes (CK0444 – 2026.2)** da Universidade Federal do Ceará (UFC).

## Pré-requisitos
- Python 3.10 ou superior
- Git 2.x ou superior
- DVC 3.x (`pip install dvc` ou `pipx install 'dvc>=3,<4'`)
- Terminal Bash / Zsh (ou WSL / Git Bash no Windows)

## Configuração do Armazenamento DVC
Os metadados (`.dvc`), manifestos, parâmetros e métricas são versionados no Git. Os dados (`.csv`) e o modelo (`models/model.json`) ficam armazenados no remote local configurado em `../dvc-storage`.

Para conferir o remote configurado:

    dvc remote list

Se necessário ajustar o caminho localmente:

    dvc remote modify --local storage url /caminho/para/dvc-storage

## Restauração de uma Versão Anterior (`modelo-r1`)
1. Clone o repositório ao lado da pasta `dvc-storage`:

       git clone [https://github.com/GabrielGarcia2309/aula-ml.git](https://github.com/GabrielGarcia2309/aula-ml.git) aula-ml-restauracao
       cd aula-ml-restauracao

2. Selecione a tag da versão desejada:

       git switch --detach modelo-r1

3. Recupere os artefatos registrados no DVC:

       dvc pull

4. Confira os hashes SHA-256 contra `reports/modelo.json`.
