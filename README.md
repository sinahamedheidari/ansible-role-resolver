# ansible-role-resolver
This role changes the default resolvers in Ubuntu/CentOS.

By default dns resolvers are controlled by NetworkManager. This role stop NeworkManager from adding dns-servers to ```/etc/resolv.conf``` 
by adding ```dns=none``` to ```/etc/NetworkManager/NetworkManager.conf```.

Then it copies your desired dns resolvers to the server.

## How to run?
Create a directory and clone the repo.
```shell
mkdir ~/ansible/
git clone https://github.com/sinahamedheidari/ansible-role-resolver
mv ansible-role-resolver/main.yml ./ 
mv ansible-role-resolver/ansible.cfg ./ 
mv ansible-role-resolver/inventory ./
```

Run with defaults:
```shell
ansible-playbook main.yml
```

To change to local dns servers:
```shell
ansible-playbook --extra-vars "dns_file=local" main.yml
```

To change to global dns servers:
```shell
ansible-playbook --extra-vars "dns_file=global" main.yml
```

You can also modify or add new resolvers inside templates directory.

## License

- **[MIT license](http://opensource.org/licenses/mit-license.php)**
