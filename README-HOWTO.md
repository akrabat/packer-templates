# How to create base box

Read [Matt Wrock's article](http://www.hurryupandwait.io/blog/creating-windows-base-images-for-virtualbox-and-hyper-v-using-packer-boxstarter-and-vagrant).

## Create Base box:

    git clone git@github.com:akrabat/packer-templates.git
    git checkout rob-current
    cd cookbooks/packer-templates/
    berks vendor ../../vendor/cookbooks
    cd ../.. 
    packer build -force -only virtualbox-iso ./vbox-2016.json
    
If it builds, you end up with `windows2016min-virtualbox.box`

## Upload to Vagrant Cloud

Upload `windows2016min-virtualbox.box` somewhere (e.g. public S3 bucket) and then
create/update your [Vagrant Cloud](https://app.vagrantup.com) box.
