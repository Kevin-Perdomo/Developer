# Configuração de SO

Este guia fornece instruções de configuração de ambiente para Linux e Windows, com as ferramentas necessárias para desenvolvimento de software.

---

## Requisitos no Linux

Para Ubuntu LTS ou outra distribuição compatível com Docker:

- **Linux Ubuntu LTS** ou qualquer distro que permita o uso de Docker
- **Git**: instale com o comando: 
```bash
sudo apt install git
```
- **Chave SSH**: configurada na máquina e na conta do GitHub
- **Docker**: para gerenciamento de contêineres
- **Docker Compose**: para orquestração de contêineres
- **VSCode** (opcional): editor de código

### Ubuntu 22.04 LTS ou Superior

- Configure o **Docker Desktop** para integrar Docker com o Ubuntu
- Configure uma **chave SSH** na máquina Ubuntu e a associe à sua conta do GitHub

---

## Requisitos no Windows

Para Windows 10 ou superior, com os seguintes aplicativos instalados:

- **VSCode**: editor de código
- **WSL (Windows Subsystem for Linux V2)**: para rodar um ambiente Linux dentro do Windows

### Comandos para Configuração do WSL

Execute os seguintes comandos para configurar o WSL:

```bash
wsl --install
wsl --set-default-version 2
wsl --list --verbose
```