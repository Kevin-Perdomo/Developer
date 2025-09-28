# System Info Display Tools

## Ferramentas de Exibição de Informações do Sistema e Repositórios

<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/e/ed/Arch_Linux_Base_Neofetch_output.png">
</p>

Ferramentas de linha de comando para exibir informações detalhadas do sistema operacional, hardware e repositórios Git de forma visual e organizada.

## **Winfetch** no Windows via Chocolatey

Instale o Winfetch:
```bash
choco install winfetch -y
```
Execute:
```bash
winfetch.ps1
```

## **Neofetch** no Linux via APT

Atualize os pacotes:
```bash
sudo apt update
```

Instale o Neofetch:
```bash
sudo apt install neofetch
```

Execute o Neofetch:
```bash
neofetch
```

## **Fastfetch** - Instalação no Ubuntu (zsh)

O Fastfetch é uma alternativa mais rápida ao Neofetch, escrita em C.

### 1. Instalar dependências
```bash
sudo apt update && sudo apt install -y build-essential cmake make gcc pkg-config git
```

### 2. Clonar e compilar
```bash
git clone https://github.com/fastfetch-cli/fastfetch.git ~/fastfetch
cd ~/fastfetch
mkdir -p build && cd build
cmake ..
make -j$(nproc)
sudo make install
```

### 3. Testar
```bash
fastfetch
```

## **Onefetch** - Instalação no Ubuntu (zsh)

O Onefetch exibe informações de repositórios Git de forma visual e detalhada.

### 1. Instalar Rust via rustup
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
source $HOME/.cargo/env
```

### 2. Instalar Onefetch
```bash
cargo install onefetch
```

### 3. Garantir que cargo/bin está no PATH do zsh
```bash
echo 'export PATH="$HOME/.cargo/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

### 4. Atalho opcional para rodar em qualquer repositório Git
```bash
echo 'alias gitinfo="onefetch"' >> ~/.zshrc
source ~/.zshrc
```

### 5. Testar dentro de um repositório Git
```bash
# cd /caminho/do/repositorio
# onefetch  ou gitinfo
```

---

## 📝 Resumo das Ferramentas

- **Neofetch**: Clássico e amplamente usado, mostra informações do sistema
- **Winfetch**: Versão para Windows do Neofetch
- **Fastfetch**: Alternativa mais rápida ao Neofetch, escrita em C
- **Onefetch**: Especializada em mostrar informações de repositórios Git