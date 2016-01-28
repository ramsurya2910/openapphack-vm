
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
 
- Install few vagrant plugins

  a) auto_network
  
  **vagrant  plugin install vagrant-auto_network**
  
  b) hostsupdater
  
  **vagrant plugin install vagrant-hostsupdater**
  
  There are some bugs identified in the current vagrant version 1.8.1 which is expected to be fixed on 1.8.2 .
  
  
  To overcome you can copy the **ansible** directory from the github link below  and replace with the original 
  
    [Github mitchellh](https://github.com/mitchellh/vagrant/)   
  
   Then goto /plugins/provisioners/  copy the ansible directory and paste on vagrant paths

  
  If you are using Ubunbtu host the path would be /opt/vagrant/embedded/gems/gems/vagrant-1.8.1/plugins/provisioners/
  
  If its windows 8 host path would be Drive:\HashiCorp\Vagrant\embedded\gems\gems\vagrant-1.8.1\plugins\provisioners
  

- Run **vagrant up**

You should now have ansible start doing the basic provisioning for you.

- Run vagrant provision

re-run vagrant provision command few more times, i.e  if ansible throws up any messages that requires your attention and you successfully resolve them .


Make changes in the following files as required.

 -config.yml // top level configuration file

 -openapphack.generateapp.yml // has instructions to generate app

 -openapphack.installapp.yml  // has instructions to install app

 -openapphack.runapp.yml  // has instructions to run your app



Few more Levelup to get yoeman to start doing the automatic scaffolding for you on the openapphack-vm:

**Level 1**:

Install yoeman

i.e npm install -g yo

Update the same as generator_instructions in  openapphack.generateapp.yml or

Write your ansible role to do the same.

**Level 2**:

Install your specific generators

npm install -g generator-{give-your-generator-name} ( this can be any one of the generators from the list of generators mentioned in openapphack-yoeman-generators repo e.g. npm install -g generator-patternlab)

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

if you are facing any challenge with getting started with the openhack-vm please refer to the [issues](https://github.com/WiproOpenSourcePractice/openapphack-vm/issues) 
