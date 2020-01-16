### usage

- connect and test network
```
docker run -it --rm --network <network name> dwiechno/toolbox bash
```
- check volume content
```
docker run -it --rm --volume <volume name>:/media/volume-test dwiechno/toolbox bash
```
- export volume
```
  mkdir backups
  docker run --rm -v <volName>:/volume dwiechno/toolbox:latest sh -c 'tar -cOzv -C / -f - /volume' > backups/volume.tgz
```
- clean/create volume and import data from archive
```   
  docker run --rm \
    -v <volName>:/volume \
    -v `pwd`/backups:/backups \
    dwiechno/toolbox:latest \
    sh -c 'rm -rf /volume/* ;cd / ;tar zxvf /backups/volume.tgz'
```


### standard network tools (examples)
```
curl --head -L webhost:80
nc -w 5 webhost 80 && echo SUCCESS || echo FAILED
route
```
### and tools for volumes
```
tree -Ca -L 2
du -sh *
ncdu
vi
```
