# Guia de Extensões Essenciais para Ubuntu (GNOME)

<p align="center">
   <img src="https://mikesmithers.wordpress.com/wp-content/uploads/2023/11/activities_extension_manager.png?w=592" alt="Extension Manager no Ubuntu">
</p>

As extensões do GNOME permitem personalizar e aprimorar a experiência no Ubuntu, adicionando funcionalidades e recursos visuais ao sistema. O **Extension Manager** facilita a busca, instalação e gerenciamento dessas extensões de forma gráfica e intuitiva.

---

## 🔧 Extensões Recomendadas

### 1. Clipboard History

Permite acessar o histórico da área de transferência, semelhante ao `Windows + V` no Windows.

- **Atalho padrão:** `Ctrl` + `Alt` + `V`
- Útil para recuperar textos copiados anteriormente.
- [Página oficial](https://extensions.gnome.org/extension/4839/clipboard-history/)

### 2. Lockscreen Extension

Facilita o bloqueio de tela pela interface, adicionando botão ou atalho visual.

- Ideal para quem bloqueia a tela com frequência.
- [Página oficial](https://extensions.gnome.org/extension/7472/lockscreen-extension/)

### 3. User Themes

Permite aplicar temas personalizados ao GNOME Shell.

- Use o **GNOME Tweaks** para gerenciar temas.
- Baixe temas em: [GNOME-Look.org](https://www.gnome-look.org/)
- [Página oficial](https://extensions.gnome.org/extension/19/user-themes/)

### 4. Vitals

Exibe informações do sistema em tempo real (CPU, RAM, temperatura, ventoinhas, etc).

- Mostra as métricas na barra superior do GNOME.
- [Página oficial](https://extensions.gnome.org/extension/1460/vitals/)

---

## 🛠 Como Instalar o Extension Manager

Se ainda não possui o Extension Manager, instale pelo terminal:

```bash
sudo apt update && sudo apt install gnome-shell-extension-manager
```

Após a instalação, procure por "Extension Manager" no menu de aplicativos e explore as extensões disponíveis.

---

## 💡 Dicas e Observações

- Algumas extensões podem exigir reinicialização da sessão do GNOME para funcionar corretamente.
- Caso uma extensão não funcione, verifique se está compatível com a versão do seu GNOME Shell.
- Para personalização avançada, instale também o **GNOME Tweaks**:
  ```bash
  sudo apt install gnome-tweaks
  ```
- Consulte sempre as páginas oficiais das extensões para instruções e atualizações.

## 🎤 Problema do Microfone em Videochamadas (Chrome/Chromium)

### Problema Identificado
Durante videochamadas no Chrome/Chromium, o volume do microfone diminui automaticamente, causando problemas de áudio.

### Solução
1. Abra o Chrome/Chromium e acesse: `chrome://flags/`
2. Procure pela configuração: **"Allow WebRTC to adjust the input volume"**
3. Altere de `Default` para `Disabled`
4. Reinicie o navegador

### Descrição da Flag
> Allow the Audio Processing Module in WebRTC to adjust the input volume during a real-time call. Disable if microphone muting or clipping issues are observed when the browser is running and used for a real-time call. This flag is experimental and may be removed at any time. – Mac, Windows, Linux

**Resultado:** O volume do microfone permanece fixo na configuração definida pelo usuário, sem ajustes automáticos durante as chamadas.

---

## 📚 Referências

- [Site oficial das extensões GNOME](https://extensions.gnome.org/)
- [Documentação do GNOME](https://help.gnome.org/users/gnome-help/stable/)
