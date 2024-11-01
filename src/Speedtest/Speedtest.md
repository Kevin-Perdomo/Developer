# Configuração e Uso do Speedtest

Instruções para instalar e executar o Speedtest no Windows e no Linux.

## Windows

### 1. **Baixe o arquivo ZIP** do Speedtest para o seu computador.
### 2. **Extraia** o conteúdo do ZIP no diretório desejado.
### 3. **Execute o comando** abaixo no PowerShell para realizar o teste de velocidade:

```powershell
Set-Location "Seu diretório"; .\speedtest
```
---

## Linux

### 1. **Atualize o sistema** com o comando abaixo:

```bash
sudo apt update
```

### 2. **Instale o Speedtest CLI**:

```bash
sudo apt install speedtest-cli
```

### 3. **Execute o Speedtest** com um dos comandos abaixo:

Para uma saída completa:

```bash
speedtest
```

Para uma saída simplificada:

```bash
speedtest --simple
```

---

Após seguir as instruções, o Speedtest estará configurado para medir a velocidade de internet na sua máquina pelo terminal.