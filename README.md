# IOS-XE-on-CSR
If you've intenet then explore [Cisco IOS XE on CSR](https://devnetsandbox.cisco.com/RM/Diagram/Index/7b4d4209-a17c-4bc3-9b38-f15184e53a94?diagramType=Topology) config with Netconf<br>
All you need a Linux Box (ADM Server aka Jump Server) with Python, Netconf and Ansible installed<br>
Install WSL to experience from Windows machine<br>

Play nciosxe_getconfig.yml:<br> 
ansible-playbook -i csr8000v -e secret=secret.var nciosxe_getconfig.yml --tags tags<br>

with following tags:<br>

--tags app-hosting<br>
--tags native<br>
--tags netconf-yang<br>
--tags licensing<br>
--tags interfaces<br>
--tags nacm<br>
--tags routing<br>
--tags acl<br>
--tags network-instances<br>
--tags running<br>

As an example the output of<br>
ansible-playbook -i csr8000v -e secret=secret.var nciosxe_getconfig.yml --tags app-hosting :<br>

![ncapphosting](https://user-images.githubusercontent.com/47313728/234462886-dea5f231-98c9-48e0-b157-3f32fabc3329.png)



