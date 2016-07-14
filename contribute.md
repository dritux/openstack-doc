==================
Documentação de contribuição
==================

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

Example message commit:

```
modified condition variable project_choices

the error was in condition "if > 1", which was allowing
the default value only when the list had two or more values.

Change-Id: If2ce5a5a3cb5f6411df0c023a818f20fa2130768
Closes-Bug: #1602903
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

## Considerações importantes

**Bug Status:**

* **New** - Recently logged by a non-triaging person.
* **Incomplete** - Needs additional information before it can be triaged.
* **Opinion** - Does not fit the project but can still be discussed.
* **Invalid** - Not an issue for docs.
* **Won't Fix** - Documentation fixes won't fix the issue.
* **Confirmed** - Acknowledged that it is a documentation bug.
* **Triaged** - Comments in the bug indicate its scope and amount of work to
  be done.
* **In Progress** - Someone is working on it.
* **Fix Committed** - A fix is in the repository; Gerrit sets this
  automatically. Do not set this manually.
* **Fix Released** - A fix is published to the site.

**Bug Importance:**

* **Critical** - Data will be lost if this bug stays in; or it is so bad that
  we are better off fixing it than dealing with all the incoming questions
  about it. Also items on the website itself that prevent access are Critical
  doc bugs.
* **High** - Definitely need docs about this or a fix to current docs; docs are
  incomplete without this. Work on these first if possible.
* **Medium** - Need docs about this within a six-month release timeframe.
* **Low** - Docs are fine without this but could be enhanced by fixing this
  bug.
* **Wishlist** - Not really a bug but a welcome change. If something is wrong
  with the doc, mark the bug as Low rather than Wishlist.
* **Undecided** - Recently logged by a non-triaging person or requires more
  research before deciding its importance.


Tags for doc bugs
-----------------
É importante selecionar uma tag, para dar mais visibilidade ao bug.

Exemplo:  

* **low-hanging-fruit** for documentaion bugs that are straightforward to fix.
  If you are a newcomer, this is a way to start.

* **sec guide**, **install guide**, **ops-guide**, and other for specific
  guides.

* **doc-builds** for documentation bugs that are in the documentation build
  tool chain, such as the Sphinx theme, openstackdocstheme.


## Referências 
<i>
http://docs.openstack.org/infra/manual/developers.html   
https://pypi.python.org/pypi/git-review  
https://git-scm.com/docs/git-config  
https://git-scm.com/docs/git-ls-remote.html  
</i>
