# Ansible OpenNebula Authentication

A very small repo just outlining how to use the 'api_*' paremeters of the ansible opennebula modules.

When trying to track down the actual usage of these paremeters in the modules, I struggled to come accross the answer which is why I have created this repo.

If you build your own OpenNebula host then this may be obvious to you but in my case, I have joined a company who use it.

The locations for the paremeters can be found at the following locations:

## api_url

This is the URL of your opennebula host, in my case I used the sunstone GUI link and added the port __':2633'__ and __'/RPC2'__
on the end i.e. __"http://<my.office.host>:2633/RPC2"__

## api_username

This should be an obvious one, you're __non__ root login for your opennebula host.

## api_password

Not to confused with the __Sunstone GUI__ password, this password (which is to oned i beleive) can be found at '/var/lib/one/.one/one_auth'.

## Example usage

A simple usage example for the opennebula authentication parameters is seen below in a one_vm module role.

```
- one_vm:
    api_password: <YOUR PASSWORD>
    api_url: http://<YOUR-OPENNEBULA-HOST>:2633/RPC2
    api_username: <YOUR USERNAME>
    template_id: 7
  register: result
```
