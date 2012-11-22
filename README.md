ruby-1.9.3-rpm
==============

Create rpm for ruby 1.9.3-p327

    yum install -y rpm-build rpmdevtools
    rpmdev-setuptree
    cd ~/rpmbuild/SOURCES
    wget http://ftp.ruby-lang.org/pub/ruby/1.9/ruby-1.9.3-p327.tar.gz
    cd ~/rpmbuild/SPECS
    wget https://raw.github.com/AlexLapin/ruby-1.9.3-rpm/master/ruby19.spec
    rpmbuild -bb ruby19.spec
    ARCH=`uname -m`
    KERNEL_REL=`uname -r`
    KERNEL_TMP=${KERNEL_REL%.$ARCH}
    DISTRIB=${KERNEL_TMP##*.}
    rpm -Uvh ~/rpmbuild/RPMS/${ARCH}/ruby-1.9.3p327-1.${DISTRIB}.${ARCH}.rpm