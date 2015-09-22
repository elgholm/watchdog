# Watchdog

Easy to use watchdog system for monitoring and reporting on Linux/Unix machines.

2015-09-22 First version released by Charlie Elgholm, charlie@elgholm.se

These scripts implement an easy to use watchdog system for monitoring and reporting on Linux machines.
The main idea is to only require bash and normal Linux GNU utilities, be easy to use and understandable by the average system administrator.

## Description of files in this package:
- "setup": This file contains your setup, change to suit your needs.
- "execute": The main script, add this to your cron, preferable for every minute.
- "log" - Logfile
- "scripts/": The individual scripts, executed each time "execute" is run (by cron).
- "out/": Placeholder directory for outputs by the scipts, check here for status.
- "notify_critical": This script is executed when notifying about critical events.
- "notify_warning": This script is executed when notifying about warning events.
- "notify_panic": This script is executed when notifying about panic events, maybe also a good place to do a reboot, your choice.
- "README.md": Your reading it.
- "LICENSE": GNU GPLv2 - The license for this system.

## How to use?
1. Create a directory somewhere in your machine, preferable under the home-directory of the root-user, i.e. /root/watchdog.
2. Copy all files in this package to the above directory. Make sure "execute", "notify-" and "scripts/"-files are executable.
3. Edit the "setup" and "notify-" to your liking.
4. Check scripts/-files (and edit them to your liking).
5. Add the file "execute" to your crontab, i.e "* * * * * /root/watchdog/execute" for monitoring each minute.

## Roll your own monitoring scripts?
Great! Just place your script (executable) under the scripts-directory, and make sure they
print "WARNING/CRITICAL/PANIC: Your text" when something happens.
You'll get the idea. It's meant to be simple. Please share with the community.

Regards
Charlie Elgholm