# Docker for symfony

## Update variables for your project 

```bash
cp docker/.env.local docker/.env
```

## Launch containers 

```bash
cd docker
docker compose up -d 
```

## Get in the php container to use symfony cli

```bash
docker composer exec -it name_of_project_defined_in_env_file-php bash
php -v
composer -V
symfony help
```
