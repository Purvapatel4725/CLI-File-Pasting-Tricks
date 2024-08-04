## Write a code:

```
# cat arp.py
import socket
for i in range(0, 256):
    sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    sock.settimeout(0.5)
    ip = '172.16.1.{}'.format(i)
    if 0 == sock.connect_ex((ip, 22)):
        sock.close()
        print(ip + '   ON' , flush=True)
    else:
        print(ip,  flush=True)
# cat arp.py | base64 | tr -d '\n' | xclip
```
## convert it into base64 format:

```
aW1wb3J0IHNvY2tldAoKZm9yIGkgaW4gcmFuZ2UoMCwgMjU2KToKICAgIHNvY2sgPSBzb2NrZXQuc29ja2V0KHNvY2tldC5BRl9JTkVULCBzb2NrZXQuU09DS19TVFJFQU0pCiAgICBzb2NrLnNldHRpbWVvdXQoMC41KQogICAgaXAgPSAnMTcyLjE2LjEue30nLmZvcm1hdChpKQogICAgaWYgMCA9PSBzb2NrLmNvbm5lY3RfZXgoKGlwLCAyMikpOgogICAgICAgIHNvY2suY2xvc2UoKQogICAgICAgIHByaW50KGlwICsgJyAgIE9OJyAsIGZsdXNoPVRydWUpCiAgICBlbHNlOgogICAgICAgIHByaW50KGlwLCAgZmx1c2g9VHJ1ZSkK
```
## echo it into a file:

```
echo 'aW1wb3J0IHNvY2tldAoKZm9yIGkgaW4gcmFuZ2UoMCwgMjU2KToKICAgIHNvY2sgPSBzb2NrZXQuc29ja2V0KHNvY2tldC5BRl9JTkVULCBzb2NrZXQuU09DS19TVFJFQU0pCiAgICBzb2NrLnNldHRpbWVvdXQoMC41KQogICAgaXAgPSAnMTcyLjE2LjEue30nLmZvcm1hdChpKQogICAgaWYgMCA9PSBzb2NrLmNvbm5lY3RfZXgoKGlwLCAyMikpOgogICAgICAgIHNvY2suY2xvc2UoKQogICAgICAgIHByaW50KGlwICsgJyAgIE9OJyAsIGZsdXNoPVRydWUpCiAgICBlbHNlOgogICAgICAgIHByaW50KGlwLCAgZmx1c2g9VHJ1ZSkK'  | base64 -d > arp.py
```

## You can now see that the contents are pasted as is inside the file
