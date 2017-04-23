# Distributed engine for IoT middleware
Distributed integration system using Akka Framework

## Initial setup

### Local setup
```
wget https://downloads.typesafe.com/typesafe-activator/1.3.12/typesafe-activator-1.3.12.zip
unzip typesafe-activator-1.3.12.zip
cd typesafe-activator-1.3.12/bin

# Initial setup
./activator

# Start the GUI (opens a tab in the browser to http://127.0.0.1:8888/home)
./activator ui
```

The GUI is web-based and locally hosted. It works really well for everything except code writing. You can build, run and test from this interface.

There are some tutorials that are nice to follow: Hello akka (java), akka-sample-cluster-java

### Openstack setup
Create 4 m1.small machines using the Ubuntu 16.04 Xenial image
The snapshot feature doesn't work so we have to configure each of them

```
sudo apt-get update
sudo apt-get install unzip openjdk-8-jdk
wget http://www.lightbend.com/activator/template/bundle/hello-akka
mv hello-akka hello-akka.zip
unzip hello-akka.zip
cd hello-akka/bin
./activator
```

Put this in ~/.ssh/config (on your fep account) to easily access each of them.
```
Host akka1
        User ubuntu
        Hostname 10.9.78.137
        IdentityFile ~/.ssh/openstack.key
Host akka2
        User ubuntu
        Hostname 10.9.78.136
        IdentityFile ~/.ssh/openstack.key
Host akka3
        User ubuntu
        Hostname 10.9.78.138
        IdentityFile ~/.ssh/openstack.key
Host akka4
        User ubuntu
        Hostname 10.9.78.110
        IdentityFile ~/.ssh/openstack.key
```
