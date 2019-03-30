# Ansible playbook: KVM
An Ansible playbook to setting up a KVM on Ubuntu (tested on 18.04).

## Requirements
* SSH Keys on the local machine.
* Ansible 2.7+ on your local machine.
* Mkpassword on your local machine.
* Remote machine with the [Ubuntu server 18.04](http://cdimage.ubuntu.com/releases/18.04.2/release/) installed.
* Non-root sudo user with SSH Key-Based Authentication your remote machine.


> Note: For managing KVM virtual machines using `virt-manager` (a graphical utility for managing KVM virtual machines), you will need a linux desktop workstation, or linux desktop VM running on your Windows or MacOS workstation. Or, you can manage VMs via the command line which is not recommended.
> .
To use `virt-manager`, install the following packages on your Linux desktop wokrstation:
`sudo apt install ssh-askpass virt-manager`. See [man pages](https://virt-manager.org/screenshots/) for more informations.

## Usage
1. Clone this repository.
    ```
    git clone https://github.com/rastoelias/ansible-kvm.git ansible-kvm
    ```
2. Copy the `hosts.example` file to the `hosts` file.
    ```
    cp hosts.example hosts
    ```
3. Open the `hosts` file and replace `SERVER-IP-ADDRESS` with the public IP address of your server.
    ```
    [server]
    111.111.111.111
    ```
4. Copy the `config.example.yml` to the `config.yml` file.
    ```
    cp config.example.yml config.yml
    ```
5. Open the `config.yml` file, make desired changes and save changes.
6. Run playbook
    ```
    ansible-playbook provision.yml -u USER --become -K -e ansible_port=PORT
    ```
