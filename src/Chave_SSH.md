#Configurar Chave SSH na máquina e na conta do github:

Acessar o terminal linux ou o app do linux no windows e executar:

ssh-keygen -t ed25519 -C "seu e-mail entre aspas"
git config --global user.name "seu nome completo entre aspas"
git config --global user.email "Seu e-mail entre aspas"
cat ~/.ssh/id_ed25519.pub