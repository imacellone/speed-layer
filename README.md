# POC - Speed Layer - Open Banking

Instruções de como subir e executar esta POC.


## Software Necessário

 1. **Git** instalado e configurado adequadamente.
 2. **Docker**.
 3. **Docker Compose**.

## Configuração

1 - Solicite, ao dono deste repositório, a inclusão de seu usuário para obter acesso ao repositório: **https://github.com/imacellone/nifi-registry**

2 -  **Gere** suas **chaves SSH** para configurar o acesso ao repositório: **https://github.com/imacellone/nifi-registry**, **bem como este** repositório. *Para mais informações: https://docs.github.com/pt/github/authenticating-to-github/connecting-to-github-with-ssh.*

 - Não utilize senhas durante a criação da chave SSH!
 
 3 - Clone **este** repositório. *Para mais informações: https://git-scm.com/book/pt-pt/v2/No%C3%A7%C3%B5es-B%C3%A1sicas-do-Git-Obtendo-um-Reposit%C3%B3rio-Git.*

4 - Na raiz do projeto, há um arquivo chamado: *docker-compose.yml*. Nele, altere as configurações, indicadas pelos comentários, para o correto funcionamento deste projeto.

## Execução

1 - Em um terminal, abra o diretório raiz do projeto.
2 - Execute: `sudo docker-compose up -d` . A primeira execução deste comando pode levar vários minutos.*
3 - Anote o endereço IP resultante da execução do seguinte comando: `sudo docker inspect nifi-registry | grep Gateway`.

### Acesse as duas instâncias de NiFi
1 - http://localhost:8080
2 - http://localhost:9090

**Em cada instância:** Configure o NiFi Registry com `http://<ip anotado no passo 3>:18080` e, em seguida: Botão direito do mouse no canvas -> Refresh.

**Na instância 1**, importe o Process Group relacionado à importação de arquivos, do Nifi Registry.
**Na instância 2**, importe o Process Group relacionado à persistência no MongoDB, do Nifi Registry.


#### Pronto! Divirta-se!

## Encerrar
Para parar todos os contêineres, basta rodar o seguinte comando no diretório raiz do projeto: 
`sudo docker-compose down`
