# ovirtctl

**Ovirt control script to manage VMs via REST API [http://ovirt.github.io/ovirt-engine-api-model/4.3/].**

Warning! The script is compatible with Ovirt 4.3 and is not tested with other versions.

Using this script, for example, you can make autostart of Ovirt VMs when OS started. Ovirt 4.3 is not supports that feature from "out of the box".


```
Usage:
	vm-list
	vm-start|vm-stop|vm-shutdown|vm-reboot|vm-suspend|vm-get <vmName>
	vm-start-all|vm-stop-all|vm-shutdown-all
```

Before use the script:
1) Set variables in /bin/ovirtctl: **host**, **user**, **password** which using for login to ovirt-engine Web UI.
2) Check path of **cacert** variable. If correct, then not need touch.
3) Change value of **vms_queue_start_timeout** variable if need. Script waiting(in seconds) before start next VM from queue.
4) Registry to **vm_map** variable the VMs which will be manage by the script.
	For example: *vm_map["bar"]="0074d052-283a-44ae-8788-c50e295dde67"*. Where *bar* is VM name and *0074d052-283a-44ae-8788-	c50e295dde67* is VM id.

```
Usage examples:
	PATH=$PATH:/opt/ovirtctl/bin
	ovirtctl vm-start foo
	ovirtctl vm-start bar
	ovirtctl vm-shutdown-all
```
