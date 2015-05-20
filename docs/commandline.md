# stap command line 101

## Querying probes

```bash
# List all traceable kernel functions
stap -l 'kernel.function("*")'
# As above + traceable vars/params
stap -L 'kernel.function("*")'
# List syscall predefined probes
stap -L 'syscall.*'
```
Some useful example
```bash
czajnik@autosan:~$ stap -L 'kernel.function("SYSC_epoll_wait")'
kernel.function("SYSC_epoll_wait@/build/buildd/linux-lts-saucy-3.11.0/fs/eventpoll.c:1917") $timeout:int $maxevents:int $events:struct epoll_event* $epfd:int
```

Same using the syscall wrapper probe:
```bash
czajnik@autosan:~$ stap -L 'syscall.epoll_wait'
syscall.epoll_wait __nr:unknown name:unknown epfd:unknown events_uaddr:unknown maxevents:unknown timeout:unknown argstr:unknown $ret:long int
```



