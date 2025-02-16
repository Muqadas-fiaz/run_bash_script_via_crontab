# System Monitor

A bash script to monitor and log CPU, RAM, and storage usage on a Linux system. The script logs data with timestamps and can be scheduled to run periodically using cron.

## Features

- **CPU Usage Monitoring**: Monitors the percentage of CPU usage.
- **RAM Usage Monitoring**: Monitors the amount of RAM used, total, and free.
- **Storage Usage Monitoring**: Monitors the storage usage of the root (`/`) filesystem.
- **Logging**: Logs the system usage data to `/var/log/system_monitor.log` with timestamps.
- **Cron Job Scheduling**: Can be set up to run periodically using a cron job.

## Requirements

- A Linux system with `bash`.
- `sysstat` package (for the `mpstat` command).

## Installation

### 1. Clone the Repository

Clone the repository to your local machine:
```sh
https://github.com/Muqadas-fiaz/run_bash_script_via_crontab.git
```
### 2. Install Dependencies

Install the necessary dependencies:
```sh
sudo yum install sysstat
```
```sh
nano system_monitor.sh
```
paste the bash file script in it
### 3. Make the Script Executable

Make the script executable:
```sh
chmod +x system_monitor.sh
```

### 4. Setup Log Directory and Permissions

Ensure the log directory exists and set the appropriate permissions
```sh
sudo mkdir -p /var/log
```
```sh
sudo touch /var/log/system_monitor.log
```
```sh
sudo chown $USER:$USER /var/log/system_monitor.log
```
**Usage**
Run the script manually to see the output:
```sh
./system_monitor.sh
```
## Setting Up Cron Job

To run the script every 2 minutes, follow these steps:
### 1. Open the Crontab Editor

Open the crontab editor:
```sh
crontab -e
```

### 2. Add the Cron Job

Add the following line to run the script every 2 minutes:
```sh
*/2 * * * * /home/muqadas/system_monitor.sh
```
/home/muqadas/system_monitor.sh the the actual path to the script.you can find out your path by using pwd
```sh
crontab -l
```
show the output by this command
```sh
cat /var/log/system_monitor.log
```
