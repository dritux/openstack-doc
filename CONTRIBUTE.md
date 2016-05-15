
#### Antes de contribuir é altamente recomendado a leitura dos links abaixo:

* [How to contribute](https://wiki.openstack.org/wiki/How_To_Contribute)
* [Contribute - quick reference](http://docs.openstack.org/infra/manual/developers.html)
* [Git commit messages](https://wiki.openstack.org/wiki/GitCommitMessages)
* [Bug triage](https://wiki.openstack.org/wiki/BugTriage)
* [Bugs](https://wiki.openstack.org/wiki/Bugs)

---
## Dependências:

```
sudo apt-get install git  
sudo apt-get install git-review  
ou  
sudo pip install git-review==x.xx
```

## Contas a serem criadas:
* [review](https://review.openstack.org/)  
* [launchpad](https://launchpad.net/)



## Gerar chave ssh:
```
$ ssh-keygen -t rsa -b 4096 -C "example@site.com"
```
##Cadastrar ssh no gerrit:
```
$ cat ~/.ssh/id_rsa.pub
```
[ssh-keys](https://review.openstack.org/#/settings/ssh-keys)

##Gerar senha para o commit:

[http-password](https://review.openstack.org/#/settings/http-password)


##Clonar repositório que irá contribuir:
```
$ git clone https://git.openstack.org/openstack/<projectname>.git
```

##Configuração do git
```
$ cd <projectname>
$ git config --global user.name "Firstname Lastname"  
$ git config --global user.email "your_email@youremail.com"  
$ git config --global gitreview.username yourgerritusername  
$ git config --global --add gitreview.username "dritec"  
$ git config --global gitreview.scheme https  
$ git config --global gitreview.port 443  
```

```
Problemas com proxy? Pode ser necessário algumas configurações :)  
$ git config --global http.proxy http://ip:port  
$ git config --global https.proxy http://ip:port  
```

##Comandos úteis
```
$ git config --help  
$ git config --list  
$ git ls-remote  
```

##Sincronizar o repositório com o gerrit:
```
$ cd <projectname>
$ git review -s
```

Could not connect to gerrit.  
Enter your gerrit username: <b>yourgerritusername</b>

```
Nota:
- git review acessa via ssh pela porta 29418 por default. No entanto, se você suspeitar que a porta 29418 esteja bloqueada, deverá acessar via https.  

$ git remote add gerrit https://<username>@review.openstack.org/<umbrella repository name>/<repository name>.git  

- Se a configuração do git-review falhar, você pode remover o Git remoto a partir do comando abaixo e recriá-lo novamente:  

$ git remote rm gerrit
```

## Passos para fazer commit

####Criar branch

Criar a branch a partir do código do bug aberto no gerrit  
Ex: bug/codebug  #for bug fix  
```
$ git checkout -b bug/1475840  
```
####Add  
```
$ git add . 
```
####Commit
```
$ git commit # 50 chars and should not  end with a '.' .
```
#### Enviar para o revisão
```
$ git review
```

##Se precisar alterar novas mudanças. 

Para enviar a mesma mudança execute:
```
$ git commit -a --amend
```
##Enviar para o revisão
```
$ git review
```


Antes de começar a contribuir é aconselhavel "treinar" a contribuição no repositório sandbox e alinhar as dúvidas com a equipe:  
[doc sandbox](http://docs.openstack.org/infra/manual/sandbox.html)  

```
$ git clone https://github.com/openstack-dev/sandbox.git
$ git remote add gerrit https://dritec@review.openstack.org/openstack-dev/sandbox.git
```

## Referências 
<i>
http://docs.openstack.org/infra/manual/developers.html  
https://pypi.python.org/pypi/git-review
https://git-scm.com/docs/git-config
https://git-scm.com/docs/git-ls-remote.html 
</i>
