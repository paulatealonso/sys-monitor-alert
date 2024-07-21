# System Monitoring Script

This script monitors CPU, memory, disk usage, and network traffic on a Linux system. It generates alerts if usage exceeds specified thresholds.

## Features

- Monitors CPU and memory usage
- Monitors disk usage
- Monitors network traffic (bytes received and transmitted)
- Sends email alerts if usage exceeds defined thresholds

## Usage

### Prerequisites

Ensure you have the following installed on your system:

- `bc`: For floating-point arithmetic
- `mailutils`: For sending email alerts

Install them using the following commands:

```bash
sudo apt-get update
sudo apt-get install bc mailutils
```

## Configuration

Create a config.env file from the provided config.env.example and update the values with your desired settings:

```
cp config.env.example config.env

```


## Thresholds

Set the thresholds for alerts in the config.env file:
    
  - CPU_THRESHOLD: CPU usage percentage threshold
  - MEM_THRESHOLD: Memory usage percentage threshold
  - DISK_THRESHOLD: Disk usage percentage threshold



## Email Configuration

Make sure to configure your email settings in the config.env file:

  - EMAIL: Your email address to receive alerts


### Running the Script

Make the script executable:

```
chmod +x monitoring-script-deb

```

Run the script manually:

```
./monitoring-script-deb

```

## Automating with Cron

To automate the script to run periodically, edit your crontab file:

```
crontab -e

```

Add the following line to run the script every 5 minutes:

```
*/5 * * * * /path/to/your/monitoring-script-deb

```


# Script Details
- check_cpu_mem()

### Monitors CPU and memory usage. Sends an email alert if the usage exceeds the defined thresholds.
- check_disk()

### Monitors disk usage. Sends an email alert if the usage exceeds the defined threshold.
- check_network()

### Monitors network traffic (bytes received and transmitted).
- main()

Calls the above functions to perform the monitoring.


## An example config.env.example file:

- CPU_THRESHOLD=80
- MEM_THRESHOLD=80
- DISK_THRESHOLD=80
- EMAIL=your-email@example.com

## Contributing

Feel free to fork this repository, make improvements, and create pull requests. Contributions are welcome!
License

### This project is licensed under the MIT License - see the LICENSE file for details.
