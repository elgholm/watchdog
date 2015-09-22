# Watchdog

Easy to use watchdog system for monitoring and reporting on Linux/Unix machines.

Written by Charlie Elgholm, charlie@elgholm.se

These scripts implement an easy to use watchdog system for monitoring and reporting on Linux machines.
The main idea is to only require bash and normal Linux GNU utilities, be easy to use and understandable by the average system administrator.

## Description of files in this package:
- setup: This file contains your setup (environment variables), change to suit your needs.
- execute: The main file who should be executed, add this to your cron, preferable for every minute.
- log - Logfile
- scripts/*: The individual scripts, executed each time the execute-script is run (by cron).
- out/*: Placeholder directory for outputs by the scipts
- notify_critical: This script is executed when notifying about critical events.
- notify_warning: This script is executed when notifying about warning events.
- notify_panic: This script is executed when notifying about panic events, maybe also a good place to do a reboot, your choice.
- README.md: Your reading it.
- LICENSE: GNU GPLv2 - The license for this system.

## How to use?
1. Create a directory somewhere in your machine, preferable under the home-directory of the root-user, i.e. /root/watchdog.
2. Copy all files in this package to the above directory. Make sure execute-, notify_*- and scripts/*-files are executable.
3. Edit the file setup, to your liking. The MACHINE_NAME environment variable must be set.
4. Check notify_*-files, and change/edit them if necessary.
5. Check scripts/*-files, and edit them to your liking.
6. Add the file "execute" to your crontab, i.e "* * * * * /root/watchdog/execute" for execution each minute.

