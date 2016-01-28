
### openapphack-vm (a.k.a your openapphack project when you fork it!!).

This is the main repository for the openapphack project. 

openapphack project is also used interchangable to refer to an openapphack-vm fork on which you are doing your openapphack vm customization.

To know more about the openapphack project please visit this [wiki](https://github.com/WiproOpenSourcePractice/openapphack/wiki)



How to take **openapphack-vm** for a spin :

You start by :

- Fork openapphack-vm

- Install ansible and execute 
  
  sudo ansible-galaxy install -r ./provisioning/requirements.yml 

  while in the openapphack-vm folder

- Installing vagrant 1.8 +

- Install nfs server on Ubuntu

- Install few vagrant plugins

  a) auto_network
  
  ```sh
  **vagrant  plugin install vagrant-auto_network**
  
  ```
  
  b) hostsupdater
  
  ```sh
  **vagrant plugin install vagrant-hostsupdater**
  
  ```
  
  There are some bugs identified in the current vagrant version 1.8.1 which is expected to be fixed on 1.8.2 .
  
  
  To overcome you can copy the **ansible** directory from the github link below 
  
    [Github mitchellh](https://github.com/mitchellh/vagrant/)   ; Download or clone it 
  
   Then goto vagrant-master/plugins/provisioners/  copy the ansible directory and paste on vagrant path

  
  If you are using Ubunbtu host the path would be /opt/vagrant/embedded/gems/gems/vagrant-1.8.1/plugins/provisioners/
  
  If its windows 8 host path would be Drive:\HashiCorp\Vagrant\embedded\gems\gems\vagrant-1.8.1\plugins\provisioners
  
```sh
- Run **vagrant up**   ( GitBash.exe run as Administrator on Windows ) 

```

You should now have ansible start doing the basic provisioning for you.

```sh
- Run **vagrant provision**

```

re-run vagrant provision command few more times, i.e  if ansible throws up any messages that requires your attention and you successfully resolve them .


Make changes in the following files as required.

```sh

 -config.yml // top level configuration file

 -openapphack.generateapp.yml // has instructions to generate app

 -openapphack.installapp.yml  // has instructions to install app

 -openapphack.runapp.yml  // has instructions to run your app

```


Few more Levelup to get yoeman to start doing the automatic scaffolding for you on the openapphack-vm:

**Level 1**:

Install yoeman

```sh 

npm install -g yo

```

Update the same as generator_instructions in  openapphack.generateapp.yml 

or  

alternatively make use of the openapphack.nodejs ansible role and install global nodejs package by declaring the same in config.yml 

i.e make the following change in config.yml

```yml
# `nodejs` must be in installed_extras for this to work.
nodejs_version: "4.2"
nodejs_npm_global_packages:
  - name: yo
  - name: bower
  - name: grunt-cli
```


**Level 2**:

Install your specific generators or pick up one of the available published yoeman generators and customize it to work with openapphack-vm.

( this can be any one of the generators from the list of generators mentioned in openapphack-yoeman-generators repo e.g. npm install -g generator-patternlab)

```sh
npm install -g generator-{give-your-generator-name} 

```

Update the same as generator_instructions in  openapphack.generateapp.yml or

Write your ansible role to do the same.

**Level 3**:

Log on to the vm https://openapphackvm.dev:4200/ as

 user : vagrant
 password : vagrant

navigate to /var/www/path_to_your_app

Type $ yo {your-generator-name}
and answer a few questions about your project.

When it's done, type
$ grunt

to generate your first build…

…and

$ grunt watch

to start the watcher.

Now you should have your fully scaffolded site!


*You can also use gulp or another build tool depending on the technology context*

*You will have to install the neccessary ansible role and notify the same with a pull request to openapphack-ansible-roles repo*


**Level 4** :

Automate all you did in level 3 :)

.. All the best..

**Level 5**

When everything works for you.. submit a pull request to openapphack-vm repo using the pullrequest template and details of your openapphack-vm fork.

After your openapphack-vm is validated please find your fork added to submitted openapphack projects.

if you are facing any challenge with getting started with the openapphack-vm please refer to the [issues](https://github.com/WiproOpenSourcePractice/openapphack-vm/issues) 
