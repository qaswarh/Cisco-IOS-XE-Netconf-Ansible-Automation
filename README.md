# IOS-XE-on-CSR
If you've intenet then explore [Cisco IOS XE on CSR](https://devnetsandbox.cisco.com/RM/Diagram/Index/7b4d4209-a17c-4bc3-9b38-f15184e53a94?diagramType=Topology) config with Netconf<br>
All you need a Linux Box (ADM Server aka Jump Server) with Python, Netconf and Ansible installed<br>
Install WSL to experience from Windows machine<br>

Play nciosxe_getconfig.yml:<br> 
ansible-playbook -i sbx-ao -e secret=secret.var nciosxe_getconfig.yml --tags tags<br>

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

