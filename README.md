<p align="center">
  <a href="" rel="noopener">
 <img width=200px height=200px src="https://camo.githubusercontent.com/1b8997f4597a4d3f1cfa29863e6ad766a8cab1fd7810f77aa7dc77811b7c327c/68747470733a2f2f63646e2e7261776769742e636f6d2f72616661656c73747a2f6d6167656e746f322d736e6970706574732d76697375616c73747564696f2f6d61737465722f696d616765732f69636f6e2e706e67" alt="Project logo"></a>
</p>

<h3 align="center">Magento 2 Docker</h3>



---

<p align="center"> Magento:2.4 +PHP:7.3 +MariaDB:10.2 +ElasticSearch:6
    <br> 
</p>



## 🧐 Sobre <a name = "about"></a>

Repositório padrão de Magento 2 e suas principais dependências para funcionamento.



## 🏁 Getting Started <a name = "getting_started"></a>


### 📝 Requisitos

Para o funcionamento deste repositório será necessário alguns requisitos e dependências instaladas.


- [Docker](https://www.docker.com/)
- [Composer](https://getcomposer.org/download/)
- [Magento Authentication Keys](https://devdocs.magento.com/guides/v2.4/install-gde/prereq/connect-auth.html)


### 🔧 Passo a passo

Os passos para instalação e funcionamento do repositório:


1 - Clonar repositório

```
git clone git@github.com:sidinei-silva/magento-docker.git
```

2 - Instalar bibliotecas vias composer 

```
composer install 
```

3 - Criar containers do docker

```
docker-compose -d up
```

4 - Entrar no container magento_web

```
docker exec -it magento_web bash
```
---

<span style="color:orange;">Obs: Caso tenho alterado o nome do container do service web em docker-compose.yml inserir o nome do mesmo no comando:</span>

```
docker exec -it {{nome_do_container}} bash
```
---

5 - Entrar na pasta da aplicação dentro do container

```
cd app/
```

6 - <span style="color:orange;">(Opcional)</span> Executar comando de dados de exemplos no magento

```
php bin/magento sampledata:deploy
```
<small style="color:orange;">Obs: Este comando cadastra produtos e dados fictícios no projeto, caso queira inserir manualmente não recomendado!!</small>

7 - Inserir username

    Colar key public em username 

8 - Inserir password

    Colar key private em password

9 - Executar comando de setup do magento

```
php bin/magento setup:install \
--admin-firstname=John \
--admin-lastname=Doe \
--admin-email=johndoe@example.com \
--admin-user=admin \
--admin-password='admin123' \
--base-url=http://localhost \
--backend-frontname=admin \
--db-host=mysql \
--db-name=magento \
--db-user=root \
--db-password=root \
--search-engine=elasticsearch6 \
--elasticsearch-host=elasticsearch \
--elasticsearch-port=9200
--use-rewrites=1 \
--language=pt_BR \
--currency=BRL \
--timezone=America/Sao_Paulo \
--use-sample-data
```
<small style="color:orange;">Obs: Altere as informações conforme a necessidade este comando foi testado da seguinte forma, qualquer alteração verificar se esta correta. Nome dos host esta sendo usado o nome do service no docker compose, não alterar!!</small>

8 - Acesse: [http://localhost](http://localhost)

    ### Parabéns! 🎈
---

## Painéis

**Site:** http://localhost/

**Admin Magento:** http://localhost/admin

**PHPMyAdmin:** http://localhost:8080

---
## Senha admin default

**Username:** admin

**Senha:** admin123

---

## 🔧 Problemas comuns encontrados <a name = "painels"></a>

Alguns problemas que foram encontrados. 


### Container Elasticsearch

1 - Invalid kernel settings. Elasticsearch requires at least: vm.max_map_count = 262144
#### **Solução**
Linux:
```
sudo sysctl -w vm.max_map_count=262144
```
---

## ⛏️ Imagens Utilizadas <a name = "built_using"></a>

- [webdevops/php-apache-dev:7.3](https://hub.docker.com/r/webdevops/php-apache-dev) 
- [mariadb:10.2](https://hub.docker.com/_/mariadb)
- [docker.io/bitnami/elasticsearch:6](https://hub.docker.com/r/bitnami/elasticsearch)


## ✍️ Authors <a name = "authors"></a>

- [@sidinei-silva](https://github.com/sidinei-silva)

See also the list of [contributors](https://github.com/kylelobo/The-Documentation-Compendium/contributors) who participated in this project.


## 🎉 Reconhecimentos <a name = "acknowledgement"></a>

- Inspirado na publicação de
[magemodule](https://www.magemodule.com/all-things-magento/magento-2-tutorials/docker-magento-2-development/#install-magento) 
- Baseado em [Bitnami Magento](https://bitnami.com/stack/magento)  

