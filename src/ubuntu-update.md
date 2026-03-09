# Comando `ubuntu-update` no Zsh

Criar um comando para **atualizar todo o sistema Ubuntu pelo terminal** (APT, Snap e Flatpak).

---

## 1. Abrir o `.zshrc`

```bash
nano ~/.zshrc
```

---

## 2. Adicionar a função

```bash
# Atualizar tudo de vez
ubuntu-update() {

SEP="━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━"

GREEN="\033[1;32m"
BLUE="\033[1;34m"
YELLOW="\033[1;33m"
RESET="\033[0m"

echo
echo -e "${SEP}"
echo -e "${BLUE}🔎 Atualizando lista de pacotes (APT)...${RESET}"
echo -e "${SEP}"
echo
sudo apt update

echo
echo -e "${SEP}"
echo -e "${BLUE}⬆️ Atualizando pacotes do sistema...${RESET}"
echo -e "${SEP}"
echo
sudo apt upgrade -y

echo
echo -e "${SEP}"
echo -e "${YELLOW}🧹 Removendo dependências antigas...${RESET}"
echo -e "${SEP}"
echo
sudo apt autoremove -y

echo
echo -e "${SEP}"
echo -e "${BLUE}📦 Atualizando snaps...${RESET}"
echo -e "${SEP}"
echo
sudo snap refresh

echo
echo -e "${SEP}"
echo -e "${BLUE}📦 Atualizando flatpaks...${RESET}"
echo -e "${SEP}"
echo
flatpak update -y

echo
echo -e "${SEP}"
echo -e "${YELLOW}🧽 Limpando cache de pacotes...${RESET}"
echo -e "${SEP}"
echo
sudo apt autoclean

echo
echo -e "${GREEN}✅ Sistema totalmente atualizado!${RESET}"
echo
}
```

---

## 3. Salvar

No `nano`:

```
CTRL + O
ENTER
CTRL + X
```

---

## 4. Recarregar o Zsh

```bash
source ~/.zshrc
```

---

## 5. Usar o comando

```bash
ubuntu-update
```

---

## Resultado

O comando executa:

- `apt update`
- `apt upgrade`
- `apt autoremove`
- `snap refresh`
- `flatpak update`
- `apt autoclean`

Tudo em **um único comando**, com saída organizada no terminal.
