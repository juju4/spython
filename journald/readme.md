linux_journald
============

This sample writes messages using [journald](https://www.freedesktop.org/software/systemd/man/latest/systemd-journald.service.html).

To build on Linux, run `make` with a copy of Python 3.8.0rc1 or later
installed. Ensure to have sd-journal.h (Fedora systemd-devel or Debian libsystemd-dev)

You may need to enable a journald service on your machine in order to
receive the events. For example, if using `rjournald`, you might use
these commands:

```
$ make
$ sudo service rjournald start
$ ./spython test-file.py
$ sudo service rjournald stop
$ cat /var/log/journald
```

References
* [systemd for Developers III](https://0pointer.de/blog/projects/journal-submit.html)

Known issues
* "TypeError: signal handler must be signal.SIG_IGN, signal.SIG_DFL, or a callable object" when using spython
