# Pi-hole

Role to deploy and configures everything required to run Pi-hole on a Raspberry Pi in your network. 

## Requirements

* Ansible 2.9 or newer

## Role Variables


|variable name| default | description|
|-------------|---------|------------|
| `raspberry_user` | pi | The user that will be running Pi-hole. |
| `dns_server1` | 8.8.8.8 | The IP for the primary DNS server Pi-hole will forward requests to. |
| `dns_server2` | 8.8.4.4 | The IP for the secondary DNS server Pi-hole will forward request to if the primary DNS server is not available. <br/><br/> Use the value "no" to  disable the secondary DNS|
| `pihole_admin_password` | random | Administrator password for the web ui for Pi-hole. <br/><br/> It is recommended that you set this to something else, or you will have to dig through the logs on the host to find the automatically generated password. |

## Dependencies

* geerlingguy.docker
* geerlingguy.pip

## Example Playbook


```
- hosts: all
  roles:
  - name: twinsnes.pihole
    vars:
      pihole_admin_password: "SomeSecretPassword"
```
## License

Apache-2.0
