# Title   

Evitar múltiplos votos de uma mesma origem

### Status

Pendente

### Date

2024-10-06   

### Context

Objetivo desta funcionalidade é auxiliar a detecção e prevenção de fraudes no sistema, mapeando a origem dos eleitores e se já foi computado os votos. Sempre mantendo a privacidade dos eleitores sem comprometer a transparência do processo e sem vincular o voto a origem(eleitor e de onde está votando).   

### Decision


- Somente eleitores devidamente cadastrados podem realizar votação, sendo os votos desvinculados ao eleitor.   
- Cada login do eleitor é registrado, com informações sobre IP e hash (browser hash) criado do navegador.   
- Gravar os dados:
    - o session ID do usuário
    - IP de origem
    - browser hash
    - Dados do navegador do usuário (headers)
    - Identificação do usuário
- Evitar um usuário de realizar mais de um login por vez, associando dados como IP de origem, hash.   
    - Se mais de um login for realizado por vez deve ser enviado uma notificação para o usuário e para equipe de prevenção com os dados do acesso.   
- Após um eleitor realizar o voto o sistema, deve ser gravada novamente as informações sobre    


### Consequences   

**Positive:**   

- Melhorar a detecção de fraude   
- Tentativa de evitar bots   


**Negative:**   

- Ocorrência de falso positivos, desta forma impedindo votos válidos de serem computados.

### Compliance    

- Votos não podem ser vinculados ao eleitor.   
- Eleitores podem ter acesso as suas informações de acesso.   
- Notificação das partes, por meio selecionado previamente.   

### Notes   

- Author: Cleber Simm        
- Version: 0.1   
- Changelog:
    - 0.1: Versão inicial do documento   