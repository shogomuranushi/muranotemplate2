UserData on EC2 add the this code.

    #!/bin/sh
    yum update -y
    yum install epel-release -y
    yum install gcc python-devel python-crypto python-pip git -y
    easy_install pip
    pip install ansible
    cd ~
    git clone https://github.com/shogomuranushi/muranotemplate2.git
    ansible-playbook muranotemplate2/ansible/main.yml
    # Remove the comment, if necessary.
    # ansible-playbook muranotemplate2/ansible/nrpe.yml --extra-vars "nagiosserver=,11.22.33.44"

    # ansible-playbook muranotemplate2/ansible/apache.yml
    # cat <<EOF > muranotemplate2/ansible/roles/apache/vars/main.yml
    # site:
    #  - { domain: "www.test1.com", owner: "root" }
    #  - { domain: "www.test2.co.jp", owner: "apache" }
    # EOF

    # ansible-playbook muranotemplate2/ansible/php.yml
    # ansible-playbook playbook/vsftpd.yml --extra-vars "eip=22.33.44.55"
    ansible-playbook muranotemplate2/ansible/selenux-desable.yml
