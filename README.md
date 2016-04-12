# ansible-splash

Ansible role to install splash based on the official splash docker provisioning scripts mentioned in http://splash.readthedocs.org/en/latest/index.html

Installing splash using ansible :
--------------------------------------------------
    $ansible-playbook splash_play.yml -vvvv'



Installing splash using vagrant:
-----------------------------
    $vagrant up
    Accessing splash using http://localhost/7000
    The vagrant also has an ip 192.168.33.70


More info
-------------------------------------------------------------------
    - Testing on Ubuntu 14.04 and MacOSX - EL captain
    - The role is associated with a sample play book.. all you need to do is adding the role to you project
    - Feel free to ask me any question or create issues and i'll fix it


TODO
------------------------------------------------------------------
    - Using docker in addition to vagrant
    - Make sure that the role compile sip and qt5 only when there's new version needed
    - Adding unit tests
