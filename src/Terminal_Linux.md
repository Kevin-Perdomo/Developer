# Instalação e Configuração do Zsh com Plugins

Este guia fornece instruções para instalar o Zsh, definir como shell padrão, e configurar os plugins `Oh My Zsh`, `zsh-syntax-highlighting`, `zsh-autosuggestions` e `asdf`.

## Passos de Instalação

### 1. Instalar o Zsh

Atualize os pacotes e instale o Zsh:

```bash
sudo apt update
sudo apt install zsh
```

### 2. Definir o Zsh como shell padrão

```bash
chsh -s $(which zsh)
```

### 3. Para instalar o Oh my zsh, você pode usar o seguinte comando:

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

### 4. Para instalar o zsh-syntax-highlighting, você pode usar o seguinte comando:

```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ~/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting
```

### 5. Para instalar o zsh-autosuggestions, você pode usar os seguintes comandos:

```bash
git clone https://github.com/zsh-users/zsh-autosuggestions.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

### 6. Para instalar o asdf, você pode usar o seguinte comando:

```bash
git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.10.2
```

### 7. Abra o arquivo .zshrc no seu editor de texto preferido. Você pode usar o nano, vim, ou qualquer outro editor. Por exemplo, usando o nano:

```bash
nano ~/.zshrc
```

### 8. Modifique essa linha para incluir os plugins desejados 
Encontre a linha que começa com `plugins=(` <br>
Essa linha geralmente é encontrada na parte superior do arquivo. <br>
A linha deve ficar assim:

```bash
plugins=(
	git 
	colored-man-pages 
	zsh-syntax-highlighting
	asdf
	zsh-autosuggestions
	extract
)
```