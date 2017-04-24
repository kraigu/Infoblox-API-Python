# Infoblox API

This project implements the subset of Infoblox API via REST API

## Infoblox API python module

Class **Infoblox** implements the following methods:

- create_network
- delete_network
- create_networkcontainer
- delete_networkcontainer
- get_all_networks
- get_next_available_network
- create_host_record
- create_txt_record
- delete_host_record
- delete_txt_record
- add_host_alias
- delete_host_alias
- create_cname_record
- delete_cname_record
- update_cname_record
- create_dhcp_range
- delete_dhcp_range
- get_next_available_ip
- get_host
- get_host_by_ip
- get_ip_by_host
- get_host_by_extattrs
- get_host_by_regexp
- get_txt_by_regexp
- get_host_extattrs
- get_network
- get_network_by_ip
- get_network_by_extattrs
- get_network_extattrs
- update_network_extattrs
- delete_network_extattrs
- csv_upload
- csv_insert
- csv_delete
- get_lease_cltt_by_hostname
- get_lease_by_ip
- get_lease_by_mac
* * *

### How to use

Example:

```
import infoblox

iba_api = infoblox.Infoblox('10.10.20.32', 'admin', 'secret', '1.6', 'internal', 'default')

try:
    ip = iba_api.create_host_record('192.168.0.0/24', 'mytest.example.com')
    print ip
except Exception as e:
    print e

```

```
import infoblox
import warnings
# ignore ssl warnings because who cares about security
warnings.filterwarnings("ignore", ".*Unverified.*")

iba_api = infoblox.Infoblox('10.10.20.32', 'admin', 'secret', '1.7', 'internal', 'default')
try:
	n = iba_api.get_all_networks(max_results='10000') # what's paginating?
except Exception as e:
    print e

for net in n:
	print net['network']
```
