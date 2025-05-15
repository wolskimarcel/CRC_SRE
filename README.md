# 🚀 CRC project SRI
### 🦄 CRC SRE Unicorn
Monitoring system implementation for a Linux environment as part of the SRE course at ING Hubs Poland.

---

## 🎯 Scope of the Task
The main objectives included:

- 🔧 Configuring system, database, and API monitoring along with alert rules  
- 🤖 Automating monitoring setup using GitHub Actions  
- 📊 Designing and deploying a Grafana dashboard showing:
  - System & database performance metrics
  - API SLIs/SLOs (latency, error rate, availability)
    
---
    
## 🧰 Tech Stack
This project is built using:
* Prometheus (with node_exporter)
* Postgresql
* Grafana

---

## ⚠️ Before You Start
### 🔒 SELinux Configuration

Disabling SELinux (Security-Enhanced Linux) may be necessary when an application, such as Prometheus, encounters restrictions related to SELinux security policies.
The execution of the command
```
$ sudo setenforce 0
```
Should work, however, it may not always be guaranteed to work, and if it does, it's only until the machine is restarted.
Changing the SELinux configuration file will ensure a persistent change in the SELinux mode after the system is restarted. To do this, you need to use the command:
```
$ sudo vi /etc/selinux/config
```
Find the line that starts with SELINUX=. The value of this line determines the SELinux mode.
Change the value from SELINUX=enforcing to SELINUX=permissive. Make sure to save the changes. Save the file and exit the editor.

## 📈 Grafana Dashboard Setup
If using a prebuilt .json file for the dashboard:

- Make sure to update the UID in the JSON to match your own Grafana datasource UID before importing.

## 🐍 API Monitoring Notes
A working Swagger-based API app is already deployed on the VM.
Initially, a custom Python script was developed to collect API metrics, but later the built-in Swagger app was used for final setup.

---

## 💡 Useful Tips
Before using any scripts you have to grant execute permissions to a file.
```
$ chmod +x script_name.sh
$ sudo ./script_name.sh
```

