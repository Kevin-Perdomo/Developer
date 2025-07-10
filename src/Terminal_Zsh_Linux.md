# Instalação e Configuração do Zsh com Plugins

Este guia fornece instruções para instalar o Zsh, definir como shell padrão, e configurar os plugins `Oh My Zsh`, `zsh-syntax-highlighting`, `zsh-autosuggestions` e `asdf`.

**Repositório oficial do Oh My Zsh:** https://github.com/ohmyzsh/ohmyzsh

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

### 9. Alterando o Tema do Oh My Zsh

Para personalizar a aparência do seu terminal, você pode alterar o tema do Oh My Zsh.

No arquivo `~/.zshrc`, encontre a linha que começa com `ZSH_THEME=` e modifique para o tema desejado:

```bash
ZSH_THEME="nome-do-tema"
```

### Temas populares:

- `robbyrussell` (tema padrão)
- `agnoster` (tema com ícones e cores)
- `powerlevel10k` (tema altamente customizável)
- `spaceship` (tema minimalista e informativo)

### Exemplo de configuração:

```bash
ZSH_THEME="agnoster"
```

### Onde encontrar mais temas:

Você pode encontrar uma lista completa de temas disponíveis no repositório oficial do Oh My Zsh:

**GitHub:** https://github.com/ohmyzsh/ohmyzsh/wiki/Themes

Após alterar o tema, reinicie o terminal ou execute:

```bash
source ~/.zshrc
```

para recarregar as configurações do terminal após fazer mudanças no arquivo de configuração.
