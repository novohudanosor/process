# process
## Управление процессами 
1. Работа скрипта основывается на анализе файлов **/proc/PID/cmdline** и **/proc/PID/stat**
2. Файл состоит из полей данных, в которых содержится информация о процессе: PID процесса, имя исполняемого файла, статус процесса, PID родительского процесса, наименование управляющего терминала процесса, временные параметры процесса в пользовательском режиме и режиме
ядра, количество занимаемой виртуальной и реальной памяти и др. 
3. Запуск скрипта
``` 
root@dmikhaylov-Ubuntu2204:~/process# ./ps_custom.sh | head -n 25
PID     TTY     STAT    TIME    COMMAND
1               S       0:30    /sbin/initsplash
2               S       0:00    [kthreadd]
3               I       0:00    [rcu_gp]
4               I       0:00    [rcu_par_gp]
5               I       0:00    [slub_flushwq]
6               I       0:00    [netns]
8               I       0:00    [kworker/0:0H-events_highpri]
11              I       0:00    [mm_percpu_wq]
12              I       0:00    [rcu_tasks_kthread]
13              I       0:00    [rcu_tasks_rude_kthread]
14              I       0:00    [rcu_tasks_trace_kthread]
15              S       0:00    [ksoftirqd/0]
16              I       0:00    [rcu_preempt]
17              S       0:00    [migration/0]
18              S       0:00    [idle_inject/0]
19              S       0:00    [cpuhp/0]
20              S       0:00    [cpuhp/1]
21              S       0:00    [idle_inject/1]
22              S       0:00    [migration/1]
23              S       0:00    [ksoftirqd/1]
25              I       0:00    [kworker/1:0H-kblockd]
26              S       0:00    [cpuhp/2]
27              S       0:00    [idle_inject/2]
28              S       0:00    [migration/2]
```
```
root@dmikhaylov-Ubuntu2204:~/process# ./ps_custom.sh | tail -n 25
4771            S       0:00    /usr/bin/python3/usr/bin/gnome-terminal--wait
4772            S       0:00    /usr/bin/gnome-terminal.real--wait
4777            S       0:00    /usr/libexec/gnome-terminal-server
4795    pts/0   S       0:00    bash
4808            S       0:04    update-notifier
4963            S       0:00    /tmp/.mount_OutlinNYAF2Y/resources/app.asar.unpacked/client/output/build/linux/tun2socks-tunNameoutline-tun0-tunAddr10.0.85.2-tunGw10.0.85.1-tunMask255.255.255.0-tunDNS1.1.1.1,9.9.9.9-proxyHost194.120.116.112-proxyPort51798-proxyPasswordm10Ua1eNS59E7WfBNRHTbl-proxyCipherchacha20-ietf-poly1305-proxyPrefix-logLevelinfo
4970            S       0:00    sshd:
5047            S       0:01    sshd:
5048            S       0:00    sshd:
5050    pts/1   S       0:00    -bash
5057            S       0:15    bash-cwhile
5093            S       0:00    sshd:
5100            S       0:00    /usr/lib/openssh/sftp-server
5125    pts/1   S       0:00    sudosu-
5146    pts/2   S       0:00    sudosu-
5148    pts/2   S       0:00    su-
5152    pts/2   S       0:12    -bash
9180            I       0:00    [kworker/0:1-events]
17827           I       0:00    [kworker/u8:0-events_unbound]
20673           I       0:00    [kworker/3:0-events]
22890           I       0:00    [kworker/u8:3-flush-8:0]
34080           I       0:00    [kworker/u8:1-events_power_efficient]
41681   pts/2   S       0:02    /bin/bash./ps_custom.sh
41682   pts/2   S       0:00    tail-n25
41682   pts/2   S       0:00    tail-n25

```

