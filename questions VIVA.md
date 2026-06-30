Question

You receive an alert in Splunk SIEM about multiple failed login attempts from a single IP across different
servers. How would you investigate and respond using SIEM features?

Suggested Answer

- Use Splunk search queries to filter authentication logs by source IP and time range.
- Correlate logs across servers to identify affected accounts.
- Check if the IP is associated with known threat actors using threat intel feeds.
- Trigger an alert rule for brute force detection.
- Coordinate with the firewall team to block the IP and initiate a password reset for impacted accounts.
---

Question
How do you monitor server uptime and service health using Nagios Core on Kali Linux?
Suggested Answer
1. Install Nagios Core on Kali Linux using the package manager or from source.
2. Configure Nagios by editing the main config file: /usr/local/nagios/etc/nagios.cfg.
3. Add hosts and services to monitor in /usr/local/nagios/etc/objects/hosts.cfg and services.cfg.
4. For server uptime, define a ping check; for service health, use check_http, check_ssh, or check_disk.
5. Restart Nagios: systemctl restart nagios or /etc/init.d/nagios restart.
6. Access the web interface (e.g., http://localhost/nagios) to view dashboards, alert status, and logs.
7. Set email notifications for critical service failures by editing contacts.cfg.

---

Question
How can a SOC analyst use IBM QRadar to trace which business systems were affected during a phishing
attack?
Suggested Answer
In QRadar, filter offence details for email logs linked to phishing indicators (e.g., known sender or malicious
links). Use Asset Reconciliation to match recipient emails to systems (IP/hostname). Then, pivot through
correlated logs like login attempts or endpoint alerts to determine which systems were accessed or impacted
post-phish, identifying asset scope.

---

