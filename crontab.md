#Job scheduling using cron
 
##run a job every 5 minutes

```console
$ crontab -e
```

(in editor)

```console
MAILTO=""
*/5 * * * * ~/path/job
```

_Explanation_

'*/5' means a recurring job

MAILTO stops email spam in var/email/$user

##delete all jobs

```console
$ crontab -r
```

##list current jobs

```console
$ crontab -l
```

##NOTE

cron doesn't understand ~/ so use the full path

also, don't rely on any path settings as ~/.bash_profile or ~/.bashrc may not have run
