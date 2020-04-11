https://www.linuxuprising.com/2018/04/install-oracle-java-10-in-ubuntu-or.html


sudo add-apt-repository ppa:linuxuprising/java
sudo apt update
sudo apt install oracle-java10-installer

sudo apt install oracle-java10-set-default

# BETTER...
https://stackoverflow.com/questions/49507160/how-to-install-jdk-10-under-ubuntu

download Sun JDK

tar xzvf jdk-10.0.1_linux-x64_bin.tar.gz 
sudo mv jdk-10.0.1 /usr/lib/jvm

sudo update-alternatives --install /usr/bin/java java /usr/lib/jvm/jdk-10.0.1/bin/java 1
sudo update-alternatives --install /usr/bin/javac javac /usr/lib/jvm/jdk-10.0.1/bin/javac 1


select...
sudo update-alternatives --config java
sudo update-alternatives --config javac

test
java --version
javac --version

GOTCHAS
check JAVA_HOME settings - maven seems to work better without this set

/etc/profile.d/jdk.csh:setenv JAVA_HOME /usr/lib/jvm/java-10-oracle
/etc/profile.d/jdk.sh:export JAVA_HOME=/usr/lib/jvm/java-10-oracle

JAVA_HOME on Linux (Ubuntu) should be set in /etc/environment

