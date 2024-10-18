` List some of the commonly used shell commands`

 ls, cp, mv, mkdir, touch, vim, grep, df

 `Write a simple shell script to list all processes`
 
 ps -ef

 how do we check only process ID?

 ps -ef | awk -F" " '{print$2}'

 `Write a script to print only errors from a remote log?`

 curl <file-name> | grep <error-name>

 we achieved this using curl, pipe and grep command

 `Write a shell script to print numbers divided by 3 & 5 and not 15?`
```
#!/bin/bash
#divisible by 3, divisible by 5, not 3*5=15

for i in {1..100}; do
if ([`expr $i%3 == 0`] || [`expr $i%5 == 0`]) && [`expr $i%15 != 0`];
then
       echo $i
fi;
done
```

`Write a script to print the number of "S" in Mississippi`

vi number.sh

```
#!/bin/bash
x=mississippi
grep -o "s" <<<"$x" | wc -l
```

`How will you debug the shell script?`

By defining the "set -x" in the script

`How to open a read-only file?`

vim -r <file-name>

`What is crontab`

With the help of crontab, we can schedule and run jobs or task in the background automatically at regular intervals.

we can automate process like backup, schedule updates and synchronization of files.

format ---> ***** /path/to/script.sh

#### Example

##### [1] Scheduling a Job for a Specific Time

job--> full-backup

time--> 12th June 09:35 AM

35 09 12 06 */home/Pratap/full-backup

35-->minute

09-->09 AM

12-->12th day

06-->6th month(June)

* --> every day of the week

##### [2] Schedule a Job for more than one instance(e.g twice a day)

job--->Incremental-backup

time-->11:00 and 16:00 on everyday

00 11,16 * * */home/Pratap/bin/incremental-backup

##### [3] Schedule a Job for Specific range of time

job--> check the status of database everyday

time--> 9AM to 6PM

00 09-18 ***/home/Pratap/bin/check-db-status

00-->0th minute

09-18-->9am,10am,11am,12am,13pm,14pm,15pm,16pm,17pm,18pm

*-->Every day

*-->Every month

*-->Every day of the week


##### [4] Cron Job every weekday during working hours

job-->check the status of the database every weekday(mon to fri)

time-->9am to 6pm

00 09-18 * * 1-5 /home/Pratap/bin/check-db-status

00-->0th minute

09-18-->9am,10am,11am,12am,13pm,14pm,15pm,16pm,17pm,18pm

*-->Every day

*-->Every month

1-5-->mon,tues,wed,thru,fri(every weekday)

Note:-Schedule a job for every minute using cron

*****CMD

*/5-->every 5 minutes

0-10/2--->every two minutes in the first 10 minutes

To view the crontab entries
```
crontab -l
```
To check the logs
```
/var/log/cron
```
Edit the crontab
```
crontab -e
```

 `Difference between Hardlink and Softlink?`

There are two types of link(ln) in linux

**Hark link:**

- It is the mirror file of original file
- It is used for backup
- If you create link the inode address is for both the files is same becoz it takes the spaces for one file only we can't put the files in cross filesystems(one is /dev/sda1 and another one is /dev/sda2)

**Softlink:**

- It is used to create the shortcuts of a file
- If you create a link then the inode address is different in both the files
- If you delete the original file then you can't access the link(now it is useless) we can put the files in cross filesystems(one is /dev/sda1 and another is /dev/sda2)
