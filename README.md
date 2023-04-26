# Cisco IOS-XE Netconf with Ansible
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

![ncapphosting1](https://user-images.githubusercontent.com/47313728/234462886-dea5f231-98c9-48e0-b157-3f32fabc3329.png)

Create j2 templates like `apphosting.j2`, `netconfyang.j2`, `licensing.j2`, `interfaces.j2`, `nacm.j2` `routing.j2`, `acl.j2`, `network-instances.j2` etc.<br>
Create a playbook to convert j2 templates to Netconf templates with site-specific dictionary<br>
var env_file in the playbook gets dictonary and provide values for the keys in j2 templates<br>
Use nciosxe_editconfig.yml to edit/create configuration with Netconf<br>

With no change of data, the idempotancy example for the output of<br>
ansible-playbook -i csr8000v -e secret=secret.var nciosxe_editconfig.yml --tags app-hosting-cfg :<br>

![ncapphosting2](https://user-images.githubusercontent.com/47313728/234472290-1a9236e3-6666-447f-b25a-676055c2eb12.png)

The playbook registered the --get-config before and after --edit-config<br>
