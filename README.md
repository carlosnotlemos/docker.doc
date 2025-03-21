# docker.doc 
Documentação Docker MYSQL 5.7 ~ FEDORA SO
<p align="left">
    <a href="#">
        <img 
            alt="Docker" 
            title="Docker"
            width="60px" 
            style="padding-right: 10px;" 
            src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/docker/docker-original-wordmark.svg"
        />
    </a>
    <a href="#">
        <img 
            alt="MySQL" 
            title="MySQL"
            width="60px" 
            style="padding-right: 10px;" 
            src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/mysql/mysql-original-wordmark.svg"
        />
    </a>
    <a href="#" >
        <img 
            alt="Fedora" 
            title="Fedora"
            width="60px" 
            style="padding-right: 10px;" 
            src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/fedora/fedora-original.svg"
        />
    </a>
</p>

# SO:     Fedora Server - Conexão
# ip:     192.168.20.11
# ssh:    mondrian
# senha:  rhfdjz9283

---------------------------------------------
#    INSTALAÇÃO DOCKER NA MAQUINA FEDORA

**IMPORTANTE: Verifique atualizações na maquina....**

**Adicione o repositório oficial do Docker:**
```bash
$ sudo dnf config-manager --add-repo https://download.docker.com/linux/fedora/docker-ce.repo
```
**Instale o Docker:**
```bash
$ sudo dnf install docker-ce docker-ce-cli containerd.io
```
**Habilite o Docker para iniciar automaticamente na inicialização:**
```bash
$ sudo systemctl enable docker
```
**Verifique se o Docker está funcionando corretamente:**
```bash
$ sudo docker --version
```
**Adicionar Sudo ao docker:**
```bash
$ sudo usermod -aG docker $USER
```
-------------------------------------------
#    REINICIE A MAQUINA APARTIR DAQUI

**Verifique se está funcionando:**
```bash
$ docker run hello-world
###Obs: Digite sem sudo
```
**Baixar imagem do MySQL 5.7:**
```bash
$ docker pull mysql:5.7
```
**Instruções para criação da imagem:**
```bash
$ docker run --name mysql-5.7-server -e MYSQL_ROOT_PASSWORD=rootpassword -e MYSQL_DATABASE=cerice -p 3306:3306 -d mysql:5.7
```
**Verifique se o Container está rodando:**
```bash
$ docker ps
###Obs: Se o campo do console estiver vazio, digite: docker ps -a
```
**!!! Processo Finalizado...**

--------------------------------------------
#    OBSERVAÇÕES FINAIS

Verificações:

# -1	Verificar se docker está iniciando junto da inicialização do computador

# -2 	Verificar como está a utilização de memoria e configurações basicas do docker de acordo com a utilização do sistema.

Implementações:

**-1**	Implementar atualização do log em tempo real no fedora/docker.
!! se possivel que esse arquivo fique salvo dentro do banco cerice ou do MYSQL para ficar acessível.

**-2** 	Implementar privilegios root para todos os usuarios da rede , independente do IP , verificar com Magno se isso é pertinente.
```bash
$ GRANT ALL PRIVILEGES ON *.* TO 'root'@'192.168.%' IDENTIFIED BY 'rootpassword' WITH GRANT OPTION;
$ FLUSH PRIVILEGES;
```
-------------------------------------------
#   APLICAÇÕES PARA VERIFICAÇÕES


MAQUINA FEDORA(SERVER)
**-BASHTOP
-VIM
-MYSQL(opicional)**
