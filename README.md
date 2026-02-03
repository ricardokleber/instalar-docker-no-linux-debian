<img width="830" height="237" src="https://github.com/user-attachments/assets/c672818d-c6fa-49d5-9672-c8cb19621590" />

***

## Em um Sistema Linux Debian
### 1. Apague eventuais versões anteriores do Docker

`apt update`

`apt remove docker docker-engine docker.io containerd runc`

### 2. Instale os pacotes e dependências necessários para o apt utilizar os repositórios via HTTPS:

`apt install ca-certificates curl gnupg lsb-release`

### 3. Adicione a chave GPG oficial do Docker:

`install -m 0755 -d /etc/apt/keyrings`

`curl -fsSL https://download.docker.com/linux/debian/gpg | gpg --dearmor -o /etc/apt/keyrings/docker.gpg`

### 4. Configure o repositório de acordo com sua distribuição e arquitetura:
`echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | tee /etc/apt/sources.list.d/docker.list > /dev/null`

### 5. Atualize novamente a lista de pacotes do repositório e instale os pacotes necessários:

`apt update`

`apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin`

### 6. Verifique se deu tudo certo exibindo o status do serviço Docker, a versão do Docker e do Docker Compose:

`systemctl status docker`

`docker –-version`

`docker compose version`

### Dica Extra (bastante utilizada em Sistemas que utilizam Docker)

Para não precisar utilizar o docker sempre como root, dê permissões de iniciar, parar e manipular contêineres a usuários comuns específicos:

`usermod -aG docker usuario_comum`


***
## Veja o Vídeo com o Tutorial na Prática no Youtube:
<a href="https://www.youtube.com/watch?v=jDQB2hnmlAQ" target="_blank"><img width="400" height="120" alt="assistavideo" src="https://github.com/user-attachments/assets/c3ceb2d8-daba-4864-9613-15aebf301423" /></a>

