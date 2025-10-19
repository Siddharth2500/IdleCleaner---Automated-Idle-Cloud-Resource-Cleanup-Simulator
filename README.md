# 🚀 IdleCleaner — Automated Idle Cloud Resource Cleanup

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg?logo=python&logoColor=white)  
![Tool](https://img.shields.io/badge/Idle-Cleanup-FF5252.svg?logo=trash)  
![Features](https://img.shields.io/badge/Features-Config%20Checks-4CAF50.svg?logo=gear&logoColor=white)
![Reports](https://img.shields.io/badge/Reports-JSON-2196F3.svg?logo=json)  
![CI/CD](https://img.shields.io/badge/CI/CD-Ready-2088FF.svg?logo=githubactions)  
![Dependencies](https://img.shields.io/badge/Dependencies-None-green.svg?logo=python)

**IdleCleaner** is a **Python 3** tool designed to scan a simulated set of cloud resources, identify those that have been **idle for more than a defined threshold** (e.g., 30 days), and flag them as candidates for cleanup. It’s built for cloud engineers and cost-optimization teams looking to automate resource hygiene.

------

## 🛠 Tech & Languages

| Layer              | Tech / Format               | Purpose                            |
|--------------------|-----------------------------|------------------------------------|
| Language           | **Python 3.10+**            | Core codebase                      |
| Core Logic         | JSON parsing + datetime math | Identify idle resources            |
| Reports            | **JSON**                    | Output list of cleanup candidates  |
| Execution          | Script / Colab / Notebook   | Flexible environment               |
| Logging            | Console & file output       | Summary + persisted audit          |

---

## 🌐 Architecture

Flow:  
1. Step 1 – Load `cloud_resources.json` containing resource-ID, type, creation & last-used dates, status.  
2. Step 2 – Compute `idle_days = now − last_used_at` for each resource.  
3. Step 3 – If `idle_days > threshold` and status is “stopped”, mark resource for cleanup.  
4. Step 4 – Aggregate results and write `cleanup_report.json`, including list of candidates.  
5. Integrate the report into CI/CD pipelines or cost dashboards for action.

---

## ▶️ Run IdleCleaner

```bash
python idlecleaner.py --input data/cloud_resources.json --output data/cleanup_report.json
