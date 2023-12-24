# Jellyfin (Makejail)

Deploy Jellyfin with a single command on FreeBSD.

```sh
appjail makejail \
    -j jellyfin \
    -f gh+DtxdF/jellyfin-makejail
```

By default `jext` is used as the external interface, but you can change it using the `ext_if` argument:

```sh
appjail makejail \
    -j jellyfin \
    -f gh+DtxdF/jellyfin-makejail \
        -- \
        --ext_if em0
```

By default `58-9c-fc-00-00-02` is used as the MAC address for the interface, but you can change it using the `macaddr` argument:

```sh
appjail makejail \
    -j jellyfin \
    -f gh+DtxdF/jellyfin-makejail \
        -- \
        --macaddr 58-9c-fc-00-00-01
```

Use `appjail cmd jexec jellyfin ifconfig` to get the IP address:

```sh
appjail cmd jexec jellyfin ifconfig sb_jellyfin inet | grep inet
        inet 192.168.1.103 netmask 0xffffff00 broadcast 192.168.1.255
```

\~ DtxdF
