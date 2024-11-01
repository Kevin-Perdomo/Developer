# Instalação do Zsh
sudo apt update
sudo apt install zsh

# Definir o Zsh como shell padrão
chsh -s $(which zsh)

# Para instalar o Oh my zsh, você pode usar o seguinte comando:
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# Para instalar o zsh-syntax-highlighting, você pode usar o seguinte comando:
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ~/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting

# Para instalar o zsh-autosuggestions, você pode usar os seguintes comandos:
git clone https://github.com/zsh-users/zsh-autosuggestions.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

# Para instalar o asdf, você pode usar o seguinte comando:
git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.10.2

# Abra o arquivo .zshrc no seu editor de texto preferido. Você pode usar o nano, vim, ou qualquer outro editor. Por exemplo, usando o nano:
nano ~/.zshrc

# Encontre a linha que começa com plugins=( 
# Essa linha geralmente é encontrada na parte superior do arquivo.
# Modifique essa linha para incluir os plugins desejados. A linha deve ficar assim:
plugins=(
	git 
	colored-man-pages 
	zsh-syntax-highlighting
	asdf
	zsh-autosuggestions
	extract
)