# crontab Example

```
# To define the time you can provide concrete values for
# minute (m), hour (h), day of month (dom), month (mon),
# and day of week (dow) or use '*' in these fields (for 'any').#
# Notice that tasks will be started based on the cron's system
# daemon's notion of time and timezones.
#
# Output of the crontab jobs (including errors) is sent through
# email to the user the crontab file belongs to (unless redirected).
#
# For example, you can run a backup of all your user accounts
# at 5 a.m every week with:
# 0 5 * * 1 tar -zcf /var/backups/home.tgz /home/
#
# For more information see the manual pages of crontab(5) and cron(8)
#
# m h  dom mon dow   command
0 5 * * * sudo apt-get update ; DEBIAN_FRONTEND=noninteractive sudo apt-get -y upgrade > /home/ubuntu/upgrade.log 2>&1
30 5 * * * /home/ubuntu/upgrade-plugins.sh > /home/ubuntu/upgrade-plugins.log 2>&1
0 3 * * SUN /usr/bin/docker images | /usr/bin/tr -s " " " " | /usr/bin/cut -d" " -f3 | /usr/bin/xargs /usr/bin/docker rmi -f > /home/ubuntu/docker-cleanup.log 2>&1
```
