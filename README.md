# unraid-vector

This plugin is a vector plugin for the Unraid server. It is a simple plugin that allows you to monitor the server's CPU, memory, and disk usage.

## How to build unraid package example

```bash
mkdir -p ./artifacts/usr/local/emhttp/plugins/vector/
mkdir -p ./artifacts/etc/rc.d/

cp vector ./artifacts/usr/local/emhttp/plugins/vector/
cp rc.vector ./artifacts/etc/rc.d/

find ./artifacts/ -type f
# ./artifacts/usr/local/emhttp/plugins/vector/vector
# ./artifacts/etc/rc.d/rc.vector

tar --owner=0 --group=0 -cvzf packages/vector-0.40.0-x86_64-unknown-linux-gnu.tgz --xform='s,./artifacts/,,' $(find ./artifacts/ -type f)

md5sum ./packages/vector-0.40.0-x86_64-unknown-linux-gnu.tgz
```

## Usage

Create config file `/boot/config/plugins/vector/config.yaml`.

Then...

- Run `/etc/rc.d/rc.vector validate` to validate.
- Run `/etc/rc.d/rc.vector start` to start.
- Or run `/etc/rc.d/rc.vector reload` to hot reload.