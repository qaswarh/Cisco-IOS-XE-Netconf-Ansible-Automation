# IOS-XE-on-CSR
If you've intenet then explore [Cisco IOS XE on CSR](https://devnetsandbox.cisco.com/RM/Diagram/Index/7b4d4209-a17c-4bc3-9b38-f15184e53a94?diagramType=Topology) config with Netconf<br>
All you need a Linux Box (ADM Server aka Jump Server) with Python, Netconf and Ansible installed<br>
Install WSL to experience from Windows machine<br>

Play nciosxe_getconfig.yml:<br> 
ansible-playbook -i sbx-ao -e secret=secret.var nciosxe_getconfig.yml --tags tags<br>

with following tags:<br>

--tags app-hosting<br>
--tags native, <br>
--tags netconf-yang<br>
--tags licensing<br>
--tags interfaces<br>
--tags nacm<br>
--tags routing<br>
--tags acl<br>
--tags network-instances<br>
--tags running<br>

ok: [localhost] => {<br>
    "result.stdout_lines": [{<br>
        "  <data xmlns=\"urn:ietf:params:xml:ns:netconf:base:1.0\" xmlns:nc=\"urn:ietf:params:xml:ns:netconf:base:1.0\">",{<br>
        "  <app-hosting-cfg-data xmlns=\"http://cisco.com/ns/yang/Cisco-IOS-XE-app-hosting-cfg\">",{<br>
        "    <apps>",{<br>
        "      <app>",{<br>
        "        <application-name>guestshell</application-name>",{<br>
        "        <application-network-resource>",{<br>
        "          <vnic-gateway-0>0</vnic-gateway-0>",{<br>
        "          <virtualportgroup-guest-interface-name-1>0</virtualportgroup-guest-interface-name-1>",{<br>
        "          <virtualportgroup-guest-ip-address-1>192.168.1.2</virtualportgroup-guest-ip-address-1>",{<br>
        "          <virtualportgroup-guest-ip-netmask-1>255.255.255.0</virtualportgroup-guest-ip-netmask-1>",{<br>
        "          <nameserver-0>8.8.8.8</nameserver-0>",{<br>
        "        </application-network-resource>",{<br>
        "      </app>",{<br>
        "    </apps>",{<br>
        "  </app-hosting-cfg-data>",{<br>
        "</data>"{<br>
    ]
}


