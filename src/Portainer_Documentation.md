# Portainer 

Este guia fornece instruções para criar e iniciar o Portainer utilizando Docker.

## Passos de Instalação

1. Crie um volume Docker para armazenar dados do Portainer:

```bash
docker volume create portainer_data
```

2. Execute o Portainer em um contêiner Docker:

```bash
docker run -d -p 8001:8001 -p 9443:9443 --name portainer --restart=always \
    -v /var/run/docker.sock:/var/run/docker.sock \
    -v portainer_data:/data portainer/portainer-ce:2.21.0
```

### Parâmetros do Comando `docker run`

- **-d**: Executa o contêiner em segundo plano.
- **-p 8001:8001 -p 9443:9443**: Expõe as portas 8001 (interface HTTP) e 9443 (interface HTTPS) do Portainer.
- **--name portainer**: Define o nome do contêiner como "portainer".
- **--restart=always**: Garante que o contêiner será reiniciado automaticamente se ele parar.
- **-v /var/run/docker.sock:/var/run/docker.sock**: Conecta o Docker socket ao contêiner, permitindo que o Portainer gerencie os contêineres Docker.
- **-v portainer_data:/data**: Monta o volume `portainer_data` no contêiner para persistir os dados.

Após a execução, você poderá acessar a interface do Portainer em `http://localhost:8001` ou `https://localhost:9443`.

---

Para mais informações sobre o Portainer, consulte a [documentação oficial](https://www.portainer.io/documentation).
