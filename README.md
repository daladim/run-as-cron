# run-as-cron

This script runs a command just like cron would.

This is useful to debug a command that, when scheduled by cron, has unexpected behaviour.

## Why isn't `cron` running my script "correctly"?

`cron` does not run a script is the very same way as if you run it from a regular user console.
Indeed, `cron` runs it:
* with a modified environment
* with a specific shell, which may or may not be your usual shell
* without an attached input terminal
* in a non-interactive shell

This script tries hard to mimic this behaviour, so that it easily helps debugging cron scripts.<br/>
An alternative way of debugging would be to schedule your script with `cron` in the following minute, but that limits to one attempt per minute (and causes risking to forget to un-schedule the cron task).

## Credits

This scipt stemmed from [some](https://unix.stackexchange.com/a/580656/330049) [Stack Overflow](https://stackoverflow.com/a/61269393/721832) [discussions](https://serverfault.com/a/1012744).

Credits go to:
* daladim
* poleguy
* (and maybe others, check the merged pull requests)
