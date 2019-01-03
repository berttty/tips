# For option


```bash
USER=root; for ip in $(cat ./nodes); do ssh -t ${USER}@${ip} 'command' ; done
```

example 

```bash
for ip in $(cat ./nodes); do ssh -t root@${ip} 'ls -lah' ; done
```