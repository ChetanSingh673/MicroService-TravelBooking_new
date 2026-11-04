## Grafana Installation Guide via APT Repository
This guide walks you through installing Grafana on a Ubuntu Linux via APT Repository.

**1. Add the Grafana APT key**
```bash
sudo apt-get install -y apt-transport-https software-properties-common wget
wget -q -O - https://apt.grafana.com/gpg.key | gpg --dearmor | sudo tee /etc/apt/keyrings/grafana.gpg > /dev/null
```
**2. Add the Grafana repository**
```bash
echo "deb [signed-by=/etc/apt/keyrings/grafana.gpg] https://apt.grafana.com stable main" | sudo tee -a /etc/apt/sources.list.d/grafana.list
```
**3. Update package list**
```bash
sudo apt-get update
```
**4. Install Grafana**
```bash
sudo apt-get install -y grafana
```
**5. Start and enable Grafana**
```bash
sudo systemctl start grafana-server
sudo systemctl enable grafana-server
```
Grafana is now running as a systemd service and will auto-start on boot.

**6. Access Grafana**
Open your browser and visit:
```bash
http://ip-address:3000
```
Default credentials:

Username: ` admin `

Password: ` admin `  (you'll be prompted to change it at first login)
