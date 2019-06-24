mcinit
======

Simple BSD init script (`rc.d`) for a Minecraft server.

Installation
------------

### Initial setup

This script requires GNU Screen to function.

For default setup, create a user named `minecraft`, set its home
directory to `/usr/local/srv/minecraft`, and place the server JAR
into said directory.


### Configuration

The following lines can be employed and modified as necessary in
`/etc/rc.conf.local`:
```
minecraft_user="<run server as this user>"
minecraft_chdir="<run server in this directory>"
minecraft_jar="<path to server JAR>"
minecraft_memory="<memory_to_allocate>"
```

Do note: if using third-party server software such as
[Spigot](http://spigotmc.org/) or [Paper](https://papermc.io/),
the `minecraft_jar` variable must be changed or the JAR renamed.

Usage
-----

Upon adding `minecraft_enable="YES"` to `/etc/rc.conf.local`, the
following commands do as expected: start, stop and restart,
respectively:
```console
# service minecraft start
# service minecraft stop
# service minecraft restart
```

You can also access the console with `service minecraft show`.

To-do
-----

* Watchdog?

Bugs
----

If something goes wrong, please report it on the
[issues board](https://gitlab.com/ssterling/mcinitd/issues).
I've only tested this script on my specific configurations,
so having input from users with diverse setups would help
promptly identify and fix issues.
