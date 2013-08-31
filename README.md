# my-dev-host

setup vagrant machine for me.

## Usage

```
# see https://github.com/opscode/bento
vagrant box add opscode-centos-6.4 https://opscode-vm-bento.s3.amazonaws.com/vagrant/opscode_centos-6.4_provisionerless.box

git clone https://github.com/takus/my-dev-host

cd my-dev-host
berks install --path vendor/bundle
vagrant up
```
