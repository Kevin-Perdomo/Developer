==========================================================================================================================================================================================

#Laravel-web_Site: https://laravel.com/

#Criando um projeto laravel completo com Docker:
//example-app pode ser qualquer nome_do_projeto
curl -s https://laravel.build/example-app | bash                            
cd example-app 

//subindo os containers
./vendor/bin/sail up 

//criando as tabelas do banco de dados
./vendor/bin/sail artisan migrate 

#Criando um Alias para rodar comandos sail:
ls -la
sudo nano .bachrc
// copiar o comando abaixo, colar e salvar dentro do arquivo.bachrc
alias sail='sh $([ -f sail ] && echo sail || echo vendor/bin/sail)'
or
alias sail='bash $PWD/vendor/bin/sail'

#Testando o Alias:
sail --help
sail up
sail up -d
sail stop   // Para os contêineres, mas mantém o estado, redes e volumes.
sail down   //Para os contêineres e remove as redes, volumes e outros recursos associados.

==========================================================================================================================================================================================

#Testando o servidor Apache (para evitar conflitos)
sudo lsof -i :80
sudo service apache2 stop

==========================================================================================================================================================================================

#Testando Artisan:
php artisan --help
sail php artisan make:controller Name_Controller
php artisan route:list --help
php artisan route:list -v
php artisan route:list

==========================================================================================================================================================================================

#Rodando em uma nova maquina a patir de um git-clone

//Laravel-sail é um orquestrador de docker compose, ou seja, ele ajuda a subir e controlar os contêineres do projeto laravel.
//A pasta vendor do projeto laravel está listado no arquivo .gitignore por padrão, ou seja, não é versionado e não consta no projeto que clonei.
//A documentação (https://laravel.com/docs/11.x/sail#introduction) fala sobre um comando que deve ser executado na pasta do projeto recém clonado 
//em uma nova máquina para que passe a ter novamente os comandos 'sail' (com o alias) disponíveis no ambiente local (fora dos contêineres):

cd <pasta do projeto>
docker run --rm \
    -u "$(id -u):$(id -g)" \
    -v "$(pwd):/var/www/html" \
    -w /var/www/html \
    laravelsail/php83-composer:latest \
    composer install --ignore-platform-reqs

//Sobre as variáveis de ambiente que sentimos falta na hora de executar docker compose up:
//devemos deixar os comandos de docker compose de lado e usar sempre o comando sail, pois o arquivo vendor/laravel/sail/bin/sail tem variáveis
//de ambiente como WWWUSER e WWWGROUP que são usados pelos contêineres.
//Por isso, as linhas do docker compose que contém WWWGROUP e WWWUSER devem ser mantidas em suas versões originais.

//Precisei usar esse comando para prosseguir com o setup em minha máquina:
sail build
sail php artisan key:generate

//Precisei alterar as variáveis de ambiente no arquivo .env para o banco de dados. Ele usaria sqlite, mas configurei pra usar o mysql:
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=sail
DB_PASSWORD=password

//Resolvendo conflito de volume do container mysql
docker volume ls  
docker volume rm laravel_docker_sail-mysql  

//Depois executei:
sail up  
sail php artisan config:cache     //não sei se precisava
sail php artisan config:clear     //não sei se precisava
sail php artisan migrate          //carga inicial da base de dados
sail php artisan migrate:status   //lista que as migrações foram executadas

//e consegui acessar a página inicial do projeto 🥲

==========================================================================================================================================================================================
