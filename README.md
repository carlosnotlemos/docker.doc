# docker.doc 
Documentação Docker MYSQL 5.7 ~ FEDORA SO
<p align="left">
    <a href="https://www.instagram.com/carlim_11">
        <img 
            alt="Perfil do instagram" 
            title="Instagram" 
            src="https://skillicons.dev/icons?i=instagram"
        />
    </a>
    <a href="https://www.linkedin.com/in/carlos-henrique-b33b78191">
        <img 
            alt="Perfil do linkedin" 
            title="Linkedin" 
            src="https://skillicons.dev/icons?i=linkedin"
        />
    </a>
    <a href="https://github.com/login?return_to=https%3A%2F%2Fgithub.com%2Fcarlosnotlemos" >
        <img 
            alt="Perfil do GitHub" 
            title="GitHub" 
            src="https://skillicons.dev/icons?i=github"
        />
    </a>
</p>

# SO:     Fedora Server - Conexão
# ip:     192.168.20.11
# ssh:    mondrian
# senha:  rhfdjz9283

---------------------------------------------
#    INSTALAÇÃO DOCKER NA MAQUINA FEDORA

-1	IMPORTANTE: Verifique atualizações na maquina....

-1.2	Adicione o repositório oficial do Docker:
```bash
$ sudo dnf config-manager --add-repo https://download.docker.com/linux/fedora/docker-ce.repo
```
-2	Instale o Docker:
```bash
$ sudo dnf install docker-ce docker-ce-cli containerd.io
```
-3	Habilite o Docker para iniciar automaticamente na inicialização:
```bash
$ sudo systemctl enable docker
```
-4	Verifique se o Docker está funcionando corretamente:
```bash
$ sudo docker --version
```
-5	Adicionar Sudo ao docker:
```bash
$ sudo usermod -aG docker $USER
```
-------------------------------------------
#    REINICIE A MAQUINA APARTIR DAQUI

-1	Verifique se está funcionando:
```bash
$ docker run hello-world     (obs: sem sudo)
```
-2	Baixar imagem do MySQL 5.7:
```bash
$ docker pull mysql:5.7
```
-3	Instruções para criação da imagem:
```bash
$ docker run --name mysql-5.7-server -e MYSQL_ROOT_PASSWORD=rootpassword -e MYSQL_DATABASE=cerice -p 3306:3306 -d mysql:5.7
```
-4 	Verifique se o Container está rodando:
```bash
$ docker ps		(obs: Se campo vazio, digite docker ps -a)
```
!!! Processo Finalizado...

--------------------------------------------
#    OBSERVAÇÕES FINAIS

Verificações:

-1	Verificar se docker está iniciando junto da inicialização do computador

-2 	Verificar como está a utilização de memoria e configurações basicas do docker de acordo com a utilização do sistema.

Implementações:

-1	Implementar atualização do log em tempo real no fedora/docker.
!! se possivel que esse arquivo fique salvo dentro do banco cerice ou do MYSQL para ficar acessível.

-2 	Implementar privilegios root para todos os usuarios da rede , independente do IP , verificar com Magno se isso é pertinente.
$ GRANT ALL PRIVILEGES ON *.* TO 'root'@'192.168.%' IDENTIFIED BY 'rootpassword' WITH GRANT OPTION;
$ FLUSH PRIVILEGES;

-------------------------------------------
#   APLICAÇÕES PARA VERIFICAÇÕES


MAQUINA FEDORA(SERVER)
-HTOP
-VIM
-MYSQL(opicional)
