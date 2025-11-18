# OPEN-SOURCE-EX-5

## NAME: Pooja S 
## REGNO: 212223040146
## DEPT: CSE 

## AIM:
To schedule automated tasks for a specific user using the Linux `crontab` utility and verify the status and execution of cron jobs.

## PROCEDURE:

### **STEP 1:**  
Switch to root user  
```bash
sudo -i
```

### **STEP 2:**  
Edit crontab for user **harry**  
```bash
crontab -u harry -e
```

### **STEP 3:**  
Add the following cron jobs:

```bash
# Run daily at 12:30 PM
30 12 * * * /bin/echo "hello"

# Run every 2 minutes
*/2 * * * * /bin/echo "Hi I'm Running"

# Run daily at 2:23 PM
23 14 * * * /usr/bin/logger "RHCSA EXAM TRAINING"

# Run daily at 12:00 PM
0 12 * * * /usr/bin/logger "EX200 in Progress"
```

### **STEP 4:**  
View the cron jobs for user **harry**  
```bash
crontab -u harry -l
```

### **STEP 5:**  
Check cron service status  
```bash
systemctl status crond
```

### **STEP 6:**  
Start and enable cron service  
```bash
systemctl start crond
systemctl enable crond
```

### **STEP 7:**  
Test cron job commands as user **harry**  
```bash
sudo -u harry /bin/echo "hello"
sudo -u harry /usr/bin/logger "RHCSA EXAM TRAINING"
```

### **STEP 8:**  
Verify logs for the scheduled messages  
```bash
journalctl | grep RHCSA
```

## OUTPUT:
![Screenshot](https://github.com/user-attachments/assets/fd099347-80ae-48cb-a391-626b127e131c)

## RESULT:
The cron jobs were successfully scheduled, executed, and verified in the Red Hat Linux environment.
