# My notes for this project, nothing to see here

```bash
> ctr --address /containers/services/docker/rootfs/var/run/docker/containerd/containerd.sock -n moby c list
CONTAINER                                                           IMAGE    RUNTIME
addceb5478d0c35fa760434c37472552f3a55ef22065727df7dece9e4e3f0339    -        io.containerd.runtime.v1.linux
bf1f43fa12b99189caf14b6cb044948e6bdaaf2a83eba449c76ecb09421e355d    -        io.containerd.runtime.v1.linux

> docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED              STATUS              PORTS               NAMES
addceb5478d0        alpine:3.8          "nsenter -t 1 -m -u …"   About a minute ago   Up About a minute                       cool_agnesi
bf1f43fa12b9        ubuntu              "sleep infinity"         5 days ago           Up 5 days                               pedantic_cohen
```

```bash
>  ls -al /mnt/host/wsl/docker-desktop-data/data/docker/image/overlay2/imagedb/content/sha256/
total 16
drwx------    2 root     root          4096 Sep 26 19:04 .
drwx------    3 root     root          4096 Sep 20 17:03 ..
-rw-------    1 root     root          3353 Sep 20 17:09 bb0eaf4eee00c28cb8ffd54e571dd225f1dd2ed8d8751b2835c31e84188bf2de
-rw-------    1 root     root          1512 Sep 26 19:04 c8bccc0af9571ec0d006a43acb5a8d08c4ce42b6cc7194dd6eb167976f501ef1
```

```bash
>  ls -al /mnt/host/wsl/docker-desktop-data/data/docker/image/overlay2/distribution/v2metadata-by-diffid/sha256/
-rw-r--r--    1 root     root           142 Sep 20 17:09 128fa0b0fb8154f33be04e9cda2c01e88c03cde4825081ed3e0c1858cb5a3431
-rw-r--r--    1 root     root           142 Sep 26 19:04 7444ea29e45e927abea1f923bf24cac20deaddea603c4bb1c7f2f5819773d453
-rw-r--r--    1 root     root           142 Sep 20 17:09 b2fd17df207168da45a6eefccbf58eca08d05b263b3eeb365b6e4b321b18cdc8
-rw-r--r--    1 root     root           142 Sep 20 17:09 c0151ca45f2728482ee96827de759393d47cd5b6707c9f3b930cf46bd92f11b8
```

```bash
ls -al /mnt/host/wsl/docker-desktop-data/data/docker/image/overlay2/layerdb/sha256/
drwx------    2 root     root          4096 Sep 20 17:09 362bda1d1f9b8af533390c6046a74e279bccd5fb70472b5afd4ab4b8d40e10cf
drwx------    2 root     root          4096 Sep 26 19:04 7444ea29e45e927abea1f923bf24cac20deaddea603c4bb1c7f2f5819773d453
drwx------    2 root     root          4096 Sep 20 17:09 832c9286fda134a08292f53028ff1d50dc232cef9317fd7e108e24c480c42217
drwx------    2 root     root          4096 Sep 20 17:09 b2fd17df207168da45a6eefccbf58eca08d05b263b3eeb365b6e4b321b18cdc8
```

```bash
find ./mnt/host/wsl/docker-desktop-data/data/docker/image/overlay2/layerdb/mounts/addceb5478d0c35fa760434c37472552f3a55ef22065727df7dece9e4e3f0339/ -type f -exec sh -c "echo \"{}:\" && cat {} && echo" \
;
./mnt/host/wsl/docker-desktop-data/data/docker/image/overlay2/layerdb/mounts/addceb5478d0c35fa760434c37472552f3a55ef22065727df7dece9e4e3f0339/mount-id:
e6993aee148cd63ef1113e80773aec8a90ab011f948a5bd4894683e10d9b1a88
./mnt/host/wsl/docker-desktop-data/data/docker/image/overlay2/layerdb/mounts/addceb5478d0c35fa760434c37472552f3a55ef22065727df7dece9e4e3f0339/init-id:
e6993aee148cd63ef1113e80773aec8a90ab011f948a5bd4894683e10d9b1a88-init
./mnt/host/wsl/docker-desktop-data/data/docker/image/overlay2/layerdb/mounts/addceb5478d0c35fa760434c37472552f3a55ef22065727df7dece9e4e3f0339/parent:
sha256:7444ea29e45e927abea1f923bf24cac20deaddea603c4bb1c7f2f5819773d453
```
