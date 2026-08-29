
# EC2 Monitoring and Alerting Project

## 📌 Project Overview
Deployed an Amazon EC2 instance and implemented monitoring and alerting using AWS CloudWatch and Amazon SNS. This project demonstrates hands-on experience with cloud observability, performance monitoring, and automated incident alerting — including verifying that the alerting pipeline actually works end-to-end, not just that it's configured.

---

## ☁️ AWS Services Used
- **Amazon EC2** – Provisioned and managed a virtual server as the monitored resource
- **Amazon CloudWatch** – Monitored CPU utilization metrics and managed alarm state
- **Amazon SNS** – Delivered email notifications when the alarm state changed

---

## ⚙️ Key Implementations
- Launched and configured an EC2 instance (Amazon Linux)
- Created a CloudWatch alarm (`High-CPU-EC2-Alert`) with a condition of CPU Utilization > 50% for 1 datapoint within 1 minute
- Created an SNS topic and subscribed an email endpoint to receive alerts
- Generated CPU load using workload simulation to intentionally cross the alarm threshold
- Monitored the CPUUtilization metric in the CloudWatch console as it climbed and triggered the alarm
- Validated that the alert fired and the notification was actually delivered, not just that the alarm existed

---

## 🐛 Troubleshooting & Validation

Setting up an alarm is easy — confirming it actually works end-to-end is the part that matters. This project was tested, not just configured:

**Verifying the alerting pipeline actually fired**
After simulating the workload spike, I watched the CPUUtilization metric cross the 50% threshold in the CloudWatch console and confirmed the alarm state transitioned from `OK` to `ALARM`. I then checked my email to confirm SNS actually delivered the notification — the metric crossed the threshold at 22:20 UTC, and the alert email arrived at 22:23:16 UTC, roughly 3 minutes end-to-end from threshold breach to notification in my inbox. This confirmed the full chain (metric → alarm → SNS → notification) functioned correctly, not just that each piece was configured in isolation.

---

## 🚀 Key Outcomes
- Implemented real-time CPU monitoring on live cloud infrastructure
- Built and verified a working automated alerting pipeline, end to end
- Confirmed alert delivery time (~3 minutes from threshold breach to notification)
- Gained hands-on experience with cloud observability, alarm configuration, and incident-response workflows

---

## 🧠 Skills Demonstrated
- EC2 Instance Management
- Cloud Monitoring & Observability
- CloudWatch Metrics & Alarms (threshold configuration, state transitions)
- SNS Notification Integration
- End-to-End Alert Validation & Troubleshooting
- Incident Response Workflow Simulation

---

## 📸 Screenshots

### CPU Utilization Spike
![CPU Spike](https://github.com/tylertbrice12-hue/ec2-monitoring-alerting-project/blob/main/cpu.spike.png?raw=true)

### CloudWatch Alarm Triggered
![Alarm Triggered](https://github.com/tylertbrice12-hue/ec2-monitoring-alerting-project/blob/main/alarm.triggered.png?raw=true)

---

## 🔗 Notes
This project simulates a real-world cloud monitoring and incident-response scenario — provisioning a resource, setting a meaningful alert threshold, and confirming the alert actually reaches someone when something goes wrong. That end-to-end verification step is what separates a configured monitoring setup from a *working* one.
