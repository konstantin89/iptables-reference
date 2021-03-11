# iptables-reference

## Topics
[Reference](doc/Reference.md)  
[Examples](doc/Examples.md)  

</br>  

## Rules persistency

Rules that are written in the terminal, are lost after system restart.  

In order to make rules persistent, rules has to be writtent in script that will run in boot time.  

</br>  

## Quick Reference

![](doc/img/iptables_command_reference.PNG)  

![](doc/img/iptables_options.PNG)  


</br>  

## Command examples

### List

If `-n` flag is used, the numeric values will be printed.   
For example, ssh port will be printed as 22.  
This prevents alot on DNS lookups.

List `filter` table (`filter` is the default table).  
(nv for numeric and verbose)
``` 
sudo iptables -nvL
```

List specific table (nat in this example).  
(nv for numeric and verbose)  

``` 
sudo iptables -nvL -t nat
```

### Flush (remove) 

Remove all rules from all chains (of the default `filter` table).  
```
sudo iptables -F
```

Remove all rules from input chain (of the default `filter` table).  
```
sudo iptables -F INPUT
```

### Fefault policy definition

Each packet that doesn't maches any rule will have the default policy.  
In the example below, all the packets in FARWARD chain will be dropped.  
```
sudo iptables -P FARWARD DROP
```
