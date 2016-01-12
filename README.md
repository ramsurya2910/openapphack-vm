

How to make use of this openapphack-vm  :

- Install vagrant 1.8 +

- Install vagrant plugins

  a) auto_network
  b) hostsupdater

- Run vagrant up

You should now have ansible start doing the basic provisioning for you.

Make changes in the config to get yoeman to start doing the automatic scaffolding for you.

Few more Levelup :

Level 1:

Use an ansible role to install yoeman

i.e npm install -g yo

Level 2:

Use an ansible role to install your specific generators

e.g npm install -g generator-patternlab

Get your ansible role to do the following as well

Level 3:

Type $ yo patternlab
and answer a few questions about your project.

When it's done, type
$ grunt

to generate your first Pattern Lab build…
…and

$ grunt watch

to start the watcher.

Now you should have your fully scaffolded site!
