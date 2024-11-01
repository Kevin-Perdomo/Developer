# Configuração de Chave SSH na Máquina e na Conta do GitHub

Para configurar uma chave SSH na sua máquina e vinculá-la à sua conta do GitHub, siga as instruções abaixo:

## 1. **Acesse o terminal Linux** (ou o aplicativo Linux no Windows) e execute os seguintes comandos:

    
### Gerar uma nova chave SSH
```bash
ssh-keygen -t ed25519 -C "seu e-mail entre aspas"
```

### Configurar o nome do usuário global para o Git
```bash
git config --global user.name "seu nome completo entre aspas"
```

### Configurar o e-mail do usuário global para o Git
```bash
git config --global user.email "seu e-mail entre aspas"
```

### Exibir a chave SSH pública gerada
```bash
cat ~/.ssh/id_ed25519.pub
```

## 2. **Copie a chave SSH pública exibida** após o último comando.

## 3. **Adicione a chave ao GitHub**:

    - Acesse o GitHub e vá até **Settings > SSH and GPG keys**.
    - Clique em **New SSH key**, cole a chave copiada, e salve.

Com isso, sua chave SSH estará configurada para autenticação no GitHub.