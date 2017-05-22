**Flask demo-app ansible**
----------------------
An ansible playbook to deploy demo-app.

**Requirements**
------------
 - Ansible
 - Vagrant
 - Virtualbox

**Installation**
------------
Download the repo in your target directory and unzip it. Then move to the folder containing our Vagrantfile and type

    vagrant up

This will create a new virtual machine in virtualbox.

Once this is done  type

    ansible -m ping -i hosts all

As is our first time connecting to the virtual machine you will see a message saying that the authenticity of host 'xxx.xxx.xxx.xxx(xxx.xxx.xxx.xxx)' can't be established and asking you if you want to continue. Type yes.

If all is working correctly you will see the following output:

    demo-app | SUCCESS => {
        "changed": false, 
        "ping": "pong"
    }

Now we can procceed to deploy our demo-app application with the following command:

    ansible-playbook -i hosts playbook.yml

If you see the following output

    PLAY RECAP *********************************************************************
    demo-app                   : ok=16   changed=15   unreachable=0    failed=0

demo-app has been successfully deployed.

**Usage**
-----
Navigate to [192.168.33.14](http://192.168.33.14) or [192.168.33.14/api](http://192.168.33.14/api) and you will see our demo-app application.

**Important**
---------
Don't forget to close the virtual machine once you finished testing the application by typing

    vagrant halt
