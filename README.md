RHEL/CentOS 5/6
==============

I use this spec to make rpm and install ruby 1.9.3-p327 to CentOS 5.5 x86_64

Important:
---
Please remove all other ruby 1.8.x versions from your system and packages (if you don't use rvm). Use <code>rpm -qa ruby*</code> to find old packages. When run <code>rpm -e</code> for every package from the list you got by find.

<b><h2>How to install ruby-1.9.3-rpm</h2></b>
Create rpm for ruby 1.9.3-p327

    yum install -y rpm-build rpmdevtools
    rpmdev-setuptree
    cd ~/rpmbuild/SOURCES
    wget http://ftp.ruby-lang.org/pub/ruby/1.9/ruby-1.9.3-p327.tar.gz
    cd ~/rpmbuild/SPECS
    wget https://raw.github.com/AlexLapin/ruby-1.9.3-rpm/master/ruby19.spec
    rpmbuild -bb ruby19.spec
    ARCH=`uname -m`
    rpm -Uvh ~/rpmbuild/RPMS/${ARCH}/ruby-1.9.3p327-1.${ARCH}.rpm
