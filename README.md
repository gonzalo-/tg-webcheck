# Telegram Bot - Web Check
Little depless bot for telegram that checks if a site is up or down by the HTTP code

## Requirements
You need a telegram bot for this, so for that you should follow the official
documentation:

[https://core.telegram.org/bots](https://core.telegram.org/bots)

Or just "talk" with the following bots and follow the steps:

[Bot Father](https://t.me/botfather)
[Bot ID](https://t.me/idbot)

## Usage
I'm using this in a really simple way, just to get an extra check from
"outside" of my websites besides my real monitoring system.

### List of sites
```
$ pwd
/home/gonzalo/monitoring
$ cat webs.txt
openbsd.org
foobar.org
foobar.com
f00bar.org
f00bar.com
poop.org
poop.com.ar
$ touch /var/log/web-checks.log
$ doas chown gonzalo:gonzalo /var/log/web-checks.log
$ for i in $(cat webs.txt); do sh tg-webcheck $i; done
```

### Just one site
```
$ pwd
/home/gonzalo/monitoring
$ touch /var/log/web-checks.log
$ doas chown gonzalo:gonzalo /var/log/web-checks.log
$ sh tg-webcheck poop.org
```
