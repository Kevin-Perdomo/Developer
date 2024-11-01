# Configuração e Comandos Úteis do Docker e Docker Compose

## Docker

### 1. **Instalação do Docker:**

```bash
sudo su
curl -fsSL https://get.docker.com -o get-docker.sh
sh get-docker.sh
groupadd docker
```

> **Nota:** Substitua `$USER` pelo nome do seu usuário no comando abaixo:

```bash
usermod -aG docker $USER
```

### 2. **Reinicie o computador** e, após a reinicialização, execute o comando abaixo para verificar se o Docker foi instalado corretamente:

```bash
docker --version
docker run hello-world
docker ps
```

### 3. **Instalação do Docker Compose:**

```bash
sudo apt-get update
sudo apt-get install docker-compose-plugin
```

### 4. **Verifique a versão instalada do Docker Compose:**

```bash
docker compose version
```

---

## Comandos Úteis Docker Compose

Executa build das imagens do projeto utilizando padrões do compose. Equivale ao comando docker build .

```bash
docker compose build
```

Cria um container temporário do serviço chamado app e permite interação com o mesmo usando o terminal bash. <br>
Útil para criação de apps usando as dependências da imagem.

```bash
docker compose run --rm app bash
```

Inicia os contêineres dos serviços descritos no arquivo docker-compose.yml. <br>
Com a opção -d deixa de mostrar o log dos serviços e libera o terminal para uso.

```bash
docker compose up
```

Para a execução de todos os contêineres em execução dos serviços descritos no arquivo docker-compose.yml. <br>
Após o termo 'stop' é possível indicar opcionalmente o nome de um serviço específico que deseja parar. <br>
Ex.: docker compose stop db <br>
vai parar apenas o serviço db.

```bash
docker compose stop
```

Remove os contêineres e demais artefatos de docker do projeto. Deve ser usado com cuidado.

```bash
docker compose down
```

Exemplo de aplicação python usando docker-compose: <br>
(https://docs.docker.com/compose/gettingstarted/)