AMBIENTE VIRTUAL EM PYTHON:
    Pasta que contém uma instalação isolada do Python e um conjunto próprio de  pacotes/bibliotecas. Quando você o ativa, os comandos python e pip passam a apontar para esse ambiente, e tudo que você instalar fica só ali, sem afetar o Python global do sistema nem outros projetos.
    
    Evita conflitos de dependências. Exemplo:
        1. Projeto A precisa de Django==4.2
        2. Projeto B precisa de Django==5.0
    
    Sem ambiente virtual, os dois usariam a mesma instalação global e um quebraria o outro. Com ambientes virtuais, cada projeto tem suas versões isoladas.
    Vantagens principais:
        1. Isola dependências por projeto.
        2. Evita poluir o Python do sistema.
        3. Facilita reproduzir o ambiente em outra máquina.
        4. Ajuda no deploy e no trabalho em equipe.
        5. Permite testar versões diferentes de bibliotecas sem conflito.
        
    Ambiente virtual não é máquina virtual. Ele não virtualiza o sistema operacional; apenas isola pacotes Python.

    Para criar um ambiente virtual, vá no terminal, dentro da pasta do projeto:
        - cd meu_projeto
        - python -m venv .venv
    
    Se python não funcionar, tente:
        - python3 -m venv .venv
    
    No Windows, também pode usar:
        - py -m venv .venv

    Isso cria uma pasta chamada .venv dentro do projeto.

    Como ativar no Windows — PowerShell:
        - .\.venv\Scripts\Activate.ps1
    
    Se der erro de permissão:
        - Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
    
    Windows — CMD:
        - .venv\Scripts\activate.bat
    
    Linux / macOS:
        - source .venv/bin/activate
    
    Git Bash no Windows:
        - source .venv/Scripts/activate
    
    Quando ativado, normalmente aparece algo assim no terminal:
        - (.venv) $
    
    Usando o ambiente aivado:
        - python --version
        - pip list
        - pip install requests
    
    Para salvar as dependências do projeto:
        - pip freeze > requirements.txt
    
    Para recriar o ambiente em outra máquina:
        - python -m venv .venv
        - source .venv/bin/activate  # ou o comando equivalente no Windows
        - pip install -r requirements.txt
    
    Para sair do ambiente:
        - deactivate
    
    Boas práticas envolve não dar commite a pasta ".venv" no git. É importante também adicionar ao ".gitignore":
        - .venv/
        - venv/
        - __pycache__/
    
    Importante dar commite no "requirements.txt ou o pyproject.toml, criar um ambiente virtual por projeto e ativar o ambiente antes de instalar qualquer biblioteca.

    Esta é uma forma de manter cada projeto Python com suas próprias dependências, versões e cofigurações, sem bagunçar o Python global da máquina.