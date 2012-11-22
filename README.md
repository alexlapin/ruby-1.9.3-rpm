ruby-1.9.3-rpm
==============

Create rpm for ruby 1.9.3-p327

    yum install -y rpm-build rpmdevtools
    rpmdev-setuptree
    cd ~/rpmbuild/SOURCES
    wget http://ftp.ruby-lang.org/pub/ruby/1.9/ruby-1.9.3-p327.tar.gz
    cd ~/rpmbuild/SPECS