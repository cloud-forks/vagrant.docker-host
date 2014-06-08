# Custom Vagrant Docker-Host

Vagrant uses a dedicated VM running Docker on operating systems like Windows and OSX because they're unable to run
Docker natively. The Docker host VM runs `boot2docker` by default but Vagrant provides a configuration option called
`vagrant_vagrantfile` which allows for setting a Vagrantfile defining custom VM configurations.

This project defines a custom Vagrantfile which can be used as a replacement for the default Docker host configuration.
