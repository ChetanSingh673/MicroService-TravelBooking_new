## Connect Grafana to Prometheus Step-by-Step
Great — let’s wire up Grafana with Prometheus so you can start visualizing all those juicy metrics!

**1. Log in to Grafana**
Go to http://localhost:3000 in your browser.
Default credentials:

* **Username**: admin
* **Password**: admin (you'll be asked to change it if you didn't already)

**2. Add Prometheus as a Data Source**
1. In the left sidebar, click ⚙️ **“Connections” > “Add new connection”**
2. Click **“Search Prometheus in Data sources”**
3. Choose **Prometheus** from the list

**3. Configure Prometheus Connection**
In the **Connection** section:

* **Prometheus server URL**
```bash
http://localhost:9090
```
* Leave all other settings as default (for a local setup)

Click **“Save & test”** — you should get a green checkmark ✅ confirming it's working.

**4. Create Your First Dashboard Panel**
1. Click the + icon in the sidebar → choose **“Dashboards”**

2. Click **“NEW”**

3. Enter a query like:
```bash
rate(prometheus_engine_query_duration_seconds[1m])
```
4. Choose a visualization type: **graph, gauge**, etc.
5. Click **Apply**

Boom — you’ve got real data visualized from Prometheus in Grafana!
