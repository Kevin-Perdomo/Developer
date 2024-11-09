# Como Rodar o DBeaver no WSL

<p align="center">
  <img src="https://hermes.dio.me/articles/cover/cea2ba01-236f-4194-814c-e8651bf1be44.png">
</p>

### Pré-requisitos

1. **WSL 2 com Ubuntu**
2. **Windows 10 ou 11**

---

### Passo 1: Adicionar o Repositório do DBeaver

Adicionar o repositório do DBeaver: <br>
No terminal do WSL, adicione o repositório PPA do DBeaver:

```bash
sudo add-apt-repository ppa:serge-rider/dbeaver-ce
```

### Passo 2:  Atualizar os pacotes:

Após adicionar o repositório, atualize a lista de pacotes do seu sistema:

```bash
sudo apt update
```

### Passo 3: Instalar o DBeaver
Instalar o DBeaver CE (Community Edition):

```bash
sudo apt install dbeaver-ce
```

### Passo 4: Instalar dependências gráficas:

Para garantir que o DBeaver funcione corretamente, instale as bibliotecas gráficas necessárias:

```bash
sudo apt install -y libgtk-3-0 libwebkit2gtk-4.0-37 libcanberra-gtk-module libcanberra-gtk3-module
```

### Passo 5: Rodar o DBeaver

iniciar o DBeaver diretamente no terminal do WSL com o comando:

```bash
dbeaver
```