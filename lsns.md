# lsns

## 1. 介绍
sns命令列出有关所有当前可访问的名称空间或给定名称空间的信息。命名空间标识符是一个索引节点号。


## 2. 参数
| -J | 使用 JSON 输出格式                                  |
|----|-----------------------------------------------|
| -l | 使用列表格式的输出                                     |
| -n | 不打印标题                                         |
| -r | 使用原生输出格式                                      |
| -u | 不截断列中的文本                                      |
| -t | 名字空间类型(mnt, net, ipc, user, pid, uts, cgroup) |




## 3. 命令
列出net名字空间类型
```
bash$ lsns -t net
        NS TYPE NPROCS PID USER COMMAND
4026531993 net     156   1 root /sbin/init auto automatic-ubiquity noprompt
```
使用列表格式的输出
```
bash$ lsns -l
        NS TYPE   NPROCS   PID USER             COMMAND
4026531835 cgroup    155     1 root             /sbin/init auto automatic-ubiquity noprompt
4026531836 pid       155     1 root             /sbin/init auto automatic-ubiquity noprompt
4026531837 user      155     1 root             /sbin/init auto automatic-ubiquity noprompt
4026531838 uts       155     1 root             /sbin/init auto automatic-ubiquity noprompt
4026531839 ipc       155     1 root             /sbin/init auto automatic-ubiquity noprompt
4026531840 mnt       151     1 root             /sbin/init auto automatic-ubiquity noprompt
4026531861 mnt         1    13 root             kdevtmpfs
4026531993 net       155     1 root             /sbin/init auto automatic-ubiquity noprompt
4026532544 mnt         1   507 root             /lib/systemd/systemd-udevd
4026532620 mnt         1   685 systemd-timesync /lib/systemd/systemd-timesyncd
4026532621 mnt         1  2935 systemd-network  /lib/systemd/systemd-networkd
```

不打印标题
```
bash$ lsns -n
4026531835 cgroup    155     1 root             /sbin/init auto automatic-ubiquity noprompt
4026531836 pid       155     1 root             /sbin/init auto automatic-ubiquity noprompt
4026531837 user      155     1 root             /sbin/init auto automatic-ubiquity noprompt
4026531838 uts       155     1 root             /sbin/init auto automatic-ubiquity noprompt
4026531839 ipc       155     1 root             /sbin/init auto automatic-ubiquity noprompt
4026531840 mnt       151     1 root             /sbin/init auto automatic-ubiquity noprompt
4026531861 mnt         1    13 root             kdevtmpfs
4026531993 net       155     1 root             /sbin/init auto automatic-ubiquity noprompt
4026532544 mnt         1   507 root             /lib/systemd/systemd-udevd
4026532620 mnt         1   685 systemd-timesync /lib/systemd/systemd-timesyncd
4026532621 mnt         1  2935 systemd-network  /lib/systemd/systemd-networkd
```

不截断列中的文本
```
bash$ lsns -u
        NS TYPE   NPROCS   PID USER             COMMAND
4026531835 cgroup    155     1 root             /sbin/init auto automatic-ubiquity noprompt
4026531836 pid       155     1 root             /sbin/init auto automatic-ubiquity noprompt
4026531837 user      155     1 root             /sbin/init auto automatic-ubiquity noprompt
4026531838 uts       155     1 root             /sbin/init auto automatic-ubiquity noprompt
4026531839 ipc       155     1 root             /sbin/init auto automatic-ubiquity noprompt
4026531840 mnt       151     1 root             /sbin/init auto automatic-ubiquity noprompt
4026531861 mnt         1    13 root             kdevtmpfs
4026531993 net       155     1 root             /sbin/init auto automatic-ubiquity noprompt
4026532544 mnt         1   507 root             /lib/systemd/systemd-udevd
4026532620 mnt         1   685 systemd-timesync /lib/systemd/systemd-timesyncd
4026532621 mnt         1  2935 systemd-network  /lib/systemd/systemd-networkd
```
