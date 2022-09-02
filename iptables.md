# iptables
## INFO

Iptables, ip6tables are used to maintain packet filter rules in the Linux kernel.
```diff
*Note:iptables is Not Service.iptables is Mechanism You can work with net Filter in Kernel*
```

![image](ptables_info.png)


1- The First thing to do is to check if Iptables is running on the system. Iptables is running as a kernel module so it can’t be seen as one of the normal processes.

**➜  ~ lsmod|grep iptable**



## Tables and Chains

**1-Table = Filter < Chains = [ OUTPUT, INPUT, FORWARD ]**
**2-Table = Nat < Chains = [ OUTPUT, PREROUTING, POSTROUTING ]**
**3-Table = Mangle < Chains = [ INPUT, OUTPUT, FORWARD, PREROUTING, POSTROUTING ]**

## Most Important Switches

**-A => append**
**-I => Insert**
**-D => DELETE**
**-F => Flush**
**-R => Replace**
**-P => Policy**
**-i -> input bound**
**-o -> output bound**
**-N -> create New chain**
**-X -> Delete chain**
```diff
*Note : in Interface switch you can use any for all Interfaces*
```
**-s or --source -> source ip**
**-d or --destination -> destination ip**
**-p -> protocol**
**-m -> module**
**--sport -> source port**
**--dport -> destination port**

### Basic Examples

**➜  ~ sudo iptables -A INPUT -i enps0 -p tcp --source 192.168.1.105 --dport 80 -j DROP**
**➜  ~ sudo iptables -A INPUT -i enps0 -p tcp --source 92.168.1.102 --sport 80 --destination 192.168.1.102 --dport 80 -j DROP**
