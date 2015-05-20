# stap command line 101

## Querying probes

```bash
# List all traceable kernel functions
stap -l 'kernel.function("*")'
# As above + traceable vars/params
stap -L 'kernel.function("*")'
```


